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

新增书后只跑一条命令：

```bash
python3 book-upload/sync_nav.py
```

它会：重新生成索引 → 拷贝进本仓库 → 有变化才 commit + push →
**顺带检查并修复个人主页的「书站导航」入口**。

主页 `leospiritlee.github.io` 是 Hexo 生成的静态产物，重新 `hexo generate`
会把入口链接冲掉。`patch_home_nav.py` 是幂等的（重复跑无副作用），能从索引
自动读出书站数量修正 `(47)` 这个数字，所以覆盖后跑一次 `sync_nav.py` 即可恢复。

常用开关：

| 命令 | 作用 |
|---|---|
| `sync_nav.py` | 完整流程（含修复主页） |
| `sync_nav.py --no-push` | 只重建并拷贝，纯本地、不碰远端 |
| `sync_nav.py --no-home` | 跳过主页修复 |
| `patch_home_nav.py` | 只体检主页链接（dry-run，不写入） |
| `patch_home_nav.py --apply` | 只修复主页链接 |

Pages 首次构建约 30–90 秒。

## 来源

书籍 Markdown / PDF 来自本地资料整理目录，站点由
[pdf-book-publisher](https://github.com/leospiritlee) 的构建脚本生成。
