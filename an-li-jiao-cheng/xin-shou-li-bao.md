# 新手礼包

## **Weex编辑器第一次实战 -- 读书大礼包活动页**

### **从一下几个流程来总结这次实战：** 

1. 页面设计
2. 代码逻辑组织
3. 页面与代码绑定
4. 代码逻辑编写
5. weex代码调试以及项目发布

### **页面设计**

设计原型：这次页面主要是由交互在有视觉稿的情况下，拼凑出来的。

1. 按照交互稿的数据，能在设计面板上快速还原设计，简单的页面几分钟就能较好得还原视觉稿。
2.  不足：非开发人员拼凑出来的页面，往往不太规范，而且没有用上编辑器很好的功能组件以及指令。不规范的页面结构也增加二次开发的难度。

 补充：现在主要要修改的vue文件中的点

1. calss : flex: 1;一般同时会删除高度；animation动画的时候也要改class；页面元素居中:align-item
2. attrs：增加指令，目前只改ref,绑定字段的组合，可能v-if="initEnd&&activityEnd"形式    

### **代码逻辑组织**

代码逻辑组织主要是编写页面内所需的数据、所需绑定的方法等。开发人员在分析需求后，决定页面需要那些数据字段，或者需要绑定什么方法，然后在js文件内编写相关的字段以及方法，最重要的一步是，编写注释，详细的注释规则可以查看 xxx 。编辑器会通过解析注释来得知设计面板中每一个页面应有哪些可绑定的字段。如此一来，代码编写后的字段以及方法，可以提供给设计页面使用。    

### **页面与代码绑定**

页面与代码绑定，是编辑器很方便的功能。通过这个步骤，我们基本可以实现开发只需要编写业务代码，无需直接修改编辑器生成的vue文件。绑定字段后，在生成的代码里，有v-if，:class, :value, :src等可以绑定字段的动态属性    

### 

由于这次只是一个简单的活动页面，故代码写得有点粗糙。通过steam模块与服务端通信，通过createSdk提供的模块来合客户端通信，在createSdk不足以满足需求的时候，还可以让客户端同学自定义模块，实现weex页面与客户端的交互，至此基本就可以和各方面的数据进行通信了。    

### 

weex代码调试，可以和安卓调试一样，连接电脑，用adb工具进行调试，查看log。当然为了方便，也可以直接用modal模块来查看（效率虽然不高，但是很实用），项目发布就是走前端静态资源发布流程。公司没有专门发布前端资源的流程，要按照java服务端发布流程来走。gerrit上传代码，jekins构建，crp平台部署。
