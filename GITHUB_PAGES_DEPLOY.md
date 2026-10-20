# GitHub Pages 部署說明

目前尚未設定 remote，也未推送到 GitHub；不要將本檔案中的說明視為已部署。

1. 將本資料夾建立為獨立 GitHub repository。
2. 將本 repo 的 `main` 分支推送到該 repository。
3. 在 GitHub Pages 設定中選擇 `Deploy from a branch`、`main`、`/docs`。
4. 使用 GitHub 顯示的實際 URL，不自行猜測 project site URL。

發布前確認：`docs/index.html`、`docs/.nojekyll`、`docs/PDFs/` 均存在，且 PDF 連結使用 `./PDFs/` 相對路徑。
