# PX-01 研究控制中心

> 本仪表盘集中管理所有研究问题，并将它们转化为可执行的任务。

## 所有问题状态总览
```dataview
TABLE 优先级, 状态, dateformat(file.cday, "yyyy年MM月dd日") AS "创建日期",投入时间
FROM "5-Knowledge-Garden(知识花园)/PX-01-Research/Research-Conrtol-Center.md(研究控制中心)"
WHERE contains(tags, "research-question")
SORT 优先级 DESC, status
```

## 本周研究焦点
```dataview
TASK
FROM "5-Knowledge-Garden(知识花园)/PX-01-Research"
WHERE !completed
GROUP BY file.link
```

```dataview
TABLE WITHOUT ID file.link AS "包含任务的文件"
FROM "5-Knowledge-Garden(知识花园)/PX-01-Research"
WHERE length(file.tasks) > 0
```




## ➕ 提出一个新问题？
1.  复制以下**绝对标准化**的模板：
```markdown
---
优先级: High/Medium/Low
状态: 未开始/调研中/阻塞/已解决
负责分析: [[]] <!-- 链接到具体分析模板，如[[Economic-Modeling]] -->
下一步行动: "" <!-- 必须是一个具体的、可执行的动作 -->
tags:
  - "research-question"
---

# 问题：[用一句清晰的话写出你的问题]

## 假设
-   假设1: ...
-   假设2: ...

## 验证路径
-   [ ] 任务1: [为验证假设1，需要做的第一件事]
-   [ ] 任务2: [需要做的第二件事]

## 结论
（完成后填写）
```































`

