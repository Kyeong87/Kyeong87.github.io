---
title:  "[Programmers] 1.STEP(정렬) - k번째수"

categories:
  - Programmers
tags:
  - [Coding Test, Programmers]

toc: true
toc_sticky: true
 
date: 2021-11-15
last_modified_at: 2021-11-15
---

### :pencil2: 문제 

![스크린샷 2021-11-15 오후 5 56 07](https://user-images.githubusercontent.com/93639793/141752754-dd2aa713-d418-4da2-a093-92090aa21476.png)

  
    


### :o: 답

```java
import java.util.*;

class Solution {
    public int[] solution(int[] array, int[][] commands) {
        int[] answer = new int[commands.length];
        int i;
        int k;

        for(k=0;k<=(commands.length)-1;k++) {
            int[] j = new int[2];
            for(i=0;i<=(commands[k].length)-2;i++) {              
                j[i] = commands[k][i];
            }
            int[] data = Arrays.copyOfRange(array, j[0]-1, j[1]);
             Arrays.sort(data);
            int count = 0;
            for(int p : data){
                count++;
                if(count==commands[k][2]) answer[k] = p; 
             }

        }
        return answer;
    }
}
```

### :closed_book: 풀이

```java
Arrays.copyOfRange(array, j[0]-1, j[1]);
```  

Arrays.sort 찾아보다가 건졌다.  
근데 배열 요소처럼 0,1,2 나가는데 아니라 1,2,3 로 시작해서  
당황했지만, 풀었다 :+1:  
  
다른사람풀이 보니까 for문을 1개만 써서도 가능하던데,  
효율성은 나중에 생각해보는걸로 :sleeping:  


내일도 가즈아~ :grinning:
