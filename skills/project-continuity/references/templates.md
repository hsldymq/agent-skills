# Adaptable Templates

Use these as content checklists, not mandatory filenames or headings. Remove fields that add no value and adopt
the repository's language and conventions. These examples use Simplified Chinese because it is the default for
new projects. Translate their semantic structure when the user or an established project selects another
language; do not produce bilingual copies unless requested.

## Repository entry point

```markdown
# 项目文档

## 从这里接力
1. 当前状态
2. 当前里程碑
3. 状态指向的设计与决策
4. 相关代码与测试
5. 版本控制状态与近期历史

## 文档地图
| 问题 | 权威来源 |
|---|---|

## 冲突处理
说明预期行为、实现证据、工作优先级和长期方向发生冲突时如何核验与收敛。
```

## Current status / handoff

```markdown
# 当前状态

最后核验：YYYY-MM-DD

## 当前目标与里程碑
## 能力状态
| 能力 | 设计 | 实现 | 验证 | 权威来源/证据 |
|---|---|---|---|---|

## 仓库事实
## 最近接受的决定
## 有序开放问题

### 当前问题
- 需要决定：
- 影响范围/里程碑：
- 已知约束：
- 候选方向：
- 当前倾向及原因：
- 收敛条件：

## 唯一下一步
## 实际完成的验证
## 工作区与接力说明
```

## Decision record

```markdown
# NNNN：决策标题

状态：Proposed | Accepted | Superseded
日期：YYYY-MM-DD
影响范围：
替代 / 被替代：

## 背景与问题
## 约束与假设
## 候选方案
## 决定
## 理由与取舍
## 后果与风险
## 验证要求
## 重新评估条件
```

## Bounded design

```markdown
# 能力设计

状态：
最后更新：
影响里程碑：

## 目的与范围
## 非目标
## 术语与不变量
## 职责与所有权
## 数据流与控制流
## API 或协议契约
## 状态与生命周期
## 并发与资源边界
## 失败、取消与恢复
## 保证与非保证
## 已接受决定与取舍
## 验证计划与证据
## 开放问题
## 重新评估条件
```

## Repository-local agent/contributor instructions

```markdown
# 项目连续性说明

开始工作前：
- 阅读文档入口与当前状态。
- 阅读当前里程碑和能力对应的权威设计与决策。
- 检查版本控制状态、相关代码与测试。
- 先收敛冲突，再继续扩大修改。

完成重要工作后：
- 只更新受到影响的权威载体。
- 分别记录设计、实现与验证状态。
- 保留决策理由、取舍与被替代历史。
- 记录实际验证、未解决风险、工作区状态和唯一下一步。
```
