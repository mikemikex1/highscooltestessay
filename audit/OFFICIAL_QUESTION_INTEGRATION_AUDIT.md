# Official Question Integration Audit

# Result

READY_WITH_GAPS

目前網站適合維持「5～10 分鐘考前快速複習」定位，但尚未把官方試卷的完整材料與題目內嵌到年度頁面。正式資料仍可透過官方 PDF 連結查看，因此後續可進入原題整合階段；本輪不修改既有教材、UI、PDF、Git 或離線包。

# Current Site

- repo = `國寫學測111-115_GitHub`
- branch = `main`
- working tree = audit 前 clean；本報告為本輪唯一新增檔案
- docs = `docs/index.html`, `docs/app.js`, `docs/data.js`, `docs/styles.css`, `docs/PDFs/`
- release = 既有離線 ZIP，未使用、未修改
- audit = `audit/`
- tabs = 115、114、113、112、111、五年總整理，共 6 個；由 `docs/app.js` renderer 產生
- content state = 年度考前摘要、任務拆解、建議策略、常見風險、評分濃縮、答題紙提醒與官方 PDF 連結

# Official Sources

官方原題判定只使用官方試卷 PDF；評分原則 PDF 僅用於 rubric；答題卷 PDF 僅用於作答格式。

| 年度 | 試卷 | 評分原則 | 答題卷 | exists |
|---|---|---|---|---|
| 111 | `docs/PDFs/01-2-111學測國寫試卷定稿.pdf` | `docs/PDFs/01-111學測國寫非選擇題評分原則.pdf` | `docs/PDFs/01-2-111學測國寫答題卷.pdf` | YES |
| 112 | `docs/PDFs/01-2-112學測國文(國寫)試卷.pdf` | `docs/PDFs/02-112學測國寫非選擇題評分原則.pdf` | `docs/PDFs/01-2-112學測國文(國寫)答題卷.pdf` | YES |
| 113 | `docs/PDFs/07-113學測國寫定稿.pdf` | `docs/PDFs/02-113學測國文考科(國寫)非選擇題評分原則.pdf` | `docs/PDFs/07-113學測國寫答題卷-定稿.pdf` | YES |
| 114 | `docs/PDFs/07-114學測國寫試題.pdf` | `docs/PDFs/02-114學測國寫閱卷評分原則說明.pdf` | `docs/PDFs/07-114學測國寫答題卷-定稿.pdf` | YES |
| 115 | `docs/PDFs/07-115學測國寫試卷.pdf` | `docs/PDFs/115學測國文考科(國寫)非選擇題評分原則.pdf` | `docs/PDFs/07-115學測國寫答題卷.pdf` | YES |

- PDF_TOTAL = 15
- PDF_BROKEN = 0；15 份檔案均可由 PDF reader 讀取並有頁面內容
- 每年 = 1 試卷 + 1 評分原則 + 1 答題卷

# Current Original Question Coverage

判定說明：網站目前的年度摘要與題目任務欄位是教師整理，不等於完整官方題幹。`sources` 是官方 PDF 檔名連結，不代表原題已嵌入頁面。

| 項目 | 111 | 112 | 113 | 114 | 115 | 性質判定 |
|---|---|---|---|---|---|---|
| 年度主題 | 有 | 有 | 有 | 有 | 有 | TEACHING_SUMMARY |
| 原始材料全文 | 無 | 無 | 無 | 無 | 無 | MISSING |
| 第一大題（一）原題 | 無 | 無 | 無 | 無 | 無 | MISSING |
| 第一大題（二）原題 | 無 | 無 | 無 | 無 | 無 | MISSING |
| 第二大題原始材料 | 無 | 無 | 無 | 無 | 無 | MISSING |
| 第二大題完整題目 | 無 | 無 | 無 | 無 | 無 | MISSING |
| 題目摘要 | 有 | 有 | 有 | 有 | 有 | TEACHING_SUMMARY |
| 任務拆解 | 有 | 有 | 有 | 有 | 有 | TEACHING_SUMMARY |
| 建議答案 | 有 | 有 | 有 | 有 | 有 | TEACHING_STRATEGY |
| 為什麼這樣答 | 有 | 有 | 有 | 有 | 有 | TEACHING_STRATEGY |
| 常見錯法 | 有 | 有 | 有 | 有 | 有 | TEACHING_STRATEGY |
| A/A+ 評分摘要 | 有 | 有 | 有 | 有 | 有 | OFFICIAL_SUMMARY |
| 官方 PDF link | 有 | 有 | 有 | 有 | 有 | OFFICIAL_EXACT（連結；非頁面內嵌原文） |

## 115

- Current coverage = `SOURCE_LINK_ONLY` for exact text; the page has teaching summaries for 小豬／魚／臉、倫理責任與人際隔閡，但沒有完整官方材料或完整第二大題題面。
- Official exam text contains the 小豬、魚、臉與「隔在我們之間的種種」相關內容；網站目前只保留摘要與任務拆解。
- Image dependency = `YES`：官方試卷 PDF 檢出 2 個嵌入圖像；完整呈現必須保留 PDF，不應自行重繪。
- Gap = `MISSING_EXACT_TEXT` + `IMAGE_ASSET_REQUIRED`

## 114

- Current coverage = `SOURCE_LINK_ONLY` for exact text; page summary covers 擬社會互動、正負面影響與 52 赫茲，但沒有完整官方材料或完整題面。
- Official exam PDF contains 擬社會互動與 52 赫茲相關文字；website content is a teaching condensation.
- Image dependency = `NO`（試卷 PDF 未檢出嵌入圖像；PDF 仍是正式版面依據）。
- Gap = `MISSING_EXACT_TEXT`

## 113

- Current coverage = `SOURCE_LINK_ONLY` for exact text; page summary covers 標籤的正負作用與縫隙聯想，但沒有完整官方材料或完整題面。
- Official exam PDF contains 標籤與縫隙相關文字；website content is a teaching condensation.
- Image dependency = `NO`（試卷 PDF 未檢出嵌入圖像；PDF 仍是正式版面依據）。
- Gap = `MISSING_EXACT_TEXT`

## 112

- Current coverage = `SOURCE_LINK_ONLY` for exact text; page summary covers 福爾摩斯／華生、兩種生活態度與氣味記憶，但沒有完整官方材料或完整題面。
- Official exam PDF contains 福爾摩斯、華生與花草樹木的氣味記憶相關文字；website content is a teaching condensation.
- Image dependency = `NO`（試卷 PDF 未檢出嵌入圖像；PDF 仍是正式版面依據）。
- Gap = `MISSING_EXACT_TEXT`

## 111

- Current coverage = `SOURCE_LINK_ONLY` for exact text; page summary covers 樂齡活動、樂齡出遊與「當我打開課本」，但沒有完整官方材料或完整題面。
- Official exam PDF contains 樂齡與「當我打開課本」相關文字；website content is a teaching condensation.
- Image dependency = `NO`（試卷 PDF 未檢出嵌入圖像；PDF 仍是正式版面依據）。
- Gap = `MISSING_EXACT_TEXT`

# Exact vs Summary

| 網站內容位置 | 目前內容 | 判定 |
|---|---|---|
| `docs/data.js` 的 `summary`、`yearTable`、`compositionTable` | 年度主題、核心能力與作文題名整理 | TEACHING_SUMMARY |
| `docs/data.js` 的 `q1a.task`、`q1b.checklist`、`q2.core/elements` | 題目任務拆解與必答元素 | TEACHING_SUMMARY |
| `docs/data.js` 的 `answer/why/structure/loss/mistakes` | 建議答案、架構、策略與風險 | TEACHING_STRATEGY |
| `docs/data.js` 的 `rubric` | 由官方評分原則濃縮出的等級摘要 | OFFICIAL_SUMMARY |
| `docs/data.js` 的 `sources` + `docs/app.js` 的 `sourceLinks()` | 官方 PDF 檔名與連結 | OFFICIAL_EXACT（來源連結） |
| 官方試卷 PDF | 完整原始題面、材料、版面及 115 圖像 | OFFICIAL_EXACT |

結論：目前網站文字沒有可標為 `OFFICIAL_EXACT` 的完整原題段落。意思相近不等於原文相同，不能把現有摘要升格為官方原題。

# Image / Asset Dependency

| 年度 | 題目 | 特殊資產 | 網站目前狀態 |
|---|---|---|---|
| 111 | 全年試卷 | 未檢出嵌入圖像 | SOURCE_LINK_ONLY |
| 112 | 全年試卷 | 未檢出嵌入圖像 | SOURCE_LINK_ONLY |
| 113 | 全年試卷 | 未檢出嵌入圖像 | SOURCE_LINK_ONLY |
| 114 | 全年試卷 | 未檢出嵌入圖像 | SOURCE_LINK_ONLY |
| 115 | 全年試卷，尤其含圖像材料之頁面 | 2 個嵌入圖像 | ASSET_REQUIRED |

115 的官方圖像不得用 AI 或自行繪圖替代；後續若要在頁面內嵌，應使用經確認的官方資產或維持 PDF 連結。

# Canonical Data

## Current

`docs/data.js` 是目前網站年度摘要、策略、rubric、答題紙與 PDF 檔名的 canonical source；`docs/app.js` 是 renderer。HTML 只有 shell，沒有重複放置完整題目。

## Schema status

`CURRENT_SCHEMA_CAN_SUPPORT_ORIGINAL = NO`（目前沒有自然承載完整原題的欄位）。現有結構缺少：

- original source type / source PDF
- material blocks / passage
- part A exact prompt
- part B exact prompt
- second question exact prompt
- image assets / image dependency
- 原題與教師註解分離的 notes 欄位

## Recommended

後續只建議在 `data.js` 每年度增加一個 canonical `officialQuestion`，例如包含：`sourceType`、`sourcePdf`、`materialBlocks`、`partA`、`partB`、`secondQuestion`、`assets`、`notes`。`notes` 只能放官方版面或來源註記，不能混入教師解析。

# Duplicate Content

目前沒有「完整官方原題」同時複製在 `data.js`、`app.js`、`index.html` 或 JSON 的情況。

但有摘要層級的重複：

| 內容 | 位置 A | 位置 B | 是否一致 |
|---|---|---|---|
| 五年第一大題年度主題 | `docs/data.js:yearTable` | `docs/data.js:[year].summary.q1a/q1b` | 大意一致，欄位用途不同 |
| 五年第二大題題名 | `docs/data.js:compositionTable` | `docs/data.js:[year].summary.q2` | 大意一致，欄位用途不同 |
| 題目要求與快速摘要 | `docs/data.js:[year].summary.core` | `docs/data.js:[year].q1a/q1b/q2` | 同一教學內容的不同顯示層 |

判定：`DUPLICATED_QUESTION_CONTENT = SUMMARY_ONLY`。不是完整原題重複，但後續加入 `officialQuestion` 後應避免再把官方題幹複製到 renderer 或 HTML。

# Recommended Placement

每年度最合理的 DOM / renderer 插入點：

1. 年度快速摘要
2. `官方原題` 收合區
3. 第一大題（一）解析
4. 第一大題（二）解析
5. 第二大題解析
6. 答題紙
7. 最後 30 秒

建議由 `docs/app.js` 在 `renderYear(year)` 中，以 `examData[year].officialQuestion` 產生一個 `<details>`；不應把材料拆到別頁。

`RECOMMENDED_INSERT_POINT = renderYear()：summary 後、q1a 前`

# UI Recommendation

原題區只規劃、不實作：

- 標籤：`【官方原題】`
- 預設收合：`查看官方原題`
- 奶油底與焦糖 border，和綠色策略卡、紅色風險卡區分
- 保留官方語意與段落，不在題幹內插入教師註解
- 區塊底部保留「查看該年度官方試卷 PDF」

`COLLAPSED_BY_DEFAULT = YES`

# Gaps

- `MISSING_EXACT_TEXT`：111～115 均缺完整官方材料、第一大題（一）、第一大題（二）與第二大題完整題目。
- `SOURCE_LINK_ONLY`：目前可追到官方 PDF，但不能在頁面內直接閱讀原題。
- `IMAGE_ASSET_REQUIRED`：115 官方試卷含 2 個嵌入圖像；若要內嵌原題，必須處理官方資產或保留 PDF。
- `CURRENT_SCHEMA_CAN_SUPPORT_ORIGINAL = NO`：需先建立 `officialQuestion` canonical 結構，才能安全整合。

沒有把現有摘要誤判為完整官方題目的其他缺口。

# Risk

- 原題預設收合時，考前頁面仍可維持 5～10 分鐘快速複習：`PASS`
- 若五年原題全部預設展開，頁面會明顯過長：`YES`
- 建議：`COLLAPSED_BY_DEFAULT = YES`
- 後續應避免把官方材料、教師解說與範文混在同一段，否則會破壞原題與解析的來源邊界。

# Recommended Next Phase

`IMPLEMENT_ORIGINAL_QUESTION`

理由：官方試卷、評分原則與答題卷已齊全且 15 份 PDF 可讀；目前真正缺口是頁面內嵌原題與圖像依賴處理，而不是來源缺失。

