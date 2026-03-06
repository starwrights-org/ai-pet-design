# TOOLS.md - Local Notes

Skills define _how_ tools work. This file is for _your_ specifics — the stuff that's unique to your setup.

## GitHub Credentials

**Token 位置（共享）：**
```
/home/ubuntu/.openclaw/workspace/.credentials/github.txt
```

**使用方式：**
```bash
# 读取 token
TOKEN=$(cat /home/ubuntu/.openclaw/workspace/.credentials/github.txt | tail -1)

# Git 配置（临时）
git config --global credential.helper store
echo "https://${TOKEN}@github.com" > ~/.git-credentials

# 或者直接在 URL 中使用
git clone https://${TOKEN}@github.com/kuro-opc/repo-name.git
git push https://${TOKEN}@github.com/kuro-opc/repo-name.git
```

**适用场景：**
- 提交设计稿（Figma 导出、PNG/SVG 等）
- 更新设计文档（README、DESIGN.md）
- 版本管理设计资产

**⚠️ 安全提示：**
- Token 在所有 agent 间共享
- 不要在日志、聊天记录中暴露完整 token
- 提交时确认 .gitignore 已排除敏感文件

---

## What Goes Here

Things like:

- Camera names and locations
- SSH hosts and aliases
- Preferred voices for TTS
- Speaker/room names
- Device nicknames
- Anything environment-specific

## Examples

```markdown
### Cameras

- living-room → Main area, 180° wide angle
- front-door → Entrance, motion-triggered

### SSH

- home-server → 192.168.1.100, user: admin

### TTS

- Preferred voice: "Nova" (warm, slightly British)
- Default speaker: Kitchen HomePod
```

## Why Separate?

Skills are shared. Your setup is yours. Keeping them apart means you can update skills without losing your notes, and share skills without leaking your infrastructure.

---

Add whatever helps you do your job. This is your cheat sheet.

## 🌐 浏览器能力（2026-03-06 新增）

详见 `BROWSER-CAPABILITY.md`

**快速参考**：
```bash
openclaw browser open <url>      # 打开网页
openclaw browser screenshot      # 截图
openclaw browser snapshot        # 获取 AI 格式快照
```
