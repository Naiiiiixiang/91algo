# 思路

- 因为本题给出了最多元素个数，所以选择数组来模拟栈的操作
- 使用s来表示栈顶元素的索引
- 出栈和入栈的时候，要考虑到是否已空或者已满

# 代码

```java
class CustomStack {
    private int[] stack;
    private int s;
    public CustomStack(int maxSize) {
        stack = new int[maxSize];
        s = 0;
    }
    
    public void push(int x) {
        if (s == stack.length){
            return;
        }
        stack[s++] = x;
    }
    
    public int pop() {
        if (s == 0) return -1;
        return stack[--s];
    }
    
    public void increment(int k, int val) {
        int b = Math.min(k, s);
        for (int i = 0; i < b; i++){
            stack[i] += val;
        }
    }
}
```

# 复杂度

- 时间复杂度：

  push：O(1)

  pop：O(1)

  increment：O(min(k, s))

- 空间复杂度：

  O(maxSize)