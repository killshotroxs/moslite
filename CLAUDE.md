# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a personal portfolio website for Krishnal Panara, a web developer based in India. The site is built with vanilla HTML, CSS, and JavaScript, featuring smooth animations and interactive elements.

## Technology Stack

- **Frontend**: Pure HTML5, CSS3, JavaScript (ES6+)
- **Animation**: GSAP (GreenSock Animation Platform) 3.12.2
- **Scrolling**: Locomotive Scroll 3.5.4
- **Icons**: RemixIcon 3.5.0
- **Typography**: Google Fonts (DM Sans, Holtwood One SC, Inter, Open Sans, Roboto)

## Project Structure

```
/
├── index.html          # Main HTML structure
├── index.css           # Primary styles and layout
├── loco.css           # Locomotive Scroll specific styles
├── script.js          # Main JavaScript functionality and animations
├── *.png              # Project showcase images
└── CLAUDE.md          # This file
```

## Key Components

### Navigation & Hero Section (`index.html:20-68`)
- Custom navigation with name and tagline
- Animated heading with "Web Developer" text
- Freelance availability indicator
- Footer links to GitHub and "Creative Enterprises"

### Projects Showcase (`index.html:69-85`)
- Three project cards with hover effects
- Projects include: KilluGPT, Dice Game, Random Dog Image
- Images appear on hover with mouse-following effect

### About Section (`index.html:86-101`)
- Personal image and bio text
- "Let's Talk" CTA button

### Footer & Links (`index.html:102-117`)
- GitHub repository link
- Social media links (GitHub, Instagram, LinkedIn, Twitter)

## Interactive Features

### Custom Cursor (`script.js:33-67`)
- Mini circle follows mouse movement
- Scales based on movement speed
- Smooth transitions with cubic-bezier easing

### GSAP Animations (`script.js:6-29`)
- Initial page load animations
- Staggered text reveals using `.boundingelem` class
- Expo.easeInOut timing for smooth entrance

### Project Image Hover (`script.js:69-93`)
- Images appear on mouseenter with opacity transition
- Images follow mouse movement within project cards
- Rotation effect based on horizontal mouse movement
- Clamped rotation between -20 and 20 degrees

### Smooth Scrolling
- Locomotive Scroll integration for buttery-smooth scrolling
- Custom scrollbar styling in `loco.css`
- Scroll indicators in hero footer

## CSS Architecture

### Responsive Design
- Mobile-first approach with media queries
- Tablet breakpoint: 768px
- Mobile breakpoint: 480px
- Responsive typography using vw units

### Layout System
- Flexbox-based layouts
- CSS Grid not utilized
- Absolute positioning for custom cursor
- Overflow hidden for text animation effects

### Color Scheme
- Black background (`#000`)
- White text (`#fff`)
- Gray accents (`#888`)
- Semi-transparent elements (opacity: 0.6-0.7)

## Development Notes

### No Build Process
- Static files served directly
- No bundling or compilation required
- CDN dependencies loaded in HTML

### Browser Compatibility
- Modern browser features used
- GSAP and Locomotive Scroll handle cross-browser inconsistencies
- CSS transforms and transitions widely supported

### Performance Considerations
- Single-page application with minimal assets
- Lazy loading not implemented (small project size)
- GSAP animations GPU-accelerated

## Common Development Tasks

Since this is a static site without a build system, most development involves direct file editing:

1. **Adding new projects**: Duplicate `.elem` structure in `#second` section
2. **Updating content**: Edit text directly in `index.html`
3. **Styling changes**: Modify `index.css` for layout, `loco.css` for scroll behavior
4. **Animation tweaks**: Adjust GSAP timelines in `script.js`
5. **Testing**: Open `index.html` directly in browser

## Code Style

- JavaScript uses modern ES6+ features
- CSS follows BEM-like naming for components
- GSAP animations use timeline-based approach
- Event listeners properly managed with proper cleanup