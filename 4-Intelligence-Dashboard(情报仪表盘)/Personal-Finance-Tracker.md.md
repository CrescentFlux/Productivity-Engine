# 个人资金流分析仪表盘

## 📈 现金流概况 (过去30天)

```dataview

TABLE 类型, 金额, tags
FROM "4-Intelligence-Dashboard"
LIMIT 5
```
```


```


## 📈 现金流概况 (过去30天)
```dataview
TABLE WITHOUT ID
	"→ 总收入" AS 类别,
	sum(金额) AS 金额
FROM "4-Intelligence-Dashboard"
WHERE contains(tags, "#finance") AND 类型 = "收入"

TABLE WITHOUT ID
	"→ 总支出" AS 类别,
	sum(金额) AS 金额
FROM "4-Intelligence-Dashboard"
WHERE contains(tags, "#finance") AND 类型 = "支出"
```


# 个人资金流分析仪表盘

## 📈 现金流概况 (过去30天)
```dataview
TABLE WITHOUT ID
	"→ 总收入" AS 类别,
	sum(金额) AS 金额
FROM "4-Intelligence-Dashboard"
WHERE contains(tags, "#finance") AND 类型 = "收入" AND date(日期) >= date(now) - dur(30 days)
GROUP BY 类型

TABLE WITHOUT ID
	"→ 总支出" AS 类别,
	sum(金额) AS 金额
FROM "4-Intelligence-Dashboard"
WHERE contains(tags, "#finance") AND 类型 = "支出" AND date(日期) >= date(now) - dur(30 days)
GROUP BY 类型
```

## 💸 支出结构分析 (消费行为洞察)
```dataview
TABLE WITHOUT ID
	分类 AS "消费类别",
	sum(金额) AS "金额",
	round((sum(金额) / ({{支出总额}})) * 100) AS "占比%"
FROM "4-Intelligence-Dashboard"
WHERE contains(tags, "#finance") AND 类型 = "支出" AND date(日期) >= date(now) - dur(30 days)
GROUP BY 分类
SORT sum(金额) DESC
```

---

## 📝 手动记账区 (确保格式绝对统一!)
| 日期 | 项目 | 类型 | 分类 | 金额 | 支付方式 | 备注 |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 2024-05-28 | 购买电子书 | 支出 | 学习 | -59.00 | 支付宝 | 研究用 |
| 2024-05-28 | 公众号打赏 | 收入 | 内容创造 | +200.00 | 微信 | 《金融科普》文章 |
**标签：** `#finance`







## 🧐 复利问题清单 (驱动分析)
-   **最大现金流出项是什么？** (答案: `[[...]]`)
-   **哪些支出是「投资性支出」** (学习、工具、健康) **，哪些是「消耗性支出」？**
-   **我的「储蓄率」是多少？** `(总收入 - 总支出) / 总收入 = ...%`
-   **下月如何将更多资金从「消耗」转向「投资」？**

---

## 📝 手动记账区 (每日花5分钟)
| 日期 | 项目 | 类型 (收入/支出) | 分类 (学习/餐饮/社交/工具) | 金额 | 支付方式 | 备注 (Why?) |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 2024-05-28 | 购买《XXX》电子书 | 支出 | 学习 | -59.0 | 支付宝 | 为了研究PX项目 |
| 2024-05-28 | Obisidian插件捐赠 | 支出 | 工具 | -5.0 | PayPal | 支持开发者 |
| 2024-05-29 | 公众号打赏 | 收入 | 内容创造 | +200.0 | 微信 | 《金融科普》文章 |
**标签：** `#finance` `#2024-05`