# 띄움\(정렬\),위치

## **float**

요소를 좌우 방향으로 띄움\(수평 정렬\)

| none | 요소 띄움 없음 |
| :--- | :--- |
| left | 왼쪽으로 띄움 |
| right | 오른쪽으로 띄움 |

-float을 적용하면 요소 주변으로 글짜가 흐르게 된다.

-각 요소에 float를 적용하면 요소가 옆으로 쌓이게 된다.

![float&#xC744; &#xC0AC;&#xC6A9;&#xD55C; &#xB4A4;&#xC5D0;&#xB294; clear&#xC744; &#xC0AC;&#xC6A9;&#xD558;&#xC5EC; &#xD574;&#xC81C;&#xD574;&#xC918;&#xC57C;&#xD55C;&#xB2E4;.](../.gitbook/assets/image%20%2825%29.png)

float속성이 적용된 요소의 주위로 다른 요소들이 흐르게 되는데 이를 방지하기 위해 속성을 해제해야함

1. 형제요소에 clear:\(left,right,both\)추가

2.부모요소에 overflow:\(hidden,auto\)추가

3.부모요소에 clearfix클래스 추가하여 해제 \*추천\*

```css
<div class="parent clearfix">
        <div class="child"></div>
        <div class="child"></div>
     </div>



.clearfix::after{
    content:"";
    clear: both;
    display: block; /* or table */ 
}
.child{
    float: left;
}

clearfix 자식요소는 float이 설정된 박스만 있어야한다.
```

### \*\*\*\*

### **display 수정**

float속성이 추가된 요소는 display속성의 값이 대부분 block으로 바뀐다.

![&#xB2E8; flex&#xC18D;&#xC131;&#xC758; &#xACBD;&#xC6B0;&#xC5D0;&#xB294; &#xBCC0;&#xD654; &#xC5C6;&#xC74C;](../.gitbook/assets/image%20%284%29.png)



### **clear**

float속성이 적용되지 않도록 해제

| none | 요소띄움 허용 |
| :--- | :--- |
| left | 왼쪽 띄움 해제 |
| right | 오른쪽 띄움 해제 |
| \*both\* | 좌/우 상관 없이 해제 |

### \*\*\*\*

### **position**

요소의 위치 지정 방법의 유형\(기준\)을 설정

| static \(기본값\) | 기준 없음 / 배치 불가 |
| :--- | :--- |
| relative | 요소 자신을 기준으로 배치 |
| absolute | 위치상 부모요소를 기준으로 배치 |
| fixed | 브라우저\(부포트\)을 기준으로 배치 |
| sticky | 스크롤 영역을 기준으로 배치 |

### \*\*\*\*

### **top/bottom/left/right**

요소의 position기준에 맞는 ''에서의 거리를 설정

| auto | 브라우저가 계산 | auto |
| :--- | :--- | :--- |
| 단위 | px,em,cm단위로 지정 | 0 |
| % | 부모\(위치상의 부모\(조상\)\)요소의 세로/가로 너비의 비율로 지정,음수허용 |  |

![](../.gitbook/assets/image%20%2867%29.png)

###  

### **relative**

![](../.gitbook/assets/image%20%2821%29.png)

###  

### **absolute**

![&#xC704;&#xCE58;&#xC0C1;&#xC758; &#xBD80;&#xBAA8;&#xC694;&#xC18C;&#xB780; &#xC0C1;&#xC704;&#xC694;&#xC18C;&#xC5D0; position&#xAC12;&#xC744; &#xAC00;&#xC9C4;&#xC694;&#xC18C;&#xB97C; &#xB9D0;&#xD55C;&#xB2E4;.](../.gitbook/assets/image%20%2849%29.png)

### \*\*\*\*

### **fixed**

쇼핑몰 우측의 배너라던가 광고등에 이용

브라우저 스크롤을 내려도 그 위치에 그대로 남는다.



### **sticky**

스크롤 영역 기주능로 배치

\*IE지원 불가\*

top/left/right/bottom중 하나라도 가지고 있어야 하고, 스크롤 영역에 맞닿아 있어야한다.

스크롤을 따라가게 만드는 것 \(요소밖으로 따라가지는 않는다.\)

![](../.gitbook/assets/image%20%2836%29.png)

### \*\*\*\*

### **요소 쌓임 순서\(Stack Order\)**

요소가 쌓여 있는 순서를 통해

어떤 효소가 사용자와 가깝게 있는지\(더 위에 쌓이는지\)를 결정 \(z축\)

1.static을 제외한 position속성의 값이 있을 경우 가장 위에 쌓임

2.position이 모두 존재한다면 z-index속성의 숫자 값이 높을 수 록 위에 쌓임

3.position속성의 값이 있고,z-index속성의 숫자값이 같다면

 html의 마지막 코드일 수 록 위에 쌓인다.\(나중에 작성한 코드\)

### \*\*\*\*

### **display수정**

absolute.fixed속성값이 적용된 요소는 display속성의 값이 대부분 bolck으로 수정된다.

\*flex속성값에는 적용되지 않는다\*

​

