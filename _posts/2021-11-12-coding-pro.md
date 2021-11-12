---
title:  "[Coding Test] 1.STEP(해시) - 완주하지 못한 선수"

categories:
  - CodingTest
tags:
  - [Coding Test, Programmers]

toc: true
toc_sticky: true
 
date: 2011-11-12
last_modified_at: 2011-11-12
---

### :pencil2: 문제 

![image](https://user-images.githubusercontent.com/93639793/141441504-85553be3-7219-4477-90a1-e436e78557c0.png)    

  
    


### :negative_squared_cross_mark: 답

```java
import java.util.ArrayList;
import java.util.Arrays;
import java.util.List;

class Solution {
    public String solution(String[] participant, String[] completion) {
        Arrays.sort(participant);
        Arrays.sort(completion);
        int i;
        for (i=0; i<completion.length; i++){
            if (!participant[i].equals(completion[i])){
                return participant[i];
            }
        }
        return participant[i];
    }
}
```

### :closed_book: 풀이

```java
Arrays.sort(participant);
```  

Arrays -> 배열(Array)을 정렬, 복제하거나, List로 변환 하는 등의 작업을 쉽게 처리 할 수 있다.
sort() -> 오름차순 정렬

String[] 으로 받은걸 배열로 변환 오름차순 정렬을 해준듯 하다.  
(나는 바보다. 1단계인데 난 바보다. :sob:)  

for문에서 equals는 파악 했는데, 이걸 나는 for문 2개로 나눠서 돌려서 남는걸 넣어야한다고 생각했는데  
바보인걸로 깔끔하게 인정하도록 하자 :disappointed_relieved:

