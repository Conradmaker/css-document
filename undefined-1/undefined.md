# 기본환경

### css초기

우리는 화면을 마음대로 꾸미고 싶지만 css는 이미 여러가지가 정해져 있죠?

예를들면 h태그의 글씨크기 처럼 말입니다.

그래서 css를 초기화해줄 필요가 있는데 cdn을 찾아 html문서에 넣어줄거에요

```markup
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/reset-css@5.0.1/reset.min.css">
```

_항상 css외부 링크의 첫번째가 되어야 한다._

\_\_

### 준비물

codepen.io 아니면 Sandbox와 같은 홈페이지에서는 

마음대로 css를 작업하고 즉시 결과를 확인할 수 있습니다! 



### emmet 문법

emmet 문법을 활용하면 더 빠르게 코드를 입력하실 수 있습니다

예를 들어볼까요?

```markup
<body>
    <!-- .box -->
   <div class="box"></div>

   <!-- ul.list -->
   <ul class="list"></ul>
   
   <!-- .container>ul.list>li.list-item*10>a{list$} -->
   <div class="container">
       <ul class="list">
           <li class="list-item"><a href="">list1</a></li>
           <li class="list-item"><a href="">list2</a></li>
           <li class="list-item"><a href="">list3</a></li>
           <li class="list-item"><a href="">list4</a></li>
           <li class="list-item"><a href="">list5</a></li>
           <li class="list-item"><a href="">list6</a></li>
           <li class="list-item"><a href="">list7</a></li>
           <li class="list-item"><a href="">list8</a></li>
           <li class="list-item"><a href="">list9</a></li>
           <li class="list-item"><a href="">list10</a></li>
       </ul>
   </div>
</body>
```

```css
.box {
    /* w100 */
    width: 100px;
    /* h100 */
    height: 100px;
    /* h100% */
    height: 100%;
    /* m100 */
    margin: 100px;
    padding: 100px;
    /* pt100 */
    padding-top: 100px;
}
```

\_\_

