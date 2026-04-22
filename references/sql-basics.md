# SQL 代码 → 自然语言映射表

## 一、查询（SELECT）- 读取数据

### 1. 基本查询模式

| SQL 语句 | 自然语言描述 |
|----------|-------------|
| `SELECT * FROM users` | 从 users 表中查询所有字段的所有记录 |
| `SELECT name, age FROM users` | 从 users 表中查询 name 和 age 两个字段 |
| `SELECT DISTINCT city FROM users` | 从 users 表中查询 city 字段，去重 |
| `SELECT COUNT(*) FROM users` | 统计 users 表里有多少条记录 |

### 2. 条件查询

| SQL 语句 | 自然语言描述 |
|----------|-------------|
| `WHERE age > 18` | 筛选 age 大于 18 的记录 |
| `WHERE name = "Alice"` | 筛选 name 等于 "Alice" 的记录 |
| `WHERE age >= 18 AND city = "Beijing"` | 筛选 age>=18 且 city 是 "Beijing" 的记录 |
| `WHERE city = "Beijing" OR city = "Shanghai"` | 筛选 city 是 "Beijing" 或 "Shanghai" 的记录 |
| `WHERE name LIKE "A%"` | 筛选 name 以 "A" 开头的记录 |
| `WHERE name LIKE "%Smith%"` | 筛选 name 包含 "Smith" 的记录 |
| `WHERE age IN (18, 20, 25)` | 筛选 age 是 18、20、25 中任一个的记录 |
| `WHERE age NOT IN (18, 20)` | 筛选 age 不是 18 也不是 20 的记录 |
| `WHERE age BETWEEN 18 AND 30` | 筛选 age 在 18 到 30 之间的记录（含两端） |
| `WHERE name IS NULL` | 筛选 name 为空（NULL）的记录 |
| `WHERE name IS NOT NULL` | 筛选 name 不为空的记录 |

### 3. 排序与限制

| SQL 语句 | 自然语言描述 |
|----------|-------------|
| `ORDER BY age` | 按 age 从小到大排序 |
| `ORDER BY age DESC` | 按 age 从大到小排序（降序） |
| `ORDER BY age ASC, name DESC` | 先按 age 升序，age 相同时按 name 降序 |
| `LIMIT 10` | 只取前 10 条记录 |
| `LIMIT 10 OFFSET 20` | 跳过前 20 条，取接下来的 10 条（分页） |

### 4. 聚合函数

| SQL 语句 | 自然语言描述 |
|----------|-------------|
| `COUNT(*)` | 统计记录总数 |
| `COUNT(column)` | 统计某字段非空的数量 |
| `SUM(price)` | 求 price 字段的总和 |
| `AVG(price)` | 求 price 字段的平均值 |
| `MAX(price)` | 求 price 字段的最大值 |
| `MIN(price)` | 求 price 字段的最小值 |
| `ROUND(AVG(price), 2)` | 求平均值并保留 2 位小数 |

### 5. 分组

| SQL 语句 | 自然语言描述 |
|----------|-------------|
| `GROUP BY city` | 按 city 分组（相同的 city 合并成一组） |
| `HAVING COUNT(*) > 5` | 筛选分组后数量大于 5 的组 |
| `GROUP BY city, gender` | 按 city 和 gender 联合分组 |

### 6. 完整查询翻译

```sql
SELECT city, COUNT(*) as user_count, AVG(age) as avg_age
FROM users
WHERE age >= 18
GROUP BY city
HAVING COUNT(*) > 10
ORDER BY user_count DESC
LIMIT 5;
```
**翻译**：从 users 表中，筛选 age 大于等于 18 的记录；按 city 分组统计每组的人数和平均年龄；只保留人数大于 10 的组；按人数从多到少排序；取前 5 条。

---

## 二、插入（INSERT）- 新增数据

| SQL 语句 | 自然语言描述 |
|----------|-------------|
| `INSERT INTO users (name, age) VALUES ("Alice", 20)` | 向 users 表插入一条新记录，name 是 "Alice"，age 是 20 |
| `INSERT INTO users VALUES (1, "Alice", 20)` | 向 users 表插入一条新记录，按字段顺序填入值 |
| `INSERT INTO users (name, age) VALUES ("Alice", 20), ("Bob", 25)` | 批量插入两条记录 |

```sql
INSERT INTO users (name, age, email)
VALUES ("Alice", 20, "alice@example.com");
```
**翻译**：向 users 表插入一条记录，name 字段填 "Alice"，age 字段填 20，email 字段填 "alice@example.com"。

---

## 三、更新（UPDATE）- 修改数据

| SQL 语句 | 自然语言描述 |
|----------|-------------|
| `UPDATE users SET age = 25` | 把 users 表所有记录的 age 改为 25 |
| `UPDATE users SET age = 25 WHERE id = 1` | 把 id=1 那条记录的 age 改为 25 |
| `UPDATE users SET age = age + 1 WHERE id = 1` | 把 id=1 那条记录的 age 加 1 |
| `UPDATE users SET name = "Bob", age = 30 WHERE id = 1` | 同时修改多个字段 |

```sql
UPDATE users
SET age = age + 1, status = "active"
WHERE last_login < "2024-01-01";
```
**翻译**：从 users 表中筛选 last_login 早于 2024-01-01 的记录，把这些记录的 age 加 1，并把 status 改为 "active"。

---

## 四、删除（DELETE）- 删除数据

| SQL 语句 | 自然语言描述 |
|----------|-------------|
| `DELETE FROM users` | 删除 users 表中所有记录（慎用！） |
| `DELETE FROM users WHERE id = 1` | 删除 users 表中 id=1 的那条记录 |
| `DELETE FROM users WHERE age < 18` | 删除 users 表中 age 小于 18 的记录 |

```sql
DELETE FROM users
WHERE status = "inactive" AND last_login < "2023-01-01";
```
**翻译**：从 users 表中删除 status="inactive" 且 last_login 早于 2023-01-01 的记录。

---

## 五、表的创建与管理

### 1. 建表

| SQL 语句 | 自然语言描述 |
|----------|-------------|
| `CREATE TABLE users (...)` | 创建一个叫 users 的表 |
| `INT AUTO_INCREMENT` | 整数类型，自增主键 |
| `VARCHAR(255)` | 可变长度字符串，最大 255 字符 |
| `TEXT` | 长文本类型 |
| `DECIMAL(10,2)` | 小数类型，共 10 位，含 2 位小数 |
| `BOOLEAN` | 布尔类型 |
| `DATE` | 日期类型 |
| `DATETIME` | 日期时间类型 |
| `DEFAULT value` | 默认值 |
| `NOT NULL` | 不能为空 |
| `PRIMARY KEY` | 设为主键（唯一标识） |
| `FOREIGN KEY (id) REFERENCES other(id)` | 设为外键，关联到其他表 |

```sql
CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    age INT DEFAULT 18,
    email VARCHAR(255) UNIQUE,
    created_at DATETIME DEFAULT CURRENT_TIMESTAMP
);
```
**翻译**：创建 users 表，字段包括：id（自增主键）、name（最长100字符不能为空）、age（整数默认18）、email（最长255字符唯一）、created_at（默认当前时间）。

### 2. 修改表结构

| SQL 语句 | 自然语言描述 |
|----------|-------------|
| `ALTER TABLE users ADD phone VARCHAR(20)` | 给 users 表新增 phone 字段 |
| `ALTER TABLE users DROP COLUMN phone` | 删除 users 表的 phone 字段 |
| `ALTER TABLE users MODIFY name VARCHAR(200)` | 修改 phone 字段的类型或约束 |
| `DROP TABLE users` | 删除整个 users 表（不可恢复） |

### 3. 其他表操作

| SQL 语句 | 自然语言描述 |
|----------|-------------|
| `TRUNCATE TABLE users` | 清空 users 表所有数据（保留结构） |
| `RENAME TABLE old TO new` | 把表名 old 改为 new |

---

## 六、表连接（JOIN）- 关联多表

| SQL 语句 | 自然语言描述 |
|----------|-------------|
| `INNER JOIN orders ON users.id = orders.user_id` | 内连接：只保留两边都能匹配上的记录 |
| `LEFT JOIN orders ON users.id = orders.user_id` | 左连接：以左表（users）为主，保留所有左表记录，右表没有匹配的则填 NULL |
| `RIGHT JOIN orders ON users.id = orders.user_id` | 右连接：以右表（orders）为主 |
| `FULL OUTER JOIN orders ON ...` | 全连接：两边都保留，不匹配的填 NULL |

### JOIN 翻译

```sql
SELECT users.name, orders.order_id, orders.amount
FROM users
INNER JOIN orders ON users.id = orders.user_id
WHERE orders.amount > 100;
```
**翻译**：把 users 表和 orders 表通过 id 字段连接起来（只保留两边都能匹配的记录）；查询用户名、订单号和金额；筛选金额大于 100 的记录。

```sql
SELECT u.name, o.amount
FROM users u
LEFT JOIN orders o ON u.id = o.user_id
WHERE o.id IS NULL;
```
**翻译**：以 users 表为主（全部保留），左连接 orders 表；找出那些没有订单的用户（o.id 为空）。

---

## 七、子查询与高级查询

| SQL 语句 | 自然语言描述 |
|----------|-------------|
| `SELECT * FROM users WHERE age > (SELECT AVG(age) FROM users)` | 找出年龄大于平均年龄的用户 |
| `SELECT * FROM users WHERE id IN (SELECT user_id FROM orders)` | 找出有订单的用户 |
| `SELECT * FROM users WHERE id NOT IN (...)` | 找出没有订单的用户 |
| `EXISTS (子查询)` | 判断子查询是否返回至少一行 |
| `UNION SELECT ... UNION SELECT ...` | 合并两个查询结果（自动去重） |
| `UNION ALL SELECT ...` | 合并查询结果（保留重复） |

```sql
-- 找出销量最高的产品
SELECT product_name, price
FROM products
WHERE id = (
    SELECT product_id
    FROM orders
    GROUP BY product_id
    ORDER BY SUM(amount) DESC
    LIMIT 1
);
```
**翻译**：在 products 表中，找出销量最高（订单金额总和最大）的那一个产品，显示其名称和价格。

---

## 八、索引与约束

| SQL 语句 | 自然语言描述 |
|----------|-------------|
| `CREATE INDEX idx_name ON users(name)` | 给 users 表的 name 字段创建索引（加速查询） |
| `CREATE UNIQUE INDEX idx_email ON users(email)` | 给 email 字段创建唯一索引（不能重复） |
| `DROP INDEX idx_name ON users` | 删除索引 |
| `UNIQUE` | 约束：字段值不能重复 |
| `CHECK (age > 0)` | 约束：age 必须大于 0 |
| `FOREIGN KEY REFERENCES` | 外键约束：关联其他表的主键 |

---

## 九、其他常用语句

| SQL 语句 | 自然语言描述 |
|----------|-------------|
| `SELECT NOW()` | 获取当前日期时间 |
| `SELECT CURDATE()` | 获取当前日期 |
| `SELECT DATE_FORMAT(created_at, "%Y-%m-%d")` | 把日期格式化为 "年-月-日" |
| `SELECT DATEDIFF(end, start)` | 计算两个日期相差天数 |
| `SELECT IFNULL(phone, "无")` | 如果 phone 为 NULL，返回 "无" |
| `SELECT COALESCE(a, b, c)` | 返回 a、b、c 中第一个非空的值 |
| `CASE WHEN age < 18 THEN '未成年' ELSE '成年' END` | 条件判断：年龄<18返回"未成年"，否则返回"成年" |
