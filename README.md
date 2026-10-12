# BMAHS 官网（VitePress 版）

BMAHS（Big Model Agent Hardware Specification，大模型智能体硬件规范 `bmahs/1.2`）官方网站。
由旧站（`bmahs-site-old`，Python 自建构建器 + JS 渲染防抓取架构）迁移至 VitePress 静态站，中文 / 英文双语，部署在 GitHub Pages，绑定域名 www.bmahs.com。

## 技术栈

- [VitePress](https://vitepress.dev/) 1.x（Vite + Vue 3 默认主题，深度定制样式）
- pnpm 包管理，Node.js 22
- GitHub Actions 自动构建 → GitHub Pages 发布（`actions/deploy-pages` 官方工作流）

## 本地开发

```bash
pnpm install        # 安装依赖
pnpm run dev        # 开发服务器（http://localhost:5173）
pnpm run build      # 构建产物到 docs/.vitepress/dist
pnpm run preview    # 预览构建产物（http://localhost:4173）
```

## 目录结构

```
docs/
├── .vitepress/
│   ├── config.mts          # 站点配置：导航 / 侧边栏 / i18n / SEO / sitemap
│   └── theme/
│       ├── index.ts        # 主题入口（默认主题 + 代码块复制按钮）
│       └── custom.css      # 旧站设计体系移植（变量 + 组件 + 暗色模式）
├── public/                 # 静态资源：CNAME、robots.txt、favicon、logo
├── docs/                   # 中文文档页（/docs/{slug}.html）
├── en/docs/                # 英文文档页（/en/docs/{slug}.html）
├── index.md                # 中文首页
└── en/index.md             # 英文首页
scripts/
├── convert.mjs             # 旧站内容迁移脚本（content/*.html → Markdown）
└── check-tags.mjs          # HTML 标签配平检查
.github/workflows/deploy.yml # Pages 自动部署
```

## 许可

站点内容 CC BY 4.0；示例代码 CC0。详见 `/docs/about.html`。
