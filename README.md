# Basketball Signup Web

手機版單頁網頁,顯示 LINE 籃球小幫手的點擊報名名單。純靜態、零相依,直接開 `index.html` 即可。

## 使用

- 直接用瀏覽器打開 `index.html`,或丟到任何靜態主機(GitHub Pages / Netlify / Cloudflare Pages)。
- 透過 JSONP 讀取統計 GET API,不受 CORS 限制。

## 資料來源

統計 API(公開唯讀):

```
GET https://script.google.com/macros/s/AKfycbziLnjHkUEH1Tn1Mz92ioZm1g5_K1v2HxoZ3H2jboX5QXwYvmIKIpMVBu092-QayqGz/exec?action=stats
```

只回傳 `displayName` + `count`,只計算「點擊報名」。

## 時間區間

- 預設顯示 **當週** 報名視窗:週二 10:00 ~ 週三 18:00(對齊打球日,以本地時間計算,週一~週日打開都對到同一週那場球)。
- 可用網址參數覆寫,例如:
  `index.html?startTime=2026-07-07 00:00&endTime=2026-07-08 23:59`

## 設定

如換了 Apps Script 部署,改 `index.html` 裡的 `API_BASE` 常數即可(記得用不含 `/u/1/` 的標準網址)。
