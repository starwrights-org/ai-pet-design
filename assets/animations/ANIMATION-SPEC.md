# Pet动画规格说明

## 📋 动画清单

每种Pet需要以下动画：

### 1. 基础移动 🚶
- `walk-1/2/3/4.svg` - 走路循环（4帧）
- `run-1/2/3/4.svg` - 跑步循环（4帧）

### 2. 情绪表达 🎭
- `happy-1/2.svg` - 开心（眯眼+腮红）
- `sad-1/2.svg` - 难过（泪眼+垂耳/下垂特征）
- `surprise-1/2.svg` - 惊讶（大眼+感叹号）
- `angry-1/2.svg` - 生气（皱眉+愤怒符号）

### 3. 互动动作 🎮
- `eat-1/2/3.svg` - 吃东西（低头+张嘴）
- `sleep-1/2.svg` - 睡觉（蜷缩+ZZZ）
- `play-1/2/3.svg` - 玩耍（跳跃/翻滚）

## 📐 技术规格

- **尺寸**: 32×32像素
- **格式**: SVG (rect元素组成)
- **命名**: `{pet}-{action}-{frame}.svg`
- **帧率建议**: 8-12 FPS

## 🎨 已完成

### 猫型 (cat/) ✅
- walk-1/2/3/4.svg ✅
- happy-1.svg ✅
- sad-1.svg ✅
- sleep-1.svg ✅
- eat-1.svg ✅

### 狗型 (dog/)
- walk-1.svg ✅
- happy-1.svg ✅

### 其他Pet (待完成)
- bird/
- robot/
- energy/
- slime/
- spirit/

## 🔄 实现建议

Dev可以通过以下方式使用动画：

```javascript
// 精灵图或帧序列
const walkFrames = ['walk-1', 'walk-2', 'walk-3', 'walk-4'];
let currentFrame = 0;

function animate() {
  currentFrame = (currentFrame + 1) % walkFrames.length;
  pet.src = `${petType}/${walkFrames[currentFrame]}.svg`;
}

setInterval(animate, 100); // 10 FPS
```

## 📝 备注

- 所有动画保持统一的眼睛风格（1×2极简竖点）
- 配件系统兼容（配件层叠加在动画帧之上）
- 情绪动画可以循环或单次播放
