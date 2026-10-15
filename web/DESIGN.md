---
name: PSDev Sistemas
description: Media downloader front end on cobalt; paste a link, get the file.
colors:
  brand-navy: "#0a1633"
  brand-blue: "#006dff"
  accent: "#0062e6"
  accent-hover: "#0057cc"
  accent-press: "#004db5"
  accent-dark: "#1668f0"
  accent-dark-hover: "#2272f5"
  accent-dark-press: "#125cd6"
  on-accent: "#f8faff"
  surface: "#f5f7fc"
  surface-dark: "#070d1b"
  ink: "#0b1530"
  ink-dark: "#e6ecf7"
  muted: "#56627d"
  muted-dark: "#8a97b3"
  field: "#fbfcff"
  field-dark: "#0f1729"
  field-border: "#b4bfd4"
  field-border-dark: "#2b3856"
  control: "#eaeef6"
  control-hover: "#e1e7f2"
  control-press: "#d8e0ee"
  control-dark: "#111a2e"
  control-dark-hover: "#18233b"
  control-dark-press: "#1e2a45"
  control-text: "#17223f"
  rail-ink: "#e9eef8"
  error: "#e0263b"
  error-dark: "#f0475a"
  success: "#17a34a"
  success-dark: "#2fbf62"
typography:
  headline:
    fontFamily: "Sora Variable, Segoe UI, system-ui, sans-serif"
    fontSize: "24px"
    fontWeight: 600
    letterSpacing: "-0.025em"
  title:
    fontFamily: "Sora Variable, Segoe UI, system-ui, sans-serif"
    fontSize: "20px"
    fontWeight: 600
    letterSpacing: "-0.02em"
  title-small:
    fontFamily: "Sora Variable, Segoe UI, system-ui, sans-serif"
    fontSize: "16px"
    fontWeight: 600
  input:
    fontFamily: "Sora Variable, Segoe UI, system-ui, sans-serif"
    fontSize: "15px"
    fontWeight: 500
  body:
    fontFamily: "Sora Variable, Segoe UI, system-ui, sans-serif"
    fontSize: "14.5px"
    fontWeight: 500
    lineHeight: 1.35
  body-long:
    fontFamily: "Sora Variable, Segoe UI, system-ui, sans-serif"
    fontSize: "14.5px"
    fontWeight: 400
    lineHeight: 1.8
  label:
    fontFamily: "Sora Variable, Segoe UI, system-ui, sans-serif"
    fontSize: "12.5px"
    fontWeight: 500
    lineHeight: 1.4
  rail-label:
    fontFamily: "Sora Variable, Segoe UI, system-ui, sans-serif"
    fontSize: "11px"
    fontWeight: 500
  mono:
    fontFamily: "IBM Plex Mono, ui-monospace, monospace"
    fontSize: "inherit"
rounded:
  xs: "4px"
  sm: "5px"
  inner: "8px"
  base: "12px"
  tile: "16px"
  pill: "100px"
spacing:
  hair: "3.5px"
  xs: "6px"
  sm: "10px"
  md: "12px"
  lg: "20px"
  xl: "28px"
components:
  button:
    backgroundColor: "{colors.control}"
    textColor: "{colors.control-text}"
    typography: "{typography.body}"
    rounded: "{rounded.base}"
    padding: "6px 13px"
  button-hover:
    backgroundColor: "{colors.control-hover}"
  button-press:
    backgroundColor: "{colors.control-press}"
  button-active:
    backgroundColor: "{colors.accent}"
    textColor: "{colors.on-accent}"
  button-active-hover:
    backgroundColor: "{colors.accent-hover}"
  omnibox:
    backgroundColor: "{colors.field}"
    textColor: "{colors.ink}"
    typography: "{typography.input}"
    rounded: "{rounded.base}"
    padding: "12px"
  download-key:
    backgroundColor: "{colors.accent}"
    textColor: "{colors.on-accent}"
    rounded: "{rounded.inner}"
    height: "36px"
    width: "40px"
  download-key-error:
    backgroundColor: "{colors.error}"
  download-key-done:
    backgroundColor: "{colors.success}"
  rail:
    backgroundColor: "{colors.brand-navy}"
    textColor: "{colors.rail-ink}"
    width: "80px"
  rail-tab:
    textColor: "{colors.rail-ink}"
    typography: "{typography.rail-label}"
    rounded: "{rounded.base}"
    padding: "10px 3px"
  rail-tab-active:
    backgroundColor: "{colors.accent}"
    textColor: "{colors.on-accent}"
  subnav-tab:
    textColor: "{colors.control-text}"
    typography: "{typography.body}"
    rounded: "{rounded.base}"
    padding: "6px"
  switcher-segment-active:
    backgroundColor: "{colors.accent}"
    textColor: "{colors.on-accent}"
    rounded: "{rounded.inner}"
    height: "33px"
---

# Design System: PSDev Sistemas

## Overview

**Creative North Star: "The Lit Console"**

The interface is a console that lights up, the way the blue S in the PSDev logo glows out of navy. A navy rail holds the frame in both themes; inside it, a calm field of cool ink-blue neutrals carries one centered link box. When the user focuses that box or pastes a valid link, it lights in electric blue and the download button becomes a filled blue key. Everything else stays quiet so that lit state reads instantly.

Density is low and task-first: one column, a 640px field, a short row of controls, and plain Portuguese copy in sentence case. Depth comes from accent glow, not from grey drop shadows. The brand lives in exact details: the logo lockup above the field, the monogram atop the rail, the blue focus ring, the press scale on the key.

The world refuses cobalt's grey monospace minimalism and the generic white SaaS card. Neutrals are never pure black or pure white; every grey is tinted toward navy.

**Key Characteristics:**
- Navy rail (brand navy) in light and dark themes alike; content surface switches with the system theme.
- Electric blue marks only the current/on state of a control, the focus ring, and the valid-link download key.
- Sora Variable for every piece of UI text; IBM Plex Mono only inside code, pre and kbd.
- 12px corners on every control and container; nested controls step down to 8px.
- Tabler outline icons only.
- The omnibox focus glow is the signature.

## Colors

A two-color brand (navy and electric blue, sampled from the logo) over cool ink-blue neutrals, with separate light and dark accent steps tuned for contrast.

### Primary
- **Electric Key Blue** (accent, light theme; accent-dark in dark theme): the only color that means "this is live." Fills the selected rail tab, the selected switcher segment, the download key, the enabled toggle track, text selection and the caret; draws the 2px focus ring and the 1.5px inset stroke of the selected settings tile. Hover and press step darker in light, lighter in dark.
- **Logo Blue** (brand-blue): the logo's own S and the source of the glow tints (accent-glow at 0.28 alpha in light, 0.38 in dark; accent-soft at 0.10 / 0.16). It is not used as a solid UI fill; the UI accent is a contrast-tuned step of it so white labels stay legible.

### Neutral
- **Rail Navy** (brand-navy): the sidebar rail and mobile bottom bar in both themes, and the tile behind every app icon. Also the base of the mobile tab-bar fade gradient.
- **Rail Ink** (rail-ink): labels and icons on the rail, at 75% opacity idle and 100% on hover.
- **Cool Paper** (surface) / **Deep Ink Night** (surface-dark): the content surface. Never #fff, never #000.
- **Ink Navy** (ink) / **Ink Mist** (ink-dark): primary text and titles.
- **Slate Blue Grey** (muted / muted-dark): placeholders, subtext, captions, idle subnav icons, the terms note.
- **Field White** (field / field-dark): the omnibox and popups; a hair lighter (or lifted) from the surface.
- **Field Edge** (field-border / field-border-dark): 1.5px resting stroke of the omnibox; also the off-state toggle track.
- **Control Mist** (control family, light and dark): the fill of resting buttons, switcher troughs and idle subnav icon tiles, with a 1px inset stroke of ink at 6-7% alpha.

### Status
- **Signal Red** (error / error-dark) and **Signal Green** (success / success-dark): the download key's error and done fills, error status tiles (red at 12% tint) and destructive dialog icons. They never decorate.

### Named Rules
**The One Live Thing Rule.** Electric blue marks only the current or on state of a control, the focus ring, and the download key. Within any one control group, at most one element is blue. Idle tiles, idle tabs, headings, links and surfaces stay neutral.

**The Navy Rail Rule.** The rail is brand navy in both themes. It does not invert with the theme; only the content surface does.

**The No Pure Neutrals Rule.** Every neutral is tinted toward navy. Pure #000 and #fff do not appear.

## Typography

**Display Font:** none; the logo lockup does display duty.
**Body Font:** Sora Variable (self-hosted via @fontsource-variable/sora), falling back to Segoe UI and system-ui.
**Label/Mono Font:** IBM Plex Mono, only for code, pre and kbd.

**Character:** Sora's geometric, slightly wide forms echo the heavy geometric caps of the PSDEV wordmark without imitating them. Weight does the hierarchy; sizes stay compact.

### Hierarchy
- **Headline** (600, 24px, -0.025em): page titles such as "Ajustes".
- **Title** (600, 20px, -0.02em): section titles; dialog titles run at 19px.
- **Title small** (600, 16px): settings section headings ("Tema", "Idioma").
- **Input** (500, 15px): the link text inside the omnibox.
- **Body** (500, 14.5px, 1.35): buttons, subnav labels, dialog body (dialog body uses 1.7 leading in muted ink).
- **Body long** (400, 14.5px, 1.8): About and terms prose; 14px under 535px.
- **Label** (500, 12.5px, 1.4): subtext under settings, in muted ink. The terms note sits at 12px (11px on phones).
- **Rail label** (500, 11px): sidebar tab labels.

### Named Rules
**The One Family Rule.** All UI text is Sora. Mono appears only for code-like content (code, pre, kbd); filenames and data may use it, labels and buttons never do.

**The Sentence Case Rule.** Copy is PT-BR sentence case ("Cole o link aqui", "Serviços compatíveis"). No uppercase labels, no letter-spaced overlines.

## Layout

A two-column app grid: the rail is 80px plus 4px inner padding each side, and the content surface fills the rest, separated by a 1px hairline (ink at 6% alpha). The save page centers a single column vertically: the logo lockup (clamp 180px to 248px wide) then, 28px below, the omnibox (max 640px) with its action row 10px under the field. The terms note pins to the bottom.

Base padding is 12px; the larger rhythm steps are 20px and 28px; small gaps are 6px and 10px. Settings use a two-pane layout: a subnav list on the left and 640px-ish content on the right.

Under 535px the rail becomes a bottom tab bar (50px plus safe-area inset), the content surface takes rounded bottom corners (24px), the page gap tightens to 20px, and the brand monogram leaves the rail. Under 440px the omnibox action row stacks and its buttons go full width. Under 750px subnav tabs merge into a single grouped list with chevrons.

## Elevation & Depth

Flat by default. Surfaces separate by tone (rail navy, cool paper, control mist, field white) and by 1px inset strokes at 6-9% alpha, never by grey drop shadows. The only lifted shadows are blue: an offset, blurred accent glow under whatever is live.

### Shadow Vocabulary
- **Omnibox focus glow** (`box-shadow: 0 0 0 4px var(--accent-soft), 0 12px 32px -14px var(--accent-glow)` with `outline: 2px solid var(--accent)`): the signature lit state of the link box.
- **Key glow** (`box-shadow: 0 4px 12px -6px var(--accent-glow)`): under the download key.
- **Rail tab glow** (`box-shadow: 0 6px 18px -8px var(--accent-glow)`): under the selected rail tab.
- **Hairline stroke** (`box-shadow: 0 0 0 1px var(--button-stroke) inset`): resting buttons, troughs, tiles.
- **Field rest** (`box-shadow: 0 0 0 1.5px var(--input-border) inset, 0 1px 2px rgba(11,21,48,0.04)`): omnibox at rest.

### Named Rules
**The Glow Is Blue Rule.** If something casts light, it is live and the light is accent-glow. Neutral elements get a hairline stroke, not a shadow.

## Shapes

One soft corner everywhere: 12px on buttons, the omnibox, rail tabs, subnav tabs and switcher troughs. Nested controls subtract their inset so curves stay concentric: the download key sits at 8px inside the field; switcher segments sit at 12px minus 3.5px. Small 5px corners are reserved for tag-sized pieces (subnav icon tiles, the beta tag), 4px for inline code. Toggles are full pills; the clear button is a circle. Status tiles are 56px squares at 16px.

Segmented switchers are joined rectangles at 12px (small) or a 12px trough holding inset segments (big). They are not pills.

## Components

### Buttons
Quiet, tactile, mist-filled.
- **Shape:** 12px corners.
- **Default:** control mist fill, control text, 1px inset hairline, 6px 13px padding, 14.5px/500.
- **Hover / Press:** one step darker mist on hover (hover-capable devices only), another on press.
- **Active (selected):** accent fill with on-accent text; hover steps to accent-hover. Focused active buttons switch to a 2px ink outline offset 2px so focus stays visible on blue.
- **Focus:** 2px accent outline at -2px offset (inset).

### Omnibox (signature)
The product. A 640px field with a link icon on the left, the link in 15px/500 ink, a circular clear button and, once the link is valid, the download key on the right.
- **Rest:** field fill, 1.5px field-edge stroke, 12px corners.
- **Focused / valid link:** 2px accent outline, 4px accent-soft ring, offset accent-glow shadow; the link icon turns accent. Transitions over 0.25s on cubic-bezier(0.16, 1, 0.3, 1); disabled under reduced motion.
- **Action row:** a small mode switcher (Auto / Áudio / Sem som) left, a Colar button right.

### Download Key
A filled accent key, 40 by 36px, 8px corners, white Tabler icon at 20px with stroke 2.2. The icon states the request: arrow (ready), rotating loader (working or checking), check on green (done), exclamation on red (error). Press scales to 0.95.

### Navigation
- **Rail:** brand navy; PS monogram (40px, scales 1.06 on hover) on top; tabs stacked with 22px Tabler icons and 11px labels at 75% opacity. Hover adds rail-ink at 8% fill. The selected tab is a full accent block with rail-tab glow and a short press-bounce on selection.
- **Mobile:** the rail becomes a bottom bar; tabs lay out horizontally with fading gradient edges.
- **Subnav (settings):** rows with a 28px icon tile and 14.5px/500 label. Idle tiles are control mist with muted icons; the selected row takes an accent-soft fill with a 1.5px accent inset stroke and an accent tile with a white icon.

### Switcher
- **Small:** joined 12px buttons; the selected segment is accent.
- **Big:** a control-mist trough with 3.5px padding holding transparent segments 33px tall; the selected segment is an accent block.

### Dialogs
Small dialogs center at max 340px with a 50px Tabler icon (stroke 1.5, red when destructive) or a status tile, a 19px title and muted 14.5px/1.7 body. Backdrop is a translucent cool wash (light) or navy-black (dark).

### Brand Lockup and Mark
- **Lockup:** the full PSDev Sistemas logo above the omnibox, 180-248px wide, swapping to the reverse variant in dark theme. Enters with a 0.6s rise-and-settle when motion is allowed.
- **Mark:** the P+S monogram atop the rail and as the 64px brand status glyph; reverse variant in dark theme.
- **Provenance:** every brand raster is derived with Pillow from the client's own logo file `logopsdev.png` (transparent RGBA). `static/brand/logo.png` is the full lockup crop; `static/brand/mark.png` is the P+S monogram crop. The `-reverse` variants recolor navy pixels (G channel below 80) to #ECF1FA and keep the electric blue. `static/favicon.png` and `static/icons/**` center the reverse monogram on a brand-navy tile at 0.66 of the tile (0.52 for maskable icons). No generated imagery ships.

## Do's and Don'ts

### Do:
- **Do** keep electric blue on one live element per control group: selected tab, selected segment, selected subnav tile, focus ring, enabled toggle, download key.
- **Do** keep the rail brand navy in both themes and put the PS monogram at its top.
- **Do** use 12px corners, stepping nested controls down by their inset (8px for the download key).
- **Do** express lift as accent glow, and only on live elements; use 1px inset hairlines for everything else.
- **Do** use Tabler outline icons at stroke 1.5-2.2 (2.2 on the download key, 1.5 in dialogs and tiles).
- **Do** write PT-BR sentence case, and make errors say what happened and what to try next.
- **Do** derive any new brand raster from `logopsdev.png` and record its provenance here.

### Don't:
- **Don't** use blue for idle tiles, headings, body links or surfaces.
- **Don't** use pure #000 or #fff; pick the tinted neutrals.
- **Don't** set UI labels or buttons in mono, or set any text in a face other than Sora outside code.
- **Don't** use uppercase or letter-spaced labels above headings.
- **Don't** add grey drop shadows to cards or containers.
- **Don't** reintroduce cobalt's name, logo, or mascot anywhere except the About credit.
- **Don't** generate or redraw the logo; use the derived rasters.
