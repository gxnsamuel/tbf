# TBF — Template Builder Fonts

A curated collection of **open-source font families** (TTF/OTF), organized by
style category, for use in a template/document builder project. Each category
also ships with ready-to-use CSS `@font-face` stylesheets so the fonts can be
dropped straight into a web project.

Repo: https://github.com/gxnsamuel/tbf

## 📁 Structure

```
tbf/
├── Fonts/                  # Google Fonts–style families, grouped by category
│   ├── calligraphy/        # 15 script/calligraphy families
│   ├── default-fonts/      # 7 core fallback families (Arimo, Carlito, Tinos, Liberation, Selawik...)
│   ├── display/            # 11 display/heading families (Anton, Oswald, Playfair Display...)
│   ├── handwritting/       
│   │   ├── casual/          #  casual handwriting families
│   │   └── natural/         #  natural handwriting families
│   ├── monospace/          # 5 monospace families (Courier Prime, Hack, Noto Sans Mono...)
│   ├── sans-serif/         # 50 sans-serif families (Inter, Roboto, Poppins, Montserrat...)
│   ├── serif/              # 29 serif families (Lora, Merriweather, Playfair Display...)
│   └── *.css                # per-category @font-face stylesheets
│
├── Fonts1/                 # "General Fonts" — 52 additional standalone/independent families
│   │                        #  (Satoshi, Switzer, General Sans, Geist, Clash Display, etc.)
│   │                        #  each usually in its own folder with Fonts/ + License/
│   ├── tbf_general_fonts.css   # ⭐ single consolidated stylesheet — all 59 families, one @import
│   └── tbf_other_fonts*.css    # legacy split (1–11) — same declarations, kept for compatibility
│
└── tbf_fonts.css           # top-level aggregate stylesheet
```

## 🔤 What's inside

- **~2,150+ individual font files** (`.ttf` / `.otf`) across ~150 font families
- Fonts organized into 7 broad style categories under `Fonts/`: calligraphy,
  default-fonts, display, handwriting (casual & natural), monospace,
  sans-serif, and serif
- A second collection, `Fonts1/` — the **General Fonts** set — with 59
  independently distributed families (many are "free-for-commercial-use"
  variable/display fonts distributed with their own `License/` folder — e.g.
  Satoshi, Switzer, Clash Display, General Sans, Geist, Zodiak)
- Pre-built CSS files (`tbf_*_fonts*.css`) per category, ready to `@import` or
  `<link>` into a web page/template builder for instant web-font support

### 🆕 General Fonts (`Fonts1/`)

All 59 standalone families in `Fonts1/` are now available through a single,
consolidated stylesheet — `Fonts1/tbf_general_fonts.css` — instead of having
to `@import` 11 separate split files:

```html
<link rel="stylesheet" href="Fonts1/tbf_general_fonts.css">
```

The families included:

Alan Sans · Alpino · Amulya · Author · Cabinet Grotesk · Changa · Chillax ·
Clarity City · Clash Display · Clear Sans · Creato Display · Dortmund ·
Excon · Freesentation · Gabarito · Gambarino · Gambetta · Geist · Geist Mono ·
Geist Pixel · General Sans · Geologica · Giphurs · Giphurs SC · Gmarket Sans ·
Gully (+ CD/ECD/SCD) · Hitch Grotesk · Instrument Sans (+ Condensed) ·
JHC Sines · Kreadon · Kumbh Sans · LT Karaoke Body · Mango Grotesque ·
Nacelle · Oak Sans · Pitagon Sans · Prodigy Sans · REM · Radlush ·
Rethink Sans · Rosaline · Satoshi · Science Gothic · Sentient · Spline Sans ·
Stardom · Supreme · Switzer · Synonym · Tilda Sans · Tonnelier · Unageo ·
Vercetti · Work Sans · Zodiak

The original `tbf_other_fonts1.css` through `tbf_other_fonts11.css` files are
left in place for backward compatibility, but new projects should prefer the
single `tbf_general_fonts.css` file.
- Most families include their license (`OFL.txt`, `LICENSE.txt`, or `FFL.txt`)
  alongside the font files

## 🚀 Usage

### 1. Use the pre-built CSS
Each category folder has one or more `tbf_<category>_fonts*.css` files
containing `@font-face` declarations that point at the `.ttf`/`.otf` files in
that same folder. Just include the relevant stylesheet(s) in your project:

```html
<link rel="stylesheet" href="Fonts/sans-serif/tbf_sans_serif_fonts.css">
```

Then use the font family name as normal:

```css
h1 { font-family: "Poppins", sans-serif; }
```

### 2. Use the Python font map
See `font_map.py` in this repo (or generated alongside this README) for a
`FONT_FILE_MAP` dictionary that maps every font file's name to its raw GitHub
URL, so you can fetch/download any font file directly, e.g. for a backend
template-rendering pipeline (LibreOffice, WeasyPrint, PDF generation, etc.)
that needs the actual font file rather than a browser `@font-face` link.

```python
from font_map import FONT_FILE_MAP

url = FONT_FILE_MAP["Poppins-Regular"]
# -> https://raw.githubusercontent.com/gxnsamuel/tbf/main/Fonts/sans-serif/Poppins/Poppins-Regular.ttf
```

## 📜 License

Fonts in this repository retain their original individual licenses (mostly
the **SIL Open Font License (OFL)**, with some under **Free For Personal /
Freebie Font License (FFL)** terms in `Fonts1/`). Check the `OFL.txt`,
`LICENSE.txt`, or `License/` folder shipped alongside each font family before
using it commercially.

## 🙌 Purpose

This repository exists to back a **template builder** — a tool that needs a
large, organized, locally-available font library (rather than depending on
Google Fonts at runtime) to render documents/templates with a wide variety of
typography options.