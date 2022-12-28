---
title:  "[Java] spring Bean"

categories:
  - Spring
tags:
  - [Spring, Bean]

toc: true
toc_sticky: true
 
date: 2022-08-26
last_modified_at: 2022-08-26
---

<br>  

## :one:&nbsp;&nbsp;&nbsp;  spring 의존관계 ?

<img width="620" alt="캡쳐 9" src="https://user-images.githubusercontent.com/93639793/186800790-a974b39e-8aa0-47c9-b0bc-4be504ae8114.png">

<br>

- controller 에서 service를 통해서 데이터를 조회하고, 데이터를 저장하는거
controller가 service를 의존한다고 함.   

- @controller 라는 어노테이션이 있으면 스프링이 시작될때 어노테이션을 보고 객체를 생성해서 스프링 컨테이너에서 들고있음 ( -> 스프링 컨테이너에서 스프링 빈이 관리된다라고 표현함! )



```java
@Controller
public class MemberController {
    private final MemberService memberService = new MemberService();
    // 멤버컨트롤러말고 다른 주문컨트롤러에서 멤버컨트롤러를 가져쓸수있음, 근데 new로 해줬을때 그럼 여러개가 생성됨,, (멤버컨트롤러에도 생성, 주문컨트롤러에서 생성) 여러개 쓸 필요가 없음!
    //=> 그래서 공통으로 쓸수 있게 함

    //스프링 컨테이너에 등록해서 씀 (한개만 등록이 됨!)
    private final MemberService memberService;

    @Autowired
    public MemberController(MemberService memberService) {
        this.memberService = memberService;
    }
    //생성자를 만들어줌

}
```
- 컨터이너가 뜰때 생성자를 호출함, 생성자에 Autowired가 있으면 MemberService를 스프링이 스프링 컨테이너 MemberService를 가져다가 연결을 시켜줌   


<br>
<br>

<img width="648" alt="캡쳐" src="https://user-images.githubusercontent.com/93639793/186802800-266a5ce7-12d4-4b87-aacc-c820579c3443.png">

<br>
<br>

- 정형화된 패턴
    - controller 통해서 외부요청을 받고 
    - service에서 비지니스로직을 만들고
    - repository에서 데이터를 저장   
   

- 스프링이 뜰대 @controller,@service,@repository 쫙 가지고 올라옴

- MemberController가 생성될때 스프링 빈에 등록되어있는 MemberService(객체)를 가져다가 넣어줌! 이게 바로 di (의존관계를 주입),, 밖에서 스프링 넣어줌!!!대박...

- MemberService도 마찬가지로 @Autowired가 있으면 repository를 찾아서 넣어줌! 이야   


## :two:&nbsp;&nbsp;&nbsp; 스프링 Bean 등록하는 방법

- 컴포넌트 스캔과 자동 의존관계 설정
- 자바 코드로 직접 스프링 빈 등록하기 

- @controller,@service,@repository -> @Componenet 스캔방식 -> 스프링 빈으로 자동 등록 된다
  - @controller,@service,@repository 안에 들어가면 @Componenet 있음 -> 컨포넌트 스캔이라고 함
  - 스프링이 올라올때 @component스캔 있는걸 전부 객체를 생성해서 스프링 컨테이너에 등록을 해줌  
  - @Autowired가 연관관계를 연결해줌

- 직접 등록
```java
@Configuration
    public class SpringConfig {
         @Bean
        public MemberService memberService() {
            return new MemberService(memberRepository());
        }
        @Bean
        public MemberRepository memberRepository() {
          return new MemoryMemberRepository();
        }
}

```

- DI 주입 방식
  -  생성자 주입 (권장함)
```java
@Autowired
public MemberController(MemberService memberService) {
    this.memberService = memberService;
}

```
  - => 생성자를(MemberContoroller) 통해서 MemberService가 주입됨   
  - 
  -  필드 주입
```java
@Autowired private MemberService memberservice;

```
  - => 좋지 않음, 나중에 바꿀수 있는 방법이 없음

  - setter 주입
```java
private MemberService memberService;

@Autowired
public void MemberController(MemberService memberService) {
    this.memberService = memberService;
}

```
  - => 안좋음 public으로 열려있어서 아무거나 넣어버릴수 있음

- 처음 스프링이 조립될때 빈들이 올라가고 끝나야 좋다고 함
- 개발 호출하지 않아야할 메서드를 호출하지 않아야함
<br>

-실무에서는 주로 정형화된 컨트롤러, 서비스, 리포지토리 같은 코드는 컴포넌트 스캔을 사용한다. 그리고 정형화 되지 않거나, 상황에 따라 구현 클래스를 변경해야 하면 설정을 통해 스프링 빈으로 등록한다.


