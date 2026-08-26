# GitHub 每日热榜

![GitHub 每日热榜横幅](assets/github-daily-trending-banner.png)

自动生成并发布 GitHub Trending 今日热榜的静态网站。

## 在线访问

- 最新一期（固定入口）：<https://neverslack.cn/news/github/github-daily-trending/>
- 历史页面：`https://neverslack.cn/news/github/github-trending-YYYY-MM-DD.html`

## 内容与功能

- 每期收录至少 15 个 GitHub 今日热门项目。
- 展示项目简介、主要语言、累计 Star、Fork 和当日新增 Star。
- 桌面端三列、移动端单列，并包含渐变、光晕、卡片入场等动态效果。
- 历史页面保留在 `news/github/` 下，页面底部可跳转至昨日热榜。
- 固定入口会自动跳转到最新一期，无需输入日期。

## 目录结构

```text
news/
└── github/
    ├── favicon.svg                         # 浏览器标签页图标
    ├── github-trending-YYYY-MM-DD.html     # 每日热榜页面
    └── github-daily-trending/
        └── index.html                      # 最新一期固定入口
```

## 每日发布流程

1. 查询 GitHub Trending 的 Today 榜单。
2. 新建 `news/github/github-trending-YYYY-MM-DD.html`。
3. 更新 `news/github/github-daily-trending/index.html` 中的跳转目标。
4. 提交并推送至 `master` 分支。
5. Cloudflare Pages 自动部署到 `neverslack.cn`。

## 部署配置

- GitHub 仓库：<https://github.com/CharmingHue/github-daily-trending>
- 托管平台：Cloudflare Pages
- 生产分支：`master`
- 框架预设：无
- 构建命令：`exit 0`
- 构建输出目录：`.`
- 自定义域名：`neverslack.cn`

## 本地预览

直接用浏览器打开任意 `news/github/github-trending-YYYY-MM-DD.html` 文件即可。

## 自动化

Codex 已配置每日自动任务（中国标准时间上午 9 点），负责生成当天热榜、更新固定入口并推送发布。若推送或部署失败，任务会在当前任务中报告原因。
