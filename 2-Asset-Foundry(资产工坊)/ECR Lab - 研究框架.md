# ECR Lab 研究框架

> 本框架定义了所有研究的通用流程和标准，确保分析质量的一致性。

## 研究流程
1.  **信息熵减**：创建实体数据库，对信息进行标准化、结构化。
2.  **多维建模**：强制使用至少2种不同的理论框架交叉验证分析。
3.  **假设锤炼**：主动寻找反证，挑战自己的初始假设。
4.  **成果固化**：输出可重用的模型或原理。

## 分析工具箱
```dataview
TABLE 应用阶段, 核心问题
FROM "5-Knowledge-Garden"
WHERE contains(tags, "#analysis-tool")
SORT file.ctime DESC
```

## 案例库
```dataview
LIST
FROM "2-Asset-Foundry"
WHERE contains(tags, "#ECR-Case")
SORT file.ctime DESC
```