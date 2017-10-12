---
title: Extjs Tree - 选中首节点
---
Extjs通常会要求在tree加载显示后，默认选中除去根节点（root节点）意外的第一个node，思路：1.添加TreeStore监听。 2.获取要选中的node。 3.获取selMode，调用select方法
<!--more-->
## 1. 添加TreeStore监听
``` js
var treeStore = Ext.create('Ext.data.TreeStore',{    //定义treeStore
	model : 'Model',   //数据model
	root : {
		id : '',
		text : '',
		type : 'ROOT'
	},
	autoLoad : true
});

treeStore.on('load',function(s, operator, eOpts){
	var rootNode = s.getRootNode();   //获取根节点
});
```

More info: [Writing](https://hexo.io/docs/writing.html)

### Run server

``` bash
$ hexo server
```

More info: [Server](https://hexo.io/docs/server.html)

### Generate static files

``` bash
$ hexo generate
```

More info: [Generating](https://hexo.io/docs/generating.html)

### Deploy to remote sites

``` bash
$ hexo deploy
```

More info: [Deployment](https://hexo.io/docs/deployment.html)
