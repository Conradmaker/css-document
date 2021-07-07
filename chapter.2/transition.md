# 전환 \(Transition\)

## transition

CSS속성의 시작과 끝을 지정\(전환효과\)하여 중간 값을 애니메이션 \*단축속성\*

| transition-property | 전환효과를 사용할 속성 이름 | all |
| :--- | :--- | :--- |
| transition-duration | 전환효과 지속시간 | 0s \(1s / .5s\) |
| transition-timing-function | 타이밍 함수 지정 | ease |
| transition-delay | 전환 효과의 대기시간 설정 | 0s |

```css
.box{
  width: 100px;
  height: 100px;
  background: tomato;
  margin: 50px;
  transition: width 1s,background 1s;
/* =  transition-property: width background;
      transition-duration: 1s;; */
}
.box:hover{
  width: 300px;
  background: dodgerblue;
} 
```



### transition-property

전환효과를 사용할 속성 이름

| all \(기본값\) | 모든 속성에 적용 |
| :--- | :--- |
| 속성이름 | 전환효과를 사용할 속성이름 |



### transition-duration

전환효과 지속시간

| 시간 | 전환효과가 지속되는 시간 | 1s |
| :--- | :--- | :--- |




### transition-timing-function

타이밍 함수 \(애니메이션 전환 효과를 계산하는 방법\) 지정

| ease | 빠르게-느리게 |
| :--- | :--- |
| linear | 일정하게 |
| ease-in | 느리게-빠르게 |
| ease-out | 빠르게 느리게 |
| ease-in-out | 느리게-빠르게-느리게 |
| cubic-bezier\(n,n,n,n\) | 자신만의 값을 정의\(0~1\) |
| steps\(n\) | n번 분할된 애니메이션 |

### 

### 다양한 ease함수들

[https://easings.net/](https://easings.net/)  


