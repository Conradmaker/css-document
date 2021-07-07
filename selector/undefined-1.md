---
description: (Pseudo-Classes Selector)
---

# 가상 클래스 선택자

## **가상 클래스** **선택자\(Pseudo-Classes Selector\)**

`:` 콜론기호 1개 사용해 사용합니다.  


### 1.HOVER

`E:hover` `E`에 **마우스가 올라가 있는동안**에만 `E`선택

```css
.box:hover {
   width: 100px;
   height: 100px;
   background: tomato;
   transition: 0.4s;
}
.box:hover{
    width:200px;
}
/* box클래스에 커서를 올리면 가로가 100px에서 0.4초만에 200px로 확장 */
```



### 2.ACTIVE

`E:active` `E`를 **마우스로 클릭하는 동안**만 `E`선택  


```css
.box{
   width: 100px;
   height: 100px;
   background: tomato;
   transition: 0.4s;
}
.box:active{
    width:200px;
    background: yellowgreen;
}
/* box클래스에 클릭하는동안에만 가로가 100px에서 0.4초만에 200px로 확장하고 색변경 */
```



### 3.FOCUS

`E:focus` `E`가 **포커스 된 동안**에만 `E` 선택

> input요소 즉, 대화형 콘텐츠에서 사용 가능합니다.

```css
.box{
   width: 100px;
   outline: none;
   border: 1px solid lightgray;
   padding: 5px 10px;
   transition: 0.4s;
}
.box:focus{
   border-color: red;
   width:200px
}
/* box클래스에 포커스동안에 가로가 100px에서 0.4초만에 200px로 확장하고 태두리색변경 */
```



### 4.FIRST CHILD / LAST CHILD

`E:first-child`     `E`가 **형제요소 중 첫번째 요소**라면 선택

`E:last-child`     `E`가 **형제요소 중 마지막 요소**라면 선택

```css
.fruits li:first-child{
    color:red;
}
/* fruits클래스의 자식요소 li중 첫번째 요소에 적용 */


.fruits li:last-child{
    color:red;
}
/* fruits클래스의 자식요소 li중 마지막 요소에 적용 */
```



### 5.NTH CHILD

`E:nth-child(n)`      `E`가 **형제요소중 N번째 요소라면** 선택 \(n사용시 0부터 해석 zero-base\)

```css
.fruits li:nth-child(2n){
    color:red;
}
/*2의 배수 (짝수선택)*/

.fruits li:nth-child(n+3){
    color:red;
}
/*3이후의 수 선택*/
```

그렇다면 다음 상황에는 어떻게 적용될까요?

```css
.fruits li:nth-child(1){
    color:red;
}
```

```css
<body>
<div class="fruits">
    <div>딸기</div>
    <p>사과</p>
    <p>망고</p>
    <span>오렌지</span>
</div>
</body>
```

_**이경우에는 자식요소가 p가 아니기 때문에 선택되지 않습니다.**_

_\*\*\*\*_

### 6.NTH OF TYPE

`E:nth-of-type(n)`    `E`의 타입과 **동일한 타입인 형제요소중** `E`**가 n번쨰 요소**라면 선택

```markup
.fruits p:nth-of-type(2){
    color:red;
}

<body>
<div class="fruits">
    <div>딸기</div>
    <p>사과</p>
    <p>망고</p>
    <span>오렌지</span>
</div>
</body>

/* 2번째 자식요소중 p태그 선택 */
```



### 7.부정 선택자\(Negation Selector\)

`E:not(s)`      `S`가 아닌 `E` 선택

```markup
.fruits li:not(.strawberry){
    color:red;
}


<body>
<ul class="fruits">
    <li class="strawberry">딸기</li>
    <li>사과</li>
    <li>망고</li>
    <li>오렌지</li>
</ul>
</body>

/* strawberry클래스를 제외한 li태그에 적용 */
```

​

