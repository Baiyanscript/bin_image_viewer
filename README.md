# BIN 圖片查看器 (BIN Image Viewer)

一個基於網頁的輕量級工具，專門用來檢視與解析自訂二進位格式（`.bin`）的圖片資料，並支援轉換與下載為標準的 PNG 圖片格式。

👉 **線上預覽**：[https://baiyanscript.github.io/bin_image_viewer/](https://baiyanscript.github.io/bin_image_viewer/)

---

## 🛠 功能特點

- **拖放即看**：支援點擊上傳或直接將 `.bin` 檔案拖曳至指定區域。
- **自動解析標頭 (12 Bytes Header)**：
  - **Magic** (4 bytes)：辨識碼
  - **Width / Height** (各 2 bytes)：圖片寬高尺寸
  - **Stride** (4 bytes)：跨距資料
- **RGBA8888 像素渲染**：支援解碼並呈現高解析度像素。
- **互動控制**：
  - 圖片即時縮放（支援 1× 至 20× 放大倍率調整、重設）。
  - 一鍵將 `.bin` 格式轉存並下載為 `.png` 圖檔。
- **多國語言支援**：內建繁體中文 (zh-Hant)、簡體中文 (zh-Hans) 與英文 (en) 切換。

---

## 📁 檔案格式規範

本工具所支援的 `.bin` 檔案結構如下：

1. **標頭區段 (Header - 12 Bytes)**：
   - `0x00 - 0x03`：Magic (`uint32`, Little-endian)
   - `0x04 - 0x05`：Width (`uint16`, Little-endian)
   - `0x06 - 0x07`：Height (`uint16`, Little-endian)
   - `0x08 - 0x0B`：Stride (`uint32`, Little-endian)
2. **像素資料區段 (Pixel Data)**：
   - 格式：`RGBA8888`
   - 大小：`Width × Height × 4` bytes

---

## 🚀 快速開始

本專案為純前端網頁應用（HTML5 / JavaScript），免安裝任何依賴：

1. 下載或 Clone 本專案。
2. 直接使用現代瀏覽器（Chrome, Edge, Firefox, Safari）開啟 `index.html` 即可使用。

---

## 📄 授權條款

© 2026 Made By Baiyan
