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
| YouTube 專區 | `youtube.html` |
| Podcast 專區 | `podcast.html` |
| 關於我們 | `about.html` |
| 課程簡章與報名資訊 | `blog/*.html`（8 篇） |
| 耐力訓練文章 | `articles/*.html`（488 篇） |

### 共用資源

- `shared/site-chrome.css`：全站導覽列、footer 與課程檔期通知區塊。
- `shared/kfcs-unified-theme.css`：課程簡章頁共用主題。
- `shared/article.css`：部落格文章的閱讀版型。
- `assets/`：logo 與課程封面圖。

## 內容來源

- 課程頁與影音專區：`KFCS_Website&Seminar/官方網站/`
- 部落格文章：徐國峰 Obsidian 資料庫中歷年部落格與臉書發表的文章（2009–2026），
  篩選耐力訓練主題並轉為靜態頁面。

## 維護注意事項

- **全站設定 `<meta name="robots" content="noindex">`**（審核中）。正式上線時要移除所有頁面的這一行，否則搜尋引擎不會收錄。
- 2026 年梯次的日期、時間、上課地點與費用已全部移除；報名相關的行動呼籲統一導向 2027 年課程預先登記（寄信至 <kuofengcoaching@gmail.com>）。下一梯課程確定後，需重新補上檔期資訊。
- 部分訓練現場照片仍引用 imgur 外部圖床，文章內的圖片則引用原部落格圖床。若來源失效，圖片會消失。

## 部署

GitHub Pages（main 分支根目錄），推送後自動部署：
<https://lash400.github.io/kfcs-website/>

```bash
git add -A && git commit -m "更新內容" && git push
```
