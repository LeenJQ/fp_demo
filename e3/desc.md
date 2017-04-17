#Thinking in Ramda: Partial Application

http://randycoulman.com/blog/2016/06/07/thinking-in-ramda-partial-application/

```javascript
const publishedInYear = (book, year) => book.year === year

const titlesForYear = (books, year) => {
  const selected = filter(book => publishedInYear(book, year), books)

  return map(book => book.title, selected)
}
```

## Higher-Order Functions

```javascript
const publishedInYear = year => book => book.year === year

const titlesForYear = (books, year) => {
  const selected = filter(publishedInYear(year), books)

  return map(book => book.title, selected)
}
```

## Partially-Applying Functions

partial, partialRight


## Curry


## Flip , __

```javascript
const publishedInYear = curry((book, year) => book.year === year)

const titlesForYear = (books, year) => {
  const selected = filter(flip(publishedInYear)(year), books)

  return map(book => book.title, selected)
}
```

### Placeholder
```javascript
const publishedInYear = curry((book, year) => book.year === year)

const titlesForYear = (books, year) => {
  const selected = filter(publishedInYear(__, year), books)

  return map(book => book.title, selected)
}
```

```javascript
const threeArgs = curry((a, b, c) => { /* ... */ })

const middleArgumentLater = threeArgs('value for a', __, 'value for c')

/////////
const threeArgs = curry((a, b, c) => { /* ... */ })

const middleArgumentOnly = threeArgs(__, 'value for b', __)
```
  __ 需要用在 curry 之后的函数
