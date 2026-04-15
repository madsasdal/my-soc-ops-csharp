# SocOps Arcade Redesign - Design Specification

## Vision
Transform SocOps into a vibrant, retro arcade/80s-90s pixel art bingo game with bold colors, pixelated aesthetics, playful animations, and arcade-style visual feedback.

## Design Principles
1. **Retro Arcade**: 80s-90s arcade cabinet aesthetic
2. **Bold Colors**: Vibrant, saturated color palette inspired by classic arcade games
3. **Pixel Art**: Pixelated fonts (Press Start 2P) and geometric styling
4. **Playful Animation**: Screen glitches, flashes, scoring effects, and satisfying micro-interactions
5. **Functional**: Maintain all game logic while making it visually striking

## Color Palette

### Primary Colors
- **Neon Cyan**: `#00FFFF` - Arcade border, highlights
- **Neon Magenta**: `#FF00FF` - Title, accents
- **Neon Yellow**: `#FFFF00` - Success, winning states
- **Electric Purple**: `#8B00FF` - Secondary accent
- **Hot Pink**: `#FF0080` - Button hover states

### Supporting Colors
- **Deep Purple**: `#1A0033` - Background, dark accents
- **Dark Teal**: `#001A33` - Secondary background
- **White**: `#FFFFFF` - Text, borders
- **Lime Green**: `#00FF00` - Marked/success feedback

### State Colors
- **Marked Square**: Neon Yellow bg, Neon Cyan border (winning), Electric Purple (normal marked)
- **Unmarked Square**: Dark Teal bg, White text, Neon Cyan border on hover
- **Free Space**: Deep Purple bg, Neon Magenta text, glowing effect
- **Winning Line**: Hot Pink glow, animated pulse

## Typography
- **Font Family**: "Press Start 2P" (pixelated/arcade style)
- **Fallback**: "Courier New", monospace
- **Sizes**: Intentionally bold hierarchy (large titles, medium text, small UI)

## Components

### StartScreen
- Background: Arcade cabinet entrance aesthetic (deep purple gradient with animated scanlines)
- Title: Large pixelated "SOC OPS" in neon magenta with glow effect
- Subtitle: Neon cyan "SOCIAL BINGO" with retro vibe
- Instructions Box: Dark teal border (neon cyan), white text on deep purple
- Button: Hot pink with neon cyan border, arcade-style hover state with glow

### GameScreen
- Header: Dark arcade header with neon borders
- Instructions: Neon cyan text on deep purple background
- Bingo Indicator: Flash animation when BINGO achieved
- Board Container: Neon cyan border with shadow/glow effect

### BingoBoard
- Border: Neon cyan with thick arcade-style shadow
- Grid Gap: Minimal (gives dense arcade feel)
- Background: Subtle scanline effect

### BingoSquare
- Unmarked: Dark teal bg, white text, neon cyan border
- Hover: Transforms with scale animation, brighter neon border
- Marked (Normal): Electric purple bg, white border, pulsing glow
- Marked (Winning): Neon yellow bg, hot pink border, intense glow with animation
- Transition: All state changes have smooth animations

### BingoModal
- Overlay: Semi-transparent black with scanline texture
- Content: Neon magenta border, deep purple background
- Animation: Arcade "power-up" effect - bounces in with screen flash effect
- Button: Hot pink with white border, intense glow on hover

## Animations

### Scanlines
- Subtle animated horizontal lines overlay (like old CRT monitors)
- Applied to backgrounds for atmosphere

### Screen Flash
- Quick white flash on BINGO achievement
- Gives arcade game screen hit feedback

### Glow Effects
- Neon text/border glows using CSS text-shadow and box-shadow
- Animated pulse on winning squares

### Hover States
- Scale up slightly (1.05x)
- Brighten neon color
- Add glow effect
- Slight rotation on button hover

### Marked Feedback
- Pop animation when square is clicked
- Pulsing glow for winning squares
- Smooth color transitions

## Implementation Status

### Phase 1: CSS Foundations
- [ ] Font imports and base styles
- [ ] Color system (CSS variables)
- [ ] New utility classes
- [ ] Scanline and glow animations

### Phase 2: Component Updates
- [ ] StartScreen redesign
- [ ] GameScreen header and layout
- [ ] BingoBoard styling and container

### Phase 3: Square & Interactions
- [ ] BingoSquare arcade styling
- [ ] Hover and marked state animations
- [ ] Winning line effects

### Phase 4: Modal & Celebration
- [ ] BingoModal arcade popup
- [ ] Flash and celebration animations
- [ ] Final visual polish

## Design Decisions & Notes
- Using CSS animations only (no JavaScript needed) for Blazor compatibility
- Neon colors chosen for strong contrast and arcade authenticity
- Pixel font provides visual character while maintaining readability
- Glow effects created with shadow layering (no expensive filters)
- All animations are performance-optimized for smooth gameplay
