# sqlite架构

> 翻译https://sqlite.org/arch.html

<svg xmlns="http://www.w3.org/2000/svg" style="font-size:initial;" class="pikchr" width="367" height="453" viewBox="0 0 490.32 605.52">
<path d="M2.16,293.76L236.16,293.76L236.16,2.16L2.16,2.16Z" style="fill:rgb(216,236,208);stroke-width:2.16;stroke:rgb(0,0,0);"></path>
<path d="M2.16,603.36L236.16,603.36L236.16,311.76L2.16,311.76Z" style="fill:rgb(208,236,232);stroke-width:2.16;stroke:rgb(0,0,0);"></path>
<path d="M254.16,347.76L488.16,347.76L488.16,2.16L254.16,2.16Z" style="fill:rgb(232,216,208);stroke-width:2.16;stroke:rgb(0,0,0);"></path>
<path d="M254.16,603.36L488.16,603.36L488.16,394.56L254.16,394.56Z" style="fill:rgb(224,236,200);stroke-width:2.16;stroke:rgb(0,0,0);"></path>
<path d="M38.16,92.16L200.16,92.16L200.16,38.16L38.16,38.16Z" style="fill:rgb(255,255,255);stroke-width:2.16;stroke:rgb(0,0,0);"></path>
<text x="119.16" y="65.16" text-anchor="middle" fill="rgb(0,0,0)" font-size="110%" dominant-baseline="central">Interface</text>
<polygon points="119.16,120.96 114.84,109.44 123.48,109.44" style="fill:rgb(0,0,0)"></polygon>
<path d="M119.16,92.16L119.16,115.2" style="fill:none;stroke-width:2.16;stroke:rgb(0,0,0);"></path>
<path d="M38.16,174.96L200.16,174.96L200.16,120.96L38.16,120.96Z" style="fill:rgb(255,255,255);stroke-width:2.16;stroke:rgb(0,0,0);"></path>
<text x="119.16" y="135.209" text-anchor="middle" fill="rgb(0,0,0)" font-size="110%" dominant-baseline="central">SQL&nbsp;Command</text>
<text x="119.16" y="160.711" text-anchor="middle" fill="rgb(0,0,0)" font-size="110%" dominant-baseline="central">Processor</text>
<polygon points="119.16,203.76 114.84,192.24 123.48,192.24" style="fill:rgb(0,0,0)"></polygon>
<path d="M119.16,174.96L119.16,198" style="fill:none;stroke-width:2.16;stroke:rgb(0,0,0);"></path>
<path d="M38.16,257.76L200.16,257.76L200.16,203.76L38.16,203.76Z" style="fill:rgb(255,255,255);stroke-width:2.16;stroke:rgb(0,0,0);"></path>
<text x="119.16" y="230.76" text-anchor="middle" fill="rgb(0,0,0)" font-size="110%" dominant-baseline="central">Virtual&nbsp;Machine</text>
<polygon points="119.16,347.76 114.84,336.24 123.48,336.24" style="fill:rgb(0,0,0)"></polygon>
<path d="M119.16,257.76L119.16,342" style="fill:none;stroke-width:2.16;stroke:rgb(0,0,0);"></path>
<path d="M38.16,401.76L200.16,401.76L200.16,347.76L38.16,347.76Z" style="fill:rgb(255,255,255);stroke-width:2.16;stroke:rgb(0,0,0);"></path>
<text x="119.16" y="374.76" text-anchor="middle" fill="rgb(0,0,0)" font-size="110%" dominant-baseline="central">B-Tree</text>
<polygon points="119.16,430.56 114.84,419.04 123.48,419.04" style="fill:rgb(0,0,0)"></polygon>
<path d="M119.16,401.76L119.16,424.8" style="fill:none;stroke-width:2.16;stroke:rgb(0,0,0);"></path>
<path d="M38.16,484.56L200.16,484.56L200.16,430.56L38.16,430.56Z" style="fill:rgb(255,255,255);stroke-width:2.16;stroke:rgb(0,0,0);"></path>
<text x="119.16" y="457.56" text-anchor="middle" fill="rgb(0,0,0)" font-size="110%" dominant-baseline="central">Pager</text>
<polygon points="119.16,513.36 114.84,501.84 123.48,501.84" style="fill:rgb(0,0,0)"></polygon>
<path d="M119.16,484.56L119.16,507.6" style="fill:none;stroke-width:2.16;stroke:rgb(0,0,0);"></path>
<path d="M38.16,567.36L200.16,567.36L200.16,513.36L38.16,513.36Z" style="fill:rgb(255,255,255);stroke-width:2.16;stroke:rgb(0,0,0);"></path>
<text x="119.16" y="540.36" text-anchor="middle" fill="rgb(0,0,0)" font-size="110%" dominant-baseline="central">OS&nbsp;Interface</text>
<path d="M290.16,92.16L452.16,92.16L452.16,38.16L290.16,38.16Z" style="fill:rgb(255,255,255);stroke-width:2.16;stroke:rgb(0,0,0);"></path>
<text x="371.16" y="65.16" text-anchor="middle" fill="rgb(0,0,0)" font-size="110%" dominant-baseline="central">Tokenizer</text>
<polygon points="371.16,120.96 366.84,109.44 375.48,109.44" style="fill:rgb(0,0,0)"></polygon>
<path d="M371.16,92.16L371.16,115.2" style="fill:none;stroke-width:2.16;stroke:rgb(0,0,0);"></path>
<path d="M290.16,174.96L452.16,174.96L452.16,120.96L290.16,120.96Z" style="fill:rgb(255,255,255);stroke-width:2.16;stroke:rgb(0,0,0);"></path>
<text x="371.16" y="147.96" text-anchor="middle" fill="rgb(0,0,0)" font-size="110%" dominant-baseline="central">Parser</text>
<polygon points="371.16,203.76 366.84,192.24 375.48,192.24" style="fill:rgb(0,0,0)"></polygon>
<path d="M371.16,174.96L371.16,198" style="fill:none;stroke-width:2.16;stroke:rgb(0,0,0);"></path>
<path d="M290.16,311.76L452.16,311.76L452.16,203.76L290.16,203.76Z" style="fill:rgb(255,255,255);stroke-width:2.16;stroke:rgb(0,0,0);"></path>
<text x="371.16" y="245.009" text-anchor="middle" fill="rgb(0,0,0)" font-size="110%" dominant-baseline="central">Code</text>
<text x="371.16" y="270.511" text-anchor="middle" fill="rgb(0,0,0)" font-size="110%" dominant-baseline="central">Generator</text>
<path d="M290.16,484.56L452.16,484.56L452.16,430.56L290.16,430.56Z" style="fill:rgb(255,255,255);stroke-width:2.16;stroke:rgb(0,0,0);"></path>
<text x="371.16" y="457.56" text-anchor="middle" fill="rgb(0,0,0)" font-size="110%" dominant-baseline="central">Utilities</text>
<path d="M290.16,567.36L452.16,567.36L452.16,513.36L290.16,513.36Z" style="fill:rgb(255,255,255);stroke-width:2.16;stroke:rgb(0,0,0);"></path>
<text x="371.16" y="540.36" text-anchor="middle" fill="rgb(0,0,0)" font-size="110%" dominant-baseline="central">Test&nbsp;Code</text>
<polygon points="290.16,78.66 281.572,87.4699 277.897,79.6505" style="fill:rgb(0,0,0)"></polygon>
<path d="M200.16,120.96L284.947,81.1101" style="fill:none;stroke-width:2.16;stroke:rgb(0,0,0);"></path>
<polygon points="200.16,174.96 212.033,178.185 206.985,185.197" style="fill:rgb(0,0,0)"></polygon>
<path d="M290.16,239.76L204.834,178.326" style="fill:none;stroke-width:2.16;stroke:rgb(0,0,0);"></path>
<text x="20.16" y="147.96" text-anchor="middle" font-style="italic" fill="rgb(0,0,0)" font-size="110%" transform="rotate(-90 20.16,147.96)" dominant-baseline="central">Core</text>
<text x="20.16" y="457.56" text-anchor="middle" font-style="italic" fill="rgb(0,0,0)" font-size="110%" transform="rotate(-90 20.16,457.56)" dominant-baseline="central">Backend</text>
<text x="470.16" y="174.96" text-anchor="middle" font-style="italic" fill="rgb(0,0,0)" font-size="110%" transform="rotate(-90 470.16,174.96)" dominant-baseline="central">SQL&nbsp;Compiler</text>
<text x="470.16" y="498.96" text-anchor="middle" font-style="italic" fill="rgb(0,0,0)" font-size="110%" transform="rotate(-90 470.16,498.96)" dominant-baseline="central">Accessories</text>
</svg>

## Introduction

This document describes the architecture of the SQLite library.

本文件描述了SQLite库的架构。

The information here is useful to those who want to understand or modify the inner workings of SQLite.

这里的信息对于那些想要理解或修改SQLite内部工作原理的人来说是有用的。



A nearby diagram shows the main components of SQLite and how they interoperate.

附近的图表展示了SQLite的主要组件及其如何互相操作。

The text below explains the roles of the various components.

下面的文字解释了各个组件的角色。

## Overview

SQLite works by compiling SQL text into bytecode, then running that bytecode using a virtual machine.

SQLite 通过将 SQL 文本编译为字节码，然后使用虚拟机运行这些字节码来工作。



The *sqlite3_prepare_v2()* and related interfaces act as a compiler for converting SQL text into bytecode.

*sqlite3_prepare_v2()* 及相关接口充当将 SQL 文本转换为字节码的编译器。

The *sqlite3_stmt* object is a container for a single bytecode program that implements a single SQL statement.

*sqlite3_stmt* 对象是实现单个 SQL 语句的单个字节码程序的容器。

The sqlite3_step() interface passes a bytecode program into the virtual machine, and runs the program until it either completes, or forms a row of result to be returned, or hits a fatal error, or is interrupted.

sqlite3_step() 接口将字节码程序传递给虚拟机，并运行该程序，直到其完成、形成要返回的结果行、遇到致命错误或被中断。

## Interface

Much of the C-language Interface is found in source files main.c, legacy.c, and vdbeapi.c though some routines are scattered about in other files where they can have access to data structures with file scope.

大部分的C语言接口可以在源文件 main.c、legacy.c 和 vdbeapi.c 中找到，尽管有些例程分散在其他文件中，以便它们可以访问具有文件作用域的数据结构。

The sqlite3_get_table() routine is implemented in table.c.

sqlite3_get_table() 例程实现在 table.c 文件中。

The sqlite3_mprintf() routine is found in printf.c.

sqlite3_mprintf() 例程位于 printf.c 文件中。

The sqlite3_complete() interface is in complete.c.

sqlite3_complete() 接口在 complete.c 文件中。

The TCL Interface is implemented by tclsqlite.c.

TCL 接口由 tclsqlite.c 文件实现。



To avoid name collisions, all external symbols in the SQLite library begin with the prefix sqlite3.

为了避免名称冲突，SQLite 库中的所有外部符号都以前缀 sqlite3 开始。

Those symbols that are intended for external use (in other words, those symbols which form the API for SQLite) add an underscore, and thus begin with sqlite3_.

那些用于外部使用的符号（换句话说，构成 SQLite API 的符号）添加一个下划线，因此以 sqlite3_ 开始。

Extension APIs sometimes add the extension name prior to the underscore; for example: sqlite3rbu_ or sqlite3session_.

扩展 API 有时会在下划线之前添加扩展名；例如：sqlite3rbu_ 或 sqlite3session_。

## Tokenizer

When a string containing SQL statements is to be evaluated it is first sent to the tokenizer.

 当包含SQL语句的字符串需要被执行时，它首先会被发送到词法分析器。 

The tokenizer breaks the SQL text into tokens and hands those tokens one by one to the parser. 

词法分析器将SQL文本分解为标记，并将这些标记逐个传递给解析器。 

The tokenizer is hand-coded in the file tokenize.c. 

词法分析器是在文件 tokenize.c 中手写实现的。 



Note that in this design, the tokenizer calls the parser. 

请注意，在这种设计中，是词法分析器调用解析器。 

People who are familiar with YACC and BISON may be accustomed to doing things the other way around — having the parser call the tokenizer. 

熟悉YACC和BISON的人可能习惯于相反的做法——即让解析器调用词法分析器。

 Having the tokenizer call the parser is better, though, because it can be made threadsafe and it runs faster. 然而，让词法分析器调用解析器更好，因为它可以被设计为线程安全的，并且运行速度更快。

## Parser

The parser assigns meaning to tokens based on their context.

解析器根据标记的上下文为其赋予意义。

The parser for SQLite is generated using the Lemon parser generator.

SQLite的解析器是使用Lemon解析器生成器生成的。

Lemon does the same job as YACC/BISON, but it uses a different input syntax which is less error-prone.

Lemon与YACC/BISON的工作相同，但它使用了一种不同的输入语法，这种语法更不容易出错。

Lemon also generates a parser which is reentrant and thread-safe.

Lemon还生成一个可重入且线程安全的解析器。

And Lemon defines the concept of a non-terminal destructor so that it does not leak memory when syntax errors are encountered.

并且Lemon定义了非终结符析构函数的概念，这样在遇到语法错误时不会泄漏内存。

The grammar file that drives Lemon and that defines the SQL language that SQLite understands is found in parse.y.

驱动Lemon并定义SQLite理解的SQL语言的语法文件位于parse.y中。



Because Lemon is a program not normally found on development machines, the complete source code to Lemon (just one C file) is included in the SQLite distribution in the "tool" subdirectory.

由于Lemon是一个通常不在开发机上找到的程序，Lemon的完整源代码（只有一个C文件）包含在SQLite发行版的“tool”子目录中。

## Code Generator

After the parser assembles tokens into a parse tree, the code generator runs to analyze the parse tree and generate bytecode that performs the work of the SQL statement.

在解析器将标记组装成解析树之后，代码生成器会运行以分析该解析树并生成执行SQL语句工作的字节码。

The prepared statement object is a container for this bytecode.

预处理语句对象是这种字节码的容器。

There are many files in the code generator, including: attach.c, auth.c, build.c, delete.c, expr.c, insert.c, pragma.c, select.c, trigger.c, update.c, vacuum.c, where.c, wherecode.c, and whereexpr.c.

代码生成器中有许多文件，包括：attach.c、auth.c、build.c、delete.c、expr.c、insert.c、pragma.c、select.c、trigger.c、update.c、vacuum.c、where.c、wherecode.c和whereexpr.c。

In these files is where most of the serious magic happens.

在这些文件中发生了大部分重要的“魔法”。

expr.c handles code generation for expressions.

expr.c负责表达式的代码生成。

where*.c handles code generation for WHERE clauses on SELECT, UPDATE and DELETE statements.

where*.c负责SELECT、UPDATE和DELETE语句中的WHERE子句的代码生成。

The files attach.c, delete.c, insert.c, select.c, trigger.c update.c, and vacuum.c handle the code generation for SQL statements with the same names.

文件attach.c、delete.c、insert.c、select.c、trigger.c、update.c和vacuum.c负责与这些文件同名的SQL语句的代码生成。

(Each of these files calls routines in expr.c and where.c as necessary.)

（这些文件根据需要调用expr.c和where.c中的例程。）

All other SQL statements are coded out of build.c.

所有其他SQL语句都是从build.c中编码出来的。

The auth.c file implements the functionality of sqlite3_set_authorizer().

auth.c文件实现了sqlite3_set_authorizer()的功能。



The code generator, and especially the logic in where*.c and in select.c, is sometimes called the query planner.

代码生成器，尤其是where*.c和select.c中的逻辑，有时被称为查询规划器。

For any particular SQL statement, there might be hundreds, thousands, or millions of different algorithms to compute the answer.

对于任何特定的SQL语句，可能有成百上千甚至上百万种不同的算法来计算答案。

The query planner is an AI that strives to select the best algorithm from these millions of choices.

查询规划器是一种人工智能，它力求从这数百万种选择中挑选出最佳算法。

## Bytecode Engine


The bytecode program created by the code generator is run by a virtual machine.

由代码生成器创建的字节码程序由虚拟机运行。



The virtual machine itself is entirely contained in a single source file vdbe.c.

虚拟机本身完全包含在一个源文件vdbe.c中。

The vdbe.h header file defines an interface between the virtual machine and the rest of the SQLite library and vdbeInt.h which defines structures and interfaces that are private to the virtual machine itself.

vdbe.h头文件定义了虚拟机与SQLite库其余部分之间的接口，而vdbeInt.h定义了虚拟机本身的私有结构和接口。

Various other vdbe*.c files are helpers to the virtual machine.

其他各种vdbe*.c文件是虚拟机的辅助文件。

The vdbeaux.c file contains utilities used by the virtual machine and interface modules used by the rest of the library to construct VM programs.

vdbeaux.c文件包含了虚拟机使用的工具以及库的其余部分用于构造VM程序的接口模块。

The vdbeapi.c file contains external interfaces to the virtual machine such as the sqlite3_bind_int() and sqlite3_step().

vdbeapi.c文件包含了虚拟机的外部接口，例如sqlite3_bind_int()和sqlite3_step()。

Individual values (strings, integer, floating point numbers, and BLOBs) are stored in an internal object named "Mem" which is implemented by vdbemem.c.

单独的值（字符串、整数、浮点数和BLOB）存储在一个名为“Mem”的内部对象中，该对象由vdbemem.c实现。



SQLite implements SQL functions using callbacks to C-language routines.

SQLite通过回调到C语言例程来实现SQL函数。

Even the built-in SQL functions are implemented this way.

即使是内置的SQL函数也是这样实现的。

Most of the built-in SQL functions (ex: abs(), count(), substr(), and so forth) can be found in func.c source file.

大多数内置的SQL函数（如abs()、count()、substr()等）可以在func.c源文件中找到。

Date and time conversion functions are found in date.c.

日期和时间转换函数位于date.c文件中。

Some functions such as coalesce() and typeof() are implemented as bytecode directly by the code generator.

某些函数，如coalesce()和typeof()，直接由代码生成器作为字节码实现。

## B-Tree

An SQLite database is maintained on disk using a B-tree implementation found in the btree.c source file.

SQLite数据库使用btree.c源文件中的B树实现维护在磁盘上。

Separate B-trees are used for each table and each index in the database.

数据库中的每个表和每个索引都使用单独的B树。

All B-trees are stored in the same disk file.

所有B树都存储在同一个磁盘文件中。

The file format details are stable and well-defined and are guaranteed to be compatible moving forward.

文件格式细节是稳定的、定义良好的，并且保证向前兼容。



The interface to the B-tree subsystem and the rest of the SQLite library is defined by the header file btree.h.

B树子系统与SQLite库其余部分之间的接口由头文件btree.h定义。

## Page Cache

The B-tree module requests information from the disk in fixed-size pages.

B树模块以固定大小的页面从磁盘请求信息。

The default page_size is 4096 bytes but can be any power of two between 512 and 65536 bytes.

默认的页面大小是4096字节，但可以是512到65536字节之间的任何2的幂。

The page cache is responsible for reading, writing, and caching these pages.

**页面缓存负责读取、写入和缓存这些页面。**

The page cache also provides the rollback and atomic commit abstraction and takes care of locking of the database file.

页面缓存**还提供了回滚和原子提交抽象，并处理数据库文件的锁定。**

The B-tree driver requests particular pages from the page cache and notifies the page cache when it wants to modify pages or commit or rollback changes.

B树驱动程序从页面缓存中请求特定页面，并在需要修改页面或提交或回滚更改时通知页面缓存。

The page cache handles all the messy details of making sure the requests are handled quickly, safely, and efficiently.

页面缓存处理所有复杂的细节，确保请求被快速、安全且高效地处理。



The primary page cache implementation is in the pager.c file.

主要的页面缓存实现在pager.c文件中。

WAL mode logic is in the separate wal.c.

WAL模式逻辑位于单独的wal.c文件中。

In-memory caching is implemented by the pcache.c and pcache1.c files.

内存中的缓存由pcache.c和pcache1.c文件实现。

The interface between page cache subsystem and the rest of SQLite is defined by the header file pager.h.

页面缓存子系统与SQLite其余部分之间的接口由头文件pager.h定义。

## OS Interface

In order to provide portability across operating systems, SQLite uses an abstract object called the VFS.

为了提供跨操作系统的可移植性，SQLite使用了一个称为VFS的抽象对象。

Each VFS provides methods for opening, reading, writing, and closing files on disk, and for other OS-specific tasks such as finding the current time, or obtaining randomness to initialize the built-in pseudo-random number generator.

每个VFS提供了打开、读取、写入和关闭磁盘文件的方法，以及执行其他特定于操作系统的任务（如查找当前时间或获取随机数以初始化内置的伪随机数生成器）的方法。

SQLite currently provides VFSes for unix (in the os_unix.c file) and Windows (in the os_win.c file).

SQLite目前为Unix（在os_unix.c文件中）和Windows（在os_win.c文件中）提供了VFS。

## Utilities

Memory allocation, caseless string comparison routines, portable text-to-number conversion routines, and other utilities are located in util.c.

内存分配、不区分大小写的字符串比较例程、可移植的文本到数字转换例程及其他实用工具位于util.c文件中。

Symbol tables used by the parser are maintained by hash tables found in hash.c.

解析器使用的符号表由hash.c文件中的哈希表维护。

The utf.c source file contains Unicode conversion subroutines.

utf.c源文件包含了Unicode转换子程序。

SQLite has its own private implementation of printf() (with some extensions) in printf.c and its own pseudo-random number generator (PRNG) in random.c.

SQLite在printf.c文件中有自己的私有实现版本的printf()（带有一些扩展），并在random.c文件中有自己的伪随机数生成器（PRNG）。

## Test Code

Files in the "src/" folder of the source tree whose names begin with test are for testing only and are not included in a standard build of the library.

源代码树中"src/"文件夹里名称以test开头的文件仅供测试使用，并不包含在库的标准构建中。

------

*This page last modified on [2022-04-18 02:55:50](https://sqlite.org/docsrc/finfo/pages/arch.in?m=5dd2504487) UTC*
