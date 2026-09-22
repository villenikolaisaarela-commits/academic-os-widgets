# Optional widgets: Clock & Focus Timer

- `clock.html`: analog clock with digital time and date (the left column on Home).
- `timer.html`: Pomodoro timer with Pomodoro 25, Short break 5 and Long break 15, plus Start/Reset (the right column on Home).
- `focus-timer.html`: a compact widget with the clock and timer combined (Focus 25 / Deep 50 / Break 5 / Long break 15).

`focus-timer.html` is a single, self-contained HTML file. It makes **no network requests**, stores nothing, follows the system light/dark theme, and plays a short beep when a session ends.

**Academic OS works fully without it.** Home already shows today's date and the current semester week.

## Why it is a separate file
Notion does not run uploaded HTML files: an uploaded `.html` embed shows a spinner forever. To embed the timer, it must be served from a web address.

## Option A: open it locally (simplest)
Double-click `focus-timer.html` and keep the browser tab next to Notion.

## Option B: host it for free and embed it
Any static host works. Two free options:
1. **GitHub Pages:** create a public repository, upload `focus-timer.html` as `index.html`, and enable Pages (Settings → Pages → Deploy from branch). You get a URL like `https://<you>.github.io/<repo>/`.
2. **Netlify Drop:** go to app.netlify.com/drop and drag the folder containing the file. You get a URL instantly.

Then, in Notion, type `/embed` on Home (the right-hand column works well), paste the URL, and resize the embed to about 260 px high.

## Privacy
The file contains no tracking, fonts or external scripts. You can read the whole source in a text editor; it is under 6 KB.

## For the creator
Don't host the timer on a server you control **for buyers**. That would create a dependency and a maintenance obligation. Ship the file and these instructions only.
