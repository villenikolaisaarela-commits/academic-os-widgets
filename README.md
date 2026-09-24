# Framewise widgets, covers and icons

Hosted files for **Framewise Academy**, a student planner template for Notion. The template embeds these files from GitHub Pages, so they are part of the paid product (see LICENSE).

## Widgets
- `clock.html`: an analog clock with digital time and date. Language and 12/24-hour format follow the viewer's device; `?h=12`, `?h=24` or `?lang=` force them.
- `clock-us.html`: the same clock, fixed to US format ("5:03:03 PM · Tue, Sep 22"). Used on the US edition's Home.
- `clock-intl.html` (same as `clock-24.html`): the same clock, fixed to 24-hour English ("17:03:03 · Tue 22 Sep"). Used on the International edition's Home.
- `timer.html`: a focus timer with Study 25, Short break 5 and Long break 15 minutes. It sits in the Focus studio block on Home. Its state is kept in the viewer's browser (localStorage), so a running session survives leaving the page and "sessions today" counts the whole day.
- `spotify.html`: a wrapper around Spotify's embed player for the Focus studio block. `?list=<playlist id>` picks the playlist, `&type=album` embeds an album and `&theme=dark|light` pins the background. It loads Spotify's player, which follows Spotify's own privacy policy.
- `whiteboard.html`: a drawing board with several boards, pen, highlighter, eraser, colours, paper styles, undo and redo, and PNG export. Boards are kept in the viewer's browser (localStorage); nothing is uploaded.
- `focus-timer.html`: a compact clock and timer in one widget.

### Embedding notes
- Every widget paints Notion's own background (#ffffff light, #191919 dark), because an embedded frame is never transparent. An embed cannot read Notion's theme, only the device setting, so `?theme=dark` or `?theme=light` pins it.
- Notion's embed frame blocks browser dialogs (alert, confirm, prompt) and downloads. The whiteboard therefore names boards inline and opens its PNG in a small panel, where it can be opened in a new tab and saved from there.
- After changing a widget, bump the `?v=` number in the embed URLs if a change must show up immediately. GitHub Pages caches files for about ten minutes.

## Covers and icons
- `covers/`: hand-painted gouache covers for pages, databases and courses (`covers/p1/`), plus arch windows for the landing pages (`covers/arch/`).
- `icons/fw1/`: the Framewise duotone icon set used in callouts and page icons.

## Privacy
The clock, timer and whiteboard make no network requests, use no cookies or tracking, and load no external fonts or scripts. Only `spotify.html` loads an external service (Spotify's player).
