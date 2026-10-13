# RAYRE Digital Invitations v2

## Deploy
1. Create a Supabase project at https://supabase.com/dashboard .
2. In SQL Editor, run `supabase-setup.sql`.
3. In Authentication > Users, create/invite an admin email user, set a password securely. Copy their User UID.
4. In SQL Editor run: `insert into public.admins (user_id) values ('YOUR_AUTH_USER_UUID');`
5. In Project Settings > API / Data API, copy the project URL and **publishable/anon key** into `config.js`. NEVER place service_role/secret keys in frontend files.
6. Upload `index.html`, `admin.html`, `config.js` to the root of the GitHub Pages repository (and an optional licensed `assets/wedding-music.mp3`). Commit.
7. Test the public invitation RSVP from a different phone; sign in to `.../admin.html` to see it.

## Important
- Public RSVP forms can be spammed. Before real client use add CAPTCHA, rate limiting, and privacy notices; restrict guest count to invitation allocations.
- `admins` must be configured via SQL editor, not via public website.
- Public GitHub Pages is not suitable for storing private credentials or guest data. Only the publishable Supabase key belongs in config.js.
- No private data is returned to anonymous visitors by the database policies.
- RSVP form does not automatically email guests or prevent duplicates.
- Change sample venue, date, photos and music before sharing with real guests.
- The music button needs a licensed MP3 at `assets/wedding-music.mp3` and a user tap to play.
