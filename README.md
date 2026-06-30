# biupc_data GitHub Pages 面板

把本目录下的 `index.html` 上传到 `biupc_data` 仓库根目录，然后在 GitHub 仓库设置中启用 Pages：

1. 进入仓库 `Settings` → `Pages`。
2. `Source` 选择 `Deploy from a branch`。
3. `Branch` 选择 `main` / `/root`，保存。
4. 稍后访问 GitHub Pages 地址。

这个面板是静态只读页面，只会读取本仓库里的 JSON 数据文件，不会经过 Render，也不会消耗 Render 出站流量。

Render 后端默认写入：

- `archive/counters/YYYY/MM/YYYY-MM-DD.json`
- `archive/summary/YYYY/YYYY-MM.json`

新版 `server.js` 会额外维护一个最新索引文件：

- `latest.json`

`latest.json` 只保存最新日期、最新月份、对应 JSON 路径和最近若干天的摘要，不保存 GitHub Token，不承担写入功能。面板读取当天文件失败时，会自动读取 `latest.json`，再根据索引指向的路径加载最新可用数据。

如果你的 Render 后端写入路径不同，只需要修改 `index.html` 里的 `candidatePathsForDate()` 和 `candidatePathsForMonth()`。
