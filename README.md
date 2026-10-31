# AITOOLS

深色极简风格的 AI 工具导航站。单文件 HTML、零依赖，收录 42 款常用 AI 工具，支持 **5 种语言**、分类浏览、搜索与收藏。

**线上地址**：https://matongqiao-lab.github.io/aitools/

## 功能

- 6 大分类：对话助手 / AI 绘图 / AI 视频 / AI 音频 / 编程开发 / 办公效率
- 5 种语言切换：简体中文、繁體中文、English、日本語、한국어
  - 界面文案、分类名、标签、42 条工具简介全部随语言切换
  - 首次访问按浏览器语言自动匹配，手动选择后写入 localStorage
- 搜索（名称 / 简介 / 标签，按当前语言检索）、分类筛选、收藏（localStorage 持久化）
- 三类广告位：顶部横幅 970×90、信息流 300×250、底部横幅 728×90
- 响应式布局，桌面 / 移动端自适应

## 多语言扩展

新增语言只需两步：

1. 在 `LANG_ORDER` 与 `LANGS` 中追加语言代码与显示名；
2. 补充 `UI`、`DESC` 两处文案（`CATS` 与 `TAGS` 为按 `LANG_ORDER` 顺序排列的数组，追加一项即可）。

框架已预留 `es` / `fr` / `de` / `pt` / `ru` 的界面文案，补齐对应 `DESC` 后把语言代码加进 `LANG_ORDER` 即可启用。

## 广告接入

所有广告位使用统一的 `.ad-slot` 容器（含 `data-ad-slot` 标识），接入步骤如下：

1. 在 `<head>` 中引入广告联盟脚本（如 Google AdSense / 百度联盟）；
2. 将各 `.ad-slot` 内的占位内容替换为广告单元代码（如 `<ins class="adsbygoogle">` 或联盟广告位标签）；
3. 在 `ads.txt` 中填入你的广告联盟发布商声明。

## 本地运行

直接双击 `index.html` 即可在浏览器打开，无需安装任何依赖。

## 部署

### GitHub Pages（当前使用）

仓库 Settings → Pages → Source 选 `Deploy from a branch`，Branch 选 `main`，目录 `/ (root)`，保存后自动构建。

### Vercel

1. 将本仓库导入 Vercel（Import Repository，代码源选择 GitHub）；
2. Framework Preset 选择 `Other`，Build Command 与 Output Directory 留空；
3. 点击 Deploy 完成，Vercel 自动托管根目录 `index.html`。

## 目录结构

- `index.html` — 网站本体（单文件自包含）
- `ads.txt` — 广告联盟声明文件（按需填写）
