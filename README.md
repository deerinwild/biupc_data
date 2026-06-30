# biupc_data GitHub Pages 面板

把本目录下的 `index.html` 上传到 `https://github.com/deerinwild/biupc_data` 仓库根目录，然后在 GitHub 仓库设置中启用 Pages：

1. 进入仓库 `Settings` → `Pages`。
2. `Source` 选择 `Deploy from a branch`。
3. `Branch` 选择 `main` / `/root`，保存。
4. 稍后访问 GitHub Pages 地址。

这个面板是静态只读页面，只会读取本仓库里的 JSON 数据文件，不会经过 Render，也不会消耗 Render 出站流量。

默认会尝试读取这些路径：

- `archive/counters/YYYY/MM/YYYY-MM-DD.json`
- `archive/counters/YYYY-MM-DD.json`
- `counters/YYYY-MM-DD.json`
- `data/YYYY-MM-DD.json`
- `latest.json`
- `summary/latest.json`
- `archive/summary/YYYY/YYYY-MM.json`
- `archive/summary/YYYY-MM.json`
- `summary/YYYY-MM.json`
- `monthly/YYYY-MM.json`

如果你的 Render 后端写入路径不同，只需要修改 `index.html` 里的 `candidatePathsForDate()` 和 `candidatePathsForMonth()`。
