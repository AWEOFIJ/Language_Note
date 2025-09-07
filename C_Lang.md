# C 筆記 

`Note` `2025.02.02`

> GFDL: GNU Freedom Document License

- Last Update : [time=Sun, Sep 7, 2025 8:31 AM]

---

`C_Programing_Language_Learning_Note`

**C語言為編譯式語言**
> C語言是一種通用的、程序式編程，程式語言，支援結構化編程、詞法作用域和遞迴，使用靜態型別系統，並且廣泛用於系統軟體與應用軟體的開發。


#### 特點:
- 移植性高: C語言提供前置處理器來處理不同平台之間的問題。
- 強大類別庫: 內建功能強大的類別庫以及函示庫。
- 兼具高低階語言能力: C語言是一種指令式編程語言。
- 可模組化: 可自行製作函示庫使用 (有提供良好的介面呼叫方式)。

> Acknowledge

- [C語言 - Wikipedia](https://zh.wikipedia.org/zh-tw/C%E8%AF%AD%E8%A8%80)
- [time=Sun, Jun 29, 2025 8:17 AM]


### 開發環境

- [Dev C++](https://bloodshed.net/)
- [OnlineGDB](https://www.onlinegdb.com/)


#### 引入標頭檔

```=c
#include<stdio.h>
#include<stdlib.h>
```


#### 主程式區塊

```=c
int main(){
    /* 程式敘述 */
    /* -------------------- */
    
    /* 暫停指令 */
    /* system("pause"); */
    
    /* --- */
    return 0;
}
```


#### 範例

```=c
#include<stdio.h>
#include<stdlib.h>

#include<string.h> /* 使用char[]可以不用引入string */

int main(){
    
    char action[20]="Good"
    int observed=0
    
    / ... */

    if (observed == 1){
        /* action = "take action"; */
        /* printf(action); */
    }
    
    /* system("pause"); */
    return 0;
}
```


#### Print 格式

* 格式由"%"與格式字元組成，將輸出的數據轉換為指定的格式輸出，由"%"開始。
* 格式字元：d, o, x, u, c, s, f, e, g, ...。

> [C語言教學手冊 天瓏網路書局](https://www.tenlong.com.tw/products/9789574424849)

<!--  
```c=
%d 整形輸出，或%ld長整型輸出。
%o 以八進位數形式輸出整數。
%x 以十六進位數形式輸出整數，或輸出字串的位址。
%u 以十進位數輸出unsigned型資料(無符號數)。請注意%d與%u有無符號的數值範圍。
%c 用來輸出一個字元。
%s 用來輸出一個字串。
%f 用來輸出實數，以小數形式輸出，預設情況下保留小數點6位。
%.100f 用來輸出實數，保留小數點100位。
%e 以指數形式輸出實數。
%g 根據大小自動選f格式或e格式，且不輸出無意義的零。
%p 是列印位址(指標位址)，以十六進位的形式，全部顯示。
```
- [CSDN博客](https://blog.csdn.net/qq_32365567/article/details/55045942)
- [CSDN博客](https://blog.csdn.net/Young__Fan/article/details/90609247)
-->


#### 變數的資料型態
:::info
char 字元

int 整數

long 長整數

short 短整數

float 浮點數

double 倍精度浮點數
:::

:::warning
sign 有號

unsign 無號
:::


#### 基本資料型態

| 資料型態  |           | 型態說明     | 位元組(byte) | 表示範圍               |
| ---------- | --------- | ------------ | ------ | ---------------------- |
| 整數類型   | long int  | 長整數       | 4      | -2147483648~2147483647 |
|            | int       | 整數         | 4      | -2147483648~2147483647 |
|            | short int | 短整數       | 2      | -32768~32767           |
|            | char      | 字元         | 1      | 0~255                  |
| 浮點數類型 | float     | 浮點數       | 4      | 1.2e-38~3.4e38         |
|            | double    | 倍精度浮點數 | 8      | 2.2e-308~1.8e308       |
| 有號 | singed | 有號的變數可存放正值或負值 |  |  |
| 無號 | unsigned | 無號的變數只能存放正值 |  |  |


#### 無號整數

| 資料型態 | 型態說明 | 位元組 | 表示範圍 |
| -- | -- | -- | -- |
| unsigned long int | 無號長整數 | 4 | 0~4294927695 |
| unsigned int | 無號整數 | 4 | 0~4294927695 |
| unsigned short int | 無號短整數 | 2 | 0~65535 |


#### 基本型態資料的溢位

```c=
#include <stdio.h>
#include <stdlib.h>

int main()
{
    unsigned short int num = 32767;
    short pub = 32767;
    
    num += 1;
    pub += 1;
    
    printf("%d \n\n", num);
    printf("%d \n\n", pub);
    printf("Hello World");

    /* system("pause"); */
    return 0;
}
```


#### 字元型態 char

```
字元型態佔有一個位元組 (byte)，可以用來儲存字元。
通常字元會被編碼，ASCII是其中較為人知的編碼系統。
ASCII是American Standard Code for Information Interchange的縮寫，
用來制定電腦中每個符號對應的整數代碼，也叫做電腦的內碼(code)。
```

**Byte Reference**

```
每個ASCII碼佔了一個位元組，每個位元組有8個位元。
```

> [C The sizeof Operator - W3school](https://www.w3schools.com/c/c_data_types_sizeof.php)

> [位元組 - wiki]( https://zh.wikipedia.org/zh-tw/%E5%AD%97%E8%8A%82)


#### ASCII 範例

```c=
#include<stdio.h>
#include<stdlib.h>

int main(){
    
    char ch = 'a';

    printf("ch = %c \n", ch);
    printf("ASCII of ch = %d \n", ch);
    
    /* system("pause"); */
    return 0;
}
```


#### 常用的跳脫字元

| 跳脫字元 | 所代表的意義 | 十進位ASCII |
| -------- | ------------ | ----------- |
| \a | 警告音(alert) | 7 |
| \b | 倒退一格(backspace) | 8 |
| \n | 換行(new line) | 10 |
| \r | 歸位(carriage return) | 13 |
| \0 | 字串結束字元(null charactor) | 0 |
| \t | 跳格(tab) | 9 |
| \\ | 反斜線(backslash) | 92 |
| \' | 單引號(single quote) | 39 |
| \" | 雙引號(double quote) | 34 |



### 運算子的優先順序

| 優先順序 | 運算子              | 類別 | 結合性 |
| -------- | ------------------- | ---- | ------ |
| 1        | ()                  | 括號運算子 | 由左至右 |
| 1        | []                  | 方括號運算子 | 由左至右 |
| 2        | !、+(正號)、-(負號)   | 一元運算子 | 由右至左 |
| 2        | ~                   | 位元邏輯運算子 | 由右至左 |
| 2        | ++、--              | 遞增與遞減運算子 | 由右至左 |
| 3        | * 、/、%             | 算數運算子 | 由左至右 |
| 4        | +、-                | 算數運算子 | 由左至右 |
| 5        | <<、>>              | 位元左移、右移運算子 | 由左至右 |
| 6        | >、>=、<、<=         | 關係運算子 | 由左至右 |
| 7        | ==、!=              | 關係運算子 | 由左至右 |
| 8        | & (位元運算的AND)     | 位元邏輯運算子 | 由左至右 |
| 9        | ^ (位元運算的XOR)     | 位元邏輯運算子 | 由左至右 |
| 11       | &&                  | 邏輯運算子 | 由左至右 |
| 12       | \\|\\|              | 邏輯運算子 | 由左至右 |
| 13       | ?!                  | 條件運算子 | 由右至左 |
| 14       | =                   | 設定運算子 | 由右至左 |



#### 一元運算子

| 一元運算子 | 意義 | 範例 | 說明 |
| -------- | -------- | -------- | --- |
| + | 正號 | a=+5 | 同 a=5，相當於設定a=+5 |
| - | 負號 | a=-3 | 設定a=-3 |
| ! | NOT，否 | a=!b | 把b的值取NOT，在設定給a存放 |

```c=
#include<stdio.h>

int main(void)
{
    int b = 6;
    printf("!b=%d", !b);
    
    /* system("pause"); */
    return 0;
}
```

```
* output.
*
* !b=0
*
----------------*
```

- [time=Sat, Feb 22, 2025 8:26 AM]


#### 算數運算子

| 運算子 | 意義 | 範例 |     |
| ------ | ---- | ---- | --- |
| +      | 加法    | 5 + 2 = 7      |     |
| -      | 減法    | 5 - 2 = 3      |     |
| *      | 乘法    | 5 * 2 = 10     |     |
| /      | 除法    | 5 / 2 = 2    |     |

- note: `% 算餘數， 5 % 2 = 1 。` 
- note: `十進位小數使用 Decimal in C#`

- [time=Sun, Jun 29, 2025 1:30 PM]


#### 位元邏輯運算子

| 位元邏輯運算子 | 意義 |
| - | - |
| ~ | 位元NOT運算子 |
| & | 位元AND運算子 |
| \\| | 位元OR運算子 |
| ^ | 位元XOR運算子 |


#### 位元位移運算子

| 位元位移運算子 | 意義 |
| -------------- | ---- |
| num << n | 左移，將num的位元向左移n個位元 |
| num >> n | 右移，將num的位元項右移n個位元 |


- [time=Sun, Jun 1, 2025 10:23 AM]


#### Define 前置處理器

```c=
#include<stdio.h>
#define BEGIN {
#define END }

int main(void)
BEGIN
    printf("Hello World !");
    
    /* system("pause"); */
    return 0;
END
```

note: `C 語言中 typedef 可以用來擴充 C 原有的資料型態`
- [time=Wed, Jun 4, 2025 6:27 AM]


### 指標 Pointer
- 位址運算子【&】: 可用來取得變數的位址。
- 依址取值運算子【*】: 可取得指標所指向變數的內容。 

```c=
#include<stdio.h>
#include<stdlib.h>

int main(void)
{
    int *ptr, num=20;
    
    ptr = &num;
    
    printf("num=%d, &num=%p \n", num, &num);
    printf("ptr=%d, ptr=%p, &ptr=%p \n", *ptr, ptr, &ptr);
    
    /* system("pause"); */
    return 0;
}
```


#### C stdlib calloc() 函數

:::info
The calloc() function allocates memory, fills it with zeroes and returns a pointer to it.
:::

Parameter Values

| Parameter | Description |
| -------- | -------- |
| *amount*     | Specifies the amount of items to allocate memory for. |
| *size* | Specifies the size of each item measured in bytes. |

```c=
#include<stdio.h>
#include<stdlib.h>

int main()
{
    
    /* Allocate memory for a number of items */
    int num = 1;
    int num_i = 18;
    int *arr = calloc(num_i, sizeof(int));

    printf("%d", *arr);

    /* system("pause"); */
    return 0;
}
```

- [w3schools C calloc()](https://www.w3schools.com/c/ref_stdlib_calloc.php)
- [time=Tue, Mar 18, 2025 10:25 AM]


#### C stdlib malloc() 函數

:::info
The malloc() function allocates memory and returns a pointer to it. Unlike calloc() the memory is not initialized, so the values are unpredictable.
:::

Parameter Values

| Parameter | Description |
| -------- | -------- |
| *size*   | Specifies the number of bytes of memory to allocate.  |

```c=
#include<stdio.h>
#include<stdlib.h>

int main()
{
    int num = 1;
    int num_i = 18;
    
    int *ptr = malloc(num_i * sizeof(int));
        
    printf("%d", *ptr);
    
    /* system("pause"); */
    return 0;
}
```

- [w3schools C malloc()](https://www.w3schools.com/c/ref_stdlib_malloc.php)
- [time=Tue, Mar 18, 2025 11:02 AM]


#### 結構變數的使用及初值的設定

```c=
#include<stdio.h>
#include<stdlib.h>

typedef struct data
{
    char name[50];
    char gender;
    int math;
};

int main()
{
    struct data student = {"Andy", 1, 80};
    printf("%s", student.name);
    
    /* system("pause"); */
    
    return 0;
}
```
- [time=Sun, Aug 3, 2025 2:46 AM]


### Statement

#### If...Else statement

```c=
#include<stdio.h>

int main(){
    
    int observed=0;
    
    if (observed=1){
        return 1;
    } else {
        return observed;
    }
    
    /* system("pause"); */
    return 0;
}
```


#### While loop statement

```c=
#include<stdio.h>
#include<stdlib.h>

int main(){
    int i=0;
    
    while(i<=125){
        i++;
        print("%d\n", i);
        /* continue; */
    }
    
    /* system("pause"); */
    return 0;
}
```


#### Do While loop statement

```c=
#include<stdio.h>
#include<stdlib.h>

int main(){
    int i=0;
    
    do {
        i++;
        print("%d\n", i);
        /* continue; */
    } 
    while(i<=125);
    
    /* system("pause"); */
    return 0;
}
```


#### 數字替換函式 Swap Number

- [Swap number - GDB_Online_Editor](https://learn.onlinegdb.com/c_program_to_swap_two_numbers)
- [time=Sat, Mar 15, 2025 8:59 AM]


#### 陣列

```c=
#include <stdio.h>
#include <stdlib.h>

int main()
{
    /* - Element */
    
    int n[5]; /* 宣告陣列 */
    printf("int 陣列元素佔 %d 個位元組\n",sizeof(n[0]));
    printf("整個 int 陣列佔 %d 個位元組\n",sizeof(n));
    printf("陣列元素個數：%d\n",sizeof(n)/sizeof(n[0]));
    
    /* system("pause"); */   
    return 0;
}
```


#### 處理陣列

```c=
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int main()
{
    /* - Encode */
    
    char password[20];
    printf("請輸入密碼（可包含空白鍵）："); 
	
    /* gets(password); */  /* 輸入字串 */
    scanf("%s", password);  /* 輸入字串 */
    
    printf("加密後的密碼：");
    
    for(int i=0;i<strlen(password);i++)  /* 逐一處理字元 */
    {
        password[i]++;  /* 將字元碼加1 */
        printf("%c",password[i]);
    }
    
    printf("\n");
    
    /* system("pause"); */
    return 0;
}
```


### 函數
#### 階乘函式 (遞迴函數)
```c=
#include<stdio.h>
#include<stdlib.h>
int fac(int);

int fac(int n)
{
    if(n > 9) return 0;
    if(n > 1) return (n * fac(n - 1));
    else return 1;
}

int main()
{
    printf("fac(4)=%d \n", fac(4));
    /* system("pause"); */
    return 0;
}
```

- [time=Thu, Jun 19, 2025 6:02 AM]


### 演算法
#### 費波納契數列

```c=
#include <stdio.h>
int fib(int n);

int fib(int n)
{
    if(n < 0) return -1;
    if(n < 1) return 0;
    if(n > 9) return 0;
    if(n > 1) return fib(n - 2) + fib(n - 1);
    else return 1;
}

int main()
{
    printf("%d \n", fib(9));
    return 0;
}

/* n > 9 return 0 for redundant avoid computing */
/* https://stackoverflow.com/questions/3165293/fibonacci-sequence-in-c */
```

- [time=Sun, Jun 29, 2025 12:33 PM]


#### DAG (DFS vs BFS)

```c=
#include <stdio.h>
#include <stdlib.h>
#include <stdbool.h>

#define MAX 100
#define N 10

/* =========================
   Queue 模組 (FIFO)
   ========================= */
typedef struct {
    int data[MAX];
    int front;
    int rear;
} Queue;

void initQueue(Queue *q) {
    (*q).front = 0;
    (*q).rear = 0;
}

int isEmptyQueue(Queue *q) {
    return (*q).front == (*q).rear;
}

void enqueue(Queue *q, int value) {
    if ((*q).rear < MAX) {
        (*q).data[(*q).rear] = value;
        (*q).rear = (*q).rear + 1;
    }
}

int dequeue(Queue *q) {
    if (!isEmptyQueue(q)) {
        int value = (*q).data[(*q).front];
        (*q).front = (*q).front + 1;
        return value;
    }
    return -1;
}

/* =========================
   Stack 模組 (LIFO)
   ========================= */
typedef struct {
    int data[MAX];
    int top;
} Stack;

void initStack(Stack *s) {
    (*s).top = -1;
}

int isEmptyStack(Stack *s) {
    return (*s).top == -1;
}

void push(Stack *s, int value) {
    if ((*s).top < MAX - 1) {
        (*s).top = (*s).top + 1;
        (*s).data[(*s).top] = value;
    }
}

int pop(Stack *s) {
    if (!isEmptyStack(s)) {
        int value = (*s).data[(*s).top];
        (*s).top = (*s).top - 1;
        return value;
    }
    return -1;
}

/* =========================
   Graph 結構
   ========================= */
typedef struct {
    bool adjacency[N][N];
} Graph;

/* =========================
   BFS (樹狀縮排)
   ========================= */
void breadth_first_search(Graph graph_reference, int starting_node) {
    bool visited[N] = {false};
    Queue q;
    initQueue(&q);

    int level[N] = {0}; // 記錄節點層級
    visited[starting_node] = true;
    enqueue(&q, starting_node);

    printf("BFS Tree View:\n");

    while (!isEmptyQueue(&q)) {
        int current_node = dequeue(&q);
        int depth = level[current_node];

        // 縮排輸出
        for (int i = 0; i < depth; i++) printf("    ");
        printf("└── %d\n", current_node);

        for (int adjacent = 0; adjacent < N; adjacent++) {
            if (graph_reference.adjacency[current_node][adjacent] && !visited[adjacent]) {
                visited[adjacent] = true;
                level[adjacent] = depth + 1;
                enqueue(&q, adjacent);
            }
        }
    }
}

/* =========================
   DFS (樹狀縮排)
   ========================= */
void dfs_recursive(Graph graph_reference, int node, bool visited[], int depth) {
    visited[node] = true;

    for (int i = 0; i < depth; i++) printf("    ");
    printf("└── %d\n", node);

    for (int adjacent = 0; adjacent < N; adjacent++) {
        if (graph_reference.adjacency[node][adjacent] && !visited[adjacent]) {
            dfs_recursive(graph_reference, adjacent, visited, depth + 1);
        }
    }
}

void depth_first_search(Graph graph_reference, int starting_node) {
    bool visited[N] = {false};
    printf("DFS Tree View:\n");
    dfs_recursive(graph_reference, starting_node, visited, 0);
}

/* =========================
   Topological Sort (樹狀縮排)
   ========================= */
void topo_dfs(Graph graph_reference, int node, bool visited[], Stack *result, int depth) {
    visited[node] = true;

    for (int i = 0; i < depth; i++) printf("    ");
    printf("└── %d\n", node);

    for (int adjacent = 0; adjacent < N; adjacent++) {
        if (graph_reference.adjacency[node][adjacent] && !visited[adjacent]) {
            topo_dfs(graph_reference, adjacent, visited, result, depth + 1);
        }
    }

    push(result, node);
}

void topological_sort(Graph graph_reference) {
    bool visited[N] = {false};
    Stack result;
    initStack(&result);

    printf("Topological Sort Tree View:\n");
    for (int node = 0; node < N; node++) {
        if (!visited[node]) {
            topo_dfs(graph_reference, node, visited, &result, 0);
        }
    }

    printf("\nTopological Order:\n");
    while (!isEmptyStack(&result)) {
        printf("%d ", pop(&result));
    }
    printf("\n");
}

/* =========================
   測試主程式
   ========================= */
int main() {
    Graph graph = {0};

    /* 測試 BFS / DFS 的圖 */
    graph.adjacency[0][1] = true;
    graph.adjacency[0][2] = true;
    graph.adjacency[1][3] = true;
    graph.adjacency[1][4] = true;
    graph.adjacency[2][5] = true;
    graph.adjacency[2][6] = true;
    graph.adjacency[3][7] = true;
    graph.adjacency[4][8] = true;
    graph.adjacency[5][9] = true;

    printf("=== DFS ===\n");
    depth_first_search(graph, 0);

    printf("\n=== BFS ===\n");
    breadth_first_search(graph, 0);

    /* 測試 Topological Sort 的 DAG */
    Graph dag = {0};
    dag.adjacency[0][1] = true;
    dag.adjacency[0][2] = true;
    dag.adjacency[1][3] = true;
    dag.adjacency[2][3] = true;
    dag.adjacency[3][4] = true;

    printf("\n=== Topological Sort ===\n");
    topological_sort(dag);

    return 0;
}
```

##### 假設圖結構如下：
```
0 → 1 → 3 → 7
  ↘ 4 → 8
0 → 2 → 5 → 9
      ↘ 6
```

##### DFS Tree View
```
└── 0
    └── 1
        └── 3
            └── 7
        └── 4
            └── 8
    └── 2
        └── 5
            └── 9
        └── 6
```

##### BFS Tree View
```
└── 0
    └── 1
    └── 2
        └── 3
        └── 4
        └── 5
        └── 6
            └── 7
            └── 8
            └── 9
```

##### Topological Sort Tree View
```
└── 0
    └── 1
        └── 3
            └── 4
    └── 2
        └── 3
            └── 4
```

##### Topological Order:
```
0 2 1 3 4
```

- [time=Sat, Sep 6, 2025 8:52 PM]


#### 泡泡排序法 Bubble Sort

```c=
#include <stdio.h>
#include <stdlib.h>

int main()
{
    int arrSize = 10; /* 陣列長度 */
    int arr[10] = {3, 4, 0, 1, 2, 5, 6, 9, 7, 8}; /* 宣告陣列 */
    size_t arr_n = sizeof(arr) / sizeof(arr[0]);

    printf("arr 陣列的長度arr_n=%lu \n", arr_n);
    printf("arr 陣列的位元=%lu \n", sizeof(arr_n));
    printf("arr--- \n");

    
    int i = 0;
    for(i = 0; i < arrSize; ++i)
    {
        printf("%d \t", arr[i]);
    }
    
    printf("\n");

    i = (int)arr_n;
    
    do
    {
        if (i > 0)
        {
            int j = 1;
            do
            {
                if (arr[j] < arr[j - 1])
                {
                    int w = arr[j];
                    arr[j] = arr[j - 1];
                    arr[j - 1] = w;
                    printf("\nw=%d \t---\n", w);
                    
                    int x=0;
                    while(x < (int)arr_n) { 
                        printf("%d \t", arr[x]);
                        ++x;
                    }
                }
                
                j++;
            } while(j < i);
            
            i--;
            if (i == 0) { break; }
        }
    } while(i < arr_n);

    printf("\n");
    printf("arr--- \n");

    
    for(i = 0; i < arrSize; i++)
    {
        printf("%d \t", arr[i]);
    }
    
    printf("\n");

    return 0;
}
```
```
arr 陣列的長度arr_n=10 
arr 陣列的位元=8 
arr--- 
3       4       0       1       2       5       6       9       7       8 

w=0     ---
3       0       4       1       2       5       6       9       7       8 
w=1     ---
3       0       1       4       2       5       6       9       7       8 
w=2     ---
3       0       1       2       4       5       6       9       7       8 
w=7     ---
3       0       1       2       4       5       6       7       9       8 
w=8     ---
3       0       1       2       4       5       6       7       8       9 
w=0     ---
0       3       1       2       4       5       6       7       8       9 
w=1     ---
0       1       3       2       4       5       6       7       8       9 
w=2     ---
0       1       2       3       4       5       6       7       8       9 
arr--- 
0       1       2       3       4       5       6       7       8       9 


...Program finished with exit code 0
Press ENTER to exit console.
```

- [time=Thu, Aug 7, 2025 10:03 PM]


#### 二分搜尋法

```c=
#include <stdio.h>
#include <stdlib.h>

// 泡泡排序法
void bubbleSort(int arr[], int size) {
    
    int i = size;
    
    while(i > 0){ 
        
        int j = 1;
        while(j < i) { 
            
            if (arr[j] < arr[j - 1]) {
                // 交換 arr[j] 和 arr[j-1]
                int w = arr[j];
                arr[j] = arr[j - 1];
                arr[j - 1] = w;
                
            }
            
            ++j;
        }
        
        --i;
    }
}

// 二分搜尋法
int binarySearch(int arr[], int size, int target) {
    int left = 0;
    int right = size - 1;
    
    printf("搜尋對象: %d \n", target);

    while (left <= right) {
        int moderate = (left + right) / 2;  /* mod */  /* moderate */
        
        printf("取中間數: %d \n", moderate);

        if (arr[moderate] == target) {
            return moderate; // 找到目標
        } else if (arr[moderate] < target) {
            left = moderate + 1; // 往右邊找
            printf("往右邊找! \n");
        } else {
            right = moderate - 1; // 往左邊找
            printf("往左邊找! \n");
        }
    }

    return -1; // 沒找到
}

int main() {
    // 未排序的陣列
    int arr[10] = {5, 2, 9, 1, 7, 6, 3, 8, 0, 4};
    size_t size_array = sizeof(arr) / sizeof(arr[0]);
    int size = (int)size_array;
    int target = 2; // 要查找的目標值

    printf("原始陣列：\t");
    for (int i = 0; i < size; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");

    // 排序陣列
    bubbleSort(arr, size);

    printf("排序後的陣列：\t");
    for (int i = 0; i < size; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");

    // 查找目標值
    int result = binarySearch(arr, size, target);
    if (result != -1) {
        printf("找到數值 %d 在索引位置 %d。\n", target, result);
    } else {
        printf("找不到數值 %d。\n", target);
    }

    return 0;
}
```
```c=
原始陣列：      5 2 9 1 7 6 3 8 0 4 
排序後的陣列：  0 1 2 3 4 5 6 7 8 9 
搜尋對象: 2 
取中間數: 4 
往左邊找! 
取中間數: 1 
往右邊找! 
取中間數: 2 
找到數值 2 在索引位置 2。


...Program finished with exit code 0
Press ENTER to exit console.

```

<!-- - [time=Sun, Jun 29, 2025 3:15 PM] -->
<!-- - [time=Thu, Aug 7, 2025 10:17 PM] -->
- [time=Fri, Aug 8, 2025 4:19 AM]


#### Binary Tree

```c=
#include <stdio.h>
#include <stdlib.h>

/* Define the structure of a node in the binary tree */
struct Node {
    int data;
    struct Node *left;
    struct Node *right;
};

/* Function to create a new node */
struct Node* createNode(int data) {
    struct Node *newNode = (struct Node *)malloc(sizeof(struct Node));
    (*newNode).data = data;
    (*newNode).left = NULL;
    (*newNode).right = NULL;
    return newNode;
}

void modifyNode(struct Node* node, int newData) {
    if (node != NULL) {
        (*node).data = newData;
    }
}

/* Function to perform pre-order traversal */
void preOrderTraversal(struct Node *root) {
    if (root != NULL) {
        printf("%d ", (*root).data);           // 訪問根節點
        preOrderTraversal((*root).left);       // 遍歷左子樹
        preOrderTraversal((*root).right);      // 遍歷右子樹
    }
}

/* Function to perform in-order traversal */
void inOrderTraversal(struct Node *root) {
    if (root != NULL) {
        inOrderTraversal((*root).left);
        printf("%d ", (*root).data);
        inOrderTraversal((*root).right);
    }
}

int main() {
    /* Create nodes */
    struct Node *root = createNode(0);
    (*root).left = createNode(1);
    (*root).right = createNode(2);
    (*(*root).left).left = createNode(3);
    (*(*root).left).right = createNode(4);
    (*(*root).right).left = createNode(5);
    (*(*root).right).right = createNode(6);
    (*(*(*root).left).left).left = createNode(7);
    (*(*(*root).left).left).right = createNode(8);
    (*(*(*root).left).right).left = createNode(9);
    
    printf("Pre-order Traversal: ");
    preOrderTraversal(root);
    printf("\n");
    
    printf("In-order Traversal: ");
    inOrderTraversal(root);
    printf("\n");
    
    printf("Pro-order 後序排列");
    
    printf("\n");

    return 0;
}
```
```
Pre-order Traversal: 0 1 3 7 8 4 9 2 5 6   /* 前序排列 */
In-order Traversal: 7 3 8 1 9 4 0 5 2 6    /* 中序排列 */
                                           /* Pro-order Traversal 後序排列 */

...Program finished with exit code 0
Press ENTER to exit console.
```

- [time=Thu, Aug 7, 2025 10:05 AM]


### 數學 Math

$Latex$

- [Using LaTeX for Math](https://help-center.atlasbeta.so/getatlas-b2hge49eel/articles/203764-using-latex-for-math)
- [LaTeX wiki](https://en.wikipedia.org/wiki/LaTeX)
- [latex-tutorial](https://latex-tutorial.com/)
- [LaTeX Project Public License _ LPPL](https://en.wikipedia.org/wiki/LaTeX_Project_Public_License)
- [MathJax](https://docs.mathjax.org/en/latest/basic/mathematics.html)
- [time=Fri, Aug 1, 2025 12:18 AM]


#### 黃金比例 Golden Ratio

![黃金比例](https://hackmd.io/_uploads/S1SdF5Q4ex.png)

$A = \frac{y}{x-\frac{y}{x-\frac{y}{...}}} = \frac{y}{x-A}$

$\frac{x}{y} = \frac{y}{x-y} = \phi$

$\phi = \frac{1 + \sqrt{5}}{2}$

<!-- fraction = y / (x-y) -->
<!-- - [time=Tue, Aug 5, 2025 11:28 AM] -->

> [圖解數學](https://www.books.com.tw/products/0010777752?sloc=main)

> [黃金比例 維基百科](https://zh.wikipedia.org/wiki/%E9%BB%84%E9%87%91%E5%88%86%E5%89%B2%E7%8E%87)

> [time=Fri, Aug 1, 2025 12:22 AM]


#### 質因數分解

$362880 
= 0 + 1 \times 2 \times 3 \times 4 \times 5 \times 6 \times 7 \times 8 \times 9$

$707281 
= 841 \times 841 
= 29^{4}$

- [質因數 維基百科](https://zh.wikipedia.org/zh-tw/%E8%B3%AA%E5%9B%A0%E6%95%B8)
- [time=Sun, Sep 7, 2025 8:31 AM]


#### 哥德巴赫猜想

$32 
= 13 + 19$

$200 
= 31 + 13^{2} 
= 37 + 163$

- [歌德巴赫猜想 維基百科](https://zh.wikipedia.org/zh-tw/%E5%93%A5%E5%BE%B7%E5%B7%B4%E8%B5%AB%E7%8C%9C%E6%83%B3)
- [time=Thu, Jun 26, 2025 9:20 AM]


#### 三角函數 Triangle

![三角函數](https://hackmd.io/_uploads/HypBwNExgg.png)

$cos \theta = b / h$

$sin \theta = a / h$

$tan \theta = a / b$

$sin \theta ^ 2 + cos \theta ^ 2 = 1$

```c=
#include <stdio.h>
#include <stdlib.h>

int main(){
    // ...
}
```

- [三角函數 維基百科](https://zh.wikipedia.org/zh-tw/%E4%B8%89%E8%A7%92%E5%87%BD%E6%95%B0)
- [time=Sat, Jul 26, 2025 1:52 PM]


#### Acknowledge

```
推薦一本書，書名為真確。
```

* [C語言學習聖經 誠品](https://www.eslite.com/product/10012011762682390517009)
* [C語言教學手冊 誠品](https://www.eslite.com/product/1001113881689082)
* [真確 誠品](https://www.eslite.com/product/1001124182687226)

#### addition 補充：

* [Javascript 筆記](https://hackmd.io/@EIT-/javascript_)
* [JAVA 筆記](https://hackmd.io/@EIT-/java_)
* [SQLite 筆記](https://hackmd.io/@EIT-/sql_)
* [演算法 (Python) 筆記](https://hackmd.io/@EIT-/python_Mollitutanimreprehenderitdovelitculpexdolorutincididuntidanim)
* [Math 筆記](https://hackmd.io/@EIT-/cal_)