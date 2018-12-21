---
title: JavaScript规范
date: 2018-12-21 15:01:46
tags: 
- JavaScript
- ReactNative
---

### 规范参考 [Google JavaScript Style Guide](https://google.github.io/styleguide/jsguide.html)

## 变量
{% codeblock lang:javascript %}
let phoneNum = '18761891111' // 局部变量使用let修饰
const phoneNum = '18761891111' // 局部常量使用const修饰
var phoneNum = '18761891111' // 杜绝使用var修饰变量
{% endcodeblock %}

## 字符串
{% codeblock lang:javascript %}
let name = 'Ladder' // 使用''而不是""
let str = `My name is ${name}` // 使用``插值拼接字符串

let str = 'My name is Ladder.' + // 不要使用\换行拼接字符串
          'I am four years old' 
{% endcodeblock %}

## 对象解构
{% codeblock lang:javascript %}
let data = undefined
let userInfo = data && data.userInfo // userInfo值为undefined
let userInfo = !!data && data.userInfo // userInfo值为false
let name = !!userInfo && userInfo.name // 在使用变量userInfo前 确保其存在
{% endcodeblock %}