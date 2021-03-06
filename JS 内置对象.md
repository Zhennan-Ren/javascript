# js常用对象总结

js中内置了17个对象,  
常用的是Array对象,Data对象,正则表达式对象,string对象,Global对象

### :one: Array对象中常用方法
1. **concat():** 表示把几个数组合并成一个数组  
2. **join():** 返回字符串值,其中包含了连接到一起的数组的所有元素,元素由指定的分隔符分隔开来
3. **pop():** 移除数组最后一个元素
4. **shift():** 移除数组中第一个元素
5. **slice(start,end):** 返回 数组中指定的一段元素
6. **push():** 往数组中添加一个元素,返回最新数组
7. **sort():** 对数组进行排序
8. **reverse():** 反转数组的排序
9. **toLocalString():** 返回当前系统时间
10. **length():** 表示取得当前数组长度

### :two: Global对象
Global对象是一个固有对象,目的是把所有的全局方法集中在一个对象中  
Global没有语法,直接调用其方法  
1. **escape()** 对string对象编码以便它能在所有计算机上可读  
    escape(charString) 必选项charString参数是要编码的任意String对象或文字
2. **isNaN()** 判断一个值是否是NaN
3. **parseInt** 返回由字符串得到的整数
### :three: 正则表达式对象
该对象包含正则表达式模式以及表明如何应用模式的标志  
1. 语法1: **re = /pattern/[flags]** 
2. 语法2: **re = new RegExp("pattern",["flags"])**  
  **re** 为将要赋值正则表达式模式的变量名  
  **pattern** 为正则表达式  
  **flags** 为标记:有如下3种:  
    g:全文查找  
    i:忽略大小写  
    m:多行查找  
 当预先知道查找字符串时用语法1,  
 当查找的字符串经常变动或不知道时用语法2,比如由用户输入得到的字符串

### :three: string对象
1. **chartAt():** 返回指定索引的位置的字符
2. **concat():** 返回字符串值,表示两个或多个字符串的链接
3. **match():** 使用正则表达式模式对字符串进行查找,并将包含查找结果为返回结果
```js
function MatchDemo(){ 
   var r, re;         // 声明变量。 
   var s = "The rain in Spain falls mainly in the plain"; 
   re = /ain/i;    // 创建正则表达式模式。 
   r = s.match(re);   // 尝试匹配搜索字符串。 
   return(r);         // 返回第一次出现 "ain" 的地方。 
} 
```
4. **replace(a,b):** 字符b替换字符a
5. **search(stringObject):** 指明是否存在响应的匹配,  
           如果找到一个匹配,search方法将返回一个整数值 指明这个匹配距离字符串开始位置的偏移位置,  
           如果没有找到匹配,则返回-1
6. **slice(start,end):** 返回字符串片段
7. **split():** 字符串拆分
8. **substr(start,length):** 字符串截取
9. **substring(start,eng):** 取得指定长度内的字符串
10. **toUpperCase():** 返回一个字符串,该字符串中的所有字母都被转化为大写字母
11. **toLowerCase():** 返回一个字符串,该字符串中的所有字母都被转化为小写字母
### :four: Math对象
1. **Math.min()** 取得字符串中的最小值  
2. **Math.max()** 取得字符串中的最大值
```js
d = Math.min(1,2,3,4);
console.log(d);

d = Math.max(2,3,4,5);
console.log(d);

var nums = [1,2,3,34,56,78];
d = Math.max.apply(Math, nums);
console.log(d);
```
3. **Math.ceil():** 向上取整
4. **Math.floor():** 向下取整
5. **Math.round():** 四舍五入
```js
alert(Math.ceil(25.1)); //26
alert(Math.floor(25.1)); //25
alert(Math.round(25.1)); //26
```
6. **Math.random():** 返回大于等于 0 小于 1 的一个随机数
```js
产生[0, 11]之间的数
num = Math.floor(Math.random()*12 + 0);

产生[2, 10]之间的数
num = Math.floor(Math.random()*9 + 2);
```
### :five: Date对象
要创建一个日期对象,使用new操作符和Date构造函数即可
```js
var d = new Date()
```
1. get/setDate()：返回或设置日期。
2. get/setFullYear():返回或设置年份，用四位数表示。
3. get/setYear():返回或设置年份。
4. get/setMonth():返回或设置月份。0为一月
5. get/setHours():返回或设置小时，24小时制
6. get/setMinutes():返回或设置分钟数。
7. get/setSeconds():返回或设置秒钟数。
8. get/setTime():返回或设置时间（毫秒为单位）
```js
console.log(d.getDate()); //获取日
console.log(d.getDay()); //获取星期
console.log(d.getMonth()); //获取月份，从0 开始
console.log(d.getFullYear()); //获取年份
```
#### Data 日期格式转换为字符串的方法
1. toDateString() ——以特定于实现的格式显示星期几、月、日和年;
2. toTimeString() ——以特定于实现的格式显示时、分、秒和时区;
3. toLocaleDateString() ——以特定于地区的格式显示星期几、月、日和年;
4. toLocaleTimeString() ——以特定于实现的格式显示时、分、秒;
5. toUTCString() ——以特定于实现的格式完整的 UTC 日期。  
   与 toLocaleString() 和 toString() 方法一样,以上这些字符串格式方法的输出也是因浏览器而异的,  
   因此没有哪一个方法能够用来在用户界面中显示一致的日期信息。
```js
console.log(d.toDateString());
console.log(d.toLocaleDateString());
console.log(d.toTimeString());
console.log(d.toLocaleTimeString());
console.log(d.toUTCString());
```
### :six: function 对象可以将函数作为对象访问,并可以在执行期间动态生成和调用函数
方法:   
    1. **apply():** 用于将一个对象中的方法应用到另一个对象   
    2. **call(this)/call(this,arg1,arg2):** 允许调用另一个函数的方法  
    3. **toString:** 用于将一个对象转换为字符串  
属性:  
   **arguments** 表示函数参数的数组  
   **caller** 表示调用当前正在执行的函数    
   **prototypt** 为对象添加新的属性和方法













