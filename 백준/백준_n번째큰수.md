# [백준] N번째 큰 수

```protobuf
import heapq

n=int(input())
heap=[]
for i in range(n):
    arr=list(map(int,input().split()))
    for j in arr:
        if len(heap)<n:
            heapq.heappush(heap,j)
        else:
            tmp=heapq.heappop(heap)
            if j > tmp:
                heapq.heappush(heap,j)
            else:
                heapq.heappush(heap,tmp)

print(heap[0
```