## Lodash
    - [Array](#Array)
    - [Collection](#Collection)
###  Array 
1. _chunk(array, [size=1]) :块。
``` 
    将一个数组分成多个size长度的块，并返回一个新的数组，如果这个数组不能被平均分，剩余的将作为一块。
    参数：1，(array)被处理数组；2，(number),每个快的长度。
    _.chunk(['a', 'b', 'c', 'd'], 2);
    => [['a', 'b'], ['c', 'd']]
    _.chunk(['a', 'b', 'c', 'd'], 3);
    => [['a', 'b', 'c'], ['d']]
```
2. _.compact(array) :压紧。
```
    返回一个非假的值，假的值，0,'',false,null,NAN,undefind.
```
3. _.difference(array, [values]) :删除指定/不确定。
```
    去掉array中values中的值(没有的除外)
    _.difference([1, 2, 3], [4, 2]);
    => [1, 3] 去掉2.
```
4. _.drop(array, [n=1]) :截取。
```
    截取掉n之前的元素返回剩余的(n默认为1，从1开始)。_.dropRight(array, [n=1]) 区别:从数组末尾开始
    参数
    1.array (Array): 被操作的数组。2.[n=1] (number): 去掉的元素个数。
    _.drop([1, 2, 3]);
    => [2, 3] 默认是1开始的
    _.drop([1, 2, 3], 2);
    => [3]
```
5. _.dropWhile(array, [predicate=_.identity], [thisArg]) 
```
    从左起第一个不满足条件的开始截取数组,返回截取后的数组[根据thisArg的值返回对应的值，以数组的格式]。
    参数
    1.array (Array): 需要查询的数组
    2.[predicate=_.identity] (Function|Object|string): 数组遍历的条件
    3.[thisArg] (*): 对应 predicate 属性的值.
    _.dropWhile([1, 2, 3], function(n) {
    return n < 3;
    });
    // => [3]
    var users = [
    { 'user': 'barney',  'active': false },
    { 'user': 'fred',    'active': false },
    { 'user': 'pebbles', 'active': true }
    ];
    // using the `_.matches` callback shorthand
    _.pluck(_.dropWhile(users, { 'user': 'barney', 'active': false }), 'user');
    // => ['fred', 'pebbles']

    // using the `_.matchesProperty` callback shorthand
    _.pluck(_.dropWhile(users, 'active', false), 'user');
    // => ['pebbles']

    // using the `_.property` callback shorthand
    _.pluck(_.dropWhile(users, 'active'), 'user');
    // => ['barney', 'fred', 'pebbles']
```
6. _.fill(array, value, [start=0], [end=array.length]) :替换。
```
   参数
    1.array (Array): 需要填充的数组.
    2.value (*): 填充 array 元素的值.
    3.[start=0] (number): 起始位置（包含）
    4.[end=array.length] (number): 结束位置（不含）
```

  