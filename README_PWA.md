# 數位易經 PWA 安裝與使用指南

## 📱 什麼是 PWA？
PWA (Progressive Web App) 是一種可以像原生 APP 一樣安裝到手機上的網頁應用程式，具有以下優點：
- ✅ 無需透過 App Store 下載
- ✅ 可離線使用
- ✅ 可新增到主畫面，像 APP 一樣啟動
- ✅ 全螢幕體驗，無瀏覽器介面干擾
- ✅ 自動更新

## 📦 檔案清單
- `數位易經_優化版_v2_1.html` - 主要應用程式
- `manifest.json` - PWA 設定檔
- `sw.js` - Service Worker（離線快取）
- `icon-*.png` - 8 個不同尺寸的應用程式圖示

## 🚀 部署步驟

### 方法一：使用 GitHub Pages（推薦）

1. **上傳到 GitHub**
   - 在 GitHub 創建新 repository
   - 將所有檔案上傳到 repository

2. **啟用 GitHub Pages**
   - 進入 repository 的 Settings
   - 找到 Pages 選項
   - Source 選擇 "main" branch
   - 點擊 Save

3. **取得網址**
   - 幾分鐘後，您會得到類似這樣的網址：
   - `https://your-username.github.io/your-repo-name/數位易經_優化版_v2_1.html`

### 方法二：使用其他網頁主機
支援的平台：
- Netlify (拖放上傳，免費)
- Vercel (免費)
- Firebase Hosting (免費)

## 📲 在手機上安裝

### iOS (iPhone/iPad)
1. 用 Safari 瀏覽器開啟您的 PWA 網址
2. 點擊底部的「分享」按鈕 (方框加箭頭圖示)
3. 向下滾動，找到「加入主畫面」
4. 自訂名稱（預設：數位易經）
5. 點擊「加入」
6. 完成！圖示會出現在主畫面

### Android
1. 用 Chrome 瀏覽器開啟您的 PWA 網址
2. 點擊右上角的「選單」(三個點)
3. 選擇「加入主畫面」或「安裝應用程式」
4. 確認安裝
5. 完成！圖示會出現在主畫面

## ✨ PWA 功能特色

### 1. 離線使用
- 第一次訪問後，應用程式會被快取
- 之後即使沒有網路也能使用
- 所有占卜功能完全正常運作

### 2. 獨立應用程式體驗
- 全螢幕顯示，無瀏覽器工具列
- 在應用程式切換器中有自己的圖示
- 與原生 APP 使用體驗一致

### 3. 快速啟動
- 從主畫面直接啟動
- 啟動速度快
- 無需每次輸入網址

## 🔧 測試是否成功

1. **檢查 manifest**
   - 打開 Chrome DevTools (F12)
   - 前往 Application → Manifest
   - 確認所有資訊正確顯示

2. **檢查 Service Worker**
   - DevTools → Application → Service Workers
   - 應該看到 sw.js 已註冊且運行中

3. **測試離線功能**
   - 訪問一次應用程式
   - 關閉網路連線
   - 重新整理頁面
   - 應該仍然可以正常使用

## 📝 注意事項

1. **HTTPS 要求**
   - PWA 必須在 HTTPS 環境下運行
   - GitHub Pages 自動提供 HTTPS
   - 本地測試可使用 localhost

2. **檔案路徑**
   - 所有檔案必須在同一目錄
   - manifest.json 和 sw.js 必須與 HTML 在同一層級

3. **快取更新**
   - 修改檔案後，需更新 sw.js 中的 CACHE_NAME
   - 建議改為 'iching-pwa-v2', 'v3' 等

## 🎯 優化建議

1. **效能優化**
   - 所有資源都已內嵌在 HTML 中
   - 首次載入後即可完全離線使用
   - 無需額外的網路請求

2. **版本控制**
   - 每次更新應用程式時，修改 sw.js 的 CACHE_NAME
   - 這樣可確保用戶獲得最新版本

3. **圖示優化**
   - 已提供 8 種尺寸的圖示
   - 支援所有主流裝置
   - 包含 maskable 圖示支援

## 🆘 常見問題

**Q: 為什麼 iOS 沒有自動提示安裝？**
A: iOS Safari 不會自動彈出安裝提示，需要手動透過「分享」→「加入主畫面」安裝。

**Q: 如何更新已安裝的 PWA？**
A: 重新訪問網址，Service Worker 會自動檢查更新。關閉並重新開啟 APP 即可套用更新。

**Q: 可以在電腦上使用嗎？**
A: 可以！Chrome 和 Edge 瀏覽器支援桌面版 PWA 安裝。

**Q: 資料會儲存在哪裡？**
A: 所有占卜歷史記錄儲存在瀏覽器的 localStorage，不會上傳到伺服器。

## 📞 技術支援

如有任何問題，請檢查：
1. 瀏覽器控制台 (Console) 的錯誤訊息
2. Service Worker 是否成功註冊
3. manifest.json 是否正確載入

---

**版本**: v2.1 (PWA)
**更新日期**: 2026-02-05
**相容性**: iOS 11.3+, Android 5.0+, Chrome 45+, Safari 11.1+
