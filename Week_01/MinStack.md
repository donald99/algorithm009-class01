MinStack

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