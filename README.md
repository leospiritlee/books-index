# 我的书站 · 导航

47 个技术书精读/速学笔记站点的统一导航入口，托管于 GitHub Pages：

**https://leospiritlee.github.io/books-index/**

## 这是什么

每本书都有一个独立的 docsify 在线阅读站（`https://leospiritlee.github.io/<repo>/`），
仓库根目录还放有原 PDF。这个页面把 47 个站点收拢成一个可搜索、可按分类筛选的导航：

- **7 个分类**：课程速学笔记 / Java 生态 / 数据与中间件 / AI / Agent / 计算机基础 / 架构与工程 / 入门手册
- **实时搜索**：书名、副标题、仓库名
- 每张卡片同时给出「进站」和「仓库」两个链接

单文件、零外部依赖：CSS/JS 全内联，无字体/CDN 请求，离线打开也能用。

## 如何更新

索引由本地 `book-upload/build_index.py` 生成。新增书后执行：

```bash
cd book-upload
python3 build_index.py                 # 重新生成 out/books-index.html
cp out/books-index.html nav-site/index.html
cd nav-site && git add -A && git commit -m "chore: refresh index" && git push
```

或用仓库自带的一键脚本：`python3 book-upload/sync_nav.py`

Pages 首次构建约 30–90 秒。

## 来源

书籍 Markdown / PDF 来自本地资料整理目录，站点由
[pdf-book-publisher](https://github.com/leospiritlee) 的构建脚本生成。
