# skills

[![skills.sh](https://skills.sh/b/qiulin/skills)](https://skills.sh/qiulin/skills)

Personal Agent Skills

## 思维方法论 Skills

| Skill | 原则 | 一句话说明 |
|---|---|---|
| [first-principles](skills/first-principles/) | 第一性原理 | 剥离惯例与假设，还原为事实约束，从约束重新推导方案 |
| [adversarial-review](skills/adversarial-review/) | 对抗式审查 | 交付前切换反方立场，找出最能推翻方案的一点并修复 |
| [ablation-test](skills/ablation-test/) | 消融实验 | 拿掉候选对象验证必要性：无影响则删，有影响则记录理由 |
| [occams-razor](skills/occams-razor/) | 奥卡姆剃刀 | 如无必要勿增实体：满足约束的方案里选实体最少的 |
| [confidence-check](skills/confidence-check/) | 列出不自信点 | 交付前标注置信度，明示最没把握的点及验证途径 |
| [independent-thinking](skills/independent-thinking/) | 保持独立思考 | 同意基于论证，反对给出证据与替代方案，不迎合 |
| [critical-thinking](skills/critical-thinking/) | 批判性思维 | 先质疑前提 → 再注明依据地推理 → 后分档交付结论 |
| [high-cohesion-low-coupling](skills/high-cohesion-low-coupling/) | 高内聚低耦合 | 按"一起变化的放一起"切分模块，依赖单向无环 |
| [rethink](skills/rethink/) | 深度复查 | 换视角找遗漏、下钻找深度不足，分诊出修正项与补充项 |
| [competitive-research](skills/competitive-research/) | 竞品调研 | 拆解竞品/相邻实现/先例尸检，产出比较矩阵与借鉴避坑清单 |
| [handoff-implement](skills/handoff-implement/) | 移交实现 | 自足 prompt 交新会话隔离实现，执行汇总后按冻结标准严格验收 |
| [design-only](skills/design-only/) | 纯设计 | 只产出实现者可直接开工的完整方案，零代码改动，可与移交实现串联 |
| [execution-summary](skills/execution-summary/) | 执行汇总 | 自足可复制的实现汇报：基线、证据、逐条自检、复验指引，交原会话严格验收 |
| [independent-design](skills/independent-design/) | 独立设计交叉验证 | 派互不可见的子代理盲设同一问题，收割收敛/分歧/独有点，综合单一方案 |
| [align-understanding](skills/align-understanding/) | 对齐理解 | 术语表+边界探测+实例走查+假设两栏标注，固化理解基线防偏差 |
| [subagent-sequential-implement](skills/subagent-sequential-implement/) | 依次派子代理实现 | 方案切有序阶段逐个派子代理，阶段验收门+还原点，失败只重做一段 |
| [design-doc](skills/design-doc/) | 方案落文档 | docs/design 目录规范 + 日期前缀命名 + 状态元数据 + 索引表，方案持久化留档 |

## 安装

### 通过 skills.sh（推荐）

任何支持 agent skills 的工具都可用 Vercel 的 skills CLI 安装（需要 Node 20.12+）：

```bash
npx skills add qiulin/skills                            # 交互式选择
npx skills add qiulin/skills --skill first-principles   # 只装一个
npx skills add qiulin/skills -g                         # 全局安装
```

### 手动链接/复制

`skills/<name>/SKILL.md` 为标准 skill（`SKILL.md` + frontmatter），复制或链接到 agent 的 skills 目录即可生效：

```powershell
# Windows (PowerShell)：链接单个 skill
New-Item -ItemType SymbolicLink -Path "$env:USERPROFILE\.agents\skills\first-principles" -Target "<仓库路径>\skills\first-principles"

# 或批量复制全部
Get-ChildItem .\skills -Directory | ForEach-Object { Copy-Item -Recurse $_.FullName "$env:USERPROFILE\.agents\skills\" }
```

```bash
# macOS / Linux
ln -s "$(pwd)/skills/first-principles" ~/.agents/skills/first-principles
```

skill 未设置 `disable-model-invocation`，因此会在场景匹配时被模型自动触发，也支持手动 `/skill-name` 调用。
