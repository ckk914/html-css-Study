
---
레이아웃
---
## 박스 배치
# float : 전통 방식
     ㄴ고전이지만 많이 씀
---
## div로 만들면 기본 그냥 수직 배치임


width: 700px;<br>
height: auto;  
//알아서 width 늘어난 만큼 비례해서
  늘어난 만큼 늘어남

---
## 리팩토링 <= (추천도서)

---
#ccaaaa => #caa   두개씩 묶어서 rgb임

---
# float
---
```css
//각각 자식들인데 float 속성 적용
.box
{
/* 박스 수평 배치 - 브라우저 공간 없음 밑으로 내려감*/
/* left 왼쪽부터아래로, right 오른쪽부터 아래로 */
float: left;      /*right 이면 clear도 right*/
}
```

```css
/* float 항상 3행 3열 만들기 */
	/* .box:nth-child(4),.box.box:nth-child(7) */

	/* 3열  3n+1 
     4열 4n+!
     5열 5n+1 */
	/* x열 xn+1 */
	.box:nth-child(3n+1)
	{
		/* 강제 줄바꿈 같은 느낌 */
		/* 수평 배치 해제 */
clear: both;  /*L,R 상관없이 다 알아서 클리어 함*/
	}

.........

/* 가상 클래스 - 다른 클래스에서 쓸 수 있게 클래스를 만들어서*/ 
/* 돌려쓴다 (해제가 필요한 부모에게 붙인다.)*/
.clearfix::after{
content: '';   /*after 쓰면 무조건 넣어야함*/
display: block; /*여기도 필수*/
clear: both;    /*여기도 필수*/
}

//부모의 클래스에 추가해줘서 사용 자식들은 float:left;
<div class="ct container1 clearfix">


## 리셋 css 적용
[common.css]  //공통 css
/* 공통css 적는 파일 */
/* css 파일이 다른 css 파일을 불러오는 것*/
@import url('https://cdn.jsdelivr.net/npm/reset-css@5.0.2/reset.min.css');
/*  ㄴ 리셋 css */

---
다른 css
@import url('../Css-study/common.css');
ㄴ 이런식으로 다른 css를 불러준다

```