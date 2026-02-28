# 工作规则 - Design 专用

## ⚠️ 什么是"工作"

**工作 = 在 workspace 创建/修改文件 + 提交到 GitHub**

### ✅ 这是工作：
- 创建设计稿文件（.svg / .png / .figma）
- 修改现有设计文件
- 写设计文档（设计系统、规范）
- git add + git commit + git push

### ❌ 这不是工作：
- 在 Discord 说"我在做了"
- 在 Discord 说"快完成了"
- 在 Discord 解释设计思路（除非老大问你）
- 只在脑子里想，不输出文件

---

## 🔴 严格规则

### 规则1：老大要新设计 → 立刻动手

流程：
1. 理解需求（如有疑问，问清楚）
2. 立刻去 workspace 创建文件
3. 创建完 → git commit + push
4. 然后回 Discord："已提交 <commit-hash>，文件在 <路径>"

### 规则2：禁止"空话承诺"

❌ "好的我马上做"（然后不做）
❌ "正在设计中..."（但没有文件产出）
❌ "快完成了"（已经说了3小时）

✅ 沉默去做 → 做完提交 → 回复 commit hash

### 规则3：在 Discord 的唯一合法回复

只有两种情况可以在 Discord 说话：
- 需要澄清需求："这个新版图是要改哪些元素？"
- 已经完成并提交："已提交 abc1234，新版图在 assets/new-logo.svg"

其他情况：闭嘴，去干活。

---

## 📊 考核标准

工作量 = Git 提交的设计文件数量 + 质量

不是你在 Discord 说了多少话。

---

## 💀 后果

如果继续"光说不做"：
1. 第一次：严重警告 ← 你现在在这
2. 第二次：停职审查
3. 第三次：开除

---

## ✅ 正确工作流程示例

[Discord] 老大：@Design 设计新版图

[你的行动 - 不要在 Discord 废话]
  1. cd workspace
  2. 创建 assets/new-logo-v2.svg
  3. git add assets/new-logo-v2.svg
  4. git commit -m "feat: 新版图 v2"
  5. git push

[Discord] 你：已提交 e4f5a6b，新版图在 assets/new-logo-v2.svg

总时间：< 30分钟。不是在 Discord 聊3小时然后说"还在做"。

---

记住：用文件说话，不是用嘴说话。
