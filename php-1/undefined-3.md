---
description: '인스턴스, 접근제어, 정보 은닉'
---

# 클래스

* 인스턴스 생성

> $객체이름 = new 클래스이름\(인수1, 인수2, ...\);

* 클래스 멤버에 접근

> $객체이름-&gt;프로퍼티이름;
>
> $객체이름-&gt;메소드이름;

* 접근 제어\(access modifier\)

> public : 외부로 공개, 해당 객체를 사용하는 어디에서나 직접 접근 가능
>
> private : 외부로 공개 x, 해당 클래스의 멤버만 접근 가능
>
> protected : 상위 클래스에 대해서는 public 멤버처럼 취급, 외부에서는 private 멤버처럼 취급. 즉 해당 클래스의 멤버와 해당 클래스를 상속받은 자식 클래스에서만 접근 가능

```php
class ClassName {
    public $publicVar;
    private $privateVar;
    protected $protectedVar;

    public function __constructor() {
        $this->publicVar = "public property<br>";

        $this->privateVar = "private property<br>";

        $this->protectedVar = "protected property<br>";
    }

    public function publicMethod() {
        echo "public method<br>";
    }
    protected function protectedMethod() {
        echo "protected method<br>";
    }
    private function privateMethod() {
        echo "private method<br>";
    }
}

$object = new ClassName();

echo $object->publicVar;      // 접근 가능
//echo $object->protectedVar; // 접근 불가능
//echo $object->privatev;     // 접근 불가능

$object->publicMethod();      // 호출 가능
//$object->protectedMethod(); // 호출 불가능
//$object->privateMethod();   // 호출 불가능
```

* 정보 은닉 \(data hiding\)

> 클래스 외부에서는 private이나 protected멤버로는 직접 접근이 불가하나, public 메소드를 사용하면 해당 클래스의 private 멤버나 protected 멤버에도 접근 가능.
>
> public 메소드는 private 멤버나 protected 멤버와 프로그램 사이의 인터페이스 역할을 수행한다. 이렇게 외부에서 바로 데이터로 접근하지 못하게 하는것을 정보 은닉이라고 한다.

```php
class ClassName{
    private $privateVar;

    public function __constructor() {
        $this->privateVar = "private property";
    }

    public function getValue() {
        return $this->privateVar;
    }

    public function setValue($value) {
        $this->privateVar = $value;
    }
}
$object = new ClassName();
$object->setValue("hello"); // setValue() 함수를 통해 $private의 값을 변경할 수 있음.
echo $object->getValue;     // getValue() 함수를 통해 $private의 값을 출력할 수 있음.
```

