---
layout: page
author: LeeKiJong
title: Projects
date:   2019-12-16
permalink: /Projects/
main_nav: true
comments : true
---

<h2>Static</h2>
Static = 공유  
```java
public ㄴtatic int wallet = 200;  
```
지갑 공유 문제에서 사용
Static 있는 곳에는 주로 final을 사용함  
```java
public static final int i=1;
```
final = 상수, 변하지 않는 값
<h2>상속</h2>
```java
public class method1 extends 상속{
   public void method1(){
   // TODO....
   }
}
```

<h2>추상</h2>
Override 를 자동으로 생성해줌.
```java
public abstract class SuperClass{
  public SuperClass(){
  }
  public abstract void method1();
}
```

<h2>인터페이스</h2>  
<h4>정의</h4>
1. 객체의 소통 수단  
2. 작업 명세서  
3. JAVA에서 다형성을 가능하게 한다.  
4. 객체의 부속품화  

<h4>문법</h4>
1. 실제 기능은 없다. 구현된 기능은 없고 추상메소드와 상수만이 존재한다.  
2. private 안된다. 상수를 만들 때 Private 접근 제한자는 X  
3. 추상화 - 메소드는 무조건 추상 메소드만 존재한다.  
4. 객체타입 - 인터페이스는 개체는 아니다. 다만, 객체 타입으로만 사용된다.  
5. 구현은 실행 되는 객체의 메소드에서 한다.
```java
public interface InterfaceEx{
  public void inMethod();
}
```
```java
public class Ainterface implements InterfaceEx{
  public void inMethod(){
    System.out.println("AAAAA");
  }
}
```
```java
public class Binterface implements InterfaceEx{
  public void inMethod(){
    System.out.println("BBBBB");
  }
}
```

```java
public class Main {
  public static void main(){
    InterfaceEx Ainter = new Ainterface();
    InterfaceEx B inter = new Binterface();
    InterfaceEx[] inters = {Ainter, Binter};
    
    for(int i=0 ; i < inters.length ; i++){
      inters[i].inMethod();
    }
  }
}
```
배열로 만들어서 사용가능  
JAVA는 다중상속 X 대신에 다중구현(다형성) 가능  

<h2>인터페이스와 추상클래스</h2>  
<h4>공통점</h4>  
1. 추상메소드를 가지고있다. - 추상메소드를 가지고 있어 하위 클래스에서 구현해야 한다.  
2. 데이터 타입이 목적이다. - 객체생셩이 목적이 아니라 데이터 타입을 정의하는 것이 목적  
3. 객체 생성은 'anonymose'를 이용  
<h4>차이점</h4>  
1. 상속, 구현 - 추상메소드는 상속을 통한 사용이고, 인터페이스는 구현을 통한 사용이다.  
2. 구성요소 차이 - 추상클래스는 일반 클래스와 동일하게 변수, 메소드의 모든 기능을 사용할 수 있지만, 인터페이스는 상수와 추상메소드만이 존재한다.   
3. 단일상속, 다중구현 - 추상클래스는 단일 상속, 인터페이스는 다중구현 가능  

<h2>디자인 패턴</h2>  
1. 싱글턴 패턴  
```java
public class SingletonClass{
  private static SingletonClass SINGLETON_CLASS_INSTANCE = new singletonClass();
  public int i = 10;
  
  private SingletonClass(){
  }
  public static SingletonClass getSingletonClass(){
    if(SINGLETON_CLASS_INSTANCE == null){
      SINGLETON_CLASS_INSTANCE = new SingletonClass();
    }
    return SINGLETON_CLASS_INSTANCE;
  }
  public int geti(){
    return i;
  }
  public int seti(){
    this.i = i;
  }
}

```

