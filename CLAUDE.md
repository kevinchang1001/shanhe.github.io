# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 项目概述

Hexo 静态博客，使用 pnpm 作为包管理器，主题为 landscape。

## 常用命令

```bash
pnpm server    # 启动本地开发服务器（默认 http://localhost:4000）
pnpm build    # 生成静态文件到 public/ 目录
pnpm clean    # 清理 generated 文件和缓存
pnpm deploy   # 部署到远程站点
```

## 目录结构

| 目录 | 用途 |
|------|------|
| `source/_posts/` | 博客文章（Markdown 格式） |
| `source/_drafts/` | 草稿文章 |
| `public/` | 生成的静态网站文件 |
| `themes/landscape/` | 当前使用的主题 |
| `scaffolds/` | 文章/页面模板 |

## 文章管理

- 新建文章：`hexo new "标题"`（在 `source/_posts/` 生成 `.md` 文件）
- 文章模板定义在 `scaffolds/` 目录
- Front-matter 字段：`title`, `date`, `tags`, `categories`, `comments` 等

## 主题配置

- 当前主题：`landscape`（定义在 `_config.yml` 的 `theme` 字段）
- 主题配置：`themes/landscape/_config.yml`
- 更换主题需修改根目录 `_config.yml` 中的 `theme` 字段

## 部署配置

`_config.yml` 中的 `deploy` 字段配置部署目标，支持 git、heroku 等多种方式。

## 注意事项

- `public/` 目录由 `hexo generate` 自动生成，无需手动编辑
- `db.json` 是 Hexo 的数据库文件，记录已处理的文件状态
- 更改主题后需运行 `hexo clean && hexo generate`
