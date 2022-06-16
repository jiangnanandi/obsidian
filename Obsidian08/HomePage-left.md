![[bernd-dittrich-fiXjuBOECs4-unsplash@2x.png]]
Photo by [Bernd Dittrich](https://unsplash.com/@hdbernd?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) on [Unsplash](https://unsplash.com/?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)

----
## 未完成 Blog
[点击进入频道](https://sspai.com/column/263)

```dataviewjs
	let pages = dv.pages("#Blog and -#Blog/Done");
	dv.table(
		["Name","genre"],
		pages.sort(b => b.file.mtime,"desc")
			.map(b => [b.file.link,b.genre])
	)
```

[[所有 Blog 相关|点击查看所有 Blog 相关>>]]


## 未完成摘录
```dataviewjs
	dv.table(["Name","author","publisher","Create Time"],
		dv.pages("#waiting")
		.where(b=> b.type=="Extracts")
		.sort(b => b.file.mtime,"desc")
		.map(b => [b.file.link,b.author,b.publisher,b.file.ctime]))
```



## 归档
```dataviewjs
	dv.table(["Name","Modified Date"],dv.pages("#Done")
		.sort(b => b.file.mtime,"desc")
		.map(b => [b.file.link,b.file.mtime])
		.limit(10)
	)
```
[[所有归档|点击查看所有归档>>]]