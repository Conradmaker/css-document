# Grid - Basic



CSS Grid\(그리드\)는 2차원\(행과 열\)의 레이아웃 시스템을 제공합니다.

Flexible Box도 훌륭하지만 비교적 단순한 1차원 레이아웃을 위하며, 좀 더 복잡한 레이아웃을 위해 우리는 CSS Grid를 사용할 수 있습니다.

> CSS Grid는 예전부터 핵\(Hack\)으로 불린 다양한
>
>  레이아웃 대체 방식들을 해결하기 위해 만들어진 특별한 CSS 모듈입니다.

## **CSS Grid**

CSS Grid의 효율적인 학습을 위해서 [파이어폭스 브라우저](https://www.mozilla.org/ko/firefox/new/)를 사용해 테스트할 것을 추천합니다.

개발자 도구를 열고 요소를 검색해 표시된 **grid** 버튼을 선택합니다.

![](../.gitbook/assets/image%20%2870%29.png)

### **Grid Properties**

CSS Grid는 [CSS Flex](https://heropy.blog/2018/11/24/css-flexible-box/)와 같이 Container\(컨테이너\)와 Item\(아이템\)이라는 

두 가지 개념으로 구분되어 있습니다.

Container는 Items를 감싸는 부모 요소이며, 그 안에서 각 Item을 배치할 수 있습니다.





### **Grid Container Properties**

Grid Container를 위한 속성들은 다음과 같습니다.

| **속성** | **의미** |
| :--- | :--- |
| display | 그리드 컨테이너\(Container\)를 정의 |
| grid-template-rows | 명시적 행\(Track\)의 크기를 정의 |
| grid-template-columns | 명시적 열\(Track\)의 크기를 정의 |
| grid-template-areas | 영역\(Area\) 이름을 참조해 템플릿 생성 |
| grid-template | **grid-template-xxx**의 단축 속성 |
| row-gap\(grid-row-gap\) | 행과 행 사이의 간격\(Line\)을 정의 |
| column-gap\(grid-column-gap\) | 열과 열 사이의 간격\(Line\)을 정의 |
| gap\(grid-gap\) | **xxx-gap**의 단축 속성 |
| grid-auto-rows | 암시적인 행\(Track\)의 크기를 정의 |
| grid-auto-columns | 암시적인 열\(Track\)의 크기를 정의 |
| grid-auto-flow | 자동 배치 알고리즘 방식을 정의 |
| grid | **grid-template-xxx**과 **grid-auto-xxx**의 단축 속성 |
| align-content | 그리드 콘텐츠\(Grid Contents\)를 수직\(열 축\) 정렬 |
| justify-content | 그리드 콘텐츠를 수평\(행 축\) 정렬 |
| place-content | **align-content**와 **justify-content**의 단축 속성 |
| align-items | 그리드 아이템\(Items\)들을 수직\(열 축\) 정렬 |
| justify-items | 그리드 아이템들을 수평\(행 축\) 정렬 |
| place-items | **align-items**와 **justify-items**의 단축 속성 |

### \*\*\*\*

### **Grid Item Properties**

Grid Item을 위한 속성들은 다음과 같습니다.

| **속성** | **의미** |
| :--- | :--- |
| grid-row-start | 그리드 아이템\(Item\)의 행 시작 위치 지정 |
| grid-row-end | 그리드 아이템의 행 끝 위치 지정 |
| grid-row | **grid-row-xxx**의 단축 속성\(행 시작/끝 위치\) |
| grid-column-start | 그리드 아이템의 열 시작 위치 지정 |
| grid-column-end | 그리드 아이템의 열 끝 위치 지정 |
| grid-column | **grid-column-xxx**의 단축 속성\(열 시작/끝 위치\) |
| grid-area | 영역\(Area\) 이름을 설정하거나, **grid-row**와 **grid-column**의 단축 속성 |
| align-self | 단일 그리드 아이템을 수직\(열 축\) 정렬 |
| justify-self | 단일 그리드 아이템을 수평\(행 축\) 정렬 |
| place-self | **align-self**와 **justify-self**의 단축 속성 |
| order | 그리드 아이템의 배치 순서를 지정 |
| z-index | 그리드 아이템의 쌓이는 순서를 지정 |



