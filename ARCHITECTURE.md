# UTOP-3D V2.0 Modular Framework

## 目標

每個頁面、設備模組、服務與設定各自獨立，避免修改一項功能時破壞其他功能。

## 啟動流程

```text
index.html
   ↓
core/boot.js
   ├─ config/app-config.js
   ├─ core/page-registry.js
   ├─ core/module-registry.js
   ├─ runtime/legacy-v114/runtime.js
   └─ services/cloud-storage/cloud-save.js
```

## 第一階段策略

V2.0.0先以Adapter方式包住穩定的V1.1.4核心，畫面和操作保持一致。

這一版已完成「資料夾與責任分離」，但3D內部函式仍由
`runtime/legacy-v114/runtime.js`維持。後續每次只替換一個頁面或一個設備模組。

## 禁止事項

- Google存檔服務不可直接修改3D場景。
- 設備模組不可直接呼叫另一設備模組。
- 頁面不可直接保存Drive資料。
- 新設備不可把程式寫進boot.js。
