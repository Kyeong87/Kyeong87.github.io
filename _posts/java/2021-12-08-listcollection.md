---
title:  "[Java] list collection(리스트 컬렉션)"

categories:
  - Java
tags:
  - [Java, collectionframework, listcollection]

toc: true
toc_sticky: true
 
date: 2021-12-08
last_modified_at: 2021-12-08
---

<br>  

## :one:&nbsp;&nbsp;&nbsp;  List 컬렉션 클래스?
 요소의 저장 순서가 유지됩니다. 같은 요소의 중복 저장을 허용합니다. 

 (처음 접했을때 굉장히 희안한 모양이라 생각 되었음. php는 <> 괄호를 사용하지 않아서...)
<br>
<br>

## :two:&nbsp;&nbsp;&nbsp; ArrayList\<E> 클래스

ArrayList 클래스는 배열을 이용하기 때문에 인덱스를 이용해 배열 요소에 빠르게 접근할 수 있습니다

```java
ArrayList<Integer> arrList = new ArrayList<Integer>();
// add() 메소드를 이용한 요소의 저장
arrList.add(40);
arrList.add(20);
arrList.add(30);
arrList.add(10);
// for 문과 get() 메소드를 이용한 요소의 출력
for (int i = 0; i < arrList.size(); i++) {
    System.out.print(arrList.get(i) + " ");
}
// remove() 메소드를 이용한 요소의 제거
arrList.remove(1);
// Enhanced for 문과 get() 메소드를 이용한 요소의 출력
for (int e : arrList) {
    System.out.print(e + " ");
}
// Collections.sort() 메소드를 이용한 요소의 정렬
Collectio ns.sort(arrList);
// iterator() 메소드와 get() 메소드를 이용한 요소의 출력
Iterator<Integer> iter = arrList.iterator();
while (iter.hasNext()) {
    System.out.print(iter.next() + " ");
}
// set() 메소드를 이용한 요소의 변경
arrList.set(0, 20);
for (int e : arrList) {
    System.out.print(e + " ");
}
// size() 메소드를 이용한 요소의 총 개수
System.out.println("리스트의 크기 : " + arrList.size());
```

<br>
<br>






- 출처 : http://tcpschool.com/java/java_collectionFramework_concept
