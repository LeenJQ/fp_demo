# Thinking in Ramda: Declarative Programming

http://randycoulman.com/blog/2016/06/14/thinking-in-ramda-declarative-programming/

## Imperative vs Declarative

## Declarative Replacements

multiply
add
inc: 等价 add(1)
equals ===
gt >  |  gte >=
lt <  | lte <=


## Logic

complement !
both &&
either ||

const lineWidth = defaultTo(80, settings.lineWidth)


## 条件语句

### IFElse

```javascript
const forever21 = age => ifElse(lt(21), () => 21, inc)(age)
```

### Constants

always

```javascript
const forever21 = age => ifElse(gte(__, 21), always(21), inc)(age)
```

## Identity

a => a -> identity

```javascript
const alwaysDrivingAge = age => ifElse(lt(__, 16), always(16), identity)(age)
```
