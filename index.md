### js(学习三部分内容：ECMAScript+DOM+BOM)

###### helloworld

```html
 <script type="text/javascript">
alert("这是我的第一行代码,哥,你真的帅");//控制浏览器弹出一个警告框
document.write("你是真的帅");//向body中输出一个内容
console.log("hhhhhhh");//向控制台输出一个内容
    </script>
```

```html
  <!-- 将js代码写入标签的onclick属性中 -->
    <button onclick="alert('哈哈哈哈哈')">大帅逼</button>
    <!-- 将js代码写超链接的href属性中，点击超链接时，会执行js代码 -->
    <a href="javascript:alert('gun')">hhhhhhhh</a>

  <!-- 以上两种不推荐使用，不方便维护  最好写在script标签当中或者外部文件引用-->
  <!-- 新建一个js文件 在进行引入 <script type="text/javascript" src=".....js"></script> -->

```

==script标签一旦引入外部文件， 就不能够在编写代码，即使编写了浏览器也会忽略==

###### js的基本语法

js当中严格区分大小写

语句以分号结尾（如果不写分号，浏览器会自动添加，但是会消耗一些系统资源，但是有些时候会加错分号）

js忽略多个空格和换行

```js
//字面量和变量
字面量：不可改变的值（常量） 可以直接使用 但是一般不会直接使用字面量
变量可以用来保存字面量
使用var来声明一个变量;

//标识符:可以自主命名 数字 字母 下划线
不能是es中的关键字或者保留字
一般都采用驼峰命名 首字母小写 每个单词的开头字母大写 其余字母小写

//字符串
String Number Boolean Bull Undefined Object Js中的六种数据类型 其中Object属于引用数据类型
在js当中字符串需要使用单引号引起来 
使用双引号或单引号都可以
在字符串可以使用\作为转义字符

//数值类型（整数 浮点数）
js中可以表示数字的最大值（Number.MAX_VALUE）
如果使用number超过了最大数字 则返回Infinity 表示正无穷
NaN 表示的不是一个数字 ，类型返回的也是number 
js可以表示数字的最小值（Number.MIN_VALUE）
不要使用js进行对精确度比较高的运算
 //null和undefined
null这个值用于表示一个空的对象
当声明一个变量 但是并不给变量赋值时 他的值就是undefined（未定义）
```

###### 强制类型转换-String（转换成String类型）

```js
1.调用被转换数据类型的toString().方法 该方法不会影响原变量 它会将转换的结果返回
a=null;
a=a.toString();会报错
null和undefined没有toString方法
2.调用String()函数 将转换的数据作为参数传递给函数
使用String（）函数做强制类型转换时，对于null和undefined 它会将null转换为“null” undefined转换成“undefined”
```

###### 强制类型转换Number

```js
1.使用Number（）函数
（1）纯数字转换成字符串
（2）字符串中有非数字的内容 则转换成NaN
（3）空格的字符串 则为0
（4）布尔类型转数字 true-1 false-0
（5）Null转数字 则为0
（6）undefined转数字 则为NaN
2.专门用于对付字符串 parseInt() parseFloat()
parseInt() 将一个字符串中的有效的整数内容取出来 然后转换成Number
parseFloat() 将一个字符串的有效浮点数内容取出来 
如果对非String使用parseInt（）或者parseFloat（） 它会先转换成String然后在操作

在parseInt（）中传递两个参数 第二个参数表示进制
```

###### 强制类型转换Boolean（）

```js
使用Boolean（）函数
(1)非0数字调用函数Boolean()函数布尔值为true 除了0和NaN,其余的都是true
(2)字符串转布尔，除了空串 都是true
(3)NaN 和undefined都是false
(4)object也会转换成true

```

###### 算术运算符

```js
1.当对非Number类型的值进行运算时，会将这些值转换成Number然后在进行运算
任何值对NaN进行运算都是NaN
2.如果对多个字符串进行加法运算 则会将字符串进行拼接
任何的值和字符串做加法 都会先转换成字符串 在进行拼串的操作
3.将任意数据类转换成String的一个方法 我们只需要将任意数据类型+“” 是一种隐式的类型转换
例:var c=123; c=c+"";
4.任何值做减法 乘法 除法 都会自动转化成Number 
我们可以利用这一点 做隐式的转换 通过一个值-0 *1 /1 将其转换成Number
```

![image-20210809213828413](C:\Users\21906\AppData\Roaming\Typora\typora-user-images\image-20210809213828413.png)

###### 一元运算符（只需要一个操作数）

```js
1.正号：正号不会对数字产生任何影响
2.负号：负号对数字产生取反的操作 
3.对于非Number值 先转换成Number 在进行运算
可以对其他的一个数据类型用+ 将其转换成Number 和Number（）函数一样 隐式的类型转换
```

###### 逻辑运算符

```js
1. ！非：对非布尔值操作 会将其转换成布尔值 然后再进行取反 可以利用这一特点 将其他的值转换成布尔类型，对其进行两次取反2.&& 与3.|| 或对于非布尔值进行与或操作  会将其先转换成布尔值 然后在运算并且返回原值与运算：如果第一个值为true 则直接返回第二个值/如果第一个值为false 则直接返回第一个值或运算：如果第一个值为真 则直接返回第一个值/如果第一个值为false 则直接返回第二个值
```

###### 关系运算符（> < 等）

````js
对于非数值的情况，进行比较，会先将其转换成数字 然后在比较 1>"0"如果符号两侧的值都是字符串 不会将其转换数字进行比较 只会比较字符对应的unicode编码比较字符编码是一位一位进行比较，"abc"和"b" 如果两位一样 则比较下一位任何值和NaN进行比较 都是false 
````

在字符串中使用转义字符 \u  输入Unicode编码

在网页当中 使用unicode编码   &#编码 ； 这里的编码是十进制 可用电脑自带的计算器进行数值转换 

###### 相等运算符

```js
当使用== !=来比较两个值时，如果值的类型不同，会先转化成相同的类型，在进行比较 undefined衍生自null 所以undefined==null 为trueNaN不和任何值相等 包括它自己可以通过一个函数isNaN（）来判断一个值是否是NaN===:全等他不会进行类型转换 如果两个值类型不同 他直接返回false！==：不全等用来判断两个值是否不全等 如果两个值类型不同 他直接返回true
```

###### 条件运算符

```js
条件表达式？语句一:语句二;
```

![image-20210812165908808](C:\Users\21906\AppData\Roaming\Typora\typora-user-images\image-20210812165908808.png)



###### 流程控制语句if

```js
prompt()可以弹出一个提示框，该提示框中带有一个文本框，用户可以在文本框中输入一段内容，该函数需要一个字符串作为参数，该字符串用作提示的文字 该函数的返回值是String类型用户输入的内容会作为函数的返回值，可以定义一个变量来接收该内容
```

==需要注意的是js中的/操作符如果两侧是整数，它会当做浮点数进行运算，不会整除，它会保留小数==

==正确的取整方式需要借助parseInt()方法==（源自于水仙花案例）

break关键字用于退出swiitch或者循环语句，if当中不能单独使用，会立即终止离他最近的循环语句

可以为循环语句创建一个label，来表示当前的循环，这样break会结束指定的循环，而不是最近的循环

continue跳过当次的循环

```js
测试程序的性能在程序执行前，开启计时器console.time() 可以开启一个计时器 他需要一个字符串作为参数，这个字符串是计时器的标识console.timeEnd() 用来停止一个计时器
```

Math.sqrt()对一个数进行开方



##### 对象

读取的对象中没有的属性，不会报错，而是会返回undefined

delete 对象.属性名：可以用于删除一个属性

```js
向对象中添加属性不强制要求遵守标识符规范，什么都可以，但是尽量不要使用如果要使用特殊的属性名，需要使用以下方式对象["属性名"]=属性值，读取时也要采用这种方法使用[]去操作属性更为灵活，在[]中可以直接传递一个变量，可以直接读取这个属性var n="123";obj["123"]=789;console.log(obj[n])相当于console.log(obj["123"]) n可以随意修改 更为灵活 推荐使用对象的属性值，可以是任意的类型，甚至也可以是一个对象in运算符可以检查一个对象中是否有指定的属性 有则返回true 语法:"属性名" in 对象js中的变量都是保存在栈内存中的基本数据类型的值直接在栈内存中保存 ，值与值之间是独立存在的，修改一个变量不会影响其他变量的值对象是保存到堆内存中的，每创建一个对象，就会在堆内存中开辟出一个新的空间，对象保存的是内存地址（对象的引用） 对对象进行赋值，两个对象保存的是同一个对象的引用当比较两个基本数据类型的值时，就是比较值而比较两个引用数据类型值时，比较的是内存的地址，即使两个对象是一样的，但是地址不同，他也会返回false对象字面量:创建一个对象var a=new Object(); 与var a={};等价使用对象字面量，在创建对象时，直接指定对象中的属性语法:{属性名:属性值, 属性名:属性值.......}
```

```js
//函数，也是一个对象 var 变量名=new Function()封装到函数中的代码不会立即执行，函数中的代码会在函数调用的时候执行调用语法:函数对象()使用函数声明来创建一个函数function 函数名(形参)使用函数表达式来创建一个函数var 函数名=function(形参)----匿名函数对象调用函数解析器时它不会检查实参的类型，要注意是否可能接收到非法的参数调用函数是，也不会解析实参的数量，多余实参不会被赋值，实参少于形参的数量，则没有对应实参的形参是undefined函数名():调用函数函数名:函数对象函数的返回值可以是任意的类型，可以是对象，也可以是函数立即执行函数(function(){alert("我是一个匿名对象");})();  对象的属性值也可以是个函数，函数作为对象的属性时，称为对象的方法枚举对象中的属性for(var n in对象){} 每次执行，会将属性名赋值给变量nfor(var n in object){console.log("属性值"+obj[n]); //不能写成obj.n}
```

###### 作用域

```js
1.全局作用域：写在script标签中的js代码中，全局作用域在页面打开时创建，在页面关闭时销毁全局对象window，代表浏览器的窗口在全局作用域中，创建的所有变量都会作为window对象的属性保存创建的函数都会作为window的方法保存变量的声明提前:使用var关键声明的变量，会在所有代码执行之前被声明，但是如果声明变量不加var关键字，则变量不会被提前声明;函数的声明提前:使用函数声明创建的函数 function 函数名() 会在所有代码执行之前被创建fun2();var fun2=function(){console.log("  ");}//此代码执行会报错，变量fun2会被提前声明，但是没有赋值，不能在声明之前调用2.函数作用域调用函数时创建函数作用域，执行完毕后，函数作用域销毁，每调用一次函数就会创建一个新的函数作用域在函数作用域中，可以访问到全局作用域的变量;在全局作用域中无法访问到函数作用域当在函数作用域中操作一个变量，它会先在自身作用域中寻找，之后再寻找上一级作用域再函数作用域中，使用var关键字声明的变量，会在函数中所有代码执行之前被声明，函数声明也会在所有的代码执行之前被声明在函数中不使用var声明的变量 都会成为全局变量定义形参就相当于在函数作用域中声明了变量
```

this：浏览器在每次调用函数每次都会向函数内部传递进一个隐含的参数，这个隐含的参数就是this，this指向的是一个对象，根据函数的调用方式不同，this会指向不同的对象

==以函数形式调用，this永远都是window;以方法的形式调用，this就是调用方法的对象;==

```html
//使用工厂方法创建对象:大批量创建对象
```

![image-20210813221706985](C:\Users\21906\AppData\Roaming\Typora\typora-user-images\image-20210813221706985.png)

要区分多钟不同类型的对象，需要使用构造函数

```js
//创建一个构造函数构造函数和普通函数的区别，普通函数是直接调用，构造函数是使用new关键字来调用构造函数的执行流程:创建一个新的对象;将新建的对象设置为函数中的this,在构造函数中使用this来引用新建的对象执行函数的代码;将新建的对象作为返回值返回;使用instanceof 可以检查一个对象是否是一个类的实例 对象 instanceof 类如何使所有的对象共享同一个方法：如下图（将方法在全局作用域中定义）
```

![image-20210813223833125](C:\Users\21906\AppData\Roaming\Typora\typora-user-images\image-20210813223833125.png)

```js
将函数定义在全局作用域，污染全局作用域的命名空间，而且也不安全//原型对象 prototype我们所创建的每一个函数，解析器都会向函数中添加一个属性prototype,这个属性是一个对象当函数作为构造函数调用，它所创建的对象中都会有一个隐含的属性，指向该构造函数的原型对象
```

![image-20210813224623581](C:\Users\21906\AppData\Roaming\Typora\typora-user-images\image-20210813224623581.png)

```js
我们可以通过_proto_来访问该属性原型对象就相当于一个公共的区域，所有同一个类中的实例都可以访问到这个原型对象,我们可以将对象中共有的内容，统一设置到原型对象当中去；当我们访问对象的属性或者方法时，先在自身对象中寻找，如果有，则直接使用，没有的话找原型对象
```

![image-20210813225403183](C:\Users\21906\AppData\Roaming\Typora\typora-user-images\image-20210813225403183.png)

以后再创建函数时，可以将这些对象共有的属性和方法添加到构造函数的原型对象中，这样不用为每一个对象添加，也不会影响到全局作用域

```js
使用in检查对象中是否含有某个属性，如果对象中没有但是原型中有，也会返回true可以使用hasOwnProperty()检查对象自身的属性：只有对象自身有该属性才能返回true
```

![image-20210813230709182](C:\Users\21906\AppData\Roaming\Typora\typora-user-images\image-20210813230709182.png)





## toString()

![image-20210821105931535](C:\Users\21906\AppData\Roaming\Typora\typora-user-images\image-20210821105931535.png)

输出的结果是object Object ？为什么？

**当我们直接在页面中打印一个对象时，实际上输出的对象是toString()方法的返回值，console.log(per)和console.（per.toString()）是一致的**

**如果我们希望在输出对象时不输出object Object ,可以为对象添加一个toString()方法**

```js
//修改person原型的toSting()方法Person.prototype.toString()=function(){}//这样所有person的实例的toString()方法都跟着变化了
```

### 垃圾回收（GC）

就像人生活的时间长了会产生垃圾一样，程序运行也会产生垃圾，这些垃圾积攒过多，会导致程序运行速度变慢，所以我们需要一个垃圾回收机制，来处理程序运行产生的垃圾。

当一个对象没有任何变量或属性对他进行引用，此时我们无法操作该对象，此时这种对象就是垃圾，过多会导致占用大量内存空间，导致程序运行变慢，所以这种必须进行清理。在js中有自动的垃圾回收机制，会自动将这些垃圾对象从内存中销毁，我们不需要也不能进行垃圾回收的操作。

我们需要做的就是将不再使用的对象设置为null即可



## 数组

### 数组简介

1.数组也是一个对象，不同的是普通对象是使用字符串作为属性名的，而数组是使用数字来作为索引操作元素

索引是从0开始的数字

2.数组的存储性能比普通对象要好，在开发中经常使用数组才存储一些数据

```js
//语法如下：//1.创建数组对象var arr=new Array();//使用typeof检查数组时，会返回object//2.向数组中添加元素:数组[索引]=值arr[0]=10;//3.读取数组中的元素：如果读取不存在的索引返回undefinedarr[0],arr[1].....//4.获取数组长度：对于连续的数组，使用length属性获取数组长度;对于非连续的数组，使用length，返回最大索引+1，尽量不要创建非连续的数组arr.length//5.修改length:如果修改的length大于原长度，多出来的部分会空出来;如果修改的length小于原长度，多出来的部分会被删除//6.向数组的最后一个位置添加元素:即为length 语法如下：数组[数组.length]=值arr[arr.length]
```

### 数组字面量

1.使用字面量创建数组,可以在创建时就指定数组中的元素

```js
var arr=[1,2,3,4,5];
```

2.使用构造函数创建数组时，也可以添加元素，将要添加的元素作为构造函数的参数传递，元素之间用逗号隔开,较少使用

```js
var arr2=new Array(10,20,30);
```

3.创建一个数组中，只有一个元素10

```js
arr=[10];
```

4.创建一个长度为10的数组

```js
arr2=new Array(10);
```

5.数组中元素可以是任意的数据类型,也可以是对象,也可以是一个函数,也可以放数组

```js
arr=["hello",1,true,null];var obj={name:"孙悟空"}arr[arr.length]=obj;console.log(arr[4].name);//对象arr=[function(){alert("hello")},function(){alert("hello2")}];//函数
```

### 数组的方法

1.push():该方法用于向数组添加一个或多个元素，并**返回数组新的长度**，可以将这些元素作为方法的参数传递，这样这些元素将会自动添加到数组的末尾

```js
arr.push(elementary1,elementary2.....);
```

2.pop()该方法可以删除数组最后一个元素,将**删除的元素作为返回值**

```js
arr.pop();
```

3.unshift()：向数组开头添加一个或多个元素，并**返回新的长度**

```js
arr.unshift("牛魔王".....);
```

4.shift():删除并返回数组的第一个元素

```js
arr.shift();
```

### 数组的遍历

1.所谓的数组遍历，就是将数组中的所有元素都取出来

```js
for(var i=0;i<arr.length;i++){    console.log(arr[i]);}
```

练习：判断一数组Person对象是否大于18，将大于18的对象放到一个新的数组当中

```js
function getAdult(Arr){    var newArr=[];    //遍历arr,将Person对象取出来    for(var i=0;i<arr.length;i++){        var p=arr[i];        //判断是否大于18        if(p.age>=18){            //如果大于18，则将这个对象添加到newArr中            //将对象放入到新数组            newArr.push(p);                           }    }    return newArr;}
```

### forEach方法

1.这个方法只支持IE8以上的浏览器，该方法需要一个函数作为参数

```js
arr.forEach(function(){    console.log("hello");})//像这种函数，由我们创建，但是不由我们调用，我们称为回调函数，函数执行的次数为数组中元素的个数每次执行时，浏览器会将遍历到的元素，以实参的形式传递进来，我们可以定义形参来读取这些内容//浏览器会在回调函数中传递三个参数//第一个参数，就是正在遍历的元素//第二个参数，就是正在遍历元素的索引//第三个参数，就是我们正在遍历的数组
```

### slice()和splice()方法

1.slice()方法可以用来从数组中提取指定元素:**该方法不会改变原数组**，而是将截取到的元素封装到一个新数组中返回

```js
//语法arrayObject.slice(start,end);
```

参数：截取开始的位置的索引，包含开始索引；截取结束位置的索引，不包含结束索引

第二个参数省略不写，截取从开索引往后的所有元素；

如果传递一个负值，则从后往前计算。-1表示倒数第一个

2.splice()方法：用于删除数组中指定元素，**使用splice()会影响到原数组**，会将指定元素从原数组中删除

并将删除的元素作为返回值返回，**并向数组中添加新元素**

```js
arrayObject.splice(index,howmany,item1,.....,itemX)
```

参数：

第一个参数：表示开始位置索引

第二个参数：表示删除的数量，设置为0，不会删除

第三个参数：可选，传递一些新的元素，这些元素会自动插入到开始位置索引前边

###  数组去重练习

```js
//获取数组中的每一个元素for(var i=0;i<arr.length;i++){    //console.log(arr[i]);    //获取当前元素后的所有元素    for(var j=i+1;j<arr.length;j++){        if(arr[i]==arr[j]){            //出现重复元素，删除arr[j]            arr.splice(j,1);            //删除了当前j所在的元素之后，后边的元素会自动补位，此时将不会在比较这个元素，而我们需要在比较一次j所在的位置，正确的做法是是j自减            j--;           }}
```

### 数组的剩余方法

1.concat()方法用于连接两个或者多个数组，并将新的数组返回，该方法不会对原数组产生影响

```js
arrayObject.concat(arrayX,arrayX,......,arrayX)
```

2.join()方法可将数组转换成一个字符串，该方法不会对原数组产生影响，而是将转换后的字符串作为结果返回，在join()中可以指定一个字符串作为参数，这个字符串将会成为数组中元素的连接符

```js
arr=["1","2","3"];result=arr.join("hello");//hello为连接符
```

3.reverse()方法用于颠倒元素顺序，该方法会直接修改原数组

4.sort()方法用于数组元素进行排序，会影响原数组，默认按unicode编码排序

即使对于纯数字的数组，使用sort()进行排序，也会按照unicode编码来排序，所以对数字进行排序可能会的到错误的排序。

我们可以**自己来指定排序的规则**，在sort()中添加一个回调函数

* 回调函数中需要定义两个形参；

* 浏览器将会分别使用数组中的元素作为实参去调用回调函数，使用哪个元素不确定，但是肯定的是在数组	a一定在b前边；

* 浏览器会根据回调函数的返回值来决定元素的顺序，如果返回一个大于0的值，则元素会交换位置；如果返回一个小于0的值，则位置不变；如果返回0，则两个元素相等，也不交换位置

  ```js
  arr=[5,4,6,2,3];arr.sort(function(a,b){    /*if(a>b){        return 1;//前边的大交换位置    }    else if(a<b){        return -1;    }    else{        return 0;    }*/    return a-b;})//如果需要升序排列：则返回a-b;降序排列则返回b-a
  ```



### call()和apply()函数对象的方法

1.需要**通过函数对象来调用**

```js
function fun(){    alert("我是fun函数");}fun();fun.call();fun.apply();
```

2.在调用call和apply可以将一个对象指定为第一个参数，此时这个对象会成为函数执行时的this

```js
function fun(){    alert(this.name);}var obj={name:"1",sayName:function(){    alert(this.name);}};var obj2={name:"2"};fun.apply(obj2);obj.sayName.apply(obj2);
```

3.Call()方法可以将实参在对象之后依次传递

```js
function fun(a,,b){    console.log("a="+a);    console.log("b="+b);}fun.call(obj,2,3);//得到的结果 a=2 b=3
```

4.apply()方法需要将实参封装到一个数组中统一传递

```js
fun.apply(obj,[2,3]);
```

5.this的情况

以函数形式调用时，this是window；以方法形式调用，this是调方法的对象

以构造函数形式调用，this是新创建的那个对象；使用Call和appply调用时，this是指定的那个对象

### arguments

1.在调用函数时，浏览器每次都会传递两个隐含的参数

* 函数的上下文对象：this、
* 封装实参的对象arguments:他是一个类数组对象,可以通过索引来操作数据，也可以获取长度
* 在我们调用函数时，所传递的实参都会封装到arguments中，arguments.length可以用来获取实参的长度，即使不定义形参，也可以通过arguments来使用实参，但是较为麻烦
* arguments有一个属性叫做callee，这个属性对应一个函数对象，就是当前正在执行的函数对象

检查是否是数组：Array.isArray(arguments);

### Date对象

1.创建一个Date对象,如果直接使用Date对象，则会封装成当前代码执行的时间（Date是一个函数）

```js
var a=new Date();
```

2.创建一个指定的时间对象，需要在构造函数中传递一个指定的字符串作为参数

```js
var a=new Date("12/03/2013 11:02:03");//日期格式为月/日/年 时:分:秒
```

3.getDate()获取当前日期对象是几日

4.getDay()获取当前日期对象是周几，会返回0-6的值，0表示周日

5.getmMonth()获取当前对象的月份，返回0-11 ，0表示1月，依次类推

6.getFullYear()获取当前对象的年份

7.getTime()获取当前对象的时间戳：

* 时间戳指得是从格林威治标准时间的1970年1月1日0时0分0秒到现在日期所花时间的毫秒数

* 计算机底层在保存时间时使用的都是时间戳

  

8.获取当前的时间戳：可以用来测试代码执行的性能

```js
time=Date.now();
```

### Math对象

1.Math和其他对象不同，它不是一个构造函数，它属于一个工具类不用创建对象，里面封装了数学运算的属性和方法

```js
Math.PI表示π
```

2.abs()用来计算一个数的绝对值

3.ceil()可以对一个数进行向上取整，小数位有就自动进1

4.floor()可以对一个数进行向下取整，小数位会被舍弃

5.round()可以对一个数进行四舍五入取整

6.random()可以生成0-1之间的随机数

```js
//生成0-x之间的随机数Math.random()*x;//生成x-y之间的随机数Math.random()*(y-x)+x
```

7.max()可以获取多个数中的最大值，min()获取最小值

8.pow()：返回x的y次方

9.sqrt()：对一个数进行开方运算 

### 包装类

1.在js中提供了三个包装类，可以将三个基本数据类型转换成对象

```js
//String()将基本数据类型转换成String对象//Number()将基本数据类型转换成Number对象//Boolean()将基本数据类型转换成Boolean对象
```

2.在我们实际开发中不会使用基本数据类型的对象，如下所示

```js
var a=new String("hello");
```

3.对象转换成Boolean值都为true

```js
var b=new Boolean(false);if(b){    alert("我运行了");}//以上会弹出"我运行了"？为什么
```

4.方法和属性只能添加给对象，不能添加给基本数据类型

当我们对一些基本数据类型的值去调用属性和方法时，浏览器会临时调用包装类将其转换成对象，在调用对象的属性和方法，调用完后在将其转换成基本数据类型

```js
var s=123;s=s.toString();console.log("s");//123console.log(typeof s);//strings.hello="nihao";console.log(s.hello);//undefined? 第五行代码将s转换成对象1，第六行代码将s转换成对象2 这两个不是同一个对象
```

### 字符串的相关方法

1.字符串是以字符数组的形式保存的

```js
//length属性获取字符串长度
```

2.charAt():返回指定位置的字符，根据索引获取，从0开始

3.charCodeAt():返回指定位置字符的unicode编码

4.formCharCode():根据字符编码获取字符

```js
var a;a=String.fromCharAt(72);//H
```

5.concat():连接两个或多个字符串，不会对原字符串产生影响

6.indexof()检索一个字符串中是否含有指定内容，没有找到的话会返回-1，找到的话会返回第一次出现的位置

可以指定第二个参数，为开始查找的位置

7.lastIndexof()：也可以指定第二个参数

* indexof()是从前往后找
* lastIndexof()是从后往前找

8.slice()可以截取指定的内容，不会影响原字符串

* 第一个参数：开始位置的索引
* 第二个参数：结束位置的索引（不包括结束位置）
* 如果省略第二个参数，则会截取到后边所有的
* 也可以是一个负数作为参数，从后往前数

9.substring():截取字符串，和slice一样，但是不能接收负值作为参数，如果传递了一个负值，则默认使用0，而且还会自动调整参数的位置，如果第二个参数小于第一个参数，则会自动交换

10.sunstr():截取字符串

* 第一个参数:开始索引的位置
* 第二个参数:截取长度

11.**split()**:将一个字符串拆分成一个数组,参数为字符串，根据该参数来拆分数组

12.toUpperCase():将字符串转换成大写

13. toLowerCase():将字符串转换成小写

### 正则表达式

1.用于定义一些字符串的规则，计算机可以根据正则表达式，来检查一个字符串是否符合规则

2.创建正则表达式对象

```js
var reg=new RegExp("正则表达式","匹配模式");//语法//使用typeof检查正则对象，返回object
```

3.正则表达式的方法

```js
test():检查一个字符串是否符合正则表达式的规则，如果符合则返回truevar reg=new RegExp("a");//检查一个字符串中是否含有a,严格区分大小写var str="a";var result=reg.test(str);//true
```

3.在构造函数中传递第二个参数，匹配模式，可以是

* i:忽略大小写
* g:全局匹配模式

### 正则表达式的语法

1.使用字面量创建正则表达式:更加简单 ，使用构造函数更加灵活

```js
//语法：var 变量=/正则表达式/匹配模式reg=/a/i;
```

2.创建一个正则表达式，检查一个字符串中是否含有a或b

```js
reg=/a|b/;//使用|表示或者//[]里的内容也是或者的关系:[ab]=a|b
```

3.创建一个正则表达式，检查一个字符串中是否含有字母

```js
[a-z]:表示任意的小写字母[A-Z]:表示任意的大写字母[A-z]:表示任意字母[0-9]:表示任意数字[^ab]:找除了ab以外的[^0-9]:除了数字
```

4.检查一个字符串中是否含有abc或adc

```js
reg=/a[bd]c/;
```

### 字符串和正则相关的方法

1.split():将一个字符串拆分成一个数组

```js
//根据任意字母拆分字符串：方法中可以传递一个正则表达式去拆分var result=str.split(/[A-z]/);
```

2.search():搜索字符串中是否含有指定内容,如果搜索成功则返回第一次出现的索引，没有的话则返回-1

3.match():可以根据正则表达式从一个字符串中将符合条件的内容提取出来

* 默认情况下match只会找到第一个符合要求的，我们可以设置正则表达式为全局匹配模式，这样就会匹配所有内容；
* 可以为一个正则表达式设置多个匹配模式，且顺序无所谓
* match()会将匹配到的内容封装到一个数组中，即便只有一个查询结果

```js
 var result=str.match(/[A-z]/ig);
```

4.replace()将字符串指定内容替换成新的内容，默认只替换第一个

* 被替换的内容，可以接收正则表达式作为参数
* 新的内容

```js
var result=str.replace(/[A-z]/ig,"");//将字母删除
```

### 正则表达式的语法（1）

1.创建一个正则表达式，检查一个字符串中是否含有aaa

* 通过量词设置一个字符串出现的次数

```js
var reg=/a{3}/; //{n}出现n次
```

* 量词只对它的前边的一个内容有作用

  ```js
  reg =/ab{2}/;//表示的是检查abb 而不是ababreg =/(ab){2}/;//表示的是检查ababreg=/ab(1,3)/;//{m,n}表示m到n次 {m,}:表示m次以上reg=/ab+/;//+表示至少一个，相当于{1,,}reg=/ab*/;//*表示0或者多个，相当于{0,}reg=/ab?/;//表示0或者1个，相当于{0,1}
  ```

  

2.检查一个字符串是否以a开头

```js
reg=/^a/; //^表示开头reg=/a$/;//匹配结尾的areg=/^a$/;//只能是areg=/^a|a$/;//以a开头或者以a结尾
```

3.创建一个正则表达式，用来检查一个字符串是否是一个合法的手机号

手机号的规则：

* 11位
* 第一位是1；第二位不能是0,1,2；第三位以后是任意数字，但是长度为9

```js
var reg=/^1[3-9][0-9]{9}$/;
```

### 正则表达式的语法（2）

1.检查一个字符串中是否含有. 

**.表示任意字符,在正则表达式中使用\作为转义字符**

```js
var reg=/\./;//\.表示.   \\表示\
```

2.注意使用构造函数时，由于参数是字符串，而\是字符串转义字符，如果需要使用\，则需要使用\\\代替

```js
  var reg=/\\/;     reg=new RegExp("\\\\");//检查是否含有一个\     console.log(reg.test("\\"));
```

```js
reg=/\w/:表示任意字母 数字 下划线reg=/\W/;除了字母 数字 下划线reg=/\d/;任意数字reg=/\D/;除了数字reg=/\s/;空格reg=/\S/;除了空格
```

3.创建一个正则表达式检查一个字符串中是否含有单词child

```js
reg=/\bchild\b/;
```

4.接收一个用户的输入，去除字符串前后的空格，**去除空格就是采用""来替换空格**

```js
var str="    hello      ";str=str.replace(/\s/g,"");//去除字符串的所有空格str=str.replace(/^\s*/g,"");//去除前面的空格str=str.replace(/^\s*$/g,"");//去除后边的空格str=str.replace(/^\s*|\s*$/g,"");//去除字符串中前后的空格 或者/^\s+|\s+$/g
```

### 邮件的正则表达式

```js
hello .nihao @abc.com.cn
```

* 任意的字母 数字 下划线 .   任意的字母 数字 下划线  @ 任意字母数字 .任意字母（2-5位） .任意字母（2-5位

```js
/^\w{3,} (\.\w+)* @ [A-z0-9]+ (\.[A-z]{2,5}){1,2}$/
```

任意字母数字：[A-z0-9] 不能去除下划线 因为下划线的ASCII为95 在A-z之间



## 	DOM-全称文档对象模型

### 什么是DOM

1. 文档：表示的是整个html网页文档

2. 对象：将网页中的每一部分转换成了一个对象

3. 模型：表示对象之间的关系

4. 节点：html标签，属性，文本，注释，整个文档都一个节点（文档节点，元素节点，属性节点，文本节点）

   ``` js
   1.浏览器已经为我们提供了文档节点，这个对象就是Windows属性，可以在页面中直接使用，文档节点表示的是整个网页<button id="btn">我是一个按钮</button><script type="text/javascript">    //获取btn对象    var btn=document.getElementById("btn");	//修改按钮文字	btn.innerHTML="我是另一个按钮";</script>
   ```

### 事件(交互瞬间）

1.用户和浏览器之间的交互行为

``` js
//在事件对应的属性中设置一些js代码，这样在事件被触发时，这些代码会执行<button id="btn" onclick=alert("这是一个按钮") ></button>这种写法将事件写入html代码中，被称为行为和结构相耦合，不推荐使用//我们可以为按钮的事件绑定对应的处理事件，这种写法我们提倡1.获取按钮对象<script>    var btn=document.getElementById("btn");//绑定一个单击事件,单击响应函数btn.onclick=function(){    alert("66666");};</script>
```

### 文档的加载

1.浏览器加载页面的一个顺序

 按照自上向下的顺序加载的，读取·到一行运行一行，如果将script标签写到<head>内，页面还没有加载，是不能够运行成功的   ；将js代码写在页面的下部，就是为了可以在页面加载完毕后在执行js代码

``` html
<script>    alert("666");</script><body>    <button id="btn" onclick=alert("这是一个按钮") ></button></body>//我们希望alert在页面加载完之后在运行，如何实现
```

2.onload()会在页面加载完之后才触发

为window绑定一个onload事件，该事件对应的响应事件会在页面加载完成之后执行，这样可以确保我们的代码执行时所有的DOM对象都已经加载完毕了

``` html
<script>    window.onload=function(){        alert("666");    }</script><body>    <button id="btn" onclick=alert("这是一个按钮") ></button></body>//此时button按钮先出来，666在弹出来
```

### 	DOM查询（1）

1.获取元素节点

``` html
 <script>        window.onload = function(){            var btn=document.getElementById("btn01");            btn.onclick=function(){                var bj=document.getElementById("bj")                alert("我是北京");            };        };    </script><body>    <div><button id="btn01">        <ul>            <li id="bj"></li>        </ul>    </button></div></body></html>2.getElementSByTagName()可以根据标签名获取一组对象，这个方法会返回一个类数组对象，所有查询到的元素都会封装到对象中;即使查询到的只有一个，也会封装到一个数组中 <script>        window.onload = function(){            var btn02=document.getElementById("btn02");            btn02.onclick=function(){               var list=document.getElementByTagName("li");                console.log(list.length);                for(var i=0;i<list.length;i++){                    alert(list[i].innerHTML);                }            };        };    </script>3.getElementByName()根据name属性获取一组节点对象 <script>        window.onload = function(){            var btn03=document.getElementById("btn03");            btn03.onclick=function(){               var name=document.getElementByName("gender");                console.log(name.length);            }             for(var i=0;i<name.length;i++){                    alert(list[i].innerHTML);//innerHTML对于自结束标签，这个属性没有任何意义，返回为空                 //如果需要读取元素节点的属性，直接使用元素.属性名                 alert(name[i].value);                 alert(name[i].className);//class属性不能采用这种方式，需要使用className                }                      };    </script><body>    <div>        gender:<input type="radio" name="gender" value="male" class="hello">male        <input type="radio" name="gender" value="male">female    </div></body>
```

此处犯了一个致命的错误，再写css样式时，遇到;号就结束了

```html
/按钮实现切换图片/ <script>        window.onload = function () {            //获取两个按钮            var pre = document.getElementById("btn01");            var next = document.getElementById("btn02");            var img = document.getElementsByTagName("img")[0];            var imgArr = ["洗手1.png", "洗手2.png", "洗手3.png"];            //创建一个变量，来保存当前正在显示的图片的索引            var index = 0;                         var info = document.getElementById("info");            info.innerHTML ="一共"+imgArr.length+"张图片"+"当前第"+(index+1)+"张图片";            //为两个按钮绑定单击响应函数            pre.onclick = function () {                // img.src="洗手1.png";                index--;                if (index < 0) {                    index = imgArr.length - 1;                }                img.src = imgArr[index];                 info.innerHTML ="一共"+imgArr.length+"张图片"+"当前第"+(index+1)+"张图片";            };            next.onclick = function () {                // img.src="洗手2.png";                 index++;                if (index > imgArr.length - 1) {                    index = 0;                }                img.src = imgArr[index];                 info.innerHTML ="一共"+imgArr.length+"张图片"+"当前第"+(index+1)+"张图片";            };            //切换图片就是修改src属性        };    </script><body>    <div class="box">        <img src="洗手1.png" alt="">        <button id="btn01"> 上一张</button>        <button id="btn02"> 下一张</button>    </div></body>
```

### DOM查询（2）

1.获取元素的子节点（通过具体的元素节点调用）

``` html
childNodes属性会获取包括文本节点在内的所有  空白的内容也会当成文本节点，但是注意IE8以下不将空白内容当成节点返回children获取当前元素所有的子元素firstChild获取当前元素的第一个子节点（包括空白文本节点）firstElementChild获取当前元素的第一个子元素：不建议使用，兼容性较差，不支持IE8以下的浏览器
```

2.获取父节点和兄弟节点

``` html
1.返回元素的父节点：parentNode();2.innerText:与innerHTML类似，但是会自动将HTML去除3.previousSibling:前一个兄弟节点，也可能获取空白的文本4.previousElementSibling:获取前一个兄弟元素，不获取空白文本5.bj.firstChild.nodevalue:显示结果为北京<li id="bj">北京</li> 节点的三大属性：nodeName nodeType nodeValue
```

``` html
练习：全选练习关键点:遍历多选框的checked属性，并且设置为true|false 可以设置选中状态  <script>        window.onload = function(){                // 全选按钮                var btn=document.getElementById("checkAllBtn");            	var name=document.getElementsByName("item");                btn.onclick=function(){                                        // alert(name.length);                    // 遍历name数组                    for(var i=0;i<name.length;i++){                        name[i].checked=true;                    }                };        };    </script><body>    <form action="post">        你爱好的运动是？<input type="checkbox" id="checkAllBox" >全选 全不选                <input type="checkbox" name="item" value="足球">足球        <input type="checkbox" name="item" value="篮球">篮球        <input type="checkbox" name="item" value="排球">排球        <input type="button" id="checkAllBtn" value="全选"/>        <input type="button" id="checkNoBtn" value="全不选"/>        <input type="button" id="checkRevBtn" value="反选"/>        <input type="button" id="sendBtn" value="提交"/>    </form></body>练习：反选按钮<script> for(var i=0;i<name.length;i++){                        if(item[i].checked){                                 item[i].checked=false;                                 }                                   if(!item[i].checked){                                 item[i].checked=true;                                 }                                 //或者换种写法                                 item[i].checked=!item[i].checked;                    }                                 }</script>  在事件的响应函数中，响应函数是谁，判定的this就是谁
```

### DOM查询的剩余方法（3）

``` html
1.在document当中就有一个属性body,他就是body的引用var body=document.body;2.获取HTML标签 var html=document.documentElement;3.var all=document.all; //获取页面中的所有元素 尽量不要使用4.根据元素的class属性值获取一组对象:只支持ie9以及以上classNamevar box=document.getElementsByClassName("box01");5.document.querySelector(".box1 div");将选择器作为参数<div class="box1">        <div>        选择这个div    </div>    </div>虽然IE8中没有getElementClaSSName() 但是可以使用document.querySelector();使用该方法会返回唯一的一个元素，如果满足条件的有多个，那么他只会返回第一个6.document.querySelectorAll(".box"):会将符合条件的对象封装到数组中，即使符合条件的元素只有一个，他也会返回一个数组
```

### DOM增删改

1.createElement():可以用于创建一个元素节点对象，需要一个标签名作为参数

2.createTextNode()：创建一个文本节点对象 需要一个文本内容作为参数 根据该内容创建文本 返回新的节点

3.appendChild()：向一个父节点中添加一个子节点

4.insertBefore(新节点，旧节点）：向指定节点前插入新节点

5.replaceChild(新节点，旧节点）使用指定的子节点替换已有的子节点

6.removeChild()：删除子节点(父节点调用）

==以上父节点调用在没有获取父节点对象的时候，可以成采用bj.parentNode.removeChild();

 ```html
向一个父节点中添加一个子节点除了appendChild()方法还可以对最原始的innerHTML对象进行修改 city.innerHTML+="<li>beijing</li>";
 ```

==for 循环会在页面加载完毕完成之后立即执行，而相应的响应函数会在超链接被点击时才执行==

==，当响应函数执行时，for循环早已结束。此时的i值与For循环中的i值不是同一个==

``` html
练习：增删改查练习 <script>        window.onload = function() {            // 点击超链接删除信息            // 首先获取所有超链接信息            var ALLa=document.getElementsByTagName("a");                        // 每个超链接绑定事件            for(var i=0;i<ALLa.length;i++) {                ALLa[i].onclick=function(){                    // 在响应函数的最后取消超链接的跳转页面 通过return false                    var tr=this.parentNode.parentNode;                    var name=tr.getElementsByTagName("td")[0].innerHTML;                    // 或者var name=tr.children[0].innerHTML;                                      //confirm用于弹出一个带有确认消息的弹出框                    if(confirm("你确定删除"+name))                    {                        tr.parentNode.removeChild(tr);                    }                    return false;                }            }            var btn=document.getElementById("btn");            btn.onclick=function(){                //获取员工的名字                var name=document.getElementById("name").value;                // alert(name);                var dizhi=document.getElementById("dizhi").value;                var xinshui=document.getElementById("xinshui").value;                alert(name+","+dizhi+","+xinshui);                // 创建一个tr                var tr=document.createElement("tr");                tr.innerHTML="<td>"+name+"</td>"+"<td>"+dizhi+"</td>"+"<td>"+xinshui+"</td>"+"<td><a href='javascript:;'>"+"detele"+"</a>";                var  employee=document.getElementById("employee");                var tbody=employee.getElementsByTagName("tbody")[0];                tbody.appendChild(tr);            }        }    </script><body>    <table id="employee" border="1" cellspacing=""        <tr>            <td>name</td>            <td>dizhi</td>            <td>xinshui</td>            <th>&nbsp;</th>        </tr>        <tr>            <td>缪新勇</td>            <td>新建县</td>            <td>10000</td>            <td><a href="delete?id=01">delete</a></td>        </tr>        <tr>            <td>缪新亮</td>            <td>新建县</td>            <td>2000</td>            <td><a href="delete?id=02">delete</a></td>        </tr>        <tr>            <td>缪玉权</td>            <td>新建县</td>            <td>1000</td>            <td><a href="delete?id=03">delete</a></td>        </tr>    </table>    <div class="div">        <h4>添加新员工</h4>        <table>            <tr>                <td class="word">name:</td>                <td class="info"><input type="text" name="UserName" id="name"></td>            </tr>            <tr>                <td class="word">dizhi</td>                <td class="info"><input type="text" name="dizhi" id="dizhi"></td>            </tr>            <tr>                <td class="word">xinshui</td>                <td class="info"><input type="text" name="xinshui" id="xinshui"></td>            </tr>            <tr>                <!-- 提交按钮 -->              <td>                <button id="btn">提交</button>              </td>            </tr>        </table>    </div>    </table></body>
```

### 使用DOM来操作样式

1.通过JS来修改样式 

语法：元素.style.样式名=样式值

2.如果在CSS	样式名中含有- 这个在JS中是不合法的

```html
例如：box.style.background-color=""  这种写法是不合法的解决办法是将-去除 采用驼峰命名法 正确的样式名为backgroundColor
```

3.通过STYLE修改的属性为内联样式 优先级较高；但是如果在·样式中写了！important，则此时样式会有最高优先级，即使通过JS也不能覆盖样式

3.通过STYLE读取到的属性 都是内联样式 无法读取样式表中的属性

### 读取元素当前的样式

1.语法：元素.currentStyle.样式名=“”；==这个属性只有IE支持 但是不建议使用==

2.在其它浏览器中可以使用getComputedStyle(); 需要两个参数

1. 第一个参数：需要获取·样式的元素

2. 第二个参数：可以传递一个伪元素，也可以传递一个NULL

   

``` html
var obj=getComputedStyle(box1,null);//该方法会返回一个对象alert(obj.width);//可以通过对象.样式名来设置，IE8及以下不支持
```

### 其他样式操作的属性

1.*element*.clientHeight  *element*.clientWidth：返回可视内容的可视高度 宽度，包括内容区和内边距 ==这些属性是可读的 不可修改==

2.*element*.offsetHeight *element*.offsetWidth：返回元素整个的宽度和高度 包括内容 内边距和边框

3.*element*.offsetParent：可以获取当前元素的定位父元素 ==它会获取到离当前元素开启了定位 的最近的祖先元素，如果所有的祖先元素都没有开启定位，则返回body==

4.*element*.offsetLeft *element*.offsetTop：当前元素相对于定位元素的水平 垂直偏移量

5.*element*.scrollHeight *element*.scrollWidth：返回元素的宽度 高度（包括滚动区域）

6.*element*.scrollLeft ：获取水平滚动条滚动的一个距离

7.*element*.scrollTop：获取垂直滚动条滚动的一个距离

8.==一个等式：scrollHeight-scrollTop=clinetHeight== 说明垂直滚动条滚到底了

``` html
当垂直滚动条时使表单项可用 onscroll:该事件会在元素的滚动条滚动时出触发但是在谷歌浏览器中会有小数 滚动条拖到底时也不能触发事件 需要使用parsentInt进行取整scrollHeight-scrollTop+1>=clientHeight
```

### 事件对象

1.onmousemove:鼠标在元素中移动时触发

2.事件对象：当事件的响应函数被触发时，浏览器每次都会将事件对象作为实参传递给响应函数，在事件对象中封装了一系列的信息，包括鼠标的坐标

clientX clientY：返回事件被触发时，鼠标的水平，垂直坐标（不支持IE8以及以下）

==在IE8中，响应函数被触发时，浏览器不会传递事件对象，是将事件对象作为window对象的属性保存的==

event=event||window.event： 兼容所有的浏览器的写法

### div跟随鼠标移动

1.var left=even.pageX或者pageY 是鼠相对于页面的坐标偏移量，但是这两个属性不支持ie8

2.获取滚动条滚动的距离：chrom认为滚动条是body，可以根据document.body.scrollTop来获取；其他浏览器认为滚动条是html的，根据document.documentElement.scrollTop来获取

### 事件的冒泡

1.所谓的冒泡指的是事件的向上传导，当后代元素上的事件被触发时，其祖先元素的事件也会被触发

2.在实际开发中，冒泡是有实际用处的

3.如果不需要发生事件，可以取消冒泡事件

```html
event.cancleBubble=true; //所有浏览器都支持
```

### 事件的委派

1.我们希望只绑定一次事件，即可应用到多个元素上，即使元素是后添加的；我们可以将其绑定给元素共同的祖先元素

2.事件的委派：将事件统一绑定给元素的共同祖先元素，这样当后代元素的事件被触发时，会一直冒泡到祖先元素，从而通过祖先元素的响应函数来处理事件；利用了冒泡，减少事件绑定的次数，提高程序的性能

3.target：表示事件触发的对象，由谁来触发 

### 事件的绑定

1.使用对象.事件=函数的形式来绑定响应函数，他只能为一个元素的一个事件绑定一个响应函数，，不能绑定多个，如果绑定了多个，只有最后一个能生效

2.addEventListener():通过此方法为元素绑定响应函数

* 第一个参数：事件的字符串，不要on 例如：onclick变为click
* 第二个参数：回调函数，当事件触发时该函数会被调用
* 第三个参数：是否在捕获阶段触发事件，需要一个布尔值，一般为flase

在IE8中可以使用attachEvent（）绑定事件,==这个方法也可以同时为一个事件绑定多个处理函数，不同的是先绑定后执行，执行顺序与addEventListener()相反

* 第一个参数：事件的字符串，要on
* 第二个参数：回调函数，当事件触发时该函数会被调用

3.addEventListener（）中的this是指绑定事件的对象；attachEvent（）中的this是指window

### bind函数

1.定义一个函数，用来为指定元素绑定响应函数

参数：

* obj绑定事件的对象
* eventStr：事件的字符串
* callback回调函数

```js
function bind(obj,enentStr,callback){    if(obj.addEventListener){        //大部分浏览器兼容的方式        obj.addEventListener(eventStr,callback,false)    }    else{         obj.attachEvent("on"+eventStr,callback);            }}绑定事件的对象在调用bind函数时，addEvent和attach调用的this不一样，attach是window在调用this：以函数形式调用，this值的是window;以方法形式调用，值得是当前对象？？？如何统一obj.attchEvent("on"+eventStr,function(){    //在匿名对象中调用回函数    callback.call(obj);//当前对象自己调用})
```

### 事件的传播

1.微软公司：事件应该是由内向外传播的，先触发当前元素的事件，在向祖先元素传播，也就是在冒泡阶段执行；而网景公司相反

2.w3c综合了两个公司的方案

* 捕获阶段：从最外层的祖先元素，向目标元素进行事件的捕获，但是默认不会触发事件
* 目标阶段：事件捕获到目标元素，开始在目标元素上触发事件
* 冒泡阶段：事件从目标元素向祖先元素传递，依次触发祖先元素上的事件

==如果希望在捕获阶段就触发事件，可以将addEventListener()的第三个参数设置为true，一般情况下不使用==

IE8以及以下浏览器没有捕获阶段

==当使用一个元素的setCapture()方法以后，这个元素将会把下一次所有鼠标按下的相关的事件捕获到自身身上，setCapture（）这个方法只有IE支持，在Chrome中调用会报错==

### 事件的拖拽-练习

``` html
<style>        #box1 {            width: 100px;            height: 100px;            background-color: red;            position: absolute;        }        #box2 {            width: 100px;            height: 100px;            background-color: pink;            position: absolute;            left: 200px;            top: 200px;        }    </style>    <script>        window.onload = function () {            // 拖拽的流程            // 1.当鼠标按下拖拽元素时，开始拖拽            var box1 = document.getElementById("box1");            box1.onmousedown = function (event) {                //求出div的偏移量，鼠标.clientX-元素.offsetLeft;                var ol = event.clientX - box1.offsetLeft;                var ot = event.clientY - box1.offsetTop;                // alert("6666");                // 2.当鼠标移动时，元素跟着移动                // 为document绑定一个onmousemove事件                document.onmousemove = function (event) {                    event = event || window.event;                    var left = event.clientX - ol;                    var top = event.clientY - ot;                    box1.style.left = left + "px";                    box1.style.top = top + "px";                };                document.onmouseup = function () {                    // 3.当鼠标松开时。元素固定                    document.onmousemove = null;                    document.onmouseup = null;                };                //当我们拖拽一个网页中的内容时，浏览器会默认去搜索引擎中搜索内容，此时会导致拖拽功能的异常                //这个是浏览器的默认行为，如果不希望发生。则可以通过return false来取消                return false;            };        };    </script><body>    <div id="box1">    </div>    <div id="box2">    </div></body>
```

### 滚轮的事件

1.onwheel():该事件在鼠标滚轮在元素上下滚动时触发

2.wheelDelta():可以获取鼠标滚轮滚动的方向，向上滚数120，向下滚是-120，这个值我们不看大小，只看正负；这个属性火狐中不支持，在火狐中使用event.detail来获取滚动的方向，向上是-3 向下是3

3.当滚动条滚动时，如果浏览器有滚动条，滚动条会随之滚动；这是浏览器的默认行为，如果不希望，则可以取消默认行为，return false

4.使用addEventListener()方法绑定响应函数，取消默认行为时不能使用return false

需要使用preventDefa()方法；但是IE8不支持，如果直接调用会报错

### 键盘事件

1.onkeydown():按钮按下，如果一直按着不松手，事件会一直触发，当onkeydown连续触发时，第一次和第二次之间会间隔稍微长一些，其他的会非常的快；这种设计是为了防止误操作

2.onkeyup():按键松开

3.键盘事件一般会绑定给一些可以获取到焦点的对象或者是document

4.可以通过keyCode来获取按键的编码，通过他可以判哪个按键被按下

5.==在文本框中输入内容，属于onkeydown的默认行为，如果在onkeydown中取消了默认行为，则输入的内容不会出现在文本框中

### BOM---navigator

1.BOM：浏览器对象模型，可以通过JS来操作浏览器，在BOM中为我们提供了一组对象，用来完成浏览器的操作

2.window对象：整个浏览器的窗口，网页的全局对象

2.navigator对象：当前浏览器信息，通过该对象可以用来识别不同的浏览器(由于历史原因，navigator中的大部分属性都已经不能帮助我们识别浏览器的信息；一般只会使用userAgent来判断浏览器的信息，==userAgent是一个字符串，这个字符串包含有用来描述浏览器信息的内容，不同的浏览器会有不同的userAgent==)

* appName:
* 在IE11以及微软都已经将相关的表示去除了，所以不能通过userAgent来识别一个浏览器是否是IE了

3.location对象：当前浏览器的地址栏信息，通过location可以获取地址栏信息，或者操作浏览器跳转页面

4.history对象：代表浏览器的历史记录 通过该对象来操作浏览器的历史记录出于隐私保护，该对象不可以获取到具体的历史记录，只能操作浏览器向前或者向后翻页；而且该操作只在当次操作有效

5.screen对象：代表用户的屏幕信息，通过该对象可以获取用户的显示器的相关信息

==这些BOM对象都是作为window对象的属性保存的，可以通过window对象来使用，也可以直接使用==


### history对象

1.length属性可以获取到当前页面访问到的链接数量

2.back():退回至上一个页面

3.forward()：可以跳转至下一个页面

4.go():可以用来跳转至指定页面

* 他需要一个整数参数
* 1:表示跳转至一个页面
* 2:表示跳转至两个页面
* -1：表示向后跳转一个页面

### location对象

1.如果直接打印location：可以获取当前页面的完整路径

2.如果直接将location修改为一个完整的路径或相对路径，页面会跳转至指定页面

3.assign（）:跳转至其他页面

4.reload（）：重新加载当前页面 当我们传递一个true作为参数 时，会强制清楚缓存

5.replace():可以使用一个新的页面替换当前页面，不会生成历史记录，不能够利用back（）回退至上一个页面

### 定时器简介

1.如果希望一段程序每间隔一定时间运行一次，可以使用定时调用

``` html
setInterval():定时调用，每隔一段时间调用一次参数：1.回调函数2.调用间隔时间，单位为ms返回值：返回一个Number类型的数据，这个数字作为定时器的唯一标识var timer=......clearInterval(timer):可以用来关闭定时器，方法中需要一个定时器的标识作为参数；
```

==clearInterval（）可以接收任意一个参数，也可以是undefined，如果参数是一个有效的定时器标识，则停止对应的定时器，如果参数不是一个有效的标识，则说明也不做==

###### 切换图片练习-定时器

```html
  <script>        window.onload = function() {            var img1=document.getElementById("img1");            var btn1=document.getElementById("btn1");            var btn2=document.getElementById("btn2");            // 定义一个变量，用来保存定时器的标识            var timer;            //点击停止按钮以后，自动停止图片的轮放            btn2.onclick=function() {                clearInterval(timer);            }            var imgArr=["洗手1.png","洗手2.png","洗手3.png"];            //创建一个变量，来保存当前变量的索引            var index=0;            btn1.onclick=function() {                // 再开启定时器前，要关闭当前元素上的其他定时器                clearInterval(timer);                // 目前每点击一次按钮,就会开启一次定时器，点击多次的话会开启多个定时器，导致图片的切换速度过快，只能关闭最后一次的定时器                                //开启一个定时器来自动切换图片          timer= setInterval(function() {                index++;                img1.src=imgArr[index%imgArr.length];            },1000)        };            };                                            </script><body>    <img src="洗手1.png" alt="" id="img1">    <br/>    <button id="btn1">开始</button>   <button id="btn2">暂停</button></body>
```

### 延时调用

1.指的是函数隔一段时间执行，而且只会执行一次；而定时调用会执行多次

``` html
setTimeout(function(){},3000);
```

2.使用clearTimeout()来关闭一个延时调用

### 定时器的应用（1）

==parseInt() 将一个字符串中的有效的整数内容取出来 然后转换成Number==

```html
 <style>        *{            margin: 0;            padding: 0;                    }        #box1{            width: 100px;            height: 100px;            background-color: #ff0000;            position: absolute;            left: 0;        }    </style>    <script>        window.onload = function() {            var btn1=document.getElementById("btn1");            var box1=document.getElementById("box1");            var timer;//定义一个变量来保存定时器的标识            btn1.onclick=function() {                //关闭上一个定时器                clearInterval(timer);                // 开启一个定时器，用来执行动画效果               timer=  setInterval(function() {                    // 获取box1原来的left值                    var old=parseInt(getStyle(box1,"left"));                    // 在旧值的基础上增加                    var newValue=old+10;                    box1.style.left=newValue+"px";                    // alert(old);                },30)            };        };        //获取当前元素的任意的样式        function getStyle(obj,name) {            if(window.getComputedStyle){                return getComputedStyle(obj,null)[name];            }            else{                return obj.currentStyle[name];            }        }    </script><body>    <button id="btn1">点击按钮以后，box1向右移动</button>    <br>    <div id=box1>    </div></body>
```

### 定时器的应用（2）

抽离出一个执行简单动画的函数

``` html
 // 创建一个可以执行简单动画的函数            // 参数：            // 要执行动画的对象obj            //移动的速度speed  speed的正负值应该在函数内部考虑            //target:执行动画的目标位置（向左移动时判断newValue是否小于target）<script>            function move(obj, speed, target) {                clearInterval(timer);//避免在同一个元素上开启多个定时器                // 判断speed的正负                // 如果是从0往800走 则speed为正，反之为负                var current = parseInt(getStyle(obj, "left"));                if(current>target){                    speed=-speed;                }                // 开启一个定时器，用来执行动画效果                timer = setInterval(function () {                    // 获取box1原来的left值                    var old = parseInt(getStyle(obj, "left"));                    // 在旧值的基础上增加                    var newValue = old + speed;                    if ((newValue < target && speed < 0) || (speed > 0 && newValue > target)) {                        newValue = target;                    }                    obj.style.left = newValue + "px";                    if (newValue == target) {                        clearInterval(timer);                    }                    // alert(old);                }, 30)            };</script>
```

目前我们定时器的标识由timer保存，所有正在执行的定时器都在这个变量中保存

我们向执行动画的对象中添加一个timer属性，用来保存他自己的定时器的标识，obj.timer

 发现新大陆：callback&&callback()   有callback才执行对应的函数callback（）

### 轮播图练习
