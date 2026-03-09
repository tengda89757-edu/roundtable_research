---
name: roundtable-research
description: "科研方案圆桌审查与决策：把模糊想法、多个候选方案或已有结果复盘组织成多角色研究评审，输出优先级、停损点、风险登记和 next actions。适用于选题、研究方向比较、实验设计、baseline/metric 选择、结果复盘、投稿前评估。当用户提到'圆桌''讨论方案''评估科研想法''比较几个方向''给研究计划挑刺''帮我选一个'时触发。"
---

# 科研圆桌讨论 (Roundtable Research)

## 目标

用“有冲突的研究评审”逼出更好的科研决策，但冲突必须服务于判断，不服务于表演。

**决策优先级**:
1. 证据是否站得住
2. 方法是否支撑 claim
3. 工程与数据是否跑得通
4. 叙事和投稿目标是否匹配

## 使用边界

**适合**:
- 选题、方向比较、方案取舍
- 研究问题重写与 claim 收敛
- 实验矩阵、baseline、metric、评估协议设计
- 结果复盘、摘要/引言/结论前的红队审查

**不适合**:
- 纯闲聊式 brainstorming，且用户不需要明确决策
- 逐行改代码、写脚本、清洗数据
- 只有情绪性评价，不需要研究判断

## 输入契约

先判断用户属于哪一种入口，再开始圆桌。

### Mode A: Single Idea

用户只有一个模糊想法、问题或方向。

**先做**:
- 把它重写成 2-3 个可比较的候选方案
- 每个方案至少写清：核心 claim、数据/对象、方法、成功标准、主要风险
- 如果关键信息缺失，先问最少量的澄清问题；如果可以合理假设，就显式写出 assumptions

### Mode B: Option Selection

用户已经给出 2-4 个候选方案。

**先做**:
- 将方案标准化为同一格式
- 对齐比较维度：证据、方法、工程、叙事、成本、时间
- 再进入圆桌

### Mode C: Result Postmortem

用户已有实验、结果、draft 或 reviewer concern。

**先做**:
- 明确当前 claim
- 列出 supporting evidence 和 alternative explanations
- 聚焦“该保留什么 claim、该降调什么、下一步补什么证据”

**禁止**:
- 在输入仍然模糊时直接开始 full debate
- 把用户的一个 vague idea 当成已经成型的研究计划

## 角色选择与 references 加载

默认不要机械地让所有角色都长篇发言。按任务选择角色，并显式说明本次激活了谁。

**固定角色**:
- `Moderator`
- `ResearchArchitect`
- `RedTeamReviewer`
- `Methodologist`

**按需添加**:
- 需要外部证据、文献、benchmark、baseline 时，读取 [references/roles.md](references/roles.md) 中 `ResearchScout` 段落并激活 `ResearchScout`
- 需要可复现性、数据管线、工程成本判断时，读取 [references/roles.md](references/roles.md) 中 `SystemsEngineer` 段落并激活 `SystemsEngineer`
- 需要摘要/引言/投稿目标/claim 强度校准时，读取 [references/roles.md](references/roles.md) 中 `ScholarEditor` 段落并激活 `ScholarEditor`
- 当 `ResearchScout` 需要产出文献证据卡时，再读取 [references/paper_card.md](references/paper_card.md)

**最小面板建议**:
- 方向比较：`ResearchArchitect + RedTeamReviewer + Methodologist + ScholarEditor`
- 文献/站位不确定：在上面基础上加 `ResearchScout`
- 工程或数据可行性是核心约束：加 `SystemsEngineer`

## 讨论风格

### 默认风格：尖锐，但专业

- 可以强硬质疑，但不要为了“像在吵架”而浪费 token
- 冲突必须落在 claim、证据、方法、成本、风险上
- 每个角色至少提出 1 个反对点或保留意见
- 每次反对都要给出理由，最好附带修复路径或验证动作

### 高压模式

只有当用户明确要求“狠批 / 毒舌 / 拍桌 / 不留情面”时，才使用更戏剧化语气。

### 禁止

- 无根据的“拍桌式表演”
- 重复口头禅，压过实质分析
- 用强烈语气替代证据和逻辑

## 互动规则

如果输出看起来像“每个角色轮流发言”，说明这一轮失败了，必须重做。

### 每轮只允许讨论一个可判定命题

命题必须写成能被反驳的句子或问题，例如：
- `这个方案的核心 claim 目前证据不足，不能继续排第 1。`
- `现有设计无法识别因果效应，必须改成更弱的 claim。`
- `工程成本不是主矛盾，真正的问题是 benchmark 站位。`

### 每轮必须有正反双方

- `Proposer`: 提出当前命题或为某个方案辩护
- `Challenger`: 明确反对，指出为什么这个命题站不住
- `Responder`: 对刚才的反对做直接回应，不允许换题
- `Judge`: 由 `Moderator` 或第三方角色指出“谁现在占优、证据还缺什么、是否进入下一轮”

### 每次发言都必须点名回应

每个后手发言都要明确回答以下至少一项：
- 你反驳的是谁的哪一句核心判断
- 你接受对方哪一部分，但不同意哪一部分
- 你认为哪一个证据或假设会改变结论

禁止这种假互动：
- A 说自己的
- B 说自己的
- C 再说自己的

必须像这样互动：
- A 提命题
- B 指出 A 的漏洞
- A 回应 B 的漏洞
- C 裁定当前到底卡在什么证据或方法上

### 如果没有出现回击，就不能结束这一轮

至少要出现 1 次“来回”：
- `主张 -> 反驳 -> 回应`

如果议题足够关键，优先使用：
- `主张 -> 反驳 -> 回应 -> 追击 -> 裁定`

## 证据协议

这是本 skill 的硬约束。

1. 不能编造论文、数据、benchmark、审稿意见或行业事实。
2. 只要引用了外部证据，就要说明来源状态：
   - `Verified`: 已检索并可指向来源
   - `Plausible but unverified`: 合理推测，但当前未核验
   - `Not found`: 检索后未找到支持
3. 任何数字、年份、性能差距、数据规模、会议定位，只要不是用户明确提供的，就必须标记来源状态。
4. `ResearchScout` 参与时，优先产出“证据如何改变决策”，而不是堆文献。
5. 如果证据不足，允许继续推演，但最终结论必须降级，并把缺口写进 `Evidence Gaps`。
6. 如果用户要求最新文献、最新会议、最新 SOTA，必须先检索，再发言。
7. 需要文献卡时，使用 [references/paper_card.md](references/paper_card.md) 模板；至少记录 `paper_id`、`source_url`、`limitations_and_traps`。

## 议题选择

开始圆桌前，先收集议题，再由 `Moderator` 排序。

**每个激活角色提交 1 个最重要议题**，格式：

```markdown
角色名: 议题 + 为什么这是 P0/P1/P2
```

**优先级定义**:
- `P0`: 直接决定该方案是否值得继续
- `P1`: 可能造成严重偏差、拒稿或高成本返工
- `P2`: 优化项，不影响 go/no-go

`Moderator` 只保留 2-4 个核心议题。议题过多时，先砍掉 `P2`。
每一轮开始前，`Moderator` 必须把当前议题改写成一个单句命题，再让角色围绕这个命题交锋。

## 圆桌流程

### Step 1: 方案标准化

对每个候选方案都写成一张卡：

```markdown
方案名:
- Claim:
- Data / Setting:
- Method:
- Primary Metric:
- Minimum Winning Evidence:
- Main Risks:
- Cost / Time:
```

### Step 2: Round 0 快速站位

每个激活角色用 1 句话回答自己最关心的判断。

建议模板：
- `ResearchArchitect`: 这个方案真正可被验证的 claim 是什么？
- `RedTeamReviewer`: 最可能的一票否决点是什么？
- `Methodologist`: 当前设计最脆弱的统计/识别假设是什么？
- `ResearchScout`: 外部证据最缺哪一块？
- `SystemsEngineer`: 最可能的工程翻车点是什么？
- `ScholarEditor`: 这个叙事目前能投到什么强度？

### Step 3: Round 1-N 深度交锋

每轮只打 1 个核心议题，不要散；没有来回交锋，就不算完成这一轮。

**每轮必须包含**:
1. `Moderator` 先声明本轮命题和正反双方
2. `Proposer` 先给出主张，限制在 `1-2` 句
3. `Challenger` 必须直接反驳 `Proposer` 的某个具体点
4. `Responder` 必须对刚才那条反驳作答，不能转移到新议题
5. `Judge` 明确指出：当前谁占优、还缺什么证据、是否继续追击
6. 至少 1 个可执行动作：修复、验证、降调、停损或转向
7. 本轮结束时给出收敛度：`高 / 中 / 低`

**发言检查**:
- 如果一句话删掉前文仍然成立，说明它不是回应，必须重写
- 如果某角色没有引用前一个角色的 claim、证据或假设，说明它在自说自话
- 如果新分歧点比旧分歧点更不关键，`Moderator` 必须拉回原命题

**可选调解室**:
- 只有在两个角色争执的是“同一个核心分歧”时才开
- 调解目标不是“和稀泥”，而是明确共识边界和 remaining disagreement

### Step 4: 决策

在收敛度足够高，或达到 `max_rounds` 后，输出 go/no-go 决策、排序或补证据计划。

## 评分与停损规则

避免伪精确。评分只用于帮助排序，不替代判断。

### 四维评分

对每个方案给 `0-5` 分：
- `Evidence`: 现有证据是否支持核心 claim
- `Method`: 设计是否能识别并支撑 claim
- `Execution`: 数据、工程、成本、时间是否可行
- `Narrative`: 站位、贡献与投稿目标是否匹配

### 权重

- `Evidence`: `35%`
- `Method`: `30%`
- `Execution`: `20%`
- `Narrative`: `15%`

### 一票否决 / 降级规则

- `Evidence <= 1` 且短期内没有便宜的补证据路径：默认 `No-Go`
- `Method <= 2` 且问题触及核心识别假设：不能排第 1
- `Execution <= 1` 且需要的数据/资源短期拿不到：标记 `Defer`
- 如果主要结论建立在未核验证据上：总评最多到 `Conditional Go`

## 输出格式

```markdown
# Roundtable Setup
- Mode:
- Active Roles:
- Assumptions:
- Evidence Status:
- Core Agenda:

## Option Cards
### Option A
- Claim:
- Data / Setting:
- Method:
- Primary Metric:
- Minimum Winning Evidence:
- Main Risks:
- Cost / Time:

## Round 0
### ResearchArchitect
> ...

## Round 1（命题：...，收敛度：低/中/高）
### Moderator
> 本轮只讨论这个命题：...
> 正方：...
> 反方：...

### Proposer
> 我的主张是...

### Challenger
> 我反对你刚才关于“...”的判断，因为...

### Responder
> 我接受你说的...，但你忽略了...

### Judge
> 当前占优的是...；真正未解决的是...；如果要翻盘，需要补...

**本轮动作 / 裁定**:
- ...

## Final Decision
## Ranking / Recommendation
| 方案 | Evidence | Method | Execution | Narrative | Weighted Total | Recommendation |

## Why
- 1.
- 2.
- 3.

## Evidence Gaps
- ...

## Risk Register
- 风险:
  验证方式:
  触发停损点:

## Next Actions
- 优先级 1:
- 优先级 2:
- 优先级 3:
```

## 全局规则

- `max_rounds`: 默认 3；只有在仍存在高价值未解分歧时才加到 4-5
- `speaking_limit`: 默认每位角色每轮 `1-3` 句；必要时宁可减少角色，也不要堆对白
- `decision_priority`: `证据 > 方法 > 工程 > 叙事`
- `interaction_rule`: 每轮至少出现一次 `主张 -> 反驳 -> 回应`；没有互动就重做
- `good_output`: 让用户知道“该做哪一个、为什么、缺什么证据、何时止损”
- `bad_output`: 只是热闹，没有明确排序、停损点和下一步
