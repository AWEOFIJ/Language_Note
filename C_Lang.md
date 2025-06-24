---
title: C 程式語言筆記

---

# C 程式語言筆記 

`C_Programing_Language_Learning_Note`

> [Creative Commons License 4.0](https://creativecommons.org/licenses/by-nc/4.0/)

- Start Time: 2025.02.02
- Last Update : [time=Tue, Jun 24, 2025 7:46 AM]

---

**C語言為編譯式語言**
> C語言是一種通用的、程序式編程，程式語言，支援結構化編程、詞法作用域和遞迴，使用靜態型別系統，並且廣泛用於系統軟體與應用軟體的開發。

#### 特點:
- 移植性高: C語言提供前置處理器來處理不同平台之間的問題。
- 強大類別庫: 內建功能強大的類別庫以及函示庫。
- 兼具高低階語言能力: C語言是一種指令式編程語言。
- 可模組化: 可自行製作函示庫使用 (有提供良好的介面呼叫方式)。

> Acknowledge

- [C語言 - wiki](https://zh.wikipedia.org/zh-tw/C%E8%AF%AD%E8%A8%80)
- [time=Sat, Feb 22, 2025 8:33 AM]

### 開發環境

- Dev C++
- [OnlineGDB](https://www.onlinegdb.com/online_c_compiler)

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
---

#### 範例

```=c
#include<stdio.h>
#include<stdlib.h>

#include<string.h> /* 使用char[]可以不用引入string */

int main(){
    
    char action[20]="Good"
    int observed=0
    
    / ... */

    if (observed=1){
        /* action = "take action"; */
        /* printf(action); */
    }
    
    /* system("pause"); */
    return 0;
}
```

---

#### Print 格式

* 格式由"%"與格式字元組成，將輸出的數據轉換為指定的格式輸出，由"%"開始。
* 格式字元：d, o, x, u, c, s, f, e, g, ...。

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
```
- [CSDN博客](https://blog.csdn.net/qq_32365567/article/details/55045942)

-->

---

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

---

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

---

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
| \* | 單引號(single quote) | 39 |
| \" | 雙引號(double quote) | 34 |

---

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

---

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

note: `% 算餘數， 5 % 2 = 1 。` 

note: `C 小數使用 =`
<!-- note: `十進位小數好像使用 Decimal in C#` -->

- [time=Thu, Mar 6, 2025 5:11 PM]

---

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

<!-- F(I/O) -->

- [time=Sun, Jun 1, 2025 10:23 AM]

---

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

---

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

---

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

---

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

---

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
    struct data student = {"Andy", 1, 85};
    printf("%s", student.name);
    
    /* ... */
    
    /* system("pause"); */
    
    return 0;
}
```
- [time=Fri, Feb 21, 2025 10:38 AM]

---

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

---

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

---

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

---

#### 數字替換函式 Swap Number

- [Swap number - GDB_Online_Editor](https://learn.onlinegdb.com/c_program_to_swap_two_numbers)
- [time=Sat, Mar 15, 2025 8:59 AM]

---

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

---

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

---

### 函數

#### 階乘函數
```c=
#include<stdio.h>
#include<stdlib.h>
int fac(int);

int fac(int n)
{
    if (n > 1) return (n * fac(n - 1));
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

---

#### 費波納契函數(遞迴函數)

```c=
#include<stdio.h>
#include<stdlib.h>
int fib(int);

int fib(int n)
{
    if (n < 0 || n > 37) return -1;
    if (n == 0) return 0;
    if (n == 1) return 1;
    return fib(n - 1) + fib(n - 2);
}

int main()
{
    printf("fib(6)=%d \n", fib(4));
    system("pause");
    return 0;
}

/* https://stackoverflow.com/questions/3165293/fibonacci-sequence-in-c */
```
> [fibonacci_stackoverflow](https://stackoverflow.com/questions/3165293/fibonacci-sequence-in-c)
- [time=Thu, Jun 19, 2025 6:03 AM]

---

#### 有向無環圖 Directed Acyclic Graph

```c=
#include <stdio.h>
#include <stdlib.h>
#include <stdbool.h>

#define N 10

typedef struct {
    bool adj[N][N];  /* 鄰接矩陣 */
    int visit[N];    /* 訪問標記 */
    int order[N];    /* 拓撲排序結果 */
    int t;           /* 記錄排序索引 */
    bool cycle;      /* 是否存在環 */
} Dag;

void DFS(Dag *dagRef, int i) {
    if ((*dagRef).visit[i] == 1) {
        (*dagRef).cycle = true;
        return;
    }
    if ((*dagRef).visit[i] == 2) return;

    (*dagRef).visit[i] = 1;
    
    int j = 0;
    while( j < N){
	   if ((*dagRef).adj[i][j]) DFS(dagRef, j);
	   j++; 
    };
    
    (*dagRef).visit[i] = 2;
    (*dagRef).order[(*dagRef).t++] = i;
}

void topological_ordering(Dag *dagRef) {
    
    int i = 0;
    while (i < N){
	(*dagRef).visit[i] = 0;
	i++; 
    }
	
    (*dagRef).t = 0;
    (*dagRef).cycle = false;

    i = 0;
    while(i < N){
	if ((*dagRef).visit[i] == 0) {
            DFS(dagRef, i);
        }
    }

    if ((*dagRef).cycle) {
        printf("圖上有環\n");
    } else {
        printf("拓撲排序:\n");
        
        i = N - 1;
        while( i >= 0){
	    printf("%d ", (*dagRef).order[i]);
	}

        printf("\n");
    }
}

int main() {
    Dag dag = {0};  /* 直接使用變數而非指標 */ 
    topological_ordering(&dag);
    return 0;
}
```

- [Directed Acyclic Graph](https://web.ntnu.edu.tw/~algo/DirectedAcyclicGraph.html)
- [time=Thu, May 8, 2025 8:19 AM]

---

#### DAG (DFS vs BFS)

```c=
#include <stdio.h>
#include <stdlib.h>
#include <stdbool.h>

#define N 10

typedef struct {
    bool adjacency[N][N];  
    int visited[N];    
    int order[N];    
    int index;      
    bool has_cycle;  
} Graph;

Graph depth_first_search(Graph graph_reference, int node) {
    if (graph_reference.visited[node] == 1) {
        graph_reference.has_cycle = true;
        return graph_reference;
    }
    if (graph_reference.visited[node] == 2) return graph_reference;

    graph_reference.visited[node] = 1;
    
    int adjacent = 0;
    while(adjacent < N){
		if (graph_reference.adjacency[node][adjacent]) {
            graph_reference = depth_first_search(graph_reference, adjacent);
        }
		adjacent++;
	}

    graph_reference.visited[node] = 2;
    graph_reference.order[graph_reference.index++] = node;

    return graph_reference;
}

Graph topological_sort(Graph graph_reference) {
	
	int node = 0;
	while(node < N){
		graph_reference.visited[node] = 0;
	}

    graph_reference.index = 0;
    graph_reference.has_cycle = false;

	node = 0;
	while(node < N){
		if (graph_reference.visited[node] == 0) {
            graph_reference = depth_first_search(graph_reference, node);
        }
	}

    if (graph_reference.has_cycle) {
        printf("Graph contains a cycle\n");
    } else {
        printf("Topological Sorting:\n");
        
        int i = N;
        while(i >= 0){
			printf("%d ", graph_reference.order[i]);
		}
        
        printf("\n");
    }

    return graph_reference;
}

void breadth_first_search(Graph graph_reference, int starting_node) {
    bool visited[N] = {false};
    int queue[N], front = 0, rear = 0;

    visited[starting_node] = true;
    queue[rear++] = starting_node;

    printf("BFS Traversal:\n");

    while (front < rear) {
        int current_node = queue[front++];
        printf("%d ", current_node);

		int adjacent = 0;
		while(adjacent < N){
			if (graph_reference.adjacency[current_node][adjacent] && !visited[adjacent]) {
                visited[adjacent] = true;
                queue[rear++] = adjacent;
            }
		}
    }
    printf("\n");
}

int main() {
    Graph graph = {0};  

    graph.adjacency[0][1] = true;
    graph.adjacency[1][2] = true;
    graph.adjacency[2][3] = true;
    graph.adjacency[3][4] = true;
    graph.adjacency[4][5] = true;
    graph.adjacency[5][6] = true;
    graph.adjacency[6][7] = true;
    graph.adjacency[7][8] = true;
    graph.adjacency[8][9] = true;

    printf("Running Topological Sorting:\n");
    graph = topological_sort(graph);

    int start_node = 0;  
    printf("Running BFS:\n");
    breadth_first_search(graph, start_node);

    return 0;
}
```

- [time=Thu, May 8, 2025 8:23 AM]


---

#### 泡泡排序法 Bubble Sort

```c=
#include <stdio.h>
#include <stdlib.h>

int main()
{
    int arrSize = 10; /* 陣列長度 */

    int arr[10] = {3, 4, 0, 1, 2, 5, 6, 9, 7, 8}; /* 宣告陣列  */
    size_t arr_n = sizeof(arr) / sizeof(arr[0]);

    printf("arr 陣列的長度arr_n=%lu \n", arr_n);
    printf("arr 陣列的長度值arr_n位元=%lu \n", sizeof(arr_n));
    printf("arr--- \n");

    int i = 0;
    for (i = 0; i < arrSize; i++)
    {
        printf("%d \t", arr[i]);
    }

    i = arr_n;

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
                    
                    /*  */
                }
                j++;
            } while (j < i);
            i--;
            if (i == 0)
                break;
        }
    } while (i < arr_n);

    printf("\n");
    printf("arr--- \n");

    i = 0;
    for (i = 0; i < arrSize; i++)
    {
        printf("%d \t", arr[i]);
    }

    return 0;
}
```

- [time=Sun, Jun 22, 2025 12:48 PM]

---

#### 二分搜尋法

```c=
#include <stdio.h>
#include <stdlib.h>

// 泡泡排序法
void bubbleSort(int arr[], int size) {
    for (int i = 0; i < size - 1; i++) {
        for (int j = 0; j < size - i - 1; j++) {
            if (arr[j] > arr[j + 1]) {
                // 交換 arr[j] 和 arr[j+1]
                int w = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = w;
                
                /*  */
            }
        }
    }
}

// 二分搜尋法
int binarySearch(int arr[], int size, int target) {
    int left = 0;
    int right = size - 1;

    while (left <= right) {
        int mid = (left + right) / 2;

        if (arr[mid] == target) {
            return mid; // 找到目標
        } else if (arr[mid] < target) {
            left = mid + 1; // 往右邊找
        } else {
            right = mid - 1; // 往左邊找
        }
    }

    return -1; // 沒找到
}

int main() {
    // 未排序的陣列
    int arr[] = {5, 2, 9, 1, 7, 6, 3, 8, 0, 4};
    int size = sizeof(arr) / sizeof(arr[0]);
    int target = 4; // 要查找的目標值

    printf("原始陣列：\n");
    for (int i = 0; i < size; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");

    // 排序陣列
    bubbleSort(arr, size);

    printf("排序後的陣列：\n");
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

- [time=Sun, Jun 22, 2025 12:49 PM]

---
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
    struct Node *root = createNode(1);
    (*root).left = createNode(2);
    (*root).right = createNode(3);
    (*(*root).left).left = createNode(4);
    (*(*root).left).right = createNode(5);
    /*  */
    (*(*root).right).left = createNode(6);
    (*(*root).right).right = createNode(7);
    
    printf("In-order Traversal: ");
    inOrderTraversal(root);
    printf("\n");

    return 0;
}
```

- [time=Thu, Jun 19, 2025 6:05 AM]

---

### 數學 Math

$Latex$

- [Using LaTeX for Math](https://help-center.atlasbeta.so/getatlas-b2hge49eel/articles/203764-using-latex-for-math)
- [LaTeX wiki](https://en.wikipedia.org/wiki/LaTeX)
- [latex-tutorial](https://latex-tutorial.com/)
- [LaTeX Project Public License _ LPPL](https://en.wikipedia.org/wiki/LaTeX_Project_Public_License)
- [MathJax](https://docs.mathjax.org/en/latest/basic/mathematics.html)

---

#### 黃金比例 Golden Ratio

![黃金比例](https://hackmd.io/_uploads/S1SdF5Q4ex.png)


$A = \frac{y}{x-\frac{y}{x-\frac{y}{...}}} = \frac{y}{x-A}$

$\frac{x}{y} = \frac{y}{x-y} = \phi$

$\phi = \frac{1 + \sqrt{5}}{2}$
 
> [圖解數學](https://www.books.com.tw/products/0010777752?sloc=main)

> [黃金比例 維基百科](https://zh.wikipedia.org/wiki/%E9%BB%84%E9%87%91%E5%88%86%E5%89%B2%E7%8E%87)
- [time=Mon, Jun 23, 2025 9:07 AM]

---

#### 質因數分解

$362880 = 0 + 1 \times 2 \times 3 \times 4 \times 5 \times 6 \times 7 \times 8 \times 9$

$707281 = 841 \times 841 = 29^{4}$

- [質因數 維基百科](https://zh.wikipedia.org/zh-tw/%E8%B3%AA%E5%9B%A0%E6%95%B8)
- [time=Mon, Jun 23, 2025 9:07 AM]

---

#### 哥德巴赫猜想

$32 = 13 + 19$

- [歌德巴赫猜想 維基百科](https://zh.wikipedia.org/zh-tw/%E5%93%A5%E5%BE%B7%E5%B7%B4%E8%B5%AB%E7%8C%9C%E6%83%B3)
- [time=Thu, Jun 19, 2025 5:49 AM]

---

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
    
}
```

> [三角函數 維基百科](https://zh.wikipedia.org/zh-tw/%E4%B8%89%E8%A7%92%E5%87%BD%E6%95%B0)
- [time=Thu, Jun 19, 2025 5:49 AM]

---

#### 泰勒展開式 Taylor Expansion

:::info
在數學上，對於一個在實數或複數$a$鄰域上，以實數作為變量或以複數作為變量的函數，並且是無窮可微的函數$f(x)$，它的泰勒級數是以下這種形式的冪級數
:::

$\sum_{n=0}^{\infty}{\cfrac {f^{(n)}(a)}{n!}}(x-a)^{n}$

<!-- ![多元函數的展開](https://wikimedia.org/api/rest_v1/media/math/render/svg/c429bf7c3300745b302d2906cb24577a309ec9f5) -->

- [泰勒展開式 維基百科](https://zh.wikipedia.org/zh-tw/%E6%B3%B0%E5%8B%92%E7%BA%A7%E6%95%B0) 
- [time=Sat, Jun 21, 2025 10:28 AM]

---

#### 傅立葉轉換

$F(f)(\mathbf{k}) = {\hat {f(\mathbf{k})}} = \int_{\mathbb{R}^d} f(\mathbf{x})\, e^{-2\pi i\, \mathbf{k} \cdot \mathbf{x}}\, d\mathbf{x}$

- [傅立葉轉換 維基百科](https://zh.wikipedia.org/zh-tw/%E5%82%85%E9%87%8C%E5%8F%B6%E5%8F%98%E6%8D%A2)
- [time=Tue, Jun 24, 2025 12:31 PM]

---
#### Q: 何謂穩固結構

```
What structure would be Solidity ? 
參考以上圖形，最簡單的起點為三角形，最簡單的回答為圓形。
```
```
讀過一本書，
書名為真確。
```

- [name=EIT-]

---

#### Reference 參考資料：

> [C語言教學手冊](https://www.books.com.tw/products/0010360466)

> [C語言學習聖經](https://www.books.com.tw/products/0010958702?sloc=main)

> [真確 - 博客來](https://www.books.com.tw/products/E050030362?sloc=main)# C 程式語言筆記 

`C_Programing_Language_Learning_Note`

> [Creative Commons License 4.0](https://creativecommons.org/licenses/by-nc/4.0/)

- Start Time: 2025.02.02
- Last Update : [time=Tue, Jun 24, 2025 7:46 AM]

---

**C語言為編譯式語言**
> C語言是一種通用的、程序式編程，程式語言，支援結構化編程、詞法作用域和遞迴，使用靜態型別系統，並且廣泛用於系統軟體與應用軟體的開發。

#### 特點:
- 移植性高: C語言提供前置處理器來處理不同平台之間的問題。
- 強大類別庫: 內建功能強大的類別庫以及函示庫。
- 兼具高低階語言能力: C語言是一種指令式編程語言。
- 可模組化: 可自行製作函示庫使用 (有提供良好的介面呼叫方式)。

> Acknowledge

- [C語言 - wiki](https://zh.wikipedia.org/zh-tw/C%E8%AF%AD%E8%A8%80)
- [time=Sat, Feb 22, 2025 8:33 AM]

### 開發環境

- Dev C++
- [OnlineGDB](https://www.onlinegdb.com/online_c_compiler)

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
---

#### 範例

```=c
#include<stdio.h>
#include<stdlib.h>

#include<string.h> /* 使用char[]可以不用引入string */

int main(){
    
    char action[20]="Good"
    int observed=0
    
    / ... */

    if (observed=1){
        /* action = "take action"; */
        /* printf(action); */
    }
    
    /* system("pause"); */
    return 0;
}
```

---

#### Print 格式

* 格式由"%"與格式字元組成，將輸出的數據轉換為指定的格式輸出，由"%"開始。
* 格式字元：d, o, x, u, c, s, f, e, g, ...。

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
```
- [CSDN博客](https://blog.csdn.net/qq_32365567/article/details/55045942)

-->

---

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

---

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

---

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
| \* | 單引號(single quote) | 39 |
| \" | 雙引號(double quote) | 34 |

---

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

---

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

note: `% 算餘數， 5 % 2 = 1 。` 

note: `C 小數使用 =`
<!-- note: `十進位小數好像使用 Decimal in C#` -->

- [time=Thu, Mar 6, 2025 5:11 PM]

---

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

<!-- F(I/O) -->

- [time=Sun, Jun 1, 2025 10:23 AM]

---

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

---

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

---

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

---

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

---

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
    struct data student = {"Andy", 1, 85};
    printf("%s", student.name);
    
    /* ... */
    
    /* system("pause"); */
    
    return 0;
}
```
- [time=Fri, Feb 21, 2025 10:38 AM]

---

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

---

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

---

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

---

#### 數字替換函式 Swap Number

- [Swap number - GDB_Online_Editor](https://learn.onlinegdb.com/c_program_to_swap_two_numbers)
- [time=Sat, Mar 15, 2025 8:59 AM]

---

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

---

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

---

### 函數

#### 階乘函數
```c=
#include<stdio.h>
#include<stdlib.h>
int fac(int);

int fac(int n)
{
    if (n > 1) return (n * fac(n - 1));
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

---

#### 費波納契函數(遞迴函數)

```c=
#include<stdio.h>
#include<stdlib.h>
int fib(int);

int fib(int n)
{
    if (n < 0 || n > 37) return -1;
    if (n == 0) return 0;
    if (n == 1) return 1;
    return fib(n - 1) + fib(n - 2);
}

int main()
{
    printf("fib(6)=%d \n", fib(4));
    system("pause");
    return 0;
}

/* https://stackoverflow.com/questions/3165293/fibonacci-sequence-in-c */
```
> [fibonacci_stackoverflow](https://stackoverflow.com/questions/3165293/fibonacci-sequence-in-c)
- [time=Thu, Jun 19, 2025 6:03 AM]

---

#### 有向無環圖 Directed Acyclic Graph

```c=
#include <stdio.h>
#include <stdlib.h>
#include <stdbool.h>

#define N 10

typedef struct {
    bool adj[N][N];  /* 鄰接矩陣 */
    int visit[N];    /* 訪問標記 */
    int order[N];    /* 拓撲排序結果 */
    int t;           /* 記錄排序索引 */
    bool cycle;      /* 是否存在環 */
} Dag;

void DFS(Dag *dagRef, int i) {
    if ((*dagRef).visit[i] == 1) {
        (*dagRef).cycle = true;
        return;
    }
    if ((*dagRef).visit[i] == 2) return;

    (*dagRef).visit[i] = 1;
    
    int j = 0;
    while( j < N){
	   if ((*dagRef).adj[i][j]) DFS(dagRef, j);
	   j++; 
    };
    
    (*dagRef).visit[i] = 2;
    (*dagRef).order[(*dagRef).t++] = i;
}

void topological_ordering(Dag *dagRef) {
    
    int i = 0;
    while (i < N){
	(*dagRef).visit[i] = 0;
	i++; 
    }
	
    (*dagRef).t = 0;
    (*dagRef).cycle = false;

    i = 0;
    while(i < N){
	if ((*dagRef).visit[i] == 0) {
            DFS(dagRef, i);
        }
    }

    if ((*dagRef).cycle) {
        printf("圖上有環\n");
    } else {
        printf("拓撲排序:\n");
        
        i = N - 1;
        while( i >= 0){
	    printf("%d ", (*dagRef).order[i]);
	}

        printf("\n");
    }
}

int main() {
    Dag dag = {0};  /* 直接使用變數而非指標 */ 
    topological_ordering(&dag);
    return 0;
}
```

- [Directed Acyclic Graph](https://web.ntnu.edu.tw/~algo/DirectedAcyclicGraph.html)
- [time=Thu, May 8, 2025 8:19 AM]

---

#### DAG (DFS vs BFS)

```c=
#include <stdio.h>
#include <stdlib.h>
#include <stdbool.h>

#define N 10

typedef struct {
    bool adjacency[N][N];  
    int visited[N];    
    int order[N];    
    int index;      
    bool has_cycle;  
} Graph;

Graph depth_first_search(Graph graph_reference, int node) {
    if (graph_reference.visited[node] == 1) {
        graph_reference.has_cycle = true;
        return graph_reference;
    }
    if (graph_reference.visited[node] == 2) return graph_reference;

    graph_reference.visited[node] = 1;
    
    int adjacent = 0;
    while(adjacent < N){
		if (graph_reference.adjacency[node][adjacent]) {
            graph_reference = depth_first_search(graph_reference, adjacent);
        }
		adjacent++;
	}

    graph_reference.visited[node] = 2;
    graph_reference.order[graph_reference.index++] = node;

    return graph_reference;
}

Graph topological_sort(Graph graph_reference) {
	
	int node = 0;
	while(node < N){
		graph_reference.visited[node] = 0;
	}

    graph_reference.index = 0;
    graph_reference.has_cycle = false;

	node = 0;
	while(node < N){
		if (graph_reference.visited[node] == 0) {
            graph_reference = depth_first_search(graph_reference, node);
        }
	}

    if (graph_reference.has_cycle) {
        printf("Graph contains a cycle\n");
    } else {
        printf("Topological Sorting:\n");
        
        int i = N;
        while(i >= 0){
			printf("%d ", graph_reference.order[i]);
		}
        
        printf("\n");
    }

    return graph_reference;
}

void breadth_first_search(Graph graph_reference, int starting_node) {
    bool visited[N] = {false};
    int queue[N], front = 0, rear = 0;

    visited[starting_node] = true;
    queue[rear++] = starting_node;

    printf("BFS Traversal:\n");

    while (front < rear) {
        int current_node = queue[front++];
        printf("%d ", current_node);

		int adjacent = 0;
		while(adjacent < N){
			if (graph_reference.adjacency[current_node][adjacent] && !visited[adjacent]) {
                visited[adjacent] = true;
                queue[rear++] = adjacent;
            }
		}
    }
    printf("\n");
}

int main() {
    Graph graph = {0};  

    graph.adjacency[0][1] = true;
    graph.adjacency[1][2] = true;
    graph.adjacency[2][3] = true;
    graph.adjacency[3][4] = true;
    graph.adjacency[4][5] = true;
    graph.adjacency[5][6] = true;
    graph.adjacency[6][7] = true;
    graph.adjacency[7][8] = true;
    graph.adjacency[8][9] = true;

    printf("Running Topological Sorting:\n");
    graph = topological_sort(graph);

    int start_node = 0;  
    printf("Running BFS:\n");
    breadth_first_search(graph, start_node);

    return 0;
}
```

- [time=Thu, May 8, 2025 8:23 AM]


---

#### 泡泡排序法 Bubble Sort

```c=
#include <stdio.h>
#include <stdlib.h>

int main()
{
    int arrSize = 10; /* 陣列長度 */

    int arr[10] = {3, 4, 0, 1, 2, 5, 6, 9, 7, 8}; /* 宣告陣列  */
    size_t arr_n = sizeof(arr) / sizeof(arr[0]);

    printf("arr 陣列的長度arr_n=%lu \n", arr_n);
    printf("arr 陣列的長度值arr_n位元=%lu \n", sizeof(arr_n));
    printf("arr--- \n");

    int i = 0;
    for (i = 0; i < arrSize; i++)
    {
        printf("%d \t", arr[i]);
    }

    i = arr_n;

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
                    
                    /*  */
                }
                j++;
            } while (j < i);
            i--;
            if (i == 0)
                break;
        }
    } while (i < arr_n);

    printf("\n");
    printf("arr--- \n");

    i = 0;
    for (i = 0; i < arrSize; i++)
    {
        printf("%d \t", arr[i]);
    }

    return 0;
}
```

- [time=Sun, Jun 22, 2025 12:48 PM]

---

#### 二分搜尋法

```c=
#include <stdio.h>
#include <stdlib.h>

// 泡泡排序法
void bubbleSort(int arr[], int size) {
    for (int i = 0; i < size - 1; i++) {
        for (int j = 0; j < size - i - 1; j++) {
            if (arr[j] > arr[j + 1]) {
                // 交換 arr[j] 和 arr[j+1]
                int w = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = w;
                
                /*  */
            }
        }
    }
}

// 二分搜尋法
int binarySearch(int arr[], int size, int target) {
    int left = 0;
    int right = size - 1;

    while (left <= right) {
        int mid = (left + right) / 2;

        if (arr[mid] == target) {
            return mid; // 找到目標
        } else if (arr[mid] < target) {
            left = mid + 1; // 往右邊找
        } else {
            right = mid - 1; // 往左邊找
        }
    }

    return -1; // 沒找到
}

int main() {
    // 未排序的陣列
    int arr[] = {5, 2, 9, 1, 7, 6, 3, 8, 0, 4};
    int size = sizeof(arr) / sizeof(arr[0]);
    int target = 4; // 要查找的目標值

    printf("原始陣列：\n");
    for (int i = 0; i < size; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");

    // 排序陣列
    bubbleSort(arr, size);

    printf("排序後的陣列：\n");
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

- [time=Sun, Jun 22, 2025 12:49 PM]

---
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
    struct Node *root = createNode(1);
    (*root).left = createNode(2);
    (*root).right = createNode(3);
    (*(*root).left).left = createNode(4);
    (*(*root).left).right = createNode(5);
    /*  */
    (*(*root).right).left = createNode(6);
    (*(*root).right).right = createNode(7);
    
    printf("In-order Traversal: ");
    inOrderTraversal(root);
    printf("\n");

    return 0;
}
```

- [time=Thu, Jun 19, 2025 6:05 AM]

---

### 數學 Math

$Latex$

- [Using LaTeX for Math](https://help-center.atlasbeta.so/getatlas-b2hge49eel/articles/203764-using-latex-for-math)
- [LaTeX wiki](https://en.wikipedia.org/wiki/LaTeX)
- [latex-tutorial](https://latex-tutorial.com/)
- [LaTeX Project Public License _ LPPL](https://en.wikipedia.org/wiki/LaTeX_Project_Public_License)
- [MathJax](https://docs.mathjax.org/en/latest/basic/mathematics.html)

---

#### 黃金比例 Golden Ratio

![黃金比例](https://hackmd.io/_uploads/S1SdF5Q4ex.png)


$A = \frac{y}{x-\frac{y}{x-\frac{y}{...}}} = \frac{y}{x-A}$

$\frac{x}{y} = \frac{y}{x-y} = \phi$

$\phi = \frac{1 + \sqrt{5}}{2}$
 
> [圖解數學](https://www.books.com.tw/products/0010777752?sloc=main)

> [黃金比例 維基百科](https://zh.wikipedia.org/wiki/%E9%BB%84%E9%87%91%E5%88%86%E5%89%B2%E7%8E%87)
- [time=Mon, Jun 23, 2025 9:07 AM]

---

#### 質因數分解

$362880 = 0 + 1 \times 2 \times 3 \times 4 \times 5 \times 6 \times 7 \times 8 \times 9$

$707281 = 841 \times 841 = 29^{4}$

- [質因數 維基百科](https://zh.wikipedia.org/zh-tw/%E8%B3%AA%E5%9B%A0%E6%95%B8)
- [time=Mon, Jun 23, 2025 9:07 AM]

---

#### 哥德巴赫猜想

$32 = 13 + 19$

- [歌德巴赫猜想 維基百科](https://zh.wikipedia.org/zh-tw/%E5%93%A5%E5%BE%B7%E5%B7%B4%E8%B5%AB%E7%8C%9C%E6%83%B3)
- [time=Thu, Jun 19, 2025 5:49 AM]

---

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
    
}
```

> [三角函數 維基百科](https://zh.wikipedia.org/zh-tw/%E4%B8%89%E8%A7%92%E5%87%BD%E6%95%B0)
- [time=Thu, Jun 19, 2025 5:49 AM]

---

#### 泰勒展開式 Taylor Expansion

:::info
在數學上，對於一個在實數或複數$a$鄰域上，以實數作為變量或以複數作為變量的函數，並且是無窮可微的函數$f(x)$，它的泰勒級數是以下這種形式的冪級數
:::

$\sum_{n=0}^{\infty}{\cfrac {f^{(n)}(a)}{n!}}(x-a)^{n}$

<!-- ![多元函數的展開](https://wikimedia.org/api/rest_v1/media/math/render/svg/c429bf7c3300745b302d2906cb24577a309ec9f5) -->

- [泰勒展開式 維基百科](https://zh.wikipedia.org/zh-tw/%E6%B3%B0%E5%8B%92%E7%BA%A7%E6%95%B0) 
- [time=Sat, Jun 21, 2025 10:28 AM]

---

#### 傅立葉轉換

$F(f)(\mathbf{k}) = {\hat {f(\mathbf{k})}} = \int_{\mathbb{R}^d} f(\mathbf{x})\, e^{-2\pi i\, \mathbf{k} \cdot \mathbf{x}}\, d\mathbf{x}$

- [傅立葉轉換 維基百科](https://zh.wikipedia.org/zh-tw/%E5%82%85%E9%87%8C%E5%8F%B6%E5%8F%98%E6%8D%A2)
- [time=Tue, Jun 24, 2025 12:31 PM]

---
#### Q: 何謂穩固結構

```
What structure would be Solidity ? 
參考以上圖形，最簡單的起點為三角形，最簡單的回答為圓形。
```
```
讀過一本書，
書名為真確。
```

- [name=EIT-]

---

#### Reference 參考資料：

> [C語言教學手冊](https://www.books.com.tw/products/0010360466)

> [C語言學習聖經](https://www.books.com.tw/products/0010958702?sloc=main)

> [真確 - 博客來](https://www.books.com.tw/products/E050030362?sloc=main)