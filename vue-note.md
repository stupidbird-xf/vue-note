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

1. v-if 操作dom

2. v-show 不操作dom ,只是display显隐 性能更优

> v-if v-else-if v-else

> 注：每个input都要加一个key属性，避免input被复用

#### vue中的列表渲染

1. 数组循环

> v-for="(item, index) in list"

> v-for="(item, index) of list"

> 注： 提升循环显示的性能，循环项上加唯一的key值 尽量不用index作为key值

2. 对象做循环

v-for="(item, key, index) of obj"

#### 修改数组

1. 改变数组中的引用


2. vue7种操作数组的方法

push pop shift unshift splice sort reverse

> template 模板占位符

作用：包裹元素，在循环的时候不会呗真正的渲染出来

3. vue中的set方法

> 改变对象中的值，可以通过实例的方法改变

 > vm.$set(vm.userInfo, 'address', 'beijing');

> 数组上的set方法 

 > vm.$set(vm.userInfo, 2, 'ceshi');

#### 组件使用的细节点

1. table中tbody里面不能直接加模板， 因为tbody里面不许是tr (例：select>option；ul>li；ol>li) is标签解决渲染中的bug2

	> 需要在tbody里面写<tr is="模板名称"></tr>

2. 子组件里面定义data必须是函数，要返回一个对象

> 原因子组件多次调用，让每一个子组件有独立的数据存储，不会互相影响，根组件调用一次

3. vue中操作dom 

 > ref 引用，<div ref="hello" @click="handleClick"> hello world</div>  this.$refs.hello取出（标签上引用：获取到的是标签对应的dom元素；组件上引用：获取的是组件的引用）

 4. 子组件中数据改变，怎么传到父组件上

  > 通过this.$emit('change'); 组件上写@change="父组件中的方法名"

#### 父子组件的数据传递

1. 父组件想子组件传递数据 (通过属性的形式)

> 子组件 <counter count="0"></counter>  :count="0(js表达式)" 传递过去是数字，不带":"传递过去是字符串
var counter = {
	props: ['count'],
	template: '<div>{{count}}</div>'
}

> 父组件 var vm = new Vue({
	el: '#root',
	components: {
		counter: counter
	}
})

注意： 父子间可以通过属性的形式传递参数给子组件，但是子组件不能修改父组件的数据

2. 子组件向父组件传递数据

> 

难点：
1. 调用导出excel接口的时候，由于文件过大，接口反应时间过长，最后失败，

> 解决：用浏览器打开新窗口

2. 写移动端的页面，固定定位的元素，滑动手机的时候，它与页面分离

> 在body里面包裹一层div,所有元素都写在div里面，不要直接写在body上

### this.$route.query.id 第一次是原类型，之后是字符串类型

#### 

> npm run build 构建

> 如果报错先执行 npm i 
