# 2022 WTR 招新试题集 by TITH

### 关键字
-  关键字 extern 和 static 修饰的变量特性和在使用中有什么不同之处？
-  关键字 inline 和 static 修饰的函数特性和在使用中有什么不同之处？

### C程序的内存区域
-  在 C 程序中，什么是堆区，什么是栈区？
-  一段 C 语言代码如下，请指出其中 var1, var2, var3, var4 和 malloc() 分配的内存各存储在哪个区域。var1~var4 和 *p 中，哪些初始值一定是 0？  


main.c 

```c
#include <stdio.h>

int var1;

int func(int var2)
{
	int var3;
	static int var4;
	void *p = malloc(4);
}
```

### 多文件编程

有如下 3 个文件，请补全以完成以下要求

- 在 main() 中调用 PrintAdd.c 中的 PrintAdd()，打印 4 + 5 的结果
- Add() 函数为 PrintAdd.c 内部使用的函数，不要将其暴露给 main.c
- 尽量不要出现 warning

提示：
1. printf() 需要 包含 stdio.h
2. 函数定义已经实现，请补充函数声明以及其他必要部分

main.c 
```c
#include "PrintAdd.h"

int main()
{
	PrintAdd(4,5);
	return 0;
}

```

PrintAdd.c
```c
#include "PrintAdd.h"
// TO DO

void PrintAdd(int x, int y)
{
	int result = Add(x, y);

	printf("%d\n", result);
}

static int Add(int x, int y)
{
	return x + y;
}

```

PrintAdd.h
```c
// TO DO

```
