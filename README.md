# 🥗 LINE Bot AI 飲食教練
**LINE Bot × n8n × OpenAI × Google Sheets**
拍照辨識熱量・每日自動結算・多用戶管理

🎬 **Demo 影片**：https://youtu.be/KsvtNtIcJqo

---

## 背景與痛點

記錄飲食熱量麻煩、APP 不好用、容易半途而廢。想要一個在 LINE 就能直接記錄、不需要額外下載 APP 的輕量解決方案。

## 功能總覽

| 功能 | 說明 |
|------|------|
| 📷 拍照記錄 | 傳食物照片 → AI 自動辨識食物名稱與熱量，生成 Flex 卡片供確認 |
| 💬 文字記錄 | 直接輸入飲食內容 → AI 解析並分類寫入 Google Sheets |
| 📊 每日結算 | 定時推播每日攝取總結，對比個人 TDEE 目標，顯示剩餘熱量空間 |
| ⚖️ 體重追蹤 | 記錄每日體重，自動計算 7 天平均趨勢 |
| 👥 多用戶 | 支援多人同時使用，新用戶自動建檔，各自獨立 TDEE 設定 |
| ✏️ 資料修正 | 辨識錯誤時可直接修正，重新計算當日總帳 |

## 系統架構

兩條 n8n workflow 並行運作：

**主 Bot**（Webhook 驅動）：接收 LINE 訊息 → 判斷圖片/文字 → AI 解析 → 寫入 Google Sheets → 回傳 Flex 卡片

**排程 Bot**（定時觸發）：每日定時撈取所有用戶飲食紀錄 → 計算總熱量 → 推播結算通知 + 未記錄提醒

## 實際成果

- ✅ 2 位用戶持續使用，連續記錄 10 天
- ✅ 全程在 LINE 完成，零 APP 安裝門檻
- ✅ AI 影像辨識準確率穩定，支援台式、日式等多樣食物

## 技術棧

`n8n` `LINE Messaging API` `LINE Flex Message` `OpenAI GPT-4o` `AI 影像辨識` `Google Sheets` `Webhook` `Schedule Trigger`

---
*Built by Sam｜AI Automation Engineer*
