# 思路
通过使用双指针来计算当前位置的最小距离。当索引等于右指针的位置后，及时地更新两个指针的位置。这样可以保证最小距离的计算结果的正确性。

# 代码
```java
class Solution {
    public int[] shortestToChar(String s, char c) {
        int[] result = new int[s.length()];
        int first = s.indexOf(c);
        int second = s.indexOf(c, first+1) != -1 ? s.indexOf(c, first+1) : first;
        for (int i=0; i<s.length();i++){
            int dis1 = Math.abs(i - first);
            int dis2 = Math.abs(i - second);
            result[i] = dis1 <= dis2 ? dis1 : dis2;
            if(i == second){
                first = second;
                second = s.indexOf(c, first+1) != -1 ? s.indexOf(c, first+1) : first;
            }
        }
        return result;
    }
}
```
