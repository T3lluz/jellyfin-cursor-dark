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
pushed to this repo reaches every device on its next reload. You don't need
to paste anything again.

If GitHub Pages is ever down, this mirror serves the same file (jsDelivr
caches it for up to 12 hours):

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
- Movie, series and season pages use a full-height hero: the backdrop fades
  into the page, and the clear logo, info and frosted Play button sit
  centred at its foot. Episodes show as a grid of 16:9 cards. Both ideas
  come from [ElegantFin](https://github.com/lscambo13/ElegantFin); the CSS
  here is written from scratch.
- Play buttons, menus, dialogs and the player controls are frosted glass.
  Purple is kept for selected tabs and progress bars.
- The player controls are three glass pills: the seek bar, the transport
  buttons and the right-hand buttons.
