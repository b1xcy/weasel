# Koxia skin for Weasel

This branch ports the supplied Sogou Koxia skin to Weasel's candidate window.
The original artwork is credited in `output/data/koxia/README.md` to 霜奶仙
(Mihuashi ID).

## What is ported

- `skin1.png` is rendered as a DPI-aware nine-slice candidate-window background.
- The original 119/206 horizontal and 74/34 vertical fixed regions are preserved.
- The original pink text colors, 16-point font, horizontal candidate layout, and
  transparent highlight treatment are represented in `output/data/weasel.yaml`.
- Candidate wrapping is disabled so the background only expands horizontally;
  vertical stretching would cross the character artwork.
- `skin2_1.png` and `skin2_2.png` are included as source artwork for later compact
  or vertical variants. Weasel does not use Sogou's separate status-bar widgets.

## Build and use

Build Weasel normally, then install from the generated package. The installer
copies the Koxia PNG files to the shared `data/koxia` directory and the bundled
`weasel.yaml` enables the skin by default.

For a development install, copy `output/data/koxia` beside the installed
`weasel.yaml`, replace that file with `output/data/weasel.yaml`, and redeploy.
Existing user overrides in `%APPDATA%/Rime/weasel.custom.yaml` still take
precedence over the bundled defaults.

The PNG background extension also accepts user resources. Put a PNG below
`%APPDATA%/Rime`, set `style/background_image` to its relative path, configure
the four `style/background_image_border_*` values, and redeploy.

## Artwork licensing

The supplied skin metadata does not state a redistribution license. Confirm the
artist's permission before publishing binaries or pushing the artwork to a
public repository.
