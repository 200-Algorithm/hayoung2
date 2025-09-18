# [백준] 미로만들기

1. 성공

```protobuf
from collections import deque
import copy
n=int(input())
arr=[]
for i in range(n):
    arr.append(list(map(int,input())))

que=deque()
visited=[[float('inf')]*n for _ in range(n)]
que.append([0,0])
minv=float('inf')
visited[0][0]=0
d=0
while que:
    r,c=que.popleft()
    for idx in [(1,0),(-1,0),(0,-1),(0,1)]:
        nr,nc=r+idx[0],c+idx[1]
        if 0<=nr<n and 0<=nc<n:

            if arr[nr][nc]==0:
                d=visited[r][c]+1
            else:
                d=visited[r][c]

            if visited[nr][nc] > d:
                if arr[nr][nc]==0:
                    visited[nr][nc] = d
                    que.append([nr,nc])
                else:
                    visited[nr][nc]=d
                    que.append([nr,nc])

print(visited[n-1][n-1])

```