# 效能仪表盘

> 本仪表盘用于追踪时间投入和个人效能，数据来源于每周手动录入。

## ⏳ 本周时间投资分布
```dataview
TABLE WITHOUT ID
	类型 AS "类别",
	round(sum(时长)) AS "总时长(hr)"
FROM "4-Intelligence-Dashboard"
WHERE contains(tags, "#time-log") AND date(日期) >= date(now) - dur(7 days)
GROUP BY 类型
SORT round(sum(时长)) DESC
```

## 📈 时间投资趋势 (过去4周)
```dataview
TABLE WITHOUT ID
	类型 AS "类别",
	round(sum(时长)) AS "总时长(hr)"
FROM "4-Intelligence-Dashboard"
WHERE contains(tags, "#time-log") AND date(日期) >= date(now) - dur(28 days)
GROUP BY 类型
SORT round(sum(时长)) DESC
```

## 🎯 项目时间投入TOP榜 (过去4周)
```dataview
TABLE WITHOUT ID
	项目 AS "项目",
	round(sum(时长)) AS "总耗时(hr)"
FROM "4-Intelligence-Dashboard"
WHERE contains(tags, "#time-log") AND date(日期) >= date(now) - dur(28 days)
GROUP BY 项目
SORT round(sum(时长)) DESC
LIMIT 5
```

---

## 📝 手动数据录入区 (每周日晚上填写)
| 日期         | 项目/任务    | 类型   | 时长(hr) | 认知收获(1-5) | 能量消耗(1-5) |
| :--------- | :------- | :--- | :----- | :-------- | :-------- |
| 2024-05-27 | 研究DCF模型  | 深度学习 | 2      | 5         | 3         |
| 2024-05-27 | 刷短视频     | 消费娱乐 | 0.5    | 1         | 1         |
| 2024-05-28 | 撰写金融科普文章 | 内容创造 | 3      | 4         | 2         |
**标签：** `#time-log` `#week-22`