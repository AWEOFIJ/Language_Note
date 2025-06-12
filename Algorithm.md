# 演算法
# Algorithm

####演算法

深度優先搜尋 比對 廣度優先搜尋

Depth First Search vs Breadth First Search

DFS vs BFS

- [time=Wed, May 28, 2025 10:53 AM]
- 202506130635457554

> [Directed_Acyclic_Graph](https://web.ntnu.edu.tw/~algo/DirectedAcyclicGraph.html)

> [T客幫 演算法](https://ithelp.ithome.com.tw/articles/10281404)

#### Directed Acyclic Graph
#### Javascript
```javascript=
let N = 10;

class Dag {
    constructor() {
        this.adj = Array.from({ length: N }, () => Array(N).fill(false));
        this.visit = Array(N).fill(false);
        this.order = Array(N).fill(null);
        this.t = 0;
        this.cycle = false;
    }

    DFS(i) {
        if (this.visit[i] === 1) { this.cycle = true; return; }
        if (this.visit[i] === 2) return;

        this.visit[i] = 1;

        for (let j = 0; j < N; ++j) {
            if (this.adj[i][j]) this.DFS(j);
        }

        this.visit[i] = 2;
        this.order[this.t++] = i;  // Fixing `s` to `i`
    }
    
    BFS(graph, startNode) {
        // 使用 Javascript 陣列作為佇列 (Queue)，用於儲存待拜訪的節點
        // BFS 使用佇列的「先進先出」(FIFO) 特性
        let queue = [];

        // 使用一個 Set 或物件來追蹤已經拜訪過的節點，避免重複處理和無限迴圈
        let visited = new Set();

        // 儲存 BFS 遍歷的順序
        let traversalOrder = [];

        //  將起始節點加入佇列和已拜訪集合中
        queue.push(startNode);
        visited.add(startNode);

        //  當佇列不為空時，持續進行遍歷
        while (queue.length > 0) {
            //  從佇列前端取出一個節點（模擬 Dequeue 操作）
            //    注意：Array.shift() 在 Javascript 中對於大型陣列可能效率不高，
            //    更有效率的實作會使用 Deque 物件或鏈結串列
            let currentNode = queue.shift();

            //  將當前節點加入遍歷順序列表
            traversalOrder.push(currentNode);

            //  拜訪當前節點所有相鄰（鄰接）的節點
            //  BFS 如何依序拜訪鄰近節點
            //  使用 AdjList
            //  使用 Adjacency List dictionary 
            const neighbors = graph[currentNode] || []; // 確保節點存在且有鄰居列表

            for (const neighbor of neighbors) {
                //  如果相鄰節點尚未被拜訪過
                if (!visited.has(neighbor)) {
                    //  將相鄰節點標記為已拜訪
                    visited.add(neighbor);
                    //  將相鄰節點加入佇列尾端，等待之後拜訪（模擬 Enqueue 操作）
                    queue.push(neighbor);
                }
            }
        }

        //  佇列清空後，遍歷結束 
        return traversalOrder;
    }
    
    getRandomInteger(min, max) {
      return Math.floor(Math.random() * (max - min + 1)) + min;
    }

    topological_ordering() {
        this.visit.fill(0);  // Reset visit array
        
        for (let i = 0; i < N; i++) {
            if (!this.visit[i]) this.DFS(i);
        }

        if (this.cycle) {
            console.log("圖上有環");
        } else {
            console.log("拓撲排序:");
            for (let i = N - 1; i >= 0; i--) {
                console.log(this.order[i]);
            }
        }
    }
}

let dag = new Dag();
dag.topological_ordering();
```

- [time=Fri, May 9, 2025 4:52 AM]

### Tree

#### Javascript
```javascript=
class Graph {
  constructor() {
    this.adjacencyList = {};
  }

  //新增頂點
  addVertex(vertex) {
    if (!this.adjacencyList[vertex]) {
      this.adjacencyList[vertex] = [];
    } else {
      return '頂點已存在';
    }
  }

  //新增邊
  addEdge(vertex1, vertex2) {
    if (this.adjacencyList[vertex1] && this.adjacencyList[vertex2]) {
      if (!this.adjacencyList[vertex1].includes(vertex2)) {
        this.adjacencyList[vertex1].push(vertex2);
      }
      if (!this.adjacencyList[vertex2].includes(vertex1)) {
        this.adjacencyList[vertex2].push(vertex1);
      }
    } else {
      return vertex1 in this.adjacencyList ? '第二項頂點不存在' : '第一項頂點不存在';
    }
  }

  //刪除頂點
  removeVertex(vertex) {
    if (this.adjacencyList[vertex]) {
      this.adjacencyList[vertex].forEach(function (item) {
        this.removeEdge(vertex, item);
        delete this.adjacencyList[vertex];
      });
    } else {
      return '此頂點已不存在';
    }
  }

  //刪除邊
  removeEdge(vertex1, vertex2) {
    if (this.adjacencyList[vertex1]) {
      if (this.adjacencyList[vertex2]) {
        this.adjacencyList[vertex1] = this.adjacencyList[vertex1].filter(
          (vertex) => vertex !== vertex2
        );
        this.adjacencyList[vertex2] = this.adjacencyList[vertex2].filter(
          (vertex) => vertex !== vertex1
        );
      } else {
        return '第二項頂點已不存在';
      }
    } else {
      return '第一項頂點已不存在';
    }
  }

  // 列印圖
  printGraph() {
    console.log(this.adjacencyList);
  }

  //深度優先
  dfs(start) {
    const result = [];
    const stack = [start];
    const visited = {};
    visited[start] = true;
    let currentVertex;
    while (stack.length) {
      currentVertex = stack.pop();
      result.push(currentVertex);
      this.adjacencyList[currentVertex].forEach(neighbor => {
        if (!visited[neighbor]) {
          visited[neighbor] = true;
          stack.push(neighbor);
        }
      });
    }
    return result;
  }

  //廣度優先
  bfs(start) {
    const queue = [start];
    const result = [];
    const visited = {};
    visited[start] = true;
    let currentVertex;
    while (queue.length) {
      currentVertex = queue.shift();
      result.push(currentVertex);
      this.adjacencyList[currentVertex].forEach(neighbor => {
        if (!visited[neighbor]) {
          visited[neighbor] = true;
          queue.push(neighbor);
        }
      });
    }
    return result;
  }

  getRandomInteger(min, max) {
    return Math.floor(Math.random() * (max - min + 1)) + min;
  }
}

let N = 10;

let numGraph = new Graph();

let num = 0;
do {
  numGraph.addVertex(num);
  ++num;
} while (num < N);

let i = 0;
do {

  randB = numGraph.getRandomInteger(0, N - 1);
  randC = numGraph.getRandomInteger(0, N - 1);

  numGraph.addEdge(randB, randC);
  ++i;
} while (i < N);

numGraph.printGraph();
console.log(numGraph.dfs(0));
```

- [time=Fri, May 9, 2025 11:53 AM]

#### 3D Array

```javascript=
let graph = new Graph();
// Initialize a 3D array with dimensions 3x3x3
const rows = 3, cols = 3, depth = 3;
const arrtrpd = Array.from(
        { length: rows }, 
        () => Array.from({ length: cols }, 
        () =>  Array.from({ length: depth }, 
        () => graph.getRandomInteger(0, N-1)))
    );

let n = 0;
while (n < N) {
    graph.addVertex(n);
    ++n;
}

i = 0;
while (i < N){
    graph.addEdge(Array.from(
                                { length: rows }, 
                                () => Array.from({ length: cols }, 
                                () =>  Array.from({ length: depth }, 
                                () => graph.getRandomInteger(0, N-1)))
                            ), Array.from(
                                { length: rows }, 
                                () => Array.from({ length: cols }, 
                                () =>  Array.from({ length: depth }, 
                                () => graph.getRandomInteger(0, N-1)))
                            ));
}

graph.printGraph();  /* yet complete */
```

- [time=Sat, May 10, 2025 5:34 PM]