# JavaScript 代码 → 自然语言映射表

## 一、变量与数据类型

### 1. 变量声明

| 代码模式 | 自然语言描述 |
|----------|-------------|
| `let x = 5` | 声明一个变量 x，赋值为 5（可重新赋值） |
| `const name = "Alice"` | 声明一个常量 name，赋值为 "Alice"（不可改） |
| `var x = 5` | 声明变量 x（旧写法，不推荐） |
| `let a, b = 1` | 同时声明 a 和 b，b 赋值为 1 |

### 2. 常见数据类型

| 代码模式 | 自然语言描述 |
|----------|-------------|
| `number` | 数字类型：1, 2.5 |
| `string` | 字符串类型：文本 |
| `boolean` | 布尔类型：true / false |
| `null` | 空值：明确表示"没有" |
| `undefined` | 未定义：声明了但没赋值 |
| `array` | 数组类型：[ ] |
| `object` | 对象类型：{键: 值} |

### 3. 类型检查与转换

| 代码模式 | 自然语言描述 |
|----------|-------------|
| `typeof x` | 查看 x 的数据类型 |
| `x.toString()` | 把 x 转换为字符串 |
| `parseInt("123")` | 把字符串 "123" 转成整数 |
| `parseFloat("3.14")` | 把字符串 "3.14" 转成小数 |
| `String(x)` | 把 x 强制转为字符串 |
| `Number("5")` | 把 x 强制转为数字 |
| `Boolean(1)` | 把 x 强制转为布尔值 |

---

## 二、函数定义

### 1. 函数声明模式

| 代码模式 | 自然语言描述 |
|----------|-------------|
| `function hello() {}` | 定义一个叫 hello 的函数，无参数 |
| `function hello(name) {}` | 定义函数 hello，接收一个参数 name |
| `function add(a, b = 10) {}` | 定义函数 add，b 有默认值 10 |
| `function sum(...nums) {}` | 定义函数 sum，接收任意数量参数到 nums 数组 |
| `return result` | 返回 result 作为执行结果 |
| `return` | 返回 undefined（空返回） |

### 2. 箭头函数

| 代码模式 | 自然语言描述 |
|----------|-------------|
| `() => {}` | 定义一个无参数的箭头函数 |
| `x => x * 2` | 定义单参数箭头函数，直接返回 x*2 |
| `(a, b) => a + b` | 定义双参数箭头函数，返回 a+b |
| `(a, b) => { return a + b }` | 同上，多行写法 |

### 3. 完整函数翻译

```javascript
function add(a, b) {
    return a + b;
}
```
**翻译**：定义一个函数 `add`，把 `a` 和 `b` 传进去，做加法运算，然后返回结果。

```javascript
const greet = (name, greeting = "Hello") => {
    return `${greeting}, ${name}!`;
};
```
**翻译**：用 const 定义一个常量 `greet`，赋值为箭头函数。函数接收 `name` 和 `greeting` 两个参数，`greeting` 默认值是 "Hello"，返回模板字符串 `${greeting}, ${name}!`。

```javascript
const process = (...args) => {
    console.log(args);
};
```
**翻译**：`...args` 把所有传入的参数收集成一个数组 args，然后打印出来。

---

## 三、条件与比较

| 代码模式 | 自然语言描述 |
|----------|-------------|
| `if (x > 0) {}` | 如果 x 大于 0 |
| `else if (x === 0) {}` | 否则如果 x 等于 0（严格相等） |
| `else {}` | 以上都不满足 |
| `x === y` | 严格相等：类型和值都必须相等 |
| `x == y` | 宽松相等：只比较值（自动转类型） |
| `x !== y` | 严格不相等 |
| `&&` | 且：多个条件同时成立 |
| `||` | 或：任意一个条件成立 |
| `!x` | 非：取反 |
| `x ? a : b` | 三元运算符：x 为真则返回 a，否则返回 b |

### 条件翻译

```javascript
const grade = score >= 90 ? "A" : score >= 80 ? "B" : "C";
```
**翻译**：如果 score 大于等于 90，grade 设为 "A"；否则如果大于等于 80，grade 设为 "B"；否则设为 "C"。

---

## 四、循环遍历

| 代码模式 | 自然语言描述 |
|----------|-------------|
| `for (let i = 0; i < 5; i++) {}` | 从 0 数到 4，每次循环后 i 加 1 |
| `for (let item of items) {}` | 遍历 items 数组，每次取出一个 item |
| `for (let key in obj) {}` | 遍历 obj 对象，每次取出一个键名 key |
| `while (x > 0) {}` | 当 x 大于 0 时，持续循环 |
| `break` | 立即跳出整个循环 |
| `continue` | 跳过本次循环，继续下一次 |

### 循环翻译

```javascript
for (let i = 0; i < items.length; i++) {
    console.log(items[i]);
}
```
**翻译**：初始化 i 为 0，当 i 小于 items 数组长度时执行循环体，每次循环结束后 i 加 1。打印 items 数组中第 i 个元素。

```javascript
for (const item of items) {
    if (item > 10) break;
    console.log(item);
}
```
**翻译**：遍历 items 数组，如果遇到大于 10 的元素就立即停止循环。

---

## 五、数组操作

### 1. 增删改查

| 代码模式 | 自然语言描述 |
|----------|-------------|
| `arr.push(x)` | 把 x 添加到数组末尾 |
| `arr.pop()` | 弹出并返回数组最后一个元素 |
| `arr.shift()` | 弹出并返回数组第一个元素 |
| `arr.unshift(x)` | 在数组开头插入 x |
| `arr.splice(index, count)` | 从 index 位置删除 count 个元素 |
| `arr.slice(1, 3)` | 截取数组索引 1 到 3（不含3）的部分 |
| `arr.includes(x)` | 检查数组是否包含 x |
| `arr.indexOf(x)` | 返回数组中第一个 x 的索引 |

### 2. 遍历方法

| 代码模式 | 自然语言描述 |
|----------|-------------|
| `arr.forEach(fn)` | 对数组每个元素执行 fn 函数 |
| `arr.map(fn)` | 对每个元素执行 fn，返回新数组 |
| `arr.filter(fn)` | 筛选出满足条件的元素，返回新数组 |
| `arr.reduce(fn, init)` | 依次处理每个元素，汇总成一个值 |
| `arr.find(fn)` | 找出第一个满足条件的元素 |
| `arr.findIndex(fn)` | 找出第一个满足条件的元素的索引 |
| `arr.some(fn)` | 是否存在任意一个满足条件的元素 |
| `arr.every(fn)` | 是否所有元素都满足条件 |

### 3. 数组方法翻译

```javascript
const doubled = items.map(x => x * 2);
```
**翻译**：对 items 数组中每个元素 x，执行 x*2，组成一个新数组 doubled。

```javascript
const bigOnes = items.filter(x => x > 10);
```
**翻译**：从 items 数组中挑出所有大于 10 的元素，组成新数组 bigOnes。

```javascript
const total = nums.reduce((sum, x) => sum + x, 0);
```
**翻译**：遍历 nums 数组，用 sum 累计求和，每次把当前元素 x 加到 sum 里，初始值是 0，最终得到总和。

---

## 六、对象操作

| 代码模式 | 自然语言描述 |
|----------|-------------|
| `obj.name` | 读取对象的 name 属性 |
| `obj["name"]` | 读取对象的 name 属性（括号语法） |
| `obj.name = "Alice"` | 设置对象的 name 属性 |
| `delete obj.name` | 删除对象的 name 属性 |
| `Object.keys(obj)` | 获取对象所有键 |
| `Object.values(obj)` | 获取对象所有值 |
| `Object.entries(obj)` | 获取对象所有键值对 |
| `Object.assign({}, obj)` | 浅拷贝对象 |
| `...obj` | 展开对象（解构赋值） |

### 对象翻译

```javascript
const { name, age } = user;
```
**翻译**：从 user 对象中提取 name 和 age 属性，分别存入同名变量 name 和 age。

```javascript
const merged = { ...a, ...b };
```
**翻译**：把对象 a 和 b 的属性合并到一个新对象 merged，b 的属性会覆盖 a 的同名属性。

---

## 七、DOM 操作

### 1. 获取元素

| 代码模式 | 自然语言描述 |
|----------|-------------|
| `document.getElementById("id")` | 通过 ID 获取一个元素 |
| `document.querySelector(".class")` | 通过选择器获取第一个匹配元素 |
| `document.querySelectorAll("div")` | 通过选择器获取所有匹配元素 |
| `element.innerHTML` | 元素的内部 HTML 内容 |
| `element.innerText` | 元素的人类可读文本（忽略隐藏） |
| `element.textContent` | 元素的纯文本内容（含隐藏文本） |

### 2. 修改元素

| 代码模式 | 自然语言描述 |
|----------|-------------|
| `element.style.color = "red"` | 设置元素的文字颜色为红色 |
| `element.classList.add("active")` | 给元素添加 "active" 类名 |
| `element.classList.remove("active")` | 移除元素的 "active" 类名 |
| `element.classList.toggle("active")` | 切换 "active" 类名（有则删，无则加） |
| `element.setAttribute("href", url)` | 设置元素的属性 |
| `element.getAttribute("href")` | 读取元素的属性值 |
| `element.appendChild(child)` | 把 child 添加为 element 的子元素 |
| `element.remove()` | 删除这个元素 |

### 3. DOM翻译

```javascript
const btn = document.querySelector("#submit-btn");
btn.style.background = "blue";
btn.addEventListener("click", () => {
    console.log("点击了！");
});
```
**翻译**：
- `querySelector("#submit-btn")`：通过 ID 获取提交按钮元素
- `style.background = "blue"`：把按钮背景设为蓝色
- `addEventListener("click", ...)`：监听点击事件，点击时打印 "点击了！"

---

## 八、事件处理

| 代码模式 | 自然语言描述 |
|----------|-------------|
| `element.onclick = fn` | 点击时执行 fn（旧写法） |
| `element.addEventListener("click", fn)` | 监听点击事件，触发 fn |
| `element.addEventListener("change", fn)` | 监听值变化事件 |
| `element.addEventListener("input", fn)` | 监听输入事件（每次输入都触发） |
| `element.addEventListener("submit", fn)` | 监听表单提交事件 |
| `event.preventDefault()` | 阻止默认行为（如阻止表单提交跳转） |
| `event.stopPropagation()` | 阻止事件冒泡传播 |

### 事件翻译

```javascript
form.addEventListener("submit", (e) => {
    e.preventDefault();
    console.log("表单提交被拦截了！");
});
```
**翻译**：监听 form 的提交事件，阻止浏览器默认的提交跳转行为，然后打印提示。

---

## 九、异步操作

### 1. Promise

| 代码模式 | 自然语言描述 |
|----------|-------------|
| `new Promise((resolve, reject) => {})` | 创建 Promise 对象 |
| `resolve(value)` | Promise 成功完成，返回 value |
| `reject(error)` | Promise 执行失败，返回错误 |
| `.then(fn)` | Promise 成功后执行 fn |
| `.catch(fn)` | Promise 失败后执行 fn |
| `.finally(fn)` | 不管成功失败都执行 fn |

### 2. async / await

| 代码模式 | 自然语言描述 |
|----------|-------------|
| `async function fetchData() {}` | 定义一个异步函数 |
| `await promise` | 等待 Promise 完成，获取其结果 |
| `await fetch(url)` | 等待 fetch 请求返回结果 |

### 3. 异步翻译

```javascript
async function loadUser(id) {
    const response = await fetch(`/api/user/${id}`);
    const data = await response.json();
    return data;
}
```
**翻译**：
- `async function`：定义一个异步函数（可以内部用 await）
- `await fetch(...)`：发起网络请求，等待响应返回
- `await response.json()`：等待响应体解析为 JSON，返回 data
- 最终返回用户数据

```javascript
fetch(url)
    .then(res => res.json())
    .then(data => console.log(data))
    .catch(err => console.error(err));
```
**翻译**：发起 fetch 请求，收到响应后转为 JSON，拿到数据后打印；如果任何一步出错则捕获错误并打印。

---

## 十、常用内置对象

| 代码模式 | 自然语言描述 |
|----------|-------------|
| `console.log(x)` | 把 x 打印到控制台 |
| `console.error(x)` | 把 x 作为错误打印 |
| `JSON.stringify(obj)` | 把对象转换为 JSON 字符串 |
| `JSON.parse(str)` | 把 JSON 字符串解析为对象 |
| `Math.random()` | 生成 0 到 1 之间的随机数 |
| `Math.floor(x)` | 向下取整 |
| `Date.now()` | 获取当前时间戳（毫秒） |
| `Array.isArray(x)` | 检查 x 是否为数组 |
| `setTimeout(fn, 1000)` | 延迟 1000 毫秒后执行 fn |
| `setInterval(fn, 1000)` | 每隔 1000 毫秒执行一次 fn |
