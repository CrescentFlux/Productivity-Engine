# 执行中心看板

> 本笔记自动汇总所有执行相关的记录。

## 📅 每周复盘
```dataview
LIST
FROM "3-Execution-Loop"
WHERE contains(file.name, "Sprint-Planner") OR contains(file.name, "冲刺规划")
SORT file.ctime DESC
```

## 🗓️ 每日日志
```dataview
LIST
FROM "3-Execution-Loop"
WHERE contains(file.name, "Daily-Logbook") OR contains(file.name, "每日日志")
SORT file.ctime DESC
```

## 👥 人脉记录
```dataview
LIST
FROM "3-Execution-Loop"
WHERE contains(file.name, "Connection-Ledger") OR contains(file.name, "人脉账本")
SORT file.ctime DESC
```