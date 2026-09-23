# Optional widgets: Clock, Focus Timer & Whiteboard

- `clock.html`: analog clock with digital time and date. Language and 12/24-hour format follow the viewer's device (`?h=12`, `?h=24` or `?lang=` force them).
- `clock-us.html`: the same clock, fixed to US format ("5:03:03 PM · Tue, Sep 22"). Used on the US edition's Home.
- `clock-intl.html` (= `clock-24.html`): the same clock, fixed to 24-hour English ("17:03:03 · Tue 22 Sep"). Used on the International edition's Home.
  The edition files format the text themselves, because Notion's desktop app can ignore a requested locale.
- `timer.html`: focus timer with Study 25, Short break 5 and Long break 15, plus Start/Reset. It sits in the **Focus studio** block on Home (right column) together with a Spotify bookmark and the *Log study session* button. Like the clock, it paints Notion's own background and takes the same `?theme=` override; its spacing scales with the embed's height, so it fits whatever size the block is dragged to.
- `spotify.html`: a wrapper around Spotify's embed player for the Focus studio block. It paints Notion's background and gives Spotify's player a fixed 352 px height (152 px in a short block), because Spotify decides its layout from the iframe height at load time and paints white under a compact player. `?list=<playlist id>` picks the playlist, `&type=album` embeds an album, `&theme=dark|light` pins the background.
- `whiteboard.html`: a drawing board with six colours, three pen sizes, eraser, undo and Save PNG. The drawing is kept in the viewer's own browser (localStorage); nothing is uploaded.
- `focus-timer.html`: a compact widget with the clock and timer combined (Focus 25 / Deep 50 / Break 5 / Long break 15).

- `covers/course-*-sage.jpg`: the pale-sage line-art course covers used on the Home gallery `course-math.jpg` etc. are the original white versions).

## The clock's background and theme
The clock paints **the same background Notion uses** — `#ffffff` in light mode, `#191919` in
dark mode — so the embed blends into the page instead of looking like a card.

A `background: transparent` page does **not** work here: an embedded frame is painted on the
browser's own base canvas, which is white, so the Notion page never shows through. On a dark
Notion page that produced light ink on white and the clock was unreadable.

An embedded page also cannot read Notion's own theme, only the viewer's **device** setting.
If someone runs Notion in dark mode while their device is in light mode (or the other way
round), the clock shows as a pale or dark rectangle. Add `?theme=dark` or `?theme=light` to
the embed URL to pin it, e.g.
`https://<you>.github.io/academic-os-widgets/clock-us.html?theme=dark`.

`focus-timer.html` is a single, self-contained HTML file. It makes **no network requests**, stores nothing, follows the system light/dark theme, and plays a short beep when a session ends.

**Framewise Academy works fully without it.** Home already shows today's date and the current semester week.

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
