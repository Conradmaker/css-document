# 가상 요소 선택자 / 속성 선택자

## 가상 요소 선택자

`::`콜론 두개를 이용해 사용합니다.

### 1.BEFORE

`E: :before`    `E`요소 **내부의 앞에, 내용\(content\)을 삽입**

> 내용이 있어야 하기 때문에  content속성이 필수입니다. \(내용이 없다면 " "을 사용\)

```css
ul li::before{
  content: "숫자";
  font-weight: bold;
  color: red;
  margin-right: 2px;
}



<body>
<!-- ul>li{$}*5 -->
<ul>
    <li>1</li>
    <li>2</li>
    <li>3</li>
    <li>4</li>
    <li>5</li>
</ul>
</body>
```

![&#xC774;&#xB7F0; &#xBAA8;&#xC591;&#xC73C;&#xB85C; &#xB098;&#xC624;&#xACA0;&#xC8E0;?](../.gitbook/assets/image%20%2828%29.png)

### 2.AFTER

`E::after`      E요소의 내부 뒤에 내용을 삽입

`::before`과 사용법은 동일합니다.

```css
ul li::after{
  content: url("이미지");
  font-weight: bold;
  color: red;
  margin-right: 2px;
}
```





## 속성선택

### 1.ATTR

`[attr]` **속성 attr을 포함한 요소** 선택

```css
[disabled]{
    opacity: 0.2;
    color: red;
}

/* disabled 속성을 가진 태그를 선택 */
```

```markup
<body>
<input type="text" value="yhg">
<input type="password" value="1234">
<input type="text" valaue="disabled" disabled>  //선택!
</body>
```



### 2.ATTR=VALUE

`[attr=value]`     **속성attr을 포함하며 속성값이 value인 요소** 선택

```css
[type=password]{
    opacity: 0.2;
    color: red;
}

/* type="password" 속성 선택 */
```

```markup
<body>
<input type="text" value="yhg">
<input type="password" value="1234">    //선택!
<input type="text" valaue="disabled" disabled>
</body>
```



### 3.ATTR^=VALUE

`[attr^=value]`       **속성 attr을 포함하며 속성값이 value로 시작하는 요소** 선택

```css
[class^="btn-"]{
    font-weight: bold;
    border-radius: 20px;
}
/* class속성중 btn-으로 시작하는 속성값 가진 태그들 선택 */
```

```markup
<body>
 <button class="btn-success">succes</button>  //선택
 <button class="btn-danger">danger</button>   //선택
 <button>normal</button>
</body>
```



### 4.ATTR$=VALUE

`[attr$=value]`     **속성 attr을 포함하며 속성값이 value로 끝나는 것** 선택

```css
[class$="success"]{
    color:green;
}
[class$="danger"]{
    color:red;
}
```

```markup
<body>
 <button class="btn-success">succes</button>     //녹색으로
 <button class="btn-danger">danger</button>      //빨강색으로
 <button>normal</button>
</body>
```



지금까지 선택자를 모두 알아보았습니다!!

