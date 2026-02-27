# AI Pet - Modular Design System

## Overview

Pixel-art pet design with modular components for easy emotion/state changes and future customization (skins, accessories).

## Core Design Philosophy

1. **Modular**: Each body part (head, body, ears, tail, eyes, mouth) is independent
2. **Reusable**: Same base structure across all emotion states
3. **Scalable**: Easy to add new emotions, skins, accessories
4. **Performance-friendly**: Simple shapes = small file sizes, fast rendering

## Specifications

### Canvas Size
- **Standard**: 128x128px
- **Export formats**: SVG (source), PNG (runtime)
- **Coordinate system**: Top-left origin (0,0)

### Base Structure

#### Body (Rectangle)
- Position: `x=32, y=48`
- Size: `64x48px`
- Fill: Emotion-based color
- Stroke: `#000`, 2px

#### Head (Rectangle)
- Position: `x=40, y=24`
- Size: `48x32px`
- Fill: Emotion-based color
- Stroke: `#000`, 2px

#### Ears (2x Rectangle)
- Left: `x=32, y=16`, size `16x16px`
- Right: `x=80, y=16`, size `16x16px`
- Transform: Rotate/position varies by emotion

#### Arms (2x Rectangle)
- Left: `x=16, y=56`, size `16x24px`
- Right: `x=96, y=56`, size `16x24px`
- Transform: Rotation for gestures

#### Legs (2x Rectangle)
- Left: `x=40, y=96`, size `16x24px`
- Right: `x=72, y=96`, size `16x24px`

#### Tail (Path/Curve)
- Base: `x=96, y=64`
- Shape: Quadratic Bézier curve
- Varies by emotion (up/down/wagging)

## Emotion States

### 1. Neutral (Default)
- **Eyes**: Small circles (o o)
- **Mouth**: Straight line
- **Ears**: Upright
- **Tail**: Mid position
- **Color**: Gray (`#D3D3D3`)

### 2. Happy
- **Eyes**: Upward curves (^_^)
- **Mouth**: Smile curve
- **Ears**: Perked up
- **Tail**: Wagging up
- **Color**: Gold (`#FFD700`)
- **Effects**: White sparkles

### 3. Sad
- **Eyes**: Normal + tears (blue rectangles below)
- **Mouth**: Frown curve
- **Ears**: Drooped (rotated)
- **Tail**: Drooped down
- **Color**: Blue (`#87CEEB`)

### 4. Sleepy
- **Eyes**: Closed lines (- -)
- **Mouth**: None
- **Ears**: Relaxed (ellipse)
- **Body**: Lying down (ellipse)
- **Tail**: Curled
- **Color**: Lavender (`#E6E6FA`)
- **Effects**: "Zzz" text

### 5. Excited
- **Eyes**: Sparkling (*_*) with star shapes
- **Mouth**: Big smile
- **Ears**: Very perked
- **Arms**: Raised (rotated)
- **Tail**: Very wagging
- **Color**: Red (`#FF6347`)
- **Effects**: Gold energy particles

## Modular Components

### Eyes System
- **Base position**: Head center, `y=38`
- **Left eye**: `x=52`
- **Right eye**: `x=76`
- **Variants**:
  - Neutral: Circle, r=4
  - Happy: Path curve
  - Sad: Circle + tear rectangle
  - Sleepy: Line
  - Excited: Circle + star

### Mouth System
- **Base position**: Head bottom, `y=48`
- **Variants**:
  - Neutral: Straight line
  - Happy: Upward curve
  - Sad: Downward curve
  - Sleepy: None
  - Excited: Wide upward curve

### Tail System
- **Attachment**: Body right side, `x=96, y=64`
- **Variants**:
  - Neutral: Mid curve
  - Happy: Up curve
  - Sad: Down curve
  - Sleepy: Curled
  - Excited: Vigorous up curve

## Animation Considerations (Future)

### Idle Animation
- Slight bounce (2-4px vertical oscillation)
- Tail gentle sway
- Blink every 3-5 seconds

### Walk Animation
- Legs alternate position
- Body slight horizontal shift
- Tail follows body movement

### Interaction Animation
- Arms wave/raise
- Head tilt
- Eyes enlarge briefly

## File Structure

```
assets/
  pet/
    pet-base.svg         # Template (neutral pink)
    pet-neutral.svg      # Gray default state
    pet-happy.svg        # Gold happy state
    pet-sad.svg          # Blue sad state
    pet-sleepy.svg       # Lavender sleepy state
    pet-excited.svg      # Red excited state
    
    [Future]
    pet-hungry.svg
    pet-sick.svg
    pet-angry.svg
    
    skins/               # IAP skin variants
    accessories/         # IAP add-ons (hats, collars, etc.)
```

## Developer Integration Notes

### For Frontend (React)
```jsx
// Import SVG as component
import PetHappy from './assets/pet/pet-happy.svg';

// Or dynamic loading
const petStates = {
  happy: '/assets/pet/pet-happy.svg',
  sad: '/assets/pet/pet-sad.svg',
  // ...
};

<img src={petStates[currentEmotion]} alt="Pet" />
```

### For Sprite Sheets (Future Optimization)
- Combine all emotions into single PNG sprite sheet
- Use CSS background-position for state switching
- Reduces HTTP requests

### For Animation (Canvas/Phaser)
- Load SVGs as textures
- Apply transforms for idle/walk animations
- Layer accessories on top of base pet

## Extensibility

### Adding New Emotions
1. Copy `pet-base.svg`
2. Modify eyes, mouth, tail, color
3. Add to emotion color scheme
4. Update frontend state mapping

### Adding Skins (IAP)
1. Change primary/secondary colors
2. Keep same structure/proportions
3. Optional: Add patterns (stripes, spots)
4. Export as separate file

### Adding Accessories (IAP)
1. Design as separate SVG layer
2. Position anchors: head-top (hats), neck (collars), body (clothes)
3. Ensure compatibility with all emotion states

## Technical Constraints

- **Max file size per SVG**: <10KB
- **Stroke width**: Always 2px (pixel-art clarity)
- **No gradients**: Flat colors only (pixel-art aesthetic)
- **No filters/effects**: Keep it simple for performance

---

**Status**: ✅ Core 5 emotion states complete  
**Next steps**: Animation frames, skin variants, accessory system
