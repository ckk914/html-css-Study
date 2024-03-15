
# relative

/* 텍스트 중앙 정렬 */<br>
    /* X축 중앙 정렬 */<br>
    text-align: center;
---
/* 세로 중앙정렬 방법1(하위호환용) */<br>
/* line-height: 100PX;  */<br>
 /*ㄴ이걸로도 세로 센터로 맞출 수 있음*/
---
 /* 세로 중앙정렬 방법2 */<br>
    display: flex;<br>
    justify-content: center;<br>
    align-items: center;
---
    /* vertical-align은 너무 옛날 */
---
 /* position : relative: <br>
 기존 자리 기준으로 이동함 */<br>
---
### 자신의 조상 중에
 ### 포지션이 있는 부모 기준으로
### 자식이 움직인다
---
*자식
position:Absolute;<br>
top: 30px; <br>
left: 50px;
---
# absolute
---
 position : relative: 기존 자리 기준으로 이동함 */
 ㄴ 부모에게 주로 세팅
 position: absolute;: z축으로 위로 뜸 3번한테 자리 빼앗김 */

 position: relative; 
    /*ㄴ 부모에 속성 부여*/

/* 절대 이동 */
  .abs {
    position: absolute;
    top: 20px;
    right: 20px;
  }
ㄴ 자식에 클래스 부여
---


```css
//부모 relative나 absolute나 상관없다
//       static 빼고
---
★ 자식 이동을 위할땐 relative만 쓴다!!
---
 position: relative;

//자식
  .abs {
    position: absolute;
    top: 20px;
    right: 20px;
  }
```
float걸면 꼭 클리어
---
  ### /* position absolute, fixed를 걸면 */
  ### /* width의 기본값 100%가 깨진다. */
  ###    width: 100%;
###      /* 언제나 브라우저 전체 기준으로 움직임 */
      position: fixed;

### position absolute 걸면
### width 100% 깨짐
### 다시걸어줘야함

---
 ### /* 인라인 요소에 float 이나 position 걸면 */
 ### /* position : absolute를 걸면  */
###  /* 자동으로 블록요소로 변경됨 */
### /* float: left만 해도 블록으로 됨*/
---
그림자 효과 주기
---
### /*          x축  y축  블러크기 색상 */
### box-shadow: 2px 2px 20px #000;
### text-shadow: 2px 2px 10px #000;
### /* text도 일치함 text-shadow */
### /* 블러 10px 주면 그림자 처럼 됨! */
### /* x,y축은 그림자 위치 */
      
---
스티키는 안좋으니 쓰지말고<br>
자바스크립트로 구현해라
---
요소 쌓임 순서 ★★
나중에 작성한 요소일수록 위에 쌓인다
---
position  : relative, absolute든 쓰면
요소가 맨위로 상승!
---
포지션이 존재하면
나중에 등록된 녀석이 제일 위로 간다
-------------------
규칙꺠고 돌연변이 z-index
---
z-index: 1
누군가 위로 올라오거나 내리거나 할때 사용함
얼마나 밖으로 나오느냐 
기본값 0 
ㄴ헤더가 숨을때 사용함
---
# 헤더는 값을 높게 준다
##  z-index:9999

```css
예)
    .box2{
      position: relative;
      left: 200px;
      /* z-index 기본값 0 */
      z-index: 1  //위로 상승
      z-index: -1  //다른요소보다 아래로 상승

    }
```
---
8장까지만 해도 된다
---
## 에니메이션은 너무 남발하면 오히려 보기 싫음

---
```css
.container .menu
{
  float: left;
  width: 20%;
}
```

## float width 안하면 배치가 안됨
## 부모에게 클리어 안해줘도 마찬가지
---
영역 별 주석을 잘 달아라
---
## begin container style

## 박스 큰 것 부터 배치 끝내고
## 잔잔바리는 그 다음에 살살 하면 된다.
---

## float 안될떄
### 클리어를 했나,
### 가로를 제한(설정)했나 확인

