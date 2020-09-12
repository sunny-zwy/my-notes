# js一些知识
## js基础知识
- 工具库  1   3
- 原声 js ECMASCRIPT ES3 ES5 ES6 ES..
- 严格区分大小写
- 基础知识
- 变量：存储数据的容器
- var ind=$('.list li').index()
- 声明 必须使用var声明变量 一般不能重复声明
- 赋值：   =

## js 命名规范：
1. 语义化 
2. 只能以字母 下划线 $ 开头 只能包含祖母下划线$
3. 不能以关键字和保留字命名(js语法用到的关键字 if var，要在下一个版本当做关键字的保留字)
4. 驼峰方式命名（多个单词组合）liIndex
5. js 里面所有命名都是上述规范
·
## js的赋值错误
1. 变量没赋值就console（undefined）
2. 没声明就console(num is not defined)
3. 声明提升，声明过程提升到最顶端 赋值过程不提升
     ```js
        console.log(num1)
        var num1=10   
        // (undefined)，声明提升
        ```
4. TypeError: Cannot read property 'grade' of undefined
    ```js
    var a=undefined
    a.grade
    // 不能设置undefined的grade属性，例子不好，马马虎虎看吧
    ```
## js 里的数据类型
1. Number
2. string 
3. boolean
4. undefined
5. null
6. object
7. symbol

## 数据类型之间的转换
1. 转换成数字
    - parseInt(值) (转成整型)
    - parseFloat(值) (转成浮点型 转换方式一个一个字符的转换，直到不能转换为止)
    - Number(值) (直接整体转换 转换失败得到NaN)
    ```js
    var str='15.6af'
    var int=parseInt(str)
    var float=parseFloat(str)
    var num=Number(str)
    console.log(int,float,num)
    //15,15.6,NaN
    //NaN(not a number) 不是一个数字的数字 数学计算出错
    ```
2. 转换成字符串
    - String(值)
    - 值.toString()
    ```js
    var num = 15.87
    var str = String(num)
    var str1 = num.toString()
    console.log(typeof str, typeof str1);
    // string string
    // 数据类型的检测:typeof
    ```
3. 转换成布尔值
    - Boolean(值)
    ```js
    var num = ''
    var bool = Boolean(num)
    console.log(bool)
    // false
    // false：0,'空',undefined，null，NaN
    // true：'空格'，数字
    ```
4. 隐士转换
    - if(判断条件)：和以上规则一样，其余都是true
    - '+' :左右只要出现字符，就会进行拼接操作
    - '- / * %'  ：这些符号左右的所有值都会默认转换成数字在进行数学运算 转换方法是Number
    ```js
    var a = '6'
    var b = '7a'
    console.log(a % 5, b * 5);
    // 1 , NaN
    ```
## 运算符
- '+  -  /  *  %'
- '>  <  ==  >=  <=  !=  ===  !=='
- ===和 == 区别:前者比较的是值和数据类型，后者只比较值
- 同上 != 和 !== 意思一样 1true, 0false
- ||  &&  !   (或  与  非)
- 以后所有的判断相等都使用 === 判断(老师要求)
```js
var num = 10
var str = '10'
console.log(num == str, num === str)
console.log(num != str, num !== str)
// true,  false
// false, true
```

# js 函数的知识
## 函数定义
- 装代码块的地方。  装功能的地方
- 形参：函数定义的时候设置参数
- 实参：调用的时候传递的参数
- 功能实现之后需要将运算的结果暴露到函数外面，需要设置函数的返回值
- 直接在函数的内部使用 return关键字将需要的值显示
- return 关键字有两个作用 1.返回值 2.跳出函数
- 函数的作用域分为两种：全局作用域、局部作用域（局部作用域和子作用域）
- 一个功能使用了两次及以上就需要将功能封装到函数内

## 函数创建
1. 函数式创建
    ```js
    function fun(){
        console.log('毕业见！！')
    }
    fun()
    ```
2. 变量式创建
    ```js
    var fun = function () {
      console.log('毕业见！！')
    }
    fun()
    ```
# js 对象
## 对象的基础知识
- 对象 object 属性的无序集合
- 属性名：属性值,...
- 方法：当属性的属性值是函数的时候称这个属性叫做方法

## 自定义对象
```js
var goods = {
    goodsName:'realme 5x',
    goodsPrice:3000,
    say:function(){
        console.log('我是新品')
    }
}
```
## 获取对象的属性
```js
// 对象.属性名 就是获取对象的属性值
console.log(goods)
console.log(goods.goodsName)
goods.say()
// 修改 直接对属性进行重新赋值
goods.goodsName='realme 6x'
goods.say = function(){
    console.log('我是最新品')
}
```
## 基础类型  复杂类型object
- 两者在浏览器内的存储方式不同
- 基础类型在浏览器中存储的就是值本身
- object 在浏览器中的存储的是地址,每次创建新对象的时候都会开辟一个新的地址存储
- object :自定义对象 内置对象(日期，数学，...)  浏览器对象(没懂！)

# 内置对象，数组
## 一些定义
- 数组：数据的有序集合
- 对数组进行全面的处理需要知道数组对象内的所有属性和方法
- 内置对象内的属性和方法都是定义好了的，绝对不能进行修改只能使用
- 数组 属性 length 获取数组的长度（元素个数）
- 学习方法的网址[mdn web](https://developer.mozilla.org/zh-CN/docs/Web/)

## 学习 ‘方法’
- 方法是哪个对象的（给谁用的）
- 方法的作用
- 返回值是什么
- 修不修改原来的对象

## 数组的方法
1. push:向数组末尾添加一个或多个元素，**返回新长度**, 原来的数组改变了
```js
var arr = [1, 2, 3]
var length = arr.push(5)
console.log(arr,length)
// [1,2,3,5] 4
```
2. pop 删除数组内的最后一个元素,**返回被删除的元素**,原来的数组改变了
```js
var num = arr.pop()
console.log(arr, num)
// [1,2,3] 5
```
3. unshift 向数组开头添加一个或多个元素，**返回新长度**,原来的数组改变了
```js
var length1 = arr.unshift(0, 1)
console.log(arr, length1)
// [0,1,1,2,3] 5
```
4. shift 删除数组内第一个元素,**返回被删除的元素**，原来的数组改变了
```js
var num1 = arr.shift()
console.log(arr, num1)
//[1,1,2,3] 0
//shift括号里填任何值都无用
```
5. concat  数组拼接**返回结果**,原数组不变
```js
var arr1 = [8, 9]
var arr2 = arr.concat(arr1)
console.log(arr, arr2)
//[1,1,2,3] [1,1,2,3,8,9]
```
6. splice 对数组的元素进行删除或添加，**返回被删除的元素组成的数组**，原来的数组改变了
```js
//arr.splice(a,b,c)  a添加或删除的开始位置   b 删除的个数   c 添加的元素
var newArr = arr.splice(0, 2, 9)
console.log(arr, newArr)
// [9,2,3]  [1,1]
```
7. slice 数组的截取,**返回截取的数组**，原数组不变
```js
//arr.slice(a,b)  a,b 代表的都是位置   原则包括 a 不包括 b
var newArr1 = arr.slice(0, 2)
console.log(arr, newArr1)
//[9,2,3] [9,2]
```
8. indexOf 查看数组内是否存在某个元素，**返回元素的位置 或 -1** ，原数组不变
```js
var ind = arr.indexOf(10)
var ind1 = arr.indexOf(3)
console.log(arr, ind, ind1)
//[9,2,3] -1  2 
```
9. includes 查看数组内是否存在某个元素返回 **true  false**，原数组不变
```js
var bool = arr.includes(8)
var bool1=arr.includes(9)
console.log(arr, bool,bool1)
//[9,2,3] false true
```
10. reverse 颠倒数组顺序并返回，原数组改变了
```js
var newArr2 = arr.reverse()
console.log(arr, newArr2)
//[3,2,9] [3,2,9]
```
11. join 将数组拼接成字符串并返回,原数组不变
```js
//arr.join('') 可加任何符号，都用来拼接
var str = arr.join() 
// 以逗号拼接， 3,2,9
var str=arr.join('')
//直接拼起来  329
var str=arr.join('--')
// 3--2--9
```
12. sort 对数组进行升序排序,**返回结果**，原数组改变
```js
var arr=[12, 4, 23, 564, 8, 41]
var newArr3 = arr.sort()
console.log(arr, newArr3)
//[12,23,4,41,564,8]
//按照字符串来进行升序排序
```
13. every 遍历数组每找到一个元素执行里面的函数 当所有函数的返回值都是 true 的时候  every 返回 true 否则返回 false
```js
var arr1 = [1, 2, 3, 4, 5]
var arr = arr1.every(function (ele, index, array) {
    return ele > 0
})
console.log(arr)
// true
```
14. find findIndex 方法返回数组中满足提供的测试函数的第一个元素的值。否则返回 undefined,有点类似 indexOf() 区别前者可以对对象类型数组进行查找后者不可以,
```js
var goods = goodsArr.find(function (ele, index, array) {
    return ele.goodsPrice > 1000
})
console.log(goods)
// find找到的是大于1000的对象
// findIndex找到的是大于1000的那个对象的索引
var a = [9, 2, 3]
var a1 = a.find(function (ele) {
    return ele > 2
})
console.log(a1);
// 9,返回满足条件的第一个值
// findIndex找到的是满足条件的值的索引,找不到返回 -1
```
15. map 映射，根据原数组生成一一对应的新数组
```js
var arr1=[1,2,5]
var arr2 = arr1.map(function (ele, index, array) {
    return ele * 2
})
console.log(arr2)
// [2,4,10]
// 函数内的返回值会被当作新的数组内的值
```
16. forEach 遍历数组每找到一个元素执行里面的函数,没有返回值，**返回undefined**
```js
var arr1 = [1, 2, 5]
arr1.forEach(function (item, index, array) {
    console.log(item)
})
// 1 2 5
// 大多情况用来遍历对象数组
```
17. filter 遍历数组每找到一个元素执行里面的函数当函数的返回值时 true 就被留下，**返回新数组**，原数组不变
```js
var newArr = arr1.filter(function (item) {
    return item > 1
})
console.log(newArr)
// [2,5] 返回新数组
```


## 真正的数字数组排序
```js
var currentArr = [12, 4, 23, 564, 8, 456, 78, 24]
var resArr = currentArr.sort(function (a, b) {
    return b - a  //降序
})
console.log(resArr)
//[564, 456, 78, 24, 23, 12, 8, 4]
```
## 对象数组内的数字排序
```js
var articleArr = [
      {
        title: 'react1',
        author: '小王1',
        likes: 200
      },
      {
        title: 'react2',
        author: '小王2',
        likes: 100
      },
      {
        title: 'react3',
        author: '小王3',
        likes: 150
      }
    ]

    var resArr1 = articleArr.sort(function (a, b) {
      return a.likes - b.likes
    })
    console.log(resArr1)
    //结果是按likes升序的对象数组
```
## 构造函数
```js
var cat = {
    name: 'xiaohua',
    age: 2,
    say: function () {
    console.log('喵喵')
    }
}
cat.say()
// 喵喵
```
## 数学函数
- Math.random() ， 0-1 的随机数，不包括 0 1
- Math.floor(3.94) ，3 下舍
- Math.ceil(3.1) ， 4 上进
- Math.round(4.5) ， 5 四舍五入

## 模板字符串，普通字符串拼接
```js
for (var i = 0; i < goodsArr.length; i++) {
      // 普通的字符串拼接
      var goodsDiv = $('<div                class="goods-wrap"><img src="' + goodsArr[i].goodsPic + '" /></div>')
      // 模板字符串
      var goodsDiv = $(`<div class="goods-wrap"><img src="${goodsArr[i].goodsPic}" /></div>`)
}
```
## 解除事件绑定
```js
$('.btn1').off('click');
// off方法，能单机但不管用
$('.btn1').attr('disabled', true)
// 不能单机，变灰色
```
## 内置对象 日期对象
- 创建 当前(页面读取这段代码的那个时间)日期对象，必须new一个date才能用后面的
- 将下面的所有方法加上 UTC 就是获取的世界时间（date.getUTCSeconds）
- 将下面的所有方法get 换成 set 就是设置时间(一般没用)
```js
var d=new Date()
date.setFullYear(2015)
console.log(date)
//此时年是2015年
```
```js
var date = new Date()
//Sun Aug 02 2020 21:42:00 GMT+0800 (中国标准时间)
var year = date.getFullYear()
//年
var month = date.getMonth() + 1
// 月 0-11
var hao = date.getDate()
//getDate  几号
var day = date.getDay()
//getDay 星期 1-0
var hour = date.getHours()
// 时 
var minute = date.getMinutes()
// 分
var second = date.getSeconds()
// 秒
var milliSecond = date.getMilliseconds()
// 毫秒
var times = date.getTime()
// getTime  格林威治时间 1970.1.1  00：00：00  距现在时间的毫秒数    用于创建一个永远不会重复的数
```
## setInteval 计时器
- setInteval jquery的动画方法属于异步
- 同步阻塞，异步非阻塞
- 异步操作永远会在同步操作之后执行
- 同步是按顺序往下执行
```js
var run = setInterval('update()', 1000);
var num = 0
function update() {
    num++
    if (num == 5) {
        //clearinteval只终止定时器不终止函数
        clearInterval(run)
        // return 想终止函数可以用return
    }
    console.log(num);
}
```
## setTimeout 
```js
//setTimeout 只执行一次，而色图Interval执行多次
function hello() {
    console.log("setTimeout");
}
//使用方法名字执行方法
var t1 = setTimeout(hello, 1000);
var t2 = window.setTimeout("hello()", 3000);//使用字符串执行方法
window.clearTimeout(t1);//清除定时器
```
## setTimeout 和 setInteval
```js
//两个一起用一般是用来倒计时的，最后显示0，再变成别的
var run = setInterval('update()', 1000);
var num = 5
function update() {
    num--
    $('.box').text(num);
    if (num == 0) {
        clearInterval(run)
        setTimeout(function () {
            $('.box').text('结束');
        }, 500)

    }
}
```
## filter 拆开的例子
```js
var arr = [1, 2, 3]
function fun1(ele) {
    return ele > 2
}
var arr1 = arr.filter(fun1)
console.log(arr1)
// [2,3]
```

## 正则表达式 

- 检测字符串的一个规则
- .test -->返回Boolean     .exec  -->返回Object 详细结果  null
- []一位  [0-9]一位数字  [a-z]一位小写字母   [A-Z]一位大写字母   [A-z]一位字母或下划线
- {} 在某一个字符后面加上{} 代表这个字符的位数    {n}   {n,m}   {n,}
- {0,1} ===  ?   {0,} ===   *    {1,} === +
- ^开头   $结尾
- | 或    ()先运算
- 正则内想要写一些原本正则里面有意义的字符 需要加上转义符 \

## 正则表达式的使用
```js
// .test -->返回Boolean     .exec  -->返回Object 详细结果  null
var re = /bai/
var str = 'hello xiaobai'
console.log(re.test(str))
// true 正则.test(变量)

var re = /[abc][def]h/
// 匹配三个连续的小写字母
var re1 = /[A-z0-9]/
// 匹配一位字母或下划线或数字
var re = /^a+$/
// 匹配以a开头和结尾的多个a
var re = /^[0-9]{3}@(qq|QQ).com$/
// 345@QQ.com 3个数字开头.com结尾
var re = /^1[3678][6789][0-9]{8}$/
// 第一位是1，第二位是3678，第三位是6789，第四到第11位是数字
```
## 正则的一些规则
字符串的长度`str.length`
- \d 等价于[0 - 9]  一位任意数字字符
- \D \d的反义 一位任意非数字字符
- \w 等价于[A - z] 一位任意字母数字下划线
- \W  \w 的反义
- \s 一位任意空白符(空格或者回车)
- \S  \s 的反义
- 中括号里面的 ^ (不好理解看下面例子)
```js
var re = /[abc]/  
//这个正则的意思是一位 a 或 b 或 c
var re1 = /[^abc]/ 
//这个正则的意思是一位非(a或b或c)的字符
var re2 = /[^0-9]/ 
//这个正则的意思是一位非数字的字符
```
## 字符串的方法
1. charAt 获取某个下标的字符
```js
var str = 'joijhadsa111111'
console.log(str.charAt(5))
// a
```
2. charCodeAt 获取某个下标的字符的字符编码
```js
var str = 'bajoijhads111111'
console.log(str.charCodeAt(1))
// 97
```
3.  replace 字符串替换，没有能替换的就不替换，replace默认只替换第一个，加个g都替换
```js
var str = 'ajoijhads111111'
var newStr = str.replace('joi', '')
var newStr1=str.replace('jo','55')
console.log(newStr,newStr1)
// ajhads111111  ajoijhads111111
var newStr2 = str.replace(/[a-z]/g, '5') 
// 把所有字母换成了5，加了 g 变成全局替换了
```
4. match 查看字符串是否满足某个条件返回满足条件的子字符串组成的数组,match也是只找第一个，要加g，i是不区分大小写
```js
// 今天天气不错,最高气温20℃，最低气温7℃。
var str = 'joia1111v11'
console.log(str.match(/[a-z]/g))
// ['j','o','i','a','v']
var str1 = '今天 17 号天气不错,最高气温-20℃，最低气温-7℃。'
// (?=xx) 后面紧跟着 xx
console.log(str1.match(/-?[0-9]{1,2}(?=℃)/g))
// ["-20", "-7"]
```
5. slice 字符串的截取
```js
var str = 'ajoijhads11111v1'
console.log(str.slice(0, 3))
// ajo
```
6. split 字符串拆分成数组,按照split的参数拆分，括号里什么都没有，就不拆分，括号里有''，就一个一个拆分
```js
var str2 = '1-2-345-6'
console.log(str2.split('-'))
// ["1", "2", "345", "6"]
```