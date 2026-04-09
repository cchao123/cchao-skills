---
name: commit-no-claude
description: Use when the user asks to commit, submit, or check in code changes. Analyzes git diff, generates clean commit messages, and ensures no AI-related metadata leaks into commit history.
---

# Commit Without AI Traces

Analyze current code changes and create a clean git commit with zero AI-related metadata.

## When to Use

- User says "提交", "commit", "帮我提交", "帮我commit" or similar
- User asks to check in / submit / save changes

## Workflow

```
用户请求提交 → git status & diff → 分析变更 → 拟定 message → 用户确认 → 执行 commit
```

### Step 1: Collect Change Context

Run these in parallel:

```bash
git status
git diff                # unstaged changes
git diff --staged       # staged changes
git log --oneline -5    # recent history for style reference
```

If there are no changes at all, inform the user and stop.

### Step 2: Analyze and Stage

- If all changes are already staged → proceed
- If nothing is staged but there are unstaged changes → ask user whether to stage all or select files
- If some files are staged and some are not → list the unstaged files and ask whether to include them
- **Never blindly `git add -A`** — sensitive files (.env, credentials, build artifacts) must be excluded

### Step 3: Draft Commit Message

Generate a commit message following the project's existing style (check `git log`).

**Message rules:**
- Use **conventional commit** format if the project already follows it (`feat:`, `fix:`, `docs:`, `refactor:`, `chore:`, etc.)
- Otherwise use a concise descriptive sentence
- Default language: **match the user's request language**
- Focus on **why** the change was made, not just **what** was changed
- Keep first line under 72 characters

### Step 4: The Iron Rule — Strip All AI Metadata

<HARD-GATE>
The commit message and the commit itself must NOT contain ANY AI attribution.
</HARD-GATE>

**Forbidden patterns (exhaustive):**

| Category | Forbidden Strings |
|----------|-------------------|
| Co-author | `Co-Authored-By`, `Co-authored-by` |
| Claude | `Claude`, `claude`, `Claude Code`, `claude-opus`, `claude-sonnet`, `Anthropic`, `anthropic`, `noreply@anthropic.com` |
| Cursor | `Cursor`, `cursor`, `cursor.sh` |
| AI generic | `AI-generated`, `Generated with AI`, `auto-generated` |
| Other tools | `GitHub Copilot`, `ChatGPT`, `Windsurf`, `Aider`, `Cline`, `Continue` |

**Additional rules:**
- Do NOT use `--trailer` or `--footnote` to add any co-author
- Do NOT use git commit templates that contain AI attribution
- If a pre-commit hook adds AI co-author lines, inform the user — do NOT silently bypass with `--no-verify`
- The commit author name and email must be the user's own git identity

**Verification:** After drafting the message, scan it for every forbidden pattern above before presenting to user.

### Step 5: Confirm and Commit

Present the commit message to the user. Wait for approval, then execute:

```bash
git commit -m "$(cat <<'EOF'
<commit message here>
EOF
)"
```

After commit, run `git status` to confirm success.

## Edge Cases

| Situation | Action |
|-----------|--------|
| Pre-commit hook fails | Investigate the failure, fix the issue, re-commit |
| Merge conflicts in staging | Inform user, do not force |
| Large binary files staged | Warn user, suggest `.gitignore` |
| `package-lock.json` / `pnpm-lock.yaml` changed | Include if intentional, warn if unexpected |
| Commit fails (empty message) | Re-draft with user |

## Anti-Patterns

- Do NOT use `git commit -am` — skips proper staging review
- Do NOT use `git add .` or `git add -A` — stage files explicitly
- Do NOT use `--no-verify` to bypass hooks unless user explicitly asks
- Do NOT amend commits (`--amend`) unless user explicitly requests
- Do NOT push after committing unless user explicitly asks
