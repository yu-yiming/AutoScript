# AutoScript 语法

本篇介绍 AutoScript 的语法结构。

## 语法树说明

下面的语法说明中我会使用一些特殊的符号来表示特定的语法结构。

* 重复 0 到多次：使用符号 `*`，例 `a*`。
* 重复 1 到多次：使用符号 `+`，例 `a+`。
* 出现 0 或 1 次：使用符号 `?`，例 `a?`。
* 出现特定字符：`[]`，例 `[abcABC]`。
* 不出现特定字符：`[^]`，例 `[^"]`。
* 出现任一个：`|`，例 `a|b`。
* 字符串：`""`，例 `"this"`。
* 用特定结构分隔的 0 到多个结构：使用符号 `#*`，例如 `a #* b`。
* 用特定结构分隔的 1 到多个结构：使用符号 `#+`，例如 `a #+ b`。
* 用于修饰：使用符号 `()`，例如 `(simple)a`。
* 引用定义：使用符号 `@`，例如 `a@42`。

此外，考虑到命名习惯，我会使用特定的一些缩写，下面是一个总表：

* `constr`：约束，即 constraint。
* `decl`：声明，即 declaration。
* `stmt`：语句，即 statement。
* `spec`：规格，即 specification。

## 源文件

AutoScript 不对源文件的类型进行区分，所有以 `.as` 或 `.autoscript` 扩展名结尾的文件都会被当作 AutoScript 源文件纳入项目中。

```cpp
1:1. src = decl-stmt;
```



## 声明

### 提前声明

```cpp
2:1. forward-decl = storage-spec id type-spec constr-spec? cls?;
```



### 模式声明

```cpp
3:1. pattern-decl = simple-pattern-decl
                  | tuple-pattern-decl
                  | choice-pattern-decl
                  | qualifier-pattern-decl;
             
3:2. simple-pattern-decl = id
                         | "otherwise"
                         | "()";

3:3. tuple-pattern-decl = basic-tuple-pattern-decl #+ ",";

3:4. basic-tuple-pattern-decl = pattern-decl
                              | "..." pattern-decl;

3:5. choice-pattern-decl = (tag)id pattern-decl
                         | (tag)id;

3:6. qualifier-pattern-decl = obj-qualifier pattern-decl;
```



## 关键字

### A-C

```cpp
99.01.01 addressof-keyword = "addressof";

99.01.02 alias-keyword = "alias";

99.01.03 and-keyword = "and";

99.01.04 as-keyword = "as";

99.01.05 assert-keyword = "assert";

99.01.06 assume-keyword = "assume";

99.01.07 atom-keyword = "atom";

99.01.08 await-keyword = "await";

99.01.09 bitand-keyword = "bitand";

99.01.10 bitor-keyword = "bitor";

99.01.11 branch-keyword = "branch";

99.01.12 break-keyword = "break";

99.01.13 catch-keyword = "catch";

99.01.14 class-keyword = "class";

99.01.15 const-keyword = "const";

99.01.16 consteval-keyword = "consteval";

99.01.17 continue-keyword = "continue";

99.01.18 data-keyword = "data";

99.01.19 decay-keyword = "decay";
```



