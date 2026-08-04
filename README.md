# KFCS 官方網站

KFCS（KuoFeng Coaching System）耐力訓練系統官方網站，由徐國峰創立。以心、體能、力量、技術四大模組，整合跑步、游泳、公路車與鐵人三項的科學化訓練。

## 網站結構

| 頁面 | 檔案 |
| --- | --- |
| 首頁 | `index.html` |
| 課程總覽 | `courses.html` |
| 教練認證（R6） | `coach-certification.html` |
| 教育訓練 | `education.html` |
| 部落格（列表＋搜尋＋標籤） | `blog.html` |
| 訓練書系 | `books.html` |
| 跑步線上課程 | `online-course.html` |
| YouTube 專區 | `youtube.html` |
| Podcast 專區 | `podcast.html` |
| 關於我們 | `about.html` |

導覽列的「影音專區」下拉已於 2026-08-04 更名為「學習資源」，並新增第一個子項目
「跑步線上課程」（`online-course.html`），排在 YouTube 專區與 Podcast 專區之前。
下拉主連結指向 `online-course.html`。
| 課程簡章與報名資訊 | `blog/*.html`（8 篇） |
| 耐力訓練文章 | `articles/*.html`（621 篇） |

### 共用資源

- `shared/site-chrome.css`：全站導覽列、footer 與課程檔期通知區塊。
- `shared/kfcs-unified-theme.css`：課程簡章頁共用主題。
- `shared/article.css`：部落格文章的閱讀版型。
- `assets/`：logo 與課程封面圖。
- `_redirects`：已下架／合併頁面的 301 轉址規則。
- `serve.mjs`：本機預覽用的極簡靜態伺服器（`node serve.mjs`，預設 <http://localhost:8799>）。
  已列入 `.assetsignore`，不會部署。
- `assets/og-cover.jpg`：社群分享圖（Open Graph，1200×630）。首頁、關於我們、教育訓練、
  部落格、訓練書系、YouTube 與 Podcast 專區，以及 `articles/*.html` 全部 621 篇文章頁的
  `og:image` 都指向這張，課程總覽與教練認證也是；只有 `blog/*.html` 8 篇課程簡章沿用
  各自的專屬課程封面。原始設計檔為 `assets/og-cover.source.html`（用瀏覽器開啟即可預覽，
  已在 `.assetsignore` 中排除，不會部署）。改圖後以 headless Chrome 截圖 1200×630 重新輸出即可。

## 內容來源

- 課程頁與影音專區：`KFCS_Website&Seminar/官方網站/`
- 部落格文章：徐國峰 Obsidian 資料庫中歷年部落格與臉書發表的文章（2009–2026），
  篩選耐力訓練主題並轉為靜態頁面。
- 推薦序／導讀／譯者序：徐國峰為他人著作所寫的書籍前置文字，原稿取自個人 Pages 書寫資料夾，
  比對後補上官網未收錄的 23 篇（2013–2026），發表日期一律採「該書的出版日期」。
- 舊部落格補匯：<https://rocky549.blogspot.com/> 共 642 篇，比對後補上官網原本缺漏
  且屬訓練主題的 90 篇（2008–2020），保留原始發表日期。訓練日誌、
  生活日記、東華鐵人隊事務與過期課程活動公告未匯入。

## 維護注意事項

- 全站已開放搜尋引擎索引（`robots.txt` 允許全站、`sitemap.xml` 收錄 638 頁），每頁都有 `canonical` 與 `og:url` 指向 <https://kfcs.tw>。
- 2026 年梯次的日期、時間、上課地點與費用已全部移除；報名相關的行動呼籲統一導向 2027 年課程預先登記（寄信至 <kuofengcoaching@gmail.com>）。下一梯課程確定後，需重新補上檔期資訊。
- 已下架或合併的 12 個頁面以 301 轉址處理，規則寫在根目錄的 `_redirects`（Cloudflare Workers
  靜態資產原生支援，不需寫 Worker 程式碼）。5 篇付費書稿轉到 `/books`，7 篇重複文章轉到保留的那一篇。
  新增或移除文章時，若該網址曾進過 `sitemap.xml`，請一併補上轉址規則，避免直接 404。
  注意：GitHub Pages 備援站不支援 `_redirects`，這些轉址只在 kfcs.tw 生效。
- 部分訓練現場照片仍引用 imgur 外部圖床。文章內的圖片有兩種來源：原本就隨文匯入的引用原部落格圖床，
  若來源失效圖片會消失；2026-08 從原文補回的 483 張已下載到 `assets/articles/<文章檔名>/`，不受外站影響。

## 部署

正式站：<https://kfcs.tw>（Cloudflare Workers 靜態資產，設定見 `wrangler.jsonc`）
備援站：<https://lash400.github.io/kfcs-website/>（GitHub Pages，main 分支根目錄）

推送原始碼：

```bash
git add -A && git commit -m "更新內容" && git push
```

部署到 kfcs.tw（首次需先 `npx wrangler login`）：

```bash
npx wrangler deploy
```

Cloudflare 的靜態資產服務會把 `/about.html` 自動轉址到 `/about`，
因此站內連結保留 `.html` 即可，sitemap 則使用無副檔名的正式網址。
