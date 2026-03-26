# Frontend Clarity Iteration Plan

> **For agentic workers:** REQUIRED: Use superpowers:subagent-driven-development (if subagents available) or superpowers:executing-plans to implement this plan. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** 让用户打开线上链接和本地页面时，界面更清晰、变化可感知、使用路径更直接。

**Architecture:** 保持现有纯前端结构不重构框架，只做信息架构与可见性增强。通过欢迎引导区降低首屏空白感，通过 Service Worker 策略调整解决“改了看不见”的体验问题。

**Tech Stack:** HTML + CSS + JavaScript + Service Worker

---

## Chunk 1: 明确化流程（规划→评审→方向）

### Task 1: 定义迭代流程并固化

**Files:**
- Create: `docs/superpowers/plans/2026-03-26-frontend-clarity-iteration.md`

- [x] **Step 1: 记录迭代流程**
- [x] **Step 2: 输出阶段目标和验收口径**
- [x] **Step 3: 作为后续评审依据**

验收标准：流程文档存在且可直接执行。

## Chunk 2: 首屏清晰度改造

### Task 2: 增加首屏引导区，减少空白与迷惑

**Files:**
- Modify: `index.html`
- Modify: `css/main.css`
- Modify: `js/app-bundle.js`

- [ ] **Step 1: 添加欢迎引导区域（3步使用说明 + 功能状态）**
- [ ] **Step 2: 新增明显版本标识，便于用户判断是否更新**
- [ ] **Step 3: 解析成功后自动隐藏引导区，聚焦结果内容**

验收标准：未解析时页面不是大空白；用户一眼能看出怎么用。

## Chunk 3: 可见性与缓存策略修正

### Task 3: 解决“改了但线上看不到”的问题

**Files:**
- Modify: `sw.js`
- Modify: `index.html`

- [ ] **Step 1: 改为不拦截页面请求（或退役 SW）以避免陈旧缓存**
- [ ] **Step 2: 激活阶段清空旧缓存**
- [ ] **Step 3: 页面加载后主动触发 SW 更新检查**

验收标准：用户刷新后更容易看到最新页面。

## Chunk 4: 评审与验证

### Task 4: 快速验证与发布

**Files:**
- Modify: `js/app-bundle.js` (如需微调提示文案)

- [ ] **Step 1: 静态错误检查（HTML/CSS/JS）**
- [ ] **Step 2: 本地启动脚本可继续使用**
- [ ] **Step 3: 提交并推送，记录 commit**

验收标准：无新增错误，仓库可追踪本次迭代。
