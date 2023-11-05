# JAVA

Status: In progress
Created: 2023년 11월 1일 오전 3:14
복습: Yes
유형: 강의

# JAVA

---

## 상속

### 상속 = 일반화 + 확장

상속이란 일반화와 확장이라는 개념을 합한 것이라고 생각하면 된다. 부모클래스를 상속받는다는것은 부모가 가지고 있는 것을 자식이 물려받아 사용할 수 있다는 것을 의미한다.

- 상속은 굉장히 강한 결합(객체-객체) ,
- 반드시 써야만 할 때만 쓰고 되도록 사용x
- 결합도는 낮추고, 응집도는 높이는 것이 좋음.

### 상속 선언 방법

```java
[접근제한자] [abstract | final ] class명 extends 부모 클래스명 {

}
```

### 아무것도 상속받지 않으면 자동으로 java.lang.Object를 상속받는다

- 모든 클래스는 Object의 자손이다.

### 부모 타입으로 자손 타입을 참조할 수 있다

- 버스는 자동차다

```java
Car car = new Bus();
```

“버스는 자동차다” → Bus 인스턴스 생성 

실제 참조는 Car 

### 메소드 오버로딩 (Overloading)

- 매개변수 타입이 다르거나 갯수가 다른 같은 이름의 메소드를 여러개 만드는것

### 다형성 - 메소드 오버라이딩 (Overriding)

- over + ride = 올라 타다?
- 상위 클래스의 메소드를 하위 클래스가 재정의 하는 것
- 메서드의 이름은 물론 파라메터의 갯수나 타입도 동일해야 하며, 주로 상위 클래스의 동작을 상속받은 하위 클래스에서 변경하기 위해 사용

### 메소드가 오버라이딩 되면 무조건 자식의 메소드가 실행된다

Q. Car 도 public void run() 메소드를 가지고 있고, Bus도 public void run()메소드를 가지고 있다면?

```java
Car car = new Bus();
car.run();
```

- Bus의 run() 메소드가 실행된다.

### 메소드 오버라이딩만 기억한다

- 정보 은닉은 객체지향의 중요한 기법이다. 중요한 필드는 은닉하고, 필드는 메소드를 통해서만 접근해서 사용하도록 한다.
- 메소드가 오버라이딩 되면 무조건 자식의것이 실행된다

### setter , getter 메소드

- private한 필드를 접근하기 위해 제공하는 메소드

```java
private int pirce;    //필드 price 

// 필드의 값을 수정하고 얻기 위한 메소드를 만든다. getter,setter
// setter,getter = 프로퍼티 - price프로퍼티
 public int getPrice() {
	return this.price;    // this는 내 자신 인스턴스를 참조하는 예약어
}

public int setPrice (int price) {  //지역변수 price
	this.price = price;
}
```

- getPrice() 메소드는 자신의 값을 리턴한다
- 메소드가 길어지면 메소드에서 선언된 지역 변수인지 필드인지 착각 할 수 있기 때문에 인스턴스 필드를 사용할 때는 this.price라고 적어 줄 수도 있다
- this는 내 자신 인스턴스를 말하는 키워드
- this는 static 메소드에서 사용할 수 없다
- price : 지역변수   |    this.price : 인스턴스 변수
- 매개변수로 받은 지역변수 price로 this.price를 초기화
- getter 메소드를 이용해 값을 가공해 반환 할 수 있다

### Object가 오버라이딩하라고 제공하는 메소드

- toString()
- equals() & hashCode()

```java
@override

public String toString() {
	return "ㅇㅇㅇㅇ다";
}
```

- equals 같은 값이냐? equals를 사용하려면 무조건 오버라이딩 해서 사용.

### 추상 클래스

- 추상 클래스는 인스턴스가 될 수 없다
- 추상 클래스를 상속받는 자손이 인스턴스가 된다
- abstract 키워드를 사용하여 클래스를 정의
- 추상 클래스는 보통 1개 이상의 추상 메소드를 가짐
- public abstract class 클래스명 { … }

```java
// 추상 클래스 정의
abstract class Animal {
    // 추상 메소드 선언
    public abstract void makeSound();

    // 일반 메소드
    public void sleep() {
        System.out.println("Zzz...");
    }
}

// 추상 클래스를 상속받는 구체 클래스 1
class Dog extends Animal {
    // 추상 메소드 구현
    @Override
    public void makeSound() {
        System.out.println("Woof! Woof!");
    }
}

public class Main {
    public static void main(String[] args) {
        // 추상 클래스를 이용한 다형성
        Animal myDog = new Dog();
        Animal myCat = new Cat();

        // 다형성을 통해 각각의 동물이 소리를 내도록 호출
        myDog.makeSound(); // 출력: Woof! Woof!
        myCat.makeSound(); // 출력: Meow!

        // 추상 클래스의 일반 메소드 호출
        myDog.sleep(); // 출력: Zzz...
        myCat.sleep(); // 출력: Zzz...
    }
}
```

이 예제에서 **`Animal`** 클래스는 추상 클래스로 선언되어 있고, **`makeSound`**라는 추상 메소드를 가지고 있다. 이를 구현한 **`Dog`**와 **`Cat`** 클래스는 각각 **`makeSound`** 메소드를 구현하고 있다. 추상 클래스를 이용하여 **`Dog`**와 **`Cat`** 객체를 생성하고 다형성을 통해 메소드를 호출할 수 있다.

### 클래스 메소드 vs 인스턴스 메소드

- 인스턴스 별로 다르게 동작해야 한다면 인스턴스 메소드
- static메소드는 객체 생성이나 유틸리티 관련해서 사용될 때가 있다
- 되도록 인스턴스 메소드를 사용

### 필드

- 클래스가 가지는 속성을 자바 언어에서 필드
- 다른 언어에서는 멤버변수
- 필드는 어떤 키워드와 함께 사용하느냐에 따라서 사용방법이 달라짐
- static이라는 키워드가 함께 사용되는 필드는 클래스 필드, 함께 사용되지 않는 필트는 인스턴스 필드

필드 선언 방법

[접근 제한자] [static] [final] 타입 필드명 [=초기값]; 

→ 대괄호는 생략 가능한 부분

→ 접근 제한자 public protected , 아무것도 없는 경우 (default) private이 올 수 있다

→ 필드명은 식별자 규칙을 따름, 다만 필드 첫번째 글자는 소문자로 시작하는것이 관례

→ 타입은 기본형과 참조타입이 나올 수 있

→ 초기값이 없는 경우에는 참조형일 경우 null , boolean형일 경우는 false로 나머지 기본형은 모두 0으로 초기화 된다

### final

abstract 가 붙으면 무조건 오버라이딩을 해야하는데 이와 반대되는 것

final이 붙은 메소드는 무조건 오버라이딩 금지

### 부모가 될 수 없는 클래스

- 상속 금지 시키려면 클래스를 정의할때 final 키워드 사용
- public final class 클래스명 {..}

→ 대표적으로 String 클래스는 final 

→ String 클래스는 불변객체

```java
String str1 = "hello";
String str2 = "hello";
String str3 = new String("hello");

```

str1=”hello”

str2=”hello”

str3 = new String(”hello”)

new가 쓰이면 다른 메모리 차지, new가 쓰이지 않으면 같은객체.

str은 new 안쓰이는게 좋음. 메모리차지 ㄴ

### 인터페이스

인터페이스 작성 문법

```java
[public] interface 인터페이스이름 {...}
// 인터페이스 메소드 구현이 없고 선언만 됨
```

- 인터페이스 이름은 Upper Camelcase로 작성 (첫번째가 대문자)
- 확장자 .java
- 인터페이스의 모든 필드는 public static final이어야 하며 모든 메소드는 public abstract 이어야 한다(자바7까지는) final , abstract를 생략하면 자동으로 붙는다
- 자바8 부터는 디폴트 메소드와 정적 메소드 선언도 ㄱㄴ

```java
// 인터페이스 정의
interface Soundable {
    // 추상 메소드 선언 (구현이 없음)
    void makeSound();
}

// 인터페이스를 구현하는 클래스 1
class Dog implements Soundable {
    // 인터페이스의 추상 메소드 구현
    @Override
    public void makeSound() {
        System.out.println("Woof! Woof!");
    }
}

// 인터페이스를 구현하는 클래스 2
class Cat implements Soundable {
    // 인터페이스의 추상 메소드 구현
    @Override
    public void makeSound() {
        System.out.println("Meow!");
    }
}

public class Main {
    public static void main(String[] args) {
        // 인터페이스를 이용한 다형성
        Soundable myDog = new Dog();
        Soundable myCat = new Cat();

        // 다형성을 통해 각각의 동물이 소리를 내도록 호출
        myDog.makeSound(); // 출력: Woof! Woof!
        myCat.makeSound(); // 출력: Meow!
    }
}
```

→ 인터페이스를 구현하게 되면 반드시 인터페이스가 가지고 있는 메소드를 오버라이딩할 필요가 있다

→ 예제 설명

이 예제에서 **`Soundable`**이라는 인터페이스는 **`makeSound`**라는 추상 메소드를 정의하고 있습니다. 그리고 **`Dog`**와 **`Cat`** 클래스는 각각 이 인터페이스를 구현하고 있습니다. 구현 클래스에서는 반드시 인터페이스의 모든 추상 메소드를 구현해야 합니다.

**`Soundable myDog = new Dog();`**와 같이 인터페이스를 이용하여 객체를 생성하고, 다형성을 통해 해당 객체의 메소드를 호출할 수 있습니다. 이를 통해 인터페이스가 다른 클래스에서 동일한 동작을 보장하도록 하고, 코드의 유연성을 높일 수 있습니다.

→ **implements**

**`implements`**는 Java에서 클래스가 특정 인터페이스를 구현한다는 것을 나타내는 키워드입니다. 클래스가 인터페이스를 구현할 때는 **`implements`** 키워드를 사용하며, 해당 클래스는 인터페이스에서 정의된 모든 추상 메소드를 구현해야 합니다.

→ 실행 결과 

Woof! Woof!
Meow!

### 인터페이스의 static method

- 인터페이스를 구현한 클래스가 없어도 사용가능한 static method

### 자바 메모리 관련하여 ,,

- new연산자 사용할 때마다 메모리에 인스턴스가 생성된다
- 인스턴스는 더 이상 참조되는 것이 없을때, 나중에 가비지 컬렉션 된다
- static한 필드는 클래스가 로딩될 때 딱 한번 메모리에 올라가고 초기화 된다
- 인스턴스 메소드(static이 안붙은 메소드)는 인스턴스를 생성하고나서 래퍼런스 변수를 이용해 사용할 수 있다
- 클래스 메소드는 클래스명.메소드명()으로 사용 가능하다
- 메소드 안에 선언된 변수들은 메소드가 실행될 때 메모리에 생성되었다가, 메소드가 종료될때 사라진다.

### 다형성 (Polymorphism)

다양한 자료형에 속하는 것이 허가되는 성질을 가르킴

단형성, → 프로그램 언어가 각 요소가 한가지 형태만 가지는 성질을 가르킴

### System.out.println(…)

- println은 인자를 출력하고 줄바꿈을 한다라는 의미
- 여기서 인자는 int,float,String,double 등이 될 수 있다
- 중요한 건 메소드 이름이 같다는것

### 다형성 - 메소드 오버로딩

- 메서드의 이름은 같고 매개변수의 갯수나 타입이 다른 함수를 정의
- 리턴값만을 다르게 갖는 오버로딩은 작성 ㄴㄴ

### static 메소드

static 메소드는 인스턴스를 만들지 않아도 사용할 수 있다

### 추상화

- 중요한 것은 남기고 불필요한 것은 제거

### 캡슐화

- 관련된 것을 잘 모아서 가지고 있는것, 관련된 것을 잘 모아서 가지고 있을수록 응집도가 높다고 표현

### 이름없는 클래스(Anonymous Class)

- new 생성자 () { …}
- 생성자 뒤에 중괄호가 나오고 코드를 오버라이딩 하여 보통 구현함

예시 코드

```java
Car car = new Car() {
	public void run() {
			System.out.println("Car를 상속받는 이름없는 객체가 run메소드를 오버라이딩함");
	}
}
```

### 정적 중첩 클래스

- 자바에서 중첩 클래스(Nested Class)는 다른 클래스 내에 정의된 클래스를 의미합니다.
- 중첩 클래스는 주로 외부 클래스의 멤버로 사용되며, 코드의 구조를 단순화하고 캡슐화를 촉진하는 데 도움이 됩니다.
- 중첩 클래스에는 정적 중첩 클래스(static nested class), 비정적 중첩 클래스(inner class), 지역 클래스(local class), 익명 클래스(anonymous class)가 있습니다

```java
public class OuterClass {
    static class StaticNestedClass {
        void display() {
            System.out.println("This is a static nested class.");
        }
    }
}

public class Main {
    public static void main(String[] args) {
        OuterClass.StaticNestedClass nestedObject = new OuterClass.StaticNestedClass();
        nestedObject.display();
    }
}
```

### 인스턴스 멤버 클래스

- 인스턴스 멤버 클래스(Instance Member Class)는 다른 클래스 내에 정의되어 있으며 해당 클래스의 인스턴스와 관련된 기능을 제공합니다
- 인스턴스 멤버 클래스는 주로 외부 클래스의 인스턴스와 연관된 작업을 수행하며, 외부 클래스의 인스턴스 멤버(필드, 메소드)에 접근할 수 있습니다.

```java
public class OuterClass {
    private int outerField = 10;

    // 인스턴스 멤버 클래스
    public class InnerClass {
        private int innerField = 5;

        public void display() {
            System.out.println("Outer Field: " + outerField);
            System.out.println("Inner Field: " + innerField);
        }
    }

    public static void main(String[] args) {
        OuterClass outerObject = new OuterClass();
        
        // 외부 클래스의 인스턴스를 통해 인스턴스 멤버 클래스의 인스턴스 생성
        OuterClass.InnerClass innerObject = outerObject.new InnerClass();

        // 인스턴스 멤버 클래스의 메소드 호출
        innerObject.display();
    }
}
```

위의 코드에서 **`InnerClass`**는 **`OuterClass`**의 인스턴스 멤버 클래스로 정의되어 있습니다. **`InnerClass`**는 **`outerField`**에 접근할 수 있습니다.

인스턴스 멤버 클래스의 인스턴스를 생성할 때에는 외부 클래스의 인스턴스를 통해 생성합니다. 위의 예제에서는 **`OuterClass`**의 객체를 생성하고, 그 객체를 사용하여 **`InnerClass`**의 객체를 생성하고 있습니다.

주의할 점은, 인스턴스 멤버 클래스는 외부 클래스의 인스턴스를 통해서만 생성이 가능하며, 정적(static) 멤버를 가질 수 없습니다. 따라서 인스턴스 멤버 클래스 내에서는 인스턴스 변수, 메소드 등에 접근할 수 있지만, 정적 변수나 정적 메소드에 직접적으로 접근할 수는 없습니다.

### 정적 멤버 클래스

- 정적 멤버 클래스(Static Member Class)는 특정 클래스 내에서 **`static`** 키워드를 사용하여 정의된 클래스입니다.
- 정적 멤버 클래스는 외부 클래스의 인스턴스에 종속되지 않으며, 외부 클래스의 정적 멤버(정적 필드, 정적 메소드)에 대한 접근이 가능합니다.
- 정적 멤버 클래스는 주로 외부 클래스와 관련이 있지만 인스턴스를 생성하지 않아도 되는 경우에 사용됩니다.

```java
public class OuterClass {
    private static int outerStaticField = 10;

    // 정적 멤버 클래스
    public static class StaticInnerClass {
        private int innerField = 5;

        public void display() {
            // 정적 멤버 클래스에서 외부 클래스의 정적 필드에 접근
            System.out.println("Outer Static Field: " + outerStaticField);
            System.out.println("Inner Field: " + innerField);
        }
    }

    public static void main(String[] args) {
        // 외부 클래스의 정적 멤버 클래스의 인스턴스 생성
        OuterClass.StaticInnerClass innerObject = new OuterClass.StaticInnerClass();

        // 정적 멤버 클래스의 메소드 호출
        innerObject.display();
    }
}
```

위의 코드에서 **`StaticInnerClass`**는 **`OuterClass`**의 정적 멤버 클래스로 정의되어 있습니다. 정적 멤버 클래스는 외부 클래스의 인스턴스를 생성하지 않고도 사용할 수 있습니다.

정적 멤버 클래스의 인스턴스를 생성할 때에는 외부 클래스의 이름을 통해 생성합니다. 위의 예제에서는 **`OuterClass.StaticInnerClass`**의 형태로 생성하고 있습니다.

정적 멤버 클래스는 외부 클래스와 강하게 결합되어 있으면서도, 외부 클래스의 인스턴스에 의존하지 않기 때문에, 외부 클래스의 인스턴스를 생성하지 않고도 사용할 수 있는 편리함이 있습니다.

### 로컬 클래스

- 로컬 클래스(Local Class)는 특정 메소드나 블록 내에서 정의되는 클래스
- 해당 블록 내에서만 유효한 클래스
- 로컬 클래스는 주로 특정 메소드에서만 사용되는 간단한 기능을 가진 클래스를 정의할 때 활용
- 로컬 클래스는 메소드 내에 선언되므로 해당 메소드의 로컬 변수와 파라미터에 접근할 수 있습니다.

```java
public class OuterClass {
    private int outerField = 10;

    public void outerMethod() {
        int localVar = 5;

        // 로컬 클래스
        class LocalInnerClass {
            private int innerField = 3;

            public void display() {
                // 로컬 클래스에서 외부 메소드의 로컬 변수와 외부 클래스의 멤버에 접근
                System.out.println("Local Variable: " + localVar);
                System.out.println("Outer Field: " + outerField);
                System.out.println("Inner Field: " + innerField);
            }
        }

        // 로컬 클래스의 인스턴스 생성
        LocalInnerClass localObject = new LocalInnerClass();

        // 로컬 클래스의 메소드 호출
        localObject.display();
    }

    public static void main(String[] args) {
        // 외부 클래스의 인스턴스 생성
        OuterClass outerObject = new OuterClass();

        // 외부 클래스의 메소드 호출
        outerObject.outerMethod();
    }
}
```

위의 코드에서 **`LocalInnerClass`**는 **`outerMethod`** 메소드 내에 정의된 로컬 클래스입니다. 로컬 클래스는 해당 메소드 내에서만 유효하며, 메소드 내에서 선언된 로컬 변수 **`localVar`**와 외부 클래스의 멤버 변수 **`outerField`**에 접근할 수 있습니다.

로컬 클래스는 주로 해당 메소드에서만 사용되어야 하는 간단한 기능을 구현할 때 활용되며, 클래스가 해당 메소드 외부에서 필요하지 않을 때 유용합니다.

### 중첩 인터페이스

- 중첩 인터페이스(Nested Interface)는 하나의 인터페이스가 다른 인터페이스 내에 정의되어 있는 경우를 말함
- 중첩 인터페이스는 주로 특정 클래스나 인터페이스와 강하게 연관된 작업을 정의하는 데 사용됨
- 이를 통해 코드의 구조를 더욱 체계적으로 만들고 관련된 작업들을 그룹화할 수 있습니다.

```java
interface OuterInterface {
    // 다른 멤버들...

    interface NestedInterface {
        // 중첩 인터페이스 멤버들...
    }
}
```

**`NestedInterface`**가 **`OuterInterface`** 내에 중첩되어 있는 것을 볼 수 있습니다. 중첩 인터페이스는 해당 인터페이스를 구현하는 클래스나 다른 인터페이스에서 구현될 수 있습니다.

```java
interface Vehicle {
    void start();

    void stop();

    // 중첩 인터페이스
    interface Engine {
        void run();

        void stop();
    }
}

class Car implements Vehicle, Vehicle.Engine {
    @Override
    public void start() {
        System.out.println("Car starting...");
    }

    @Override
    public void stop() {
        System.out.println("Car stopping...");
    }

    @Override
    public void run() {
        System.out.println("Car engine running...");
    }
}

public class Main {
    public static void main(String[] args) {
        Car car = new Car();
        car.start();
        car.run();
        car.stop();
    }
}
```

이 예제에서는 **`Vehicle`** 인터페이스 내에 **`Engine`**이라는 중첩 인터페이스가 정의되어 있습니다. 그리고 **`Car`** 클래스에서는 **`Vehicle`**와 **`Vehicle.Engine`** 인터페이스를 구현하고 있습니다.

중첩 인터페이스를 사용하면 코드의 가독성을 높일 수 있고, 관련된 작업을 논리적으로 그룹화하여 정의할 수 있습니다.

### Error의 종류

- 컴피일 에러 : 컴파일시 발생하는 에러 → 대표적인것 : 문법 구문 오류
- 런타임 에러 : 실행시 발생하는 에러
- 논리적 에러 : 실행은 되지만 의도와 다르게 동작 → 버그

### 자바에서는 실행시 2가지 형태의 오류가 발생할 수 있다

- Error : 수습할 수 없는 심각한 오류
- Exception (예외) : 예외 처리를 통해 수습할 수 있는 덜 심각한 오류
- 메모리 부족, 스택오버플로우(stack overflow)등이 발생하여 프로그램이 죽는것은 프로그래머가 제어 불가

### 오류(error)와 예외(exception)

자바 프로그래밍에서는 실행시 발생할 수 있는 오류를 에러와 예외 두가지로 구분

- 에러 : 프로그램 코드에 의해서 수습될 수 없는 심각한 오류
- 예외 : 프로그램 코드에 의해서 수습될 수 있는 다소 미약한 오류
- 예외
    - 대부분 예외는 개발자가 구현한 로직에서 발생한 실수나 사용자의 영향에 의해 발생 , 예외는 에러와 달리 문제가 발생되더라도 이에 대한 대응 코드를 미리 작성해 놓음으로써 어느정도 프로그램의 비정상적인 종료나 동작을 막을 수 있음!

### 예외 처리(exception handing)

```
**[ 예외 처리(exception handling) ]**
예외 처리란 프로그램 실행 시 발생할 수 있는 예기치 못한 예외의 발생에 대비한 코드를 작성하는 행위를 말한다.
프로그램 실행도중에 발생하는 에러는 어쩔 수 없지만, 예외는 프로그래머의 실력에 따라 충분히 포괄적으로 방지할 수 있기 때문이다. 따라서 예외 처리의 목적은 예외의 발생으로 인한 실행중인 프로그램의 갑작스런 비정상 종료를 막고, 정상적인 실행상태를 유지하는 것이다.
```

### try-catch를 이용해 예외 처리

```java
try { //일반 코드는 try 블록
    // 예외가 발생할 수 있는 코드 블록
    // 예외가 발생하면 해당 예외를 처리하는 코드
} catch (ExceptionType1 e1) { //예외처리는 catch 블록
    // ExceptionType1 예외를 처리하는 코드
} catch (ExceptionType2 e2) {
    // ExceptionType2 예외를 처리하는 코드
} finally {
    // 항상 실행되어야 하는 코드 (예외 발생 여부와 상관없이)
}
```

예외가 발생한 경우에는 try → catch → finally의 순서로 실행

예외가 발생x 경우 try→finally 순서로 실행

나누기 연산을 수행하는 프로그램에서의 **`ArithmeticException`**을 처리하는 **`try-catch`** 구문

```java
public class Example {
    public static void main(String[] args) {
        int numerator = 10;
        int denominator = 0;

        try {
            // 나누기 연산을 시도
            int result = numerator / denominator;
            System.out.println("결과: " + result);
        } catch (ArithmeticException e) {
            // ArithmeticException이 발생하면 여기서 처리
            System.err.println("0으로 나눌 수 없습니다. 예외 메시지: " + e.getMessage());
        } finally {
            // 항상 실행되는 블록
            System.out.println("프로그램이 종료되었습니다.");
        }
    }
}
```

위의 예시에서 **`denominator`**가 0이므로 나누기 연산이 불가능하며 **`ArithmeticException`**이 발생합니다. **`try`** 블록 내에서 이 예외를 catch하여 적절한 메시지를 출력하고, **`finally`** 블록은 예외 발생 여부와 관계없이 항상 실행

### 예외 떠넘기기 - throws

```java
리턴타입 메소드명 ( 아규먼트 리스트 ) throws Exception 클래스명1 , Exception클래스명2..{
		코드1
		코드2
		코드3
		.......
}
```

### Runtime Exception , Checked Exception

Runtime Exception : 실행시 오류가나서 죽게되는 리셉션

Checked Exception : 컴파일러가 강제하는 예외. 이는 코드 작성 시에 반드시 예외 처리 코드를 작성하거나 예외를 던져야 함을 의미함

### 사용자 정의 Exception과 예외 발생 시키기(throw)

상속 받으면 됨 

오류 메시지나 발생한 Exception을 감싼 결과로 내가 만든 Exception을 사용하고 싶을 때가 많다.

catch를 일일히 적기 귀찮으니 my exception 클래스를 만들어 예외처리 

예제코드

```java
// 사용자 정의 예외 클래스 정의
class CustomException extends Exception {
    public CustomException(String message) {
        super(message);
    }
}

public class Example {
    // 사용자 정의 예외를 발생시키는 메서드
    public static void customMethod(int value) throws CustomException {
        if (value < 0) {
            throw new CustomException("값이 음수일 수 없습니다.");
        }
        System.out.println("입력된 값: " + value);
    }

    public static void main(String[] args) {
        try {
            // 사용자 정의 예외를 발생시키는 메서드 호출
            customMethod(-5);
        } catch (CustomException e) {
            // CustomException을 catch하여 처리
            System.err.println("사용자 정의 예외 발생: " + e.getMessage());
        }
    }
}
```

이 예제에서 **`CustomException`**은 **`Exception`** 클래스를 상속받아 만들어진 사용자 정의 예외 클래스 **`CustomException`**은 생성자를 통해 예외 메시지를 받아들일 수 있도록 되어 있음

그리고 **`Example`** 클래스의 **`customMethod`** 메서드에서는 입력된 값이 음수인 경우 **`CustomException`**을 발생시키고, **`main`** 메서드에서는 이 예외를 catch하여 적절한 메시지를 출력하고 있음