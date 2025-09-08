# 我的卡片盒总索引

> 本笔记是卡片盒中所有想法的高阶导航中心，通过自动查询生成。

## 🔥 最新想法
```dataview
LIST
FROM "6-Zettelkasten(卡片盒子)"
SORT file.ctime DESC
LIMIT 10
```

## 🧠 按主题浏览
> 以下是我最常思考的几个核心主题，点击查看相关笔记。

### [[关于 Obsidian 的使用]]
```dataview
LIST
FROM "6-Zettelkasten(卡片盒子)"
WHERE contains(file.name, "Obsidian") OR contains(file.name, "ob")
```

### [[关于 知识管理]]
```dataview
LIST
FROM "6-Zettelkasten(卡片盒子)"
WHERE contains(file.name, "知识") OR contains(file.name, "管理")
```

## 📥 待处理 inbox
```dataview
LIST
FROM "6-Zettelkasten(卡片盒子)"
WHERE contains(tags, "inbox")
```

## 🔍 全量列表（按时间倒序）
```dataview
TABLE file.ctime AS "创建时间"
FROM "6-Zettelkasten(卡片盒子)"
SORT file.ctime DESC
```