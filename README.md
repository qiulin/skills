# skills

Personal Agent Skills

## 思维方法论 Skills

| Skill | 原则 | 一句话说明 |
|---|---|---|
| [first-principles](first-principles/) | 第一性原理 | 剥离惯例与假设，还原为事实约束，从约束重新推导方案 |
| [adversarial-review](adversarial-review/) | 对抗式审查 | 交付前切换反方立场，找出最能推翻方案的一点并修复 |
| [ablation-test](ablation-test/) | 消融实验 | 拿掉候选对象验证必要性：无影响则删，有影响则记录理由 |
| [occams-razor](occams-razor/) | 奥卡姆剃刀 | 如无必要勿增实体：满足约束的方案里选实体最少的 |
| [confidence-check](confidence-check/) | 列出不自信点 | 交付前标注置信度，明示最没把握的点及验证途径 |
| [independent-thinking](independent-thinking/) | 保持独立思考 | 同意基于论证，反对给出证据与替代方案，不迎合 |
| [critical-thinking](critical-thinking/) | 批判性思维 | 先质疑前提 → 再注明依据地推理 → 后分档交付结论 |
| [high-cohesion-low-coupling](high-cohesion-low-coupling/) | 高内聚低耦合 | 按"一起变化的放一起"切分模块，依赖单向无环 |

## 安装

每个子目录是一个标准 skill（`SKILL.md` + frontmatter）。复制或链接到 agent 的 skills 目录即可生效：

```powershell
# Windows (PowerShell)：链接单个 skill
New-Item -ItemType SymbolicLink -Path "$env:USERPROFILE\.agents\skills\first-principles" -Target "<仓库路径>\first-principles"

# 或批量复制全部
Get-ChildItem . -Directory | ForEach-Object { Copy-Item -Recurse $_.FullName "$env:USERPROFILE\.agents\skills\" }
```

```bash
# macOS / Linux
ln -s "$(pwd)/first-principles" ~/.agents/skills/first-principles
```

skill 未设置 `disable-model-invocation`，因此会在场景匹配时被模型自动触发，也支持手动 `/skill-name` 调用（如 `/first-principles`）。
