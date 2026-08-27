# 主索引字段

`papers.csv` 使用 UTF-8 CSV；列表字段用分号分隔，DOI 是去重主键。

| 字段 | 含义 |
| --- | --- |
| `id` | 稳定的本地 ID，建议使用 `firstauthorYEAR_topic` |
| `year` | CrossRef 返回的出版年份；在线优先论文可能与卷期年份不同 |
| `title` / `authors` / `journal` / `doi` | 书目信息；作者字段按原顺序保留，`doi` 不带 `https://doi.org/` |
| `region` | 研究区或案例区；多个区域用分号分隔 |
| `proxy_or_method` | 代理、测年、模型或综合方法 |
| `evidence_type` | 该文在证据链中的角色，如 proxy calibration、regional reconstruction、method review |
| `priority` | `A`：直接服务古高程问题；`B`：重要扩展或区域案例；`F`：方法/历史基础 |
| `abstract_status` | `available`：接口返回摘要；`metadata-only`：只核验了书目信息，需阅读全文 |
| `metadata_source` | 当前为 CrossRef；后续可写 `CrossRef;Semantic Scholar` 等 |
| `last_checked` | 最近一次元数据核验日期（ISO 8601） |
| `notes_file` | 对应阅读卡片路径 |

## 去重规则

先将 DOI 小写化并去掉 `https://doi.org/` 前缀；无 DOI 的记录才使用“标题规范化 + 第一作者姓氏”作为后备键。合并不同来源时优先保留元数据更完整、出版社版本而非预印本的记录。

## 证据记录原则

- 把观测/代理、校准关系、年代约束、模型假设和最终高程估计分开记录。
- 明确标注成岩、非平衡分馏、湿度来源/再循环、空间代表性和年代对齐等误差项。
- 不能从摘要或元数据确认的数字、剖面和结论，写入“待阅读全文”，不作推断。
