---
title:  "[Java] Set collection(set 컬렉션)"

categories:
  - Java
tags:
  - [Java, collectionframework, Setcollection]

toc: true
toc_sticky: true
 
date: 2021-12-08
last_modified_at: 2021-12-08
---

<br>  

## :one:&nbsp;&nbsp;&nbsp;  Set 컬렉션 클래스?
 요소의 저장 순서가 유지하지 않음. 같은 요소의 중복 저장을 허용안함. 
(list와 반대)
<br>
<br>

## :two:&nbsp;&nbsp;&nbsp; HashSet\<E> 클래스

HashSet 클래스는 해시 알고리즘(hash algorithm)을 사용하여 검색 속도가 매우 빠릅니다

```java
HashSet<String> hs01 = new HashSet<String>();
HashSet<String> hs02 = new HashSet<String>();
// add() 메소드를 이용한 요소의 저장
hs01.add("홍길동");
hs01.add("이순신");
System.out.println(hs01.add("임꺽정"));
System.out.println(hs01.add("임꺽정")); // 중복된 요소의 저장

// Enhanced for 문과 get() 메소드를 이용한 요소의 출력
for (String e : hs01) {
    System.out.print(e + " ");
}
// add() 메소드를 이용한 요소의 저장
hs02.add("임꺽정");
hs02.add("홍길동");
hs02.add("이순신");

// iterator() 메소드를 이용한 요소의 출력
Iterator<String> iter02 = hs02.iterator();
while (iter02.hasNext()) {
    System.out.print(iter02.next() + " ");
}


// size() 메소드를 이용한 요소의 총 개수
System.out.println("집합의 크기 : " + hs02.size());
```

<br>
<br>

## :three:&nbsp;&nbsp;&nbsp; 해시 알고리즘(hash algorithm)    





- 출처 : http://tcpschool.com/java/java_collectionFramework_concept
