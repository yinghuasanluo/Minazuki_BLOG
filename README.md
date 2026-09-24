# 博客内容维护

本站使用 Astro 构建，部署路径配置在 `astro.config.mjs`，站点名称、导航和功能开关在 `src/config.ts`。

## 填写页面

- `src/pages/about.astro`：关于页面目前留空。将个人介绍放进 `<BlankPageLayout>` 内即可。
- `src/pages/projects.astro`：项目页面目前留空。写入真实项目后，再在 `src/config.ts` 的 `menu` 中加入 `{ name: "projects", url: "/projects" }`，并为各语言文件添加 `projects` 文案。
- `src/content/blog/`：每篇 Markdown 或 MDX 文件都是一篇文章。文章至少需要 `title`、`description` 和 `pubDate`。

## 发布文章

推荐使用以下文章头部，再根据实际内容填写正文：

```yaml
---
title: 文章标题
description: 用一句话说明文章内容
pubDate: 2026-09-24
categories: [技术笔记]
tags: [Astro]
excerpt: 首页卡片上显示的简短摘要
---
```

首页的精选文章需要至少三篇文章设置 `featured: true` 才会出现；可选的 `featuredOrder` 数字越小越靠前。分类卡片在 `src/config.ts` 的 `home_categories` 配置，目前关闭，等分类有真实内容和封面后再启用。评论系统也保持关闭，启用前需在同一配置文件中填写所选服务的有效参数。

构建命令：`pnpm build`。
