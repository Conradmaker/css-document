# 글꼴,문자

## **font**

글자 관련 속성들을 지정 \*단축속성\*

| font-style | 글자 기울기 지정 | normal |
| :--- | :--- | :--- |
| font-weight | 글자 두 지정 | normal |
| font-size | 글자 크기 지정 | medium\(16px\) |
| line-height | 줄 높이\(줄 간격\)지정 | normal\(reset.css=1\) |
| font-family | 글꼴\(서체\)지정 | 운영체제\(브라우저\)에따라 다름 |

```text
font: 기울기 두께 크기 / 줄높이 글꼴;

.box{
    font: italic bold 10px / 1.5 "arial" sans-serif;
}
```

글자 크기와 글꼴이 설정되어야만 단축속성을 사용할 수 있다.



### **font-style**

| normal \(기본값\) | 스타일 없음 |
| :--- | :--- |
| italic | 이텔릭체\(활자\) |
| oblique | 기울어진 글자 |

### **font-weight**

| normal | 기본 글자두께, 400과 동일 |
| :--- | :--- |
| bold | 글자 두껍게, 700과 동일 |
| bolder | 부모 요소보다 더 두껍게 |
| lighter | 부모 요소보다 더 얇게 |
| 숫자 | 100부터 900까지의 100단위 숫자 9개, normal과 bold이외의 두께를 제공하는 서체 위함 |

​

font-weight의 각 값은 일반적으로 다음과 같은 글꼴의 이름으로 표현됨

| 100 | thin \(hairline\) |
| :--- | :--- |
| 200 | Extra Light \(Ultra Light\) |
| 300 | Light |
| 400 | Normal |
| 500 | Medium |
| 600 | Semi Bold \(Demi Bold\) |
| 700 | Bold |
| 800 | Extra Bold \(Ultra Bold\) |
| 900 | Black \(Heavy\) |

​숫자와 두께의 불일치

-normal/bold만 지원하는 글꼴일 결구.

100~500은 normal을 의미하고 600~900은 bold를 의미한다.

​



### **font-size**

아래 속성값을 자주 사용한다

| 단위 | px,em,cm | 16px |
| :--- | :--- | :--- |
| % | 부모요소의 비율로 지정 |  |

### \*\*\*\*

### **line-height**

| normal | 브라우저의 기본 정의를 사용\(1~1.4\) |
| :--- | :--- |
| 숫자 | 요소 자체의 글꼴 크기의 배수로 지정 |
| 단위 | px,em,cm등의 단위 |
| % | 요소 자체의 글꼴 크기의 비율로 지정 |

line-height의 값이 32px이고 font-size의 값이 16px라면

여백은 16px가 된다

- 숫자값을 이용해 배수지정을 추천한다. \(1.4~1.7\)





### font-family

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#xAE00;&#xAF34;&#xC774;&#xB984;</th>
      <th style="text-align:left">&#xAE00;&#xAF34; (&#xC11C;&#xCCB4; &#xD6C4;&#xBCF4;) &#xBAA9;&#xB85D;&#xC744;
        &#xC9C0;&#xC815;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p>serif</p>
        <p>sans-serif</p>
        <p>monospace</p>
        <p>cursive</p>
        <p>fantasy</p>
      </td>
      <td style="text-align:left">&#xAE00;&#xAF34; &#xACC4;&#xC5F4; &#xC774;&#xB984;&#xC744; &#xC9C0;&#xC815;</td>
    </tr>
  </tbody>
</table>

```css
font-family:[글꼴후보1, 글꼴후보2...], 글꼴계열;

.box{
    font-family: Arial, "Open Sans", "돋움", sans-serif;
}
/* Arial이 없으면 Open Sans 없으면 돋움 마지막에도 다 없으면 sans-serif계열에서 알아서 찾아라*/
```

### 글꼴계열

| serif | 바탕체 계열 |
| :--- | :--- |
| sans-serif | 고딕체 계열 |
| monospace | 고정너비 글꼴 계열 |
| cursive | 필기체 계열 |
| fantasy | 장식 글꼴 계열 |

​

## **문자 관련 속성**

### ​

### **color**

문자의 색상을 지정

| 색상 | 문자의 색상을 지정 | rgb\(0,0,0\) |
| :---: | :---: | :---: |


| 표현 | 의미 | 예시 |
| :--- | :--- | :--- |
| 색상이름 | 브라우저에서 제공하는 색상의 이름 | red,blue |
| \*Hex색상코드 | 16진수 색상 \(Hexademical Colors\) | \#000000 |
| RGB | 빛의 삼원색 | rgb\(255,255,255\) |
| RGBA | 빛의 삼원색, 투명도 | rgb\(255,0,0, .5\) |
| HSL | 색상,채도,명도 | hsl\(120, 100%, 50%\) |
| HSLA | 색상,채도,명도,투명도 | hsla\(120, 100%, 50%, .3\) |

 색상을 이용하는 모든 속성의 값으로 사용할 수 있다.



### **text-align**

문자 정렬 방식을 지정

| left | 왼쪽 정렬 |
| :--- | :--- |
| right | 오른쪽 정렬 |
| center | 가운데 정렬 |
| justify | 양쪽 맞충 |



### **text-decoration**

문자의 장식\(line\)을 설정

| none | 선없음 |
| :--- | :--- |
| underline | 밑줄을 지정 |
| overline | 윗줄을 지정 |
| line-through | 중앙 선을 지정 |

### \*\*\*\*

### **text-indent**

\(첫번째 줄의\) 들여쓰기를 지정

-음수 값을 사용할 수 있다.\(내어쓰기\)

​

### letter-spacing

글자사이의 간격을 지정

| normal | 단어 사이의 일반 간격 |
| :--- | :--- |
| 단위 | px,em,cm등 단위로 지정 |

### word-spacing

띄어쓰기의 간격을 지정

| normal | 단어 사이의 일반 간격 |
| :--- | :--- |
| 단위 | px,em,cm등 단위로 지정 |

​

