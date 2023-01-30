函数命名原则：
1.  Function names are lowercase, with words separated by underscores. Descriptive names are encouraged.
函数名小写，用下划线分隔单词。最好用描述性名字
2.  Function names typically evoke operations applied to arguments by the interpreter (e.g., print, add, square) or the name of the quantity that results (e.g., max, abs, sum).
函数名指示变量或结果
3.  Parameter names are lowercase, with words separated by underscores. Single-word names are preferred.
参数名小写，用下划线分隔单词。最好用一个单词
4.  Parameter names should evoke the role of the parameter in the function, not just the kind of argument that is allowed.
参数名应对应参数在函数中作用，而不只是一种允许使用的变量
5.  Single letter parameter names are acceptable when their role is obvious, but avoid "l" (lowercase ell), "O" (capital oh), or "I" (capital i) to avoid confusion with numerals.
单字节参数名可以使用，如果他们的角色很明显。但应避免使用"l","o","i"，以免与数字混淆

函数设计原则：
-   Each function should have exactly one job. That job should be identifiable with a short name and characterizable in a single line of text. Functions that perform multiple jobs in sequence should be divided into multiple functions.
每个函数只应有一项职责。该职责应明确对应一个简称及一行注释。连续执行多项任务的函数应被分割成多个函数；
-   _Don't repeat yourself_ is a central tenet of software engineering. The so-called DRY principle states that multiple fragments of code should not describe redundant logic. Instead, that logic should be implemented once, given a name, and applied multiple times. If you find yourself copying and pasting a block of code, you have probably found an opportunity for functional abstraction.
"不要重复你自己"是软件工程一个核心信条。“DRY”原则指出多段代码不应描述重复逻辑。相反，一个逻辑只应植入一次，命名一次，并被多此应用。如果你发现自己复制粘贴一段代码，你可能发现了一个函数抽象的机会；
-   Functions should be defined generally. Squaring is not in the Python Library precisely because it is a special case of the pow function, which raises numbers to arbitrary powers.
函数定义应该通用。平方不是Python库里的函数，因为它只是pow函数的一种具体应用。

ps.与C、C++不同，Python用#表示注释 //是整除的意思

Python中的函数：
1.可用作函数参数
2.全局方法
3.嵌套定义
4.函数作为返回值