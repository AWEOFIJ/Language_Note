---
title: JAVA 筆記

---

# JAVA 筆記

`Note` `2025.02.28`

 - Start: [time=Wed, May 28, 2025 1:50 PM]
 - Last Update: [time=Tue, Sep 16, 2025 3:37 PM]

### Gemini 產生範例

好的，這是一個使用 Java 8 實現泡泡排序法的範例程式碼。

```java=
import java.util.Arrays;

public class BubbleSort {

    public static void main(String[] args) {
        int[] arr = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9};
        System.out.println("原始陣列: " + Arrays.toString(arr));

        bubbleSort(arr);

        System.out.println("排序後的陣列: " + Arrays.toString(arr));

        // 測試其他案例
        int[] arr2 = {5, 1, 4, 2, 8};
        System.out.println("\n原始陣列 (arr2): " + Arrays.toString(arr2));
        bubbleSort(arr2);
        System.out.println("排序後的陣列 (arr2): " + Arrays.toString(arr2));

        int[] arr3 = {}; // 空陣列
        System.out.println("\n原始陣列 (arr3): " + Arrays.toString(arr3));
        bubbleSort(arr3);
        System.out.println("排序後的陣列 (arr3): " + Arrays.toString(arr3));

        int[] arr4 = {7}; // 單一元素陣列
        System.out.println("\n原始陣列 (arr4): " + Arrays.toString(arr4));
        bubbleSort(arr4);
        System.out.println("排序後的陣列 (arr4): " + Arrays.toString(arr4));
    }

    /**
     * 使用泡泡排序法對整數陣列進行排序。
     *
     * @param arr 要排序的整數陣列。
     */
    public static void bubbleSort(int[] arr) {
        int n = arr.length;
        boolean swapped; // 判斷是否發生交換，若一輪沒有交換表示已排序完成

        for (int i = 0; i < n - 1; i++) {
            swapped = false;
            // 每一輪會將最大的元素「浮」到最右邊已排序的位置
            // 因此內層迴圈的範圍會遞減
            for (int j = 0; j < n - i - 1; j++) {
                if (arr[j] > arr[j + 1]) {
                    // 交換 arr[j] 和 arr[j+1]
                    int temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
                    swapped = true;
                }
            }

            // 如果一輪沒有發生任何交換，表示陣列已經排序完成
            if (!swapped) {
                break;
            }
        }
    }
}
```

程式碼解釋：
 * BubbleSort 類別： 包含 main 方法和 bubbleSort 方法。
 * main 方法：
   * 定義了一個整數陣列 arr 作為範例。
   * 列印原始陣列。
   * 呼叫 bubbleSort 方法對陣列進行排序。
   * 列印排序後的陣列。
   * 包含了一些額外的測試案例來驗證程式的"合理"性。
 * bubbleSort(int[] arr) 方法：
   * int n = arr.length;: 取得陣列的長度。
   * boolean swapped;: 這是泡泡排序的一個優化點。如果在一輪內層迴圈中沒有任何元素被交換，表示陣列已經是排序好的，這時就可以提前終止排序，避免不必要的比較。
   * 外層迴圈 for (int i = 0; i < n - 1; i++):
     * 這個迴圈控制排序的「輪數」。對於一個有 n 個元素的陣列，最多需要 n-1 輪才能完成排序。
     * 每一輪都會將一個最大的（或最小的，取決於排序方向）未排序元素移動到其最終的正確位置。
   * 內層迴圈 for (int j = 0; j < n - 1 - i; j++):
     * 這個迴圈負責遍歷未排序的部分，並比較相鄰的元素。
     * n - 1 - i：隨著外層迴圈的進行，右邊的 i 個元素已經排序好，所以內層迴圈的比較範圍會逐漸縮小。
     * if (arr[j] > arr[j + 1]): 如果當前元素 arr[j] 大於下一個元素 arr[j + 1]，則它們的順序不正確，需要進行交換。
     * 交換操作：
       int temp = arr[j];
arr[j] = arr[j + 1];
arr[j + 1] = temp;
swapped = true; // 標記發生了交換

   * 優化：if (!swapped) { break; }: 如果內層迴圈執行完畢後 swapped 仍然是 false，表示這一輪沒有發生任何交換，說明陣列已經完全排序，可以提前結束外層迴圈。
泡泡排序法的特性：
 * 時間複雜度：
   * 最壞情況： O(n^2) (例如，當陣列完全逆序時)。
   * 平均情況： O(n^2)。
   * 最好情況： O(n) (當陣列已經排序好時，因為有優化)。
 * 空間複雜度： O(1) (原地排序，不需額外的大量空間)。
 * 穩定性： 穩定排序演算法（相等元素的相對順序不會改變）。
雖然泡泡排序在實際應用中效率不高，但它是一個很好的入門級排序演算法，有助於理解排序的基本概念。

- [time=Fri, Aug 1, 2025 12:06 AM]

---


### Binary Tree

```java=
public class BinaryTree {

    // 定義二元樹節點結構
    static class Node {
        int data;
        Node left;
        Node right;

        Node(int data) {
            this.data = data;
            this.left = null;
            this.right = null;
        }
    }

    // 建立新節點
    static Node createNode(int data) {
        return new Node(data);
    }

    // 修改節點資料
    static void modifyNode(Node node, int newData) {
        if (node != null) {
            node.data = newData;
        }
    }

    // 前序遍歷：根 → 左 → 右
    static void preOrderTraversal(Node root) {
        if (root != null) {
            System.out.print(root.data + " ");
            preOrderTraversal(root.left);
            preOrderTraversal(root.right);
        }
    }

    // 中序遍歷：左 → 根 → 右
    static void inOrderTraversal(Node root) {
        if (root != null) {
            inOrderTraversal(root.left);
            System.out.print(root.data + " ");
            inOrderTraversal(root.right);
        }
    }

    // 後序遍歷：左 → 右 → 根
    static void postOrderTraversal(Node root) {
        if (root != null) {
            postOrderTraversal(root.left);
            postOrderTraversal(root.right);
            System.out.print(root.data + " ");
        }
    }

    public static void main(String[] args) {
        // 建立節點並構建樹結構
        Node root = createNode(0);
        root.left = createNode(1);
        root.right = createNode(2);
        root.left.left = createNode(3);
        root.left.right = createNode(4);
        root.right.left = createNode(5);
        root.right.right = createNode(6);
        root.left.left.left = createNode(7);
        root.left.left.right = createNode(8);
        root.left.right.left = createNode(9);

        System.out.print("Pre-order Traversal: ");
        preOrderTraversal(root);
        System.out.println();

        System.out.print("In-order Traversal: ");
        inOrderTraversal(root);
        System.out.println();

        System.out.print("Post-order Traversal: ");
        postOrderTraversal(root);
        System.out.println();
    }
}
```
```
Pre-order Traversal: 0 1 3 7 8 4 9 2 5 6
In-order Traversal: 7 3 8 1 9 4 0 5 2 6
Post-order Traversal: 7 8 3 9 4 1 5 6 2 0
```

- [time=Tue, Sep 16, 2025 3:37 PM]

#### Acknowledge

* [Java SE8 OCAJP專業認證指南](https://www.books.com.tw/products/E050057008?sloc=main)
* [Java SE8 OCPJP進階認證指南](https://www.books.com.tw/products/E050057009?loc=P_br_r0vq68ygz_D_2aabd0_C_2)# JAVA 筆記

`Note` `2025.02.28`

 - Start: [time=Wed, May 28, 2025 1:50 PM]
 - Last Update: [time=Tue, Sep 16, 2025 3:37 PM]

### Gemini 產生範例

好的，這是一個使用 Java 8 實現泡泡排序法的範例程式碼。

```java=
import java.util.Arrays;

public class BubbleSort {

    public static void main(String[] args) {
        int[] arr = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9};
        System.out.println("原始陣列: " + Arrays.toString(arr));

        bubbleSort(arr);

        System.out.println("排序後的陣列: " + Arrays.toString(arr));

        // 測試其他案例
        int[] arr2 = {5, 1, 4, 2, 8};
        System.out.println("\n原始陣列 (arr2): " + Arrays.toString(arr2));
        bubbleSort(arr2);
        System.out.println("排序後的陣列 (arr2): " + Arrays.toString(arr2));

        int[] arr3 = {}; // 空陣列
        System.out.println("\n原始陣列 (arr3): " + Arrays.toString(arr3));
        bubbleSort(arr3);
        System.out.println("排序後的陣列 (arr3): " + Arrays.toString(arr3));

        int[] arr4 = {7}; // 單一元素陣列
        System.out.println("\n原始陣列 (arr4): " + Arrays.toString(arr4));
        bubbleSort(arr4);
        System.out.println("排序後的陣列 (arr4): " + Arrays.toString(arr4));
    }

    /**
     * 使用泡泡排序法對整數陣列進行排序。
     *
     * @param arr 要排序的整數陣列。
     */
    public static void bubbleSort(int[] arr) {
        int n = arr.length;
        boolean swapped; // 判斷是否發生交換，若一輪沒有交換表示已排序完成

        for (int i = 0; i < n - 1; i++) {
            swapped = false;
            // 每一輪會將最大的元素「浮」到最右邊已排序的位置
            // 因此內層迴圈的範圍會遞減
            for (int j = 0; j < n - i - 1; j++) {
                if (arr[j] > arr[j + 1]) {
                    // 交換 arr[j] 和 arr[j+1]
                    int temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
                    swapped = true;
                }
            }

            // 如果一輪沒有發生任何交換，表示陣列已經排序完成
            if (!swapped) {
                break;
            }
        }
    }
}
```

程式碼解釋：
 * BubbleSort 類別： 包含 main 方法和 bubbleSort 方法。
 * main 方法：
   * 定義了一個整數陣列 arr 作為範例。
   * 列印原始陣列。
   * 呼叫 bubbleSort 方法對陣列進行排序。
   * 列印排序後的陣列。
   * 包含了一些額外的測試案例來驗證程式的"合理"性。
 * bubbleSort(int[] arr) 方法：
   * int n = arr.length;: 取得陣列的長度。
   * boolean swapped;: 這是泡泡排序的一個優化點。如果在一輪內層迴圈中沒有任何元素被交換，表示陣列已經是排序好的，這時就可以提前終止排序，避免不必要的比較。
   * 外層迴圈 for (int i = 0; i < n - 1; i++):
     * 這個迴圈控制排序的「輪數」。對於一個有 n 個元素的陣列，最多需要 n-1 輪才能完成排序。
     * 每一輪都會將一個最大的（或最小的，取決於排序方向）未排序元素移動到其最終的正確位置。
   * 內層迴圈 for (int j = 0; j < n - 1 - i; j++):
     * 這個迴圈負責遍歷未排序的部分，並比較相鄰的元素。
     * n - 1 - i：隨著外層迴圈的進行，右邊的 i 個元素已經排序好，所以內層迴圈的比較範圍會逐漸縮小。
     * if (arr[j] > arr[j + 1]): 如果當前元素 arr[j] 大於下一個元素 arr[j + 1]，則它們的順序不正確，需要進行交換。
     * 交換操作：
       int temp = arr[j];
arr[j] = arr[j + 1];
arr[j + 1] = temp;
swapped = true; // 標記發生了交換

   * 優化：if (!swapped) { break; }: 如果內層迴圈執行完畢後 swapped 仍然是 false，表示這一輪沒有發生任何交換，說明陣列已經完全排序，可以提前結束外層迴圈。
泡泡排序法的特性：
 * 時間複雜度：
   * 最壞情況： O(n^2) (例如，當陣列完全逆序時)。
   * 平均情況： O(n^2)。
   * 最好情況： O(n) (當陣列已經排序好時，因為有優化)。
 * 空間複雜度： O(1) (原地排序，不需額外的大量空間)。
 * 穩定性： 穩定排序演算法（相等元素的相對順序不會改變）。
雖然泡泡排序在實際應用中效率不高，但它是一個很好的入門級排序演算法，有助於理解排序的基本概念。

- [time=Fri, Aug 1, 2025 12:06 AM]

---


### Binary Tree

```java=
public class BinaryTree {

    // 定義二元樹節點結構
    static class Node {
        int data;
        Node left;
        Node right;

        Node(int data) {
            this.data = data;
            this.left = null;
            this.right = null;
        }
    }

    // 建立新節點
    static Node createNode(int data) {
        return new Node(data);
    }

    // 修改節點資料
    static void modifyNode(Node node, int newData) {
        if (node != null) {
            node.data = newData;
        }
    }

    // 前序遍歷：根 → 左 → 右
    static void preOrderTraversal(Node root) {
        if (root != null) {
            System.out.print(root.data + " ");
            preOrderTraversal(root.left);
            preOrderTraversal(root.right);
        }
    }

    // 中序遍歷：左 → 根 → 右
    static void inOrderTraversal(Node root) {
        if (root != null) {
            inOrderTraversal(root.left);
            System.out.print(root.data + " ");
            inOrderTraversal(root.right);
        }
    }

    // 後序遍歷：左 → 右 → 根
    static void postOrderTraversal(Node root) {
        if (root != null) {
            postOrderTraversal(root.left);
            postOrderTraversal(root.right);
            System.out.print(root.data + " ");
        }
    }

    public static void main(String[] args) {
        // 建立節點並構建樹結構
        Node root = createNode(0);
        root.left = createNode(1);
        root.right = createNode(2);
        root.left.left = createNode(3);
        root.left.right = createNode(4);
        root.right.left = createNode(5);
        root.right.right = createNode(6);
        root.left.left.left = createNode(7);
        root.left.left.right = createNode(8);
        root.left.right.left = createNode(9);

        System.out.print("Pre-order Traversal: ");
        preOrderTraversal(root);
        System.out.println();

        System.out.print("In-order Traversal: ");
        inOrderTraversal(root);
        System.out.println();

        System.out.print("Post-order Traversal: ");
        postOrderTraversal(root);
        System.out.println();
    }
}
```
```
Pre-order Traversal: 0 1 3 7 8 4 9 2 5 6
In-order Traversal: 7 3 8 1 9 4 0 5 2 6
Post-order Traversal: 7 8 3 9 4 1 5 6 2 0
```

- [time=Tue, Sep 16, 2025 3:37 PM]

#### Acknowledge

* [Java SE8 OCAJP專業認證指南](https://www.books.com.tw/products/E050057008?sloc=main)
* [Java SE8 OCPJP進階認證指南](https://www.books.com.tw/products/E050057009?loc=P_br_r0vq68ygz_D_2aabd0_C_2)