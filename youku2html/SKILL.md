---
name: youku2html
description: Convert Feishu documents or text content to formatted HTML pages with 66y game website style. Use when user says "使用youku2html输出html" or asks to convert documents to HTML with 游酷盛世 style.
---

# Youku to HTML Converter

Convert Feishu documents or text content to clean, professional HTML pages styled like the official 66y game website.

## When to Use

- User explicitly says: **"使用youku2html输出html"**
- User wants to convert Feishu docx to HTML with 游酷盛世 style
- User provides text content and wants formatted HTML output
- User needs HTML pages for game agreements, privacy policies, etc.

## Workflow

### Step 1: Identify Input Type

Determine what the user provided:
1. **Feishu docx/wiki URL** → Extract document content
2. **Text content** → Use directly

### Step 2: Get Content

#### Option A: Feishu Document

1. **Extract token** from URL:
   - Wiki URL: `https://xxx.feishu.cn/wiki/XXX` → token is `XXX`
   - Doc URL: `https://xxx.feishu.cn/docx/XXX` → token is `XXX`

2. **Get document info**:
```
feishu_wiki action=get token=<TOKEN>
```

3. **Read content**:
```
feishu_doc action=read doc_token=<OBJ_TOKEN>
```

4. **Get formatting** (IMPORTANT for red text, bold, links):
```
feishu_doc action=list_blocks doc_token=<OBJ_TOKEN>
```

#### Option B: Text Content

Use the text content directly provided by user.

### Step 3: Generate HTML

Use the template from [html-template.md](references/html-template.md):

1. **Replace placeholders**:
   - `{{TITLE}}` → Document title
   - `{{UPDATE_DATE}}` → Update date (if available)
   - `{{EFFECTIVE_DATE}}` → Effective date (if available)
   - `{{CONTENT}}` → Main content with proper HTML tags

2. **Apply formatting**:
   - **Important text**: `<span class="important">text</span>` (bold + underline)
   - **Bold text**: `<strong>text</strong>` or `<b>text</b>`
   - **Section headers**: `<h2>Section Title</h2>`
   - **Paragraphs**: `<p>text</p>`
   - **Lists**: `<ol>` for numbered, `<ul>` for bullets

3. **Style features**:
   - Clean white background
   - Max-width: 1200px for readability
   - Professional typography
   - Highlighted important clauses

### Step 4: Save HTML File

1. **Create date directory**: `output/YYYYMMDD/`
2. **Choose filename**: Use meaningful name based on content
   - Agreement: `youku-service-agreement.html`
   - Privacy policy: `privacy-policy.html`
   - Account cancellation: `account-cancellation.html`
3. **Full path**: `C:\Users\youku\.openclaw\workspace\output\YYYYMMDD\filename.html`

### Step 5: Start HTTP Server (REQUIRED)

**⚠️ 必须启动HTTP服务器供用户局域网预览！**

1. **Start server** (if not already running):
```bash
node "C:\Users\youku\.openclaw\workspace\skills\youku2html\scripts\server.js"
```

2. **Check if server is running**:
```bash
netstat -ano | findstr :8080 | findstr LISTENING
```

3. **Get local IP**:
```bash
ipconfig
```
Look for IPv4 address (e.g., `10.20.137.201`)

4. **Construct preview URL**:
```
http://YOUR_IP:8080/YYYYMMDD/filename.html
```

Example: `http://10.20.137.201:8080/20260302/youku-service-agreement.html`

### Step 6: Report to User

Provide:
1. ✅ HTML file path
2. 🌐 Preview URL (for LAN access)
3. 📝 Summary of what was converted

Example response:
```
🐟 搞定！HTML已生成。

**文件路径：** output/20260302/youku-service-agreement.html
**预览地址：** http://10.20.137.201:8080/20260302/youku-service-agreement.html

**样式特点：**
- ✅ 游酷盛世官网风格
- ✅ 简洁白色背景
- ✅ 重要条款加粗+下划线
- ✅ 移动端友好

直接访问即可～
```

## HTML Template Style

Based on https://game.66y.com/contract.html:

- **Clean layout**: White background, no container shadows
- **Typography**: System fonts (PingFang SC, Microsoft YaHei)
- **Max width**: 1200px for optimal reading
- **Important text**: Bold + underline for key clauses
- **Headers**: Clear hierarchy (h1, h2, h3)
- **Responsive**: Mobile-friendly design

## Examples

### Example 1: Feishu Document

**Input**: `https://mcn96c8o1wjs.feishu.cn/wiki/XXX`

**Process**:
1. Extract token
2. Read document content
3. Generate HTML with template
4. Save to `output/20260302/agreement.html`
5. Start/verify server on port 8080
6. Return preview URL

### Example 2: Text Content

**Input**: User provides text directly

**Process**:
1. Parse text content
2. Structure into sections
3. Generate HTML with template
4. Save and provide preview URL

## Notes

- Always use port **8080** for consistency
- Server can run in background (check with netstat)
- Important clauses should use `.important` class
- Keep the style consistent with 66y official website
- Mobile-responsive design is essential
