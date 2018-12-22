---
title: JavaScript规范
date: 2018-12-21 15:01:46
tags: 
- JavaScript
- ReactNative
---
## 遵守驼峰命名规则camelCase
{% codeblock lang:javascript %}
let phoneNumber = '18761891111' // good
let _phoneNumber = '18761891111' // ok
let PhoneNumber = '18761891111' // bad

onCallPhone() { // good 建议和用户交互关联的的函数以on前缀
  // todo
}

callPhone() { // ok
  // todo
}

CallPhone() { // bad
  // todo
}

{% endcodeblock %}

## 变量修饰符
{% codeblock lang:javascript %}
let phoneNum = '18761891111' // 局部变量使用let修饰
const phoneNum = '18761891111' // 局部常量使用const修饰
var phoneNum = '18761891111' // 杜绝使用var修饰变量 避免变量提升
{% endcodeblock %}

## 字符串
{% codeblock lang:javascript %}
let name = 'Ledder' // 用单引号'' 不用双引号""
let str = `My name is ${name}` // 使用``插值拼接字符串
let str = 'My name is Ledder.' + // 不要使用\换行拼接字符串
          'I am four years old' 

// 除了indexOf() ES6还提供了 startsWith()、endsWith()、includes()          
let str = 'Hello world!'
str.indexOf('Hello') !== -1 // true
str.startsWith('Hello') // true
str.endsWith('!') // true
str.includes('o') // true
{% endcodeblock %}

## 数组
{% codeblock lang:javascript %}
let cityNames = data.cityNames || []
if (cityNames && cityNames.length > 0) { // 务必对下标取值做越界保护
  let firstCityName = cityNames[0]
  // todo
}
{% endcodeblock %}

## 解构
{% codeblock lang:javascript %}
let data = undefined
let userInfo = data && data.userInfo // userInfo值为undefined
let userInfo = !!data && data.userInfo // userInfo值为false
let name = !!userInfo && userInfo.name // 在使用变量userInfo前 确保其存在

// good
let func({name, phone, mobile='1876189xxxx'}) { 
  // 对象解构放到函数形参中 语意简单直观且可以有解构默认值
}
// bad
let func(params) { // params里包含属性不甚明确
}
// bad 有默认值的形参应该放到最后
let func({name, phone='025888888', mobile}) {
}

import {a, b} from 'your-module' // 按需解构export内容

{% endcodeblock %}

## JSX中
{% codeblock lang:javascript %}
<View>
 {!!userInfo && !!userInfo.name && <Text>{serInfo.name}</Text>} // 使用双非!!

 [1,2,3].map((num) => { // 使用map()函数遍历数组
	<Text>{num}</Text>
 })
</View>

{% endcodeblock %}


## 样式StyleSheet
```
<View style={{flex:1,height:44,backgroundColor:'red'}}/>  // bad 尽可能不写内联样式
<View style={styles.container}/>  // good
```
## 推荐使用ES6箭头函数
 [ES6箭头函数 => 移步](http://es6.ruanyifeng.com/#docs/function)

### 参阅
 * [Google JavaScript Style Guide](https://google.github.io/styleguide/jsguide.html)
 * [菜鸟教程JavaScript代码规范](http://www.runoob.com/js/js-conventions.html)
 * [ES6标准](http://es6.ruanyifeng.com/#README)