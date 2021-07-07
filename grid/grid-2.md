# Grid - 2

### **align-content**

그리드 콘텐츠\(Contents\)를 수직\(열 축\) 정렬합니다.

그리드 콘텐츠의 세로 너비가 그리드 컨테이너\(Container\)보다 작아야 합니다.

| **값** | **의미** | **기본값** |
| :--- | :--- | :--- |
| normal | **stretch**와 같습니다. | **normal** |
| start | 시작점\(위쪽\) 정렬 |  |
| center | 수직 가운데 정렬 |  |
| end | 끝점\(아래쪽\) 정렬 |  |
| space-around | 각 행 위아래에 여백을 고르게 정렬 |  |
| space-between | 첫 행은 시작점에, 끝 행은 끝점에 정렬되고 나머지 여백으로 고르게 정렬 |  |
| space-evenly | 모든 여백을 고르게 정렬 |  |
| stretch | 열 축을 채우기 위해 그리드 콘텐츠를 늘림 |  |

```css
.container {
  width: 450px;
  height: 450px;
  display: grid;
  grid-template-rows: repeat(3, 100px);
  grid-template-columns: repeat(3, 100px);
  align-content: <align-content>;
}
```

![](../.gitbook/assets/image%20%287%29.png)

### \*\*\*\*

### **justify-content**

그리드 콘텐츠\(Contents\)를 수평\(행 축\) 정렬합니다.

그리드 콘텐츠의 가로 너비가 그리드 컨테이너\(Container\)보다 작아야 합니다.

| **값** | **의미** | **기본값** |
| :--- | :--- | :--- |
| normal | **stretch**와 같습니다. | **normal** |
| start | 시작점\(왼쪽\) 정렬 |  |
| center | 수평 가운데 정렬 |  |
| end | 끝점\(오른쪽\) 정렬 |  |
| space-around | 각 열 좌우에 여백을 고르게 정렬 |  |
| space-between | 첫 열은 시작점에, 끝 열은 끝점에 정렬되고 나머지 여백으로 고르게 정렬 |  |
| space-evenly | 모든 여백을 고르게 정렬 |  |
| stretch | 행 축을 채우기 위해 그리드 콘텐츠를 늘림 |  |

```css
.container {
  width: 450px;
  height: 450px;
  display: grid;
  grid-template-rows: repeat(3, 100px);
  grid-template-columns: repeat(3, 100px);
  justify-content: <justify-content>;
}
```

![](../.gitbook/assets/image%20%2876%29.png)

### \*\*\*\*

### **align-items**

그리드 아이템\(Items\)들을 수직\(열 축\) 정렬합니다.

그리드 아이템의 세로 너비가 자신이 속한 그리드 행\(Track\)의 크기보다 작아야 합니다.

| **값** | **의미** | **기본값** |
| :--- | :--- | :--- |
| normal | **stretch**와 같습니다. | **normal** |
| start | 시작점\(위쪽\) 정렬 |  |
| center | 수직 가운데 정렬 |  |
| end | 끝점\(아래쪽\) 정렬 |  |
| stretch | 열 축을 채우기 위해 그리드 아이템을 늘림 |  |

![](../.gitbook/assets/image%20%2865%29.png)



### **justify-items**

그리드 아이템\(Items\)들을 수평\(행 축\) 정렬합니다.

그리드 아이템의 가로 너비가 자신이 속한 그리드 열\(Track\)의 크기보다 작아야 합니다.

| **값** | **의미** | **기본값** |
| :--- | :--- | :--- |
| normal | **stretch**와 같습니다. | **normal** |
| start | 시작점\(왼쪽\) 정렬 |  |
| center | 수평 가운데 정렬 |  |
| end | 끝점\(오른쪽\) 정렬 |  |
| stretch | 행 축을 채우기 위해 그리드 아이템을 늘림 |  |

```css
.container {
  width: 450px;
  height: 450px;
  display: grid;
  grid-template-rows: repeat(3, 1fr);
  grid-template-columns: repeat(3, 1fr);
  justify-items: <justify-items>;
}
```

![](../.gitbook/assets/image%20%2810%29.png)



### **align-self**

단일 그리드 **아이템\(Item\)을** 수직\(열 축\) 정렬합니다.

그리드 아이템의 세로 너비가 자신이 속한 그리드 행\(Track\)의 크기보다 작아야 합니다.

| **값** | **의미** | **기본값** |
| :--- | :--- | :--- |
| normal | **stretch**와 같습니다. | **normal** |
| start | 시작점\(위쪽\) 정렬 |  |
| center | 수직 가운데 정렬 |  |
| end | 끝점\(아래쪽\) 정렬 |  |
| stretch | 열 축을 채우기 위해 그리드 아이템을 늘림 |  |

```css
.container {
  display: grid;
  grid-template-rows: repeat(2, 1fr);
  grid-template-columns: repeat(2, 1fr);
}
.item:nth-child(1) { align-self: start; }
.item:nth-child(2) { align-self: center; }
.item:nth-child(3) { align-self: end; }
.item:nth-child(4) { align-self: stretch; }
```

![](../.gitbook/assets/image%20%2864%29.png)



### **justify-self**

단일 그리드 아이템\(Item\)을 수평\(행 축\) 정렬합니다.

그리드 아이템의 가로 너비가 자신이 속한 그리드 열\(Track\)의 크기보다 작아야 합니다.

| **값** | **의미** | **기본값** |
| :--- | :--- | :--- |
| normal | **stretch**와 같습니다. | **normal** |
| start | 시작점\(왼쪽\) 정렬 |  |
| center | 수평 가운데 정렬 |  |
| end | 끝점\(오른쪽\) 정렬 |  |
| stretch | 행 축을 채우기 위해 그리드 아이템을 늘림 |  |

```css
.container {
  display: grid;
  grid-template-rows: repeat(2, 1fr);
  grid-template-columns: repeat(2, 1fr);
}
.item:nth-child(1) { justify-self: start; }
.item:nth-child(2) { justify-self: center; }
.item:nth-child(3) { justify-self: end; }
.item:nth-child(4) { justify-self: stretch; }
```

![](../.gitbook/assets/image%20%2850%29.png)



### **place-self**

**align-self**와 **justify-self**의 단축 속성입니다.

하나의 값만 입력하면 두 속성에 모두 적용됩니다.

> Edge\(IE\) 브라우저에서 지원하지 않는 속성입니다.

```css
.item {
  place-self: <align-self> <justify-self>;
}
```

```css
.item {
  place-self: start end;
}
.item {
  align-self: start;
  justify-self: end;
}
```

```css
.item {
  place-self: center;
}
.item {
  align-self: center;
  justify-self: center;
}
```

### \*\*\*\*

### **order**

그리드 아이템이 자동 배치되는 순서를 변경할 수 있습니다.

숫자가 작을수록 앞서 배치됩니다.

```css
.container {
  display: grid;
  grid-template-rows: repeat(2, 1fr);
  grid-template-columns: repeat(3, 1fr);
}
.item:nth-child(1) { order: 1; }
.item:nth-child(3) { order: 5; }
.item:nth-child(5) { order: -1; }
```

![](../.gitbook/assets/image%20%2843%29.png)

### \*\*\*\*

### **z-index**

**z-index** 속성을 이용해 아이템이 쌓이는 순서를 변경할 수 있습니다.

```css
.item:nth-child(1) {
  grid-area: 1 / 1 / 2 / 3;
}
.item:nth-child(2) {
  grid-area: 1 / 2 / 3 / 3;
  z-index: 1;
}
.item:nth-child(3) {
  grid-area: 2 / 2 / 3 / 4;
}
```

![](../.gitbook/assets/image%20%2812%29.png)

