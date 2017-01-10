# myNote

## 生成随机数
- 随机生成一个**0到1**的小数，代码为：
`Math.random()`

- 一个小数向下取整（取小于这个小数最近的整数）：
`Math.floor()`

- 生成一个**min到max(包含min和max)**之前的随机数：
`Math.floor(Math.random() * (max - min + 1)) + min`

##JS 方法使用
- slice() 方法会浅复制（shallow copy）数组的一部分到一个新的数组，并返回这个新数组。（不修改原数组）
  语法：
  > arr.slice([begin[, end]])
  参数说明：
  - begin
    从该索引处开始提取原数组中的元素（从 0 开始）。
    如果该参数为负数，则表示从原数组中的倒数第几个元素开始提取，slice(-2)表示提取原数组中的倒数第二个元素到最后一个元素（包含最后一个元素）。
    如果省略 begin，则 slice 从索引 0 开始。
  - end
    在该索引处结束提取原数组元素（从 0 开始）。slice会提取原数组中索引从 begin 到 end 的所有元素（包含 begin，但不包含 end）。
    
    slice(1,4) 提取原数组中的第二个元素开始直到第四个元素的所有元素 （索引为 1, 2, 3 的元素）。
    
    如果该参数为负数， 则它表示在原数组中的倒数第几个元素结束抽取。 slice(-2,-1)表示抽取了原数组中的倒数第二个元素到最后一个元素（不包含最后一个元素，也就是只有倒数第二个元素）。
    
    如果 end 被省略，则slice 会一直提取到原数组末尾。
  - 返回值：一个含有提取元素的新数组
  
  示例
  返回数组中的一部分
```
// Our good friend the citrus from fruits example
var fruits = ["Banana", "Orange", "Lemon", "Apple", "Mango"];
var citrus = fruits.slice(1, 3);

// puts --> ["Orange","Lemon"]
```
使用 slice

在下例中, slice从myCar中创建了一个新数组newCar. 两个数组都包含了一个myHonda对象的引用. 当myHonda的 color 属性改变为 purple, 则两个数组中的对应元素都会随之改变.
```
// 使用slice方法从myCar中创建一个newCar.
var myHonda = { color: "red", wheels: 4, engine: { cylinders: 4, size: 2.2 } };
var myCar = [myHonda, 2, "cherry condition", "purchased 1997"];
var newCar = myCar.slice(0, 2);

// 输出myCar, newCar,以及各自的myHonda对象引用的color属性.
print("myCar = " + myCar.toSource());
print("newCar = " + newCar.toSource());
print("myCar[0].color = " + myCar[0].color);
print("newCar[0].color = " + newCar[0].color);
```
---
- splice() 方法用新元素替换旧元素，以此修改数组的内容。

  语法:
> array.splice(start, deleteCount[, item1[, item2[, ...]]])

  参数
  - start​
    从数组的哪一位开始修改内容。如果超出了数组的长度，则从数组末尾开始添加内容；如果是负值，则表示从数组末位开始的第几位。
  - deleteCount
    整数，表示要移除的数组元素的个数。如果 deleteCount 是 0，则不移除元素。这种情况下，至少应添加一个新元素。如果 deleteCount 大于start 之后的元素的总数，则从 start 后面的元素都将被删除（含第 start 位）。
  - itemN
    要添加进数组的元素。如果不指定，则 splice() 只删除数组元素。
  - 返回值
    由被删除的元素组成的一个数组。如果只删除了一个元素，则返回只包含一个元素的数组。如果没有删除元素，则返回空数组。

  - 描述
    如果添加进数组的元素个数不等于被删除的元素个数，数组的长度会发生相应的改变。

  - 提示和注释
    注释：请注意，splice() 方法与 slice() 方法的作用是不同的，splice() 方法会直接对数组进行修改。
  
  使用 splice()
  如下代码演示了 splice 的用法：
```
var myFish = ["angel", "clown", "mandarin", "surgeon"];

//从第 2 位开始删除 0 个元素，插入 "drum"
var removed = myFish.splice(2, 0, "drum");
//运算后的 myFish:["angel", "clown", "drum", "mandarin", "surgeon"]
//被删除元素数组：[]，没有元素被删除

//从第 3 位开始删除 1 个元素
removed = myFish.splice(3, 1);
//运算后的myFish：["angel", "clown", "drum", "surgeon"]
//被删除元素数组：["mandarin"]

//从第 2 位开始删除 1 个元素，然后插入 "trumpet"
removed = myFish.splice(2, 1, "trumpet");
//运算后的myFish: ["angel", "clown", "trumpet", "surgeon"]
//被删除元素数组：["drum"]

//从第 0 位开始删除 2 个元素，然后插入 "parrot", "anemone" 和 "blue"
removed = myFish.splice(0, 2, "parrot", "anemone", "blue");
//运算后的myFish：["parrot", "anemone", "blue", "trumpet", "surgeon"]
//被删除元素的数组：["angel", "clown"]

//从第 3 位开始删除 2 个元素
removed = myFish.splice(3, Number.MAX_VALUE);
//运算后的myFish: ["parrot", "anemone", "blue"]
//被删除元素的数组：["trumpet", "surgeon"]
```       
***
给 JQuery 绑定事件：
在`script`标签中添加
`$("#getMessage").on("click", function(){});`


JSON 是 JavaScript Object Notation 的简写
