```java
import java.util.Deque;
import java.util.LinkedList;

public class DequeCode {

    public static void main(String[] args) {

        deque();

        //使用新的API
        dequeNew();
    }

    private static void dequeNew(){
        Deque<String> deque = new LinkedList<>();
        deque.addFirst("a");
        deque.addFirst("b");
        deque.addFirst("c");
        System.out.println(deque);

        String str = deque.getFirst();
        System.out.println(str);
        System.out.println(deque);

        while(deque.size() > 0){
            System.out.println(deque.pollFirst());
        }
        System.out.println(deque);
    }

    private static void deque(){
        Deque<String> deque = new LinkedList<>();
        deque.push("a");
        deque.push("b");
        deque.push("c");
        System.out.println(deque);

        String str = deque.peek();
        System.out.println(str);
        System.out.println(deque);

        while(deque.size() > 0){
            System.out.println(deque.pop());
        }
        System.out.println(deque);
    }
}

//        [c, b, a]
//        c
//        [c, b, a]
//        c
//        b
//        a
//        []
```

