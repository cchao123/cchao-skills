---
name: feishu2html
description: Convert Feishu wiki/doc documents to HTML pages with full formatting preservation (bold, red text, hyperlinks). Use when user provides a Feishu document URL (wiki/ or docx/) and wants to convert it to HTML, or mentions "飞书转HTML", "Feishu to HTML", "导出飞书文档为网页".
---

# Feishu to HTML Converter

Convert Feishu documents to clean, styled HTML pages while preserving all formatting.

## When to Use

- User provides a Feishu wiki/doc URL and asks to convert to HTML
- User mentions converting Feishu documents to web pages
- User needs offline versions of Feishu documents

## Workflow

### Step 1: Extract Document Token

From the URL, extract the document token:
- Wiki URL: `https://my.feishu.cn/wiki/XXX` → token is `XXX`
- Doc URL: `https://my.feishu.cn/docx/XXX` → token is `XXX`

### Step 2: Read Document Content

Use `feishu_doc` with `action=read` to get the basic text content:

```
feishu_doc action=read doc_token=<TOKEN>
```

This returns plain text without formatting details.

### Step 3: Get Formatting Details (Critical!)

**IMPORTANT**: The plain text from Step 2 does NOT include formatting. You MUST also call `list_blocks` to get:

- **Red text**: `text_color: 1` in text_element_style
- **Bold text**: `bold: true` in text_element_style
- **Hyperlinks**: `link: { url: "..." }` in text_element_style

Use `feishu_doc` with `action=list_blocks`:

```
feishu_doc action=list_blocks doc_token=<TOKEN>
```

This returns detailed block structure with formatting information.

### Step 4: Generate HTML

Create HTML with the following:

1. **Base template**: See [html-template.md](references/html-template.md) for the complete template
2. **Apply formatting**:
   - Bold: `<strong>text</strong>` or `<b>text</b>`
   - Red text: `<span style="color:#ff0000">text</span>`
   - Red + Bold: `<span style="color:#ff0000; font-weight:bold">text</span>`
   - Hyperlinks: `<a href="URL">text</a>`
   - Red hyperlinks: `<a href="URL" style="color:#ff0000; text-decoration:underline">text</a>`

3. **Structure**:
   - Use `<h1>` for main title
   - Use `<h2>` for section headers
   - Use `<h3>` for subsections
   - Use `<p>` for paragraphs
   - Use `<ol>/<ul>` for lists

### Step 5: Save with Date Path

1. **Create date directory**: `output/YYYYMMDD/` (e.g., `output/20260228/`)
2. **Save file**: Save HTML to the date directory with meaningful name
3. **Path format**: `C:\Users\youku\.openclaw\workspace\output\YYYYMMDD\filename.html`

### Step 6: Start HTTP Server (REQUIRED for LAN preview)

**⚠️ 重要：生成HTML后必须启动HTTP服务器，用户需要局域网预览！**

使用Node.js启动服务器：

```bash
node "C:\Users\youku\.openclaw\workspace\skills\feishu2html\scripts\server.js"
```

服务器启动后：
1. **Get local IP**: Run `ipconfig` to find your IPv4 address
2. **Share URL**: `http://YOUR_IP:8080/YYYYMMDD/filename.html`

Example:
```
Directory: output/20260228/
File: huangguan-privacy.html
URL: http://10.20.137.201:8080/20260228/huangguan-privacy.html
```

**注意**：
- 必须使用后台运行 (`background: true`)
- 确认服务启动成功后再返回URL给用户
- 如果8080端口被占用，可以换其他端口（8081, 8082等）

### Step 7: Report to User

1. Report file path, URL, and conversion summary
2. Update memory with task completion

## Example

**Input**: `https://my.feishu.cn/wiki/D3jWw0tzziMtNskJaaWcTyuenep`

**Process**:
1. Token: `D3jWw0tzziMtNskJaaWcTyuenep`
2. Read content → get text
3. List blocks → get formatting (red text, links, etc.)
4. Generate HTML with template + formatting
5. Save to `privacy.html`

**Output**: Clean HTML file with all formatting preserved

## Notes

- Feishu API does NOT return color information in `read` action
- Always use `list_blocks` to get complete formatting
- Decode URL-encoded links (e.g., `https%3A%2F%2F` → `https://`)
- Test the HTML in browser to verify formatting
