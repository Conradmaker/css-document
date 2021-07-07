# 기본 클래스 선택자

## **기본선택자**

### **1.전체선택자\(Universal Selector\)**

전체 영역에 css를 적용합니다.

 `*` 기호를 이용

```css
*{
    color:red;
}
```



### **2.태그 선택자\(Type Selector\)**

 **태그**이름이 ~ 인 요소를 선택하겠다는 의미입니다.

```css
li {
    color: red;
}
```

### \*\*\*\*

### **3.클래스 선택자&lt;Class Seletor\)**

**클래스**이름이 ~ 인 요소를 선택하겠다는 의미입니다.

`.`을 사용

```css
.orange {
    color: red;
}
```



### **4.아이디 선택자\(ID Selector\)**

**ID**이름이 ~ 인 요소를 선택하겠다는 의미입니다.

[`#`을](https://blog.naver.com/PostListByTagName.nhn?blogId=yhg0337&encodedTagName=%EC%9D%84) 사용 \(classs와 달리 고유한 부분에 사용합니다.\)

```css
#orange {
    color: red;
}
```



## **복합선택자**

### \*\*\*\*

### **1.일치 선택자\(Basic Combinator\)**

`EF`      ****`E`와`F`를 동시에 만족하는 요소 선택하겠다는 의미입니다.

```css
span.orange {       /* 태그선택자+클래스선택자 */
    color: red;     /*span태그안에 오랜지 클래스*/
}
```



### **2.자식 선택자\(Child Combinator\)**

`E > F`    `E`의 자식요소 `F`를 선택하겠다는 의미입니다.

```css
ul > .orange {       /* 태그선택자>클래스선택자 */
    color: red;      /* ul태그의 자식요소이자 orange클래스 */
}
```



### **3.후손\(하위\) 선택자\(Descendant Combinator\)**

​`E F`    `E`의 후손 요소 `F`를 선택하겠다는 의미입니다.

> 띄어쓰기가 기호이니 주의해주세요

```css
div .orange {       /* 태그선택자 클래스선택자 */
    color: red;     /* div태그의 후손요소이자 orange클래스 */
}
```



### **4.인접 형제 선택자\(Adjacent Sibling Combinator\)**

`E + F`    `E`의 다음 형제 요소 `F` 하나만 선택하겠다는 의미입니다.

```css
.orange + li {     
    color: red;    
}
```

```markup
<body>
 <ul>
     <li>사과</li>
     <li class="orange">포도</li>
     <li>망고</li>                 <!--선택 -->
 </ul>
</body>
```



### **5.일반 형제 선택자\(General Sibling Combinator\)**

`E~F`        `E`의 다음 형제 요소 `F` 모두 선택하겠다는 의미입니다.

```css
.orange ~ li {       
    color: red;    
}
```

```markup
<body>
 <ul>
     <li>사과</li>
     <li class="orange">포도</li>
     <li>망고</li>               <!--선택 -->
     <li>딸기</li>               <!--선택 -->
 </ul>
</body>
```





