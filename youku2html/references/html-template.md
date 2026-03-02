# HTML Template for Youku2HTML

This template is based on the official 66y game website style (https://game.66y.com/contract.html).

## Complete Template

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>{{TITLE}}</title>
    <style>
        * {
            margin: 0;
            padding: 0;
        }

        body {
            padding: 20px;
        }

        .title {
            border-bottom: .15em solid #000;
            line-height: 5em;
            text-align: center;
        }

        .text-decoration {
            text-decoration: underline;
        }
    </style>
</head>
<body>
    <div>
        <p class="title">
            <strong>{{TITLE}}</strong>
        </p>
        
        {{#if UPDATE_DATE}}
        <p style="line-height: 4em;">
            更新日期：{{UPDATE_DATE}}
        </p>
        {{/if}}
        
        {{#if EFFECTIVE_DATE}}
        <p style="line-height: 4em;">
            生效日期：{{EFFECTIVE_DATE}}
        </p>
        {{/if}}
        
        {{CONTENT}}
    </div>
</body>
</html>
```

## Usage Notes

### Placeholders

- `{{TITLE}}` - Document title (required)
- `{{UPDATE_DATE}}` - Update date (optional)
- `{{EFFECTIVE_DATE}}` - Effective date (optional)
- `{{CONTENT}}` - Main HTML content (required)

### Content Structure (IMPORTANT - Follow 66y Style!)

**Key differences from modern HTML:**
1. **NO h1, h2, h3 tags** - Use `<p>` with `<strong>` instead
2. **NO max-width container** - Full width layout
3. **NO background colors or shadows** - Pure white background
4. **Use inline styles** - Not CSS classes

#### 1. Main Title
```html
<p class="title">
    <strong>文档标题</strong>
</p>
```

#### 2. Section Headers (NOT h2!)
```html
<p style="line-height: 4em;">
    <strong>一、章节标题</strong>
</p>
```

#### 3. Normal Paragraphs
```html
<p style="line-height: 2.5em;text-indent: 2em;">
    段落内容，注意首行缩进2em。
</p>
```

#### 4. Important Text (Bold + Underline)
```html
<strong class="text-decoration">这是重要条款，需要加粗和下划线。</strong>
```

#### 5. Lists (Numbered items as paragraphs)
```html
<p style="line-height: 2.5em;text-indent: 2em;">
    1.1 第一项内容；
</p>

<br />

<p style="line-height: 2.5em;text-indent: 2em;">
    1.2 第二项内容；
</p>
```

#### 6. Spacing Between Sections
Use `<br />` tags to add vertical spacing:
```html
<br />
```

#### 7. Links
```html
<a href="https://example.com">链接文本</a>
```

## Style Reference

### Key CSS Values

- **Title**: `line-height: 5em`, centered, with bottom border
- **Date info**: `line-height: 4em`
- **Section headers**: `line-height: 4em`, `<strong>` wrapped
- **Normal paragraphs**: `line-height: 2.5em`, `text-indent: 2em`
- **Important text**: `<strong class="text-decoration">` (bold + underline)
- **Spacing**: Use `<br />` between paragraphs

### Typography

- **Font**: System default (no custom font-family)
- **Line heights**: Very generous (2.5em - 5em)
- **Indentation**: 2em for first line of paragraphs
- **No max-width**: Content spans full viewport width

### Visual Hierarchy

1. **Title**: Centered with bottom border, largest line-height (5em)
2. **Dates**: Smaller line-height (4em)
3. **Section headers**: Bold with 4em line-height
4. **Body text**: 2.5em line-height with 2em indent
5. **Important text**: Bold + underline

## Complete Example

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>游酷盛世服务协议</title>
    <style>
        * {
            margin: 0;
            padding: 0;
        }
        body {
            padding: 20px;
        }
        .title {
            border-bottom: .15em solid #000;
            line-height: 5em;
            text-align: center;
        }
        .text-decoration {
            text-decoration: underline;
        }
    </style>
</head>
<body>
    <div>
        <p class="title">
            <strong>游酷盛世服务协议</strong>
        </p>
        
        <p style="line-height: 4em;">
            更新日期：2026年02月03日
        </p>
        
        <p style="line-height: 4em;">
            生效日期：2026年02月03日
        </p>
        
        <p style="line-height: 4em;">
            <strong>【导言】</strong>
        </p>
        
        <p style="line-height: 2.5em;text-indent: 2em;">
            欢迎您使用和接受游酷盛世科技（北京）有限公司（以下简称"游酷盛世公司"）提供的游戏产品和服务。
        </p>
        
        <br />
        
        <p style="line-height: 2.5em;text-indent: 2em;">
            在您使用游酷盛世公司提供的游戏产品和/或服务之前，请务必审慎阅读本协议，充分理解各条款内容。<strong class="text-decoration">前述免责或者限制责任条款等重要内容将以加粗、下划线方式提示您注意，您应重点阅读。</strong>
        </p>
        
        <br />
        
        <p style="line-height: 4em;">
            <strong>【重要须知】</strong>
        </p>
        
        <p style="line-height: 2.5em;text-indent: 2em;">
            一、您在使用游酷盛世公司提供的游戏产品之前，请务必认真阅读并充分理解本协议。
        </p>
        
        <br />
        
        <p style="line-height: 2.5em;text-indent: 2em;">
            二、<strong class="text-decoration">当您完成阅读勾选注册弹窗底部勾选框或点击"同意"按钮时，即表示您已充分理解本协议并承诺作为本协议的一方当事人接受本协议的约束。</strong>
        </p>
    </div>
</body>
</html>
```

## Important Notes

1. **DO NOT use modern CSS frameworks** - Keep it simple like 66y.com
2. **DO NOT use h1-h6 tags** - Use `<p>` with `<strong>` instead
3. **DO NOT add max-width or containers** - Full width layout
4. **DO NOT add background colors** - White background only
5. **DO use inline styles** - Matches 66y.com pattern
6. **DO use `<br />` for spacing** - Not margin/padding
7. **DO use generous line-heights** - 2.5em to 5em
8. **DO indent first lines** - `text-indent: 2em` for paragraphs
