# 박스모델

박스모델은 양이 좀 많긴 하지만 꼭 알아야 하는 부분입니다!

### 1.width

| 값 | 의미 | 기본값 |
| :--- | :--- | :--- |
| auto | 브라우저가 너비를 계산 | auto |
| 단위 | px,em,cm등 단위로 지정 |  |

### 

### 2.height

| 값 | 의미 | 기본값 |
| :--- | :--- | :--- |
| auto | 브라우저가 너비를 계산 | auto |
| 단위 | px,em,cm등 단위로 지정 |  |

\*블록요소는 가로,세로사이즈를 지정할수 있지만 인라인 요소는 지정할 수 없다.

-블록요소는 width:100% / height:0 에서 시작한다.

-인라인요소는 0/0 에서 시작한다.



### 3.max-width/height

 요소의 최대 가로/세로너비를 지정

| 값 | 의미 | 기본값 |
| :--- | :--- | :--- |
| 단위 | px.em.%등 단위로 지정 | 0 |
| auto | 브라우저가 너비를 계산 |  |

​

### 4.min-width/height

 요소의 최소 가로/세로너비를 지정

| 값 | 의미 | 기본값 |
| :--- | :--- | :--- |
| 단위 | px.em.%등 단위로 지정 | 0 |
| auto | 브라우저가 너비를 계산 |  |

![-&#xCD5C;&#xC18C; &#xB108;&#xBE44;&#xAC00; 200px&#xC774;&#xAE30;&#xB54C;&#xBB38;&#xC5D0;  &#x200B;](../.gitbook/assets/image%20%2860%29.png)



### **5.margin**

요소의 '외부\(바깥\)여백'을 지정 \*단축속성\*

 - 음수의 값을 사용할 수 있다 -

| 값 | 의미 | 기본값 |
| :---: | :---: | :---: |
| 단위 | px,em,cm등 단위로 지정 | 0 |
| auto | 브라우저가 너비를 계산 |  |
| % | 부모 요소의 너비에 대한 비율로 지정 |  |

![%&#xB294; &#xBD80;&#xBAA8;&#xC694;&#xC18C; &#xB108;&#xBE44;&#xC5D0; &#xC601;&#xD5A5;&#xC744; &#xBC1B;&#xB294;&#xB2E4;](../.gitbook/assets/image%20%2834%29.png)

사용법은 다음과 같다.

```css
.box {
  margin: 10px 20px 30px 40px; /* 위 우 아래 좌 */
  margin: 10px 20px 40px;      /* 위 (좌,우) 아래 */
  margin: 10px 40px;           /* (위,아래),(좌,우) */
  margin: 10px;                /* (위,아래,좌,우) */
}
```

개별 속성으로 사용하고 싶다면

margin 뒤에 -top/right/left/bottom을 붙이자

### 

### 마진 중복\(병합,Collapse\)

마진의 특정한 값들이 '중복'되어 합쳐지는 현상

1.형제 요소들의 margin-top과 margin-bottom이 만났을때

2.부모요소의 margin-top과 자식요소의 margin-top이 만났을때

3.부모요소의 margin-bottom과 자식요소의 margin-bottom이 만났을때

\*중복은 버그가 아니라 현상을 우회하거나 응용할 수 있다\*

​

![&#xBD80;&#xBAA8;&#xC694;&#xC18C;&#xC5D0;&#xB294; margin-top&#xC774; &#xC5C6;&#xC9C0;&#xB9CC; \(&#xB450; &#xC694;&#xC18C;&#xAC00; &#xACB9;&#xCE58;&#xBA74;\) &#xC790;&#xC2DD;&#xC694;&#xC18C;&#xB97C; &#xB530;&#xB77C;&#xAC14;&#xB2E4;.](../.gitbook/assets/image%20%2819%29.png)



#### 마진 중복 계산법

| 조건 | 요소A 마진 | 요소B 마진 | 계산법 | 중복값 |
| :--- | :--- | :--- | :--- | :--- |
| 둘다 양수 | 30px | 10px | 더 큰값으로 중복 | 30px |
| 둘다 음수 | -30px | -10px | 더 작은값으로 중복 | -30px |
| 각각 양수와 음수 | -30px | 10px | -30+10=-20 | -20px |



### **6.padding**

요소의 내부\(안\)여백을 지정

| 값 | 의미 | 기본값 |
| :--- | :--- | :--- |
| 단위 | px,em,cm등 단위로 지정 | 0 |
| auto | 브라우저가 너비를 계산 |  |
| % | 부모 요소의 너비에 대한 비율로 지정 |  |

```css
.box {
  padding: 10px 20px 30px 40px; /* 위 우 아래 좌 */
  padding: 10px 20px 40px;      /* 위 (좌,우) 아래 */
  padding: 10px 40px;           /* (위,아래),(좌,우) */
  padding: 10px;                /* (위,아래,좌,우) */
}
```

margin처럼 개별속성으로도 사용할 수 있다.

#### 

#### 크기증가

추가된 padding의 값만큼 요소의 크기가 커지는 현상

  


![&#xC6D0;&#xB798; &#xAE38;&#xC774;&#xC5D0; padding&#xAC12;&#xC744; &#xB354;&#xD55C;&#xB2E4;.](../.gitbook/assets/image%20%2830%29.png)

```css
/* 100X100 크기의 요소 만들기 */
.box {
    width: 60px;  /* +40 */
    height: 80px; /* +20 */
    padding: 10px 20px; 
}
```

####  

#### **자동계산**

```css
box-sizing: border-box
```

을 넣어서 브라우저가 계산된 width/height 의 값을 계산해서 지정해준다.





### **7.border**

요소의 '테두리 선'을 지정 \*단축속성\*

| 값 | 의미 | 기본값 |
| :--- | :--- | :--- |
| border-width | 선의 두께 | medium |
| border-style | 선의 종류 | none |
| border-color | 선의 색상 | black |

```css
.box {
    border: 1px solid #000;
}
```

#### border-width \*단축/개별\*

| 값 | 의미 |
| :--- | :--- |
| medium | 중간 |
| thin | 얇은 |
| thick | 두꺼운 |
| 단위 | px,em,cm등 단위로 지정 |

```css
.box {
    border-width: 10px 20px 30px 40px; /* 위 우 아래 좌 */
    border-width: 10px 20px 40px;      /* 위 (좌,우) 아래 */
    border-width: 10px 40px;           /* (위,아래),(좌,우) */
    border-width: 10px;                /* (위,아래,좌,우) */
}
```

#### 

#### border-style

선의 종류를 지정

| 값 | 의미 |
| :--- | :--- |
| hidden | 선없음과 동일\(table에서 사용\) |
| solid | 실선 |
| dotted | 점선 |
| dashed | 파선\(긴점\) |
| double | 두줄선 |
| groove | 홈이 파여있는 선 |
| ridge | 솟은 모양 \(groove반대\) |
| inset | 요소 전체가 들어간 모양 |
| outset | 요소 전체가 나온 모양 |

```css
.box {
    border-style: solid dotted double; /* 위 우 아래 좌 */
    border-style: solid solid solid;      /* 위 (좌,우) 아래 */
    border-style: solid dotted;           /* (위,아래),(좌,우) */
    border-style: solid;                /* (위,아래,좌,우) */
}
```

#### 

#### border-color

| 값 | 의미 |
| :--- | :--- |
| 색상 | 선의 색상을 지정 |
| transparent | 투명한 선\(요소의 배경색이 보임\) |



#### 기타속성

| border-top | 위쪽선 | 두께 종류 색상 |
| :--- | :--- | :--- |
| border-top-width | 위쪽 선의 두께 | 두께 |
| border-top-style | 위쪽 선의 종류 | 종류 |
| border-top-color | 위쪽 선의 색상 | 색상 |
| bottom / left / right 도 쓸 수 있다 |  |  |

**\*padding과 마찬가지로 외각선이기 때문에 선의 두깨만큼 요소의 크기가 커진다.\***

```css
box-sizing: border-box
```

을 추가해서 사이즈를 유지하도록 구현할 수 있다.





### **8.box-sizing**

요소의 크기 계산 기준을 지정

| 값 | 의미 | 기본값 |
| :--- | :--- | :--- |
| content-box | 너비\(w/h\)만으로 요소의 크기 계산 | content-box |
| border-box | 너비에 padding과 border를 포함하여 자동으로 계산 |  |



### **9.display**

요소의 박스타입을 설정

| 값 | 의미 |
| :--- | :--- |
| block | 블록요소\(div등\) |
| inline | 인라인요소\(span등\) |
| inline-block | 인라인-블록\(input등\) 가로세로값을 가질 수 있는 inline |
| 기타 | table, table-cell, flex등 |
| none | 요소의 박스타입이 없음 \(화면에서 요소가 사라짐\) |



### **10.overflow**

요소의 크기 이상으로 내용\(자식요소\)이 넘쳤을때 내용의 보여짐을 제어 \*단축속성\*

| 값 | 의미 |
| :--- | :--- |
| visible \(기본값\) | 넘친부분을 자르지 않고 그대로 보여줌 |
| hidden | 넘친부분을 잘라내고, 보이지 않게 함 |
| scroll | 넘친부분을 잘라내고 스크롤바 이용 |
| auto | 넘친 경우에만 잘래내고 스크롤바 사용 |

![](../.gitbook/assets/image%20%2868%29.png)



### **11.opacity**

요소의 투명도를 지정

| 값 | 의미 | 기본값 |
| :--- | :--- | :--- |
| 숫자 | 0~1사이의 소수점 숫자 | 1 |

```css
.box {
    opacity: 0.5;   /* 50% 투명도 (반투명)*/
    opacity: 0;     /* 0% 투명도 (투명)*/
    opacity: .75;   /* 75% 투명도 (반투명)*/
}
```

![child&#xD074;&#xB798;&#xC2A4;&#xB97C; 50%&#xD22C;&#xBA85;&#xB3C4;&#xB85C; &#xAD6C;&#xD604; &#xD558;&#xC600;&#xB2E4;.](../.gitbook/assets/image%20%2846%29.png)





