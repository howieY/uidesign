---
description: 当你在设计面板绑定接口数据时，发现js文件中的变量，在变量列表中。这么神奇的功能是如何做到的呢？
---

# js文件解析

### js的注释解析

我们通过jsdoc技术，对js文件进行注释解析，当我们解析到相关注释时，我们就把它生成对应页面的变量列表和事件列表，这样就可以在设计面板中直接绑定js中已经声明好的变量和事件了。

我们支持普通的变量和事件数据注释，以及对象化的数据注释，当然这一切的运行原理都是按照jsdoc的注释规范进行处理支持的

### js文件解析规则

可点击查看[参考文档](http://gitlab.meizu.com/wanghao/UIDesign/blob/electron-vue/doc/weex%20js%E6%96%87%E4%BB%B6%E8%A7%A3%E6%9E%90%E5%92%8C%E6%95%B0%E6%8D%AE%E7%BB%91%E5%AE%9A%E5%85%B3%E7%B3%BB%E7%BB%93%E6%9E%84%E8%AF%B4%E6%98%8E.md)

### 对象数据示例

```text
/**
 * @typedef Chart
 * @property {string} name 排行榜名称
 * @property {string} book_image0 第一个封面
 * @property {string} book_image1 第二个封面
 * @property {string} book_image2 第三个封面
 * @property {string} book_name3 第四个书名
 * @property {string} book_name4 第五个书名
 * @property {string} book_name5 第六个书名
 */
 
 /**
  * 排行榜
  * @type {Chart}
  */
 chart: {}
```



### 列表数据示例

```text
  /**
    * 列表数据
    * @property {string} user.nickname - 昵称
    * @property {string} user.avatar - 头像
    * @property {string} timeLabel - 时间
    * @property {string} title - 内容标题
    * @property {string} desc - 描述
    */
    listData: [],
```

{% hint style="info" %}
js 文件解析依赖全局的node环境，在使用该功能时需要在本地安装node.js 
{% endhint %}

