# 배경



## **background**

요소의 배경을 설정 \*단축설정\*

| background-color | 배경색상 | transparent |
| :--- | :--- | :--- |
| background-image | 하나 이상의 배경 이미지 | none |
| background-repeat | 배경 이미지의 반복 | repeat |
| background-position | 배경이미지의 위치 | 0 0 |
| background-attachment | 배경이미지의 스크롤 여부 | scroll |

```css
background: 색상  이미지경로  반복 위치  스크롤특성;

.box{
    background: red url(...) no-repeat left top scroll;
               /* 색상  경로       반복      위치   스크롤 */
}
.box{
    background: url(...) no-repeat left 100px;
              /*이미지경로   반복      위치*/
}
```



### **background-color**

요소의 배경 색상을 지정- 개별속성

| 색상 | 요소의 배경색상 |  |
| :--- | :--- | :--- |
| transparent | 투명 | transparent |





### **background-image**

요소의 배경에 하나 이상의 이미지를 삽입- 개별속성

| none | 이미지 없음 | none |
| :--- | :--- | :--- |
| url\("경로"\) | 이미지 경로\(URL\) |  |

```css
.box{
    background-image: url(../img/image.jpg);
    width: 120px;
    height: 80px;
             
}
.box2{
    background-image: url(../img/image.jpg) no-repeat,
    url(../img/image2.jpg) no-repeat 100px 50px,
    url(../img/image3.jpg) repeat-x;
    /* 하나 이상의 배경 이미지를 삽입할 경우, ,로 구분(IE9이상) */
```



### **background-repeat**

배경이미지의 반복을 설정

| repeat\(기본값\) | 배경이미지를 수직,수평으로 반복 |
| :--- | :--- |
| repeat-x | 배경이미지를 수평으로 반복 |
| repeat-y | 배경이미지를 수직으로 반복 |
| no-repeat | 반복 없음 |

### \*\*\*\*

### **background-position**

배경 이미지의 위치를 설정- 개별

<table>
  <thead>
    <tr>
      <th style="text-align:left">%</th>
      <th style="text-align:left">
        <p>&#xC67C;&#xCABD; &#xC0C1;&#xB2E8; &#xBAA8;&#xC11C;&#xB9AC;&#xB294; 0%
          0%,</p>
        <p>&#xC624;&#xB978;&#xCABD; &#xD558;&#xB2E8; &#xBAA8;&#xC11C;&#xB9AC;&#xB294;
          100% 100%</p>
      </th>
      <th style="text-align:left">0% 0% &#xAE30;&#xBCF8;&#xAC12;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">&#xBC29;&#xD5A5;</td>
      <td style="text-align:left">
        <p>&#xBC29;&#xD5A5;&#xC744; &#xC785;&#xB825;&#xD558;&#xC5EC; &#xC704;&#xCE58;
          &#xC124;&#xC815;</p>
        <p>top, bottom, left, right, center</p>
      </td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">&#xB2E8;&#xC704;</td>
      <td style="text-align:left">px,cm,em&#xB4F1; &#xB2E8;&#xC704;&#xB85C; &#xC9C0;&#xC815;</td>
      <td style="text-align:left"></td>
    </tr>
  </tbody>
</table>

#### 

#### 사용법

값이 방향인 경우

```css
background-position: 방향1 방향2;  //두개가 바뀌어도 상관없음
```

값이 단위\(%,px\)일 경우

```css
background-position: X축 Y축;    // 두개가 바뀌면 안된다.
```

![](../.gitbook/assets/image%20%2880%29.png)



### **background-attachment**

요소가 스크롤될 때 배경 이미지의 스크롤 여부\(특성\) 설정-개별

| scroll\(기본값\) | 배경 이미지가 요소를 따라서 같이 스크롤 됨 |
| :--- | :--- |
| fixed | 배경 이미지가 뷰포트에 고정되어, 요소와 같이 스크롤되지 않음 |
| local | 요소 내 스크롤 시 배경 이미지가 같이 스크롤 |

![fixed&#xB294; &#xC774;&#xB807;&#xAC8C; &#xC6F9; &#xBC30;&#xACBD;&#xB9CC;&#xB4E4;&#xB54C; &#xC720;&#xC6A9;&#xD558;&#xB2C8; &#xC54C;&#xC544;&#xB450;&#xC790;!](../.gitbook/assets/image%20%2824%29.png)

local은 요소 안에서 같이 스크롤 할때 사용한다 **-**_잘 사용하지는 않는다-_

\_\_

### **background-size**

배경 이미지의 크기를 지정

<table>
  <thead>
    <tr>
      <th style="text-align:left">auto(&#xAE30;&#xBCF8;&#xAC12;)</th>
      <th style="text-align:left">&#xBC30;&#xACBD; &#xC774;&#xBBF8;&#xC9C0;&#xAC00; &#xC6D0;&#xB798;&#xC758;
        &#xD06C;&#xAE30;&#xB85C; &#xD45C;&#xC2DC;&#xB428;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">&#xB2E8;&#xC704;</td>
      <td style="text-align:left">
        <p>-px,em,%&#xB4F1; &#xB2E8;&#xC704;&#xB85C; &#xC9C0;&#xC815;</p>
        <p>-width height &#xD615;&#xD0DC;&#xB85C; &#xC785;&#xB825; &#xAC00;&#xB2A5;
          (120px 480px)</p>
        <p>-width &#xB9CC; &#xC785;&#xB825;&#xD558;&#xBA74; &#xBE44;&#xC728;&#xC5D0;
          &#xB9DE;&#xAC8C; &#xC9C0;&#xC815;&#xB428; (120px)</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">cover</td>
      <td style="text-align:left">
        <p>-&#xBC30;&#xACBD; &#xC774;&#xBBF8;&#xC9C0;&#xC758; &#xD06C;&#xAE30; &#xBE44;&#xC728;&#xC744;
          &#xC720;&#xC9C0;&#xD558;&#xBA70;, &#xC694;&#xC18C;&#xC758; &#xB354; &#xB113;&#xC740;
          &#xB108;&#xBE44;&#xC5D0; &#xB9DE;&#xCDB0;&#xC9D0;</p>
        <p>-&#xC774;&#xBBF8;&#xC9C0;&#xAC00; &#xC798;&#xB9B4; &#xC218; &#xC788;&#xC74C;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">contain</td>
      <td style="text-align:left">
        <p>-&#xBC30;&#xACBD; &#xC774;&#xBBF8;&#xC9C0;&#xC758; &#xD06C;&#xAE30; &#xBE44;&#xC728;&#xC744;
          &#xC720;&#xC9C0;&#xD558;&#xBA70;, &#xC694;&#xC18C;&#xC758; &#xB354; &#xC9E7;&#xC740;
          &#xB108;&#xBE44;&#xC5D0; &#xB9DE;&#xCDB0;&#xC9D0;</p>
        <p>-&#xC774;&#xBBF8;&#xC9C0;&#xAC00; &#xC798;&#xB9AC;&#xC9C0; &#xC54A;&#xC74C;</p>
      </td>
    </tr>
  </tbody>
</table>

![](../.gitbook/assets/image%20%2841%29.png)

