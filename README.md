# eslint配置项
javascript的代码基础规范为百度javascript代码规范和阮一峰的es6代码风格。 同时，也需要遵守内部的个性化代码规范，_若和基础代码规范出现冲突，以个性化为准，_并在标准之上，增加一些最佳实践规范。
##1、结构
### 1.1 缩进
**百度规范**

- ~~[强制] 使用 4 个空格做为一个缩进层级，不允许使用 2 个空格 或 tab 字符。~~
- [强制] switch 下的 case 和 default 必须增加一个缩进层级。
- [强制] 二元运算符两侧必须有一个空格，一元运算符与操作对象之间不允许有空格。
- [强制] 用作代码块起始的左花括号 { 前必须有一个空格。
- [强制] if / else / for / while / function / switch / do / try / catch / finally 关键字后，必须有一个空格。
- [强制] 在对象创建时，属性中的 : 之后必须有空格，: 之前不允许有空格。
- [强制] 函数声明、具名函数表达式、函数调用中，函数名和 ( 之间不允许有空格。
- [强制] , 和 ; 前不允许有空格。
- [强制] 在函数调用、函数声明、括号表达式、属性访问、if / for / while / switch / catch 等语句中，() 和 [] 内紧贴括号部分不允许有空格。
- [强制] 单行声明的数组与对象，如果包含元素，{} 和 [] 内紧贴括号部分不允许包含空格。
- [强制] 行尾不得有多余的空格。

**个性化规范**

- 所有缩进均使用2个空格，而不是4个空格。同时，把所有tab自动转换成空格

**涉及eslint规则**

```js
'indent': ['error', 2], // 缩进控制 2空格
'no-mixed-spaces-and-tabs': 'error', // 禁止使用 空格 和 tab 混合缩进
'no-regex-spaces': 'error', // 禁止正则表达式字面量中出现多个空格
'no-multi-spaces': 'error', // 禁止出现多个空格而且不是用来作缩进的
'array-bracket-spacing': ['error', 'never'], // 数组紧贴括号部分不允许包含空格。
'object-curly-spacing': ['error', 'never'], // 对象紧贴花括号部分不允许包含空格。
'block-spacing': ['error', 'never'], // 单行代码块中紧贴括号部分不允许包含空格。
'comma-spacing': ['error', { 'before': false, 'after': true }], //在变量声明、数组字面量、对象字面量、函数参数 和 序列中禁止在逗号前使用空格,要求在逗号后使用一个或多个空格
'semi-spacing': ['error', {'before': false, 'after': true}], //禁止分号周围的空格
'computed-property-spacing': ['error', 'never'], // 禁止括号和其内部值之间的空格
'eslint keyword-spacing': ['error', { 'before': true ,'after': true}], // 该规则强制关键字和类似关键字的符号周围空格的一致性：as、break、case、catch、class、const、continue、debugger、default、delete、do、else、export、extends、finally、for、from、function、get、if、import、in、instanceof、let、new、of、return、set、static、super、switch、this、throw、try、typeof、var、void、while、with 和 yield。
'no-trailing-spaces': 'error', // 禁用行尾空格
'no-spaced-func': 'error', // 禁止 function 标识符和圆括号之间有空格
'space-before-function-paren': 'error', // 禁止函数圆括号之前有一个空格
'space-before-blocks': ['error', 'always'], // 禁止语句块之前的空格
'space-in-parens': ['error', 'never'], // 禁止圆括号内的空格
'space-infix-ops': ['error', {'int32Hint': false}], // 要求中缀操作符周围有空格,设置 int32Hint 选项为 true (默认 false) 允许 a|0 不带空格。
'space-unary-ops': 'error', // 要求或禁止在一元操作符之前或之后存在空格,new、delete、typeof、void、yield要求有空格，-、+、--、++、!、!!要求无空格。
'spaced-comment': ['error', 'always'], // 要求在注释前有空白
'arrow-spacing': 'error', // 要求箭头函数的箭头之前和之后有空格
'generator-star-spacing': ['error', {'before': false, 'after': true}], // 强制 generator 函数中 * 号前有空格，后无空格。
'yield-star-spacing': ['error', {'before': true, 'after': false}], // 强制 yield* 表达式中  * 号前有空格，后无空格。
'no-irregular-whitespace': 'error', // 禁止不规则的空白。
'template-curly-spacing': ['error', 'never'], // 强制模板字符串中花括号内不能出现空格 
```

### 1.2 换行
**百度规范**

- [强制] 每个独立语句结束后必须换行。
- ~~[强制] 每行不得超过 120 个字符。~~
- [强制] 运算符处换行时，运算符必须在新行的行首。
- [强制] 在函数声明、函数表达式、函数调用、对象创建、数组创建、for语句等场景中，不允许在 , 或 ; 前换行。
- ~~[建议] 不同行为或逻辑的语句集，使用空行隔开，更易阅读。~~
- ~~[建议] 在语句的行长度超过 120 时，根据逻辑条件合理缩进。~~
- [建议] 对于 if...else...、try...catch...finally 等语句，推荐使用在 } 号后添加一个换行 的风格，使代码层次结构更清晰，阅读性更好。

**个性化规范**

- 如果同一段代码包含较为明确的不同逻辑和行为，尽量使用空行分割，并且在段首加入简单注释说明。
- 每行字符不能超过100个，特殊情况下例外，例如复杂的正则表达式、超长字符串等。

```js
'max-len': ['error', 100], // 每行字符不能超过100个
'no-multiple-empty-lines': 'error', // 不允许多个空行
'newline-per-chained-call': ['error', { 'ignoreChainWithDepth': 2 }], //要求方法链中每个调用都有一个换行符
'eol-last': 'error', // 要求文件末尾保留一行空行
'lines-around-comment': ['error', { 'beforeBlockComment': true }], // 强制注释周围有空行
```

### 1.3 语句
**百度规范**

- [强制] 不得省略语句结束的分号。
- [强制] 在 if / else / for / do / while 语句中，即使只有一行，也不得省略块 {...}。
- [强制] 函数定义结束不允许添加分号。
- [强制] IIFE 必须在函数表达式外添加 (，非 IIFE 不得在函数表达式外添加 (。

**涉及eslint规则**

```js
'curly': ["error", "multi-line"], // if、else if、else、for、while强制使用大括号，但允许在单行中省略大括号。
'semi': ['error', 'always'], //不得省略语句结束的分号
```

### 1.4 命名
**百度规范**

- [强制] 变量 使用 Camel命名法。（驼峰）
- [强制] 常量 使用 全部字母大写，单词间下划线分隔 的命名方式。
- [强制] 函数 使用 Camel命名法。
- [强制] 函数的 参数 使用 Camel命名法。
- [强制] 类 使用 Pascal命名法。（首字母大写）
- [强制] 类的 方法 / 属性 使用 Camel命名法。
- [强制] 枚举变量 使用 Pascal命名法，枚举的属性 使用 全部字母大写，单词间下划线分隔 的命名方式。
- [强制] 命名空间 使用 Camel命名法。
- [强制] 由多个单词组成的缩写词，在命名中，根据当前命名法和出现的位置，所有字母的大小写与首字母的大小写保持一致。
- [强制] 类名 使用 名词。
- [建议] 函数名 使用 动宾短语。
- [建议] boolean 类型的变量使用 is 或 has 开头。
- [建议] Promise对象 用 动宾短语的进行时 表达。

**个性化规范**

**涉及eslint规则**

```js
'camelcase': ['error', {properties: 'never'}], // 要求使用骆驼拼写法
```

### 1.5 注释
*关于注释：*
*必要的注释是必不可少的，但是注释的添加还是要看情况，在项目比较成熟稳定的情况下，完善的注释增加项目的完整度。但写高质量的注释往往比写代码需要消耗更多的时间，开发过程中建议只添加必要的注释*

**百度规范**

- [强制] 必须独占一行。// 后跟一个空格，缩进与下一行被注释说明的代码一致。
- [建议] 避免使用 /*...*/ 这样的多行注释。有多行注释内容时，使用多个单行注释。
- [强制] 为了便于代码阅读和自文档化，以下内容必须包含以 /**...*/ 形式的块注释中。文件、namespace、类、函数或方法、类属性、事件、全局变量、常量、AMD 模块
- [强制] 文档注释前必须空一行。
- [建议] 自文档化的文档说明 what，而不是 how。
- [强制] 类型定义都是以{开始, 以}结束。
- [强制] 文件顶部必须包含文件注释，用 @file 标识文件说明
- [建议] 文件注释中可以用 @author 标识开发者信息。
- [建议] 命名空间使用 @namespace 标识。
- [建议] 使用 @class 标记类或构造函数。
- [建议] 使用 @extends 标记类的继承信息。
- [强制] 使用包装方式扩展类成员时， 必须通过 @lends 进行重新指向。
- [强制] 类的属性或方法等成员信息使用 @public / @protected / @private 中的任意一个，指明可访问性。
- [强制] 函数/方法注释必须包含函数说明，有参数和返回值时必须使用注释标识。
- [强制] 参数和返回值注释必须包含类型信息和说明。
- [建议] 当函数是内部函数，外部不可访问时，可以使用 @inner 标识。
- [强制] 对 Object 中各项的描述， 必须使用 @param 标识。
- [建议] 重写父类方法时， 应当添加 @override 标识。如果重写的形参个数、类型、顺序和返回值类型均未发生变化，可省略 @param、@return，仅用 @override 标识，否则仍应作完整注释
- [强制] 必须使用 @event 标识事件，事件参数的标识与方法描述的参数标识相同。
- [强制] 在会广播事件的函数前使用 @fires 标识广播的事件，在广播事件代码前使用 @event 标识事件。
- [建议] 对于事件对象的注释，使用 @param 标识，生成文档时可读性更好。
- [强制] 常量必须使用 @const 标记，并包含说明和类型信息。
- [建议] 对于类型未定义的复杂结构的注释，可以使用 @typedef 标识来定义。
- [强制] AMD 模块使用 @module 或 @exports 标识。
- [强制] 对于已使用 @module 标识为 AMD模块 的引用，在 namepaths 中必须增加 module: 作前缀。
- [建议] 对于类定义的模块，可以使用 @alias 标识构建函数。
- [建议] 多模块定义时，可以使用 @exports 标识各个模块。
- [建议] 对于 exports 为 Object 的模块，可以使用@namespace标识。
- [建议] 对于 exports 为类名的模块，使用 @class 和 @exports 标识。
- [建议] 细节注释遵循单行注释的格式。说明必须换行时，每行是一个单行注释的起始。
- [强制] 有时我们会使用一些特殊标记进行说明。特殊标记必须使用单行注释的形式。

**个性化规范**

- 函数等需要使用文档化注释，为了提高开发效率，仅函数/类/方法/文件必须使用文档化注释，其它情况可以使用单行注释。
 
**建议规范**

```js
/**
 * API description
 *
 * @param {type} name/name=default_value description 
 * @return {String} description
 * @example
 *     any example
 *     
 * @other description
 */
```
##2、语言特性
### 2.1 变量
**百度规范**

- ~~[强制] 变量在使用前必须通过 var 定义。~~
- ~~[强制] 每个 var 只能声明一个变量。~~
- [强制] 变量必须 即用即声明，不得在函数或其它形式的代码块起始位置统一声明所有变量。

**个性化规范**

- 禁止使用var定义变量，局部变量请使用let、const进行定义，全局变量请使用global进行定义。

**涉及eslint规则**

```js
'no-var': 'error', //用let/const代替var
'no-const-assign': 'error', //不允许改变用const声明的变量
'prefer-const': 'error', //如果一个变量不会被重新赋值，最好使用const进行声明。
'no-use-before-define': 'error', //禁止定义前使用
```

### 2.2 条件
**百度规范**

- [强制] 在 Equality Expression 中使用类型严格的 ===。仅当判断 null 或 undefined 时，允许使用 == null。
- [建议] 尽可能使用简洁的表达式。
- [建议] 按执行频率排列分支的顺序。
- [建议] 对于相同变量或表达式的多值条件，用 switch 代替 if。
- [建议] 如果函数或全局中的 else 块后没有任何语句，可以删除 else。

**个性化规范**

- 尽量使用switch，如果判断项超过两个，请务必使用switch，保证代码清晰。
- 如果 if 块中包含了一个 return 语句，else 块就成了多余的了。可以将其内容移至块外。
- 禁止 case 语句落空 
- 禁止可以在有更简单的可替代的表达式时使用三元操作符

**涉及eslint规则**

```js
'no-cond-assign': 'error', // 禁止在条件语句中出现赋值操作符
'no-constant-condition': 'error', //禁止在条件中使用常量表达式
'no-duplicate-case': 'error', // 禁止在 switch 语句中的 case 子句中出现重复的测试表达式
'default-case': 'error', // 要求 Switch 语句中有 Default 分支 
'eqeqeq': 'error', // 使用 === 和 !== 代替 == 和 !=
'no-else-return': 'error', // 如果 if 块中包含了一个 return 语句，else 块就成了多余的了。可以将其内容移至块外。
'no-fallthrough': 'error', // 禁止 case 语句落空 
'no-unneeded-ternary': 'error', //禁止可以在有更简单的可替代的表达式时使用三元操作符
```
### 2.3 循环
**百度规范**

- [建议] 不要在循环体中包含函数表达式，事先将函数提取到循环体外。
- [建议] 对循环内多次使用的不变值，在循环外用变量缓存。
- [建议] 对有序集合进行遍历时，缓存 length。
- [建议] 对有序集合进行顺序无关的遍历时，使用逆序遍历。

### 2.4 类型
**百度规范**

- [建议] 类型检测优先使用 typeof。对象类型检测使用 instanceof。null 或 undefined 的检测使用 == null。
- [建议] 转换成 string 时，使用 + ''。
- [建议] 转换成 number 时，通常使用 +。
- [建议] string 转换成 number，要转换的字符串结尾包含非数字并期望忽略时，使用 parseInt。
- [强制] 使用 parseInt 时，必须指定进制。
- [建议] 转换成 boolean 时，使用 !!。
- [建议] number 去除小数点，使用 Math.floor / Math.round / Math.ceil，不使用 parseInt。

**涉及eslint规则**

```js
'radix': 'error', // 在parseInt()中始终使用基数以消除意想不到的后果。
```

### 2.5 字符串
**百度规范**

- [强制] 字符串开头和结束使用单引号 '。
- ~~[建议] 使用 数组 或 + 拼接字符串。~~
- [建议] 复杂的数据到视图字符串的转换过程，选用一种模板引擎。

**个性化规范**

- 使用``进行字符串拼接，尽量使用es6中的模板字符串对字符串进行拼接，避免使用加号+和join方法。

**建议规范**

- 当使用 _dirname 和 _filename 时不允许字符串拼接，windows和unix路径分隔符不同，为了避免混淆并且创建正确的路径，Node.js 提供了 path模块，例如：

```js
var fullPath = path.join(__dirname, "foo.js");
var fullPath = path.resolve(__dirname, "foo.js");
```
**涉及eslint规则**

```js
'quotes': ['error', 'single'], // 字符串开头和结束使用单引号
'prefer-template': 'error', // 使用模板而非字符串连接
'no-path-concat': 'error', // 当使用 _dirname 和 _filename 时不允许字符串拼接
'no-useless-concat': 'error', // 禁止没有必要的字符拼接
```
### 2.6 对象
**百度规范**

- [强制] 使用对象字面量 {} 创建新 Object。
- [强制] 对象创建时，如果一个对象的所有 属性 均可以不添加引号，则所有 属性 不得添加引号。
- [强制] 对象创建时，如果任何一个 属性 需要添加引号，则所有 属性 必须添加 '。
- [强制] 不允许修改和扩展任何原生对象和宿主对象的原型。
- [建议] 属性访问时，尽量使用 .。
- [建议] for in 遍历对象时, 使用 hasOwnProperty 过滤掉原型中的属性。

**涉及eslint规则**

```js
'comma-dangle': ['error', 'never'], // 多行对象字面量中要求拖尾逗号
'no-dupe-keys': 'error', // 禁止在对象字面量中出现重复的键
'no-prototype-builtins': 'error', // 禁止直接使用 Object.prototypes 的内置属性 
'dot-notation': 'error', //强制在任何允许的时候使用点号访问属性
'no-extend-native': 'error', // 禁止扩展原生对象
'no-new-object': 'error', // 禁止使用 Object 构造函数
'object-shorthand': ['error', 'always'], //要求对象字面量简写语法 
```

### 2.7 数组
**百度规范**

- [强制] 使用数组字面量 [] 创建新数组，除非想要创建的是指定长度的数组。
- [强制] 遍历数组不使用 for in。
- [建议] 不因为性能的原因自己实现数组排序功能，尽量使用数组的 sort 方法。

**涉及eslint规则**

```js
'no-sparse-arrays': 'error', // 禁用稀疏数组
'no-array-constructor': 'error', //禁止使用 Array 构造函数
```

### 2.8 函数
**百度规范**

- [建议] 一个函数的长度控制在 50 行以内。
- [建议] 一个函数的参数控制在 6 个以内。
- [建议] 通过 options 参数传递非数据输入型参数。

**涉及eslint规则**

```js
'no-dupe-args': 'error', // 禁止在 function 定义中出现重复的参数 
'no-new-func': 'error', // 禁用Function构造函数
'no-return-assign': 'error', // 禁止在返回语句中赋值 
'func-style': ['error', 'expression', { 'allowArrowFunctions': true }], // 统一函数风格为函数表达式或函数声明，并且允许使用箭头函数
'newline-before-return': 'error', // 要求 return 语句之前有一空行 
```

### 2.9 闭包
**百度规范**

- [建议] 在适当的时候将闭包内大对象置为 null。
- [建议] 使用 IIFE 避免 Lift 效应。

### 2.10 空函数
**百度规范**
- [建议] 空函数不使用 new Function() 的形式。
- [建议] 对于性能有高要求的场合，建议存在一个空函数的常量，供多处使用共享。

### 2.11 面向对象
**百度规范**

- [强制] 类的继承方案，实现时需要修正 constructor。
- [建议] 声明类时，保证 constructor 的正确性。
- [建议] 属性在构造函数中声明，方法在原型中声明。

**涉及eslint规则**

```js
'new-cap': 'error', // 要求构造函数首字母大写
```
### 2.12 动态特性
**百度规范**
 - [强制] 避免使用直接 eval 函数。
 - [建议] 使用 new Function 执行动态代码。
 - [建议] 尽量不要使用 with。
 - [建议] 减少 delete 的使用。
 - [建议] 处理 delete 可能产生的异常。
 - [建议] 避免修改外部传入的对象。
 - [建议] 具备强类型的设计。

## 3、其他最佳实践或规范

- 必须使用强制模式,即必须在文件开头加入强制模式开关use strict;
- 避免使用 console 的方法被认为是一种最佳实践。在发布到产品之前应该剔除 console 的调用。
- 禁止空块语句,但允许出现空的 catch 子句
- 禁止不必要的布尔类型转换
- 禁用不必要的分号
- 禁用 eval()
- 禁用 with 语句
- 禁止使用令人困惑的多行表达式。
- 禁止在 return、throw、continue 和 break 语句后出现不可达代码
- 禁止在 finally 语句块中出现控制流语句
- 强制 typeof 表达式与有效的字符串进行比较,有效字符串为下面其中的一个："undefined"、"object"、"boolean"、"number"、"string"、"function" 和 "symbol"
- 词法声明在整个 switch 语句块中是可见的，但是它只有在运行到它定义的 case 语句时，才会进行初始化操作。为了保证词法声明语句只在当前 case 语句中有效，将你子句包裹在块中。
- 禁止通过 new 操作符使用 String、Number 和 Boolean
- 禁用不必要的转义,对字符串和正则表达式中的常规字符进行转义，不会对结果产生任何影响
- 强制回调错误处理
**涉及eslint规则**

```js
'strict': 'error', // 使用强制模式开关use strict;
'no-console': 'warn', // 禁用console，有助于代码发布前精简代码，调试时可忽略此规则
'no-empty': ['error', { 'allowEmptyCatch': true }], // 禁止空块语句,但允许出现空的 catch 子句
'no-extra-boolean-cast': 'error', // 禁止不必要的布尔类型转换
'no-extra-parens': 'error', // 禁止冗余的括号
'no-extra-semi': 'error', // 禁用不必要的分号
'no-eval': 'error', // 禁用 eval()
'no-with': 'error', // 禁用 with 语句
'no-unexpected-multiline': 'error', // 禁止使用令人困惑的多行表达式。
'no-unreachable': 'error', // 禁止在 return、throw、continue 和 break 语句后出现不可达代码
'no-unsafe-finally': 'error', // 禁止在 finally 语句块中出现控制流语句
'valid-typeof': 'error', //强制 typeof 表达式与有效的字符串进行比较
'no-case-declarations': 'error', // 禁止在 case 或 default 子句中出现词法声明
'no-new-wrappers': 'error', // 禁止通过 new 操作符使用 String、Number 和 Boolean
'no-useless-escape': 'error', // 禁用不必要的转义
'handle-callback-err': 'error', // 强制回调错误处理 
```

