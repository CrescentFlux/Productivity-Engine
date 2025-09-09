```dataview
TABLE 类型, 假设动机, 估算成本, 估算收益
FROM "5-Knowledge-Garden/ECR Lab"
WHERE contains(tags, "#entity")
SORT file.ctime DESC
```


# ECR Lab - 实体数据库

> 本数据库动态聚合所有被打上 `#ecr-entity` 标签的实体笔记。

## 实体概览
```dataview
TABLE 类型, 预估成本, 预估收益, 状态
FROM "5-Knowledge-Garden/ECR Lab"
WHERE contains(标签, "ecr-entity")
SORT 创建日期 DESC
```

## 按成本排序
```dataview
TABLE 预估成本, 类型
FROM "5-Knowledge-Garden/ECR Lab"
WHERE contains(标签, "ecr-entity") AND 预估成本
SORT 预估成本 DESC
```

## 按状态筛选
```dataview
LIST
FROM "5-Knowledge-Garden/ECR Lab"
WHERE contains(标签, "ecr-entity") AND 状态 = "待验证"
```