# 배열

* 배열의 홀\(hole\)

> PHP에서는 배열의 특정 인덱스에만 배열 요소 추가 가능
>
> ```php
> $arr = array();            // 배열의 생성
>
> $arr[10] = "banana";       // 인덱스 10에만 배열 요소를 추가함.
>
> var_dump($arr);
> var_dump($arr[0]);         // NULL
> var_dump(isset($arr[0]));  // false
> var_dump(isset($arr[10])); // true
> ```

홀을 가지는 배열에서는 for문을 사용하면 모든 배열 요소에 접근할 수 없다.  foreach를 이용할 것.

```php
$arr = array(); // 배열의 생성 

$arr[2] = "apple";
$arr[3] = "banana";
$arr[4] = "orange";
// $arr[0]과 $arr[1]은 배열의 홀(hole)이 됨

for ($i = 0; $i < count($arr); $i++) {
    echo "\\$arr[{$i}] : ".$arr[$i]."<br>";
} // error 발
foreach ($arr as $element){
    echo $element."<br>";
} // 정상 출
```

