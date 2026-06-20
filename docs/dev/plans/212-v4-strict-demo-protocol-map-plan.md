# 212 · ResearchLoop V4 严格协议映射 Demo 优化计划

- 状态：approved（用户要求直接按本地 `01-更新之后的提示词指令` 优化 Demo）
- 日期：2026-06-20
- 目标：将 Demo 从“抽象双循环展示”升级为严格呈现 V4 源文件中的 010-040 方案层与 Loop2 同号交付链。

## 允许修改文件

- `index.html`
- `apps/index.html`
- `apps/researchloop.html`
- `README.md`
- `DESIGN.md`
- `assets/researchloop-demo-preview.png`
- `docs/dev/plans/212-v4-strict-demo-protocol-map-plan.md`
- `docs/retrospectives/2026-06-20-v4-strict-demo-protocol-map.md`

## Test Oracle

- `docs/v4/000/010/020` 与本地更新指令源哈希一致。
- Demo 必须出现 `010/012/015/020/030/035/040`。
- Demo 必须出现 `INSTRUCTION LOAD CHECK`、`WORKTREE CHECK`、`PLAN AUDIT`、`Test Oracle`、`G1/G2/G3`、`CC-R/CX-R/CC-V`。
- 页面无 mojibake、无本地绝对路径、无手机号/身份证/邮箱等个人信息。
- 浏览器本地打开无 JS 报错，点击/自动播放可更新节点状态。
