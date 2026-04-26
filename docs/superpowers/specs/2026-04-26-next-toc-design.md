# NexT 文章目录 (TOC) 设计方案

## 概述

为山河博客启用 NexT v8.27.0 内置的文章目录功能，提供更好的阅读导航体验。

## 需求背景

帮助读者快速了解文章结构并跳转到特定章节，提升长文章的阅读体验。

## 设计方案

### 展示策略

- **桌面端**：侧边栏固定目录，滚动时保持可见
- **移动端**：文中折叠目录，点击展开
- **交互**：点击跳转至对应章节，滚动时高亮当前章节

### 技术实现

#### 1. 主题配置

在 `source/_config.next.yml` 中添加/修改 `toc` 配置段：

```yaml
toc:
  enable: true
  number: true
  auto_number: true
  indent: true
  swiper: true
  list_number: true
  max_depth: 3
  min_depth: 1
```

#### 2. 样式定制

通过 NexT CSS 变量自定义目录样式：

```css
:root {
  --toc-width: 200px;
  --toc-font-size: 13px;
  --toc-line-height: 1.6;
}
```

#### 3. 容器布局

确保主题配置中侧边栏目录位置正确：

```yaml
sidebar:
  position: right
  width: 200px
```

### 预期效果

1. 文章页面右侧显示固定目录（桌面端）
2. 目录自动提取 h2、h3 标题
3. 当前章节高亮显示
4. 移动端自动切换为折叠模式
5. 目录样式与博客主题风格统一

## 实施步骤

1. 修改 `source/_config.next.yml` 添加 TOC 配置
2. 添加自定义 CSS 变量
3. 本地验证效果
4. 提交部署

## 验证标准

- [ ] 桌面端文章右侧显示目录
- [ ] 点击目录项跳转到对应章节
- [ ] 滚动时当前章节高亮
- [ ] 移动端目录折叠/展开正常
- [ ] 目录样式与博客风格统一

## 文件变更

| 文件 | 操作 |
|------|------|
| `source/_config.next.yml` | 添加 toc 配置段 |
| `source/_data/styles.styl` 或主题样式文件 | 添加自定义 CSS |

## 优先级

**P0** — 核心功能
**P1** — 样式优化
**P2** — 移动端适配
