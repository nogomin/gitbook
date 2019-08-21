# 깜빡임 효과

> 배경색이 3번 깜빡이고 종료되는 효과 \( 해당 영역 강조 역할 \)

```css
.blink {
    -webkit-animation: BLINK 1s infinite;  /* Safari 4+ */
    -moz-animation: BLINK 1s infinite;  /* Fx 5+ */
    -o-animation: BLINK 1s infinite;  /* Opera 12+ */
    animation: BLINK 1s infinite;  /* IE 10+, Fx 29+ */
}

@-webkit-keyframes BLINK {
    0%, 49% {
        background-color: white;
    }
    50%, 100% {
        background-color: yellow;
    }
}
@keyframes BLINK {
    0%, 49% {
        background-color: white;
    }
    50%, 100% {
        background-color: yellow;
    }
}

```

```javascript
// 3번 깜빡이고 종료
$(".text").addClass('blink');
    var i =0;
    var blink = setInterval(function() { 
        $(".text").addClass('blink');
        i++;
        if(i > 2) {
            $(".text").removeClass('blink');
            clearInterval(blink);
        }
    }, 1000);

```

