# AI Pet - Color Scheme

## Core Emotion Colors

### 1. Happy - Gold/Yellow
- **Primary**: `#FFD700` (Gold)
- **Secondary**: `#FFA500` (Orange)
- **Accent**: `#FFF` (White sparkles)
- **Usage**: Positive emotions, rewards, achievements

### 2. Sad - Blue
- **Primary**: `#87CEEB` (Sky Blue)
- **Secondary**: `#4682B4` (Steel Blue - tears)
- **Accent**: `#B0C4DE` (Light Steel Blue)
- **Usage**: Low mood, neglect states, needs attention

### 3. Neutral - Gray
- **Primary**: `#D3D3D3` (Light Gray)
- **Secondary**: `#A9A9A9` (Dark Gray)
- **Accent**: `#000` (Black)
- **Usage**: Default state, idle, thinking

### 4. Sleepy - Lavender
- **Primary**: `#E6E6FA` (Lavender)
- **Secondary**: `#9370DB` (Medium Purple)
- **Accent**: `#DDA0DD` (Plum)
- **Usage**: Rest state, nighttime, low energy

### 5. Excited - Red/Orange
- **Primary**: `#FF6347` (Tomato Red)
- **Secondary**: `#FFD700` (Gold - energy particles)
- **Accent**: `#FF4500` (Orange Red)
- **Usage**: High energy, play mode, level up

### 6. Base (Template) - Pink
- **Primary**: `#FFB6C1` (Light Pink)
- **Usage**: Base template, modular design reference

## Universal Elements

### Outlines
- **Color**: `#000` (Black)
- **Width**: `2px`
- **Purpose**: Sharp pixel-art definition

### Highlights
- **Color**: `#FFF` (White)
- **Usage**: Eyes, sparkles, shine effects

### Shadows
- **Color**: `#696969` (Dim Gray)
- **Usage**: Optional depth effects (use sparingly)

## Color Psychology Mapping

| Emotion | Color | Energy Level | User Action Trigger |
|---------|-------|--------------|---------------------|
| Happy | Gold | High | After feeding, playing, praise |
| Sad | Blue | Low | Neglect, hunger, boredom |
| Neutral | Gray | Medium | Default, idle |
| Sleepy | Lavender | Very Low | Nighttime, no interaction |
| Excited | Red | Very High | New toy, level up, achievement |

## Modular System

Each emotion uses:
1. **Body fill** = Primary color
2. **Ears/Tail** = Same primary (consistency)
3. **Accents** = Secondary/Accent colors
4. **Outlines** = Always black (`#000`, 2px)

## Skins/IAP Variants (Future)

Alternate color palettes for monetization:
- **Pastel Set**: Soft pinks, blues, purples
- **Neon Set**: Bright cyan, magenta, lime
- **Earth Tones**: Brown, green, beige
- **Monochrome**: Black/white/gray shades
- **Rainbow**: Dynamic multi-color gradient

## Accessibility Notes

- High contrast (black outlines + bright fills)
- Color-blind friendly: emotions distinguishable by shape changes (ears, tail, eyes)
- Clear visual hierarchy: body > head > features

---

**Format**: All colors in HEX for easy CSS/JS integration  
**Tool compatibility**: Works with SVG, CSS, canvas, sprite sheets
