# BIN / PNG 圖片轉換器 (BIN Image Converter)

一個基於網頁的輕量級雙向轉換工具，專門用於檢視、解碼與轉換自訂二進位格式（`.bin`）及標準圖片格式（`.png`, `.jpg`, `.webp`）。

👉 **線上預覽**：[https://baiyanscript.github.io/bin_image_converter/](https://baiyanscript.github.io/bin_image_converter/)

---

## 🛠 功能特點

- **雙向轉換支援**：
  - **BIN 轉 PNG**：線上檢視 `.bin` 檔並一鍵導出為 `.png` 圖檔。
  - **PNG 轉 BIN**：上傳標準圖片格式（PNG/JPG/WebP），自動加上 12 Bytes 標頭並轉碼為 `.bin` 檔案。
- **拖放即看**：支援點擊選取或將檔案直接拖曳至頁籤區域。
- **自動標頭處理 (12 Bytes Header)**：
  - **Magic** (4 bytes)：辨識碼（預設 `0x494d4730`）
  - **Width / Height** (各 2 bytes)：圖片寬高尺寸
  - **Stride** (4 bytes)：跨距資料
- **RGBA8888 像素編解碼**：支援完整 RGBA 通道渲染與二進位生成。
- **互動控制與縮放**：支援 1× 至 20× 放大倍率調整與重設。
- **多國語言介面**：內建繁體中文 (zh-Hant)、簡體中文 (zh-Hans) 及英文 (en)。

---

## 📁 BIN 檔案格式規範

本工具定義與支援的 `.bin` 二進位結構如下：

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

本專案為純前端網頁應用（HTML5 / JavaScript），無需安裝任何環境或依賴：

1. 下載或 Clone 本專案。
2. 使用現代網頁瀏覽器（Chrome, Edge, Firefox, Safari）開啟 `index.html` 即可運作。

---

## 📄 授權條款

© 2026 Made By Baiyan
