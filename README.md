# Kevin 的笔记 · Hexo + Butterfly 示例

写一篇 Markdown 文章，使用 Butterfly 生成博客首页与文章页。已配置归档、标签、分类和关于页面。

博客地址：https://zzcodd.github.io/

源码仓库：https://github.com/zzcodd/zzcodd.github.io

## 本地预览

在本目录执行：

```bash
npm ci
npm start
```

打开 http://localhost:4000/ 。在终端按 Ctrl+C 停止预览。

## 修改内容

- `source/_posts/first-blog.md`：示例文章，可以直接修改标题和正文。
- `_config.yml`：站点标题、作者、语言和线上网址。
- `_config.local.yml`：本地预览的网址覆盖配置，`npm start` 自动加载。
- `_config.butterfly.yml`：菜单、头像、颜色和侧栏。
- `source/about/index.md`：关于页面。
- `source/images/`：本地示例图片。

修改文章后刷新浏览器即可。修改配置后重新启动预览。

## 写下一篇文章

```bash
npm run new -- "第二篇文章"
```

新文件会出现在 `source/_posts/`。

## 生成可发布的网站

```bash
npm run build
```

生成结果在 `public/`。

## 更新线上博客

修改文章或配置后，把改动提交到 GitHub 仓库的 `main` 分支。

仓库的 `.github/workflows/pages.yml` 会自动安装依赖、生成网站并发布到 GitHub Pages。发布进度和失败原因可以在仓库的 Actions 页面查看。

```bash
git add source/_posts/first-blog.md
git commit -m "Update first blog post"
git push origin main
```

网页端也可以直接编辑仓库中的 Markdown 文件并提交到 `main`。

GitHub Pages 的发布来源设为 GitHub Actions。`node_modules/`、`public/`、缓存和本地预览截图不会提交到源码仓库。保存完整源码、文章、配置和 `package-lock.json`；生成目录 `public/` 可以随时重新生成。

官方参考：[Hexo 的 GitHub Pages 教程](https://hexo.io/zh-cn/docs/github-pages)。
