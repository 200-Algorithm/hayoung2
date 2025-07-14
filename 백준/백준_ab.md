# [백준] A → B

1. 성공

```python
from collections import deque
a,b=map(int,input().split())
que=deque()
que.append([a,1])
while que:
    x,dis=que.popleft()
    if x==b:
        print(dis)
        break

    tmp=str(x)+'1'
    if int(tmp) <=b:
        que.append([int(tmp),dis+1])
    if x*2<=b:
        que.append([x * 2, dis + 1])
else:
    print(-1)
```