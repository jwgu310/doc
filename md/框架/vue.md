
# vue介绍

## vue.js 是用来构建web应用接口的一个库

技术上，Vue.js 重点集中在MVVM模式的ViewModel层，它连接视图和数据绑定模型通过两种方式。实际的DOM操作和输出格式被抽象的方式到指令（Directives）和过滤器（Filters）

在哲学领域内,尽量让MVVM数据绑定API尽可能简单。模块化和可组合性也是重要的设计考虑。vue不是一个全面的框架,它被设计成简单的和灵活的。你可以用它快速原型,或混合和匹配与其他库定义前端堆栈。

Vue。js的API是参考了AngularJS、KnockoutJS Ractive.js Rivets.js。尽管有相似之处,我相信Vue.js提供一个有价值能够让你在现在的一些现有框架中舍取其价值

即使你已经熟悉其中的一些术语,建议您通过以下概念的概述,因为你的这些术语的概念可能在Vue.js的下文中有所不同

 

## 概念概述
### ViewModel

一个对象,同步模型和视图. 在Vue.js中,ViewModels是实例化的Vue的构造器或者是它的子类

var vm = new Vue({ /* options */ })
这是主要的对象,你会与作为开发人员在使用Vue.js交互。更多细节请参阅Class: Vue.

 

### View

用户看到的实际HTML / DOM

vm.$el // The View
当使用Vue.js时候，除了自己自定义的指令你几乎不会触碰到DOM的操作，当数据更新后视图的更新将会自动的触发，视图的更新可以很精确的到每一个testNode节点，他们也批处理和异步执行从而提供更好的性能。

 

### Model

这是一个略微修改的Javascript对象

vm.$data // The Model
在Vue.js中，模型只是简单的Javascript对象,数据对象,你能够操控他们的属性和视图模型，观察他们的从而能获取通知后更改。Vue.js在data对象胡总用ES5的 getter/setter 把属性转化了，它允许直接操作而不需要脏检查。

data对象在适当的时候会产生突变，所以修改它与通过引用修改vm.$data是一样的效果。这也方便了多个ViewModel实例观察同一块数据。

技术细节请看Instantiation Options: data.

 

### Directives

私有的HTML属性是告诉Vue.js做一些关于DOM的处理

    <div v-text="message"></div>
    这里的div元素有一个v-text的指令，值是message.意思是告诉Vue.js 保持这个div节点的内容与viewMode中的message属性同步

指令可以封装任意DOM操作。例如v-attr 操作一个属性元素,v-repeat克隆基于数组的一个元素，v-on附加事件监听，我们稍后讨论.

 

### Components

在Vue.js,一个组件是一个简单的视图模型构造函数，通过Vue.component(ID, constructor)注册。通过一个关联的ID，可以嵌套另外的视图模型的模板的v-component指令。这种简单的机制使声明视图模型的重用和组合方式类似于Web组件,而不需要最新的浏览器或重型polyfills。通过将应用程序分解成更小的组件,其结果是一个高度解耦和可维护的代码库。更多细节,请参阅Composing ViewModels.

