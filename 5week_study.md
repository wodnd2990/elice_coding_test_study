## 프린터

```python
def solution(priorities, location):

    addIndex = []
    for i, v in enumerate(priorities):
        addIndex.append((v, i))
    print("addIndex : ", addIndex)
    # print("max(addIndex)[0] : ", max(addIndex)[0])
    result = []
    b = 0
    while True:
        for i in range(len(addIndex)):
            if addIndex[0][0] != max(addIndex)[0]:
                addIndex.append(addIndex.pop(0))
            else:
                result.append(addIndex.pop(0))
                if len(addIndex) == 0:
                    b = 1
                    break
        if b == 1:
            break
     
    # print("result : ", result)
    answer = 0
    for i, v in enumerate(result):
        if v[1] == location:
            answer = i + 1
            
    return answer
    

print(solution([2, 1, 3, 2, 4, 1, 7, 7], 2)) # 1


```



## 더 맵게

```python
def solution(scoville, K):
    scoville_len = len(scoville)
    
    while True:
        if min(scoville) >= K:
            return scoville_len - len(scoville)
        elif len(scoville) == 1:
            return -1
            
        
        one = scoville.pop(scoville.index(min(scoville)))
        two = scoville.pop(scoville.index(min(scoville)))
        scoville.insert(0, (one + two * 2))
    
    


print(solution([1, 2, 3, 9, 10, 12], 7))
```







