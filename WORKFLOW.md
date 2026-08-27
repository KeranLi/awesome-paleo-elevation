# Reading Workflow

这个项目的核心流程是“本地阅读，公开记录”。PDF 放在 `_downloads/`，不会提交到 GitHub；阅读后的知识结论进入 `papers.md`，需要展开时再写入 `notes/`。

## One Paper

1. **下载**：将 PDF 保存到 `_downloads/`，文件名建议为 `YEAR_FirstAuthor_short-title.pdf`。
2. **建条目**：在 `papers.md` 添加文章、地点、时代、方法；结论先写 `待阅读`，状态写 `to-read`。
3. **通读原文**：至少完成摘要、引言、方法、结果、讨论、图表和限制部分。不要只根据摘要填结论。
4. **提取证据**：记录样品/地点、时代约束、代理或模型、定量结果、不确定性、作者结论和替代解释。
5. **更新主表**：把 `待阅读` 改为自己的简洁结论，把状态改为 `reading` 或 `read`。
6. **写阅读卡片**：在 `notes/` 中记录关键证据、图表页码、术语和仍未解决的问题。
7. **提交同步**：检查 PDF 没有被 Git 跟踪，然后提交并推送：

   ```powershell
   git add papers.md notes WORKFLOW.md
   git commit -m "Add reading notes for <short topic>"
   git push
   ```

## Evidence Template

```markdown
## Reading record

- **PDF**：`_downloads/...pdf`
- **阅读日期**：YYYY-MM-DD
- **地点**：
- **时代**：
- **方法**：
- **关键证据**：样品、年龄、代理、校准或模型输入。
- **定量结果**：高程/抬升/古气候值及误差。
- **结论**：作者真正支持的结论。
- **限制与争议**：成岩、水汽路径、年代、空间代表性、模型假设等。
- **数据/代码**：DOI、仓库或补充材料链接。
```

## Status Meaning

- `to-read`：已入库但尚未完成阅读。
- `reading`：正在整理证据或图表。
- `read`：已通读并把结论和限制写入主表/阅读卡片。

## Three-Paper Starter Set

本地 `_downloads/` 中的三篇文章用于练习完整流程：

- Li et al. (2021), northern Tibet and vegetation — [reading card](notes/li2021_northern_tibet_vegetation.md)
- Li et al. (2022), Lunpola Basin — [reading card](notes/li2022_lunpola_review.md)
- Li et al. (2023), western Qaidam Basin — [reading card](notes/li2023_qaidam_paleoclimate.md)
