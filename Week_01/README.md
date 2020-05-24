# 学习笔记

## 算法数据结构的目的？



###### 建立时间复杂度、空间复杂度意识，写出高质量的代码，能够设计基础架构，提升编程技能，训练逻辑思维，积攒人生经验，以此获得回报，实现价值，完善你的人生



###### 灵魂三问：

###### 算法是不是够优化？ 闪电 服务端 库 

###### 数据存取的效率是不是够高？

###### 内存是不是够节省？



### 如何行业内达到顶级专家的水平？

人的大脑不适合记忆孤立的无脉落的知识点

![](https://p5.ssl.qhimg.com/t01cd33f799a2f98fb4.png)

翻译：把知识看作是一棵语义树是很重要的——确保你理解了基本的原理，例如树干和大树枝，在你进入树叶/细节之前，或者没有什么东西可以让它们依附。https://www.reddit.com/user/ElonMuskOfficial/



#### 工具幕布：

https://share.mubu.com/doc/4R5XlkhLug0



把每个领域的知识弄成思维脑图，形成一颗树🌲并与自己已有的知识挂钩。

![](https://p3.ssl.qhimg.com/t010d1dbb03edc86cc4.png)

#### 一维：

基础：数组array（string），链表 linked list

高级：栈stack，队列 queue，双端队列deque，集合 set，映射 map（hash or map），etc

#### 二维：

基础：树tree ，图graph

高级：二叉搜索树binary search tree（red-black tree，AVL），堆heap，并查集disjoint set，字典树Trie，etc

#### 特殊：

位运算 Bitwise，布隆过滤器 BloomFliter

LRU Cache



### 如何精通一个领域？

《异类：不一样的成功启示录》

• Chunk it up 切碎知识点

• Deliberate Practicing 刻意练习

​              刻意训练：有效的刻意训练必须包含分片式训练、及时反馈、及时提高能力等级、将隐性知识显性化。

​              王者荣耀、吃鸡游戏典型训练方式

• Feedback 反馈

​      即时反馈、主动型反馈（自己去找）

​             高手代码（GitHub、Leetcode、etc）

​      被动反馈（高手给你指点）

​             code review

​             教练看你打，给你反馈



## 算法四步走：

1、跟同事确定这个题目的意思理解准确无误；

​      Clarification 澄清，说明

2、确定好所有的解法，对比出哪个是最好的和最坏的空间和时间复杂度；

​      Possible Solutions

​      compare（time/space）

​      optimal（加强）

3、找出最优的解，上手写最优解的算法程序；

​      Coding（多写）

4、测试所有可能的结果，增加程序的鲁棒性；

​      Test cases



### 练习过五遍以上：五毒神掌

1、看题审题，不会的题目，<u>切记别死磕</u>，10分钟为限，有好的模版就记住吧，反正想不出来

2、马上自己写--提交到leetcode上执行，***写不出来就背代码***，特别看那些discuss 投票高的代码

3、一天后再写

4、一周后再专项练习

5、前一周恢复性训练

####   误区：：：一个题目只做一遍是错误的！！！



### 写代码前的准备：

##### 键盘速度: 

​     便于写东西最快，提高responsive

​     https://www.bilibili.com/video/BV1Na4y147f2/?spm_id_from=333.788.videocard.1

##### VSCode + Leetcode插件

​    演示一下

##### Code Style：

​     http://google.github.io/styleguide/     

​    This project holds the [C++ Style Guide](https://google.github.io/styleguide/cppguide.html), [Swift Style Guide](https://google.github.io/swift/), [Objective-C Style Guide](http://google.github.io/styleguide/objcguide.html), [Java Style Guide](https://google.github.io/styleguide/javaguide.html), [Python Style Guide](https://google.github.io/styleguide/pyguide.html), [R Style Guide](https://google.github.io/styleguide/Rguide.html), [Shell Style Guide](https://google.github.io/styleguide/shellguide.html), [HTML/CSS Style Guide](https://google.github.io/styleguide/htmlcssguide.html), [JavaScript Style Guide](https://google.github.io/styleguide/jsguide.html), [AngularJS Style Guide](https://google.github.io/styleguide/angularjs-google-style.html), [Common Lisp Style Guide](https://google.github.io/styleguide/lispguide.xml), and [Vimscript Style Guide](https://google.github.io/styleguide/vimscriptguide.xml). This project also contains [cpplint](https://github.com/google/styleguide/tree/gh-pages/cpplint), a tool to assist with style guide compliance, and [google-c-style.el](https://raw.githubusercontent.com/google/styleguide/gh-pages/google-c-style.el), an Emacs settings file for Google style.*

##### CheckStyle plugin

![](https://p0.ssl.qhimg.com/t0168abda4fe570bd2b.png)



#### 网站：

 中文https://leetcode-cn.com/problems/move-zeroes/   国际https://leetcode.com/problems/move-zeroes/

#### 快捷键：

举例，刻意练习 VSCode Tips  

**10 Best Tips for  Visual Studio Code**

https://www.google.com.hk/search?q=vscode+top+tips&oq=vscode+top+tips&aqs=chrome..69i57j69i60.200j0j4&sourceid=chrome&ie=UTF-8

##### [宇宙最强vscode教程](https://segmentfault.com/a/1190000017949680)



### 认识时间复杂度和空间复杂度

常见复杂度：

| O(1)    | Constant Complexity    | 常数复杂度     |
| ------- | ---------------------- | -------------- |
| O(logn) | Logarithmic Complexity | 对数复杂度     |
| O(n)    | Linear Complexity      | 线性时间复杂度 |
| O(n^2)  | N square Complexity    | 平方           |
| O(n^3） | N cubic Complexity     | 立方           |
| O(2^n） | Exponetial Growth      | 指数           |
| O(n!)   | Factorial              | 阶乘           |



### 时间复杂度曲线：

![img](https://p4.ssl.qhimg.com/t0163198cc74e350b9e.png)



### 排序算法时间和空间复杂度

![](https://p0.ssl.qhimg.com/t01bdbf61477904df1e.png)



## Big-O-cheatsheet（https://www.bigocheatsheet.com）

![](https://p3.ssl.qhimg.com/t01d7e942df000a9790.png)



### 编程方式：

[自顶向下的编程方式](https://markhneedham.com/blog/2008/09/15/clean-code-book-review/)

```java
class Palindrome {

    public static void main(String[] args) {
     
        isPalindrome("A man, a plan, a canal: Panama");
    }
    
     public static boolean isPalindrome(String str) {

        //1、过滤掉 数字和字符 ； 2、revers and compare
        String filterString = filterStringAndChar(str);

        String reversString = reversString(filterString);

        return reversString.equalsIgnoreCase(filterString);
    }

    private static String reversString(String filterString) {
        return new StringBuilder(filterString).reverse().toString()
    }

    private static String filterStringAndChar(String str) {
        return str.replaceAll("[^A-Za-z0-9]","");
    }
}
```

冗余的业务代码，这样写的思路更加清晰。理清楚逻辑。



### 数组

http://developer.classpath.org/doc/java/util/ArrayList-source.html  

查找的复杂度：O(1)

增加、删除复杂度：O(n)

```java
/**
     * Adds the supplied element at the specified index, shifting all
     * elements currently at that index or higher one to the right.
     * The element, e, can be an object of any type or null.
     *
     * @param index the index at which the element is being added
     * @param e the item being added
   * @throws IndexOutOfBoundsException if index < 0 || index > size()
    */
   public void add(int index, E e)
    {
      checkBoundInclusive(index);
      modCount++;
      if (size == data.length)
        ensureCapacity(size + 1);
      if (index != size)
        System.arraycopy(data, index, data, index + 1, size - index);
     data[index] = e;
     size++;
   }
```

System.arraycopy函数，如果操作频繁的话，效率低



### 链表

##### CMU 15-121实现

[http://www.cs.cmu.edu/~adamchik/15-121/lectures/Linked%20Lists/code/LinkedList.java](http://www.cs.cmu.edu/~adamchik/15-121/lectures/Linked Lists/code/LinkedList.java)

##### 链表定义规范

https://www.geeksforgeeks.org/implementing-a-linked-list-in-java-using-class/

##### Java官方实现

http://developer.classpath.org/doc/java/util/LinkedList-source.html

随机查询任何一个元素: O(n)

前增加、后增加、插入、删除复杂度：O(1)



### 跳表

![](https://redisbook.readthedocs.io/en/latest/_images/skiplist.png)



查询有序的链表---> 二叉树、二分查找

插入、删除、搜索时间复杂度： O(log n)

空间复杂度：O(n)

用于Redis中的数据结构，为什么用于Redis呢？

https://www.zhihu.com/question/20202931
跳跃表 :

 https://redisbook.readthedocs.io/en/latest/internal-datastruct/skiplist.html

论文 ： https://www.cl.cam.ac.uk/teaching/0506/Algorithms/skiplists.pdf

##### 如何给链表访问加速？

###### 1、升维：在链表上添加多级索引

###### 2、空间换时间

### 栈、队列



### 解题思想：

找最近子问题，找重复问题。

计算机01只会做重复的事情，if else、for、while、recursive



### 题目：

## Array 

[盛最多水的容器](https://leetcode-cn.com/problems/container-with-most-water/)

```java
class Solution {
    // 暴力求解，枚举出所有可能
    // public int maxArea(int[] height) {
    //     int maxArea = 0;
    //     for (int i = 0;i < height.length - 1; i++) {
    //         for (int j = i + 1; j< height.length; j++) {
    //             int area = (j - i) * Math.min(height[i],height[j]);
    //             maxArea = Math.max(maxArea,area);
    //         }
    //     }
    //     return maxArea;
    // }

    // 夹逼法，从两边向中间枚举出所有可能
    public int maxArea(int[] h) {
        int maxArea = 0;
        for (int i = 0,j = h.length - 1; i < j;) {
            int minHeight = h[i] < h[j] ? h[i++] : h[j--];
            int area = (j - i + 1) * minHeight;
            maxArea = Math.max(maxArea,area);
        }
        return maxArea;
    }
}
```

[移动零](https://leetcode-cn.com/problems/move-zeroes/)

```java
class Solution {
    //双指针法，遍历数组遇到为0时快指针继续，慢指针停止，当快指针遇到非零数据，此时，赋值给慢指针数据，且在快慢指针不在同一位置时，给快指针赋值为0
    public void moveZeroes(int[] nums) {
        int j = 0;
        for(int i = 0;i < nums.length;i++){
            if (nums[i] != 0) {
                nums[j] = nums[i];
                if(i != j){
                    nums[i] = 0;
                }
                j++;
            }
        }
    }
}
```



[爬楼梯](https://leetcode.com/problems/climbing-stairs/)

```java
class Solution {
  //分别列举出不同台阶会有多少种步法，归纳法总结出，符合斐波那契数列 F(n) = F(n-2) + F(n-1)
    public int climbStairs(int n) {
        if (n < 2) {
            return 1;
        }
        return climbStairs(n - 2) + climbStairs(n - 1);
    }
}
```



[两数之和](https://leetcode-cn.com/problems/two-sum/)

```java
//暴力法很简单，遍历每个元素 xx，并查找是否存在一个值与 target - x 相等的目标元素。时间复杂度O(n^2),空间复杂度：O(1)。
class Solution {
    public int[] twoSum(int[] nums, int target) {
        for (int i = 0; i < nums.length; i++) {
            for (int j = i + 1; j < nums.length; j++) {
                if (target - nums[i] == nums[j]) {
                    return new int[] { i, j };
                }
            }
        }
        throw new IllegalArgumentException("No two sum solution");
    }
}

//一遍hash法时间复杂度：O(n)，空间复杂度：O(n)
//只遍历含有 n 个元素的列表一次。在表中进行的每次查找只花费 O(1) 的时间。
class Solution {
    public int[] twoSum(int[] nums, int target) {
        Map<Integer, Integer> map = new HashMap<>();
        for (int i = 0; i < nums.length; i++) {
            int complement = target - nums[i];
            if (map.containsKey(complement)) {
                return new int[] { map.get(complement), i };
            }
            map.put(nums[i], i);
        }
        throw new IllegalArgumentException("No two sum solution");
    }
}
```

[三数之和](https://leetcode-cn.com/problems/3sum/)

```java
//先排序，后遍历时间复杂度：O(n^2)，n为数组长度
class Solution {
    public List<List<Integer>> threeSum(int[] nums) {
        List<List<Integer>> result = new ArrayList<>();
        if (nums.length == 0) {
            return result;
        }
        Arrays.sort(nums);
        for (int i = 0;i < nums.length;i++) {
            if (i > 0 && nums[i] == nums[ i - 1]) { continue; }
            int target = -nums[i];
            int j = i + 1;
            int k = nums.length - 1;
            while(j < k){
                if (nums[j] + nums[k] == target) {
                    List<Integer> current = new ArrayList<>();
                    current.add(nums[i]);
                    current.add(nums[j]);
                    current.add(nums[k]);
                    result.add(current);
                    j++;k--;
                    while (j < nums.length && nums[j] == nums[j - 1]) j++;
                    while (k > j && nums[k] == nums[k + 1]) k--;
                } else if (nums[j] + nums[k] > target) {
                    k--;
                } else {
                    j++;
                }
            }
        }
        return result;
    }
}
```

![](https://p2.ssl.qhimg.com/t017aebade61c976627.png)

[加一](https://leetcode-cn.com/problems/plus-one/)

```java
//看到此题目，首先考虑了位数为9的情况，很显然不够全。
//参考高票的算法，真是绝啦，
//位置上数字+1操作 %=10 后 !=0,即可返回。
//若 %=10 每个位置都为0，只需要扩展数组一个单位，首位赋值为1，其余为0 即为所求结果。
class Solution {
    public int[] plusOne(int[] digits) {
        int len = digits.length;
        for (int i = len - 1; i >= 0; i--) {
            digits[i]++;
            digits[i] %= 10;
            if (digits[i] != 0) {
                return digits;
            }      
        }
        digits = new int[len + 1];
        digits[0] = 1;
        return digits;
    }
}
```





[合并两个有序数组](https://leetcode-cn.com/problems/merge-sorted-array/)

```java
class Solution {
    public void merge(int[] nums1, int m, int[] nums2, int n) {
        int len1 = m - 1;
        int len2 = n - 1;
        int len = m + n - 1;
        while(len1 >= 0 && len2 >= 0) {
            // 注意--符号在后面，表示先进行计算再减1，这种缩写缩短了代码
            nums1[len--] = (nums1[len1] > nums2[len2]) ? nums1[len1--] : nums2[len2--];
        }
        // 表示将nums2数组从下标0位置开始，拷贝到nums1数组中，从下标0位置开始，长度为len2+1
        System.arraycopy(nums2, 0, nums1, 0, len2 + 1);
    }
}
```





## Linked List 

[合并两个有序链表](https://leetcode-cn.com/problems/merge-two-sorted-lists/)

```
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) { val = x; }
 * }
 */
class Solution {
    public ListNode mergeTwoLists(ListNode list1, ListNode list2) {
        if (list1== null || list2 == null) {
            return list1 == null ? list2 : list1;
        }

        ListNode head = null;
        if (list1.val <= list2.val) {
            head = list1;
            head.next = mergeTwoLists(list1.next, list2);
        } else {
            head = list2;
            head.next = mergeTwoLists(list1, list2.next);
        }
        return head;
    }
}
```



[反转链表](https://leetcode.com/problems/reverse-linked-list/)

[两两交换链表中的节点](https://leetcode.com/problems/swap-nodes-in-pairs)

[环形链表](https://leetcode.com/problems/linked-list-cycle)

[环形链表 II](https://leetcode.com/problems/linked-list-cycle-ii)

[K 个一组翻转链表](https://leetcode.com/problems/reverse-nodes-in-k-group/)

## 栈和队列

[有效的括号](https://leetcode-cn.com/problems/valid-parentheses/)

```java
class Solution {
    public boolean isValid(String s) {
        Stack<Character> stack = new Stack();
        int len = s.length();
        if (len % 2 == 1) {return false;}
        for (int i = 0; i < len; i++) {
            char letter = s.charAt(i);
            switch (letter) {
                case '(' :{
                    stack.push(letter);
                    break;
                }
                case '[' :{
                    stack.push(letter);
                    break;
                }
                case '{' :{
                    stack.push(letter);
                    break;
                }
                case ')' :{
                    if (!stack.empty() && stack.pop() != '(') return false;
                    break;
                }
                case '}' :{
                    if (!stack.empty() && stack.pop() != '{') return false;
                    break;
                }
                case ']' :{
                    if (!stack.empty() && stack.pop() != '[') return false;
                    break;
                }
            }
        }
        return stack.size() == 0;
    }
}
```



[最小栈](https://leetcode-cn.com/problems/min-stack/)

```java
方案一：一个栈去保存正常的入栈出栈的值，另一个栈去存最小值，也就是用栈顶保存当前所有元素的最小值。

存最小值的栈的具体操作流程如下：
将第一个元素入栈。
新加入的元素如果大于栈顶元素，那么新加入的元素就不处理。
新加入的元素如果小于等于栈顶元素，那么就将新元素入栈。
出栈元素不等于栈顶元素，不操作。
出栈元素等于栈顶元素，那么就将栈顶元素出栈。

class MinStack {
    /** initialize your data structure here. */
    private Stack<Integer> stack;
    private Stack<Integer> minStack;

    public MinStack() {
        stack = new Stack<>();
        minStack = new Stack<>();
    }
    
    public void push(int x) {
        stack.push(x);
        if (!minStack.isEmpty()) {
            int top = minStack.peek();
            //小于的时候才入栈
            if (x <= top) {
                minStack.push(x);
            }
        }else{
            minStack.push(x);
        }
    }
    
    public void pop() {
        int pop = stack.pop();

        int top = minStack.peek();
        //等于的时候再出栈
        if (pop == top) {
            minStack.pop();
        }
    }
    
    public int top() {
        return stack.peek();
    }
    
    public int getMin() {
        return minStack.peek();
    }
}

/**
 * Your MinStack object will be instantiated and called as such:
 * MinStack obj = new MinStack();
 * obj.push(x);
 * obj.pop();
 * int param_3 = obj.top();
 * int param_4 = obj.getMin();
 */


方案二：用链表结构维护栈数据，每个节点更新最小值
 class MinStack {
    class Node{
        int value;
        int min;
        Node next;
        Node(int x, int min){
            this.value = x;
            this.min = min;
            next = null;
        }
    }
    Node head;
    //每次加入的节点放到头部
    public void push(int x) {
        if(null == head){
            head = new Node(x,x);
        }else{
            //当前值和之前头结点的最小值较小的做为当前的 min
            Node n = new Node(x, Math.min(x,head.min));
            n.next = head;
            head = n;
        }
    }
    public void pop() {
        if(head != null)
            head = head.next;
    }
    public int top() {
        if(head != null)
            return head.value;
        return -1;
    }
    public int getMin() {
        if(null != head)
            return head.min;
        return -1;
    }
}

```



[柱状图中最大的矩形](https://leetcode-cn.com/problems/largest-rectangle-in-histogram)

[滑动窗口最大值](https://leetcode-cn.com/problems/sliding-window-maximum)

[设计循环双端队列](https://leetcode.com/problems/design-circular-deque)

[接雨水](https://leetcode.com/problems/trapping-rain-water/)

