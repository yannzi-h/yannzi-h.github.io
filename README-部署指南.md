# 🚀 GitHub Pages 部署指南

## 快速部署步骤

### 1️⃣ 创建 GitHub 仓库

1. 登录 GitHub
2. 创建新仓库，命名为：`yannzi-h.github.io`
   - ⚠️ **重要**：必须用你的 GitHub 用户名替换 `yannzi-h`
   - 例如：如果你的用户名是 `john123`，仓库名就是 `john123.github.io`
3. 设为公开仓库（Public）
4. 勾选"Initialize this repository with a README"

### 2️⃣ 上传文件

**方法 A：通过 GitHub 网页上传（推荐新手）**

1. 进入刚创建的仓库
2. 点击 "Add file" → "Upload files"
3. 把以下文件拖进去：
   - `index.html`
   - `news.html`
   - `opinion.html`
   - `about.html`
   - `style.css`
   - `script.js`
   - `article-template.html`（这个是模板，可以不上传）
4. 填写提交信息，点击 "Commit changes"

**方法 B：通过 Git 命令行上传**

```bash
# 进入项目文件夹
cd /Users/huiqinze/.openclaw/workspace/github-homepage

# 初始化 Git
git init

# 添加所有文件
git add .

# 提交
git commit -m "Initial commit: 纳否新闻社评网站"

# 添加远程仓库（替换为你的仓库地址）
git remote add origin https://github.com/yannzi-h/yannzi-h.github.io.git

# 推送
git push -u origin main
```

### 3️⃣ 启用 GitHub Pages

1. 进入仓库的 **Settings**（设置）
2. 左侧菜单找到 **Pages**
3. 在 "Build and deployment" 下：
   - Source: 选择 **Deploy from a branch**
   - Branch: 选择 **main**，文件夹选 **/(root)**
4. 点击 **Save**

### 4️⃣ 访问你的网站

等待 1-2 分钟，然后访问：
```
https://yannzi-h.github.io
```

⚠️ **注意**：把 `yannzi-h` 换成你的实际 GitHub 用户名

---

## 📝 如何添加新文章

### 添加新闻或社评

1. 复制 `article-template.html`
2. 重命名为 `article-002.html`（按顺序编号）
3. 修改内容：
   - `<title>` - 页面标题
   - `<meta name="description">` - 页面描述
   - `<span class="tag">` - 栏目标签
   - `<h1>` - 文章标题
   - `<p class="meta">` - 日期和作者
   - `<div class="article-content">` - 文章内容
4. 在 `news.html` 或 `opinion.html` 中添加文章链接
5. 在 `index.html` 的头条或列表中更新

### 示例：添加文章链接

在 `news.html` 的 `<div class="list-cards">` 里添加：

```html
<article class="news-item">
  <span class="tag">国际新闻</span>
  <h2><a href="article-002.html">你的新文章标题</a></h2>
  <p class="meta">2026 年 3 月 17 日 · 你的名字</p>
  <p>文章简介...</p>
</article>
```

---

## 🎨 自定义样式

如果想修改颜色，编辑 `style.css` 顶部的变量：

```css
:root {
  --brand: #991b1b;        /* 主色调（红色） */
  --brand-dark: #7f1d1d;   /* 深色变体 */
  --bg: #f3f5f8;           /* 背景色 */
  --card: #ffffff;         /* 卡片背景 */
  --text: #1f2937;         /* 文字颜色 */
}
```

---

## ✅ 检查清单

- [ ] 仓库名是 `你的用户名.github.io`
- [ ] 所有文件已上传
- [ ] Pages 设置已配置（main branch）
- [ ] 等待 1-2 分钟让 GitHub 构建
- [ ] 访问 `https://你的用户名.github.io` 确认网站正常

---

## 🆘 常见问题

**Q: 网站显示 404？**
A: 等几分钟，GitHub 需要时间构建。检查 Pages 设置是否正确。

**Q: 修改后没更新？**
A: 清除浏览器缓存，或等 1-2 分钟让 GitHub 重新构建。

**Q: 想用自定义域名？**
A: 在 Pages 设置的 "Custom domain" 里输入你的域名，然后配置 DNS。

---

**祝你部署顺利！🎉**
