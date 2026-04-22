# CSS 代码 → 自然语言映射表

## 一、选择器 (Selector) - 告诉浏览器"选谁"

| CSS 选择器 | 代码示例 | 自然语言描述 |
|------------|----------|-------------|
| 标签选择器 | `body { }` | 选择所有 `body` 标签 |
| 类选择器 | `.container { }` | 选择所有 class="container" 的元素 |
| ID选择器 | `#header { }` | 选择 id="header" 的唯一元素 |
| 后代选择器 | `.box p { }` | 选择 .box 里面的所有 p 标签 |
| 子选择器 | `.box > p { }` | 选择 .box 的直接子元素 p |
| 并集选择器 | `h1, h2, h3 { }` | 同时选择 h1、h2、h3 |
| 通配符 | `* { }` | 选择所有元素 |
| 伪类 | `:hover`, `:first-child` | 选择特定状态的元素 |
| 属性选择器 | `[type="text"]` | 选择 type="text" 的元素 |

---

## 二、CSS 属性分类映射

### 1. 文字/字体属性

| CSS属性 | 代码示例 | 自然语言描述 |
|---------|----------|-------------|
| `font-family` | `font-family: "Inter", sans-serif` | 字体家族：优先用 Inter，没有则用系统无衬线字体 |
| `font-size` | `font-size: 16px` | 字体大小：16像素 |
| `font-weight` | `font-weight: 700` | 字体粗细：700=加粗，400=正常 |
| `font-style` | `font-style: italic` | 字体风格：斜体 |
| `line-height` | `line-height: 1.5` | 行高：1.5倍字号 |
| `color` | `color: #333` | 文字颜色：深灰色 |
| `text-align` | `text-align: center` | 文本对齐：居中 |
| `text-decoration` | `text-decoration: underline` | 文本装饰：下划线 |
| `letter-spacing` | `letter-spacing: 2px` | 字间距：2像素 |

### 2. 盒子模型属性

| CSS属性 | 代码示例 | 自然语言描述 |
|---------|----------|-------------|
| `width` | `width: 100px` | 宽度：100像素 |
| `height` | `height: 200px` | 高度：200像素 |
| `padding` | `padding: 20px` | **内边距**：元素内部边缘到内容的距离，四周都是20px |
| `padding-top` | `padding-top: 10px` | 上内边距 |
| `padding: 10px 20px` | `padding: 10px 20px` | 上下10px，左右20px |
| `margin` | `margin: 20px` | **外边距**：元素外部边缘到相邻元素的距离 |
| `margin: 0 auto` | `margin: 0 auto` | 上下0，左右自动（居中） |
| `border` | `border: 1px solid #ccc` | 边框：1像素实线浅灰色 |
| `border-radius` | `border-radius: 8px` | 圆角：8像素圆角 |
| `box-sizing` | `box-sizing: border-box` | 盒尺寸计算：padding和border算在width里 |

### 3. 背景属性

| CSS属性 | 代码示例 | 自然语言描述 |
|---------|----------|-------------|
| `background` | `background: #f0f4f8` | 背景色：浅蓝灰色 |
| `background-color` | `background-color: red` | 背景颜色：红色 |
| `background-image` | `background-image: url(img.png)` | 背景图：使用img.png |
| `background-size` | `background-size: cover` | 背景尺寸：覆盖整个区域 |
| `background-position` | `background-position: center` | 背景位置：居中 |

### 4. 布局/定位属性

| CSS属性 | 代码示例 | 自然语言描述 |
|---------|----------|-------------|
| `display` | `display: flex` | 显示模式：弹性盒子布局 |
| `display: block` | `display: block` | 块级元素：独占一行 |
| `display: inline` | `display: inline` | 行内元素：不换行 |
| `display: none` | `display: none` | 隐藏元素：不显示 |
| `position` | `position: relative` | 定位方式：相对定位（相对于原本位置） |
| `position: absolute` | `position: absolute` | 绝对定位：相对于最近定位祖先 |
| `position: fixed` | `position: fixed` | 固定定位：相对于视口 |
| `top/right/bottom/left` | `top: 10px` | 定位偏移：距顶部10px |
| `z-index` | `z-index: 100` | 层叠顺序：100（在上面） |
| `float` | `float: left` | 浮动：向左浮动 |
| `clear` | `clear: both` | 清除浮动：左右两侧都不允许浮动 |

### 5. Flex 布局属性

| CSS属性 | 代码示例 | 自然语言描述 |
|---------|----------|-------------|
| `flex-direction` | `flex-direction: row` | 主轴方向：水平（从左到右） |
| `flex-direction: column` | `flex-direction: column` | 主轴方向：垂直（从上到下） |
| `justify-content` | `justify-content: center` | 主轴对齐：居中 |
| `justify-content: space-between` | `justify-content: space-between` | 主轴对齐：两端对齐，项目间等距 |
| `align-items` | `align-items: center` | 交叉轴对齐：垂直居中 |
| `flex-wrap` | `flex-wrap: wrap` | 换行：超出后换行 |
| `gap` | `gap: 10px` | 间距：项目间10px |

### 6. 转换/动画属性

| CSS属性 | 代码示例 | 自然语言描述 |
|---------|----------|-------------|
| `transform` | `transform: rotate(45deg)` | 变换：旋转45度 |
| `transform: translate` | `transform: translate(10px, 20px)` | 位移：右移10px，下移20px |
| `transition` | `transition: all 0.3s` | 过渡：所有属性变化时，0.3秒完成 |
| `animation` | `animation: fadeIn 1s` | 动画：执行fadeIn动画，1秒 |
| `opacity` | `opacity: 0.5` | 不透明度：半透明50% |

### 7. 其他常用属性

| CSS属性 | 代码示例 | 自然语言描述 |
|---------|----------|-------------|
| `overflow` | `overflow: hidden` | 溢出处理：隐藏超出部分 |
| `overflow: auto` | `overflow: auto` | 溢出处理：超出时显示滚动条 |
| `cursor` | `cursor: pointer` | 鼠标光标：手型 |
| `visibility` | `visibility: hidden` | 可见性：隐藏但占空间 |
| `list-style` | `list-style: none` | 列表样式：无 |
| `outline` | `outline: none` | 轮廓：移除聚焦时的轮廓线 |

---

## 三、完整代码模式翻译

### 示例1：基础盒子

```css
body {
  font-family: "Inter", -apple-system, BlinkMacSystemFont, sans-serif;
  background: #f0f4f8;
  padding: 20px;
}
```

**自然语言翻译**：
> 这段 CSS 代码针对 `body` 标签（网页主体）：
> - `font-family`：字体用 Inter，系统没有就用无衬线字体
> - `background`：背景色是浅蓝灰色 #f0f4f8
> - `padding`：元素内部四周留 20px 空白（内边距）

### 示例2：卡片组件

```css
.card {
  width: 300px;
  padding: 20px;
  margin: 10px;
  border: 1px solid #e0e0e0;
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0,0,0,0.1);
}
```

**自然语言翻译**：
> 定义一个类选择器 `.card`（卡片组件）：
> - 宽度 300px
> - 内边距 20px（内容与边框的距离）
> - 外边距 10px（卡片与外部元素的距离）
> - 边框 1像素 实线 浅灰色
> - 圆角 8px
> - 阴影：向右偏移0，向下偏移2px，模糊8px，半径0.1的黑色半透明

### 示例3：Flex 居中

```css
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}
```

**自然语言翻译**：
> `.container` 容器使用弹性布局：
> - `display: flex`：开启 Flex 布局
> - `justify-content: center`：水平居中
> - `align-items: center`：垂直居中
> - `height: 100vh`：高度占满整个视口
