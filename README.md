# TegakiAnime - Web Frame-by-Frame Animation Drawing Tool

A web-based animation drawing tool for creating frame-by-frame animations with APNG and GIF export capabilities. Originally designed for use with image boards like めぶきちゃんねる.

![Version](https://img.shields.io/badge/version-1.0.0-blue)
![License](https://img.shields.io/badge/license-MIT-green)
![JavaScript](https://img.shields.io/badge/javascript-ES2015+-yellow)

## Features

- **5-frame Animation Canvas**: Draw up to 5 frames for creating animations
- **Multiple Drawing Tools**:
  - Freehand pen with adjustable size
  - Eraser with independent size control
  - Pressure sensitivity support for compatible devices
- **Onion Skin Preview**: View previous/next frames semi-transparently to maintain continuity
- **Real-time Preview**: Play back your animation to check motion and timing
- **Keyboard Shortcuts**: Quick access to tools and frame switching
- **Undo/Redo**: Full history support per layer
- **Copy/Paste**: Transfer drawings between frames
- **Export Options**:
  - APNG (Animated PNG) export
  - GIF export with adjustable frame timing
- **Responsive Design**: Works on desktop, tablet, and touch devices

## Installation

### Option 1: Use as Bookmarklet (Recommended for Casual Use)

Add this as a bookmark in your browser:

```javascript
javascript:(function(){if(!window.tegakiStart){var s=document.createElement('script');s.charset='UTF-8';s.src='https://toshinka.github.io/tegaki/tegaki_anime_test/tegaki-loader_anime.js';document.body.appendChild(s)}else{window.tegakiStart()}})();
```

Click the bookmark on any webpage to launch the tool.

### Option 2: Self-Hosted Installation

1. Clone the repository:
```bash
git clone https://github.com/toshinka/tegaki.git
cd tegaki/tegaki_anime_test
```

2. Include in your HTML:
```html
<!-- Required Libraries -->
<script src="libs/upng.js"></script>
<script src="libs/pako.js"></script>
<script src="libs/gif.js"></script>

<!-- TegakiAnime Core -->
<script src="src/tegaki_anime_core.js"></script>

<!-- Loader -->
<script src="tegaki-loader_anime.js"></script>
```

3. Initialize in your page:
```html
<div id="tegaki-container"></div>
<script>
window.TegakiAniStart = function() {
    new window.TegakiAnimeCore(document.getElementById('tegaki-container'));
};
window.TegakiAniStart();
</script>
```

## Usage

### Basic Workflow

1. **Select a Frame**: Click on the frame thumbnails at the bottom or press `1-5`
2. **Draw**: Use the pen tool (default) to draw on the canvas
3. **Switch Tools**: Press `E` for eraser, `P` for pen
4. **Refine**: Use onion skin to see neighboring frames while drawing
5. **Preview**: Click "プレビュー" (Preview) to check your animation
6. **Export**: Generate APNG or GIF files when complete

### Keyboard Shortcuts

| Key | Action |
|-----|--------|
| `1-5` | Switch between frames |
| `P` | Pen tool |
| `E` | Eraser tool |
| `Ctrl+Z` | Undo |
| `Ctrl+Y` | Redo |
| `Ctrl+C` | Copy current frame |
| `Ctrl+V` | Paste to current frame |

### Tool Controls

- **Pen Size**: Adjust with the slider (1-20px)
- **Eraser Size**: Adjust with the slider (5-50px)
- **Pressure Sensitivity**: Works with stylus input (0.0-2.0)
- **Onion Skin**: Toggle with ON/OFF button, adjust visible frames (1-3)
- **Frame Delay**: Set animation speed in milliseconds (10-2000ms)

## Supported Browsers

- Chrome/Chromium 60+
- Firefox 55+
- Safari 12+
- Edge 79+
- Mobile browsers with Canvas API support

Required features:
- Canvas API
- Pointer Events API (for pressure sensitivity)
- Uint8ClampedArray support

## Export Formats

### APNG (Animated PNG)
- Best for web use and modern platforms
- Supports transparency
- Smaller file sizes than GIF
- Supported in all modern browsers

### GIF
- Wide compatibility (legacy browsers and social media)
- Larger file sizes
- No transparency support in most cases
- Good for quick sharing

## Troubleshooting

### "GIF Worker が初期化されていません" (GIF Worker not initialized)

**Solution**: The worker script failed to load. Try:
1. Refresh the page
2. Check browser console for network errors
3. Ensure `gif.worker.js` is in the correct path
4. Check CORS settings if self-hosting

### Pressure sensitivity not working

**Solution**: 
- Ensure you're using a compatible device (stylus/pen)
- Some browsers limit pressure API - try a different browser
- Verify Pointer Events are enabled in browser settings

### Export generates blank files

**Solution**:
1. Draw on the canvas before exporting
2. Check that required libraries are loaded (UPNG.js, pako.js, gif.js)
3. Check browser console for error messages
4. Try a different browser

### Performance is slow

**Solution**:
- Reduce the number of visible onion skin frames
- Close other browser tabs
- Try a modern browser (Chrome/Edge perform best)

## Dependencies and Licenses

This project uses the following libraries:

| Library | Version | License | Purpose |
|---------|---------|---------|---------|
| [UPNG.js](https://github.com/jnordberg/upng) | Latest | MIT | APNG encoding |
| [pako](https://github.com/nodeca/pako) | Latest | MIT | PNG compression |
| [gif.js](https://github.com/jnordberg/gif.js) | Latest | MIT | GIF encoding |

All dependencies are MIT licensed and included in this distribution.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

```
MIT License

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software.
```

## Contributing

Contributions are welcome! Please feel free to:
- Report bugs via GitHub Issues
- Submit feature requests
- Create pull requests for improvements

## Changelog

### v1.0.0 (Current)
- Initial release
- Frame-by-frame animation drawing
- APNG and GIF export
- Onion skin preview
- Full undo/redo support
- Pressure sensitivity support
- Keyboard shortcuts
- Touch device support

## Credits

Created for the めぶきちゃんねる community and animation enthusiasts.

## Disclaimer

This tool is provided as-is for personal and educational use. Users are responsible for ensuring their animations comply with platform rules and local laws. The authors are not liable for misuse or any damages caused by this software.

---

For more information and live demo, visit: https://github.com/toshinka/tegaki
