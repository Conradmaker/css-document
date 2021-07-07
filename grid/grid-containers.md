# Grid - 1

## **Grid Containers**

전장에 속성들을 정리해 놓았습니다.

### **display**

Grid Container\(컨테이너\)를 정의합니다.

정의된 컨테이너의 자식 요소들은 자동으로 Grid Items\(아이템\)로 정의됩니다.

> 그리드를 사용하기 위해 컨테이너에 필수로 작성합니다!

| **값** | **의미** |
| :--- | :--- |
| **grid** | Block 특성의 Grid Container를 정의 |
| **inline-grid** | Inline 특성의 Grid Container를 정의 |

```text
﻿.container { display: grid; }﻿
```



### **grid-template-rows**

명시적 행\(Track\)의 크기를 정의합니다.

동시에 라인\(Line\)의 이름도 정의할 수 있습니다.

**fr**\(fraction, 공간 비율\) 단위를 사용할 수 있습니다.

**repeat\(\)** 함수를 사용할 수 있습니다.

> 사용 방법은 **grid-template-columns**와 같습니다.

```css
﻿.container { 
 display: grid;
 grid-template-rows: 1행크기 2행크기 ...;
 grid-template-rows: [선이름] 1행크기 [선이름] 2행크기 [선이름] ...; 
} ﻿
```

```css
/* 각 행의 크기를 정의합니다. */
.container {
  grid-template-rows: 100px 200px;
}
/* 동시에 각 라인의 이름도 정의할 수 있습니다. */
.container {
  grid-template-rows: [first] 100px [second] 200px [third];
}
/* 라인에 중복된 이름을 지정할 수 있습니다. */
.container {
  grid-template-rows: [row1-start] 100px [row1-end row2-start] 200px [row2-end];
}
```

각 라인은 행\(Row, Track\)과 열\(Column, Track\)의 개수대로 숫자\(양수/음수\) 라인 이름이 자동으로 지정되어 있어서, 꼭 필요한 경우가 아니면 라인 이름을 정의할 필요가 없습니다.

```css
.container {
  grid-template-rows: 100px 200px;
  /* grid-template-rows: [1 -3] 100px [2 -2] 200px [3 -1]; */
}
```

```css
.container {
  width: 400px;
  display: grid;
  grid-template-rows: repeat(3, 100px);
  grid-template-columns: repeat(3, 1fr);
}
```

![](../.gitbook/assets/image%20%2853%29.png)



###  **grid-template-columns**

명시적 열\(Track\)의 크기를 정의합니다.

동시에 라인\(Line\)의 이름도 정의할 수 있습니다.

**fr**\(fraction, 공간 비율\) 단위를 사용할 수 있습니다.

**repeat\(\)** 함수를 사용할 수 있습니다.

> 사용 방법은 **grid-template-rows**와 같습니다.

```css
.container {
  display: grid;
  grid-template-columns: 1열크기 2열크기 ...;
  grid-template-columns: [선이름] 1열크기 [선이름] 2열크기 [선이름] ...;
}
```

```css
/* 각 열의 크기를 정의합니다. */
.container {
  grid-template-columns: 100px 200px;
}
/* 동시에 각 라인의 이름도 정의할 수 있습니다. */
.container {
  grid-template-columns: [first] 100px [second] 200px [third];
}
/* 라인에 중복된 이름을 지정할 수 있습니다. */
.container {
  grid-template-columns: [col1-start] 100px [col1-end col2-start] 200px [col2-end];
}
```

 만약 **1200px** 너비의 ‘12컬럼 그리드 템플릿’을 정의한다면 다음과 작성할 수 있습니다.

```css
.container {
  width: 1200px;
  grid-template-columns: 100px 100px 100px 100px 100px 100px 100px 100px 100px 100px 100px 100px;
}
```

12개의 열\(컬럼\) 크기를 하나씩 지정했습니다만, 이 방법은 당연히 입력도 관리도 힘들겠죠!

**repeat\(\)** 함수를 사용하면 위 내용을 다음과 같이 간소화할 수 있습니다.

```css
.container {
  width: 1200px;
  grid-template-columns: repeat(12, 100px);
}
컬럼
```

컬럼을 크기를 **fr** 단위를 사용해 다음과 같이 비율로 지정할 수도 있습니다.

각 컬럼은 비율에 맞게 출력되기 때문에 컨테이너의 너비가 가변해도 열 크기를 수정할 필요가 없습니다.

> **fr** 단위에 대한 좀 더 자세한 내용은 본 포스트 하단에 있는 ‘Grid Units / fr’ 파트에서 확인할 수 있습니다.

```css
.container {
  width: 80%;
  grid-template-columns: repeat(12, 1fr);
}
```

 **repeat\(\)** 함수는 2번째 인수를 반복하기 때문에 다음과 같이 활용할 수 있습니다.

```css
.container {
  grid-template-columns: repeat(4, 100px 200px 50px);
  /* grid-template-columns: 100px 200px 50px 100px 200px 50px 100px 200px 50px 100px 200px 50px; */
}
.container {
  grid-template-columns: repeat(4, 1fr 2fr 3fr);
  /* grid-template-columns: 1fr 2fr 3fr 1fr 2fr 3fr 1fr 2fr 3fr 1fr 2fr 3fr; */
}
```

![form&#xD0DC;&#xADF8; &#xC0AC;&#xC6A9;&#xC2DC; &#xC720;&#xC6A9;&#xD558;&#xC9C0; &#xC54A;&#xC744;&#xAE4C;..??](../.gitbook/assets/image%20%2840%29.png)

### \*\*\*\*

### **grid-row**

**grid-row-start**과 **grid-row-end**의 단축 속성입니다.

각 속성을 **/**로 구분하는 것에 주의하세요.

```css
.item {
  grid-row: <grid-row-start> / <grid-row-end>;
}
```

 각 코드 블록 내 아이템\(**.item**\)들은 모두 같은 의미입니다.

```css
.item {
  grid-row-start: 1;
  grid-row-end: 2;
}
.item {
  grid-row: 1 / 2;
}
```

```css
.item {
  grid-row-start: 2;
  grid-row-end: span 3;
}
.item {
  grid-row: 2 / span 3;
}
.item {
  grid-row: 2 / 5;
}
```

```css
.item {
  grid-row-start: span 3;
  grid-row-end: 4;
}
.item {
  grid-row: span 3 / 4;
}
.item {
  grid-row: 1 / 4;
}
```

### \*\*\*\*

### **grid-column**

**grid-column-start**과 **grid-column-end**의 단축 속성입니다.

각 속성을 **/**로 구분하는 것에 주의하세요.

```css
.item {
  grid-column: <grid-column-start> / <grid-column-end>;
}
```

각 코드 블록 내 아이템\(**.item**\)들은 모두 같은 의미입니다.

음수 결과를 위해 **span** 키워드를 ‘시작 위치’에 작성함에 주의하세요!

```css
.item {
  grid-column-start: -1;
  grid-column-end: -3;
}
.item {
  grid-column: -1 / -3;
}
.item {
  /* Column -1번에서 -3번(-1-2=-3)까지 */
  grid-column: span 2 / -1;
}
```

```css
.item {
  grid-column-start: 2;
  grid-column-end: -1;
}
.item {
  /* Column 2번에서 끝(-1번)까지 */
  grid-column: 2 / -1;
}
```

![](../.gitbook/assets/image%20%2851%29.png)



### **grid-template-areas**

지정된 그리드 영역 이름\(**grid-area**\)을 참조해 그리드 템플릿을 생성합니다.

> **grid-area**는 Grid Container가 아닌 Grid Item에 적용하는 속성입니다.

```css
.container {
  display: grid;
  grid-template-rows: repeat(3, 100px);
  grid-template-columns: repeat(3, 1fr);
  grid-template-areas:
    "header header header"
    "main main aside"
    "footer footer footer";
}
header { grid-area: header; }
main   { grid-area: main;   }
aside  { grid-area: aside;  }
footer { grid-area: footer; }
```

![](../.gitbook/assets/image%20%2875%29.png)

 **.**\(마침표\)를 사용하거나 명시적으로 **none**을 입력해 빈 영역을 정의할 수 있습니다.

```css
.container {
  display: grid;
  grid-template-rows: repeat(4, 100px);
  grid-template-columns: repeat(3, 1fr);
  grid-template-areas:
    "header header header"
    "main . ."
    "main . aside"
    "footer footer footer";
}
header { grid-area: header; }
main   { grid-area: main;   }
aside  { grid-area: aside;  }
footer { grid-area: footer; }
```

![](../.gitbook/assets/image%20%2871%29.png)

![](../.gitbook/assets/image%20%2838%29.png)



### **row-gap\(grid-row-gap\)**

각 행과 행 사이의 간격\(Gutter\)을 지정합니다.

> 더 명확하게는 그리드 선\(Grid Line\)의 크기를 지정한다고 표현할 수 있습니다.

```css
.container {
  row-gap: 크기;
}
```

### \*\*\*\*

### **column-gap\(grid-column-gap\)**

각 열과 열 사이의 간격\(Gutter\)을 지정합니다.

```css
.container {
  column-gap: 크기;
}
```

\*\*\*\*

### **gap\(grid-gap\)**

각 행과 행, 열과 열 사이의 간격\(Gutter\)을 지정합니다.

```css
.container {
  gap: <grid-row-gap> <grid-column-gap>;
}
```

```css
.container {
  display: grid;
  grid-template-rows: repeat(2, 150px);
  grid-template-columns: repeat(3, 1fr);
  gap: 20px 10px;
}
/* 하나의 값으로 통일할 수 있습니다. */
.container {
  gap: 10px;  /* row-gap: 10px; + column-gap: 10px; */
}
/* 하나의 값만 적용하고자 한다면 다음과 같이 사용할 수 있습니다. */
.container {
  gap: 10px 0; /* row-gap */
  gap: 0 10px; /* column-gap */
}
```

![](../.gitbook/assets/image%20%2814%29.png)

**grid-gap**\(**grid-row-gap**, **grid-column-gap**\)의 접두사 **grid-**는 더 이상 사용되지 않으며\(Deprecated\), **gap**\(**row-gap**, **column-gap**\)로 교체되었습니다.

하지만 일부 버전의 브라우저 지원을 위해 **grid-** 접두사의 사용을 고려할 수 있습니다.

[\[css-grid\]\[css-multicol\]\[css-flexbox\]\[css-tables\] Proposal for Various Gap Issues.](https://drafts.csswg.org/css-grid/#change-2016-grid-gap)

[\[css-grid\] grid-gap is deprecated.](https://github.com/postcss/autoprefixer/issues/1046)

{% embed url="https://drafts.csswg.org/css-grid/\#change-2016-grid-gap" %}



### **grid-auto-rows**

암시적 행\(Track\)의 크기를 정의합니다.

아이템\(Item\)이 **grid-template-rows**로 정의한 명시적 행 외부에 배치되는 경우 암시적 행의 크기가 적용됩니다.

```markup
<div class="container">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
</div>
```

```css
.container {
  width: 300px;
  height: 200px;
  display: grid;
  grid-template-rows: 100px 100px; /* 명시적 2개 행 정의 */
  grid-template-columns: 150px 150px; /* 명시적 2개 열 정의 */
  grid-auto-rows: 100px; /* 그 외(암시적) 행의 크기 정의 */
}
.item:nth-child(3) {
  grid-row: 3 / 4;
}
```

![](../.gitbook/assets/image%20%2833%29.png)

### \*\*\*\*

### **grid-auto-columns**

암시적 열\(Track\)의 크기를 정의합니다.

아이템\(Item\)이 **grid-template-columns**로 정의한 명시적 열 외부에 배치되는 경우 암시적 열의 크기가 적용됩니다.

```css
.container {
  width: 300px;
  height: 200px;
  display: grid;
  grid-template-rows: 100px 100px;
  grid-template-columns: 150px 150px;
  grid-auto-rows: 100px;
  grid-auto-columns: 100px;
}
.item:nth-child(3) {
  grid-row: 3 / 4;
  grid-column: 3 / 4;
}
```

![](../.gitbook/assets/image%20%2831%29.png)

다음과 같이 아이템이 배치되는 위치에 맞게 암시적 행과 열의 개수가 생성됩니다.

암시적 크기가 적용된 행과 열은 양수 라인 번호만 사용할 수 있습니다.\(음수 사용 불가\)

![](../.gitbook/assets/image%20%2822%29.png)

![](../.gitbook/assets/image%20%2837%29.png)



### \*\*\*\*

### **grid-auto-flow**

배치하지 않은 아이템\(Item\)을 어떤 방식의 ‘자동 배치 알고리즘’으로 처리할지 정의합니다.

> 배치한 아이템은 **grid-area**\(이하 개별 속성 포함\)를 사용한 아이템을 의미합니다.



| **값** | **의미** | **기본값** |
| :--- | :--- | :--- |
| row | 각 행 축을 따라 차례로 배치 | **row** |
| column | 각 열 축을 따라 차례로 배치 |  |
| row dense\(dense\) | 각 행 축을 따라 차례로 배치, 빈 영역 메움! |  |
| column dense | 각 열 축을 따라 차례로 배치, 빈 영역 메움! |  |

 다음은 **row**와 **row dense**에 대한 예제입니다.

```css
/* For row & row dense */
.container {
  display: grid;
  grid-template-rows: repeat(3, 1fr);
  grid-template-columns: repeat(3, 1fr);
  grid-auto-flow: row || row dense || dense;
}
.item:nth-child(2) {
  grid-column: span 3;
}
```

![](../.gitbook/assets/image%20%2839%29.png)

 다음은 **column**과 **column dense**에 대한 예제입니다.

```css
/* For column & column dense */
.container {
  display: grid;
  grid-template-rows: repeat(3, 1fr);
  grid-template-columns: repeat(3, 1fr);
  grid-auto-flow: column || column dense;
}
.item:nth-child(1) {
  grid-column: 2 / span 2;
}
.item:nth-child(2) {
  grid-column: span 2;
}
```

![](../.gitbook/assets/image%20%2859%29.png)



### **grid-template**

**grid-template-rows**, **grid-template-columns** 그리고 **grid-template-areas**의 단축 속성입니다.

```css
.container {
  grid-template: <grid-template-rows> / <grid-template-columns>;
  grid-template: <grid-template-areas>;
}
```

다음과 같이 작성할 수도 있습니다.

```css
.container {
  grid-template:
    [1행시작선이름] "AREAS" 행너비 [1행끝선이름]
    [2행시작선이름] "AREAS" 행너비 [2행끝선이름]
    / <grid-template-columns>;
}
```

```css
.container {
  display: grid;
  grid-template:
    "header header header" 80px
    "main main aside" 350px
    "footer footer footer" 130px
    / 2fr 100px 1fr;
}
header { grid-area: header; }
main   { grid-area: main; }
aside  { grid-area: aside; }
footer { grid-area: footer; }
```

위 예제의 컨테이너는 다음과 같이 해석할 수 있습니다.

```css
.container {
  display: grid;
  grid-template-rows: 80px 350px 130px;
  grid-template-columns: 2fr 100px 1fr;
  grid-template-areas:
    "header header header"
    "main main aside"
    "footer footer footer";
}
```

### \*\*\*\*

### **grid**

**grid-template-xxx**과 **grid-auto-xxx**의 단축 속성입니다.

```css
.container {
  grid: <grid-template>;
  grid: <grid-template-rows> / <grid-auto-flow> <grid-auto-columns>;
  grid: <grid-auto-flow> <grid-auto-rows> / <grid-template-columns>;
}
```

 각 코드 블록 내 컨테이너\(**.container**\)들은 모두 같은 의미입니다.

```css
.container {
  grid: <grid-template-rows> / <grid-template-columns>;
}
.container {
  grid: 100px 200px / 1fr 2fr;
}
.container {
  grid-template-rows: 100px 200px;
  grid-template-columns: 1fr 2fr;
}
```

```css
.container {
  grid: <grid-template>;
}
.container {
  grid:
    "header header header" 80px
    "main main aside" 350px
    "footer footer footer" 130px
    / 2fr 100px 1fr;
}
.container {
  grid-template:
    "header header header" 80px
    "main main aside" 350px
    "footer footer footer" 130px
    / 2fr 100px 1fr;
}
```

**grid-auto-flow**를 작성할 때는 **auto-flow** 키워드를 사용합니다.

**/**로 구분해 작성하는 위치가 곧 **row**, **column** 값을 의미합니다.

따라서, **row**, **column** 값은 작성하지 마세요.

**dense** 값은 **auto-flow** 뒤에 붙여줍니다.

```css
.container {
  grid: <grid-template-rows> / <grid-auto-flow> <grid-auto-columns>;
}
.container {
  grid: 100px 100px / auto-flow 150px;
}
.container {
  grid-template-row: 100px 100px;
  grid-auto-flow: column;
  grid-auto-columns: 150px;
}
```

```css
.container {
  grid: <grid-auto-flow> <grid-auto-rows> / <grid-template-columns>;
}
.container {
  grid: auto-flow 150px / 100px 100px;
}
.container {
  grid-template-columns: 100px 100px;
  grid-auto-flow: row;
  grid-auto-rows: 150px;
}
```

```css
.container {
  grid: auto-flow dense 150px / 100px 100px;
}
.container {
  grid-template-columns: 100px 100px;
  grid-auto-flow: row dense;
  grid-auto-rows: 150px;
}
```

