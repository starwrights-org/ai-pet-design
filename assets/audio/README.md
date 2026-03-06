# 🔊 Mote叫声音效指南

## 需要的音效（7个）

| Mote | 文件名 | 效果 | sfxr.me预设 |
|------|--------|------|-------------|
| Cat | cat-meow.mp3 | 喵~ | Pickup → 调低频率 |
| Dog | dog-woof.mp3 | 汪~ | Explosion → 短时长 |
| Bird | bird-chirp.mp3 | 啾~ | Jump → 高频率 |
| Robot | robot-beep.mp3 | 哔哔~ | Powerup → 方波 |
| Energy | energy-hum.mp3 | 嗡~ | Laser → 持续音 |
| Slime | slime-gloop.mp3 | 咕咕~ | Blip → 湿润效果 |
| Spirit | spirit-chime.mp3 | 叮~ | Pickup → 高频+延音 |

## 生成方法（sfxr.me）

1. 打开 https://sfxr.me/
2. 点击左侧预设按钮生成基础音效
3. 调整参数（频率、时长等）
4. 点击"Export WAV"下载
5. 转换为MP3（可选）

### 参数调整建议

**Cat喵叫**：
- 预设：Pickup
- Frequency: 0.3-0.4
- Slide: -0.1（下滑）
- Sustain: 0.2
- Decay: 0.3

**Dog汪叫**：
- 预设：Explosion
- Frequency: 0.2-0.3
- Sustain: 0.1
- Decay: 0.2

**Bird啾叫**：
- 预设：Jump
- Frequency: 0.6-0.7
- Slide: 0.1（上滑）
- Sustain: 0.1
- Decay: 0.1

**Robot哔哔**：
- 预设：Powerup
- Wave type: Square
- Frequency: 0.4-0.5
- Sustain: 0.15
- Decay: 0.1

**Energy嗡鸣**：
- 预设：Laser
- Wave type: Sine
- Frequency: 0.3
- Sustain: 0.3
- Vibrato: 0.3

**Slime咕咕**：
- 预设：Blip
- Frequency: 0.2
- Slide: 0.2（上滑）
- Sustain: 0.2
- Decay: 0.3

**Spirit叮声**：
- 预设：Pickup
- Frequency: 0.7-0.8
- Sustain: 0.1
- Decay: 0.4（长延音）

## 文件规格

- 格式：MP3或WAV
- 时长：0.5-2秒
- 放置：`assets/sounds/pets/`

## 集成

Dev使用 `playSound('cat-meow')` 等调用。
