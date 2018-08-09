# vue笔记整理

- - - - - - - - - 

#### 常用指令

> v-for 循环指令

> v-on 事件监听 v-on:click == @click

> v-model 双向数据绑定

> v-bind 绑定数据 v-bind:content == :content

#### 组件化

1. 父组件引用子组件

> component 注册全局组件的方法

	> Vue.component('item', {

		template: '<div>component</div>'

		});

> 通过标签的形式使用组件 
	
	> <item></item>

2. 父组件给子组件传递参数

> 子组件里面定义props对象， 里面声明变量

> 父组件定义一个变量

> 父组件标签里面 :子组件声明的变量 = 父组件的变量

3. 子组件向父组件传值

> this.$emit() 向外触发事件

4. 获取vm的实例方法

> vm.$

5. 销毁vue实例

> vm.$destroy()

6. vue的生命周期

> vue实例在某一个时间点会自动执行的函数

> beforeCreate 在Vue初始化之后执行

> created 初始化结束

> beforeMount 在页面渲染之前执行

> mounted 页面挂载之后执行

> beforeDestroy 当组件被销毁之前执行

> destroyed 当组件被销毁之后执行

> beforeUpdate 当数据发生改变没有渲染之前执行

> updated 当数据发生改变渲染之后执行

> activated 

> deactivated

> errorCaptured

> 注意：vue的生命周期函数并不放在methods里面，单独放在实例里 一共有11个生命周期函数

#### 模板语法

> {{ name }} 差值表达式

> v-text 

> v-html  
	
 > 注：后面都可以接js表达式

> #### 计算属性、方法、侦听器

###### 计算属性

> computed 计算属性，内置缓存机制，依赖的值不发生改变时，不会计算，依赖的值发生改变时，重新计算

1. 计算属性的setter和getter

> get方法获取值

> set方法设置值

###### 方法

> methods 页面重新渲染就发生改变

###### 监听器

> watch 同computed  语法较computed 复杂

> 注 三者可通用的时候选 computed 性能优化

#### 样式绑定

1. class的对象绑定

> :class="{activated: isActivated}"

> :class="[activated]" 数组里面是变量

2. style

> :style="styleObj"

> :style=[styleObj, {fontSize: '20px'}] 样式由数字里面的对象决定

#### vue的条件渲染

> v-if 操作dom

> v-show 不操作dom ,只是display显隐 性能更优





