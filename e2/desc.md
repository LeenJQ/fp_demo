http://randycoulman.com/blog/2016/05/31/thinking-in-ramda-combining-functions/

# Complement
返回相反结果

```javascript
const isEven = x => x % 2 === 0

find(complement(isEven), [1, 2, 3, 4]) // --> 1
```

# BOTH/EITHER

&& / ||

```javascript
const isCitizen = either(wasBornInCountry, wasNaturalized)
const isEligibleToVote = both(isOver18, isCitizen)
```
## allPass, anyPass

# Pipelines

## 普通方法

```javascript
const multiply = (a, b) => a * b
const addOne = x => x + 1
const square = x => x * x

const operate = (x, y) => {
  const product = multiply(x, y)
  const incremented = addOne(product)
  const squared = square(incremented)

  return squared
}

operate(3, 4) // => ((3 * 4) + 1)^2 => (12 + 1)^2 => 13^2 => 169
```

## 使用pipe

```javascript
const operate = pipe(
  multiply,
  addOne,
  square
)
```

# COMPOSE

另一种方法

```javascript
const operate = compose(
  square,
  addOne,
  multiply
)
```
