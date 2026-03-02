# HTML Template for Feishu Documents

## Base Template

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>[Document Title]</title>
    <style>
        * {
            box-sizing: border-box;
        }
        html {
            overflow-x: hidden;
        }
        body {
            display: block;
            width: 100%;
            max-width: 1200px;
            padding: 0 15px;
            margin: 20px auto;
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, "PingFang SC", "Microsoft YaHei", sans-serif;
            line-height: 1.6;
            color: #333;
            overflow-x: hidden;
        }
        h1 {
            font-size: 24px;
            margin: 20px 0;
            text-align: center;
            padding-bottom: 15px;
            border-bottom: 1px solid #ddd;
        }
        h2 {
            font-size: 18px;
            margin: 20px 0 10px;
        }
        h3 {
            font-size: 16px;
            margin: 15px 0 10px;
        }
        p {
            margin: 10px 0;
            word-break: break-all;
            overflow-wrap: break-word;
        }
        ol, ul {
            margin: 10px 0;
            padding-left: 30px;
        }
        li {
            margin: 5px 0;
        }
        .important {
            font-weight: bold;
            text-decoration: underline;
        }
        .red {
            color: #ff0000;
        }
        .red-bold {
            color: #ff0000;
            font-weight: bold;
        }
        .update-note {
            background: #f5f5f5;
            padding: 10px 15px;
            border-radius: 5px;
            margin: 15px 0;
        }
        a {
            color: #337ab7;
            text-decoration: none;
        }
        a:hover {
            text-decoration: underline;
        }
    </style>
</head>
<body>
    <!-- Document content here -->
</body>
</html>
```

## Formatting Patterns

### Text Formatting

| Feishu Style | HTML Code |
|-------------|-----------|
| Bold | `<strong>text</strong>` |
| Red text | `<span style="color:#ff0000">text</span>` |
| Red + Bold | `<span style="color:#ff0000; font-weight:bold">text</span>` |
| Underline | `<u>text</u>` |

### Links

| Type | HTML Code |
|------|-----------|
| Normal link | `<a href="URL">text</a>` |
| Bold link | `<a href="URL"><strong>text</strong></a>` |
| Red link | `<a href="URL" style="color:#ff0000">text</a>` |
| Red + Bold + Underline link | `<a href="URL" style="color:#ff0000; font-weight:bold; text-decoration:underline">text</a>` |

### Special Sections

**Update notice box**:
```html
<div class="update-note">
    <p><strong>更新提示：</strong></p>
    <p>Update content here...</p>
</div>
```

**Important note**:
```html
<p><span class="important">Important:</span> content here...</p>
```

## Structure Guidelines

1. **Title**: Use `<h1>` for the main document title
2. **Sections**: Use `<h2>` for major sections (e.g., "1. 如何收集信息")
3. **Subsections**: Use `<h3>` for subsections (e.g., "1.1 注册登录")
4. **Paragraphs**: Use `<p>` for regular text
5. **Lists**: 
   - Use `<ol>` for numbered lists
   - Use `<ul>` for bullet lists
   - Use `<li>` for list items

## Best Practices

1. **Responsive**: Template is already responsive with `max-width: 1200px`
2. **Chinese fonts**: Uses system fonts including PingFang SC and Microsoft YaHei
3. **Readability**: Good line-height (1.6) and spacing
4. **Clean**: Minimal styling, focus on content

## Example Output

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>隐私政策</title>
    <style>
        /* ... styles ... */
    </style>
</head>
<body>
    <h1>隐私政策</h1>
    
    <div class="update-note">
        <p><strong>更新提示：</strong></p>
        <p>新增了敏感信息收集概要</p>
    </div>

    <h2>【敏感信息收集概要】</h2>
    <p>我们对于<span class="red-bold">敏感个人信息</span>进行加粗提示。</p>
    
    <p>具体请查阅<a href="https://example.com/policy.html">《隐私政策》</a>了解详情。</p>
</body>
</html>
```
