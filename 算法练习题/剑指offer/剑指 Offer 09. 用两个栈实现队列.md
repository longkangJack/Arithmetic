用栈实现队列

用两个栈实现队列

思路:创建两个栈s1 s2

s2用来模拟入队。s1用来模拟出队

后面设计思路就非常的简单

```c++
class CQueue {
public:
 stack<int> a;//入队
    stack<int> b;//出队
    CQueue() {
    }
    void appendTail(int value) {
        a.push(value);
    }
    int deleteHead() {
        if(b.empty()&&a.empty())
        return -1;
        else if(b.empty()&&!a.empty())
        {
            while(!a.empty())
            {
                b.push(a.top());
                a.pop();
            }
        }
        int tmp = b.top();
        b.pop();
        return tmp;         
    }
};
```

