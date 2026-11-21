# WebP Shot — 高清截图标注 · 极致压缩 WebP 导出

纯前端单文件工具，零后端、零数据库、零服务器。图片只在你浏览器本地处理，不上传任何服务器。

## 功能

- **不模糊**：画布内部分辨率始终等于原图真实像素，导出按原始像素出图，不缩放、不拉伸。
- **极致压缩 WebP**：默认开启「自动极致压缩」，填目标体积（KB），程序二分搜索满足体积的最高画质（0.5–0.95）；也可关掉用固定质量。
- **标注**：选择移动、矩形、椭圆、箭头、直线、自由画笔、文字（双击编辑），支持撤销 / 重做 / 删除选中。
- **水印**：文字水印（右下角 / 全图平铺 / 居中，可调透明度、字号、旋转）；图片 Logo 水印（可拖动、缩放、调透明度）。
- **导入**：点上传、拖拽进页面、或系统截图后直接 Ctrl/Cmd + V 粘贴。

## 部署到 Cloudflare Pages（全程可视化，不用命令行）

1. 登录 GitHub（github.com），右上角 `+` → `New repository`：
   - 仓库名随便填，如 `webp-shot`；选 Public；**不要勾选** "Add a README"；点 Create。
2. 进入新建仓库 → 页面上方 `Add file` → `Upload files` → 把 `index.html` 拖进去 → 底部 `Commit changes`。
3. 打开 Cloudflare 后台（dash.cloudflare.com）→ 左侧 `Workers & Pages` → `Create` → `Pages` 标签 → `Connect to Git`，授权并选中刚建的仓库：
   - Framework preset 选 **None**；Build command 留空；输出目录留空；点 `Save and Deploy`。
4. 约 1 分钟后得到 `https://你的项目.pages.dev` 域名，直接可用，全球 CDN、永久免费。

## 备选：GitHub Pages

仓库 → `Settings` → 左侧 `Pages` → Source 选 `main`、目录选 `/ (root)` → Save，得到 `https://用户名.github.io/webp-shot/`。

## 使用说明

- 推荐用 Chrome / Edge 打开（视图缩放用了 zoom）。
- 系统截图（Win：Win+Shift+S；Mac：Cmd+Shift+4）后，在页面里 Ctrl/Cmd+V 粘贴。
- 左侧工具栏标注；右侧加水印；点右上角「导出 WebP」自动下载，底部显示导出体积与原图对比。
- 自动极致压缩：目标体积填越小越压；若 0.5 最低质量仍超目标，会在结果栏提示。

## 文件说明

- `index.html`：全部代码，Fabric.js 标注库走 CDN，单文件即可运行。
