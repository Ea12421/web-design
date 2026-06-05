# Anti-Slop 反 AI 味禁忌清单

> 提炼自 [taste-skill](https://github.com/Leonxlnx/taste-skill)（MIT）的 forbidden patterns，
> **剔除了与本 skill「风格中立 / 参考驱动」原则冲突的条目**，并对中文场景做了适配。
>
> **何时用**：Phase B 写 DESIGN.md 的 Do's/Don'ts 时引用；Phase C 审计时逐条过。

## 使用原则

- 这些是**客观的「一眼 AI 做的」痕迹**，不是风格偏好——和具体审美无关，去掉只会更像「人做的」。
- 与 DESIGN.md 的调性（tone）冲突时，以调性优先；但默认全部遵守。
- 标 **[仅英文]** 的条目只在英文文案输出时生效，**中文页面忽略**。

---

## 1. 文案 / 命名（最高频，优先查）

### 人名 / 头像 / 品牌名
- [ ] 禁通用假人名：`John Doe` / `Jane Doe` / `Sarah Chan` / `Jack Su` → 用真实、地域贴合的名字
- [ ] 禁通用占位头像：SVG "egg"、Lucide `user` 图标 → 用真实头像或有设计感的字母头像
- [ ] 禁 startup 烂大街品牌名：`Acme` / `Nexus` / `SmartFlow` / `Cloudly` 这类

### 动词 / 形容词
- [ ] 禁空洞营销词：`Elevate` / `Seamless` / `Unleash` / `Next-Gen` / `Revolutionize` → 用具体动词
- [ ] 中文同类空话一并禁：赋能 / 一站式 / 无缝 / 颠覆 / 引领 / 重新定义 → 说人话、给具体动作

### 数字 / 步骤标签
- [ ] 禁一眼假的完美数字：`99.99%` / `50%` / `1234567` → 用可信的具体数
- [ ] 禁通用步骤标签：`Step 1/2/3`、`Stage 1/2/3`、`Phase 01/02/03` → 用有信息量的步骤名

### 标点
- [ ] **[仅英文]** 禁 em-dash（`—`）和作分隔符的 en-dash（`–`）出现在英文文案任何可见处（标题/正文/标签/署名）——这是英文 AI 文案的明显指纹。**中文页面破折号是正常标点，本条不生效。**

---

## 2. 装饰性噪音文字（零信息量的「高级感」摆设）

- [ ] 禁 hero 里的版本标签：`V0.6` / `v2.0` / `BETA` / `INVITE-ONLY PREVIEW`
- [ ] 禁 section 编号 eyebrow：`00 / INDEX`、`001 · Capabilities`、`002 · Featured`
- [ ] 禁图片上的分页标签：`01 / 4`
- [ ] 禁滚动提示：`Scroll` / `↓ scroll` / `Scroll to explore` / 动画鼠标滚轮图标
- [ ] 禁天气 / 地点 / 时间条：`LIS 14:23 · 18°C`（仅当 brief 明确是全球分布式团队时才允许）
- [ ] 禁营销页假版本 footer：`v1.4.2` / `Build 0048`
- [ ] 装饰性状态点：默认 0 个；元数据行里中点（`·`）每行最多 1 个

---

## 3. eyebrow / 小标签节制（机械可查）

- [ ] 每 3 个 section 最多 1 个 uppercase tracking 小标签；数一下，超 `ceil(section数 / 3)` 就删
- [ ] 禁竖排旋转文字作默认装饰
- [ ] 禁标题里右上角浮动小字
- [ ] 禁十字准星 / 发丝网格线当装饰

---

## 4. 布局 AI 味

- [ ] 禁 3 列等大 feature 卡片（三个一模一样的横排卡）→ 用不等大 / 主次分明 / Bento
- [ ] 禁 logo 墙塞进 hero；hero 只放价值主张 + 主 CTA，logo 墙单独放下一节
- [ ] 禁巨型导航吃掉 ~15% 视口；禁桌面端两行导航
- [ ] hero 大标题 4 行 = **字号错误**（不是文案太长）→ 调小字号让其 ≤ viewport，CTA 不滚动即可见
- [ ] 禁长列表 / 规格表每行都 `border-t` + `border-b` 的「发票脸」
- [ ] 禁 `Trusted by` / `Quietly trusted by` 这类社会证明标题硬塞

---

## 5. 图片 / 视觉资产

- [ ] 禁用 `<div>` 矩形拼假的产品界面冒充截图（尤其 hero 里的假产品 UI）
- [ ] 禁假截图里再嵌假版本 footer
- [ ] 禁图片上叠 pills / labels / tags
- [ ] 禁照片署名小字当装饰
- [ ] （呼应主 skill）图片禁纯色块占位

---

## 6. CTA / 表单

- [ ] CTA 按钮文字桌面端必须**单行**，换行 = 不合格
- [ ] 禁同一页多个**相同意图**的 CTA
- [ ] 禁用 placeholder 当 label

---

## 7. 动效 AI 味

- [ ] 禁到处都是的无限循环微动画（除非调性 / 动效档位明确要）
- [ ] marquee 横滚带每页最多 1 条
- [ ] （呼应主 skill 性能红线）禁裸 `window.addEventListener('scroll')` / 在 React state 里存 `scrollY` / 用 `requestAnimationFrame` 改 React state

---

## 8. 颜色（只摘客观项，不碰风格选择）

- [ ] 禁纯黑 `#000000` → 用 off-black / `zinc-950` / 炭黑
- [ ] 禁浅色背景上的纯黑投影 → 用带色调的柔和阴影
- [ ] 禁默认的霓虹 / 外发光 → 用内描边或淡色调阴影
- [ ] 「AI 紫 / 蓝光晕」不作默认（调性需要时可用）

---

## 本 skill 主动剔除的 taste-skill 条目（防止误用）

以下 taste-skill 有、但本 skill **不采纳**，因为与「风格中立 / 参考驱动」哲学冲突：

- ❌ **「衬线字体不推荐作默认 / 禁 Fraunces、Instrument Serif」**——本 skill 把衬线作为合法风格方向（见 `style-seeds.md`）
- ❌ **「暖色纸张色板（`#f5f1ea` 等）一律禁用」**——配色由参考站 / style-seeds 决定，不一刀切禁某些 hex
- ❌ **「禁居中 Hero」**——居中 hero 不是错，取决于设计意图
