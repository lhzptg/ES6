# ES6 20个经常使用的技巧

1.  打乱数组顺序

```
let arr = ['😄', 67, true, false, '55']
arr = arr.sort(() => 0.5 - Math.random())
console.log(arr)
// [ '😄', '55', 67, false, true ]
```

2.  删除数字之外的所有字符

```
const str = 'xieyezi 23213 is 95994 so hansome 223333'
const numbers = str.replace(/\D/g, '')
console.log(numbers)
// 2321395994223333
```

3.  反转字符串或者单词

```
const sentence = 'xieyezi js so handsome, lol.'
const reverseSentence = reverseBySeparator(sentence, "")
console.log(reverseSentence);
// .lol ,emosdnah os sj izeyeix

const reverseEachWord = reverseBySeparator(reverseSentence, " ")
console.log(reverseEachWord)
// izeyeix sj os ,emosdnah .lol

function reverseBySeparator(string, separator) {
  return string.split(separator).reverse().join(separator)
}
```

4.  将十进制转换为二进制文件或十六进制数

```
const num = 45
num.toString(2)
num.tostring(16)
```

1. 合并多个对象

```
const city = {
  name: 'Chongqing',
  population: '1,234,567,890'
}
const location = {
  longitude: '116.4',
  latitude: '39.9'
}
const fullCity = { ...city, ...location }
console.log(fullCity)
// {
//   name: 'Chongqing',
//   population: '1,234,567,890',
//   longitude: '116.4',
//   latitude: '39.9'
// }
```

1. `===` 和 `==` 的区别

```
// ==   ->  类型转换 (浅比较)
// ===  ->  无类型转换 (严格比较)

0 == false // true
0 === false // false
1 == "1" // true
1 === "1" // false
null == undefined // true
null === undefined // false
```

1. 解构赋值

```
const forest = {
  location: 'Sweden',
  animals: 3,
  animalsTypes: ['Lions', 'Tigers', 'Bears'],
};

const { location, animals, animalsTypes } = forest;
const [lions, tigers, bears] = animalsTypes;

console.log(location); // Sweden
console.log(animals); // 3
console.log(lions); // Lions
console.log(tigers); // Tigers
console.log(bears); // Bears
```

1. 交换变量的值

```
let bears = 'bears'
let tigers = 'tigers'
[bears, tigers] = [tigers, bears]
console.log(bears) // tigers
console.log(tribes) // bears
```

1. 1.判断回文字符串

```
const isRevervse = (str1, str2) => {
  const normalize = (str) =>
    str.toLowerCase()
    .normalize('NFD')
    .split('')
    .reverse()
    .join('')
  return normalize(str1) === str2
}
console.log(isRevervse('anagram', 'margana')) // true
console.log(isRevervse('rac', 'car')) // true
```

>  回文字符串: 正着写和反着写都一样的字符串 (特别感谢[@浮生阁阁主](https://juejin.cn/user/3998255455678968)勘误)

1. 2.判断两个字符串是否为互相排列

```
const isAnagram = (str1, str2) => {
  const normalize = (str) =>
    str.toLowerCase()
    .normalize('NFD')
    .split('')
    .sort()
    .join('')
  return normalize(str1) === normalize(str2)
}
console.log(isAnagram('anagram', 'nagaram')) // true
console.log(isAnagram('rat', 'car')) // false
console.log(isAnagram('heArT', 'traEH')) // true
```

>  判断两个字符串是否为互相排列: 给定两个字符串,一个是否是另一个的排列

1. 可选链操作符

```
const player = {
  name: 'xieyezi',
  rating: 1000,
  click: () => {
    return 'click'
  },
  pass: (teammate) => {
    return `Pass to ${teammate}`
  },
}
console.log(player?.name) // xieyezi
console.log(player?.click?.()) // click
console.log(player?.teammate?.()) // undefined
```

1. 三目运算符

```
// condition ? expression if true : expression if false
const oxygen = 10
const diver = (oxygen < 10 ) ? 'Low oxygen' : 'High oxygen'
console.log(diver) // High oxygen
```

1. 从数组中随机选择一个值

```
const elements = [24, 'You', 777, 'breaking', 99, 'full']
const random = (arr) => arr[Math.floor(Math.random() * arr.length)]
const randomElement = random(elements)
console.log(randomElement) // 777
```

1. 冻结对象

```
const octopus = {
  tentacles: 8,
  color: 'blue',
}
Object.freeze(octopus)
octopus.tentacles = 10 // Error, 不会改变
console.log(octopus) // { tentacles: 8, color: 'blue'}
```

1. 删除数组重复的元素

```
const animals = ['bears', 'lions', 'tigers', 'bears', 'lions']
const unique = (arr) => [...new Set(arr)]

console.log(unique(animals)) // [ 'bears', 'lions', 'tigers' ]
```

1. 保留指定位小数

```
const num = 0.123456789
const fixed2 = num.toFixed(2)
const fixed3 = num.toFixed(3)

console.log(fixed2) // 0.12
console.log(fixed3) // 0.123
```

1. 清空数组

```
const numbers = [1, 2, 3, 4, 5]
numbers.length = 0

console.log(numbers) // []
```

1. 从 `RGB` 转换为 `HEX`

```
const rgbToHex = (r, g, b) => {
  const toHex = (num) => {
    const hex = num.toString(16)
    return hex.length === 1 ? `0${hex}` : hex
  }
  return `#${toHex(r)}${toHex(g)}${toHex(b)}`
}
console.log(rgbToHex(46, 32, 67)) // #2e2043
```

1. 从数组中获取最大值和最小值

```
const nums = [1, 2, 3, 4, 5, -3, 99, -45, -1]
const max = Math.max(...nums)
const min = Math.min(...nums)
console.log(max) // 99
console.log(min) // -45
```

1. 空值合并运算符

```
const nullval = null
cost emptyString = ''
const someNum = 13

const a = nullval ?? 'A default'
const b = emptyString ?? 'B default'
const c = SomeNum ?? 'C default'

console.log(a) // A default
console.log(b) // '' // empty string != undefined or null
console.log(c) // 13
```

1. 过滤数组中值为 `false` 的值

```
const nums = [1, 0 , undefined, null, false];
const truthyNums = nums.filter(Boolean);
console.log(truthyNums) // [1]
```

<details class="details-reset details-overlay details-overlay-dark" id="jumpto-line-details-dialog" style="box-sizing: border-box; display: block;"><summary data-hotkey="l" aria-label="Jump to line" role="button" style="box-sizing: border-box; display: list-item; cursor: pointer; transition: color 80ms cubic-bezier(0.33, 1, 0.68, 1) 0s, background-color, box-shadow, border-color; list-style: none;"></summary></details>

