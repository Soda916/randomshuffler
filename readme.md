# 隨機排序工具 (Random Shuffle Tool)

一個輕量、直覺且具備現代 UI 視覺效果的單網頁隨機排序工具。使用者可以快速輸入多個項目，並透過 Fisher-Yates 演算法一鍵打亂序列，非常適合用於抽籤、分組、活動排序或隨機決策等場景。

透過 GitHub Pages 託管，免安裝、免下載，點擊下方連結即可直接在線上使用！

👉 **[線上即時使用連結](https://soda916.github.io/randomshuffler/)**

---

## ✨ 功能特點

* **多種分隔輸入**：支援使用 `Enter`、半形逗號 `,` 或全形逗號 `，` 自動將文字分割並轉換為獨立標籤。
* **動態標籤管理**：輸入的項目會以標籤（Tags）形式呈現，支援點擊 `✕` 即時刪除特定項目。
* **流暢視覺動畫**：點擊「打亂」時，結果標籤會帶有優雅的動態漸顯與位移效果。
* **一鍵複製結果**：提供複製功能，打亂後的序列會以逗號分隔自動寫入剪貼簿，並伴隨按鈕狀態反饋（顯示「已複製」）。
* **響應式設計**：完美適配行動裝置與桌面端，在窄螢幕下會自動調整版面配置（如輸入框與按鈕改為垂直排列）。

---

## 🛠️ 技術棧與架構

此專案採用**單檔案（Single File Component）**架構，不依賴任何外部前端框架（如 Vue、React）或大型函式庫，具備極高的載入速度與可移植性，非常適合 GitHub Pages 靜態託管。

* **HTML5**：使用語意化標籤，並針對螢幕閱讀器（Screen Reader）加入 `sr-only` 無障礙隱藏標題。
* **CSS3**：利用 CSS 變數進行樣式管理，並透過 `transition` 與 `requestAnimationFrame` 實作原生 JavaScript 驅動的延時流暢動畫。
* **Vanilla JavaScript (ES6+)**：
    * **核心演算法**：使用 **Fisher-Yates (Knuth) Shuffle 演算法**，確保打亂結果達到 $O(n)$ 時間複雜度的真正隨機。
    * **資料防禦**：內建 `esc()` 函式進行 HTML 轉義，防止使用者輸入惡意字串引發 XSS（跨網站指令碼攻擊）。
    * **現代 API**：使用 `navigator.clipboard` 實作非同步剪貼簿複製。

---

## 🚀 部署與本機開發

### 1. 線上使用 / Fork
你可以直接點擊上方的「線上即時使用連結」，或者點擊 GitHub 右上角的 **Fork** 將此專案複製到你自己的帳號下，並在 Settings 裡的 Pages 頁面開啟 GitHub Pages 服務，即可擁有屬於你的專屬網址。

### 2. 本機執行
如果你想在自己的電腦上修改或測試：
1. 將專案 `git clone` 到本機，或直接下載 `index.html`。
2. 雙擊 `index.html` 檔案，即可直接在瀏覽器中開啟並執行，不需要啟動任何本地伺服器（Local Server）。

---

## 🎨 樣式與變數自訂

本網頁的樣式設計採用了通用變數。若你想修改網頁的主題配色（例如改成暗黑模式），可以直接修改 `index.html` 內 `<style>` 中的以下變數：

```css
:root {
  --font-sans: system-ui, -apple-system, sans-serif;
  --color-background-primary: #ffffff;
  --color-background-secondary: #f5f5f7;
  --color-border-secondary: #d2d2d7;
  --color-border-tertiary: #e5e5ea;
  --color-text-primary: #1d1d1f;
  --color-text-secondary: #86868b;
  --color-text-tertiary: #aeaeac;
  --border-radius-md: 8px;
}