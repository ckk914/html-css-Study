
---
# 3장 - Box 속성

## 단위

### px, % 픽셀
<pre>
- px 단위는 픽셀이라는 뜻이며 
화면에 **고정적인 길이**를 의미하며 
  절대적인 수치를 의미합니다.

- 1px은 디바이스마다 
고정크기가 다를 수 있습니다.

- % 단위는 **부모요소 대비 비율**적 영향을 받습니다.
</pre>

---
## em, rem
<pre>
- em 단위는 **요소 자기 자신의 
font-size**에 영향을 받습니다.

- 예를 들어 h1태그의 font-size를 
   10px로 지정하고
    width를 5em으로 지정하면
     가로 길이는  5 x 10px의 50px이 됩니다.

- rem단위는 **html태그에서
 지정한 font-size**에 영향을 받습니다.

- html태그에는 기본값으로 16px이
   정의되어 있습니다. 
    라서 따로 font-size를 조절하지 않으면 
    2rem은 32px이됩니다.
 
/* 16px *40 = 640px */
width: 40em;
em이 상자 사이즈에 영향을 줌
★em은 실무에서 잘 안씀
ㄴrem을 씀

이런식으로 써서 rem 을 계산하기 편하게 10px로 맞춤
html{
font-size: 10px; //계산용
}
body{
margin: 0;
padding: 0;
font-size: 18px; //실제 적용값
}
</pre>
--

## vw

viewport = 디바이스화면

body의 콘텐츠가 없으면 세로 0 임
가로는 원래 잡혀있음

---
### vw, vh
  (화면 전체 크기임)%와 유사함 h는 내용 없으면 표시가 안되는데
   vh를 쓰면 화면에 박스가 보임


<pre>
- vw, vh 단위는 **뷰포트(디바이스 화면)를 기준**으로
 설정되는 길이 단위이며,
  0~100사이의 값을 가집니다.

- vw는 width를 지정할 때 사용하며, 
vh는 height를 지정할 때 사용합니다.

- 뷰포트란?
 화면 전체 크기를 의미하며
  만약 어떤 이미지의 높이값을 100vh로 지정하면 
  데스크탑 화면이든 태블릿, 모바일 
  화면과 관계없이 높이가 
  화면 전체를 꽉 채우게 됩니다.

---
비유
자바=라면 
스프링=밀키트
잘 배우면 할 수 있음.
---

width: auto;   // with: 100% 와 같음 (기본값)

height: auto;  // 세로는 height : 0임. (기본값)
ㄴ세로를 그래서 지정해야 보임

콘텐츠 없을때,
세로 지정 안하면 아예 안보임
</pre>
---
height: 50%; 부모 대비 크기
---
<pre>
max-width/height
 어느정도 늘어나서 max걸리면 
 스크롤만 생김
(예)쇼핑몰 장바구니, to-do 리스트 스크롤

min-width/height
</pre>
---
## 마진  : 바깥쪽 여백이다/.
<pre>
네이버에서
메일과 아이콘 과의 거리
div 박스와 뉴스스탠드와 거리
三 N 사이 간격  다 마진임

w25p  : width:25%
w25r   : width:25rem
w25e  : width:25em

margin: 5px;
/* 
마진만 쓰면 전부 4방향 5px씩 추가됨.
 */


       /*상하 좌우  */
margin: 20px 10px;
        /*상  좌우   하  */
margin: 20px 10px 30px;
      /* 상    우  하   좌 */
margin: 20px 10px 30px 15px;
</pre>
---

마진 나누기
---
<pre>
부모 있고
자식일때
	section h1{
		width: 50%;     
		border:4px solid violet;
		text-align: center;
		margin-left: 25%;
		margin-right: 25%;
	}
  
^ section 의 절반
  		width: 50%;     

^ 반반씩 적절히 나눔
  margin-left: 25%; 
		margin-right: 25%;
</pre>
---
<pre>
width: 70%;
border:4px solid violet;
text-align: center;
 // LR을 스스로 계산하여
 // 적절히 분배하여 가운데 값이 오도록 함
margin-left: auto;   // auto
margin-right: auto;  // auto
                ㄴmargin: 0 auto; 
                //같은 코드인데 쉽게 간략화
</pre>

---

```html
	section h2{
 //width 이렇게 안하면
 // 가로를 끝까지 다 먹어서
// 마진 분배를 통해 박스 x축 정렬을
//   하려면 가로 길이가 100%면
//   여유 마진이 없어서 분배를 못하므로
//   정렬이 안된다.
---
		width: 50%;                  
		background: #000;
		margin: 10px auto;
		text-align: center;

	}
```
---
<pre>
fit-content는 알아서 잘 계산하도록하는 키워드임!
		width: fit-content;
		background: #000;
		margin: 10px auto;
		text-align: center;
    </pre>

---


## 패딩 : 안쪽 여백
<pre>
패딩을 쓰면 박스가 커짐
(=패딩 입으면 몸이 커지잖슴)

width + 패딩 사이즈
height + 패딩 사이즈
패딩 추가된 값을 원래 값에서 빼라
500이었으면 좌우 50,50 이면 width 400
ㄴbox-sizing: border-box;
  // 위에 패딩 으로 인해 늘어난 width를
     마치 안늘어난 것 처럼
  // 사이즈를 알아서 잘 조절함
  ★ 패딩쓰면 box-sizing 무조건 써라
  </pre>
---

###  ★실무에서는 헷갈리니까 
### 위에다가 그냥 선언해둔다.
```css
*{
		box-sizing: border-box;
 }
```
------------------
###  패딩 넣을때 마다 넣을라면 헷갈리기 떄문.!
         
---
★★굉장히 많이 쓰는 디자인 (카드 스타일)
```html
	<div class="card">
		<div class="image">
			<img src="" alt="">
		</div>
		<p class="content">
			텍스트
		</p>
	</div>
```

    //모서리를 경계를 둥글게 만들어라
	border-radius: 15px; 


---

### 마진 패딩 상황에 맞게 잘 써라
### 폴라로이드 사진 같이 만들때는 패딩

---

### 이미지 핏하게 맞추는 방법
### 	.card .image img{
### 		height: 100%;
###   }
이미지의 가로가 더 길면 가로 100% <Br>
이미지의 세로가 더 길면 세로 100%


### border도 테두리가 width+테두리 크기
### ㄴbox-sizing: border-box; 해줘야 크기 고정됨 
원래 width값으로 가만히 있게

### border도 몸집이 뚱뚱해진다~!!
---

### border-width: 10px; /*선굵기*/
### border-style:solid; /*선모양*/
### border-color: orange;/*선색*/
---

 border-radius: 50%;
둥글게 그림
