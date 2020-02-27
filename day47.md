day47

### JScript

#### 1.Js引入方式

```
两种方式：
1.内部Javascript
2.外部Javascript
```

```html
	<head>
		<meta charset="utf-8">
		<title></title>
		<script type="text/javascript" src="js/index.js">
		</script>
<!-- 		<script type="text/javascript">
			// js代码
		</script> -->
	</head>
	<body>
<!-- 		<p id="class"	style="" onclick="console.log(2)">luwei
		</p> -->
		<p id="class" onclick="console.log(123)" >luwei</p>
	</body>
```

#### 2.递增和递减运算符

```
		<script type="text/javascript">
			var a=4;
			//先让a的值赋值给c，再对a++
			var c=a++
			console.log(c)
			console.log(a)
			//先对a++,再让a的值赋值给c
			// var c=++a;
			// console.log(c)
			// console.log(a)
		</script>
```

#### 3.拼接字符串

```
<script>
    var name = 'wusir', age = 28;
    var str = name + '今年是' + age + '岁了，快要结婚了，娶了个黑姑娘';
    console.log(str);
    //    es6的模板字符串 ``
    var str2 = `${name}今年是${age}岁了，快要结婚了，娶了个黑姑娘`;
    console.log(str2);
</script>
```

#### 4.数组

```
<script>
    var arr  = [1,'2','mjj'];
    //解释器 遇到var声明的变量 会把var声明的变量提升到全局作用域下
    var i;
    for(i = 0;i < arr.length;i++){
        console.log(arr[i]);
    }
    var c;
    function fn(){
        var d = 4;
    }
    console.log(i,c);
</script>
```

#### 5.流程控制



```
<script>
    var score = 100;
    if(score > 80){
       console.log('可以吃鸡了');
    }else if(条件){
        console.log('在家呆着');
    }else{};
    var weather = prompt('请输入今天的天气');
    switch (weather) {
        case '晴天':
            console.log('可以去打篮球');
            break;
        case '下雨':
            console.log('可以睡觉');
            break;
        default:
            console.log('学习');
            break;
    }
    var a = 2;
    var b = '2';
    console.log(a == b);//比较的是值
    console.log(a === b); //比较是值和数据类型
</script>
```

#### 6.循环

```
<script>
    var arr = [8,9,0];
    //1.初始化循环变量  2.循环条件  3.更新循环变量
    for(var i = 0;i < arr.length; i++){
        console.log(arr[i]);
    }

//    1到100之间的数
//     while

    var a = 1;
    while(a <= 100){
        console.log(a);
        a+=1;
    }
</script>
```

#### 7.函数

```
<script>
    function fn() {
        switch (arguments.length) {//判断实参个数
            case 2:
                console.log('2个参数')
                break;
            case 3:
                console.log('3个参数')
                break;
            default:
                break;
        }
    }
    fn(2, 3);
    fn(2, 3, 4)
</script>
```

#### 8.对象object



```
		<script type="text/javascript">
		//1.字面量创建方式
		var obj={};
		obj.name='luwei';//给对象添加内容
		obj.fav=function(){
			//obj
			console.log(this);
		};
		obj.fav();
		obj.name='weilu';
		console.log(obj.name);
		
		//构造函数
		var obj2=new Object();
		console.log(obj2);
		obj2.name='luweiweiwei';
		console.log(obj2.name);
		
		function add(x,y){
			console.log(this.name);
			console.log(x);
			console.log(y);
		};
		console.dir(add);//dir查看add属性和方法
		add();
		add.call(obj,1,2);//add.call()等于add(),但.call能改变this指向
		add.apply(obj,[1,2]);//类似call，传参使用[1,2]
		
		(function (){console.log(this)})();//匿名函数
		
		class person{
			constructor(name,age) {
			    //初始化
				this.name=name;
				this.age=age;
			};
			fav(){
				console.log(this.name);
			}
		};
		var p=new person('luweiiiii',18);
		p.fav();
		</script>
```

#### 9.数组的常用方法

##### 9.1**slice()方法**

```html
slice()方法，它能够基于当前数组中一个或多个项创建一个新数组。slice()方法可以接受一或两个参数，既要返回项的起始和结束位置。

一个参数的情况下，slice()方法会返回从该参数指定位置开始到当前数组默认的所有项
两个参数的情况下，该方法返回起始和结束位置之间的项——但不包括结束位置的项。

#@##注意： slice()方法不会影响原始数组

var colors = ['red','blue','green','yellow','purple'];
colors.slice(1);//["blue", "green", "yellow", "purple"]
colors.slice(1,4);// ["blue", "green", "yellow"]
```

```
如果slice()方法的参数中有一个负数，则用数组长度加上该数来确定响应的位置。例如，在一个包含5项的数组上调用slice(-2,-1)与调用slice(3,4)得到的结果相同。如果技术位置小于起始位置，则返回空数组

var colors = ['red','blue','green','yellow','purple'];
colors.slice(-2,-1);//["yellow"] 
colors.slice(-1,-2);//[]
```

##### 9.2**splice()方法**

```
splice()方法这个恐怕要算是最强大的数组的方法了，它有很多种用法。

splice()的主要用途是向数组的中路插入想。使用这种方法的方式则有3中。

1.删除：可以删除任意数量的项，只需指定2个参数：要删除的第一项的位置和要删除的个数。例如splice(0,2)会删除数组中的前两项
2.插入：可以向指定位置插入任意数量的项，只需提供3个参数：起始位置、0（要删除的个数）和要插入的项。如果要插入多个项，可以再传入第四、第五、以至任意多个项。例如，splice(2,0,'red','green')会从当前数组的位置2开始插入字符串'red'和'green'。
3.替换：可以向指定位置插入任意数量的项，且同时删除任意数量的项，只需指定 3 个参数:起始位置、要删除的项数和要插入的任意数量的项。插入的项数不必与删除的项数相等。例如，splice (2,1,"red","green")会删除当前数组位置 2 的项，然后再从位置 2 开始插入字符串"red"和"green"。
```

```
var colors = ["red", "green", "blue"];
var removed = colors.splice(0,1); 
alert(colors); // green,blue 
alert(removed); // red，返回的数组中只包含一项
removed = colors.splice(1, 0, "yellow", "orange"); 
alert(colors); // green,yellow,orange,blue alert(removed); // 返回的是一个空数组
removed = colors.splice(1, 1, "red", "purple"); 
alert(colors); // green,red,purple,orange,blue alert(removed); // yellow，返回的数组中只包含一项
```

##### 9.3**位置方法**

```
indexOf()和 lastIndexOf()。这两个方法都接收两个参数:要查找的项和(可选的)表示查找起点位置的索引。其中，indexOf()方法从数组的开头(位置 0)开始向后查找，lastIndexOf()方法则从数组的末尾开始向前查找。

这两个方法都返回要查找的那项在数组中的位置，或者在没找到的情况下返回-1。在比较第一个参数与数组中的每一项时，会使用全等操作符；也就是说，要求查找的项必须严格相等(就像使用===一样)。举个栗子：

			var numbers = [1,2,1,3,4,12,1,3,2,4,3,2,1];
			console.log(numbers.indexOf(4)); //3
			console.log(numbers.lastIndexOf(4));// 5
			console.log(numbers.indexOf(4,4));// 5 (需要找值，从哪个索引位置)
			console.log(numbers.lastIndexOf(4,5));//3(需要找值，从哪个索引位置)
```

#### 10.日期

```
<script>
    var date = new Date();
    console.log(date);
    console.log(date.getDate());
    console.log(date.getMonth()+1);
    console.log(date.getFullYear());
    console.log(date.getDay());
    console.log(date.getHours());
    console.log(date.getMinutes());
    console.log(date.getSeconds());

    console.log(date.toLocaleString());
    /*var weeks = ['星期天','星期一','星期二','星期三','星期四','星期五','星期六'];
    console.log(weeks[date.getDay()]);
    var day = weeks[date.getDay()];
    document.write(`<a href="#">${day}</a>`);*/

    var a =  1 < 2 ? "yes": "no";
    console.log(a);

</script>
```

#### 11.math对象

```
<script>
    var obj = {name:'mjj'};
    function add() {
        console.log(this.name);
    }
    // add();
    // add.call(obj);
    // add.apply(obj,[]);

    //求最大值和最小值
    var values = [1,2,36,23,43,3,41];
    var max = Math.max.apply(null,values);
    console.log(max);

    var a = 1.49999999;
    console.log(Math.ceil(a));//天花板函数
    console.log(Math.floor(a))//地板函数
    console.log(Math.round(a))//四舍五入

//    随机数
    console.log(Math.random());

//    min~  max
    //0.113131313
    function random(min,max) {
       return min+Math.floor(Math.random()*(max-min))
    }

    console.log(random(100, 400));

//    rgb(237,100,10)


</script>
```

