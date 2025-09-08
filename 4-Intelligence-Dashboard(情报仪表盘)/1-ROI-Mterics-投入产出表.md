# 投入产出审计报告

> 本报告基于「效能仪表盘」的数据，定期评估时间投资的价值。

## 📊 核心资产ROI分析 (过去30天)
```dataview
TABLE WITHOUT ID
	类型 AS "领域",
	sum(时长) AS "总投入(hr)",
	round(avg(认知收获), 1) AS "平均认知收益",
	round(sum(时长) * avg(认知收获)) AS "总收益指数"
FROM "4-Intelligence-Dashboard"
WHERE contains(tags, "#time-log") AND date(日期) >= date(now) - dur(30 days)
GROUP BY 类型
SORT round(sum(时长) * avg(认知收获)) DESC
```

## ⚖️ 战略配比分析
**基于以上数据，你当前的“时间资产配置”如下：**
```dataview
TABLE WITHOUT ID
	类型 AS "资产类别",
	round((sum(时长) / (TOTAL)) * 100) AS "实际占比%"
FROM "4-Intelligence-Dashboard"
WHERE contains(tags, "#time-log") AND date(日期) >= date(now) - dur(30 days)
GROUP BY 类型
SORT round((sum(时长) / (TOTAL)) * 100) DESC
```

> **如何使用**：请手动将下方`手动录入区`的数据录入到`效能仪表盘`中，本报告即可自动生成。

## 🧭 战略调整建议 (基于数据)
1.  **高收益高投入领域**：
    -   `[领域名称]`：当前占比`[X]%`，收益指数`[Y]`。建议：**保持**。
2.  **高收益低投入领域** (被低估的宝石)：
    -   `[领域名称]`：当前仅占`[X]%`，但收益指数高达`[Y]`。建议：**下周将占比提升5%**。
3.  **低收益高投入领域** (需要优化或削减)：
    -   `[领域名称]`：当前占比`[X]%`，收益指数极低。建议：**设立上限**。

## 📈 行动指令 (Next Action)
-   [ ] 根据以上分析，调整下周时间分配计划。