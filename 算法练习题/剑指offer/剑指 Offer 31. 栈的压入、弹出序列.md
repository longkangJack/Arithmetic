#### [剑指 Offer 31. 栈的压入、弹出序列](https://leetcode-cn.com/problems/zhan-de-ya-ru-dan-chu-xu-lie-lcof/)

```c++
class Solution {
public:
    bool validateStackSequences(vector<int>& pushed, vector<int>& popped) {
        stack<int> st;
        int i = 0;
        int j = 0;
        while(i<pushed.size()&&j<popped.size())
        {
            st.push(pushed[i++]);
            while(j<popped.size()&&!st.empty()&&st.top()==popped[j])
                {st.pop();
                j++;
                }                    
        }
        return st.empty();
    }
};
```

思路：判断是否为他的出栈顺序，创建一个栈，然后将数组1入栈，入一个判断栈顶元素是否和出栈顺序的第一个元素一致，一致则将该元素出栈，如果不一致，则继续入栈，然后在判断。

最后当栈空时，则证明是出栈顺序。