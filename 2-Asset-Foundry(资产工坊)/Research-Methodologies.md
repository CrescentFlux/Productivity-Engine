# 研究方法库

> 本库定义并标准化所有研究流程，确保分析质量的可重复性。

## 方法清单
```dataview
TABLE 适用场景, 使用次数
FROM "5-Knowledge-Garden"
WHERE contains(tags, "#research-method")
SORT 使用次数 DESC
```

## ➕ 添加新方法
当你完成一次成功分析后，将其流程总结成一个新方法。
**模板**:
```markdown
# 方法名称 (如：经济模型审计法)
-   **适用场景**：需要快速判断一个商业模式的财务可行性时。
-   **核心步骤**：
    1.  估算LTV (用户终身价值)
    2.  估算CAC (用户获取成本)
    3.  计算LTV/CAC比值 (>3为健康)
    4.  分析现金流燃烧速率
-   **产出**：一份明确的「Go/No-Go」决策建议。
-   **标签**：`#research-method`
```