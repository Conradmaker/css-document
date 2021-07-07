# Grid Function\(함수\)

## **Grid Functions**

그리드에서 사용하는 주요 함수들에 대해서 알아봅시다.

​

**​**

### **repeat**

**repeat\(\)** 함수는 행/열\(Track\)의 크기 정의를 반복합니다.

‘반복되는 횟수’와 ‘행/열의 크기 정의’를 인수로 사용합니다.

**grid-template-rows**와 **grid-template-columns**에서 사용합니다.

각 코드 블록 내 컨테이너\(**.container**\)들은 모두 같은 의미입니다.

```css
/* 9컬럼 그리드 */
.container {
  grid-template-columns: 100px 100px 100px 100px 100px 100px 100px 100px 100px;
}
.container {
  grid-template-columns: repeat(9, 100px);
}
```

```css
.container {
  grid-template-rows: [row-start] 200px [row-end row-start] 200px [row-end];
  grid-template-columns: [col-start] 100px [col-end col-start] 100px [col-end col-start] 100px [col-end];
}
.container {
  grid-template-rows: repeat(2, [row-start] 200px [row-end]);
  grid-template-columns: repeat(3, [col-start] 100px [col-end]);
}
.container {
  grid-template: repeat(2, [row-start] 200px [row-end]) / repeat(3, [col-start] 100px [col-end]);
}
```

```css
.container {
  /* 12컬럼 그리드 */
  grid-template-columns: 1fr 2fr 1fr 2fr 1fr 2fr 1fr 2fr 1fr 2fr 1fr 2fr;
}
.container {
  grid-template-columns: repeat(6, 1fr 2fr);
}
```



### **minmax**

**minmax\(\)** 함수는 행/열\(Track\)의 ‘최소/최대 크기’를 정의합니다.

첫 번째 인수는 ‘최솟값’이고 두 번째 인수는 ‘최댓값’입니다.

**grid-template-rows**, **grid-template-columns**, **grid-auto-rows** 그리고 **grid-auto-columns**에서 사용합니다.

일반 요소에 **min-width**와 **max-width** 속성을 동시 지정하는 것과 유사합니다.

![](../.gitbook/assets/image%20%2877%29.png)

**minmax\(\)**를 통해 암시적 행/열\(Track\) 크기를 좀 더 유연하게 사용할 수 있습니다.

다음 예제는 암시적 ‘행/열’의 크기를 최소 ‘200px/300px’으로 지정하지만 **auto**를 통해 그리드 아이템의 크기에 따라 확장될 수 있습니다.

```css
.container {
  grid-auto-rows: minmax(200px, auto);
  grid-auto-columns: minmax(300px, auto);
}
```

### \*\*\*\*

### **fit-content**

**fit-content\(\)** 함수는 행/열\(Track\)의 크기를 그리드 아이템\(Item\)이 포함하는 내용\(Contents\) 크기에 맞춥니다.

‘내용의 최대 크기’를 인수로 사용합니다.

**minmax\(auto, max-content\)**와 유사합니다.

```css
.container {
  grid-template-columns: fit-content(300px) fit-content(300px);
}
```

![](../.gitbook/assets/image%20%2829%29.png)

