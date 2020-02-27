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

```

