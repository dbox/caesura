# Caesura <img src="https://rawgit.com/jonathantneal/media-expressions-spec/gh-pages/css-logo.svg" alt="CSS Logo" width="90" height="90" align="right">

[![npm version](https://badge.fury.io/js/caesura.svg)](https://badge.fury.io/js/caesura)

Caesura is a reasonable breakpoint scale using [@custom-media](https://github.com/postcss/postcss-custom-media).
> **Note:** This project is in early development, and versioning is a little different. [Read this](http://markup.im/#q4_cRZ1Q) for more details.

```css
.foo {
  border: 1px solid green;

  @media (--xl) {
    border: 3px solid red;
  }
```

### Installation

Install with npm:
`npm install caesura`

Make sure you have [postcss-import](https://github.com/postcss/postcss-import) and [@custom-media](https://github.com/postcss/postcss-custom-media) (or cssnext) installed, then import caesura at the top of your css:

```
@import 'caesura';

<!-- Your css code here -->
```
That's it!

### The scale

```
Breakpoint:     320px       448px         768px         1024px       1280px             1800px
            ──────┬───────────┬─────────────┬─────────────┬─────────────┬──────────────────┬─────
      Name:    '--xs'       '--s'         '--m'         '--l'        '--xl'              '--hd'
```

```css
@custom-media --xs (width < 320px);
@custom-media --s (width < 448px);
@custom-media --m (width < 768px);
@custom-media --l (width < 1024px);
@custom-media --xl (width < 1280px);
@custom-media --hd (width < 1800px);

@custom-media --above-xs (width >= 320px);
@custom-media --above-s (width >= 448px);
@custom-media --above-m (width >= 768px);
@custom-media --above-l (width >= 1024px);
@custom-media --above-xl (width >= 1280px);
@custom-media --above-hd (width >= 1800px);

@custom-media --retina (-webkit-min-device-pixel-ratio: 2), (min-resolution: 192dpi);
@custom-media --landscape (orientation: landscape);
@custom-media --portrait (orientation: portrait);
```

I've yet to find a great use-case for needing `below` or `at` rules for media queries. I'm happy to add/revise if there are other examples people need. Furthermore, [content should dictate breaking points](https://github.com/jescalan/gps#breakpoints), but sometimes it's just nice to have your trusty standby stops.

Feel free to point out any issues, or open a PR!
