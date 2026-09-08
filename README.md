# 方程移項大激鬥（第一階段）

中學數學方程移項速度遊戲：HTML/CSS/JavaScript + Supabase PostgreSQL。

## 學生端
- 不需要註冊
- 不需要登入
- 只輸入班別學號，例如 `1B02`
- Lv1 / Lv2 / Lv3
- 每局 10 題
- 計時
- 錯誤操作 +2 秒
- 成績及作答事件寫入 Supabase
- 雲端排行榜

## 教師端
- `teacher.html`
- 不需要登入
- 顯示整體統計、學生表現、最佳／平均時間、錯誤次數及題型統計
- 後台資料透過 Supabase public RPC 提供，不直接公開資料表

## GitHub Pages
GitHub repository：`andrewhong0629/equation-transposition-game`

若尚未開啟 Pages：
Settings → Pages → Build and deployment → Deploy from branch → `main` → `/ (root)`。

開啟後網址：
- 學生遊戲：`https://andrewhong0629.github.io/equation-transposition-game/`
- 教師平台：`https://andrewhong0629.github.io/equation-transposition-game/teacher.html`

## 檔案
- `index.html` — 學生遊戲
- `teacher.html` — 教師平台
- `config.js` — Supabase 公開設定
- `supabase_schema.sql` — 資料庫參考 schema
- `.nojekyll` — GitHub Pages helper

## Supabase
目前前端使用的是 publishable/anon key，沒有把 service_role key 放入網站。

## 安全提示
學生端為免登入模式，因此班別學號本身不是身份驗證。適合課堂遊戲及一般練習；若日後要作正式校內比賽，可再加入教師 PIN、裝置限制、伺服器端題目及計時驗證。