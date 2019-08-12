---
description: regular expression
---

# 정규 표현식

* PHP 에서는 다음과 같은 두 가지의 정규 표현식을 지원한다.
* * POSIX
  * PCRE\(Perl-Compatible Regular Expression\)

> POSIX는 배우기 쉽고 실행 속도가 빠른편. PCRE는 POSIX의 확장편. 더 강력하고 유연하게 동작

* 정규표현식 리터럴

> /검색패턴/플래그

* preg\_match\(\)

> preg\_match\($pattern, $subject, \[,$matches\]\);
>
> 일치 값 발견시 1 리턴, 찾지못하면 0 리턴

```php
$subject = "간장 공장 공장장은 강 공장장이고, 된장 공장 공장장은 장 공장장이다.";

 

if (preg_match('/공장/', $subject)) {

    echo "해당 문자열에서 '공장'을 발견했습니다.<br>";

} else {

    echo "해당 문자열에서 '공장'을 발견하지 못했습니다.<br>";

}

 

if (preg_match('/장공/', $subject)) {

    echo "해당 문자열에서 '장공'을 발견했습니다.<br>";

} else {

    echo "해당 문자열에서 '장공'을 발견하지 못했습니다.<br>";

}

//output
/*
해당 문자열에서 '공장'을 발견했습니다.
해당 문자열에서 '장공'을 발견하지 못했습니다.
*/


```

* 플래그

| 플래그 | 설명 |
| :--- | :--- |
| i | 검색 패턴을 비교할 때 대소문자를 구분하지 않음 |
| g | 검색 패턴을 비교할 때 일치하는 모든 부분을 선택하도록 설정 |
| m | 검색 패턴을 비교할 때 여러 줄의 입력 문자열을 그 상태 그대로 여러줄로 비교하도록 설정 |
| y | 대상 문자열의 현재 위치부터 비교를 시작하도록 설정 |
| u | 대상 문자열이 UTF-8로 인코딩된 것으로 설정 |

```php
$subject = "bcabcAB";

// 기본 설정으로 검색 패턴을 비교할 때 대소문자를 구분함.
preg_match_all('/AB/', $subject, $matches_01);      // "AB"

// 검색 패턴을 비교할 때 대소문자를 구분하지 않도록 설정함.
preg_match_all('/AB/i', $subject, $matches_02); // "ab", "AB"


```

