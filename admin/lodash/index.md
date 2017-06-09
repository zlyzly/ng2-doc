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
### Collection 
1. _.every(collection,条件,thisArg)
```
    若所有元素通过谓词检查返回true，否则false.
```
2. _find(collection,条件,thisArg)，返回匹配的元素，否则undefined.
3. _findWhere(collection,source)
```
   1.collection （阵列|对象|字符串）：集合进行搜索。
   2.source （对象）：属性值的对象进行匹配。
    var users = [
   { 'user': 'barney', 'age': 36, 'active': true },
   { 'user': 'fred',   'age': 40, 'active': false }
   ];

   _.result(_.findWhere(users, { 'age': 36, 'active': true }), 'user');
   => 'barney'
```
4. _forEach(collection,每次迭代调用的函数,thisArg)
```
    _([1, 2]).forEach(function(n) {}).value();
    => logs each value from left to right and returns the array

    _.forEach({ 'a': 1, 'b': 2 }, function(n, key) {
    console.log(n, key);
    });
```
5. _.groupBy(collection, 每次迭代调用的函数, [thisArg]):组成聚合对象。
```
    _.groupBy([4.2, 6.1, 6.4], function(n) {
    return Math.floor(n);
    });
     => { '4': [4.2], '6': [6.1, 6.4] }

    _.groupBy([4.2, 6.1, 6.4], function(n) {
    return this.floor(n);
    }, Math);
     => { '4': [4.2], '6': [6.1, 6.4] }

    _.groupBy(['one', 'two', 'three'], 'length');
     => { '3': ['one', 'two'], '5': ['three'] }
```
6. _.includes(collection, target, [fromIndex=0]):匹配的元素被发现返回true,否则false.
```
    1.collection （阵列|对象|字符串）：集合进行搜索。
    2.target （*） ：这个值来搜索。
    3.[fromIndex=0] （数字）：从搜索的索引。
    _.includes([1, 2, 3], 1);
     => true

    _.includes([1, 2, 3], 1, 2);
     => false

    _.includes({ 'user': 'fred', 'age': 40 }, 'fred');
    => true

    _.includes('pebbles', 'eb');
     => true
```
7. _.reduce(collection, 迭代的调用的函数, [初始值], [thisArg])：返回累积的值。
``` 
    _.reduce([1, 2], function(total, n) {
    return total + n;
    });
    => 3

    _.reduce({ 'a': 1, 'b': 2 }, function(result, n, key) {
    result[key] = n * 3;
    return result;
    }, {}); => { 'a': 3, 'b': 6 }
```