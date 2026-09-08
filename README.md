# 方程移項大激鬥

Secondary-school equation transposition game using **HTML/CSS/JavaScript + Supabase Auth + PostgreSQL**, deployable on GitHub Pages or Netlify.

## Included
- Student email/password login and signup
- Class/seat profile
- Lv1 / Lv2 / Lv3 equation-transposition gameplay
- 10 questions per game
- Timer and +2 second penalty for incorrect actions
- Per-game and per-answer records in Supabase
- Public leaderboard RPC without exposing email addresses
- Teacher dashboard (`teacher.html`) for overview, student performance and question statistics
- Editable Supabase question bank

## Supabase project
The connected project is already configured in the deployment files. The database migrations have been applied to the connected project.

## Teacher account
New accounts default to `student`. After creating the teacher account, promote its profile once in Supabase SQL Editor:

```sql
update public.profiles
set role = 'teacher'
where id = 'YOUR_AUTH_USER_UUID';
```

Do not expose a `service_role` key in frontend code.

## GitHub Pages
Settings → Pages → Deploy from branch → `main` → `/ (root)`.

## Files
- `index.html` — student game
- `teacher.html` — teacher dashboard
- `config.js` — Supabase public configuration
- `supabase_schema.sql` — reference schema/migrations
- `.nojekyll` — GitHub Pages helper

## Security note
The current game client records timer/question events but still performs gameplay timing and validation in the browser. It is suitable for classroom use/prototyping. For a high-stakes competition, move question selection, scoring and timing validation to trusted server-side functions.
