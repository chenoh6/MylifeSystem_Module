---
name: code-natural-lang-map
description: |
  编程代码 ↔ 自然语言 映射速查表。用于将代码语法映射为自然语言解释，降低代码理解门槛。
  适用于：(1) 阅读代码时快速理解语义 (2) 编写代码时将需求翻译为代码 (3) 作为编程概念的语义对照字典。
  触发时机：用户提到"代码翻译"、"自然语言映射"、"编程概念解释"、"这个代码是什么意思"等。
---

# 代码 ↔ 自然语言 映射表

## 按编程语言分类

### 1. CSS - 样式/布局
→ [references/css-basics.md](references/css-basics.md)
- 选择器：`body`、`.class`、`#id`、`:hover`
- 属性分类：字体、盒子模型、背景、Flex布局、动画
- 完整代码翻译示例

### 2. HTML - 结构/标签
→ [references/html-attrs.md](references/html-attrs.md)
- 属性映射：`src`、`href`、`class`、`id`、`onclick`

### 3. Python - 逻辑/数据
→ [references/python-basics.md](references/python-basics.md)
- 变量/数据类型、函数定义、流程控制、类定义
- 列表/字典操作、异常处理、文件操作、模块导入

### 4. JavaScript - 交互/逻辑
→ [references/javascript-basics.md](references/javascript-basics.md)
- 变量声明（let/const）、函数定义、箭头函数
- 数组操作（map/filter/reduce）、DOM操作
- 事件处理、异步操作（async/await/Promise）

### 5. SQL - 数据库查询
→ [references/sql-basics.md](references/sql-basics.md)
- 查询（SELECT/WHERE/ORDER BY/GROUP BY）
- 插入（INSERT）、更新（UPDATE）、删除（DELETE）
- 表连接（JOIN）、子查询、索引与约束

## 使用方式

### 方式一：静态速查

查阅对应语言的参考文件，查找：
- 某个选择器/属性/关键字的含义
- 某个完整代码模式的翻译

### 方式二：动态翻译

把一段代码发给我，我按结构逐块翻译成自然语言。

## 翻译输出模板

```
## 原文代码
[代码]

## 自然语言翻译
[逐块/逐行翻译]

## 关键概念
- [概念1]: [含义]
```

## 扩展计划

后续可扩展：
- Shell / Bash 命令
- TypeScript
- React / Vue 语法
- 其他语言
