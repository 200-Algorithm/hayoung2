# [백준] Four Squares

1. gpt 동적계획너무어려움….

```python
n=int(input())
dp=[0]*(n+1)
dp[1]=1
 # 최소 개수의 제곱수 합으로 표현
for i in range(2,n+1): 
    j=1
    minv=float('inf')
    while j*j <=i : # 같으면 dp[0]=0뒤에 +1
    #다르면  남은 값을 제곱수들로 구성한 최소 개수(dp[i - j*j]) 중 최솟값 찾기
        minv=min(minv, dp[i-j*j])
        j+=1
    dp[i] = minv+1

print(dp[n])

```

| i | dp[i] | 이유 |
| --- | --- | --- |
| 1 | 1 | 1 = 1² |
| 2 | 2 | 1 + 1 |
| 3 | 3 | 1 + 1 + 1 |
| 4 | 1 | 2² |
| 5 | 2 | 4 + 1 |
| 6 | 3 | 4 + 1 + 1 |
| 7 | 4 | 4 + 1 + 1 + 1 |
| 8 | 2 | 4 + 4 |
| 9 | 1 | 3² |