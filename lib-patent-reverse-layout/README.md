# lib-patent-reverse-layout 快速使用指南

## 一句话定位

本技能用于**实测数据驱动的可反向专利撰写**——从已有实测产品、材料信息、极片结构参数和性能结果出发，倒推构建可反向检测、可举证覆盖的专利申请文件。

## 触发场景

| 用户的输入材料 | 是否应触发本技能 |
|---|---|
| 实测产品的部件尺寸、材质、视觉特征 + 性能参数 | ✓ |
| 实测产品 + 原专利（且原专利与实物冲突） | ✓ |
| 仅有研发交底书 / 实验记录 | ✗（应用 lib-patent-refiner） |

## 4 步分段工作流

```
Step 1: Reverse_Claims          → 权利要求设计 (10-15 项)
   └→ [等待用户确认] ✓

Step 2: Reverse_Examples        → 实施例 + 对比例
   └→ [等待用户确认] ✓

Step 3: Reverse_Perftest        → 详细性能测试方法
   └→ [等待用户确认] ✓

Step 4: Reverse_IdentifyTest    → 可反向性能测试 (产品鉴定)
   └→ [等待用户确认] ✓

Compile: Reverse_Compile        → 合成最终 md

Optional: Reverse_FinalDraftOptimize → 最终稿整合优化
```

**每步结束必须等待用户显式确认**，未确认绝不推进。

## 核心方法论

1. **三维设计模型**：材料 × 极片 × 性能 三维交叉布局
2. **数据居中区间设计法**：让实测值嵌入权要区间正中
3. **反向可测性评分**：选易从成品检测的参数作为主权要核心
4. **规避封堵**：对比例覆盖 5 类规避路径
5. **CNIPA 说明书补强**：吸收实施例、测试标准、产品鉴定和逐变量机理模板

## 文件清单

| 文件 | 用途 |
|---|---|
| `SKILL.md` | 主技能文件，定义触发与工作流 |
| `VERSION.md` | 独立版本模块，记录版本号、来源兼容和变更摘要 |
| `references/three_dimension_design.md` | 三维模型 + 6 种组合模式 |
| `references/data_centering_rules.md` | 数据居中 ±% 库 |
| `references/claim_layer_template.md` | 10-15 项权要层级模板 |
| `references/circumvention_blocking_templates.md` | 5 类规避封堵对比例模板 |
| `references/reverse_perftest_methods.md` | 详细性能测试方法库 |
| `references/reverse_identify_methods.md` | 产品反向鉴定方法库 |
| `references/reverse_compile_markdown_output.md` | Markdown 最终申请稿合成规则 |
| `references/final_draft_optimization_patterns.md` | 最终稿二次优化、实施例具体化、逐变量机理和单只电池反向鉴定规则 |

## 与 lib-patent-refiner 的关系

| 项 | lib-patent-refiner | lib-patent-reverse-layout |
|---|---|---|
| 起点 | 交底书/实验数据 | 实测产品+性能 |
| 流程 | 正向（创新→保护） | 反向（产品→保护） |
| 触发 | 有交底书 | 有实测产品 |
| 资源 | 自有完整资源 | 主流程独立 + 只读复用对方的工艺/测试/机理/鉴定资源 |

## 部署说明

将 `lib-patent-reverse-layout/` 整个目录放入 `/mnt/skills/user/` 下，Claude 将自动加载该技能。

## 版本

版本号、变更记录和兼容来源见 `VERSION.md`。

## 反馈

如需调整工作流、增删参考文档、修改默认参数，请直接向 Claude 提出意见。
