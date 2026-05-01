---
name: gb-reference-generator
description: "Use when: 用户需要搜索学术论文（SCI期刊论文及高水平会议论文）、生成符合GB/T 7714-2015标准的参考文献表、撰写论文引用或做文献综述；每篇文献必须经过真实性验证并附带原文链接。"
---
# GB参考文献生成器
## 快速开始
1. 明确检索主题、关键词和期望文献数量
2. 同时搜索 Google Scholar（英文/SCI）和 CNKI（中文）
3. 逐篇验证真实性和完整性
4. 获取每篇的原文链接（DOI 优先）
5. 按作者姓氏字母序排序，纯文本 GB/T 7714-2015 格式输出
## 文献类型范围
本技能覆盖两种类型：
| 类型 | 标识 | 说明 |
|------|------|------|
| 期刊论文 | `[J]` | SCI 收录期刊、中文核心期刊 |
| 会议论文 | `[C]` | SCI/EI 收录的高水平会议（如 NeurIPS、ICML、CVPR、ACL、AAAI 等 CCF 推荐会议） |
- SCI 文献优先，中文文献适当占比（非必须）
- arXiv 预印本**仅作参考**，优先使用已发表的正式版本
## 工作流程
### 第一步：检索
- **Google Scholar**：搜索英文 SCI 期刊论文和顶会论文，优先高被引、近 5 年发表
- **CNKI**：搜索中文核心期刊论文
- 收集超过需求量 **20%~30%** 的候选文献（为验证淘汰留余量）
### 第二步：逐篇验证（防幻觉关键环节）
**每篇文献必须满足以下全部条件，否则丢弃：**
1. **信息完整性**：确认作者全名、题名、期刊/会议全称、出版年、卷号/期号/页码、DOI
2. **交叉确认**：通过至少一个独立来源核实（DOI 解析 → Crossref / 期刊/会议官网 / DBLP / CNKI 记录）
3. **原文可访问**：找到浏览器可直接打开的原文/摘要链接
4. **会议论文额外验证**：确认会议级别（CCF 推荐列表 / SCI 收录），优先 A 类会议
5. **无法验证的文献直接丢弃**，不用标注，不纳入最终列表
### 第三步：获取原文链接
- **优先**：DOI 链接（`https://doi.org/...`）
- **备选**：期刊/会议官网、DBLP 链接、CNKI 链接
- 链接必须可公开访问（至少能打开摘要页）
### 第四步：格式化输出
**格式标准**：GB/T 7714-2015
## GB/T 7714-2015 著录格式
**期刊论文 `[J]`**：
- 中文：`[序号] 作者1, 作者2, 作者3, 等. 题名[J]. 刊名, 年, 卷(期): 起页-止页.`
- 英文：`[序号] Author A A, Author B B, Author C C, et al. Title[J]. Journal Name, Year, Volume(Issue): Pages.`
**会议论文 `[C]`**：
- 中文：`[序号] 作者1, 作者2, 作者3, 等. 题名[C]// 会议录名称. 出版地: 出版者, 出版年: 起止页码.`
- 英文：`[序号] Author A A, Author B B, Author C C, et al. Title[C]// Proceedings of the Conference Name. Place: Publisher, Year: Pages.`
**作者数量规则**：
- 3 人及以内：全部列出
- 超过 3 人：列前 3 人 + 「, 等」或 「, et al.」
**英文作者格式**：
- 姓在前全大写，名缩写（首字母大写加点），如 `VASWANI A, SHAZEER N, PARMAR N, et al.`
- 名缩写之间不加空格
## 排序规则
- 英文作者：按**姓氏字母序**（A→Z）
- 中文作者：按**拼音字母序**
- 中英混排：统一按字母序合并排序（拼音与英文不区分）
## 输出模板
[1] Author A A, Author B B. Title[J]. Journal Name, 2020, 15(3): 123-130.
    原文: https://doi.org/10.xxxx/xxxxx
[2] Author C C, Author D D, Author E E, et al. Title[C]// Proceedings of
    ABC Conference 2022. New York: ACM, 2022: 456-465.
    原文: https://doi.org/10.yyyy/yyyy
[3] 张三, 李四. 论文标题[J]. 期刊名, 2019, 10(2): 45-50.
    原文: https://kns.cnki.net/...
## 搜索时间标注
每条文献末尾可选标注检索确认时间（格式：`[检索日期: YYYY-MM-DD]`），便于追溯。
## 进阶参考
- 详细格式规则见 [REFERENCE.md](REFERENCE.md)
- 完整使用示例见 [EXAMPLES.md](EXAMPLES.md)