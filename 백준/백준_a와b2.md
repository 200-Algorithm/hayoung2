# [백준] A와 B 2

```protobuf
S = input().strip()
T = input().strip()

def can_convert(cur):
    # 길이가 같아졌을 때 똑같으면 성공
    if len(cur) == len(S):
        return cur == S

    # 1) 맨 뒤가 A라면 → 그 A 빼고 다시 시도
    if cur.endswith('A'):
        if can_convert(cur[:-1]):
            return True

    # 2) 맨 앞이 B라면 → B를 제거하고 뒤집어서 다시 시도
    if cur.startswith('B'):
        next_str = cur[1:][::-1]
        if can_convert(next_str):
            return True

    # 둘 다 안 되면 실패
    return False

print(1 if can_convert(T) else 0)

```