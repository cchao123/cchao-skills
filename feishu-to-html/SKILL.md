---
name: feishu-to-html
description: |
  将飞书文档转换为移动端友好的 HTML 页面。当用户需要将飞书文档转为 HTML 时激活。
---

# 飞书文档转 HTML

## 工作流程

1. 使用 `feishu_doc` 读取飞书文档内容
2. 使用本 skill 定义的 HTML 模板生成页面
3. 保存到 `workspace/output/YYYY-MM-DD/` 目录

## HTML 模板

**必须使用以下样式模板**，确保移动端兼容：

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>文档标题</title>
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
        h4 {
            font-size: 15px;
            margin: 12px 0 8px;
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
        .red {
            color: #ff0000;
        }
        .red-bold {
            color: #ff0000;
            font-weight: bold;
        }
        .important {
            font-weight: bold;
            text-decoration: underline;
        }
    </style>
</head>
<body>
    <!-- 内容区域 -->
</body>
</html>
```

## 关键样式规则

**必须包含以下样式**，解决移动端问题：

| 问题 | 解决方案 |
|------|----------|
| 宽度超出屏幕 | `* { box-sizing: border-box; }` + `html, body { overflow-x: hidden; }` |
| 长字符串不换行 | `p { word-break: break-all; overflow-wrap: break-word; }` |
| padding 过大 | 移动端使用 `padding: 0 15px` |

## 输出路径

- 目录：`workspace/output/YYYY-MM-DD/`
- 文件名：根据文档内容命名，如 `privacy.html`、`agreement.html`

## 本地预览服务

如需启动本地 HTTP 服务预览：

```powershell
npx -y serve -l 8080 C:\Users\youku\.openclaw\workspace\output
```

访问地址：`http://<本机IP>:8080/YYYY-MM-DD/<文件名>.html`

关闭服务：使用 `process` 工具 `action: kill`
