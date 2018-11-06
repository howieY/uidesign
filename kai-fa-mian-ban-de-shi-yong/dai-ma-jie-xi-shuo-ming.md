---
description: 按照 jsdoc 规范编写的注释，可以被编辑器解析，并在设计编辑面板中使用
---

# 代码解析说明

### 变量注释

支持 普通变量、数组变量、类 三种类型注释，示例如下：

```text
/**
 * @typedef App
 * @property {string} pkg 包名
 * @property {string} title 标题
 */

export default {
    private: {
        /**
         * 普通变量
         */
        normal: '',
        
        /**
         * 数组类型变量
         * @property {String} name 名称
         * @property {Boolean} hasMore 是否更多
         * @property {App[]} appList app列表
         */
         blockList: [{
           name: '',
           hasMore: false,
           appList: [{
             title: '',
             pkg: ''
           }]
         }]
    }
}
```

### 方法注释

```text
/**
 * 打开最近应用
 */
async openHistory(app) {
	const apps = await system.openApp(app)
	this.recentList = apps.slice(0, 12)

	Stats.appClick(Object.assign({from: APP_FROM.HISTORY}, app))
}
```

{% hint style="info" %}
在编写好注释后，切回到设计编辑面板，在属性绑定时即可选择对应的变量/方法。注释解析依赖本地的node环境，需要安装node.js。
{% endhint %}

