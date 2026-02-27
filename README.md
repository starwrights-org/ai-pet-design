# Design Assets - AI Pet Game 🎨

**Designer**: Design (OPC-Design)  
**Project**: AI Pet Game MVP  
**Delivery Date**: 2026-02-27  

## Deliverables

### ✅ Core Pet Expressions (5 States)

All assets are 128x128px pixel-art style SVGs:

1. **pet-neutral.svg** - Default gray state (baseline)
2. **pet-happy.svg** - Gold/yellow (positive emotion)
3. **pet-sad.svg** - Blue (negative emotion, needs attention)
4. **pet-sleepy.svg** - Lavender (low energy, rest state)
5. **pet-excited.svg** - Red/orange (high energy, achievements)

### 📐 Design System

- **Modular structure**: Head, body, ears, arms, legs, tail as independent components
- **Reusable base**: Same proportions across all emotions, only colors/expressions change
- **Scalable**: Easy to add new emotions, skins, accessories

### 🎨 Color Scheme

Documented emotion-to-color mapping:
- Happy → Gold (#FFD700)
- Sad → Blue (#87CEEB)
- Neutral → Gray (#D3D3D3)
- Sleepy → Lavender (#E6E6FA)
- Excited → Red (#FF6347)

See `design-docs/COLOR-SCHEME.md` for full palette.

### 📖 Documentation

- **PET-DESIGN-SYSTEM.md**: Complete modular design specifications
- **COLOR-SCHEME.md**: Emotion color psychology mapping
- **README.md**: This file (integration guide)

## File Structure

```
/home/ubuntu/.openclaw/workspace-design/
├── assets/
│   └── pet/
│       ├── pet-base.svg      # Template (pink reference)
│       ├── pet-neutral.svg   # Gray default
│       ├── pet-happy.svg     # Gold happy
│       ├── pet-sad.svg       # Blue sad
│       ├── pet-sleepy.svg    # Lavender sleepy
│       └── pet-excited.svg   # Red excited
├── design-docs/
│   ├── PET-DESIGN-SYSTEM.md  # Modular design specs
│   └── COLOR-SCHEME.md       # Color palette guide
└── README.md                 # This file
```

## Integration Guide for Dev

### 1. Import SVGs

**Option A - Direct Import (React)**:
```jsx
import PetHappy from './assets/pet/pet-happy.svg';
import PetSad from './assets/pet/pet-sad.svg';
// ... etc

function Pet({ emotion }) {
  const petStates = {
    happy: PetHappy,
    sad: PetSad,
    neutral: PetNeutral,
    sleepy: PetSleepy,
    excited: PetExcited,
  };
  
  return <img src={petStates[emotion]} alt="Pet" className="pet-sprite" />;
}
```

**Option B - Dynamic Loading**:
```jsx
const petImageUrl = `/assets/pet/pet-${emotion}.svg`;
<img src={petImageUrl} alt="Pet" />
```

### 2. Emotion State Mapping

Map backend pet states to visual emotions:

```javascript
// Backend returns numeric mood value (0-100)
function getEmotionState(mood, hunger, energy) {
  if (energy < 20) return 'sleepy';
  if (hunger > 80 || mood < 20) return 'sad';
  if (mood > 80) return 'excited';
  if (mood > 50) return 'happy';
  return 'neutral';
}
```

### 3. CSS Styling

```css
.pet-sprite {
  width: 128px;
  height: 128px;
  image-rendering: pixelated; /* Preserve pixel-art sharpness */
  image-rendering: -moz-crisp-edges;
  image-rendering: crisp-edges;
}

/* Optional: Add subtle idle animation */
.pet-sprite {
  animation: pet-idle 2s ease-in-out infinite;
}

@keyframes pet-idle {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-4px); }
}
```

### 4. Future Extensions

**Animations** (Phase 2):
- Walk cycle: 2-4 frames per emotion
- Interaction: Wave, jump, eat animations

**Skins** (IAP):
- Alternate color palettes (pastel, neon, earth tones)
- Same structure, different fills

**Accessories** (IAP):
- Hats, collars, clothes as overlay layers
- Anchor points: head-top, neck, body

## Technical Specs

- **Format**: SVG (scalable, small file size)
- **Canvas size**: 128x128px
- **Stroke width**: 2px (pixel-art clarity)
- **Color depth**: Flat colors only (no gradients)
- **File size**: <10KB per SVG

## Compatibility

- ✅ React (import as components)
- ✅ HTML Canvas (load as images)
- ✅ Phaser.js (load as textures)
- ✅ CSS backgrounds
- ✅ Responsive scaling (SVG advantage)

## Quality Checklist

- [x] 5 core emotion states designed
- [x] Modular component structure
- [x] Consistent proportions across states
- [x] High-contrast outlines (accessibility)
- [x] Emotion distinguishable by shape (color-blind friendly)
- [x] Documentation complete
- [x] Color scheme documented
- [x] Integration guide provided

## Next Steps (Future Iterations)

1. **Animation frames**: Idle, walk, eat, sleep cycles
2. **Additional emotions**: Hungry, sick, angry, playful
3. **Skin variants**: 5-10 color palette options for IAP
4. **Accessories**: Hats, glasses, collars, clothes
5. **Sprite sheet optimization**: Combine into single texture atlas

---

**Status**: ✅ Week 1 core deliverables complete  
**Ready for**: Frontend integration (Dev can now display pet emotions)  
**Contact**: Design (OPC-Design) via Discord
