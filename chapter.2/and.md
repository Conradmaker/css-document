# 애니메이션 & 다단

## animation

요소에 애니메이션을 설정/제어

| animation-name | @keyframes 규칙의 이름을 지정 | none |
| :--- | :--- | :--- |
| animation-duration | 애니메이션의 지속시간 설정 | 0s |
| animation-timing-function | 타이밍 함수 지정 | ease |
| animation-delay | 애니메이션의 대기 시간 설정 | 0s |
| animation-iteration | 애니메이션의 반복횟수 설정 | 1 |
| animation-direction | 애니메이션의 반복 방향 설정 | normal |
| animation-fill-mode | 애니메이션의 전후 상태 설정 | none |
| animation-play-state | 애니메이션의 재생과 정지 설정 | running |

```css
/* animation: 애니메이션이름 지속시간[ 타이밍함수 대기시간 반복횟수 전후상태 재생/정지]; */

.box{
  width: 100px;
  height: 100px;
  background: tomato;
}
.box:hover{
  animation: first-animation 1s infinite alternate;
}
@keyframes first-animation{
  0%{
    width: 100px;
  }
  100%{
    width: 500px;
  }
}
```

### @keyframes

2개 이상의 애니메이션 중간 상태\(프레임\)을 지정

```css
.box{
  width: 100px;
  height: 100px;
  background: tomato;
  border-radius: 10px;
}
.box:hover{
  animation: my-animation 3s infinite alternate;
}

@keyframes my-animation{
  0%{
    width: 100px;
  }
  75%{
    width: 500px;
    background: dodgerblue;
  }
  100%{
    width: 300px;
  }
}


/* 100  >   500  파란색   > 300토마토색으로 변화한다 */
```

### 

### animation-name

@keyframes 규칙의 이름을 지정

| none \(기본값\) | 애니메이션을 지정하지 않음 |
| :--- | :--- |
| @keyframes 이름 | 이름이 일치하는 @keyframes 규칙의 애니메이션을 적용 |

### ​

### animation-duration

애니메이션의 지속시간 설정

| 시간 | 지속 시간을 설정 | 0s |
| :--- | :--- | :--- |


​

### animation-timing-function

타이밍 함수 지정

| ease | 빠르게-느리게 |
| :--- | :--- |
| linear | 일정하게 |
| ease-in | 느리게-빠르게 |
| ease-out | 빠르게 느리게 |
| ease-in-out | 느리게-빠르게-느리게 |
| cubic-bezier\(n,n,n,n\) | 자신만의 값을 정의\(0~1\) |
| steps\(n\) | n번 분할된 애니메이션 |

​

### animation-delay

애니메이션의 대기 시간 설정

| 시간 | 대기 시간을 설정 | 0s |
| :--- | :--- | :--- |


음수가 허용된다. 음수가 있을경우 그 값만큼 애니메이션 주기 도중에 시작

```css
.box{
  width: 150px;
  height: 100px;
  margin: 10px;
  border-radius: 10px;
  color:white;
  font-size: 24px;
  display: flex;
  justify-content: center;
  align-item:center;
}

.box1{background: tomato;}
.box2{background: blue;}
.box3{background: yellowgreen;}

.box1:hover{
  animation: my-animation 2s infinite alternate 0s linear;
}
.box2:hover{
  animation: my-animation 1s infinite alternate 1s linear;
}
.box3:hover{
  animation: my-animation 3s infinite alternate -2s linear;
}


@keyframes my-animation{
  0%{
    width: 100px;
  }
  100%{
    width: 300px;
  }
}
```



### animation-iteration-count

애니메이션의 반복 횟수를 설정

| 숫자 | 반복횟수를 설정 | 1 |
| :--- | :--- | :--- |
| infinite | 무한반복 |  |

### 

### animation-direction

| normal | 정방향만 반복 |
| :--- | :--- |
| reverse | 역방향만 반복 |
| alternate | 정방향에서 역방향으로 반복\(왕복\) |
| alternate-reverse | 역방향에서 정방향으로 반복\(왕복\) |

```css
.box{
  width: 150px;
  height: 100px;
  margin: 10px;
  border-radius: 10px;
  background: cyan;
  animation: movemove 2s;
  animation-iteration-count: infinite; 
/*   반복횟수 */
  animation-direction: alternate-reverse;
/*   반복방향: 반대왕복 */
}

@keyframes movemove{
  0%{
    transfrom: translate(0, 0);
  }
  25%{
    transfrom: translate(100px, 0);
  }
  50%{
    transfrom: translate(100px, 100px);
  }
  75%{
    transfrom: translate(0, 100px);
  }
  100{
    transfrom: translate(0, 0);
  }
}
```



### animation-fill-mode

애니메이션의 전후 상태\(위치를 설정\)

| none\(기본\) | 기존위치에서 시작 &gt; 시작위치로 이동 &gt; 동작 &gt;기존위치에서 끝 |
| :--- | :--- |
| forwards | 기존위치에서 시작 &gt; 시작위치로 이동 &gt; 동작 &gt;애니 끝위치에서 끝 |
| backwards | 애니 시작위치로 이동 &gt; 동작 &gt;기존위치에서 끝 |
| both | 애니 시작위치로 이동 &gt; 동작 &gt;애니 끝위치에서 끝 |



### animation-play-state

애니메이션의 재생과 정지를 설정

| running | 애니메이션을 동작 |
| :--- | :--- |
| paused | 애니메이션 동작을 정지 |

{% embed url="https://codepen.io/xzyboldb/pen/KKpdyog?editors=1100" %}

이런 결과를 보여줄 수 있죠

### 

### multi-columns

일반 블록 레이아웃을 확장하여

여러 텍스트 다단으로 쉽게 정리하며 가독성 확보



## columns

다단을 정의

| auto\(기본\) | 브라우저가 단의 너비와 개수 설정 |
| :--- | :--- |
| column-width | 단의 최적 너비를 설정 |
| column-count | 단의 개수를 설정  |

```css
columns:너비개수;

.text{
   columns:100px 2;
}
```



### column-width/count 

단의 최적 너비/개수를 설정

| auto | 브라우저가 단의 너비를 설정 |
| :--- | :--- |
| 단위 | px,em,cm등 단위로 지정 |

### colunm-gap

단과 단 사이의 간격 설정

| normal | 브라우저가 단과 단 사이의 간격 설정 \(1em = 글자크기\) |
| :--- | :--- |
| 단위 | px,em,cm등 단위로 지정 |

### column-rule

단과 단 사이의 선을 지정

| column-width | 선의 두께 지정 | medium |
| :--- | :--- | :--- |
| column-style | 선의 종류를 지정 | none |
| column-color | 선의 색상을 지정 | 요소의 글자색과 동일 |

```css
column-rule: 두께 종류 색상;
```

{% embed url="https://codepen.io/xzyboldb/pen/rNVOYRp?editors=1100" %}

이렇게 단을 나눌 수 있다.

```css
p{
  columns: 200px 3;     /* 3개로 문단으로 나눈다 신문처럼   */
/*   column-width:200px;
  column-count: 3; */
  column-gap: 20px;
  column-rule: 2px solid red;
/*   column-rule: border과 사용법 동일 색 지정을 안하면 글자색과 동일하게 출력 */
}
```



