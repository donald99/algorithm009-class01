有效的括号
```java
public static boolean isValid(String s) {
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
```

