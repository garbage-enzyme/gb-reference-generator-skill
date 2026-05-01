# REFERENCE.md — GB/T 7714-2015 参考文献格式详解
> 本文档详述 GB/T 7714-2015《信息与文献 参考文献著录规则》中
> **期刊论文 `[J]`** 和 **会议论文 `[C]`** 的著录规则。
> 作为 SKILL.md 的补充参考，处理边界情况时查阅。
---
## 一、文献类型标识
| 标识 | 中文名称 | 英文名称 |
|------|----------|----------|
| `[J]` | 期刊文章 | Journal Article |
| `[C]` | 会议录/论文集 | Conference Proceeding / Collection |
| `[M]` | 专著/图书 | Monograph |
| `[D]` | 学位论文 | Dissertation |
| `[P]` | 专利 | Patent |
| `[S]` | 标准 | Standard |
| `[R]` | 报告 | Report |
| `[EB/OL]` | 电子资源（联机） | Electronic Resource (Online) |
---
## 二、期刊论文 `[J]` 著录规则
### 2.1 标准格式
```
[序号] 主要责任者. 题名[J]. 刊名, 年, 卷(期): 起页-止页.
```
### 2.2 示例
**英文示例：**
```
CHANG Y, WANG X, WANG J, et al. A survey on evaluation of large
language models[J]. ACM Computing Surveys, 2024, 56(8): Article 195.
```
**中文示例：**
```
黄勃, 吴申奥, 王文广, 等. 图模互补：知识图谱与大模型融合综述[J].
武汉大学学报(理学版), 2024, 70(4): 397-412.
```
### 2.3 字段详解
| 字段 | 规则 | 示例 |
|------|------|------|
| **作者** | 3人内全列，超3人列前3+「等」/「et al.」 | `CHANG Y, WANG X, WANG J, et al.` |
| **英文作者** | 姓全大写在前，名缩写加点在后，缩写间不加空格 | `VASWANI A` / `LE Q V` |
| **中文作者** | 姓在前名在后，全称，无缩写 | `黄勃` / `张三丰` |
| **题名** | 完整保留原文（英文首字母大写或句首大写均可，全文统一） | — |
| **刊名** | 英文用标准缩写或全称，全文统一；中文用全称 | `ACM Comput. Surv.` 或 `ACM Computing Surveys` |
| **年** | 四位数字 | `2024` |
| **卷(期)** | 卷号加粗或正常均可，期号在括号内 | `56(8)` |
| **页码** | 起止页码用短横线连接 | `397-412` |
### 2.4 边界情况处理
| 情况 | 处理方式 | 示例 |
|------|----------|------|
| 缺卷号 | 只写年和期 | `2024(8): 12-20` |
| 缺期号 | 只写年和卷 | `2024, 56: 12-20` |
| 缺页码 | 标注 DOI 或 URL | `DOI: 10.xxxx/xxxxx` |
| 在线优先出版（无卷期） | 标注年 + DOI | `2024. DOI: 10.xxxx/xxxxx` |
| 电子期刊 `[J/OL]` | 加载体标识和引用日期 | `[J/OL]. 刊名, 年[引用日期]. URL` |
| 合期出版 | 用 `/` 连接期号 | `56(4/5): 100-110` |
| 文章编号（无连续页码） | 用 `Article` 标注 | `56(8): Article 195` |
---
## 三、会议论文 `[C]` 著录规则
### 3.1 标准格式
```
[序号] 主要责任者. 题名[C]// 会议录名称. 出版地: 出版者, 出版年: 起止页码.
```
### 3.2 示例
**英文顶会论文：**
```
HUANG Q, DONG X, ZHANG P, et al. OPERA: alleviating hallucination in
multi-modal large language models via over-trust penalty and
retrospection-allocation[C]// Advances in Neural Information Processing
Systems 36 (NeurIPS 2023). Cambridge: MIT Press, 2023.
```
```
CHEN Z, ZHAO Z, LUO H, et al. HALC: object hallucination reduction via
adaptive focal-contrast decoding[C]// Proceedings of the IEEE/CVF
Conference on Computer Vision and Pattern Recognition (CVPR).
Piscataway: IEEE, 2024.
```
```
ZHANG S, ROLLER S, GOYAL N, et al. Stay on topic with classifier-free
guidance[C]// Proceedings of the 41st International Conference on
Machine Learning (ICML 2024). PMLR, 2024.
```
### 3.3 字段详解
| 字段 | 规则 | 说明 |
|------|------|------|
| **作者** | 同期刊论文规则 | 3人内全列 |
| **题名** | 完整保留 | 同期刊规则 |
| **会议录名称** | 完整会议名 + 缩写（括号内），如 `NeurIPS 2023` | 方便读者识别 |
| **出版地** | 城市名，英文可用州名 | `Cambridge` / `Piscataway` / `北京` |
| **出版者** | 出版社全称 | `MIT Press` / `IEEE` / `ACM` / `PMLR` |
| **出版年** | 四位数字 | `2024` |
| **页码** | 起止页码，缺页码可省略 | `456-465` |
### 3.4 常见会议出版信息速查
| 会议缩写 | 出版者 | 出版地 |
|----------|--------|--------|
| NeurIPS | MIT Press / Curran Associates | Cambridge, MA |
| ICML | PMLR | (在线) |
| ICLR | OpenReview | (在线) |
| CVPR | IEEE | Piscataway, NJ |
| ICCV | IEEE | Piscataway, NJ |
| ACL | ACL | Stroudsburg, PA |
| AAAI | AAAI Press | Palo Alto, CA |
| WWW | ACM | New York, NY |
| SIGIR | ACM | New York, NY |
| SIGMOD | ACM | New York, NY |
### 3.5 边界情况处理
| 情况 | 处理方式 |
|------|----------|
| 会议论文仅在线发表 | 加 `[EB/OL]` 标识，标注 URL 和访问日期 |
| 缺出版地 | 标 `[出版地不详]` 或留空，用 `[s.l.]` |
| 缺出版者 | 标 `[出版者不详]` 或留空，用 `[s.n.]` |
| Workshop 论文 | 建议标注所属主会议：`Workshop on XXX, NeurIPS 2023` |
| Poster / Spotlight | 不影响著录格式，按正常会议论文处理 |
---
## 四、作者名格式规则
### 4.1 英文作者
```
姓全大写, 名缩写加点
```
| 原名 | GB 格式 |
|------|---------|
| Ashish Vaswani | `VASWANI A` |
| Quoc V. Le | `LE Q V` |
| Yoshua Bengio | `BENGIO Y` |
| Geoffrey E. Hinton | `HINTON G E` |
| Noam Shazeer | `SHAZEER N` |
**注意**：
- 姓和名之间用空格分隔
- 名缩写之间**不加空格**（如 `LE Q V` 而非 `LE Q. V.`）
- 多个作者之间用逗号分隔
### 4.2 中文作者
保持不变，姓在前名在后，多个作者用逗号分隔：
```
黄勃, 吴申奥, 王文广, 等.
```
### 4.3 作者数量规则
| 作者数 | 处理 |
|--------|------|
| 1–3 人 | 全部列出 |
| ≥4 人 | 列前 3 人 + 「, 等」（中文）或「, et al.」（英文） |
---
## 五、标点符号规范
| 符号 | 用途 | 前后空格 |
|------|------|----------|
| `.` | 字段结束 | 后空一格（或延续下一字段） |
| `,` | 作者分隔/字段内分隔 | 后空一格 |
| `:` | 页码前缀 | 后空一格 |
| `//` | 会议录前缀（仅 [C]） | 前空一格 |
| `()` | 期号 | 紧跟卷号 |
| `[]` | 文献类型标识 | 紧跟题名 |
| `-` | 起止页码连接 | 前后不加空格 |
---
## 六、排序规则
按作者姓氏字母序排列：
1. **英文**：按姓氏首字母（A→Z），同字母比较第二字母，以此类推
2. **中文**：按拼音首字母（A→Z），规则同上
3. **中英混排**：统一按字母序（拼音与英文不区分）
同作者多年份：按出版年升序排列。
---
## 七、快速检查清单
输出每篇文献前，确认以下项目：
- [ ] 作者格式正确（英文姓全大写、名缩写）
- [ ] 题名完整、无遗漏
- [ ] `[J]` / `[C]` 标识正确
- [ ] 刊名/会议名完整
- [ ] 年、卷、期、页码齐全
- [ ] DOI 或原文链接可访问
- [ ] 标点符号规范
- [ ] 排序符合字母序
```
---