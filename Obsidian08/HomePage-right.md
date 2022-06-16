![[Group Copy@2x.png]]
Photo by [Spencer Davis](https://unsplash.com/@spencerdavis?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) on [Unsplash](https://unsplash.com/s/photos/big-sur?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)

----
## Daily
```dataview
	LIST From "Daily" sort file.mtime desc limit (5)
```

#### 最近修改
```dataview
	LIST WHERE file.mtime >= date(today) - dur(10 day) sort file.mtime desc limit (5)
```

## 稍后读
```dataviewjs
	dv.table(["Task","Name"],

		dv.pages("#稍后读").file.tasks

		.where(t => (!t.completed && t.text.indexOf("#稍后读")>0))

		.map(b => ["[ ] - " + b.text,b.link])

	)
```

## 闪念胶囊 Todo
```dataviewjs
	dv.table(["Task","Name"],
		dv.pages("#闪念胶囊").file.tasks
		.where(t => (!t.completed && t.text.indexOf("#闪念胶囊")>0))
		.map(b => ["[ ] - " + b.text,b.link])
	)
```
[[闪念胶囊|点击查看所有闪念胶囊>>]]

## podcast
```dataviewjs
	dv.table(["Name","Type","Create Time"],
		dv.pages("#PodCast and #waiting")
		.map(b => [b.file.link,b.type,b.file.ctime])
	)
```

## 其他未完成任务
```dataviewjs
	dv.table(["Task","Name"],
		dv.pages("-#闪念胶囊 and -#稍后读")
		.file.tasks.where(t => !t.completed)
		.limit(10)
		.map(b => ["[ ] - " + b.text,b.link])
	)
```

[[所有未完成任务|点击查看所有未完成>>]]

