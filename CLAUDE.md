# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Personal portfolio website for Krishnal Panara, a web developer based in India. Built with vanilla HTML, CSS, and JavaScript featuring smooth animations via GSAP and Locomotive Scroll.

## Technology Stack

- **Frontend**: Pure HTML5, CSS3, JavaScript (ES6+)
- **Animation**: GSAP 3.12.2 (CDN)
- **Scrolling**: Locomotive Scroll 3.5.4 (CDN)
- **Icons**: RemixIcon 3.5.0
- **Typography**: Google Fonts (DM Sans, Holtwood One SC, Inter, Open Sans, Roboto)

## Project Structure

```
index.html    # Main HTML structure
index.css     # Primary styles and layout
loco.css      # Locomotive Scroll scrollbar styles
script.js     # GSAP animations and interactivity
*.png         # Project showcase and profile images
```

## Key Architecture

### Animation System (`script.js`)

The site uses three interconnected animation systems:

1. **GSAP Timeline** - Page load animations stagger `.boundingelem` elements using `Expo.easeInOut` easing. Elements start with `transform: translateY(100%)` and animate to visible.

2. **Custom Cursor** - `#minicircle` follows mouse position with scale distortion based on movement velocity (clamped 0.5-1.2). Uses `cubic-bezier(0.19, 1, 0.22, 1)` transitions.

3. **Project Hover Images** - Images within `.elem` cards appear on mouseenter, follow cursor position, and rotate based on horizontal mouse delta (clamped -20° to 20°).

### Locomotive Scroll Integration

The `#main` container is passed to Locomotive Scroll for smooth scrolling behavior. The scrollbar is styled in `loco.css` with `.c-scrollbar` and `.c-scrollbar_thumb` classes.

### CSS Layout Patterns

- **Text Reveal Animation**: `.bounding` containers have `overflow: hidden` to clip `.boundingelem` children that slide up into view
- **Block Text Alignment**: `.blocktext` uses `flex-direction: column` with `align-items: end` for right-aligned text stacks
- **Project Cards**: `.elem` uses flexbox with `justify-content: space-between` for title/year layout; images are absolutely positioned

### Section Structure (`index.html`)

- `#hero` - Full viewport hero with nav, animated heading, freelance status, footer links
- `#second` - Project showcase with three `.elem` cards (Crawlipse, Self Hosted Analytics, Proxy Corner)
- `.about` - Profile image and bio with CTA button
- `.subscribe` - GitHub follow link
- `.footer` - Copyright and social links

## Development Notes

- No build process - static files served directly
- All dependencies loaded via CDN in `index.html`
- GSAP script is included twice in HTML (duplicate script tags at lines 119-130)
- The `timeout` variable in `circleChaptaKaro()` is used before declaration (relies on hoisting)
