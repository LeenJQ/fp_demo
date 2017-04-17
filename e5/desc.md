# Thinking in Ramda: Pointfree Style

## Pointfree Style

在Part3，我们讨论了2个原则

* Put the data last
* Curry all the things

这2个原则衍生出 pointfree 风格， 我喜欢把它想成: "数据？什么数据？没有数据在这里。"

```javascript
const isEligibleToVote = person => both(isOver18, isCitizen)(person)
```
pointfree 后

```javascript
const isEligibleToVote = both(isOver18, isCitizen)
```

## Why

使用 pointfree 风格的好处如下：

* 使得程序更简单简洁
* 使得算法更加清晰
* 使得我们更加注重变化如何做，而不是数据如何改变
* 使得函数可以接受任意参数类型的模块
