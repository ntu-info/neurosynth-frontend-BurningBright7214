[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/yOwut1-r)
[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=21297525&assignment_repo_type=AssignmentRepo)
# Neurosynth Frontend（AJAX 即時查詢）

這是一個使用 Tailwind CSS 的單頁前端，對接 `https://mil.psy.ntu.edu.tw:5000` 的 API，並以「輸入即查」的方式，無需按下 Enter/Submit，就會自動呼叫並渲染結果。

## 介面功能
- **Terms 相關詞即時查詢**：輸入術語後自動呼叫 `/terms/<term>`；若空白則呼叫 `/terms`。
- **Studies 邏輯查詢**：輸入查詢字串後自動呼叫 `/query/<q_string>/studies` 並呈現表格。
- **UX 強化**：
  - 輸入去抖（200~250ms）避免過度請求。
  - `AbortController` 會中止舊請求，保證只呈現最新結果。
  - 載入中指示器、HTTP 狀態、回應時間、回應大小等資訊。
  - 錯誤處理（含 CORS 與網路錯誤）與空狀態顯示。

## 本地預覽
直接開啟 `index.html` 即可。為避免 `file://` 情境下的 CORS/安全性限制，建議啟動一個簡單的本地伺服器：

```bash
# 任選其一
python -m http.server 8080
npx serve -p 8080
```

然後瀏覽 `http://localhost:8080`。

## 部署到 GitHub Pages（生產 URL）
1. 在 GitHub 建立一個公開 Repo，將此專案的檔案（至少 `index.html` 與 `README.md`）推上去。
2. 在該 Repo 的 Settings → Pages：
   - Source 選擇 `Deploy from a branch`
   - Branch 選擇 `main` 與 `/ (root)`
   - 儲存後等 1~3 分鐘，會得到一個 Pages 網址，格式類似：
     `https://<your-username>.github.io/<repo-name>/`

完成後，請回填以下兩個 URL：

1. 你的 GitHub Repo 連結
2. 你部署後的前端頁面（GitHub Pages）連結

## API 範例
- `https://mil.psy.ntu.edu.tw:5000/terms`
- `https://mil.psy.ntu.edu.tw:5000/terms/amygdala`
- `https://mil.psy.ntu.edu.tw:5000/query/amygdala%20not%20emotion/studies`

## 注意
- 若伺服器未允許 CORS，瀏覽器將無法跨來源存取；此專案已提供清楚的錯誤提示。
- 網路環境與伺服器狀態會影響回應時間及穩定性。
