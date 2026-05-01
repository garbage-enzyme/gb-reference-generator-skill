<p align="center">
  <strong>本仓库所有内容均为ai生成</strong>
</p>

# 🔖 GB参考文献生成器

> 联网搜索学术论文，逐篇验证真实性，一键生成符合 **GB/T 7714-2015** 标准的参考文献表。

<p align="center">
  <strong>SCI期刊 &nbsp;·&nbsp; CCF顶会 &nbsp;·&nbsp; 中文核心 &nbsp;·&nbsp; 杜绝幻觉</strong>
</p>

---

## 💡 为什么需要这个工具？

使用 AI 生成参考文献时，最常见的问题是：

| 问题 | 说明 |
|------|------|
| 🔴 **AI 幻觉** | 模型编造看似真实但根本不存在的论文 |
| 🟠 **信息残缺** | 缺作者、缺卷期、缺页码、DOI 打不开 |
| 🟡 **格式混乱** | 不符合 GB/T 7714-2015，被期刊/导师退回 |
| 🟢 **链接失效** | 给了链接却发现是付费墙或 404 |

本工具的核心设计：**每篇文献必须经过真实性交叉验证，验证不通过的直接丢弃。**

---

## ✨ 功能特性

- 🔍 **双源并行检索** — Google Scholar（英文/SCI）+ CNKI（中文核心）
- 🛡️ **逐篇防幻觉验证** — DOI 解析 + Crossref + 期刊官网 + DBLP + CNKI 多重交叉确认
- 📄 **GB/T 7714-2015 标准输出** — 期刊 `[J]` + 会议 `[C]`，纯文本直接复制粘贴
- 🔗 **每篇附原文链接** — DOI 优先，确保可公开访问
- 🔤 **智能排序** — 按作者姓氏字母序，中英混排统一处理

---

## 📁 文件结构

```
gb-reference-generator/
├── SKILL.md           # 主指令：检索→验证→格式化，约60行
├── EXAMPLES.md        # 完整对话示例（期刊+会议论文混排）
├── REFERENCE.md       # GB/T 7714-2015 格式详解（边界情况速查）
└── README.md          # 本文件
```

| 文件 | 用途 |
|------|------|
| `SKILL.md` | 加载后即用的核心技能指令 |
| `EXAMPLES.md` | 6 篇文献完整检索示例，含验证淘汰过程 |
| `REFERENCE.md` | 作者格式、标点规范、边界情况、会议出版信息速查表 |

---

## 🎯 覆盖范围

| 类型 | 标识 | 来源 |
|------|------|------|
| SCI 期刊论文 | `[J]` | Nature / ACM Computing Surveys / JAIR / … |
| CCF-A 会议论文 | `[C]` | NeurIPS / ICML / CVPR / ACL / AAAI / … |
| 中文核心期刊 | `[J]` | CNKI 收录的核心期刊 |
| arXiv 预印本 | ❌ | 优先使用已发表的正式版本 |

---

## 🚀 快速开始

加载技能后，直接描述需求：

```
帮我找 5 篇关于大语言模型幻觉的论文，SCI 优先，中文也要有
```

技能会自动执行以下流程：

```
检索（GS + CNKI）
    ↓
筛选（排除 arXiv / 低水平会议）
    ↓
逐篇验证（DOI → Crossref → 期刊官网）
    ↓
排序（作者姓氏字母序）
    ↓
格式化输出（GB/T 7714-2015 纯文本）
```

---

## 📋 输出示例

```
[1] CHANG Y, WANG X, WANG J, et al. A survey on evaluation of large
    language models[J]. ACM Computing Surveys, 2024, 56(8): Article 195.
    原文: https://doi.org/10.1145/3641289

[2] CHEN Z, ZHAO Z, LUO H, et al. HALC: object hallucination reduction
    via adaptive focal-contrast decoding[C]// Proceedings of the IEEE/CVF
    Conference on Computer Vision and Pattern Recognition (CVPR).
    Piscataway: IEEE, 2024.
    原文: https://doi.org/10.1109/CVPR52733.2024

[3] 黄勃, 吴申奥, 王文广, 等. 图模互补：知识图谱与大模型融合综述[J].
    武汉大学学报(理学版), 2024, 70(4): 397-412.
    原文: https://kns.cnki.net/

[4] HUANG Q, DONG X, ZHANG P, et al. OPERA: alleviating hallucination in
    multi-modal large language models via over-trust penalty and
    retrospection-allocation[C]// Advances in Neural Information Processing
    Systems 36 (NeurIPS 2023). Cambridge: MIT Press, 2023.
    原文: https://papers.nips.cc/

[5] LIU M, ZHANG Y, LI X, et al. Application of large language models in
    medicine[J]. Nature Reviews Bioengineering, 2025, 3: 259-274.
    原文: https://www.nature.com/articles/s44222-025-00279-5

[6] ZHANG S, ROLLER S, GOYAL N, et al. Stay on topic with classifier-free
    guidance[C]// Proceedings of the 41st International Conference on
    Machine Learning (ICML 2024). PMLR, 2024.
    原文: https://proceedings.mlr.press/
```

> 详见 [`EXAMPLES.md`](EXAMPLES.md) 中完整的检索与验证过程。

---

## 🛡️ 防幻觉机制

每篇文献必须同时满足以下 **5 个条件**：

| # | 条件 | 验证方式 |
|---|------|----------|
| 1 | 信息完整性 | 作者全名、题名、刊名/会议名、年、卷、期、页码、DOI 缺一不可 |
| 2 | 交叉确认 | DOI → Crossref / 期刊官网 / DBLP / CNKI 至少两个来源一致 |
| 3 | 原文可访问 | 浏览器可打开（至少摘要页），非死链 |
| 4 | 级别达标 | 期刊：SCI/中文核心；会议：CCF 推荐 / SCI 收录 |
| 5 | 已正式发表 | arXiv 预印本仅作参考，优先正式出版版本 |

**任何一条不满足 → 直接丢弃，不纳入最终列表。**

---

## 📐 格式速查

### 期刊论文 `[J]`

```
[序号] 作者. 题名[J]. 刊名, 年, 卷(期): 起页-止页.
```

### 会议论文 `[C]`

```
[序号] 作者. 题名[C]// 会议录名称. 出版地: 出版者, 年: 起止页码.
```

### 作者格式

| 语种 | 规则 | 示例 |
|------|------|------|
| 英文 | 姓全大写，名缩写加点 | `VASWANI A, SHAZEER N, PARMAR N, et al.` |
| 中文 | 姓在前名在后，全称 | `黄勃, 吴申奥, 王文广, 等.` |
| 人数 | 3 人内全列，≥4 人列前 3 + 等/et al. | |

> 更多边界情况（缺卷期、合期、在线优先出版等）见 [`REFERENCE.md`](REFERENCE.md)。

---

## 📦 本地使用

```bash
# 克隆仓库
git clone https://github.com/你的用户名/gb-reference-generator.git

# 进入目录
cd gb-reference-generator

# 将 SKILL.md 加载到你的 AI 助手中即可使用
```

---

## 🤝 贡献

欢迎提交 Issue 或 Pull Request，改进方向包括：

- 补充更多文献类型（学位论文 `[D]`、专利 `[P]` 等）
- 增加 BibTeX 输出格式
- 完善常见会议出版信息速查表

---

## 📄 许可

MIT License — 自由使用、修改、分发。

---

<p align="center">
  <sub>Made with ❤️ for researchers who are tired of AI hallucinations.</sub>
</p>
