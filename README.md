# ainixiaojie 的博客

基于 [Hexo](https://hexo.io/) + [Fluid](https://github.com/fluid-dev/hexo-theme-fluid) 主题的个人博客，通过 GitHub Pages 部署：

- 站点地址：https://ainixiaojie.github.io/
- 源码仓库：https://github.com/ainixiaojie/ainixiaojie.github.io

## 分支说明

| 分支 | 内容 | 说明 |
|---|---|---|
| `main` | Hexo 源码 | 文章、主题、配置，日常开发分支 |
| `master` | 部署产物 | GitHub Pages 展示内容，**不要手动改动**，由部署流程自动生成 |

## 本地开发

```bash
npm install        # 安装依赖
npm run server     # 本地预览（默认 http://localhost:4000）
npm run build      # 生成静态站点到 public/
npm run deploy     # 手动部署（GitHub Actions 会自动部署，通常不需要）
```

## 发布流程

推送 `main` 分支即可自动构建并部署：

```bash
git add .
git commit -m "描述本次改动"
git push
```

GitHub Actions 会自动执行 `hexo generate` 并把生成的静态站点推送到 `master` 分支。

## 目录结构

```
├── _config.yml        # 站点配置
├── scaffolds/         # 文章模板
├── source/
│   ├── _posts/        # 博客文章（Markdown）
│   └── img/           # 文章图片资源
├── themes/fluid/      # 主题源码（直接修改即生效）
├── public/            # 生成产物（不入库）
└── .github/workflows/ # 自动部署配置
```

## 注意事项

- 视频等大文件：GitHub 单文件上限 100MB，超限会导致部署失败；大文件请放网盘 / CDN 后以链接引用。
- `public/`、`node_modules/` 不入库，克隆后执行 `npm install` 和 `npm run build` 即可还原。
