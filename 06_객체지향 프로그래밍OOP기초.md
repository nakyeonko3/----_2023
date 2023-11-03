# 객체지향프로그래밍
---
- 부품에 해당하는 객체들을 만들고, 그 객체를 조립해서 소프트웨어를 만드는 개발방식이다.
- 부품에 해당하는 객체를 생성하기 위한 설계도가 필요하다.
- 완성품 객체를 모델링하고, 집합관계에 있는 부품객체와 사용관계에 있는 객체들을 하나씩 설계 후 조립하는 방식으로 프로그램을 개발한다.

## 객체지향프로그래밍 언어의 주요 장점
---
- 코드의 재사용성이 높다.
	+ 새로운 코드를 작성할 때 기존의 코드를 이용해서 쉽게 작성할 수 있다.(상속)
- 코드의 관리가 용이하다
	+ 코드간의 관계를 이용해서 적은 노력으로 쉽게 코드를 변경할 수 있다.(디자인패턴)
- 신뢰성이 높은 프로그래밍을 가능하게 한다.
	+ 접근제한자와 메소드를 이용해서 데이터를 보호하고 올바른 값을 유지하도록 한다.(캡슐화)
	+ 코드의 중복을 제거하여 코드의 불일치로 인한 오동작을 방지할 수 있다.(중복제거, 리팩토링)

## 객체지향프로그래밍의 주요 개념
---
- **캡슐화**(Encapsulation)
	+ 캡슐화는 객체의 내부 상태와 동작을 숨기고 외부에서 접근을 제한하는 것을 의미한다.
	+ 다른 객체는 객체의 내부구조를 알 수 없고, 공개된 속성과 기능만을 이용할 수 있다.
```java
class Person {
    private String name;
    private int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }
    public void setName(String name) {
        this.name = name;
    }

    public void setAge(int age) {
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public int getAge() {
        return age;
    }
}

public class Main {
    public static void main(String[] args) {
        Person person = new Person("nakyeonko", 24);
        person.setAge(223);
        person.setName("hnodla");
        // person.age = 23 ; // error: age has private access in Person
        System.out.println(person.getName());
        System.out.println(person.getAge());

        System.out.println("Hello world!");

    }
}
```


- **상속**(Inheritance)
	+ 상속은 기존 클래스의 필드와 메서드를 하위 클래스에서 재사용한다.
	+ 상위클래스를 재사용하기 때문에 하위클래스를 빠르게 개발할 수 있다.
```java
class Engine {
    public void start() {
        System.out.println("엔진 작동 시작!");
    }
}

class Car extends Engine { // Car 클래스는 Engine 클래스를 상속받고 있다.
    public void honk() {
        System.out.println("Car is honking");
    }
}
```

- **다형성**(Polymorphism)
	+ 같은 종류의 객체지만, 실행 결과가 다양한 객체를 이용할 수 있는 성질이다.
```java
interface Animal {
    void cry();
}

class Cat implements Animal {
    public void cry() {
        System.out.println("냐옹!");
    }
}

class Dog implements Animal {
    public void cry() {
        System.out.println("멍멍!");
    }
}

public class Main {
    public static void main(String[] args) {
        Cat c = new Cat();
        Dog d = new Dog();

        c.cry();
        d.cry();
    }
}
```


