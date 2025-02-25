以下是专为 **`life-diary`** 项目设计的 `README.md` 模板，既适合放在项目根目录帮助访客快速上手，也可稍作修改作为博客的引导文章。

````markdown
# 🎨 Life Diary · 我的数字生活花园

![Vercel Deploy Status](https://vercel-badge.xxoo.workers.dev/你的GitHub用户名/life-diary) 
![Hexo Version](https://img.shields.io/badge/Hexo-7.0+-blue?logo=hexo) 
![License MIT](https://img.shields.io/badge/License-MIT-green)

**Life Diary** 是一个基于 [Hexo](https://hexo.io/) 静态博客框架和 [Vercel](https://vercel.com/) 部署的个人博客项目，专注于记录生活碎片、技术思考与灵感瞬间。无需服务器，免费托管，支持 Markdown 写作与自动发布。

**在线访问**: [life-diary.vercel.app](https://life-diary.vercel.app) 或 [你的自定义域名](https://diary.yourname.com)

![博客预览截图](https://cdn.example.com/life-diary-preview.png)

---

## ✨ 功能特性

- 🚀 **极速加载**：Vercel 全球 CDN 加速 + 静态页面缓存
- 📝 **沉浸写作**：Markdown 语法 + 实时本地预览
- 🌓 **主题美化**：Fluid 主题支持暗色模式、自定义导航、社交链接
- 🔍 **全文搜索**：内置本地文章搜索引擎
- 💬 **互动评论**：集成 Giscus（基于 GitHub Discussions）
- 🌐 **多端同步**：GitHub 仓库管理内容，随时随地写作

---

## 🛠️ 快速开始

### 前置条件

- [Node.js](https://nodejs.org/) (v18+)
- [Git](https://git-scm.com/)

### 本地安装

```bash
# 克隆项目
git clone https://github.com/你的GitHub用户名/life-diary.git
cd life-diary

# 安装依赖
npm install

# 启动本地服务器
hexo server
```
访问 `http://localhost:4000` 预览效果。

---

## ⚙️ 配置指南

### 1. 修改博客信息
编辑 `_config.yml`：
```yaml
title: Life Diary
subtitle: 让记忆有迹可循
description: "记录每一刻的感动与成长"
author: 你的名字
language: zh-CN
```

### 2. 自定义 Fluid 主题
编辑 `themes/fluid/_config.yml`：
```yaml
# 导航菜单
navbar:
  menu:
    首页: /
    归档: /archives/
    影集: /gallery/
    关于: /about/

# 社交链接
social:
  GitHub: https://github.com/你的用户名
  Email: mailto:yourname@example.com
```

### 3. 添加文章
```bash
hexo new "夏日露营日记"
```
生成的 Markdown 文件位于 `source/_posts/夏日露营日记.md`。

---

## 🚀 部署到 Vercel

1. **推送代码到 GitHub**
   ```bash
   git add .
   git commit -m "feat: 添加新文章"
   git push origin main
   ```

2. **Vercel 自动构建**  
   每次推送代码后，Vercel 会自动执行 `hexo generate` 并部署到 CDN。

---

## 🌐 绑定自定义域名

1. 在 Vercel 控制台中进入项目 → **Settings** → **Domains**
2. 输入你的域名（如 `diary.yourname.com`）
3. 在域名注册商处添加 CNAME 记录：
   ```plaintext
   主机名: diary
   类型: CNAME
   值: cname.vercel-dns.com
   ```

---

## 📚 写作指南

### 文章 Front-Matter 示例
```markdown
---
title: 冰岛极光追逐日记
date: 2024-02-15
tags:
  - 旅行
  - 摄影
cover: /images/iceland-aurora.jpg
---

正文内容...
```

### 插入图片
1. 将图片放入 `/source/images/`
2. 使用 Markdown 引用：
   ```markdown
   ![冰岛瀑布](/images/iceland-waterfall.jpg)
   ```

---

## 🤝 参与贡献

欢迎提交 Issue 或 Pull Request！  
建议流程：
1. Fork 本仓库
2. 创建分支 (`git checkout -b feature/新功能`)
3. 提交代码 (`git commit -am '添加新功能'`)
4. 推送分支 (`git push origin feature/新功能`)
5. 创建 Pull Request

---

## 📜 开源协议

本项目基于 [MIT License](LICENSE) 授权。

---

## ❓ 常见问题

**Q：本地运行正常，部署后样式丢失？**  
A：检查主题路径配置，确保 `themes/fluid` 已提交到仓库。

**Q：如何添加评论功能？**  
A：在 [Giscus](https://giscus.app/) 生成配置，更新 `themes/fluid/_config.yml` 中的 `comments` 部分。

**Q：自定义域名显示 SSL 错误？**  
A：在 Vercel 的 Domains 设置中重新验证 SSL 证书。
````

---

### 使用说明
1. 将上述内容保存为项目根目录的 `README.md`
2. 替换以下占位符：
   - `你的GitHub用户名`
   - `你的自定义域名`
   - `cdn.example.com`（可删除或替换为实际图片链接）
3. 添加实际截图路径（如 `/source/images/blog-preview.png`）

此 README 既可作为项目文档，也可通过 `hexo new "关于本博客"` 转换为引导文章，帮助访客了解博客的技术背景。
