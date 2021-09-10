# 思路

总体思路仿照的是，加法计算过程。采用最低位向前依次递进的方式。最后逆序输出。

# 代码

```java
class Solution {
    public List<Integer> addToArrayForm(int[] num, int k) {
        int n = num.length;
        List<Integer> res = new ArrayList<Integer>();

        for (int i = n - 1; i >= 0 || k > 0; i--) {
            if (i >= 0) {
                k += num[i];
            }
            res.add(k % 10);
            k /= 10;
        }
        Collections.reverse(res);
        return res;
    }
}
```

# 复杂度

时间复杂度：
$$
O(n)
$$
空间复杂度：
$$
O(n)
$$


