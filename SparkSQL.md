# [Built-in Functions](https://spark.apache.org/docs/latest/api/sql/index.html#built-in-functions)

### [!](https://spark.apache.org/docs/latest/api/sql/index.html#_1)

! expr - Logical not.

!  Expr-逻辑非 ,**或非与的非**

**Examples:**

```sql
> SELECT ! true;
 false
> SELECT ! false;
 true
> SELECT ! NULL;
 NULL
```

**Since:** 1.0.0



### [!=](https://spark.apache.org/docs/latest/api/sql/index.html#_2)

expr1 != expr2 - Returns true if `expr1` is not equal to `expr2`, or false otherwise.

expr1 != expr2 - 如果‘ expr1’不等于‘ expr2’返回 true，否则返回 false。**不等判断**

**Arguments:**

- expr1, expr2 - the two expressions must be same type or can be casted to a common type, and must be a type that can be used in equality comparison. Map type is not supported. For complex types such array/struct, the data types of fields must be orderable.
- Expr1，expr2-这两个表达式必须是相同的类型，或者可以强制转换为公共类型，并且必须是可以用于相等比较的类型。不支持map类型。对于诸如 array/struct 这样的复杂类型，字段的数据类型必须是可排序的。

**Examples:**

```sql
> SELECT 1 != 2;
 true
> SELECT 1 != '2';
 true
> SELECT true != NULL;
 NULL
> SELECT NULL != NULL;
 NULL
```

**Since:** 1.0.0



### [%](https://spark.apache.org/docs/latest/api/sql/index.html#_3)

expr1 % expr2 - Returns the remainder after `expr1`/`expr2`.

expr1% expr2-返回 expr1/expr2之后的余数。求余

**Examples:**

```sql
> SELECT 2 % 1.8;
 0.2
> SELECT MOD(2, 1.8);
 0.2
```

**Since:** 1.0.0



### [&](https://spark.apache.org/docs/latest/api/sql/index.html#_4)

expr1 & expr2 - Returns the result of bitwise AND of `expr1` and `expr2`.

Expr1 & expr2-返回 expr1和 expr2的按位 AND 的结果。

**Examples:**

```sql
> SELECT 3 & 5;
 1
```

**Since:** 1.4.0



### [*](https://spark.apache.org/docs/latest/api/sql/index.html#_5)

expr1 * expr2 - Returns `expr1`*`expr2`.

Expr1 * expr2-返回 expr1 * expr2。**乘法计算**

**Examples:**

```sql
> SELECT 2 * 3;
 6
```

**Since:** 1.0.0



### [+](https://spark.apache.org/docs/latest/api/sql/index.html#_6)

expr1 + expr2 - Returns `expr1`+`expr2`.

返回 expr1 + expr2。**加法运算**

**Examples:**

```sql
> SELECT 1 + 2;
 3
```

**Since:** 1.0.0



### [-](https://spark.apache.org/docs/latest/api/sql/index.html#-)

expr1 - expr2 - Returns `expr1`-`expr2`.

返回 expr1-expr2。**减法运算**

**Examples:**

```sql
> SELECT 2 - 1;
 1
```

**Since:** 1.0.0



### [/](https://spark.apache.org/docs/latest/api/sql/index.html#_7)

expr1 / expr2 - Returns `expr1`/`expr2`. It always performs floating point division.

Expr1/expr2-返回 expr1/expr2。它总是执行浮点除法。**除法运算**

**Examples:**

```sql
> SELECT 3 / 2;
 1.5
> SELECT 2L / 2L;
 1.0
```

**Since:** 1.0.0



### [<](https://spark.apache.org/docs/latest/api/sql/index.html#_8)

expr1 < expr2 - Returns true if `expr1` is less than `expr2`.

Expr1 < expr2-如果 expr1小于 expr2，返回 true。**小于号**

**Arguments:**

- expr1, expr2 - the two expressions must be same type or can be casted to a common type, and must be a type that can be ordered. For example, map type is not orderable, so it is not supported. For complex types such array/struct, the data types of fields must be orderable.
- Expr1，expr2-这两个表达式必须是相同的类型，或者可以强制转换为公共类型，并且必须是可以排序的类型。例如，map类型不可排序，因此不支持。对于诸如 array/struct 这样的复杂类型，字段的数据类型必须是可排序的。

**Examples:**

```
> SELECT 1 < 2;
 true
> SELECT 1.1 < '1';
 false
> SELECT to_date('2009-07-30 04:17:52') < to_date('2009-07-30 04:17:52');
 false
> SELECT to_date('2009-07-30 04:17:52') < to_date('2009-08-01 04:17:52');
 true
> SELECT 1 < NULL;
 NULL
```

**Since:** 1.0.0



### [<=](https://spark.apache.org/docs/latest/api/sql/index.html#_9)

expr1 <= expr2 - Returns true if `expr1` is less than or equal to `expr2`.

Expr1 < = expr2-如果 expr1小于或等于 expr2，返回 true。**小于等于号**

**Arguments:**

- expr1, expr2 - the two expressions must be same type or can be casted to a common type, and must be a type that can be ordered. For example, map type is not orderable, so it is not supported. For complex types such array/struct, the data types of fields must be orderable.
- Expr1，expr2-这两个表达式必须是相同的类型，或者可以强制转换为公共类型，并且必须是可以排序的类型。例如，map类型不可排序，因此不支持。对于诸如 array/struct 这样的复杂类型，字段的数据类型必须是可排序的。

**Examples:**

```
> SELECT 2 <= 2;
 true
> SELECT 1.0 <= '1';
 true
> SELECT to_date('2009-07-30 04:17:52') <= to_date('2009-07-30 04:17:52');
 true
> SELECT to_date('2009-07-30 04:17:52') <= to_date('2009-08-01 04:17:52');
 true
> SELECT 1 <= NULL;
 NULL
```

**Since:** 1.0.0



### [<=>](https://spark.apache.org/docs/latest/api/sql/index.html#_10)

expr1 <=> expr2 - Returns same result as the EQUAL(=) operator for non-null operands, but returns true if both are null, false if one of the them is null.

Expr1 < = > expr2-返回与非NULL值的 等号(=)相同的结果，即如果两个操作数都为空，则返回 true; 如果其中一个值为空，则返回 false。

**Arguments:**

- expr1, expr2 - the two expressions must be same type or can be casted to a common type, and must be a type that can be used in equality comparison. Map type is not supported. For complex types such array/struct, the data types of fields must be orderable.
- Expr1，expr2-这两个表达式必须是相同的类型，或者可以强制转换为公共类型，并且必须是可以用于相等比较的类型。不支持map类型。对于诸如 array/struct 这样的复杂类型，字段的数据类型必须是可排序的。

**Examples:**

例子:

```
> SELECT 2 <=> 2;
 true
> SELECT 1 <=> '1';
 true
> SELECT true <=> NULL;
 false
> SELECT NULL <=> NULL;
 true
```

**Since:** 1.1.0



### [<>](https://spark.apache.org/docs/latest/api/sql/index.html#_11)

expr1 != expr2 - Returns true if `expr1` is not equal to `expr2`, or false otherwise.

Expr1! = expr2-如果 expr1不等于 expr2，则返回 true，否则返回 false。**不等号判断**

**Arguments:**

- expr1, expr2 - the two expressions must be same type or can be casted to a common type, and must be a type that can be used in equality comparison. Map type is not supported. For complex types such array/struct, the data types of fields must be orderable.
- Expr1，expr2-这两个表达式必须是相同的类型，或者可以强制转换为公共类型，并且必须是可以用于相等比较的类型。不支持map类型。对于诸如 array/struct 这样的复杂类型，字段的数据类型必须是可排序的。

**Examples:**

例子:

```
> SELECT 1 != 2;
 true
> SELECT 1 != '2';
 true
> SELECT true != NULL;
 NULL
> SELECT NULL != NULL;
 NULL
```

**Since:** 1.0.0



### [=](https://spark.apache.org/docs/latest/api/sql/index.html#_12)

expr1 = expr2 - Returns true if `expr1` equals `expr2`, or false otherwise.

Expr1 = expr2-如果 expr1等于 expr2返回 true，否则返回 false。**等号判断**

**Arguments:**

- expr1, expr2 - the two expressions must be same type or can be casted to a common type, and must be a type that can be used in equality comparison. Map type is not supported. For complex types such array/struct, the data types of fields must be orderable.
- Expr1，expr2-这两个表达式必须是相同的类型，或者可以强制转换为公共类型，并且必须是可以用于相等比较的类型。不支持map类型。对于诸如 array/struct 这样的复杂类型，字段的数据类型必须是可排序的。

**Examples:**

```
> SELECT 2 = 2;
 true
> SELECT 1 = '1';
 true
> SELECT true = NULL;
 NULL
> SELECT NULL = NULL;
 NULL
```

**Since:** 1.0.0



### [==](https://spark.apache.org/docs/latest/api/sql/index.html#_13)

expr1 == expr2 - Returns true if `expr1` equals `expr2`, or false otherwise.

Expr1 = = expr2-如果 expr1等于 expr2返回 true，否则返回 false。**和等号(=)没什么区别**

**Arguments:**

- expr1, expr2 - the two expressions must be same type or can be casted to a common type, and must be a type that can be used in equality comparison. Map type is not supported. For complex types such array/struct, the data types of fields must be orderable.
- Expr1，expr2-这两个表达式必须是相同的类型，或者可以强制转换为公共类型，并且必须是可以用于相等比较的类型。不支持map类型。对于诸如 array/struct 这样的复杂类型，字段的数据类型必须是可排序的。

**Examples:**

```
> SELECT 2 == 2;
 true
> SELECT 1 == '1';
 true
> SELECT true == NULL;
 NULL
> SELECT NULL == NULL;
 NULL
```

**Since:** 1.0.0



### [>](https://spark.apache.org/docs/latest/api/sql/index.html#_14)

expr1 > expr2 - Returns true if `expr1` is greater than `expr2`.

Expr1 > expr2-如果 expr1大于 expr2，返回 true。**大于号**

**Arguments:**

- expr1, expr2 - the two expressions must be same type or can be casted to a common type, and must be a type that can be ordered. For example, map type is not orderable, so it is not supported. For complex types such array/struct, the data types of fields must be orderable.
- Expr1，expr2-这两个表达式必须是相同的类型，或者可以强制转换为公共类型，并且必须是可以排序的类型。例如，map类型不可排序，因此不支持。对于诸如 array/struct 这样的复杂类型，字段的数据类型必须是可排序的。

**Examples:**

```
> SELECT 2 > 1;
 true
> SELECT 2 > 1.1;
 true
> SELECT to_date('2009-07-30 04:17:52') > to_date('2009-07-30 04:17:52');
 false
> SELECT to_date('2009-07-30 04:17:52') > to_date('2009-08-01 04:17:52');
 false
> SELECT 1 > NULL;
 NULL
```

**Since:** 1.0.0



### [>=](https://spark.apache.org/docs/latest/api/sql/index.html#_15)

expr1 >= expr2 - Returns true if `expr1` is greater than or equal to `expr2`.

Expr1 > = expr2-如果 expr1大于或等于 expr2，返回 true。**大于等于号**

**Arguments:**

- expr1, expr2 - the two expressions must be same type or can be casted to a common type, and must be a type that can be ordered. For example, map type is not orderable, so it is not supported. For complex types such array/struct, the data types of fields must be orderable.
- Expr1，expr2-这两个表达式必须是相同的类型，或者可以强制转换为公共类型，并且必须是可以排序的类型。例如，map类型不可排序，因此不支持。对于诸如 array/struct 这样的复杂类型，字段的数据类型必须是可排序的。

**Examples:**

```
> SELECT 2 >= 1;
 true
> SELECT 2.0 >= '2.1';
 false
> SELECT to_date('2009-07-30 04:17:52') >= to_date('2009-07-30 04:17:52');
 true
> SELECT to_date('2009-07-30 04:17:52') >= to_date('2009-08-01 04:17:52');
 false
> SELECT 1 >= NULL;
 NULL
```

**Since:** 1.0.0



### [^](https://spark.apache.org/docs/latest/api/sql/index.html#_16)

expr1 ^ expr2 - Returns the result of bitwise exclusive OR of `expr1` and `expr2`.

Expr1 ^ expr2-返回 expr1和 expr2的按位异或用运算的结果。

*首先将expr1, expr2转为2进制,如果2进制的长度不同, 短的那个在左边不0, 和长的补齐, 然后按照`0 ^ 0 = 0 ` `0 ^ 1 = 1` `1 ^ 0 = 1`  ` 1 ^ 1 = 0` 的规则从左到右逐个计算异或, 最后将得到的2进制数字转为10进制就得到结果*, 如下面的例子中, 3的2进制是11, 5的2进制是101,将3的2进制补齐未011, 那么011和101的按位异或结果为110, 转为十进制为6

**Examples:**

例子:

```
> SELECT 3 ^ 5;
 6
```

**Since:** 1.4.0



### [abs](https://spark.apache.org/docs/latest/api/sql/index.html#abs)

abs(expr) - Returns the absolute value of the numeric or interval value.

Abs (expr)-返回数值或区间值的绝对值。**取绝对值**

**Examples:**

```
> SELECT abs(-1);
 1
> SELECT abs(INTERVAL -'1-1' YEAR TO MONTH);
 1-1
```

**Since:** 1.2.0



### [acos](https://spark.apache.org/docs/latest/api/sql/index.html#acos)

acos(expr) - Returns the inverse cosine (a.k.a. arc cosine) of `expr`, as if computed by `java.lang.Math.acos`.

acos (expr)-返回 expr 的反余弦，类似于 java.lang. Math.acos 或 python中的math.acos计算的余弦。

*acos是cos(expr)的相反计算,其中返回值是表示弧度单位的数字, 如3.141592653589793=π , 1.0471975511965976=π/3 ,  0.5235987755982988=π/6 等*, *如果参数超出范围，则返回 `NaN`*

**Examples:**

```sql
> SELECT acos(2);
 NaN
>select cos(pi())
-1.0
>select acos(-1)
3.141592653589793
>select cos(0)
1.0
>select acos(1)
0.0
>select cos(pi()/3)
0.5
>select acos(0.5)
1.04719755 -- 等于π/3
```

**Since:** 1.4.0



### [acosh](https://spark.apache.org/docs/latest/api/sql/index.html#acosh)

acosh(expr) - Returns inverse hyperbolic cosine of `expr`.

Acosh (expr)-返回 expr 的反双曲余弦。**没学过双曲余弦函数**

**Examples:**

```sql
> SELECT acosh(1);
 0.0
> SELECT acosh(0);
 NaN
```

**Since:** 3.0.0



### [add_months](https://spark.apache.org/docs/latest/api/sql/index.html#add_months)

add_months(start_date, num_months) - Returns the date that is `num_months` after `start_date`.

add _ mones(start _ date,num _ mones) - 返回 start _ date 之后的 num _ months的日期。**减1个月用-1**

**Examples:**

```sql
> SELECT add_months('2016-08-31', 1);
 2016-09-30
```

**Since:** 1.5.0



### [aes_decrypt](https://spark.apache.org/docs/latest/api/sql/index.html#aes_decrypt)

aes_decrypt(expr, key[, mode[, padding]]) - Returns a decrypted value of `expr` using AES in `mode` with `padding`. Key lengths of 16, 24 and 32 bits are supported. Supported combinations of (`mode`, `padding`) are ('ECB', 'PKCS') and ('GCM', 'NONE'). The default mode is GCM.

aes_decrypt(expr, key[, mode[, padding]]) - 使用 AES  (`mode`, `padding`) , 返回“ expr”的解密值。支持16位、24位和32位的密钥长度。支持的组合(`mode`, `padding`)是('ECB', 'PKCS')和('GCM', 'NONE')。默认模式是 GCM。

**Arguments:**

- expr - The binary value to decrypt.

- key - The passphrase to use to decrypt the data.

- mode - Specifies which block cipher mode should be used to decrypt messages. Valid modes: ECB, GCM.

- padding - Specifies how to pad messages whose length is not a multiple of the block size. Valid values: PKCS, NONE, DEFAULT. The DEFAULT padding means PKCS for ECB and NONE for GCM.

  

- expr - 要解密的二进制值。

- key - 用于解密数据的密钥。

- mode - 指定应该使用哪种分组密码模式来解密消息。有效模式: ECB，GCM。

- padding - 指定如何填充长度不是块大小的倍数的消息。有效值: PKCS，NONE，DEFAULT。DEFAULT 填充表示 ECB 为 PKCS，GCM 为 NONE。

  

**Examples:**

```sql
> SELECT aes_decrypt(unhex('83F16B2AA704794132802D248E6BFD4E380078182D1544813898AC97E709B28A94'), '0000111122223333');
 Spark
> SELECT aes_decrypt(unhex('6E7CA17BBB468D3084B5744BCA729FB7B2B7BCB8E4472847D02670489D95FA97DBBA7D3210'), '0000111122223333', 'GCM');
 Spark SQL
> SELECT aes_decrypt(unbase64('3lmwu+Mw0H3fi5NDvcu9lg=='), '1234567890abcdef', 'ECB', 'PKCS');
 Spark SQL
```

**Since:** 3.3.0



### [aes_encrypt](https://spark.apache.org/docs/latest/api/sql/index.html#aes_encrypt)

aes_encrypt(expr, key[, mode[, padding]]) - Returns an encrypted value of `expr` using AES in given `mode` with the specified `padding`. Key lengths of 16, 24 and 32 bits are supported. Supported combinations of (`mode`, `padding`) are ('ECB', 'PKCS') and ('GCM', 'NONE'). The default mode is GCM.

aes_crypt (expr,key [ ,mode [, pding ]) - 在给定`mode`下使用 AES 以指定的`padding`返回 expr 的加密值。支持16位、24位和32位的密钥长度。支持的(`mode`, `padding`)组合是(‘ ECB’，‘ PKCS’)和(‘ GCM’，‘ NONE’)。默认模式是 GCM。

**Arguments:**

- expr - The binary value to encrypt.

- key - The passphrase to use to encrypt the data.

- mode - Specifies which block cipher mode should be used to encrypt messages. Valid modes: ECB, GCM.

- padding - Specifies how to pad messages whose length is not a multiple of the block size. Valid values: PKCS, NONE, DEFAULT. The DEFAULT padding means PKCS for ECB and NONE for GCM.

  

- expr-要加密的二进制值。

- key-用于加密数据的密钥

- mode - 指定应该使用哪种分组密码模式来加密消息。有效模式: ECB，GCM。

- padding - 指定如何填充长度不是块大小的倍数的消息。有效值: PKCS，NONE，DEFAULT。DEFAULT 填充表示 ECB 为 PKCS，GCM 为 NONE。

**Examples:**

```sql
> SELECT hex(aes_encrypt('Spark', '0000111122223333'));
 83F16B2AA704794132802D248E6BFD4E380078182D1544813898AC97E709B28A94
> SELECT hex(aes_encrypt('Spark SQL', '0000111122223333', 'GCM'));
 6E7CA17BBB468D3084B5744BCA729FB7B2B7BCB8E4472847D02670489D95FA97DBBA7D3210
> SELECT base64(aes_encrypt('Spark SQL', '1234567890abcdef', 'ECB', 'PKCS'));
 3lmwu+Mw0H3fi5NDvcu9lg==
```

**Since:** 3.3.0



### [aggregate](https://spark.apache.org/docs/latest/api/sql/index.html#aggregate)

aggregate(expr, start, merge, finish) - Applies a binary operator to an initial state and all elements in the array, and reduces this to a single state. The final state is converted into the final result by applying a finish function.

aggregate(expr, start, merge, finish) - 将二进制运算符应用于初始状态和数组中的所有元素，并将其减少为单个状态。最终状态通过应用 finish 函数转换为最终结果。**好复杂,感觉用不到**

**Examples:**

例子:

```sql
> SELECT aggregate(array(1, 2, 3), 0, (acc, x) -> acc + x);
 6
> SELECT aggregate(array(1, 2, 3), 0, (acc, x) -> acc + x, acc -> acc * 10);
 60
```

**Since:** 2.4.0



### [and](https://spark.apache.org/docs/latest/api/sql/index.html#and)

expr1 and expr2 - Logical AND.

Expr1和 exp2-逻辑 与。

**Examples:**

```
> SELECT true and true;
 true
> SELECT true and false;
 false
> SELECT true and NULL;
 NULL
> SELECT false and NULL;
 false
```

**Since:** 1.0.0



### [any](https://spark.apache.org/docs/latest/api/sql/index.html#any)

any(expr) - Returns true if at least one value of `expr` is true.

any (expr)-如果 expr 的至少一个值为 true，则返回 true。

**Examples:**

```
> SELECT any(col) FROM VALUES (true), (false), (false) AS tab(col);
 true
> SELECT any(col) FROM VALUES (NULL), (true), (false) AS tab(col);
 true
> SELECT any(col) FROM VALUES (false), (false), (NULL) AS tab(col);
 false
```

**Since:** 3.0.0



### [approx_count_distinct 近似去重统计](https://spark.apache.org/docs/latest/api/sql/index.html#approx_count_distinct)

approx_count_distinct(expr[, relativeSD]) - Returns the estimated cardinality by HyperLogLog++. `relativeSD` defines the maximum relative standard deviation allowed.

approx_count_distinct(expr[, relativeSD]) -通过 HyperLoglog + + 返回近似估计的去重统计数。 relativeSD 定义允许的最大相对标准差。**相当于不太准确的count(distinct col) , 优势是速度快, 劣势是估计结果有少许偏差,下方的例子显示去重后有3个值**

**Examples:**

```
> SELECT approx_count_distinct(col1) FROM VALUES (1), (1), (2), (2), (3) tab(col1);
 3
```

**Since:** 1.6.0



### [approx_percentile 近似百分比](https://spark.apache.org/docs/latest/api/sql/index.html#approx_percentile)

approx_percentile(col, percentage [, accuracy]) - Returns the approximate `percentile` of the numeric or ansi interval column `col` which is the smallest value in the ordered `col` values (sorted from least to greatest) such that no more than `percentage` of `col` values is less than the value or equal to that value. The value of percentage must be between 0.0 and 1.0. The `accuracy` parameter (default: 10000) is a positive numeric literal which controls approximation accuracy at the cost of memory. Higher value of `accuracy` yields better accuracy, `1.0/accuracy` is the relative error of the approximation. When `percentage` is an array, each value of the percentage array must be between 0.0 and 1.0. In this case, returns the approximate percentile array of column `col` at the given percentage array.

approx_percentile(col, percentage [, accuracy]) - 返回数值或 ansi 区间列 `col` 的近似百分位数，它是有序 `col` 值中最小的值(从最小到最大排序) ，使得不超过 `col` 值的百分比小于或等于该值。百分比的值必须在0.0和1.0之间。`accuracy`参数(默认值: 10000)是一个正数，它以内存为代价控制近似精度。`accuracy`越高产生的精度越高，1.0/`accuracy` 是近似值的相对误差。`percentage`为数组时，百分比数组的每个值必须介于0.0和1.0之间。在这种情况下，返回给定百分比数组中列 `col` 的近似百分比数组。

**Examples:**

```
> SELECT approx_percentile(col, array(0.5, 0.4, 0.1), 100) FROM VALUES (0), (1), (2), (10) AS tab(col);
 [1,1,0]
> SELECT approx_percentile(col, 0.5, 100) FROM VALUES (0), (6), (7), (9), (10) AS tab(col);
 7
> SELECT approx_percentile(col, 0.5, 100) FROM VALUES (INTERVAL '0' MONTH), (INTERVAL '1' MONTH), (INTERVAL '2' MONTH), (INTERVAL '10' MONTH) AS tab(col);
 0-1
> SELECT approx_percentile(col, array(0.5, 0.7), 100) FROM VALUES (INTERVAL '0' SECOND), (INTERVAL '1' SECOND), (INTERVAL '2' SECOND), (INTERVAL '10' SECOND) AS tab(col);
 [0 00:00:01.000000000,0 00:00:02.000000000]
```

**Since:** 2.1.0



### [array](https://spark.apache.org/docs/latest/api/sql/index.html#array)

array(expr, ...) - Returns an array with the given elements.

array (expr，...)-返回一个包含给定元素的数组。

**Examples:**

例子:

```
> SELECT array(1, 2, 3);
 [1,2,3]
```

**Since:** 1.1.0



### [array_agg](https://spark.apache.org/docs/latest/api/sql/index.html#array_agg)

array_agg(expr) - Collects and returns a list of non-unique elements.

array _ agg (expr)-收集并返回非唯一元素的列表。 

**Examples:**

```
> SELECT array_agg(col) FROM VALUES (1), (2), (1) AS tab(col);
 [1,2,1]
```

**Note:**

The function is non-deterministic because the order of collected results depends on the order of the rows which may be non-deterministic after a shuffle.

该函数是非确定性的，因为收集结果的顺序取决于行的顺序，这些行在洗牌后可能是非确定性的。

**Since:** 2.0.0



### [array_contains](https://spark.apache.org/docs/latest/api/sql/index.html#array_contains)

array_contains(array, value) - Returns true if the array contains the value.

array _ content (array,value)-如果数组包含值，则返回 true。

**Examples:**

```
> SELECT array_contains(array(1, 2, 3), 2);
 true
```

**Since:** 1.5.0



### [array_distinctArray _ different](https://spark.apache.org/docs/latest/api/sql/index.html#array_distinct)

array_distinct(array) - Removes duplicate values from the array.

array _ different (array)-从数组中删除重复值。

**Examples:**

```
> SELECT array_distinct(array(1, 2, 3, null, 3));
 [1,2,3,null]
```

**Since:** 2.4.0



### [array_except](https://spark.apache.org/docs/latest/api/sql/index.html#array_except)

array_except(array1, array2) - Returns an array of the elements in array1 but not in array2, without duplicates.

array_except (array1，array2)-返回在array1且不在array2中的元素组成的数组，不带重复项。

**Examples:**

```
> SELECT array_except(array(1, 2, 3), array(1, 3, 5));
 [2]
```

**Since:** 2.4.0



### [array_intersect](https://spark.apache.org/docs/latest/api/sql/index.html#array_intersect)

array_intersect(array1, array2) - Returns an array of the elements in the intersection of array1 and array2, without duplicates.

array_intersect (array1,array2) - 返回 array1和 array2交集元素组成的数组，不带重复项。

**Examples:**

```
> SELECT array_intersect(array(1, 2, 3), array(1, 3, 5));
 [1,3]
```

**Since:** 2.4.0



array_join(array, delimiter[, nullReplacement]) - Concatenates the elements of the given array using the delimiter and an optional string to replace nulls. If no value is set for nullReplacement, any null value is filtered.

array _ join (array,delimiter [ ,nullReplace ])-使用分隔符(delimiter)和可选的替换null的字符串(nullReplace)把数组中的元素拼接起来。如果没有为 nullReplace 设置值，则null 值会被剔除。

**Examples:**

```
> SELECT array_join(array('hello', 'world'), ' ');
 hello world
> SELECT array_join(array('hello', null ,'world'), ' ');
 hello world
> SELECT array_join(array('hello', null ,'world'), ' ', ',');
 hello , world
```

**Since:** 2.4.0



### [array_max](https://spark.apache.org/docs/latest/api/sql/index.html#array_max)

array_max(array) - Returns the maximum value in the array. NaN is greater than any non-NaN elements for double/float type. NULL elements are skipped.

array_max (array)-返回数组中的最大值。NaN 大于任何非 NaN 的double/float 类型元素。 NULL 元素会被跳过。

**Examples:**

```
> SELECT array_max(array(1, 20, null, 3));
 20
```

**Since:** 2.4.0



### [array_min](https://spark.apache.org/docs/latest/api/sql/index.html#array_min)

array_min(array) - Returns the minimum value in the array. NaN is greater than any non-NaN elements for double/float type. NULL elements are skipped.

array _ min(array) - 返回数组中的最小值。NaN 大于任何非 NaN 的double/float 类型元素。 NULL 元素会被跳过。

**Examples:**

```
> SELECT array_min(array(1, 20, null, 3));
 1
```

**Since:** 2.4.0



### [array_position](https://spark.apache.org/docs/latest/api/sql/index.html#array_position)

array_position(array, element) - Returns the (1-based) index of the first element of the array as long.

array_position(array, element) - 返回元素在数组中第一次出现时的index(索引从1开始)。

**Examples:**

```
> SELECT array_position(array(3, 2, 1), 1);
 3
```

**Since:** 2.4.0



### [array_remove](https://spark.apache.org/docs/latest/api/sql/index.html#array_remove)

array_remove(array, element) - Remove all elements that equal to element from array.

array_remove(array, element) - 从 array 中删除所有与 element 相等的元素。

**Examples:**

例子:

```
> SELECT array_remove(array(1, 2, 3, null, 3), 3);
 [1,2,null]
```

**Since:** 2.4.0



### [array_repeat](https://spark.apache.org/docs/latest/api/sql/index.html#array_repeat)

array_repeat(element, count) - Returns the array containing element count times.

array_repeat(element, count) - 返回由count个element组成的数组。

**Examples:**

```
> SELECT array_repeat('123', 2);
 ["123","123"]
```

**Since:** 2.4.0



### [array_size](https://spark.apache.org/docs/latest/api/sql/index.html#array_size)

array_size(expr) - Returns the size of an array. The function returns null for null input.

array_size(expr) - 返回数组的大小,如果输入值为null, 该函数返回null。

**Examples:**

```
> SELECT array_size(array('b', 'd', 'c', 'a'));
 4
```

**Since:** 3.3.0



### [array_sort](https://spark.apache.org/docs/latest/api/sql/index.html#array_sort)

array_sort(expr, func) - Sorts the input array. If func is omitted, sort in ascending order. The elements of the input array must be orderable. NaN is greater than any non-NaN elements for double/float type. Null elements will be placed at the end of the returned array. Since 3.0.0 this function also sorts and returns the array based on the given comparator function. The comparator will take two arguments representing two elements of the array. It returns a negative integer, 0, or a positive integer as the first element is less than, equal to, or greater than the second element. If the comparator function returns null, the function will fail and raise an error.

array_sort(expr, func) - 对输入数组进行排序。如果未指定 func参数，则按升序排序。输入数组的元素必须是可排序的。NaN 大于任何非 NaN 的double/float 类型元素。Null元素将放置在返回数组的末尾。从3.0.0开始，这个函数还根据给定的比较器函数对数组进行排序并返回数组。比较器将接受表示数组中两个元素的参数。当第一个元素小于、等于或大于第二个元素时，它返回负整数、0或正整数。如果比较器函数返回 null，则函数将失败并报错。

**Examples:**

```
> SELECT array_sort(array(5, 6, 1), (left, right) -> case when left < right then -1 when left > right then 1 else 0 end);
 [1,5,6]
> SELECT array_sort(array('bc', 'ab', 'dc'), (left, right) -> case when left is null and right is null then 0 when left is null then -1 when right is null then 1 when left < right then 1 when left > right then -1 else 0 end);
 ["dc","bc","ab"]
> SELECT array_sort(array('b', 'd', null, 'c', 'a'));
 ["a","b","c","d",null]
```

**Since:** 2.4.0



### [array_union](https://spark.apache.org/docs/latest/api/sql/index.html#array_union)

array_union(array1, array2) - Returns an array of the elements in the union of array1 and array2, without duplicates.

array_union(array1, array2) - 返回 array1和 array2并集中元素的数组，不带重复项。

**Examples:**

```
> SELECT array_union(array(1, 2, 3), array(1, 3, 5));
 [1,2,3,5]
```

**Since:** 2.4.0



### [arrays_overlap](https://spark.apache.org/docs/latest/api/sql/index.html#arrays_overlap)

arrays_overlap(a1, a2) - Returns true if a1 contains at least a non-null element present also in a2. If the arrays have no common element and they are both non-empty and either of them contains a null element null is returned, false otherwise.

arrays_overlap(a1, a2) - 如果 a1至少包含一个a2中的非null元素，返回 true。如果两数组没有公共元素，且它们均为非空数组，且其中任意一个数组包含null元素，则返回 null，否则返回 false。

**Examples:**

例子:

```
> SELECT arrays_overlap(array(1, 2, 3), array(3, 4, 5));
 true
```

**Since:** 2.4.0



### [arrays_zip](https://spark.apache.org/docs/latest/api/sql/index.html#arrays_zip)

arrays_zip(a1, a2, ...) - Returns a merged array of structs in which the N-th struct contains all N-th values of input arrays.

arrays_zip(a1, a2, ...) - -返回一个合并的结构数组，其中第 N 个结构包含输入数组的所有第 N 个值。

**Examples:**

```
> SELECT arrays_zip(array(1, 2, 3), array(2, 3, 4));
 [{"0":1,"1":2},{"0":2,"1":3},{"0":3,"1":4}]
> SELECT arrays_zip(array(1, 2), array(2, 3), array(3, 4));
 [{"0":1,"1":2,"2":3},{"0":2,"1":3,"2":4}]
```

**Since:** 2.4.0



### [ascii](https://spark.apache.org/docs/latest/api/sql/index.html#ascii)

ascii(str) - Returns the numeric value of the first character of `str`.

ascii(str) - 返回 str 的第一个字符的[ascii代码](https://baike.baidu.com/item/ASCII/309296)。**0123456789的ascii代码分别为48,49,50,51,52,53,54,55,56,57**

**Examples:**

```
> SELECT ascii('222');
 50
> SELECT ascii(2);
 50
```

**Since:** 1.5.0



### [asin](https://spark.apache.org/docs/latest/api/sql/index.html#asin)

asin(expr) - Returns the inverse sine (a.k.a. arc sine) the arc sin of `expr`, as if computed by `java.lang.Math.asin`.

asin(expr) - 返回 expr 的反正弦，就像 java.lang. Math.asin 计算的一样。**asin是sin的相反过程的函数,结果为弧度值不是角度值**

**Examples:**

```
> SELECT asin(0);
 0.0
> SELECT asin(2);
 NaN
```

**Since:** 1.4.0



### [asinh](https://spark.apache.org/docs/latest/api/sql/index.html#asinh)

asinh(expr) - Returns inverse hyperbolic sine of `expr`.

Asinh (expr)-返回 expr 的反双曲正弦。

**Examples:**

```
> SELECT asinh(0);
 0.0
```

**Since:** 3.0.0



### [assert_true](https://spark.apache.org/docs/latest/api/sql/index.html#assert_true)

assert_true(expr) - Throws an exception if `expr` is not true.

assert_true(expr) - 如果 expr 不为 true，则报错。

**Examples:**

```
> SELECT assert_true(0 < 1);
 NULL
```

**Since:** 2.0.0



### [atan](https://spark.apache.org/docs/latest/api/sql/index.html#atan)

atan(expr) - Returns the inverse tangent (a.k.a. arc tangent) of `expr`, as if computed by `java.lang.Math.atan`

atan(expr) - 返回 expr 的反正切 ，类似于 java.lang. Math.atan 计算的结果

**Examples:**

```
> SELECT atan(0);
 0.0
```

**Since:** 1.4.0



### [atan2](https://spark.apache.org/docs/latest/api/sql/index.html#atan2)

atan2(exprY, exprX) - Returns the angle in radians between the positive x-axis of a plane and the point given by the coordinates (`exprX`, `exprY`), as if computed by `java.lang.Math.atan2`.

atan2(exprY, exprX) - 返回一个平面的正 x 轴和坐标(exprX，exprY)给出的点之间弧度的角度，就像 java.lang.Math.atan2 计算的那样。

**Arguments:**

- exprY - coordinate on y-axis

- exprX - coordinate on x-axis

  

- Y 轴坐标

- 在 x 轴上的坐标

**Examples:**

```
> SELECT atan2(0, 0);
 0.0
```

**Since:** 1.4.0



### [atanh](https://spark.apache.org/docs/latest/api/sql/index.html#atanh)

atanh(expr) - Returns inverse hyperbolic tangent of `expr`.

atanh(expr) - 返回 expr 的反双曲正切。

**Examples:**

```
> SELECT atanh(0);
 0.0
> SELECT atanh(2);
 NaN
```

**Since:** 3.0.0



### [avg](https://spark.apache.org/docs/latest/api/sql/index.html#avg)

avg(expr) - Returns the mean calculated from values of a group.

avg(expr) - 返回根据组内的值计算出的平均值。

**Examples:**

```
> SELECT avg(col) FROM VALUES (1), (2), (3) AS tab(col);
 2.0
> SELECT avg(col) FROM VALUES (1), (2), (NULL) AS tab(col);
 1.5
```

**Since:** 1.0.0



### [base64](https://spark.apache.org/docs/latest/api/sql/index.html#base64)

base64(bin) - Converts the argument from a binary `bin` to a base 64 string.

base64(bin) - 将参数从二进制 bin 转换为以64为基数的字符串。

**Examples:**

```
> SELECT base64('Spark SQL');
 U3BhcmsgU1FM
```

**Since:** 1.5.0



### [between](https://spark.apache.org/docs/latest/api/sql/index.html#between)

expr1 [NOT] BETWEEN expr2 AND expr3 - evaluate if `expr1` is [not] in between `expr2` and `expr3`.

expr1 [NOT] BETWEEN expr2 AND expr3 - 评估 expr1是否在 expr2和 expr3之间。

**Examples:**

```
> SELECT col1 FROM VALUES 1, 3, 5, 7 WHERE col1 BETWEEN 2 AND 5;
 3
 5
```

**Since:** 1.0.0



### [bigint](https://spark.apache.org/docs/latest/api/sql/index.html#bigint)

bigint(expr) - Casts the value `expr` to the target data type `bigint`.

bigint(expr) - 将 expr 值转换为目标数据类型 bigint。

**Since:** 2.0.1



### [bin](https://spark.apache.org/docs/latest/api/sql/index.html#bin)

bin(expr) - Returns the string representation of the long value `expr` represented in binary.

bin(expr) - 返回用二进制表示的long类型的 expr 的字符串表示形式。

**Examples:**

```
> SELECT bin(13);
 1101
> SELECT bin(-13);
 1111111111111111111111111111111111111111111111111111111111110011
> SELECT bin(13.3);
 1101
```

**Since:** 1.5.0



### [binary](https://spark.apache.org/docs/latest/api/sql/index.html#binary)

binary(expr) - Casts the value `expr` to the target data type `binary`.

binary(expr) - 将 expr 值转换为二进制目标数据类型。

**Since:** 2.0.1



### [bit_and](https://spark.apache.org/docs/latest/api/sql/index.html#bit_and)

bit_and(expr) - Returns the bitwise AND of all non-null input values, or null if none.

bit_and(expr) - 返回所有非空输入值的按位 AND，如果没有，返回 null。

**Examples:**

```
> SELECT bit_and(col) FROM VALUES (3), (5) AS tab(col);
 1
```

**Since:** 3.0.0



### [bit_count](https://spark.apache.org/docs/latest/api/sql/index.html#bit_count)

bit_count(expr) - Returns the number of bits that are set in the argument expr as an unsigned 64-bit integer, or NULL if the argument is NULL.

bit_count(expr) - 返回参数 expr 中设置为无符号64位整数的位数，如果参数为 NULL，返回 NULL。

**Examples:**

```
> SELECT bit_count(0);
 0
```

**Since:** 3.0.0











