# 🧠 NeuroSynth Frontend - 神經科學文獻即時查詢系統

[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/yOwut1-r)
[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=21297525&assignment_repo_type=AssignmentRepo)

> 一個使用現代化設計的 NeuroSynth 前端應用，提供即時 AJAX 查詢功能，無需按下 Enter 即可自動搜尋神經科學術語與研究。

## 🌐 線上預覽

- **GitHub Repository**: [https://github.com/ntu-info/neurosynth-frontend-BurningBright7214](https://github.com/ntu-info/neurosynth-frontend-BurningBright7214)
- **GitHub Pages**: `https://ntu-info.github.io/neurosynth-frontend-BurningBright7214/` *(待部署)*

## ✨ 主要特色

### 🎯 核心功能

1. **Terms 相關詞即時查詢**
   - 輸入術語立即顯示相關詞彙（如：amygdala）
   - 自動呼叫 `GET /terms/<term>` API
   - 點擊相關詞可直接加入右側邏輯查詢

2. **Studies 邏輯查詢**
   - 支援複雜邏輯運算（AND、OR、NOT）
   - 即時呼叫 `GET /query/<q_string>/studies` API
   - 以美觀的表格呈現研究結果

3. **真正的 AJAX 即時查詢**
   - ⚡ **無需按 Enter/Submit**：輸入即搜尋
   - 🔄 自動取消舊請求，只顯示最新結果
   - ⏱️ 去抖機制（200-250ms）避免過度請求
   - 📊 即時顯示 HTTP 狀態、回應時間、資料大小

### 🎨 現代化 UI 設計

- **動態漸變背景**：藍紫色調自動循環動畫
- **毛玻璃效果**：半透明的 Header 與 Footer
- **懸停動效**：卡片浮起、按鈕縮放等互動效果
- **彩色徽章系統**：HTTP 狀態、時間、資料大小一目了然
- **漸變表格**：現代化的表頭設計與斑馬紋背景
- **響應式設計**：完美支援手機、平板、桌面設備

### 🛠️ 技術亮點

- **單一 HTML 檔案**：無需建置工具，開箱即用
- **AbortController**：智能請求管理，自動取消過期請求
- **錯誤處理完善**：清楚提示 CORS、網路或伺服器錯誤
- **效能優化**：Debounce、請求取消、智能解析
- **無障礙設計**：語意化 HTML、ARIA 標籤

## 🚀 技術棧

<div align="left">

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)

</div>

- **前端框架**: Vanilla JavaScript (ES6+)
- **CSS 框架**: Tailwind CSS 3.x (CDN)
- **API 通訊**: Fetch API
- **後端 API**: NTU MIL NeuroSynth Backend (`https://mil.psy.ntu.edu.tw:5000`)

## 📸 功能展示

### 介面概覽

```
┌─────────────────────────────────────────────────────────────┐
│  🧠 NeuroSynth 即時查詢              [毛玻璃 Header]      │
├─────────────────────────────────────────────────────────────┤
│                                                               │
│  ┌─────────────────────────┐  ┌──────────────────────────┐ │
│  │ 🏷️ Terms 相關詞查詢     │  │ 📋 Studies 邏輯查詢      │ │
│  │                         │  │                          │ │
│  │ [搜尋框: amygdala    🔍]│  │ [搜尋框: emotion not... 🔍]│
│  │ [載入全部]              │  │ [快速範例按鈕群組]        │ │
│  │                         │  │                          │ │
│  │ ✅ HTTP 200 ⏱️ 245ms    │  │ ✅ HTTP 200 ⏱️ 113ms     │ │
│  │ 💾 202.7KB              │  │ 💾 16.1KB 📊 50筆研究    │ │
│  │                         │  │                          │ │
│  │ [相關詞彙藥丸按鈕群組]  │  │ [精美表格顯示研究結果]  │ │
│  └─────────────────────────┘  └──────────────────────────┘ │
│                                                               │
│  ┌───────────────────── API 端點測試 ─────────────────────┐ │
│  │  [1] /terms  [2] /terms/amygdala  [3] /query/.../studies│ │
│  └─────────────────────────────────────────────────────────┘ │
│                                                               │
└─────────────────────────────────────────────────────────────┘
```

### 視覺特色

- **動態背景**：柔和的藍紫漸變，15秒循環動畫
- **卡片設計**：圓角、陰影、懸停浮起效果
- **狀態徽章**：
  - 🟢 綠色：HTTP 200 成功
  - 🔵 藍色：回應時間
  - 🟣 紫色：資料大小
  - 🟡 琥珀色：研究筆數
- **表格樣式**：漸變表頭、懸停高亮、斑馬紋

## 📖 使用說明

### AJAX 即時查詢演示

1. **Terms 查詢流程**
   ```
   使用者輸入 "amygdala"
   → 等待 200ms（debounce）
   → 自動呼叫 GET /terms/amygdala
   → 顯示載入動畫
   → 渲染相關詞彙為可點擊按鈕
   → 點擊任一按鈕 → 自動填入右側查詢欄
   ```

2. **Studies 邏輯查詢**
   ```
   使用者輸入 "emotion not memory"
   → 等待 250ms（debounce）
   → 自動呼叫 GET /query/emotion%20not%20memory/studies
   → 顯示載入動畫
   → 解析 JSON 回應（data.results 陣列）
   → 渲染為漂亮的表格，顯示：
      - authors（作者）
      - contrast_id（對比 ID）
      - id（研究 ID）
      - journal（期刊）
      等欄位
   ```

## 💻 本地開發

### 快速開始

1. **直接開啟**（推薦用本地伺服器）
   ```bash
   # 方法 1: Python
   python -m http.server 8080
   
   # 方法 2: Node.js
   npx serve -p 8080
   
   # 方法 3: VS Code
   # 安裝 Live Server 擴充套件，右鍵 index.html → Open with Live Server
   ```

2. **瀏覽器訪問**
   ```
   http://localhost:8080
   ```

### 檔案結構

```
neurosynth-frontend-BurningBright7214/
├── index.html                                    # 主應用程式（單一檔案）
├── README.md                                     # 本文件
├── LICENSE                                       # MIT 授權
└── cursor_review_ajax_implementation_for_f.md    # Cursor AI 開發對話紀錄
```

## 🌍 部署到 GitHub Pages

### 步驟

1. **推送程式碼**
   ```bash
   git add .
   git commit -m "Deploy to GitHub Pages"
   git push origin main
   ```

2. **啟用 GitHub Pages**
   - 進入 Repository → Settings → Pages
   - Source: `Deploy from a branch`
   - Branch: `main` / `(root)`
   - 點擊 Save

3. **等待部署**（約 1-3 分鐘）
   - 訪問：`https://<username>.github.io/<repo-name>/`
   - 範例：`https://ntu-info.github.io/neurosynth-frontend-BurningBright7214/`

## 🔌 API 文檔

### Backend Endpoint

```
Base URL: https://mil.psy.ntu.edu.tw:5000
```

### API 端點

#### 1️⃣ 取得所有術語

```http
GET /terms
```

**回應範例**:
```json
["amygdala", "emotion", "memory", "cortex", ...]
```

#### 2️⃣ 取得術語的相關詞

```http
GET /terms/{term}
```

**參數**:
- `term`: 術語名稱（如：amygdala）

**回應範例**:
```json
{
  "term": "amygdala",
  "related": ["emotion", "fear", "limbic", ...]
}
```

#### 3️⃣ 邏輯查詢研究

```http
GET /query/{query_string}/studies
```

**參數**:
- `query_string`: 邏輯查詢字串
  - 支援 `and`、`or`、`not` 運算子
  - 範例：`amygdala not emotion`、`emotion and memory`

**回應範例**:
```json
{
  "count": 50,
  "results": [
    {
      "authors": "Smith J, Doe A",
      "contrast_id": "1",
      "id": "12345",
      "journal": "Nature Neuroscience"
    },
    ...
  ]
}
```

## 🤖 開發歷程 - AI 輔助開發

本專案使用 **Cursor AI** 輔助開發，完整對話紀錄請見：

📄 [cursor_review_ajax_implementation_for_f.md](./cursor_review_ajax_implementation_for_f.md)

### 開發過程

1. **需求分析**：實現 AJAX 即時查詢功能
2. **核心功能**：實作三個 API 端點的即時查詢
3. **UI 美化**：使用 Tailwind CSS 打造現代化介面
4. **優化體驗**：添加載入狀態、錯誤處理、性能優化
5. **測試除錯**：處理資料解析、CORS 錯誤等問題

### AI 協助內容

- ✅ AJAX 即時查詢架構設計
- ✅ Debounce 與 AbortController 實作
- ✅ 動態 UI 元件渲染
- ✅ CSS 動畫與漸變效果
- ✅ 錯誤處理與使用者回饋
- ✅ 程式碼優化與重構

## 🎯 核心實作細節

### AJAX 即時查詢實作

```javascript
// 1. Debounce 避免過度請求
const debouncedSearch = debounce(() => {
  runSearch(input.value.trim());
}, 200);

// 2. AbortController 取消舊請求
let abortController = null;
async function runSearch(term) {
  if (abortController) abortController.abort();
  abortController = new AbortController();
  
  const response = await fetch(url, { 
    signal: abortController.signal 
  });
  // ... 處理回應
}

// 3. 監聽 input 事件（非 submit）
input.addEventListener('input', debouncedSearch);
```

### 智能資料解析

```javascript
// 自動識別不同的資料結構
if (Array.isArray(data)) {
  renderResults(data);
} else if (Array.isArray(data?.results)) {
  renderResults(data.results);
} else if (Array.isArray(data?.terms)) {
  renderResults(data.terms);
} else {
  // 智能搜尋所有可能的陣列
  const arrays = Object.values(data).filter(v => Array.isArray(v));
  if (arrays.length > 0) renderResults(arrays[0]);
}
```

## 📝 注意事項

### CORS 限制

- 若伺服器未允許 CORS，瀏覽器將阻擋跨來源請求
- 本專案已提供清楚的錯誤提示與除錯資訊
- 建議使用本地伺服器而非直接開啟 `file://`

### 瀏覽器支援

- ✅ Chrome 90+
- ✅ Firefox 88+
- ✅ Safari 14+
- ✅ Edge 90+

需要支援：Fetch API、ES6+、CSS Grid、Flexbox

## 📄 授權

MIT License - 詳見 [LICENSE](./LICENSE) 檔案

## 👨‍💻 作者

**BurningBright7214**
- Email: cchangyu3@gmail.com
- GitHub: [@BurningBright7214](https://github.com/BurningBright7214)

## 🙏 致謝

- **NTU MIL** - 提供 NeuroSynth Backend API
- **Tailwind CSS** - 優秀的 CSS 框架
- **Cursor AI** - 智能程式碼輔助工具
- **GitHub Classroom** - 專案管理平台

---

<div align="center">

**🧠 探索神經科學，從即時查詢開始**

Made with ❤️ and ☕ by BurningBright7214

</div>
