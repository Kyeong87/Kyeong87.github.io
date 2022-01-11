---
title:  "[Java] collection framework(컬렉션 프레임워크)"

categories:
  - Java
tags:
  - [Java, collectionframework]

toc: true
toc_sticky: true
 
date: 2021-12-08
last_modified_at: 2021-12-08
---

<br>  

## :one:&nbsp;&nbsp;&nbsp;  collection framework?
 
다수의 데이터를 쉽고 효과적으로 처리할 수 있는 표준화된 방법을 제공하는 클래스의 집합을 의미합니다

즉, 데이터를 저장하는 자료 구조와 데이터를 처리하는 알고리즘을 구조화하여 클래스로 구현해 놓은 것입니다.
<br>
<br>

## :two:&nbsp;&nbsp;&nbsp; collection framework 특징

![스크린샷 2021-12-08 오후 5 55 18](https://user-images.githubusercontent.com/93639793/145178963-3c19fee7-eff4-4c9f-be31-695070c778fc.png)

<br>
<br>

## :three: &nbsp;&nbsp;&nbsp; 컬렉션 클래스(collection class)
컬렉션 프레임워크에 속하는 인터페이스를 구현한 클래스를 컬렉션 클래스(collection class)라고 합니다.   
컬렉션 프레임워크의 모든 컬렉션 클래스는 List와 Set, Map 인터페이스 중 하나의 인터페이스를 구현하고 있습니다.   

또한, 클래스 이름에도 구현한 인터페이스의 이름이 포함되므로 바로 구분할 수 있습니다.   

새로 추가된 ArrayList나 HashMap 클래스를 사용하는 것이 성능 면에서도 더 나은 결과를 얻을 수 있습니다.   
```java
public class Collection01 {
    public static void main(String[] args) {
        // 리스트 생성
        ArrayList<String> arrList = new ArrayList<String>();
        // 리스트에 요소의 저장
        arrList.add("넷");
        arrList.add("둘");
        arrList.add("셋");
        arrList.add("하나");
        // 리스트요소의 출력
        for(int i = 0; i < arrList.size(); i++) {
            System.out.println(arrList.get(i));
        }
    }
}
```
<br>
<br>

## :three:&nbsp;&nbsp;&nbsp;Collection 인터페이스   
List와 Set 인터페이스의 많은 공통된 부분을 Collection 인터페이스에서 정의하고, 두 인터페이스는 그것을 상속받습니다.   

따라서 Collection 인터페이스는 컬렉션을 다루는데 가장 기본적인 동작들을 정의하고, 그것을 메소드로 제공하고 있습니다.

![스크린샷 2021-12-08 오후 6 02 34](https://user-images.githubusercontent.com/93639793/145179667-48ecd98e-ba74-44be-8247-a53fddb41ab8.png)   




- 출처 : http://tcpschool.com/java/java_collectionFramework_concept
