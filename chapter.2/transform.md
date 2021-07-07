# 변형 \(Transform\)

## **transform**

요소의 변환 효과\(변형\)를 지정

```css
transform: 변환함수1 변환함수2 변환함수3....;
transform: 원근밥  이동  크기  회전  기울임;


.box{
  transform: rotate(20deg) translate(10px,0);
}
```

### \*\*\*\*

### **2D 변환 함수**

| translate\(x,y\) | 이동\(X축,Y축\) | 단위 |
| :--- | :--- | :--- |
| translateX\(x\) | 이동\(X축\) | 단위 |
| translateY\(y\) | 이동\(Y축\) | 단위 |
| scale\(x,y\) | 크기\(X축,Y축\) | 없음\(배수\) |
| scaleX\(x\) | 크기\(X축\) | 없음\(배수\) |
| scaleY\(y\) | 크기\(Y축\) | 없음\(배수\) |
| rotate\(degree\) | 회전\(각도\) | deg |
| skew\(x-deg,y-deg\) | 기울임\(X축,Y축\) | deg |
| skewX\(x\) | 기울임\(X축\) | deg |
| skewY\(y\) | 기울임\(Y축\) | deg |
| metrix\(n,n,n,n,n,n\) | 2차원 변형 효과 | 없음 |

position은 배치후 끝내는 개념이라면

translate는 애니메이션에 최적화되어있음

```css
.box{
  width: 200px;
  height: 200px;
  background: tomato;
  margin: 50px;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 30px;
  transition: 1s;
  }
.box:hover{
  transform: translate(100px,100px); 
/*   왼쪽아래로 50px */
  transform: scale(2);
/*   크기 2배 */
  transform: skewX(20deg);
/*   X축으로 20도 비틀기(마름모 만들기) */
}
```



### **3D변환 함수**

| translate3d\(x,y,z\) | 이동\(X,Y,Z축\) | 단위 |
| :--- | :--- | :--- |
| translateZ\(z\) | 이동\(Z축\) | 단위 |
| scale3d\(x,y,z\) | 크기\(X,Y,Z축\) | 없음\(배수\) |
| scaleZ\(z\) | 크기\(Z축\) | 없음\(배수\) |
| rotate3d\(x,z,z,a\) | 회전\(X벡터,Y벡터,Z벡터,각도\) | 없음,deg |
| rotateX\(x\) | 회전\(X축\) | deg |
| rotateY\(y\) | 회전\(Y축\) | deg |
| rotateZ\(z\) | 회전\(Z축\) | deg |
| perspective\(n\) | 원근법\(거리\) | 단위 |
| matrix3d\(n\) | 3차원변환효과 | 없음 |

![](../.gitbook/assets/image%20%285%29.png)



## **transform변환 속성**

| transform-origin | 요소 변환의 기준점을 설정 |
| :--- | :--- |
| transform-style | 3D 변환 요소의 자식 요소도 3D 변환을 사용할지 설정 \(원래 자식은 안됌\) |
| perspective | 하위 요소를 관찰하는 원근 거리를 설정 |
| perspective-origin | 원근 거리의 기준점을 설정 |
| backface-visibility | 3D변환으로 회전된 요소의 뒷면 숨김을 설정 |



### **transform-origin**

요소 변환의 기준점을 설정

| X축 | left,right,center,%,단위 | 50% 기본값 |
| :--- | :--- | :--- |
| Y축 | top,bottom,center,%,단위 | 50% |
| Z축 | 단위 | 0 |

```css
img{
  width: 300px;
  border: 2px solid blue;
  transition: 1s;
  transform: rotate(45deg);
  transform-origin: 100% 100%;
/*   우측 하단 기준으로 회전 bottom right으로 대체가능 */
}
```



### **transform-style**

3D 변환 요소의 자식 요소도 3D 변환을 사용할지 설정

| flat\(기본값\) | 자식요소의 3D변환을 사용하지 않음 |
| :--- | :--- |
| preserve-3d | 자식요소에 3D변환을 사용함 |

![](../.gitbook/assets/image%20%2820%29.png)



### **perspective**

하위요소를 관찰하는 원근 거리를 설정

| 단위 | px,em,cm등 단위로 지정 |  |
| :--- | :--- | :--- |


**perspective속성과 함수의 차이점**

| 속성/함수 | 적용대상 | 기준점 설정 |
| :--- | :--- | :--- |
| perspective | 관찰대상의 부모요소 \(여러개\) | perspective-origin |
| transform:perspective\(\) | 관찰대상 \(1개\) | transform-origin |

### \*\*\*\*

### **perspective-origin**

원근거리의 기준점을 설정

| X축 | left,right,center,%,단위 | 50% 기본값 |
| :--- | :--- | :--- |
| Y축 | top,bottom,center,%,단위 | 50% |



```markup
<div class="perspective">
  <div class="grandparent">
    <div class="parent">
      <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/3/3d/CSS.3.svg/1200px-CSS.3.svg.png" alt="1">
    </div>
  </div>
</div>

```

```css
.perspective{
  margin: 100px 0px 0px 60px;
  width: 200px;   /* 넓이를 일치시켜주는게 좋다 */
  perspective:500px;
    perspective-origin: 50% 50%
/*       perspective 클래스의 중앙에서 바라본다 */
}

.grandparent{
  width: 200px;
  transition: 1s;
  border: 3px solid dodgerblue;
  transform: rotateX(-45deg);
  transform-style: preserve-3d;  /*자식요소에도 3D효과를 가능하게함*/
}

.parent{
  width: 200px;
  border: 3px solid tomato;
  transition:1s;
  transform: rotateY(45deg);
  transform-style: preserve-3d;  /*자식요소에도 3D효과를 가능하게함*/
}

img{
  width: 200px;
  border: 3px solid lightgrey;
  transition:1s;
  transform: rotateX(45deg);
}
```

![&#xC774;&#xB7EC;&#xD55C; &#xACB0;&#xACFC;&#xAC00; &#xB098;&#xC628;&#xB2E4;.](../.gitbook/assets/image%20%2863%29.png)



### **backface-visivility**

3D변환으로 회전된 요소의 뒷면 숨김을 설정 \(보기보다 유용\)

| visible | 뒷면을 숨기지 않음 |
| :--- | :--- |
| hidden | 뒷면을 숨김 |

![&#xC774;&#xCC98;&#xB7FC; &#xD558;&#xB098;&#xB294; hidden&#xC744; &#xC0AC;&#xC6A9;&#xD55C; &#xD558;&#xB098;&#xB294; &#xB4A4;&#xAC00; &#xB098;&#xC624;&#xC9C0; &#xC54A;&#xB294;&#xB2E4;.](../.gitbook/assets/image%20%2852%29.png)



### **matrix\(a,b,c,d,e,f\)**

요소의 2차원 변환\(Transforms\)효과를 지정

scale\(\), skew\(\), translate\(\) 그리고 rotate를 지정

 - 요소에 일반변환함수를 사용해도 브라우저에 의해 matrix함수로 계산되어 적용된다.

​_일반적인 상황에는 일반변환함수를 사용하면 된다._

