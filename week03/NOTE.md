# 学习笔记 #

## Grammar ##

- Tree vs Priority
  - +、-
  - *、/
  - ()

## Expressions ##

- Member
  - a.b
  - a[b]
  - foo\`string\`
  - super.b
  - super['b']
  - new.target
  - new Foo()
- New
  - new Foo

Example:

```javascript
new a()()
new new a()
```

- Call
  - foo()
  - super()
  - foo()['b'
  - foo().b
  - foo()\`abc\`

Example:

```
new a()['b']
```

- Left Handside & Right Handside

Example:

```javascript
a.b=c; //left
a+b=c; //right wrong
```

- Update
  - a++
  - a--
  - --a
  - ++a

Example:

```
++a++
++(a++)
```

- Unary
  - delete a.b
  - void foo()
  - typeof a
  - +a //可能会发生类型转换
  - -a
  - ~a
  - !a
  - await a
- Exponental
  - **

Example:

```
3**2**3 //从右向左运算 3的（2的3次方）次方 === 3**（2**3）
```

- Multiplicative
  - */%
- Additive
  - +、-
- Shift
  - << >>> >>
- Relationship
  - < > <= >= instanceof
- Equality
  - ==
  - !=
  - ===
  - !==
- Bitwise
  - & ^ |
- Logical：短路原则
  - && 前为false，后不会执行
  - || 前为true，后不会执行
- Conditional：短路逻辑
  - ? : 前为true，后不会执行

## Reference ##

- Object
- Key
- delete
- assign

## Type Convertion ##

- a+b
- "false"==false
- a[o]=1

## Unboxing ##

- ToPremitive
- toString vs valueOf
- Symbol.toPrimitive

## Boxing ##

- Number->new Number(1)->1
- String->new String("a")->"a"
- Boolean->new Boolean(true)->true
- Symbol->new Object(Symbol("a"))->Symbol("a")

## 运行时相关概念 ##

### Completion Record

- [[type]]:normal,break,continue,return,or throw
- [[value]]:基本类型
- [[target]]:label

## 简单语句和复合语句 ##

### 简单语句

- ExpressionStatement //表达式语句
- EmptyStatement 
- DebuggerStatement //触发断点
- ThrowStatement //抛出异常
- ContinueStatement //结束当此循环
- BreakStatement //结束整个循环
- ReturnStatement 

### 复合语句

- BlockStatement

  - ```javascript
    {
    	xxx
    }
    ```

- IfStatement

- SwitchStatement //性能较高 if代替

- IterationStatement //while do while

  - while(){}
  - do{} while()
  - for( ; ; ){}
  - for(  in ){}
  - for(  of  ){}

- WithStatement //不确定性高，拒绝使用

- LabelledStatement

- TryStatement //try catch finally

  - try{}

    catch(){}

    finally{}

## 声名

- FunctionDeclaration
- GeneratorDeclaration
- AsyncFunctionDeclaration
- AsyncGeneratorDeclaration
- VariableStatement
- ClassDeclaration
- LexicalDeclaration

### 预处理

提前找到所有var声名的变量

所有的声名都有预处理机制

const：在声明前使用会报错

## 宏任务和微任务

### JS执行粒度（运行时）

- 宏任务
- 微任务（Promise）
- 函数调用（Execution Context）
- 语句/声名（Completion Record）
- 表达式（Reference）
- 直接量/变量/this

### 事件循环 ###

wait=>get code=>execute>wait...

