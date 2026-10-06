# 幼兒特殊教育評量整合工具 v8

## GitHub Pages

若原本 v7 已經部署完成，只需要用本版 `index.html` 覆蓋 GitHub repository 根目錄的 `index.html`；`assets/` 兩張圖片不用更換。

檔案結構：

```text
/
├── index.html
└── assets/
    ├── taipei_age4.png
    └── taipei_age5.png
```

## v8 變更

1. 基本資料新增「10. 是否為期末幼兒個案」。只有選「是」才會顯示並要求填寫 E. 綜合評量與專業判斷；選「否」時報告與後台不會帶入 E 區內容。
2. ASQ:SE-2-TC 新增「填寫者身分」：父母親、老師、其他。選「其他」時會出現文字欄位。
3. 後台新增 `isFinalCase` 與 `asqRespondent` 兩個欄位。

## Apps Script

`apps-script/Code.gs` 是對應 v8 的後台版本。

如果原本 `responses` 已經有資料，不要清空工作表。本版 `setupSheet()` 與 `doPost()` 只會在最右側補上缺少欄位，不會刪除既有資料。

更新 Apps Script 後，請到「部署 → 管理部署作業 → 編輯 → 新版本 → 部署」。若是編輯原本的 Web App 部署，通常可以維持原 `/exec` 網址。
