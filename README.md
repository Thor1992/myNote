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
  语法：arr.slice([begin[, end]])
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


       
