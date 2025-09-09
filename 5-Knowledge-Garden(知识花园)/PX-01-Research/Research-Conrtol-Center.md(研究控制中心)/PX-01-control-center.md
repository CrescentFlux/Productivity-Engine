# PX-01 研究控制中心

> 本仪表盘集中管理所有研究问题，并将它们转化为可执行的任务。

## 所有问题状态总览
```dataview
TABLE 优先级, 状态, 负责分析, 下一步行动
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


## ➕ 如何提出一个新问题？
1.  在`PX-01-Research/`文件夹下创建新文件。
2.  复制以下**绝对标准化**的模板：

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

3.  保存后，它就会自动出现在上方的总览和任务列表中。


```dataview
TABLE file.name
FROM "PX-01-Research"
LIMIT 5
```

```dataview
TABLE file.name
FROM "5-Knowledge-Garden(知识花园)"
LIMIT 5
```

```dataview
TABLE file.name , file.folder
LIMIT 10
```


```dataview
TABLE file.name,file.folder
WHERE file.name="text1"
```

```dataview
TABLE file.name,file.folder
FROM #research-question 
```

```dataview
LIST tags
WHERE tags
LIMIT 20
```

```dataview
TASK
FROM "Research-Control-Center.md(研究控制中心)/PX-01-Research"
LIMIT 5
```
```dataview
TASK 
FROM #research-question 
LIMIT 10
```
```dataview
TASK
WHERE file.name = "text1"
```
```dataview
TASK
FROM "PX-01-Research"
LIMIT 10
```
```dataview
TABLE file.folder
FROM #research-question 
```
```dataview 
TABLE file.folder
WHERE file.name = "text1"
```
```dataview 
TASK 
FROM "5-Knowledge-Garden(知识花园)/PX-01-Research/Research-Conrtol-Center.md(研究控制中心)"
LIMIT 10
```
```dataview
TASK
WHERE file.path = "5-Knowledge-Garden(知识花园)/PX-01-Research/Research-Conrtol-Center.md(研究控制中心)"
AND contains(tags,"research-question")
```
```dataview
TASK
WHERE 状态 = "调研中"
LIMIT 5
```
```dataview
TASK 
WHERE 状态 = "调研中"
LIMIT 5
```
```dataview
TABLE 状态,优先级,tags
WHERE file.name = "text1"
```

```dataview
TASK
FROM #research-question 
SORT file.name
LIMIT 10
```

```dataview
TASK
FROM "5-Knowledge-Garden(知识花园)/PX-01-Research"
WHERE contains(tags,"research-question") AND 状态 = "调研中 "
SORT 优先级 DESC
```
```dataview
TASK
FROM "PX-01-Research"
WHERE contains(tags,"research-question")AND 状态 = "调研中"
SORT 优先级 DESC
```
```dataview
TASK
TABLE "PX-01-Research"
WHERE contains(tags,"research-question")
```

```dataview
TASK
FROM "PX-01-Research-question"
WHERE contains(tags,"research-question")
```
```dataview
TABLE 优先级,状态,下一步行动
FROM "PX-01-Research"
WHERE contains(tags,"research-question")
```
```dataview
TABLE tags
FROM "PX-01-Research"
LIMIT 5
```
```dataview
TASK
FROM "PX-01-Research"
LIMIT 5
```
```dataview
TABLE 优先级,状态,下一步行动
FROM "5-Knowledge-Garden(知识花园)/PX-01-Research"
WHERE contains(properties.tags,"research-question")
```
```dataview
TABLE file.ctime,优先级,下一步行动,tags
FROM "5-Knowledge-Garden(知识花园)/PX-01-Research"
WHERE 状态 = "调研中"
```

```dataview 
TABLE 状态,下一步行动,tags
FROM "5-Knowledge-Garden(知识花园)/PX-01-Research"
WHERE 优先级 = "High"
```
```dataview
TABLE WITHOUT ID
    file.link AS "文件夹",
    优先级 AS "优先级",
    状态 AS "状态",
    下一步行动 AS "下一步行动",
    tags AS "标签"
    
FROM "5-Knowledge-Garden(知识花园)/PX-01-Research"
WHERE 优先级
SORT 优先级 DESC,file.ctime DESC
```
