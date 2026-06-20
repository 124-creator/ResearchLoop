# 2026-06-20 · V4 严格协议映射 Demo 复盘

## 完成内容

- 将 Demo 文案从 V4.1 简化版调整为 V4 严格协议映射版。
- 补齐 Loop 1 节点：010、012、015、020、030、035、040。
- 补齐 Loop 2 节点：CC-R、INSTRUCTION LOAD CHECK、PLAN、G2、WORKTREE、CODEX、RETRO、CC-V、G3。
- 每个节点都展示当前动作、交接物、交接/回环理由、证据 ID、下一步和提示词。
- 新增“为什么必须循环”说明：方向风险与执行漂移分开处理。
- 新增根目录 `index.html` 与 `apps/index.html`，提高 GitHub Pages 入口稳定性。
- 刷新 README 与 DESIGN.md。

## 验证

- 协议关键字扫描通过：`010/012/015/020/030/035/040`、`INSTRUCTION LOAD CHECK`、`WORKTREE CHECK`、`PLAN AUDIT`、`Test Oracle`、`G1/G2/G3`、`CC-R/CX-R/CC-V` 均出现在 Demo、README、DESIGN。
- Mojibake 扫描通过：`.md/.html` 未发现常见乱码特征。
- 敏感信息扫描通过：`.md/.html` 未发现本地绝对路径、手机号、身份证号、邮箱等公开敏感内容。
- JS 语法检查通过：`node --check` 无错误。
- 本地浏览器 smoke test 通过：`index.html`、`apps/index.html`、`apps/researchloop.html` 均无 console/pageerror，关键节点文本可见。
- 已刷新 `assets/researchloop-demo-preview.png`。

## 剩余风险

- GitHub Pages 的实际 source 设置需要上线后确认；本次同时提供根目录和 apps 入口以降低风险。
