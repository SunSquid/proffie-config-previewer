
[README.md](https://github.com/user-attachments/files/26613046/README.md)
# Proffie config.h Blade Previewer

A browser-based tool for previewing ProffieOS blade styles from a `config.h` file — no board required.

Built to fill a gap in the Proffie community: previously there was no way to preview all presets in a config at once before flashing to the board.

**[Try it live →](https://your-username.github.io/proffie-previewer)**

![screenshot placeholder](screenshot.png)

---

## Features

- **Drop or paste** any `config.h` — no install, no dependencies
- **Animated blade preview** with ignition wipe, retraction, swing dot, and clash flash
- **Supports all style complexity levels:**
  - Simple: `StyleNormalPtr`, `EASYBLADE`
  - Medium: `InOutHelper`, `AudioFlicker`, `Stripes`, `Fire`, `Rainbow`
  - Complex: `Layers<>` with `AlphaL`, `Bump`, `Scale`, `SwingSpeed`, `BladeAngle`
  - Advanced: `ColorChange`, `Gradient`, `Pulsing`, `Sparkle`
- **Node tree inspector** — see exactly how your style was parsed
- **Multi-preset support** — all presets shown in a grid, click to select
- **Works with ProffieOS V2.2 and V3+**
- **Dark mode** supported automatically

---

## Usage

### Option A — hosted (GitHub Pages)
Visit the live URL above. No install needed.

### Option B — single HTML file
Download `proffie-previewer.html` and open it in any modern browser. Works fully offline.

### Option C — run locally
```bash
git clone https://github.com/your-username/proffie-previewer
cd proffie-previewer
# open index.html in your browser, or:
npx serve .
```

---

## Deploying to GitHub Pages

1. Fork or clone this repo
2. Go to **Settings → Pages**
3. Set source to `main` branch, `/ (root)`
4. Your site will be live at `https://your-username.github.io/proffie-previewer`

That's it — no build step required.

---

## Supported style nodes

| Node | Support |
|------|---------|
| `StyleNormalPtr` | ✅ Full |
| `EASYBLADE` | ✅ Expanded to StyleNormal |
| `Layers<>` | ✅ Full compositing |
| `BaseLayerF` | ✅ |
| `AlphaL` + `Bump` (static) | ✅ Fixed zones |
| `AlphaL` + `Bump<Scale<SwingSpeed,...>>` | ✅ Dynamic swing dot |
| `InOutHelper` / `InOutHelperL` | ✅ Ignition wipe |
| `AudioFlicker` | ✅ Animated |
| `Fire` / `StyleFire` | ✅ Animated |
| `Stripes` / `HardStripes` | ✅ Animated |
| `Rainbow` | ✅ Animated |
| `Gradient` | ✅ |
| `Pulsing` | ✅ Animated |
| `ColorChange` | ✅ Cycles |
| `Sparkle` | ✅ Animated |
| `ClashF` / `BlastF` / `LockupF` | ✅ Event masks |
| `Scale` / `SwingSpeed` / `BladeAngle` | ✅ Scalar evaluation |

---

## Limitations

- Preview is an **approximation** — the ProffieOS style engine is a C++ template system; this tool reimplements the rendering logic in JavaScript
- **Sub-blades** (splitting one strip into logical segments) are not yet supported — each `StylePtr` renders as a full blade
- Audio-reactive effects (`AudioFlicker`) are simulated with noise rather than real audio input

---

## Contributing

PRs welcome. Key areas for improvement:
- Sub-blade / crossguard support
- More style nodes (`OriginalBlast`, `LockupL`, `TransitionEffectL`)
- GIF export of blade animation
- Shareable preset URLs

---

## Credits

- [ProffieOS](https://github.com/profezzorn/ProffieOS) by Fredrik Hubinette (profezzorn)
- Style reference: [fett263.com](https://www.fett263.com)
- Built with React

## License

MIT
