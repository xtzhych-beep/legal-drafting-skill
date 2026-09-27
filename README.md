# legal-drafting

一个 **Claude Code 技能（Skill）**：起草中国法律文书——起诉状、答辩状、律师函、合同、通知函件、婚内财产协议等，覆盖民事、刑事、劳动仲裁、婚姻家事。

它不是"让 AI 帮你写文书"那么简单。它把**执业律师起草文书时真正会做的两件事**固化成了强制流程。

---

## 它解决什么问题

让 AI 写法律文书，最常见的失败不是文笔差，是这两种：

**一、套模板套出错误。** 模型见过一万份"合同解除通知"，于是写出一份"标准"的——包括那句"恢复原状"。但你手上那份合同约定的是"不得破坏装修"。**模板思维会覆盖合同原文。**

**二、写得漂亮，但没抓住钱。** 一份逻辑严密、引经据典的文书，可能把力气花在了次要条款上，而真正的财产价值在另一处沉没着。

这个技能用一条**两步验证法**把这两个坑堵住。

---

## 核心方法：两步验证法（强制）

起草任何文书前，必须先走完这两步。

### 第一步 · 对照原文

涉及已有合同或协议的，**逐条对照原文**核实每个表述，不得依赖模板惯性。

> 每一句话都要有合同条款或法律依据支撑。
> **禁止使用"恢复原状"这类概括性表述——先查合同里到底约定了什么。**

### 第二步 · 商业利益分析

问自己一句：**这个条款背后的钱在哪里？**

每个条款都对应一个实际财产价值——装修添附可能是几万到十几万的沉没成本，违约金是实际能收回的现金，履约保证是对方真正的核心利益所在。

**优先保护最有经济价值的权利，不在次要条款上消耗资源。**

### 这两步怎么协同

举个方法层面的示意（**虚构，仅说明方法**）：某份租赁合同约定承租方"不得破坏装修"，出租方要解约。

- 只走第一步：你会写"要求恢复原状"——但这与合同约定冲突，且真的恢复原状对出租方未必有利。
- 加上第二步：你会先算这笔装修添附值多少钱、折旧到第几年、恢复原状的成本由谁承担、留着它是否更值钱。**然后才发现该主张的根本不是"恢复原状"。**

第二步不是修辞，它决定第一步该主张什么。

---

## 第二个特性：起草前强制检索办案指引

**起草任何文书前，技能会强制按顺序检索是否存在对应的权威指引：**

1. **全国律协**发布的业务操作指引
2. **地方律协**（广东、深圳、广州等）发布的业务操作指引
3. **最高人民法院**发布的文书样式或示范文本
4. 法律出版社、中国法制出版社等**权威出版社**的文书范本

命中即作为约束性框架，在指引结构内填充案情，**不得偏离**。

举例：起草婚内财产协议时，技能会先定位到全国律协《律师办理婚姻家庭法律业务操作指引》第 139 条，按其规定的**十项必备内容**逐项落实。

---

## 效力层级

技能内置了一张效力层级表，让 AI 知道哪些是"必须遵守"、哪些只是"可以借鉴"：

| 层级 | 来源 | 处理规则 |
|---|---|---|
| 🥇 强制规范 | 最高法/最高检官方文书样式 | **必须遵守**，要素不得删改 |
| 🥈 行业指引 | 全国律协 / 地方律协业务操作指引 | **优先参考**，除当事人另有要求 |
| 🥉 权威参考 | 出版社文书范本丛书 | **借鉴格式**，不强制 |
| 📖 通用规范 | 国家标准（GB/T 15834 等） | **通用遵守** |

配套一张速查表，列明婚姻家庭、民事起诉状、刑事文书、执行文书、检察文书等领域的现行指引与编号（含 2025 年全面推行的**67 类要素式起诉状/答辩状示范文本**）。

---

## 安装

```bash
git clone https://github.com/xtzhych-beep/legal-drafting-skill.git ~/.claude/skills/legal-drafting
```

重启 Claude Code 即可。技能会被自动发现。

> 默认安装在用户级（`~/.claude/skills/`）。想只在某个项目里用，就放到该项目的 `.claude/skills/` 下。

---

## 用法

```
/legal-drafting 起草一封合同解除通知
/legal-drafting 写一份劳动仲裁申请书
/legal-drafting 帮我写律师函——催收货款
/legal-drafting 起草婚内财产协议
```

也可以直接说"帮我起草一份……"，技能会自动判断是否启动。

**默认输出 .docx**（Word），排版符合文书规范（A4、宋体/仿宋小四、标题小二居中、1.5 倍行距）。需要 Markdown、PDF 等其他格式时提前说明即可。

---

## 起草纪律

1. **最少的字表达完整的意思**——删掉所有可有可无的修饰语
2. **每个结论必须有依据**——合同条款、法律条文，或双方确认的事实
3. **数字与金额必须双重确认**——合同原文与计算结果要一致，不一致必须标注
4. **法条必须核实效力状态**——引用前确认未被废止或修订

---

## 适用范围

| 类别 | 具体文书 |
|---|---|
| 合同类 | 审查意见书、起草/修订、补充协议、解除协议 |
| 通知函件 | 合同解除通知、催告函、律师函、解除劳动关系通知、声明 |
| 民事 | 起诉状、答辩状、代理词、上诉状、再审申请、执行申请 |
| 刑事 | 辩护词、取保候审申请、法律意见书 |
| 劳动仲裁 | 仲裁申请书、答辩书、质证意见 |
| 婚姻家事 | 婚内财产协议、婚前财产约定、离婚协议、分居协议、抚养权变更 |
| 信息采集 | 案件信息采集表、证据清单、委托手续 |

---

## 重要声明

> **本技能不代替律师的专业判断。** 它产出的是初稿，**必须经执业律师审阅后**才能对外出具。
>
> 法律会修订，地方司法实践有差异。技能中的指引编号、文书样式、法条效力状态**请在使用前自行核实**。作者不对因使用本技能产生的任何后果承担责任。

---

## License

MIT —— 见 [LICENSE](LICENSE)。可自由使用、修改、商用，保留版权声明即可。

---

## 关于作者

张元辰，执业律师，广东知恒（西安）律师事务所。主要办理刑事辩护、婚姻家事、合同纠纷与劳动仲裁。

这个技能来自日常办案中的实际需要——先解决自己的问题，再拿出来分享。

---

<details>
<summary>English</summary>

A **Claude Code Skill** for drafting Chinese legal documents — complaints, statements of defence, attorney letters, contracts, notices, and marital property agreements.

Unlike a generic "write me a contract" prompt, it enforces a **two-step verification** that mirrors what a practising lawyer actually does before drafting:

1. **Check against the source text** — verify every assertion against the actual contract, never relying on template habits.
2. **Commercial-value analysis** — identify where the money actually sits in each clause, and protect the most valuable rights first.

It also forces a **priority lookup of authoritative drafting guidelines** (All China Lawyers Association, provincial bar associations, Supreme People's Court model documents) before writing, and ships a hierarchy table telling the model what is mandatory versus merely advisory.

Drafting is in Chinese and targets Chinese legal practice.

</details>
