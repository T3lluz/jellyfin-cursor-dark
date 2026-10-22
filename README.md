# Cursor Dark for Jellyfin

Neutral dark gray in the style of Cursor's editor theme with a purple accent.
Flat and minimal, with frosted glass on everything that floats. It's a port
of the Cursor Dark Stremio theme.

## Install

In Jellyfin, paste this one line into a Custom CSS box:

```css
@import url("https://t3lluz.github.io/jellyfin-cursor-dark/cursor-dark.css");
```

- **Every user, every device:** Dashboard → General → **Custom CSS code**
- **Just your account:** Settings → Display → **Custom CSS**

Save, then reload the page. Clients load the theme from the link, so a change
pushed to this repo reaches every device by itself: GitHub Pages publishes it
within a minute, and browsers may keep their copy for up to 10 minutes before
they check for a new one. You don't need to paste anything again.

A hard refresh doesn't skip those 10 minutes, because Jellyfin adds the custom
CSS after the page has loaded. To fetch an update right away, add a tag to the
link and change it when you want a fresh copy. The tag doesn't pin a version:
the link always serves the latest theme.

```css
@import url("https://t3lluz.github.io/jellyfin-cursor-dark/cursor-dark.css?v=2");
```

If GitHub Pages is ever down, this mirror serves the same file. It updates
much more slowly (its CDN keeps a copy for up to 12 hours, and browsers may
keep theirs for a week), so use it only as a fallback:

```css
@import url("https://cdn.jsdelivr.net/gh/T3lluz/jellyfin-cursor-dark@main/cursor-dark.css");
```

## Tweaks

Put overrides under the `@import` line in the same box:

```css
@import url("https://t3lluz.github.io/jellyfin-cursor-dark/cursor-dark.css");

:root, :root[data-theme] {
	--cx-accent: #c4a7ff;                 /* accent colour */
	--cx-accent-rgb: 196, 167, 255;       /* same colour as r, g, b */
	--jf-palette-primary-main: #c4a7ff;
	--jf-palette-primary-mainChannel: 196 167 255;
	--jf-card-borderRadius: 0.4rem;       /* sharper posters */
}
```

## Notes

- Works with Jellyfin 10.9 and newer (tested on 12.2), in both the classic
  and the experimental layout. Any Jellyfin display theme can stay selected,
  because this overrides its colours.
- Selectors use Jellyfin's own class names only, so web client updates
  shouldn't break it.
- Movie, series and season pages use a full-height hero: the backdrop
  scrolls with the page and fades into it, and the clear logo, info and
  frosted Play button sit centred at its foot. Episodes show as a grid of
  16:9 cards. Both ideas come from
  [ElegantFin](https://github.com/lscambo13/ElegantFin); the CSS here is
  written from scratch.
- The content sits on a lighter inner sheet. The header and a slim frame
  round the sheet are one pane of frosted glass, so rows that scroll under
  any edge blur instead of being cut off.
- Apple-style frosted glass throughout: header, frame, menus, dialogs,
  drawer and buttons. Panels are rounded rectangles, buttons rounded
  squares. Purple is kept for progress bars, toggles and focus.
- The player is one floating glass panel (title, seek bar, buttons) with
  the transport centred, and it blurs the video behind it in Chromium- and
  Firefox-based browsers (Zen included).
- Works in both the classic layout (Desktop Legacy) and the newer one.
