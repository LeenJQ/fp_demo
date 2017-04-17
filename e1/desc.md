#高阶函数

接受一个函数作为参数的函数

##函数作为参数

数组排序 sort

  [1,3,2,5,4].sort( (x, y) => x - y )

对象排序

```javascript
[{id:1, name:'one'},
 {id:3, name:'three'},
 {id:2, name:'two'},
 {id:5, name:'five'},  
 {id:4, name:'four'}].sort((x,y) => x.id - y.id)
 ```

##函数作为返回值

```javascript
var E = () => {}
var aliasFor = oldName => {
    var fn = newName => {
      E[newName] = E[oldName];
      return fn;
    };
    return (fn.is = fn.are = fn.and = fn);
};
```

# Curry
Abc(1,2) -> Abc(1)(2)

#函数组合
g(f(x)) -> (g·f)(x)

  f(x)        g(x)
| -----  |   ------ |
| ------------------|
        (g·f)


```javascript
    compose(sortBy(task=>task.id),   filter(task=>task.completed===true))(tasks)
```

##pipe

pipe(find, grep(porno))(/)


## Reducer
