# ECR Lab 经济模型库

> 库存放所有可复用的经济分析模型模板。

## 模型列表
```dataview
TABLE 应用场景, 复杂度
FROM "5-Knowledge-Garden"
WHERE contains(tags, "#economic-model")
SORT file.ctime DESC
```

## 添加新模型
当你创建一个新模型分析后（如下面的PX模板），将其总结成一个模板，打上 `#economic-model` 标签，它就会自动出现在这里。