# Grid Units \(단위 , 용어\)

## **Grid Units**

그리드에서 사용하는 주요 단위들에 대해서 알아봅시다.

**fr**

**fr**\(fractional unit\)은 **사용 가능한 공간에 대한 비율**을 의미합니다.

다음 예제는 그리드 컨테이너의 3번째 컬럼에 **100px**, 4번째 컬럼에 **25%**를 사용하고 남은 공간을 1번째 컬럼에 ‘1/3’, 2번째 컬럼에 ‘2/3’ 만큼 사용합니다.

```css
.container {
  grid-template-columns: 1fr 2fr 100px 25%;
}
```

![](../.gitbook/assets/image%20%2826%29.png)



### **min-content**

그리드 아이템이 포함하는 내용\(Contents\)의 최소 크기를 의미합니다.

```markup
<div class="container">
  <div class="item">Hello HEROPY~</div>
  <!-- ... -->
</div>
```

```css
.container {
  grid-template-columns: min-content 1fr;
}
```

![](../.gitbook/assets/image%20%2872%29.png)

```markup
<div class="container">
  <div class="item">내용의 최소 크기</div>
  <!-- ... -->
</div>
```

 한글을 사용하는 경우 **word-break: keep-all;**를 설정하면 정상적으로 동작합니다.

![](../.gitbook/assets/image%20%288%29.png)

### \*\*\*\*

### **max-content**

그리드 아이템이 포함하는 내용\(Contents\)의 최대 크기를 의미합니다.

```markup
<div class="container">
  <div class="item">Hello HEROPY~</div>
  <!-- ... -->
</div>

```

```css
.container {
  grid-template-columns: max-content 1fr;
}
```

![](../.gitbook/assets/image%20%281%29.png)

그리드 함수들과 같이 더 유용하게 활용할 수 있습니다.

다음 예제는 총 4컬럼 그리드를 생성하며 각 열\(Track\)은 최대 **1fr** 크기를 가지지만, **max-content**를 통해 포함된 그리드 아이템의 내용보다 작아질 수 없습니다.

```css
.container {
  grid-template-columns: repeat(4, minmax(max-content, 1fr));
}
```

​

### **auto-fill, auto-fit**

행/열\(Track\)의 개수를 그리드 컨테이너\(Container\) 및 행/열 크기에 맞게 자동으로\(암시적\) 조정합니다.

**repeat\(\)** 함수와 같이 사용하며, 행/열과 아이템\(Item\) 개수가 명확할 필요가 없거나 명확하지 않은 경우 유용합니다.\(반응형 그리드\)

**auto-fill**과 **auto-fit**은 **간단한 차이점을 제외하면 동일하게 동작합니다.**

다음 4컬럼 그리드 예제에서 컨테이너의 크기가 아이템들을 수용하기 충분하지 않은 경우 아이템은 넘치기 시작합니다.\(아이템의 최소 크기가 **120px**입니다.\)  


```css
.container {
  grid-template-columns: repeat(4, minmax(120px, 1fr));
}
```

![](../.gitbook/assets/image%20%2861%29.png)

만약 4컬럼 그리드를 고집할 필요가 없다면, 다음과 같이 ‘반복횟수’\(**repeat\(\)** 함수의 첫 번째 인수\)를 **auto-fill**이나 **auto-fit**으로 수정할 수 있습니다.

이는 컨테이너의 크기가 아이템들을 수용하기 충분하지 않을 경우 아이템을 자동으로 줄 바꿈 처리하며, 그에 맞게 암시적 행/열도 자동으로 수정합니다

```css
.container {
  grid-template-columns: repeat(auto-fill, minmax(120px, 1fr));
}
```

![](../.gitbook/assets/image%20%2845%29.png)

### **auto-fill과 auto-fit의 차이**

**auto-fill**과 **auto-fit**은 차이점은 그리드 컨테이너가 하나의 행/열\(Track\)에 모든 아이템을 수용하고 **남는 공간이 있을 때** 발생합니다.

다음과 같이 **auto-fill**은 남는 공간\(빈 트랙\)을 그대로 유지하고, **auto-fit**은 남는 공간을 축소합니다.

```css
.container.auto-fill {
  grid-template-columns: repeat(auto-fill, minmax(120px, 1fr));
}
.container.auto-fit {
  grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
}
```

![](../.gitbook/assets/image%20%286%29.png)

## **주요 용어 정리**

### **Track**

트랙\(Track\)은 하나의 행\(Row\) 혹은 열\(Column\)을 의미합니다.

![](../.gitbook/assets/image%20%2874%29.png)

### **Line**

선\(Line\)은 일반적으로 거터\(Gutter\)라고 하는 트랙과 트랙 사이의 간격을 의미합니다.

![](../.gitbook/assets/image%20%2879%29.png)

### **Cell**

셀\(Cell\)은 아이템\(Item\)이 배치되는 최소 단위의 영역\(Area\)입니다.  


![](../.gitbook/assets/image%20%2862%29.png)

### **Area**

영역\(Area\)은 아이템이 배치되는, 하나 이상의 셀\(Cell\)로 이루어진 영역입니다.  


![](../.gitbook/assets/image%20%2813%29.png)

