---
title: 从零开始：用 Hexo + Vercel 搭建「Life Diary」个人博客
date: 2025-02-25
tags: 
  - 技术教程
  - 博客搭建
  - Hexo
  - Vercel
---

Hexo 静态博客框架和 Vercel 部署服务教程
<!-- more -->

![Hexo + Vercel 博客封面](https://cdn.example.com/hexo-vercel-banner.png)
欢迎来到 **Life Diary** ！本文将手把手教你如何从零开始，用 Hexo 静态博客框架和 Vercel 部署服务，搭建属于你自己的「生活日记」博客。无需服务器，全程免费，且支持自定义域名！

---

### 一、博客效果预览
最终你将拥有：
- 🚀 自动构建 + 全球 CDN 加速的博客
- 🎨 简洁优雅的 [Fluid 主题](https://hexo.fluid-dev.com/)界面
- 🔗 专属域名（如 `diary.yourname.com`）
- 📝 Markdown 写作 + 实时发布

[点击查看演示站](https://life-diary-minty.vercel.app)

---

### 二、环境准备
#### 1. 安装 Node.js
访问 [Node.js 官网](https://nodejs.org/) 下载 **LTS 版本**，安装完成后验证：
```bash
node -v  # 需显示 v18.x 或更高
npm -v   # 需显示 9.x 或更高
```

#### 2. 安装 Git
从 [Git 官网](https://git-scm.com/) 下载安装，验证：
```bash
git --version  # 需显示 2.40.x 或更高
```

---

### 三、创建 Hexo 项目
#### 1. 初始化博客
```bash
# 安装 Hexo 命令行工具
npm install -g hexo-cli

# 创建项目文件夹
hexo init life-diary
cd life-diary

# 安装依赖
npm install
```

#### 2. 本地启动
```bash
hexo server
```
访问 `http://localhost:4000`，你会看到默认主题的博客：

![Hexo 默认主题](https://cdn.example.com/hexo-default-theme.png)

---

### 四、配置 Fluid 主题
#### 1. 下载主题
在项目目录中运行：
```bash
git clone https://github.com/fluid-dev/hexo-theme-fluid.git themes/fluid
```

#### 2. 启用主题
修改 **`_config.yml`**：
```yaml {hl_lines=[3]}
# 约第 95 行
theme: landscape  # 改为 fluid
theme: fluid
```

#### 3. 基础配置
修改 **`_config.yml`** 中的博客信息：
```yaml
title: Life Diary
subtitle: 记录每一刻的感动
description: "我的私人数字花园🌱"
author: 你的名字
language: zh-CN
```

#### 4. 个性化设置
在 **`themes/fluid/_config.yml`** 中配置：
```yaml
navbar:
  menu:
    首页: /
    归档: /archives/
    影集: /gallery/
    关于: /about/

about:
  avatar: /img/avatar.jpg  # 将头像图片放入 /source/img/
```

---

### 五、部署到 Vercel
#### 1. 推送代码到 GitHub
```bash
git init
git add .
git commit -m "Init Life Diary blog"
git branch -M main
git remote add origin https://github.com/${user}/life-diary.git
git push -u origin main
```

#### 2. 在 Vercel 部署
1. 访问 [Vercel](https://vercel.com) 并登录 GitHub 账号
2. 点击 **Add New Project** → 选择 `life-diary` 仓库
3. 配置部署参数：
   - **Build Command**: `hexo generate`
   - **Output Directory**: `public`
4. 点击 **Deploy**，1 分钟后你的博客将上线！

![Vercel 部署成功](https://cdn.example.com/vercel-deploy-success.png)

---

### 六、绑定自定义域名
1. 在 Vercel 控制台进入项目 → **Settings** → **Domains**
2. 输入你的域名（如 `diary.yourname.com`）
3. 按照提示到域名注册商添加 **CNAME 记录**：
   ```plaintext
   主机记录：diary
   记录类型：CNAME
   记录值：cname.vercel-dns.com
   ```

---

### 七、开始写作！
#### 1. 创建新文章
```bash
hexo new "北海道冬日旅行笔记"
```
编辑生成的 Markdown 文件：`source/_posts/北海道冬日旅行笔记.md`

#### 2. 插入图片
将图片放入 `/source/images/`，用 Markdown 引用：
```markdown
![函馆山夜景](/images/hakodate-night.jpg)
```

#### 3. 发布更新
```bash
git add .
git commit -m "添加北海道游记"
git push origin main
```
Vercel 会自动重新部署，1 分钟后文章生效！

---

### 八、高级技巧
#### 1. 添加本地搜索
安装插件：
```bash
npm install hexo-generator-searchdb --save
```
在 **`_config.yml`** 中添加：
```yaml
search:
  path: search.xml
  field: post
```

#### 2. 启用评论系统
推荐使用 [Giscus](https://giscus.app/)（基于 GitHub Discussions），在 Fluid 主题配置中：
```yaml
comments:
  enable: true
  type: giscus
  giscus:
    repo: 你的用户名/life-diary
    repo_id: YOUR_REPO_ID
    category: Announcements
```

---

### 九、常见问题
#### Q1：部署失败提示 "hexo: command not found"
**解决**：在 `package.json` 中声明 Hexo 依赖：
```json
"dependencies": {
  "hexo": "^7.0.0"
}
```
然后运行 `npm install && git push`

#### Q2：如何修改文章永久链接？
在 **`_config.yml`** 中配置：
```yaml
permalink: :year/:month/:title/
```

---

现在，你的「Life Diary」博客已整装待发！接下来可以：
- ✨ 在 `/source/about/index.md` 撰写个人简介
- 📂 创建分类和标签
- 🌐 在 [Webring](https://webring.xxiivv.com/) 加入博客联盟



> **提示**：本文已自动适配你的项目名 `life-diary`，请将文中 **`你的用户名`** 替换为你的 GitHub 账号，**`yourname.com`** 替换为你的域名。