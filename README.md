# web-design

Web 视觉设计 Skill（Claude Code / Cursor / Codex 通用）。

输入 PRD / 参考 URL / 截图 / 关键词（任意组合），先产出一份标准化 `DESIGN.md` 设计规范，确认后据此生成 UI/UX、视觉、动效、响应式全部达标的 web 代码。专攻 Landing Page、Portfolio、产品页、博客、SaaS 介绍页等。

## 安装

装到 Claude Code 的 skills 目录：

```bash
git clone https://github.com/Ea12421/web-design ~/.claude/skills/web-design
```

## 用法

触发词：「帮我做个网站」「设计一个页面」「参考 XX 做一个」「做一个 landing page」。

工作流：**理解需求 → 输出 `DESIGN.md`（确认）→ 生成代码 → 审计**。详见 [`SKILL.md`](SKILL.md)。

## 可选：机械检测（detector）

审计阶段可选用 [impeccable](https://github.com/pbakaus/impeccable) 的检测器对产物做一次**确定性扫描**（不依赖 AI 自觉）：

```bash
npx -y impeccable detect --json --gpt <文件 / 目录 / URL>
```

抓 CSS/HTML 层的 AI 味（烂大街字体 / 紫色渐变 / 弹跳缓动 / 跳级标题等），与本仓 `references/anti-slop.md`（文案 / 中文空话 / 布局）互补。需要 Node.js，无则自动跳过。

## 来源与致谢

- 本仓库**基于 KAOPU-XiaoPu 的 web-design skill（MIT）**二次开发，原版权声明完整保留于 [`LICENSE`](LICENSE)。
- 本仓库新增：[`references/anti-slop.md`](references/anti-slop.md) 反 AI 味禁忌清单（提炼自 [taste-skill](https://github.com/Leonxlnx/taste-skill)，MIT），并接入 Phase C 审计。
- 动效效果目录参考 [vue-bits / reactbits](https://github.com/DavidHDev/vue-bits)（MIT, by DavidHDev）。
