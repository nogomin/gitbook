---
description: '지역변수, 전역변수, 슈퍼글로벌, 정적변수'
---

# 변수\(variable\)

* 지역변수 \(local variable\)

```php
function varFunc() {
    $var = 10; // 지역 변수로 선언함
    echo "함수 내부에서 호출한 지역 변수 var의 값은 {$var}입니다.<br>";
}
varFunc();
echo "함수 밖에서 호출한 지역 변수 var의 값은 {$var}입니다.";

//output
//함수 내에서 호출한 지역 변수 var의 값은 10입니다.
//함수 밖에서 호출한 지역 변수 var의 값은 입니다.
```

* 전역변수 \(global variable\)

```php
$var = 10;       // 전역 변수로 선언함
function varFunc() {
    echo "함수 내부에서 호출한 전역 변수 var의 값은 {$var}입니다.<br>";
    global $var; // 함수 내에서 사용할 전역 변수를 명시함
    echo "함수 내부에서 호출한 전역 변수 var의 값은 {$var}입니다.<br>";
}
varFunc();
echo "함수 밖에서 호출한 전역 변수 var의 값은 {$var}입니다.";

//output
/*
함수 내에서 호출한 전역 변수 var의 값은 입니다.
함수 내에서 호출한 전역 변수 var의 값은 10입니다.
함수 밖에서 호출한 전역 변수 var의 값은 10입니다.
*/
```

> php는 모든 전역 변수를 $GLOBALS 배열에 저장한다. 이 배열에 인덱스로 변수의 이름을 사용하면, 해당 전역 변수의 값에 접근 가능.

> ```php
> $var = 10; // 전역 변수로 선언함
> function varFunc() {
>     echo "함수 내부에서 호출한 전역 변수 var의 값은 {$var}입니다.<br>";
>     echo "함수 내부에서 호출한 전역 변수 var의 값은 {$GLOBALS['var']}입니다.<br>";
> }
> varFunc();
> echo "함수 밖에서 호출한 전역 변수 var의 값은 {$var}입니다.";
> //output
> /*
> 함수 내에서 호출한 전역 변수 var의 값은 입니다.
> 함수 내에서 호출한 전역 변수 var의 값은 10입니다.
> 함수 밖에서 호출한 전역 변수 var의 값은 10입니다.
> */
> ```

* 슈퍼 글로벌\(superglobal\)

> 특별한 선언 없이 스크립트 내의 어디에서라도 바로 사용가능

1. $GLOBALS
2. $\_SERVER
3. $\_GET
4. $\_POST
5. $\_FILES
6. $\_COOKIE
7. $\_SESSION
8. $\_REQUEST
9. $\_ENV

* 정적 변수 \(static variable\)

> 함수 내부에서 선언된 정적 변수는 함수의 호출이 종료되도 메모리상에서 사라지지 않음. 하지만 지역변수처럼 해당 함수 내부에서만 접근 가능.

> ```php
> function counter() {
>     static $count = 0;
>     echo "함수 내부에서 호출한 static 변수 count의 값은 {$count}입니다.<br>";
>     $count++;
> }
> counter();
> counter();
> counter();
> //output
> /*
> 함수 내에서 선언한 정적 변수 count의 값은 0입니다.
> 함수 내에서 선언한 정적 변수 count의 값은 1입니다.
> 함수 내에서 선언한 정적 변수 count의 값은 2입니다.
> */
> ```

