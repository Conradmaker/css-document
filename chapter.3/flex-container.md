# FLEX - Container

대부분의 사이트는 레이아웃이 수직 구성이기 때문에 '위-아래'로 스크롤하여 사용함

레이아웃에서 가장 많이 사용되는 요소들이 블록요소이기때문에 수직으로 쌓인다는 특징이 있다.

​

flex는 두개의 개념으로 나뉜다.

Container / Items

Container는 Items요소를 감싸는 요소이다.

​

## flex Container

| display | flex Contianer를 정의 |
| :--- | :--- |
| flex-flow | flex-direction와 flex-wrap의 단축 속성 |
| flex-direction | flex items의 주축을 설정 |
| flex-wrap | flex items의 여러줄 묶음 설정 |
| justify-content | 주 축의 정렬 방법을 설정 |
| align-content | 교차축의 정렬 방법을 설정\(2줄 이상\) |
| align-items | 교차축에서 items의 정렬 방법을 설정\(1줄\) |



### display

| display:flex | 컨테이너 자체가 블럭요소로 활용 |
| :--- | :--- |
| display:inline-flex | 컨테이너가 인라인요소처럼 옆으로 쌓임 |

![](../.gitbook/assets/image%20%2823%29.png)



### flex-flow

단축 속성으로 Flex Items의 주 축\(main-axis\)을 설정하고 Items의 여러 줄 묶음\(줄 바꿈\)도 설정

| flex-direction | Items의 주 축\(main-axis\)을 설정 | **row** |
| :--- | :--- | :--- |
| flex-wrap | Items의 여러 줄 묶음\(줄 바꿈\) 설정 | **nowrap** |

```css
flex-flow: 주축 여러줄묶음;

.flex-container {
  flex-flow: row-reverse wrap;
}
```



### **flex-direction**

Items의 주 축\(main-axis\)을 설정합니다.

| **값** | **의미** | **기본값** |
| :--- | :--- | :--- |
| row | Itmes를 수평축\(왼쪽에서 오른쪽으로\)으로 표시 | **row** |
| row-reverse | Items를 **row**의 반대 축으로 표시 |  |
| column | Items를 수직축\(위에서 아래로\)으로 표시 |  |
| column-reverse | Items를 **column**의 반대 축으로 표시 |  |

![](../.gitbook/assets/image%20%2811%29.png)

### **주 축\(main-axis\)과 교차 축\(cross-axis\)**

위에서 언급했었던 주 축\(main-axis\)과 교차 축\(cross-axis\)의 개념은 다음과 같습니다.

값 **row**는 Items를 수평축으로 표시하므로 이때는 주 축이 수평이며 교차 축은 수직이 됩니다.

반대로 값 **column**은 Items를 수직축으로 표시하므로 주 축은 수직이며 교차 축은 수평이 됩니다.

즉, 방향\(수평, 수직\)에 따라 주 축과 교차 축이 달라집니다.  


![&#xC8FC;&#xCD95;&#xC774; &#xBC14;&#xB00C;&#xBA74; &#xAD50;&#xCC28;&#xC810;&#xB3C4; &#xBC14;&#xB00C;&#xAC8C; &#xB41C;&#xB2E4;.](../.gitbook/assets/image%20%2857%29.png)

### **시작점\(flex-start\)과 끝점\(flex-end\)**

시작점\(flex-start\)과 끝점\(flex-end\)이라는 개념도 있습니다.

이는 주 축이나 교차 축의 시작하는 지점과 끝나는 지점을 지칭합니다.

역시 방향에 따라 시작점과 끝점이 달라집니다.

![](../.gitbook/assets/image%20%2848%29.png)

### **flex-wrap**

Items의 여러 줄 묶음\(줄 바꿈\)을 설정합니다.

| **값** | **의미** | **기본값** |
| :--- | :--- | :--- |
| nowrap | 모든 Itmes를 여러 줄로 묶지 않음\(한 줄에 표시\) | **nowrap** |
| wrap | Items를 여러 줄로 묶음 |  |
| wrap-reverse | Items를 **wrap**의 역 방향으로 여러 줄로 묶음 |  |

기본적으로 Items는 한 줄에서만 표시되고 줄 바꿈 되지 않습니다.

이는 지정된 크기\(주 축에 따라 **width**나 **height**\)를 무시하고 한 줄 안에서만 가변합니다.

Items를 줄 바꿈 하려면 값으로 **wrap**을 사용해야 합니다.

![wrap&#xC744; &#xC0AC;&#xC6A9;&#xD558;&#xC9C0; &#xC54A;&#xC73C;&#xBA74; &#xC544;&#xC774;&#xD15C;&#xB4E4;&#xC774; &#xD55C;&#xC904;&#xC5D0; &#xB2E4; &#xB4E4;&#xC5B4;&#xAC04;&#xB2E4;.](../.gitbook/assets/image%20%2856%29.png)



**justify-content**

주 축\(main-axis\)의 정렬 방법을 설정합니다.

| **값** | **의미** | **기본값** |
| :--- | :--- | :--- |
| flex-start | Items를 시작점\(flex-start\)으로 정렬 | **flex-start** |
| flex-end | Items를 끝점\(flex-end\)으로 정렬 |  |
| center | Items를 가운데 정렬 |  |
| space-between | 시작 Item은 시작점에, 마지막 Item은 끝점에 정렬되고 나머지 Items는 사이에 고르게 정렬됨 |  |
| space-around | Items를 균등한 여백을 포함하여 정렬 |  |

![](../.gitbook/assets/image%20%2815%29.png)



### **align-content**

교차 축\(cross-axis\)의 정렬 방법을 설정합니다.

주의할 점은 **flex-wrap** 속성을 통해 Items가 여러 줄\(2줄 이상\)이고 여백이 있을 경우만 사용할 수 있습니다.

> **Items가 한 줄일 경우** **align-items** **속성을 사용하세요.**

| **값** | **의미** | **기본값** |
| :--- | :--- | :--- |
| stretch | Container의 교차 축을 채우기 위해 Items를 늘림 | **stretch** |
| flex-start | Items를 시작점\(flex-start\)으로 정렬 |  |
| flex-end | Items를 끝점\(flex-end\)으로 정렬 |  |
| center | Items를 가운데 정렬 |  |
| space-between | 시작 Item은 시작점에, 마지막 Item은 끝점에 정렬되고 나머지 Items는 사이에 고르게 정렬됨 |  |
| space-around | Items를 균등한 여백을 포함하여 정렬 |  |

![](../.gitbook/assets/image%20%2855%29.png)



### **align-items**

교차 축\(cross-axis\)에서 Items의 정렬 방법을 설정합니다.

Items가 한 줄일 경우 많이 사용합니다.

주의할 점은 Items가 **flex-wrap**을 통해 여러 줄\(2줄 이상\)일 경우에는 **align-content** 속성이 우선합니다.

따라서 **align-items**를 사용하려면 **align-content** 속성을 기본값\(**stretch**\)으로 설정해야 합니다.

| **값** | **의미** | **기본값** |
| :--- | :--- | :--- |
| stretch | Container의 교차 축을 채우기 위해 Items를 늘림 | **stretch** |
| flex-start | Items를 각 줄의 시작점\(flex-start\)으로 정렬 |  |
| flex-end | Items를 각 줄의 끝점\(flex-end\)으로 정렬 |  |
| center | Items를 가운데 정렬 |  |
| baseline | Items를 문자 기준선에 정렬 |  |

```css
align-items: 정렬방법;
```

![](../.gitbook/assets/image%20%283%29.png)

