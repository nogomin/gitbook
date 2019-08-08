---
description: 'do/while, foreach'
---

# 반복문

* do / while 

> 먼저 루프를 한번 실행한 후에 표현식 검사. 즉, 표현식의 결과와 상관없이 무조건 한번은 루프 실행
>
> ```php
> $i = 0;
> $j = 0;
> while ($i > 3) {
>     echo "변수 i의 값은 ".(++$i)."입니다.<br>";
> }
> do { // do / while문은 조건식과 상관없이 반드시 한 번은 루프를 실행함
>     echo "변수 j의 값은 ".(++$j)."입니다.<br>";
> } while ($j > 3);
>
> //output
> //변수 j의 값은 1입니다.
> ```

* foreach

> 배열의 모든 요소를 손쉽게 순회할 수 있도록 해준다. 루프마다 배열의 각 요소를 지정된 변수에 대입함. 이렇게 대입받은 변수를 이용하면 루프 안에서 배열의 각 요소에 순차적으로 접근 가능

> ```php
> $arr = array(2, 4, 6, 8);
> foreach ($arr as $value) { //배열 as 값을 저장할 변수
>     echo "변수 \$value의 현재값은 {$value}입니다.<br>";
> }
> unset($value); //$value는 foreach문 내에서만 사용되는 변수임으로 해제해주는것이 좋다
>
> //output
> //변수 value의 현재값은 2입니다.
> //변수 value의 현재값은 4입니다.
> //변수 value의 현재값은 6입니다.
> //변수 value의 현재값은 8입니다.
> ```

> 배열의 값뿐만 아니라 키값도 저장하여 활용 가능
>
> ```php
> $arr = array(
>     "둘" => 2,
>     "넷" => 4,
>     "여섯" => 6,
>     "여덟" => 8,
> );
> foreach ($arr as $key => $value) {
>     echo "배열 \$arr에서 키값 '{$key}'에 대한 값은 {$value}입니다.<br>";
> }
> unset($value);
> ```

