# 自托管指南 — Demo

面向海外华人的 Homelab 教程静态站。GitHub Pages 部署。

## 本地预览

```bash
# Python 自带 HTTP 服务器
cd /root/selfhost-guide
python3 -m http.server 8000
# 访问 http://localhost:8000
```

## 部署到 GitHub Pages

### 方法一：直接 push（推荐）

```bash
# 1. 在 GitHub 创建仓库 selfhost-guide（Public）
# 2. 本地推送
cd /root/selfhost-guide
git init
git add -A
git commit -m "init: selfhost guide demo"
git remote add origin https://github.com/fulankizao/selfhost-guide.git
git branch -M main
git push -u origin main

# 3. 去 GitHub 仓库 Settings → Pages
#    Source: Deploy from branch → main → / (root) → Save
# 4. 等 1-2 分钟，访问 https://fulankizao.github.io/selfhost-guide/
```

### 方法二：gh-pages 分支

```bash
# 安装 gh-pages 工具
npm install -g gh-pages

# 部署到 gh-pages 分支
gh-pages -d /root/selfhost-guide
```

## SEO 检查清单

- [x] 每页有 `meta description`
- [x] `canonical` URL
- [x] `ld+json` 结构化数据
- [ ] 提交 Google Search Console
- [ ] 添加 sitemap.xml
- [ ] 添加 robots.txt

## 目录结构

```
selfhost-guide/
├── index.html          # 首页
├── about.html          # 关于
├── style.css           # 样式
├── articles/
│   ├── hermes-agent-setup.html   # Hermes Agent 指南
│   ├── wsl-setup.html            # WSL 环境配置
│   └── fastapi-deploy.html       # FastAPI 部署
└── README.md           # 本文件
```