# HTML 产品需求文档 Skill

把已经稳定的产品需求转成研发、设计和测试可直接使用的中文交互式 HTML PRD。

## 交付内容

- 先输出 Mermaid 流程图，等待用户确认后再生成 HTML PRD。
- HTML 中固定包含需求 list、需求背景、流程图、页面/操作节点需求明细和验收标准。
- 每个页面卡片包含原型图、前端交互逻辑、后端数据逻辑、接口定义和异常处理逻辑。
- 前端逻辑覆盖页面布局、图标/图片/按钮的尺寸与展示规则；后端逻辑覆盖数据计算规则。
- 提供右上角悬浮目录和可收起的逻辑模块。
- 四套模板都包含隐藏的完整页面卡片示范，展示原型图占位、前后端逻辑、接口表和异常/验收填写粒度；生成最终文档时复制其结构并删除示范容器。

## 什么时候用

- 需要新建或更新一份完整、可交付的中文 HTML PRD。
- 输入是产品想法、功能需求、业务规则、原型/截图、流程笔记、模块清单或已确认流程。
- 希望输出完整页面说明、接口、异常与验收口径，而不是只讨论一个需求点。

## 什么时候不用

- 只要头脑风暴、问答、流程图、出图提示词、UI 方案、前端代码、接口实现、测试用例或测试报告。
- 明确只要 Markdown、Word 或 PDF，且不需要同步生成 HTML PRD。
- 需求仍有会影响目标、范围、交付物、优先级、约束或验收的关键不确定项；先在本 Skill 内一次确认影响最大的一项，再生成文档。

## 行业模板匹配

Skill 会根据需求本身适配模板，而不是要求用户先选样式：

| 明确匹配的需求 | 使用模板 |
| --- | --- |
| 电商、内容、会员、生活服务、消费端 App/H5 | `prd-consumer-service-template.html` |
| 医疗健康、护理、预约、患者服务、健康管理 | `prd-healthcare-template.html` |
| 金融、保险、政务、公共服务、强合规流程 | `prd-finance-public-service-template.html` |
| 未命中或无法明确匹配行业模板 | `prd-document-template.html`（通用） |

所有模板都保留相同的业务结构、接口表、异常逻辑、验收标准和悬浮目录；模板只改变阅读版式与视觉层级。

## 接入 Product Workflow Router 时

Router 不是生成 HTML PRD 的前置条件。已有 Router task 时，按 [交接信封 v1](https://github.com/shilisong1996-cpu/product-workflow-router/blob/main/contracts/handoff-envelope.md) 继承需求、视觉和素材引用：若有未关闭澄清项，不重复提问，也不因无关补充自动关闭；发现会改变业务、页面、接口或验收的缺口时回到最早受影响阶段。`figma_delivery=skipped` 时可直接引用确认视觉稿和用户原始静态素材，不要求补做 Figma。

## 安装

将整个仓库目录作为一个 Skill 安装到 Codex 的个人 Skills 目录，并命名为 `pm-requirements`：

```bash
git clone https://github.com/shilisong1996-cpu/pm-requirements.git
mv pm-requirements ~/.codex/skills/pm-requirements
```

不要只复制 `SKILL.md`；`assets/` 中的四套 HTML 模板是 Skill 的必要组成部分。

## 仓库结构

```text
pm-requirements/
├── SKILL.md
├── agents/openai.yaml
├── assets/
│   ├── prd-document-template.html
│   ├── prd-consumer-service-template.html
│   ├── prd-healthcare-template.html
│   └── prd-finance-public-service-template.html
└── README.md
```
