# 알짜 정보

#### HTML이나 CSS 브라우저 지원 버전 조사

{% embed url="https://www.caniuse.com" %}

---

#### 폰트 크기 상대적 조절

```text
html {
    font-size: 14px;
}
h1 {
    font-size: 1.4rem;
}
h2 {
    font-size: 1.14rem;
}
```

반응형 디자인에서 pc용과 스마트폰용 폰트 크기 변경시 위력 발

---

#### line-height: 1.7 

단위없이 숫자로 조절. 행간이 폰트 크기의 1.7배라는 의미! 주요 브라우저의 초깃값은 1.5

---

#### font-weight

bold와 normal이 일반적이나 숫자로 지정할수도 있음. 100, 200, 300 ... 900 \(9종류\). 400이 일반 굵기. 구글 폰트 등 웹폰트를 사용할 때는 값에 숫자를 지정하는 경우도 있다.

---

#### font 설정

```text
body {
    font-family: "돋움", dotum, "굴림", gulim, arial, helvetica sans-serif;
}    
```

여러개가 지정돼 있으면 첫번째부터 순서대로 존재여부 확인. 고딕체로 표시하는 경우 마지막에 반드시 'sans-serif' 넣기 

---

#### text-indent 활용

```text
.note {
    padding-left: 1em;
    text-indent: -1em;
}

<p class="note">* 주의사항입니다. 반드시 지켜주세요</p>
```

---

#### 이미지 크기 동적 변경

```text
<style>
.img-responsive {
    display: block;
    max-width: 100%;
    height: auto;
}
.thumbnail {
    width: 200px;
}
</style>

<div class="thumbnail">
    <img src="../images/image.jpg" width="900" height="580" alt="" class="img-responsive">
</div>
```



