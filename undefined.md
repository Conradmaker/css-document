# 상속 / 우선순위

## 상속

 보통 글자를 가진 속성들이 상속됩니다.   


```css
.ecosystem {
    color: red;
}

/* ecosystem 클래스를 가진 태그들이 하위요소까지 모두 적용 */
```

```markup
<body>
    <div class="ecosystem">생태계
        <div class="animal">동물
            <div class="tiger">호랑이</div>
        </div>            
    </div>    
</body>
```

 추가적으로 상속이 되지 않는 속성도 있겠죠? 그럴경우에

```css
.ecosystem {
    position: absolute; /*상속되지 않는 속성과 값 */
}

.ecosystem {
    position: inherit;   /*강제 상속받아 position: absolute;와 동일 */
}

```

상속되지 않는 속성\(값\)도 `inherit` 이라는 값을 사용하여 **'부모'에서 '자식'**으로 강제 상속시킬수 있습니다.

단, 주의점이 있습니다.

{% hint style="danger" %}
* '자식'이 아닌 '후손' 에게는 적용되지 않습니다.
* 모든 속성이 강제상속을 사용할 수 있는것은 아닙니다.
{% endhint %}

## 우선순위

같은 요소가 여러 선언의 대상이 될 경우, 어떤 선언의 CSS속성을 우선 적용할지 결정하는 방법입니다.

​이럴경우 아래의 방법대로 계산을 해서 스타일을 적용시켜 줍니다.

 1.명시도 점수가 높은 선언이 우선 \(명시도\)

 2.점수가 같은 경우, 가장 마지막에 해석\(늦게 작성한\)되는 선언이 우선 \(선언순서\)

 3.명시도는 '상속'받은 규칙보다 우선 \(중요도\)

 4.!important가 선언된 방식이 다른 모든 방식보다 우선 \(중요도\)

그럼 이제 명시도 점수에 대하여 알아보겠습니다.

### 

### 1.가장중요\(!important\)

모든 선언을 무시하고 가장 우선

```css
div{
    color:red !important;
}
```

### 

### 2.인라인 선언 방식\(Style Attribute\)

점수:1000pt

```markup
<div style="color:red;"></div> 
```

인라인 선언 방식의 경우에는 _점수가 너무 높아서 주의_ 해야 _합니다._

### 

### 3.아이디\(ID Selector\) 

점수: 100pt

```css
#123{
    color:red;
}
```

### 

### 4.클래스\(class Selector\) 

점수:10pt

```css
.123{
    color:red;
}
```



### 5.태그\(Type Selector\) 

점수:1pt

```css
div{
    color:red;
}
```



### 6.전체\(Universal Selector\) 

점수:0pt

```css
*{
    color:red;
}
```



### 7.상속\(CSS Inheritance\)

 상속받은 선택자는 점수를 계산하지 않습니다. 0pt



자, 그럼 한번 예시를 볼까요?

```css
.list li.item     21pt
.list li:hover    21pt
.box::before      11pt
#submit span      101
header.menu li:nth-child(2)  22
:not(.box)        10  not은 점수X
```

