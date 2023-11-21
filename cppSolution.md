# c primer plus选题题解
<br>
<br>

---
## 第<font color=grey size=10>1</font>章
## 初识c语言
<br>
<br>

### 复习题
1. **对编程而言，可移植性意味着什么？**

```c
可移植性意味着在一种系统中编写的c程序在另一中系统中稍加修改或不修改就可以运行
```

2. **解释源代码文件，目标代码文件和可执行文件有什么区别？**
```c
源代码文件是指在程序编写中编写的代码内容存储的文件，文件名一般以”.c“，其中”.“号前面的被称为基本名，后面的被称为扩展名。

目标代码文件是指源代码经过编译转换后生成内容所存储的文件，一种常见的方式就是把源代码转为机器语言代码，再放入目标代码文件中。(目标代码文件缺少启动代码和库函数)

可执行文件是指通过链接器把目标文件，系统标准启动代码和库函数合并后形成的一个新的文件
```

3. **编程的七个主要步骤是什么？**
```c
定义程序的目标：明确程序所要达成的效果，程序的需求等；
设计程序：设计用什么样的方法步骤来达到程序的目标；
编写代码：把程序设计用代码实现；
编译：编译器将源代码编译成可执行代码，再由编译器调动链接器来链接合并源代码和库，生成可执行文件；(预处理，编译，汇编，链接)
运行程序；
测试和调试程序；
维护和修改代码；
```
4. **编译器的任务是什么**
```c
编译器通过编译将高级语言编写的源代码转换成目标平台的机器语言代码，生成目标文件，再经过链接库，启动代码等生成可执行文件(编译器的工作包括编译和链接两步)
```
5. **链接器的任务是什么**
```c
将编译生成的中间代码和系统库代码以及第三方代码合并，生成可执行文件。
```
###编程练习
1. **你刚被MacroMuscle有限公司聘用，该公司准备进入欧洲市场，需要一个把英寸转换成厘米(1 in = 2.54 cm)的程序，该程序需要提示用户输入英寸值，你的任务是定义程序目标和程序设计(编程的第一步和第二步)**
```c
1.用户输入转换数值。
2.读取用户的输入。
3.程序将输入值进行转换。
4.将结果输出给用户。
```
<br>

***

<br>

## 第<font color=grey size=10>2</font>章
## c语言概述
<br>

### 复习题
1. **c语言的基本模块是什么**
```c
c语言的基本模块是函数。函数是可以重复使用的具有某一功能的语句块，可以提高开发效率。
```
2. **什么是语法错误？给出一个中文例子和c语言例子**
```c
中文例子：“作业写”（宾语应该放在动词后面）
c语言例子：“int a = 1”（缺少分号）
```
3. **什么是语义错误？给出一个中文例子和c语言例子。**
```c
中文例子：“我喜欢学习”（语法上是正确的，但表达的含义不正确，因为我不喜欢学习，所以所谓语义错误是指用正确的语法表示错误的内容）
c语言例子：“a == 1；”（我们本来想将a赋值为1,但实际确实表示a和1是否相等）
```
4. **Indiana Sloth编写了下面的程序，并征求你的意见，请你帮他评定。**
```c
include studio.h
int main{void}
(
    int s
    s :=56;
    printf(There are s weeks in a year.);
    return 0;
```
改错如下
```c
#include<stdio.h>
int main(void)
{
    int s;
    s = 56;
    printf("There are %d weeks in a year",s);
    return 0;
}
```
5. **假如下面的4个例子都是完整程序的一部分，它们分别输出什么结果？**
```c
a. printf("Baa Baa Black Sheep.");
   printf("Have you any wool!?\n");
b. printf("Begone!\nO Creature of lard!\n");
c. printf("What?\nNo/nfish?\n");
d. int num;
   num = 2;
   printf("%d + %d = %d",num,num,num+num);
```
输出如下：
```c
a. Baa Baa Black Sheep.
   Have you any wool!?
   (这是空格)
b. Begone!
   O Creature of lard!
   (这是空格)
c. What?
   No/nfish?
   (这是空格)
d. 2 + 2 = 4
```
6. **在main ,int ,function ,char ,= 中，哪些是c语言的关键字**
```c
main ,char ,int是关键字. =是运算符 ,function是自定义的标识符。
```
7. **如何以下面的格式输出变量words和lines的值(这里，3020和350代表两个变量的值)。**
```c
There were 3020 words and 350 lines.
```
```c
int words = 3020;
int lines = 350;
printf("There were %d words and %d lines.",words,lines);
```
8. **考虑下面的程序。**
```c
#include<stdio.h>
int main(void)
{
    int a,b;
    a = 5;
    b = 2;  /*第七行*/
    b = a;  /*第八行*/
    a = b;  /*第九行*/
    printf("%d   %d\n",b,a);
    return 0;
}
```
请问，在执行完第7,8,9行后，程序的状态分别是什么。
```c
第七行：b被赋值为2；
第八行：b被赋值为a,为5；
第九行：a被赋值为b,为5；
```
9. **考虑下面的程序。**
```c
#include<stdio.h>
int main(void)
{
    int x,y;
    x = 10;
    y = 5;      /*第七行*/
    y = x + y;  /*第八行*/
    x = x*y;    /*第九行*/
    printf("%d   %d\n",x,y);
    return 0;
}
```
请问，在执行完第7,8,9行后，程序的状态分别是什么。
```c
第七行：y被赋值为5；
第八行：y等于y(5)加上x(10)为15；
第九行：x等于x(10)乘y(15)为150；
```
### 编程练习
1. **编写一个程序，调用一次printf()函数，ba你的名和姓打印在一行。再调用一次printf()函数，把你的名和姓分别打印到两行。然后，再调用两次printf()函数，把你的名和姓打印在一行。**
示例输出如下：
```c
Gustav Mahler  /*第一次打印内容*/
Gustav         /*第二次打印内容*/
Mahler         
Gustav Mahler  /*第三次打印内容*/
```

```c
#include<stdio.h>
int main(void)
{
    printf("Gustav Mahler");
    printf("Gustav\nMahler");
    printf("Gustav ");
    printf("Mahler");
    return 0;
}
```
2. **编写一个程序，打印你的姓名和地址。**
```c
#include<stdio.h>
int main(void)
{
    printf("名字\n地址");
    return 0;
}
```
3. **编写一个程序，把你的年龄换成天数，并显示年龄和天数。这里不用考虑闰年的问题。**
```c
#include<stdio.h>
#define year 365
int main(void)
{
    int age,day;
    scanf("%d",&age);
    day = age*year;
    printf("age=%d day=%d",age,day);
    return 0;
}
```
4. **编写一个程序，生成以下输出**
```c
For he's a jolly good fellow!
For he's a jolly good fellow!
For he's a jolly good fellow!
Which nobody can deny!
```
除main()函数外，该程序还要调用两个自定义函数：一个名为jolly()，用来打印前3条消息，调用一次打印一条；另一个函数名为deny()，打印最后一条消息。
```c
#include<stdio.h>
void jolly(void)
{
    printf("For he's a jolly good fellow!");
}
void deny(void)
{
    printf("Which nobody can deny!");
}

int main(void)
{
    jolly();
    jolly();
    jolly();
    deny();
    return 0;
}
```
5. **编写一个程序，生成以下输出**
```c
Brazil, Russia, India, China
India, China,
Brazil, Russia
```
除main()函数外，该程序还要调用两个自定义函数：一个名为br()，调用一次打印一次"Brazil, Russia"；另一个函数名为ic()，调用一次打印一次"India, China".其他功能在mian()函数实现。
```c
#include<stdio.h>
void br(void)
{
    printf("Brazil, Russia");
}
void ic(void)
{
    printf("India, China");
}

int main(void)
{
    printf("%s, %s\n%s,\n%s",br(),ic(),ic(),br());
    return 0;
}
```
6. **编写一个程序，创建一个整形变量toes,并将toes设置为10,程序中还要计算toes的两倍和toes的平方。该程序打印3个值，并分别描述以区别。**
```c
#include<stdio.h>
int main(void)
{
    int toes = 10;
    printf("toes = %d,toes的两倍 = %d,toes的平方 = %d"，toes,2*toes,toes*toes);
    return 0;
}
```
7. **许多研究表明，微笑多多益善，编写一个程序，生成以下格式的输出。**
```c
Smile!Smile!Smile!
Smile!Smile!
Smile!
```
该程序要定义一个函数，调用该函数一次打印一次“Smile!”，根据程序的需要使用该函数。
```c
#include<stdio.h>
void smile(void)
{
    printf("Smile!");
}

int main(void)
{
    smile();smile();smile();
    printf("\n");
    smile();smile();
    printf("\n");
    smile();
    return 0;
}
```
8. **在c语言中，一个函数可以调用另一个函数。编写一个程序，用于调用一个名为one_three()函数，该函数在一行打印“One”，再调用另一个函数two()，然后在另一行打印单词“three”。two()函数在一行显示单词“two”。main()函数在调用one_three()函数前要打印短语“Staring now：”，并在调用完毕后显示短语“Done！”。应此，该程序的输出如下所示。**
```c
Staring now;
one
two
three
Done!
```
```c
#include<stdio.h>
void two(void)
{
    printf("two\n");
}
void one_three(void)
{
    printf("one\n");
    two();
    printf("three");
}

int main(void)
{
    printf("Staring now：");
    one_three();
    printf("Done!");
}
```
<br>
<br>

## 第<font color=grey size=10>3</font>章
### 复习题
1. **指出下面各种数据使用的合适类型(有些可以使用多种类型)**
```c
East Simpleton的入口(short)
DVD的价格(float)
本章出现次数最多的字母(char)
本章出现次数最多的字母的次数(int)
```
2. **在什么情况下要用long类型的变量代替int类型的变量**
```
long所能储存的数据范围更大，当我们储存的数据超过int的储存范围时，我们会用long代替int.
```
3. **使用哪些可移植的数据类型可以获得32位有符号整数？选择的理由是什么**
c语言可移植数据类型
```
C语言中的可移植数据类型是指具有确定大小和范围的数据类型，其大小和范围在不同的平台上是一致的。这些数据类型被定义在C标准库的头文件 <stdint.h> 中，其中包含了以下可移植数据类型：

    整数类型：
        int8_t：有符号8位整数
        uint8_t：无符号8位整数
        int16_t：有符号16位整数
        uint16_t：无符号16位整数
        int32_t：有符号32位整数
        uint32_t：无符号32位整数
        int64_t：有符号64位整数
        uint64_t：无符号64位整数

    最小宽度的整数类型：
        int_least8_t：至少8位的有符号整数
        uint_least8_t：至少8位的无符号整数
        int_least16_t：至少16位的有符号整数
        uint_least16_t：至少16位的无符号整数
        int_least32_t：至少32位的有符号整数
        uint_least32_t：至少32位的无符号整数
        int_least64_t：至少64位的有符号整数
        uint_least64_t：至少64位的无符号整数
        （"至少n位的有符号整数"指的是一个有符号整数类型，其大小至少为n位。这意味着它可以容纳至少n个二进制位。）

    最快宽度的整数类型：
        int_fast8_t：最快宽度的有符号整数
        uint_fast8_t：最快宽度的无符号整数
        int_fast16_t：最快宽度的有符号整数
        uint_fast16_t：最快宽度的无符号整数
        int_fast32_t：最快宽度的有符号整数
        uint_fast32_t：最快宽度的无符号整数
        int_fast64_t：最快宽度的有符号整数
        uint_fast64_t：最快宽度的无符号整数
（"最快宽度的有符号整数"指的是一个有符号整数类型，其大小是在当前平台上具有最高性能的整数类型。这意味着在当前平台上，这个整数类型的读写操作是最高效的。）
    指针相关类型：
        intptr_t：整数类型，足够容纳指针的值
        uintptr_t：无符号整数类型，足够容纳指针的值

这些可移植数据类型的定义保证了它们在不同平台上的大小和范围是一致的，使得编写可移植的C代码更加方便和可靠。
```
4. **指出下列常量的类型和含义**
```
'\b'   表示单个字符，\b表示退格字符
1066   表示一个整形常量
99.44  表示一个浮点数常量
0XAA   表示一个十六进制(对于八进制和十六进制整形数据，系统优先解释为无符号类型)
2.0e30 表示双精度浮点常量(编译器通常将浮点型常量解释为双精度类型)
```
5. **Dottie Cawm编写了一个程序，请找出其中的错误。**
```c
include<stdio.h>
main(
    float g;h;
    float tax,rate;
    g=e21;
    tax = rate*g;
)
```
修改如下
```c
#include<stdio.h>
int main(void)
{
    float g,h;
    float tax,rate;
    g=1.0e21;
    rate=0.08;
    tax=rate*g;
    h = g+tax;
    return 0;
}
```
6. **写出下列常量在声明中使用的数据类型和在printf()中对应的转换说明。**
```
12            int                    %d
0X3           unsigned int(十六进制)  %#x
‘C’           char                   %c
2.34e07       double                 %e(%e 是一个转换说明符，用于格式化输出浮点数类型中的科学计数法表示)
'\040'        char                   %c 
7.0           double                 %lf
6L            long                   %ld
6.0f          float                  %f
0x5.b6p12     float                  %a(%a 转换说明符用于将浮点数以十六进制格式输出，并且在输出中包含指数部分)
```
7. **写出下列常量在声明中使用的数据类型和在printf()中对应的转换说明(假设int为16位)**
```
012           unsigned int(八进制)    %#o
2.9e05L       long double            %Le
's'           char                   %c
100000        long                   %ld
'\n'          char                   %c
20.0f         float                  %f
0x44          unsigned int           %#x
-40           int                    %d
```
8. **假设程序的开头有以下声明。**
```c
int imate = 2;
long shot = 53456;
char grade = 'A';
float log = 2.71828;
```
把下面的printf()语句中的转换字符补充完整。
```
printf("The odds against the %d were %ld to 1.\n",imate,shot);
printf("A score of %f is not an %c grade.\n",log,grade);
```
9. **假设ch是char类型的变量，分别用转义序列，十进制，八进制和十六进制把回车字符赋给ch.**
```
char ch = '\r';
char ch = 13;
char ch = '\015';
char ch = '\xd';
```
10. **修正下面的程序**
```c
void main(int) /this program is perfect/
{
    cows,legs,integer;
    printf("How many cows legs did you count?\n");
    scanf("%c",legs);
    cows = legs/4;
    printf("That implies there are %f cows,\n",cows);
}
```
修改如下
```c
#include<stdio.h>
intt main(void)
{
    int cows,legs;
    printf("How many cows legs did you count?\n");
    scanf("%d",&legs);
    cows = legs/4;
    printf("That implies there are %d cows,\n",cows);
}
```
11. **指出下列转义序列的含义**
```
\n        表示换行
\\        表示转义\
\"        表示转义“
\t        表示水平制表符
```
<br>

### 编程题
1. **通过试验(即编写带有此类问题的程序)观察系统如何处理整数上溢，浮点数上溢和浮点数下溢的情况。**
```c
#include<stdio.h>
int main(void)
{
    int a=2147483647;
    float b=3.4e38;
    float c=0.111111111;
    printf("a=%d\n",a+1);
    printf("b=%f\n",b+1);
    printf("c=%f\n",c);
    return 0;
}
```
```
a=-2147483648
b=339999995214436424907732413799364296704.000000
c=0.111111
```
2. **编写一个程序，要求提示输入一个ASCII码值，然后打印输出的字符。**
```c
#include<stdio.h>
int main(void)
{
    int a;
    printf("请输入字符的ASCII码：");
    scanf("%d",&a);
    printf("%c\n",a);
    return 0;
}
```
3. **编写一个程序，发出一声警报，然后打印下列文本。**
```
Starled by the sudden sound, Sally shouted,
"By the Great Pumpkin, what was that!"
```
程序如下：
```c
#include<stdio.h>
int main(void)
{
    char a='\a';
    printf("%c",a);
    printf("Starled by the sudden sound, Sally shouted,\n\"By the Great Pumpkin, what was that!\"");
}
```
4. **编写一个程序，读取一个浮点数，先打印小数形式，后打印指数形式。然后，如果系统支持，再打印p计数法(即十六进制计数法)。按以下格式输出。**
```c
#include<stdio.h>
int main(void)
{
    float a;
    printf("请输入一个浮点数：");
    scanf("%f",&a);
    printf("%f\n",a);
    printf("%e\n",a);
    printf("%a\n",a);
    return 0;
}
```
```
1.250000
1.250000e+00
0x1.4p+0
```
5. **一年大约有3.156 x 10^7秒。编写一个程序，提示用户输入年龄，然后显示该年龄对应的秒数。**
```c
#include<stdio.h>
define year_second 3.156e7
int main(void)
{
    double second,year;
    printf("请输入您的年龄：");
    scanf("%lf",&year);
    second=year*year_second;
    printf("您的年龄对应的秒数为%e\n",second);
    return 0;
}
```
6. **一个水分子的质量约为3.0 x 10^-32克。1夸脱(1夸脱=0.000946立方米)水的质量大约是950克。编写一个程序，提示用户输入水的夸脱数，并显示水分子的数量。**
```c
#include<stdio.h>
#define WATER 3.0e-32
#deefine QURRT 950
in main(void)
{
    double nums,quartnums;
    printf("请输入夸脱的数量：");
    scanf("%lf",&quartnums);
    nums=quartnums*QUART/WATER;
    printf("水分子数为：%e",nums);
    return 0;
}
```
7. **1英寸相当于2.54厘米。编写一个程序，提示用户输入身高(单位是英寸)，然后以厘米为单位显示身高。**
```c
#include<stdio.h>
#define INCH_CM 2.54
in main(void)
{
    float height,inch;
    printf("请输入您的身高：");
    scanf("%f",&inch);
    height=inch*INCH_CM;
    printf("您的身高为：%.2f",height);
    return 0;
}
```
8. **在美国的测量体系中，1品脱(1品脱=0.4731765立方分米)等于2杯，1杯等于8盎司(1盎司=29.57353立方厘米)，1盎司大约等于2大汤勺，1大汤勺等于3茶勺。缩写一个程序，提示用户输入杯数，并且以品脱，盎司，汤勺，茶勺为单位显示等价容量。思考对于该程序，为何使用浮点型数据比整形数据更合适？**
```
在单位转化过程中，可能会出现浮点型数据，并且实际使用中，也可能有浮点型数据的输入
```
```c
#include<stdio.h>
#define PINT_CUP 2
#define CUP_OUNCE 8
#define OUNCE_SPOON 2
#define SPOON_TEA 3
int main(void)
{
    float numcup,pint,cup,ounce,spoon,tea;
    printf("请输入杯数：");
    scanf("%f",&numcup);
    pint=cup/PINT_CUP;
    ounce=cup*CUP_OUNCE;
    spoon=ounce*OUNCE_SPOON;
    tea=spoon*SPOON_TEA;
    printf("%f\n%f\n%f\n%f\n",pint,ounce,spoon,tea);
    return 0;
}
```
<br>

## 第<font color=grey size=10>4</font>章
### 复习题

1. **再次运行程序1清单4.1,但是在要求输入人名时，请输入名和姓(根据英文书写习惯，姓和名中间有一个空格)，看看程序会发生什么情况。为什么?**

