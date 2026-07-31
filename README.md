# KFCS 官方網站

KFCS（KuoFeng Coaching System）耐力訓練系統官方網站，由徐國峰創立。以心、體能、力量、技術四大模組，整合跑步、游泳、公路車與鐵人三項的科學化訓練。

## 網站結構

| 頁面 | 檔案 |
| --- | --- |
| 首頁 | `index.html` |
| 課程總覽 | `courses.html` |
| 教練認證（R6 實體課程） | `coach-certification.html` |
| 教育訓練 | `education.html` |
| 部落格索引 | `blog.html` |
| YouTube 專區 | `youtube.html` |
| Podcast 專區 | `podcast.html` |
| 關於我們 | `about.html` |
| 課程簡章與報名資訊（8 篇） | `blog/*.html` |

- `shared/kfcs-unified-theme.css`：課程簡章頁共用主題。
- `shared/site-chrome.css`：全站導覽列與 footer 樣式。
- `assets/`：logo 與課程封面圖。

## 部署

GitHub Pages（main 分支根目錄）。推送到 main 後自動部署至：
<https://lash400.github.io/kfcs-website/>

## 注意事項

- 目前所有頁面皆設定 `<meta name="robots" content="noindex">`（網站審核中）。正式上線時請移除各頁的這一行。
- 報名相關連結指向站內「報名流程」頁；報名方式為寄信至 <kuofengcoaching@gmail.com>。
- 內容來源：`KFCS_Website&Seminar/官方網站/`，經組裝腳本轉為獨立靜態網站。
