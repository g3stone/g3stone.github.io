---
title: "Hugo + GitHub Pages 博客搭建教程"
date: 2024-03-21
draft: false
tags: ["Hugo", "GitHub Pages", "博客搭建", "教程"]
categories: ["技术教程"]
---

在当今数字化时代，拥有一个个人技术博客是展示专业能力、分享技术见解的重要平台。本文将详细介绍如何使用 Hugo 静态网站生成器在 GitHub Pages 上搭建个人技术博客。

## 为什么选择 Hugo + GitHub Pages？

- **Hugo 优势**：
  - 极快的构建速度
  - 简单易用的 Markdown 写作
  - 丰富的主题和插件生态
  - 强大的模板系统
  - 无需数据库，纯静态文件

- **GitHub Pages 优势**：
  - 完全免费
  - 自动 HTTPS
  - 与 Git 完美集成
  - 全球 CDN 加速
  - 自定义域名支持

## 环境准备

1. 安装 Hugo
   ```bash
   # macOS
   brew install hugo
   
   # Windows
   choco install hugo
   
   # Linux
   snap install hugo
   ```

2. 安装 Git
   ```bash
   # macOS
   brew install git
   
   # Windows
   choco install git
   
   # Linux
   sudo apt-get install git
   ```

## 创建博客站点

1. 创建新的 Hugo 站点
   ```bash
   hugo new site my-blog
   cd my-blog
   ```

2. 初始化 Git 仓库
   ```bash
   git init
   ```

3. 添加主题（以 PaperMod 为例）
   ```bash
   git submodule add https://github.com/adityatelange/hugo-PaperMod.git themes/PaperMod
   ```

## 配置博客

1. 创建配置文件 `hugo.toml`：
   ```toml
   baseURL = 'https://your-username.github.io/'
   languageCode = 'zh-cn'
   title = 'Stone 的个人博客'
   theme = 'PaperMod'

   [params]
     defaultTheme = "auto"
     ShowReadingTime = true
     ShowShareButtons = true
     ShowPostNavLinks = true
     ShowBreadCrumbs = true
     ShowCodeCopyButtons = true
     ShowRssButtonInSectionTermList = true
     ShowWordCount = true
     ShowFullTextinRSS = true

   [menu]
     [[menu.main]]
       identifier = "posts"
       name = "文章"
       url = "/posts/"
       weight = 10
     [[menu.main]]
       identifier = "tags"
       name = "标签"
       url = "/tags/"
       weight = 20
     [[menu.main]]
       identifier = "categories"
       name = "分类"
       url = "/categories/"
       weight = 30
     [[menu.main]]
       identifier = "about"
       name = "关于"
       url = "/about/"
       weight = 40
   ```

2. 配置说明：
   - `baseURL`：设置为您的 GitHub Pages 地址
   - `languageCode`：设置为 `zh-cn` 支持中文
   - `theme`：使用 PaperMod 主题
   - `params`：配置主题的各种显示选项
   - `menu`：配置导航菜单，包括文章、标签、分类和关于页面

## 创建内容

1. 创建新文章
   ```bash
   hugo new content posts/my-first-post.md
   ```

2. 编辑文章内容（使用 Markdown 格式）

## 部署到 GitHub Pages

1. 在 GitHub 创建仓库
   - 仓库名格式：`your-username.github.io`
   - 设置为公开仓库

2. 配置 GitHub Actions
   - 在仓库中创建 `.github/workflows/hugo.yml` 文件
   - 配置自动部署工作流

3. 推送代码
   ```bash
   git add .
   git commit -m "Initial commit"
   git remote add origin https://github.com/your-username/your-username.github.io.git
   git push -u origin main
   ```

## 自定义和优化

1. 添加评论系统
   - 推荐使用 Giscus（基于 GitHub Discussions）
   - 或使用 Disqus

2. 添加统计功能
   - Google Analytics
   - 或使用不蒜子统计

3. 优化 SEO
   - 添加 meta 标签
   - 配置 sitemap
   - 添加 robots.txt

## 注意事项

1. 确保 `baseURL` 配置正确
2. 定期备份博客内容
3. 保持主题更新
4. 注意文章版权问题

## 结语

搭建个人技术博客是一个持续学习和改进的过程。通过 Hugo 和 GitHub Pages，我们可以快速搭建一个专业的博客平台，专注于内容创作而不是技术细节。希望这篇教程能帮助您开始博客之旅！

## 参考资源

- [Hugo 官方文档](https://gohugo.io/documentation/)
- [GitHub Pages 文档](https://docs.github.com/cn/pages)
- [PaperMod 主题文档](https://github.com/adityatelange/hugo-PaperMod)
