# TIL
Today I Learned

**질문**

GitHub 저장소는 온라인? 그럼 내 컴퓨터의 공간에 저장된 저장소는 로컬인가요?

<details>
  <summary>0일차 학습</summary>

  - GitHub 계정 생성
  - GitHub 저장소 생성
  - GitKraken 설치
  - GitKraken을 사용하여 GitHub 저장소 데이터를 내 컴퓨터로 복제(Clone)

  </details>



## 구조 디자인(HTML)
<details>
	<summary>1일차 학습</summary>

#### [HTML 이란?]

- HTML은 HyperText Markup Language로 구조를 설정할 때 사용하는 언어임
- 하이퍼링크 시스템을 가지고 있음
- 확장자 : .html

#### [시멘틱 마크업]
- 시멘틱 마크업(Semantic Markup)은 비주얼 디자인(모양, 색, 크기 등)이 목표가 아니라, 구조 설계(Structure Design)를 목표로 합니다
```html
<h1></h1> <!--제목 heading-->
<p></p> <!--단락 paragraph-->
```

#### [기본 문법]

- element : tag name / attribute name, value
- <여는 태그> 컨텐츠 </닫는 태그>
- <태그이름 속성="값"> 컨텐츠 </태그이름>
- (참고) 페이지 검사 -> console -> document.characterSet -> 문자 인코딩 반환 (UTF-8)
```html
<html>
	<head>
	<meta charset="utf-8">
		<title>HTML 문서 작성을 위한 기본 문법</title>
	</head>
	<body>
		<p title="Development"> 개발 도구(DevTools)</p>
	</body>
</html>
```

#### [텅 빈 요소]

- meta는 컨텐츠를 감싸지 않아 닫는 태그를 가지지 않음.
- 이를 Empty Element라고 함.

#### [표준 호환모드]

- html(root)는 자식을 둘 가지며 그 자식은 head와 body임. 
- head와 body는 각각 다른 성질의 자식들을 가질 수 있음. 

- DTD : 문서 유형 정의(Document Type Definition)
```html
<!DOCTYPE html> <!--웹표준문서-->
```

#### [주 언어 설정]

```html
<html lang="ko-KR"> <!--ko/en/es/ja 등..-->
```
- KR : Republic of Korea 지역(locale) 정보. ko 만 사용하면 한국어를 통칭
- (참고) en-GB ⇒ 영국 영어 / en-US ⇒ 미국 영어 / en-CA ⇒ 캐나다 영어

#### [제목과 단락]

- 제목 레벨(Level): 1 ~ 6단계에서 1단계는 문서에서 하나만 작성가능, 2단계부터는 여러개의 제목을 사용할 수 있음

```html
<h1>제목 1</h1> <!-- 문서에서 단 1회만 사용 (HTML5 표준 부터는 섹션 콘텐츠 마다 사용 가능) -->
<h1>제목 2</h1>
<h1>제목 3</h1>
<h1>제목 4</h1>
<h1>제목 5</h1>
<h1>제목 6</h1>

<!--주석-->

<p>단락</p>
```

#### [이미지와 피규어]

- img : image 태그
- figure : 이미지, 차트, 도표 등을 감싸는 태그
- alt(alternative) : 대체텍스트, 이미지를 분석하여 묘사할것.

```html
<figure>
  <img src="" alt="대체 텍스트">
  <figcaption>이미지 출처 등 캡션</figcaption>
</figure>
```

#### [문법 검사]
- validator.w3.org : 문법 유효성 검사
- entitycode.com : entitycode

```html
&lt; &gt; &copy; &midot; &nbsp; &amp;
```

#### [순차/비순차 목록]

- ul : unordered lists 비순차 목록
- ol : ordered lists 순차 목록
- li : list Item

</details>

<details>
	<summary>2일차 학습</summary>

#### [앵커와 하이퍼링크]

- anchor : 현재 페이지에서 위치 이동
- hyperlink : 다른 창으로 이동
- target= "＿blank" : 새창(새탭)열림
- href="mailto:" : 이메일 링크

```html
<!--anchor-->
<a href="#intro">소개</a>
<h3 id="intro">소개</h3><!-- 위 링크를 누르면 여기로 이동 -->
<!--hyperlink-->
<a href="http://naver.com" target="_blank">
  <img src="img경로" alt="NAVER logo" />네이버
</a>
```

#### [설명 목록]

- dl : 설명목록(Description lists)
- dt : 용어(Definition Term)
- dd : 설명(Definition Description)

```html
<dl>
  <!--1-->
  <dt>용어</dt>
  <dd>설명</dd>
  <!--2-->
  <dt>용어</dt>
  <dt>용어</dt>
  <dt>용어</dt>
  <dd>설명</dd>
  <!--3-->
  <dt>용어</dt>
  <dd>설명</dd>
  <dd>설명</dd>
  <dd>설명</dd>
</dl>
```

#### [인용과 줄 바꿈]
- q (quote) : 짧은 인라인 인용문. ("") 사용가능 / 강조용으로 쓰인 경우 <q> 사용 불가. / 중첩가능
- blockquote : 긴 인용문
- cite(citation) : 출처 정보

```html
<p>어렸을 때 어른들이 <q>너 많이 컸구나</q> 하면 그게 굉장한 칭찬으로 느껴졌었습니다. 다만 시간이 지난 것뿐인데… 지금은 <q>너 아직도 노안이 안 왔구나</q> <q>너 아직 머리숱이 많구나 (혹은 너 아직도 흰머리가 덜 났구나)</q> 등의 이야기가 퍽 반갑습니다. 어렸을 때는 시간이 흐른 것 때문에 칭찬받고, 나이 들어서는 시간을 비껴간 것 때문에 칭찬 비슷한 것을 듣습니다.</p>
```
```html
<figure>
    <img src="images/sbs-drama__do-you-want-to-kiss-first.png" alt="">
    <figcaption>-이미지 출처: SBS &lt;키스 먼저 할까요?&gt; 방송화면 캡쳐-</figcaption>
  </figure>
```
```html
  <blockquote>
    <p>“…우리 같은 여자들은.”</p>
    <p>“우리?”</p>
    <p>“시절이 끝난 여자들이요. 꽃이 아닌 풀떼기가 된…(중략)”</p>
    <p>“당신 아직 안 늙었어.”</p>
    <p>“맞아요. 안 늙었어요, 나는 아직.<br>그렇게 안 봐주는 세상 때문에 매 순간 늙고 있어서 그렇지.”</p>
    <cite>_SBS 드라마 &lt;키스 먼저 할까요?&gt; 중에서</cite>
  </blockquote>
```

#### [어휘 요소들]
의미 요소(Semantic Elements)
- 강조의 의미를 부여하는 용도

<hr>

1) &lt;strong&gt; : 내용의 중요성(importance), 심각성(seriousness), 긴급성(urgency)을 강조할 경우 사용

- [중요성] : 제목/캡션의 글자 중 일부를 더욱 강조하는데 사용

```html
<h1>챕터 1: <strong>연습</strong></h1>
	
<figcaption>피규어 1. <strong>개미 식민지 역학</strong>. 이 식민지 지역의 개미는 열원(왼쪽 위)과 식량 공급원(오른쪽 아래)의 영향을 받습니다.</figcaption>
		
<h1><strong>꽃, 꿀벌, 꿀</strong> 그리고 내가 이해하지 못하는 다른 요소</h1>
```

- [심각성] : 경고 또는 주의를 주고자 할 때 사용

```html	
<p>
	<strong>경고.</strong> 이 지하 감옥은 위험합니다.
	<strong>오리 때를 피하세요.</strong> 찾은 금은 가지고 떠나세요.
	<strong>
		<strong>다이아몬드는 사용하지 마세요.</strong>,
		그것을 사용하면 폭발할 것이며
		<strong>10미터 내에 있는 모든 것을 파괴할 것입니다.</strong>
	</strong>
	당신에게 경고 했습니다.
</p>
```

- [긴급성] : 문서의 다른 부분보다 빨리 보아야 하는 내용을 나타내는데 사용

```html
<p>리마인더 시스템 Remy에 오신 것을 환영합니다.</p>
<p>오늘 할 일1</p>
<ul>
	<li><p><strong>오븐을 끕니다.</p></strong></li>
	<li><p>휴지통에 불필요한 것을 버립니다.</p></li>
	<li><p>세탁을 합니다.</p></li>
</ul>
```

<hr>

2) &lt;em&gt; : 특정 내용의 스트레스(Stress) 강조(Emphasis) - 문장 의미를 변경

강조가 없는 예

```html
<p>고양이는 귀여운 동물입니다.</p>
```

고양이(종)을 강조한 예

```html
<p><em>고양이</em>는 귀여운 동물입니다.</p>
```

귀여운(형용사)을 강조한 예

```html
<p>고양이는 <em>귀여운</em> 동물입니다.</p>
```

문장 전체를 강조한 예 (느낌표 사용)

```html
<p><em>고양이는 귀여운 동물입니다!</em></p>
```

<hr>

3) &lt;b&gt; : 단순히 다른 글자와 구분된 용도로 사용. 문서 요약의 주요 단어, 리뷰 제품 이름 등

아래 조선에 부합하지 않을 경우 최종적으로 b 요소 사용을 고려

제목은 h1 ~ h6 요소를 사용하고,
강조는 em 요소를 사용해야 하며,
중요도는 strong 요소로 표시 되어야 하고,
표시 또는 강조 표시된 텍스트는 mark 요소를 사용.

b 요소 사용 예시
	
```html
<p>
	작은 방에 들어가니 <b>낡은 액자</b>와 <b>거미줄이 엮인 손전등</b>이 탁자에 놓여있었다.
</p>
```

<hr>

4) &lt;i&gt; : 다른 글자와 구분된 용도로 사용. 기술적 용어, 다른 언어(목소리), 인물의 생각 등을 표현

i 요소 사용 예시
	
```html
<p><i class="taxonomy">펠리스 실베스트리 카터스(Felis silvestris catus)</i>는 귀여워요.</p>
<p><i>산문 내용</i> 용어는 위에 기술되어 있습니다.</p>
<p>
	Galileo Galilei는 재판을 받고 나오면서
	<i lang="la">"E pur si muove."</i>
	라고 말했습니다.
</p>
```

꿈의 연속된 장면을 i 요소로 사용한 예시

```html
<p>Raymond는 잠을 자려고 했습니다.</p>
<p>
	<i>그 배는 목요일에 멀리 출항합니다.</i>, 그는 꿈을 꾸었습니다.
	<i>그 배는 아름다운 공주 Carey를 포함하여 많은 사람들이 타고 있었습니다.
	그는 그녀가 자신을 알아주기를 매일 밤낮으로 원했지만 그런 일은 일어나지 않았습니다.</i>
</p>
<p><i>마지막 날 밤 그는 용기를 내어 그녀에게 말을 걸었습니다.</i></p>
<p>Raymond는 화재 경보기 알람 소리에 눈이 띄였습니다.</p>
```
	
#### [섹션/메인 요소]

루트 섹션(Root Section) 요소

&lt;body&gt;
- 문서에서 단 1번만 사용 가능.

<hr>

섹션(Sections) 요소들
- 섹션 요소는 일반적인 컨테이너 요소가 아니며, 문서 개요에
  명시적으로 나열되는 경우에만 섹션 요소가 적합하다는 규칙이 있다.
  일반적인 컨테이너 요소로는 &lt;div&gt;, &lt;span&gt; 등이 있다.

&lt;article&gt;
- 문서, 페이지, 애플리케이션, 사이트 등에 포함된 독립적인 섹션을 말한다.
  잡지, 신문, 논문, 에세이, 보고서, 블로그, 기타 소설 미디어 일 수 있음.
  일반적인 규칙은 article 요소의 내용이 문서 개요에 명시적으로 나열되는
  경우에만 적합하다. 각 article 요소는 일반적으로 요소의 하위 항목으로
  제목(h1~h6 요소)을 포함시켜 식별해야 한다.

[예시]

```html
<aticle>
<h2>기사 제목</h2>
...
</aticle>
```

&lt;section&gt;
- section 요소는 문서, 애플리케이션의 일반적인 섹션을 말한다.
  이 컨텍스트의 섹션은 주제별로 그룹화 된 콘텐츠이다.
  웹 사이트의 섹션은 소개(introduction), 뉴스 항목(news item),
  연락처 정보(contact information)를 위한 섹션으로 나눌 수 있다.

[참고]
콘텐츠가 사이트에 포함된 독립적인 섹션의 성향이 크다면
section 요소 대신 article 요소를 사용하는 것이 좋다.

&lt;aside&gt;
- 웹 사이트의 사이드바에 해당되는 부 콘텐츠(메인 콘텐츠와 분리된) 섹션을 말한다.

&lt;nav&gt;
- 다른 페이지로 이동하는 링크 또는 사이트 내 탐색 링크를 포함하는 섹션 요소이다.

[참고]
내용을 쉽게 이해할 수 있도록 nav 요소 내부에는 비순차 목록(ul)을 사용한다.
사이트의 모든 링크를 nav에 포함하는 것은 아니며, 주로 사이트를 탐색하는 링크를 포함한다.
사이트 하단에 위치한 링크는 footer 요소로도 충분하다.

<hr>

섹션 내부에 사용되는 요소들
&lt;heaader&gt;
- header 요소는 일반적으로 섹션의 제목, 목차, 검색, 로고 등을 포함하는데 사용한다.

&lt;footer&gt;
- footer 요소는 일반적으로 섹션의 저자, 링크, 저작권 정보 등을 포함하는데 사용한다.

섹션과 헤딩
- 헤딩(h1 ~ h6) 요소는 섹션의 제목에 해당된다.
  
<hr>
  
메인(Main) 요소
&lt;main&gt;
- 문서 또는 애플리케이션 body 요소의 메인 콘텐츠에 해당한다.
  main 요소는 섹션 요소가 아니며, 보이는 요소가 2개 이상이면 안된다.
  사용되지 않는 main 요소는 화면에서 감춤(hidden) 처리해야 한다.
  article, section, aside, nav 요소는 main 요소를 자식으로 포함할 수 없다.
  반대로 main 요소는 섹션 요소들을 포함할 수 있다.
  main 내부에는 header, footer 요소를 직접적으로 포함하지 않는다.

[예시]

```html
<main>...</main>
<main hidden>...</main>
<main hidden>...</main>
```
	
</details>

<details>
  <summary>3일차 학습</summary>

#### [컨테이너 요소]

<b>HTML 요소를 묶는 컨테이너 요소들</b>
- 아무런 의미(Semantic)는 가지지 않는다.
- 그러하므로 이 요소들은 적절한 시멘틱 요소가 없을 때 사용해야 한다.

<b>&lt;div&gt; 디비전(Division) 요소</b>
- 블록(block) 컨테이너

<b>&lt;span&gt; 스팬(Span) 요소</b>
- 인라인(inline) 컨테이너
- 인라인 요소들(a, strong, em, b, i 등)을 감쌀 때 사용된다.
- 블록 요소들(h1~6, p, blockquote, section 등)을 감쌀 수 없다.


#### [텍스트 레벨 요소]

&lt;sup&gt; 요소
    - 윗첨자

&lt;sub&gt; 요소
  - 아래첨자

&lt;mark&gt; 요소
  - 관련 참조 목적의 하이라이트된 글자 요소

&lt;abbr&gt; 요소
  - 축약 요소

&lt;time&gt; 요소
  - 기계가 이해할 수 있는 형태로 날짜나 시간을 나타내는 요소

&lt;s&gt; 요소
  - 더 이상 관련이 없거나 더 이상 정확하지 않은 요소


#### [그룹핑 요소]

- address
  - href="tel:" - 전화 연결
- pre(Preserved Text)
  - 이메일, 빈 줄이 표시된 단락, 글 머리표가 붙은 줄로 표시된 목록 등에 사용
  - 컴퓨터 코드(언어) 표시 목적으로 사용
  - ASCII 아트 표시
  - 컴퓨터 코드, 출력, 키보드 블록을 나타내기 위해 pre 요소는 code, samp, kbd 요소와 함께 사용 가능

```html
<pre>
     ____ ∧ ∧
    |＼ /(´～`)＼ &lt;변화구
    |　|￣￣￣￣￣|
    |　|＝みかん＝ |
     ＼|＿＿＿＿＿|
</pre>
```

```html
<pre>
<code>
function Panel(element, canClose, closeHandler) {
  this.element = element;
  this.canClose = canClose;
  this.closeHandler = function () { if (closeHandler) closeHandler() };
}
</code>
</pre>
```

#### [임베디드 요소]

##### ▷ picture 요소
- 0개 이상의 <source> 요소와 **1개 이상의 img**를 포함하는 컨테이너 요소.
- 다양한 스크린 환경에 맞는 적합한 이미지를 제공하기 위한 목적으로 사용.
- source 요소를 사용할 수 없을 경우, img 요소가 화면에 표시.

  ```html
    <picture>
      <source srcset="bamboo-pen2.png" media="(min-width: 900px)">
      <source srcset="bamboo-pen.png" media="(min-width: 600px)">
      <img src="bamboo-pen-narrow.png" alt="Bamboo Pen">
    </picture>

    <picture>
      <source srcset="bamboo-pen.svg" type="image/svg+xml">
      <img src="bamboo-pen-narrow.png" alt="Bamboo Pen">
    </picture>
  ```

##### ▷ source 요소
- picture, audio, video 요소의 다중 미디어 리소스를 지정하기 위해 사용.

##### ▷ video 요소
- 동영상 콘텐츠를 HTML 문서에 포함하기 위해서 사용.
- src 속성이나 <source> 요소을 이용해 여러 개의 동영상 소스 중 하나를 표시.(현재는 mp3,mp4등의 브라우저 지원으로 source 사용 X)
- 속성
  - src      - 파일 경로
  - poster   - 포스터 이미지 경로
  - preload  - 미리 읽어와서 사용자 경험 향상(메타데이터 / 비디오 다운로드)에 관한 설정 [none, metadata, auto(기본값)]
  - controls - 재생 컨트롤 표시 설정
  - autoplay - 자동 재생 설정(사용자 경험를 위해 자동 재생 설정은 가급적 사용 X)
  - loop     - 반복 설정
  - muted    - 음소거 설정

  ```html
    <video src="videofile.mp4" poster="posterimage.jpg" controls loop="true" autoplay="true" mute="true"><!--true값 생략 가능-->
      HTML5 <code>video</code> 요소를 지원하지 않는 구형 웹 브라우저를 사용 중입니다.
      <a href="http://outdatedbrowser.com/ko">최신형 브라우저로 업데이트</a> 하세요.
    </video>
  ```

##### ▷ audio 요소
- 오디오 콘텐츠를 포함하기 위해서 사용. video와 유사.
- (속성) volume : 볼륨 조절(0.0 ~ 1.0)

  ```html
    <audio src="audiofile.mp3" controls>
      HTML5 <code>audio</code> 요소를 지원하지 않는 구형 웹 브라우저를 사용 중입니다.
      <a href="http://outdatedbrowser.com/ko">최신형 브라우저로 업데이트</a> 하세요.
    </audio>
  ```


##### ▷ track 요소
- 비디오/오디오 재생 시, 자막을 표시.
-  default 속성을 설정하지 않을 경우, 자막 사용 안함 됨
  ```html
    <video src="videofile.mp4" poster="posterimage.jpg">
      <track kind="subtitles" src="videofile.ko.vtt" srclang="ko" label="한국어" default>
      <track kind="subtitles" src="videofile.en.vtt" srclang="en" label="English">
      <track kind="subtitles" src="videofile.en.vtt" srclang="ja" label="日本語">
    </video>

    <audio src="audiofile.mp3">
      <track kind="subtitles" src="audiofile.ko.vtt" srclang="ko" label="한국어">
      <track kind="subtitles" src="audiofile.en.vtt" srclang="en" label="English">
    </audio>
  ```

##### ▷ iframe 요소
- 인라인 프레임(Inline Frame)에 다른 HTML 페이지를 포함하여 화면에 표시.
- (속성) allowfullscreen : 프레임 전체화면 설정

  ```html
    <iframe
      width="560"
      height="315"
      src="https://www.youtube.com/embed/0wlXaHmmOVc?rel=0&amp;showinfo=0"
      style="border:0"
      allowfullscreen></iframe>
  ```

##### ▷ map 요소
- 이미지 맵(클릭 가능한 링크 영역)을 정의하기 위해 <area>와 함께 사용됨.
- [image-map.net](https://www.image-map.net/) : 이미지 맵 좌표 생성

##### ▷ area 요소
- 이미지의 핫스팟 지역 정의, 하이퍼링크 설정. <map> 내부에서만 사용 가능.
- 속성
  - shape    - 핫스팟 모양 설정
  - coords   - 모양의 좌표 값 설정
  - href     - 하이퍼링크 주소 설정
  - target   - 새 창(탭) 열림 설정
  - alt      - 대체 텍스트 설정
  - hreflang - 연결된 페이지의 언어 속성 설정
  - download - canvas 데이터 다운로드 설정
  - title    - 툴팁제공을 위해 사용

  ```html
    <img src="products-map.jpg" alt="제품 모음" usemap="#products-map">
    <map name="products-map">
      <area
        shape="circle"
        coords="200,250,25"
        hreflang="en-GB"
        href="another.html"
        alt="Another Page"
        target="_blank"
        title="제품1">
    </map>
  ```

##### ▷ svg 요소
- 확장가능한 벡터 그래픽(SVG - Scalable Vector Graphics)은 2차원의 벡터 그래픽을 기술하기 위한 XML 마크업 언어.

  ```html
    <img src="svgfile.svg" alt="SVG File">

    <svg width="150" height="150" viewBox="0 0 150 150">
      <circle r="50" cx="75" cy="75" fill="#333" stroke="#900" stroke-width="4" />
    </svg>
  ```
</details>

<details>
  <summary>4일차 학습</summary>

#### [테이블 요소]
- ```<table>``` 요소
    ```
    테이블 몸체에 해당되며, 행(row)/열(column) 및 셀(cell)을 포함한다.
    복잡한 내용을 x, y축에 따라 이해하기 쉽게 데이터를 구조화하는데 테이블을 사용한다.
    가장 좋은 테이블 디자인은 최대한 단순하게 표를 구성하는 것이다.
    테이블 내 테이블을 중첩해서는 안된다.
    테이블을 레이아웃(배치) 목적으로 사용해서는 안된다.
    border 속성을 사용해 테두리를 그릴 수 있다. (CSS로 대체하는 것이 좋다)
    ```

 - ```<caption>``` 요소
    ```
    테이블의 제목을 명시적으로 제공하며, 제작자는 표의 내용을 이해할 수 있도록 정보를 제공해야 함.
    테이블 내용이 복잡해 설명이 필요하다면 아래 나열된 방법 중 하나를 선택해 기술해야 한다.

      [설명(summary)을 추가하는 방법]
        1. aria-describedby 속성을 사용해 설명 단락(paragraph)을 연결
        2. <figure> 요소에 aria-labelledby 속성을 사용해 제목(caption)을 연결
    ```

 - ```<tr>``` 요소
  
    ```
      테이블의 행(row)을 말하며 내부에 셀 제목(header), 셀 내용(data)을 포함한다.
    ```

 - ```<th>``` 요소

    ```
    테이블 셀 제목(header cell in a table)으로 행(tr) 내부에 포함되어야 한다.

    [속성]
      scope: 행(row) 또는 열(col), 행그룹(rowgroup), 열그룹(colgroup)의 제목임을 명시
      abbr: 제목이 길어 축약(Abbreviation)이 필요할 때 사용
      colspan: 열(column)을 그룹 지을 때 사용
      rowspan: 행(row)을 그룹 지을 때 사용
    ```

 - ```<td>``` 요소
    ```
    테이블 셀 내용(data cell in a table)으로 행(tr) 내부에 포함되어야 한다.

    [속성]
      colspan: 열(column)을 그룹 지을 때 사용
      rowspan: 행(row)을 그룹 지을 때 사용
      headers: 셀 제목을 하나 이상 연결하여 읽기 용이하도록 구성할 때 사용
    ```

 - ```<thead>``` 요소
    ```
    테이블 행 블록(row block) 내에 제목 열 그룹(column headers)으로 구성할 경우 사용한다.
      선택적(option)으로 사용한다. (필수 아님)
    ```

 - ```<tbody>``` 요소
    ```
    행 블록 내에 테이블 데이터로 구성할 때 사용한다.
    선택적(option)으로 사용한다. (필수 아님)
    ```

 - ```<tfoot>``` 요소
    ```
    행 블록 내에 열 요약(column summaries)로 구성할 때 사용한다.
    선택적(option)으로 사용한다. (필수 아님)
    ```

 - ```<col>``` 요소
    ```
    테이블 열(column)을 하나 이상 묶고자 할 때 사용한다.
    일반적으로 colgroup 요소 내부에 포함시킨다.
    선택적(option)으로 사용한다. (필수 아님)

    [속성]
      span: 열 묶음 개수 설정
    ```
 - ```<colgroup>``` 요소
    ```
    테이블 열(column) 그룹을 만들고자 할 때 사용한다.
    내부에 col 요소를 포함하거나, 포함하지 않을 수 있다.
    선택적(option)으로 사용한다. (필수 아님)

    [속성]
      span: colgroup 요소가 col을 포함하지 않을 경우, 열 묶음 개수 설정
    ```

  실습 

  - table내에 tody를 안 적어줘도 자동으로 생깁니다.
  - 열은 꼭 맞쳐야합니다.
  - th에는 스크린 리더로 알 수 있게 scope="row" 라는 것을 넣어주어야 합니다. 
  - aria-describedby="" 자세한 내용을 기술하기 위해 사용. 표에 대한 자세한 내용 전달
  - table border 속성은 css를 사용하여 표현해 주는 것이 좋다.

    ```
    <p id="compare-shoes-table"> 국제(한국, 미국, 영국, 유럽) 성인 남성 운동화 사이즈 비교 표로 4행 
    12열로 구성되어 있습니다.
    <table border="1" aria-describedby="compare-shoes-table">
    ```


    ```html
    <table border="1">
      <cation>성인 남성 운동화 사이즈표</cation>
      <tr>
        <th>한국(mm)</th> 
        <td>240</td> 
        <td>245</td>
        <td>250</td>
        <td>255</td>
        <td>260</td>
        <td>265</td>
        <td>270</td>
        <td>275</td>
        <td>280</td>
        <td>285</td>
        <td>290</td>
      </tr>
      <tr>
        <th>미국(US)</th> 
        <td>6</td>
        <td>6.5</td>
        <td>7</td>
        <td>7.5</td>
        <td>8</td>
        <td>8.5</td>
        <td>9</td>
        <td>9.5~10</td> 
        <td>10~10.5</td>
        <td>11</td>
        <td>11.5</td>
      </tr>
      <tr>
        <th>영국(UK)</th> 
        <td>5</td>
        <td>5.5</td> 
        <td>6</td> 
        <td>6.5</td> 
        <td>7</td> 
        <td>7.5</td> 
        <td>8</td> 
        <td>8.5~9</td> 
        <td>9~9.5</td> 
        <td>10</td> 
        <td>11</td>
      </tr>
      <tr>
        <th>유럽(EU)</th> 38~39 39 40 40~41 41 42 42~43 43 44 44~45 45
      </tr>
    </table>
    ```

  - ```<thead>``` 행 블록을 만들때 사용
  - scope 속성 'rowgroup' 가로그룹 'colgroup' 세로 그룹 (행인지 열인지 아니면 행의 그룹인지 열의 그룹인지 설정해줍니다.)
  - ```<th>```  해당 그룹의 제목
  - td header 속성 **

    ```html
      <table id="real-deal-table" border="1" aria-describedby="real-deal-table-summary">
      <caption>
        <strong>
          최근 3개월간 실거래가
          <button type="button" class="open-tooltip" title="자세히" aria-label="자세히">?</button>
        </strong>
          <!-- ? -->
        <div id="real-deal-table-summary" class="a11y-hidden">
          <h3>국토교통부 실거래가</h3>
          <p>
            제공: 국토교통부<br>
            최근 3개월간(2018.01월~03월) 신고된 국토교통부 실거래 가격자료를
            기반으로 최저가격과 최고가격 및 거래건수를 노출합니다.
          </p>
          <button type="button" class="close-tooltip" title="닫기" aria-label="닫기">X</button>
        </div>
        
        <!-- URL 주소: https://goo.gl/FxWHEg -->
        <p>실거래가 기준: 2018.03 <a href="https://goo.gl/FxWHEg" target="_blank">자료: 국토교통부</a></p>
      </caption>
      
      <thead>
        <tr>
          <th id="rd-1" rowspan="2" scope="col">공급/전용(㎡)</th>
          <th id="rd-2" colspan="3" scope="colgroup">매매 실거래가(만원)</th>
          <th id="rd-3" colspan="3" scope="colgroup">전세 실거래가(만원)</th>
          <th id="rd-4" colspan="3" scope="colgroup">월세 실거래가(만원)</th>
        </tr>
        <tr>
          <th id="rd-2-1" scope="col">최저가</th>
          <th id="rd-2-2" scope="col">최고가</th>
          <th id="rd-2-3" scope="col">거래건수</th>
          <th id="rd-3-1" scope="col">최저가</th>
          <th id="rd-3-2" scope="col">최고가</th>
          <th id="rd-3-3" scope="col">거래건수</th>
          <th id="rd-4-1" scope="col">최저가</th>
          <th id="rd-4-2" scope="col">최고가</th>
          <th id="rd-4-3" scope="col">거래건수</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <th id="rd-1-1" scope="row">80/59.91</th>
          <td headers="rd-1 rd-1-1 rd-2" colspan="3">-</td>
          <td headers="rd-1 rd-1-1 rd-3 rd-3-1">43,000(2층)</td>
          <td headers="rd-1 rd-1-1 rd-3 rd-3-2">43,000(2층)</td>
          <td headers="rd-1 rd-1-1 rd-3 rd-3-3">1</td>
          <td headers="rd-1 rd-1-1 rd-4" colspan="3">-</td>
        </tr>
        <tr>
          <th id="rd-1-2" scope="row">84/59.99</th>
          <td headers="rd-1 rd-1-2 rd-2 rd-2-1">47,800(4층)</td>
          <td headers="rd-1 rd-1-2 rd-2 rd-2-2">55,000(22층)</td>
          <td headers="rd-1 rd-1-2 rd-2 rd-2-3">10</td>
          <td headers="rd-1 rd-1-2 rd-3 rd-3-1">43,000(2층)</td>
          <td headers="rd-1 rd-1-2 rd-3 rd-3-2">43,000(2층)</td>
          <td headers="rd-1 rd-1-2 rd-3 rd-3-3">1</td>
          <td headers="rd-1 rd-1-2 rd-4 rd-4-1">5,000/120(6층)</td>
          <td headers="rd-1 rd-1-2 rd-4 rd-4-2">40,000/10(4층)</td>
          <td headers="rd-1 rd-1-2 rd-4 rd-4-3">5</td>
        </tr>
        <tr>
          <th id="rd-1-3" scope="row">111/84.82</th>
          <td headers="rd-1 rd-1-3 rd-2 rd-2-1">63,200(12층)</td>
          <td headers="rd-1 rd-1-3 rd-2 rd-2-2">63,500(19층)</td>
          <td headers="rd-1 rd-1-3 rd-2 rd-2-3">2</td>
          <td headers="rd-1 rd-1-3 rd-3 rd-3-1">53,000(13층)</td>
          <td headers="rd-1 rd-1-3 rd-3 rd-3-2">53,000(13층)</td>
          <td headers="rd-1 rd-1-3 rd-3 rd-3-3">1</td>
          <td headers="rd-1 rd-1-3 rd-4" colspan="3">-</td>
        </tr>
        <tr>
          <th id="rd-1-4" scope="row">112/84.92</th>
          <td headers="rd-1 rd-1-4 rd-2 rd-2-1">65,000(6층)</td>
          <td headers="rd-1 rd-1-4 rd-2 rd-2-2">65,000(6층)</td>
          <td headers="rd-1 rd-1-4 rd-2 rd-2-3">1</td>
          <td headers="rd-1 rd-1-4 rd-3 rd-3-1">52,000(10층)</td>
          <td headers="rd-1 rd-1-4 rd-3 rd-3-2">52,000(10층)</td>
          <td headers="rd-1 rd-1-4 rd-3 rd-3-3">1</td>
          <td headers="rd-1 rd-1-4 rd-4" colspan="3">-</td>
        </tr>
        <tr>
          <th id="rd-1-5" scope="row">112/84.94</th>
          <td headers="rd-1 rd-1-5 rd-2 rd-2-1">60,000(25층)</td>
          <td headers="rd-1 rd-1-5 rd-2 rd-2-2">60,000(25층)</td>
          <td headers="rd-1 rd-1-5 rd-2 rd-2-3">1</td>
          <td headers="rd-1 rd-1-5 rd-3 rd-3-1">45,000(10층)</td>
          <td headers="rd-1 rd-1-5 rd-3 rd-3-2">45,000(10층)</td>
          <td headers="rd-1 rd-1-5 rd-3 rd-3-3">1</td>
          <td headers="rd-1 rd-1-5 rd-4 rd-4-1">35,000/60(5층)</td>
          <td headers="rd-1 rd-1-5 rd-4 rd-4-2">35,000/60(5층)</td>
          <td headers="rd-1 rd-1-5 rd-4 rd-4-3">1</td>
        </tr>
        <tr>
          <th id="rd-1-6" scope="row">145/114.98</th>
          <td headers="rd-1 rd-1-6 rd-2 rd-2-1">76,800(15층)</td>
          <td headers="rd-1 rd-1-6 rd-2 rd-2-2">80,000(14층)</td>
          <td headers="rd-1 rd-1-6 rd-2 rd-2-3">2</td>
          <td headers="rd-1 rd-1-6 rd-3 rd-3" colspan="3">-</td>
          <td headers="rd-1 rd-1-6 rd-4 rd-4-1">5,000/200(5층)</td>
          <td headers="rd-1 rd-1-6 rd-4 rd-4-2">5,000/200(5층)</td>
          <td headers="rd-1 rd-1-6 rd-4 rd-4-3">1</td>
        </tr>
      </tbody>
    </table>
    ```
<br>

#### [폼 요소]

- ```<form>``` 는 처음에는 method의 기본 값이 get 입니다. (개발자와 협의를 해서 어떤 주소로 넣어 줄까 물어봐야합니다.)
  - post인 경우 민감한 정보 데이터, 이메일, 개인정보 같은 것을 전송할 때 사용.

      ```html
      <form action-"/" method="POST" enctype="multpart-formdata">
        <p>
          <label for="user_name">이름</label>
          <input id="user_name"
            name="user_name" 
            type="text" 
            placeholder="주" 
            maxlength="4" 
            readonly 
            value="정소하" 
            minlength="2"
          </p>
          <p>
            <label for="user_pass">비밀번호</label>
            <input
              type="password"
              name="user_pass"
              id="user_pass"
              required
              placeholder="비밀번호 6자리 입력해주세요."
          </p>
          <p>
            <label><input type="radio" name="user_gender" value="1">남성</label>
            <label><input type="radio" name="user_gender" value="2" checked>여성</label>
          </p>
          <p>
            <label><input type="checkbox" name="user_agree" id="user_agree">모든 내용을 읽고 동의합니까?</label>
          </p>
          <p>
            <input type="file" name="user_data_upload" id="user_data_upload">
          </p>
          <p>
            <label>검색<input type="search" name="user_search" id="user_search"></label>
          </p>
          <p>
            <label>이동할 웹주소<input list="url_ex" type="url" name="user_url" id="user_url"></label>
            <datalist id="url_ex">
              <option value="http://naver.com">naver.com</option>
              <option value="http://nate.com">nate</option>
              <option value="http://google.com">google</option>
              <option value="http://goo.gl">google. short url</option>
            </datalist>
          </p>
          <p>
            <label>전화번호<input list="tel_ex" type="tel" name="user_tel" id="user_tel"></label>
             <datalist id="tel_ex">
              <option value="111">111</option>
              <option value="222">222</option>
              <option value="333">333</option>
              <option value="444">444</option>
            </datalist>
          </p>
          <p>
            <label>이메일<input type="email" name="user_email" id="user_email"></label>
          </p>
          <p>
            <label for="user_hobby">취미</label>
            <select name="user_hobby" id="user_hobby">
              <option value="0">없음</option>
              <option value="1">축구</option>
              <option value="2">독서</option>
              <option value="3">영화관람</option>
            </select>
          </p>
          <input type="submit" value="전송">
          <input type="button" value="버튼">
          <input type="image" src="https://goo.gl/Ng66oQ" alt="체크인" width="20" height="20">
          <input type="reset" value="초기화">
          <input type="hidden" name="using-ajax" value="true">
          <input type="number" name="" id="" min="100" step="10" max="1000" value="150">
          <input type="range" name="" id="" min="10" step="5" max="25" value="15">
          <input type="color" name="" id="" value="#F7CC60">
          <button type="reset">초기화</button>
          <button type="submit">전송</button>
      </form>

      사용자의 데이터를 입력 받을 수 있는 폼 컨트롤을 말함.
      다양한 유형(Type) 설정이 가능하며, 유형에 맞는 역할을 수행한다.

      [사용 예시]
      <form action="https://formspree.io/your@email.com" method="POST">
        ...
      </form>
      ```

  - ```input``` 사용자의 데이터를 입력받을 수 있는 폼 컨트롤러입니다. 기본값은 text입니다.
  - input만 있으면 어떤 것인지 모르기 때문에 label 요소를 사용해 줘야 합니다.
  - placeholder 기능을 이용해서 텍스트에 어떤 것을 사용해야 할지 알려줍니다.
  - required 필수 요소를 설정할 수 있습니다.
  - optgroup으로 셀렉트 들을 묶어 줄 수 있습니다.. disabled 라는 속성을  사용하게 되면 선택이 안되게 설정이 가능합니다.
  - fieldset으로 묶고 제목을 legend로 묶게되면 해당 폼들은 묶이게 됩니다.
  - progres태그 smeter태그

    ```
    <input>
    사용자의 데이터를 입력 받을 수 있는 폼 컨트롤을 말함.
    다양한 유형(Type) 설정이 가능하며, 유형에 맞는 역할을 수행한다.

    [속성]
      - name
      - placeholder
      - value-
      - readonly
      - required
      - disabled
      - minlength
      - maxlength
      - list

    [유형]
      - text
      - password
      - checkbox
      - radio
      - file
      - submit
      - button
      - image
      - reset
      - hidden
      - search
      - url
      - tel
      - email
      - date
      - month
      - week
      - time
      - datetime-local
      - number
      - range
      - color

    <label>
    - 컨트롤에 레이블(이름)을 붙이고자 할 경우 사용.

    [사용 예시]

      1. <label>이름 <input type="text" placeholder="이두연"></label>

      2. <label for="u_pass">비밀번호</label>
         <input id="u_pass" name="u_pass" type="password" maxlength="8" placeholder="비밀번호 8자리를 입력해주세요">

  <button>
    - 버튼 폼 컨트롤로 사용자의 인터랙션을 받아 액션을 트리깅(방아쇠) 처리함.

    [type]
      - submit (초기 값)
      - button
      - reset

      [사용 예시]
        <button type="submit">전송</button>
        <button type="button">버튼</button>
        <button type="reset">초기화</button>

  <select>
    - 드롭 다운 메뉴(옵션을 선택 할 수 있는) 컨트롤을 말함.
      내부에 <option> 요소를 포함하여 사용자에게 선택할 수 있도록 한다.
      <option>을 묶어 그룹으로 만들고자 한다면 <optgroup> 요소를 사용하고,
      label 속성을 사용해 그룹 이름을 설정한다.

      [속성]
        - name
        - multiple
        - disabled
        - required
        - size

      [사용 예시]
        <label for="user_hobby">취미</label>
        <select name="user_hobby" id="user_hobby">
          ...
        </select>

  <option>
    - <select>, <datalist>, <optgroup> 내부에 포함 가능한 컨트롤로 항목을 만드는데 사용됨.

    [속성]
      - value
      - selected
      - label
      - disabled

    [사용 예시]
      <label for="user_hobby">취미</label>
      <select name="user_hobby" id="user_hobby" required>
        <option value="0">없음</option>
        <option value="1" selected>축구</option>
        <option value="2" label="basketball" disabled>농구</option>
        <option value="3">독서</option>
        <option value="3">영화관람</option>
      </select>

  <optgroup>
    - <option> 컨트를을 그룹지을 때 사용됨.

    [속성]
      - disabled
      - label

    [사용 예시]
      <p>
        <label for="user_hobby">취미</label>
        <select name="user_hobby" id="user_hobby" required>
          <option value="0">없음</option>
          <optgroup label="구기종목">
            <option value="1" selected>축구</option>
            <option value="2" label="basketball" disabled>농구</option>
          </optgroup>
          <optgroup label="문화생활" disabled>
            <option value="3">독서</option>
            <option value="3">영화관람</option>
          </optgroup>
        </select>
      </p>

  <textarea>
    - 멀티라인 일반 텍스트 편집 컨트롤을 말한다.

    [속성]
      - name
      - placeholder
      - rows
      - cols
      - readonly
      - required
      - disabled
      - minlength
      - maxlength

    [사용 예시]
      <div>
        <label for="user_comments">코멘트</label>
        <p>
          <textarea name="user_comments" id="user_comments" cols="24" rows="5">남기고 싶은 말을 
          작성해주세요.</textarea>
        </p>
      </div>

  <fieldset>
    - 하나 이상의 폼 컨트롤을 그룹화 하는데 사용됨.

    [속성]
      - name
      - disabled

    [사용 예시]
      <fieldset name="user_acount">
        ...
      </fieldset>

  <legend>
    - <fieldset> 컨트롤의 레이블(이름)을 설정하는 컨트롤.

    [사용 예시]
      <fieldset name="user_acount">
        <legend>사용자 계정</legend>
      </fieldset>

  <output>
    - 계산된 결과를 출력하는 컨트롤.

    [속성]
      - name
      - for

    [사용 예시]
      <form oninput="result_sum.value = parseInt(n1.value + n2.value, 10)">
        <p>
          <input type="number" name="n1" value="4"> +
          <input type="number" name="n2" value="10"> =
          <output name="result_sum">14</output>
        </p>
      </form>

  <datalist>
    - 데이터 목록 요소 컨테이너 컨트롤.
      내부에 <option> 요소를 사용해 항목을 만든다.

      [사용 예시]
        <label>이동할 웹주소 <input list="url_ex" type="url" name="user_url" id="user_url"></label>
        <datalist id="url_ex">
          <option value="http://naver.com">naver</option>
          <option value="http://nate.com">nate</option>
          <option value="http://google.com">google</option>
          <option value="http://goo.gl">google short url</option>
        </datalist>

  <progress>
    - 작업의 완료 진행 상황을 표시하는데 사용되는 컨트롤.

    [속성]
      - value
      - max

    [사용 예시]
      <progress value="10" max="100">10%</progress>

  <meter>
    - 알려진 범위 내에서의 스칼라 측정 또는 분포 비율을 나타내는 컨트롤. (게이지(gauge)라고도 불림)
      디스크 사용 현황, 쿼리 결과의 관련성, 특정 후보에 대한 투표율 등이 해당됨.

    [속성]
      - value
      - min
      - max
      - low
      - high
      - optimum

    [사용 예시]
      <meter value="20" min="5" max="40">20</meter>
    ```

</details>

<details id="5day">
  <summary>5일차 학습</summary>

#### [인터랙티브 요소]
  - ```<deatils>``` 예전 강의에서 sup를 이용해서 각주로 만든적이 있다. 하지만 details는 각주의 용도로 적합하지 않다.
  - open 속성을 넣어주면 details 요소가 펼쳐서 보여줍니다.
  - 원하는 제목을 표시하고 싶으면 summery를 사용할 수 있습니다.

  ```html
  <details open>
    <summary>서용자
    <p>
      디스클로저 위젯(disclosure widget, 참고: https://goo.gl/uznvFY)으로 정보를 감추거나, 펼쳐서 보여준다.
      모든 정보를 일시에 공개하지 않고 사용자의 요구에 맞춰 정보를 공개할 수 있다. (화면의 복잡함을 줄임)
      아코디언(Accordion) 컴포넌트와 비슷하게 작동한다.
    </p>
  </details>
  ```

  ```html
  <div class="container">
    <dialog>
      <button type="submit">confirm</button>
    </dialog>
  </div>
  ```

  ```html
  <style>
    body {
      margin: 0;
      min-height: 100vh;
    }
    .demo {
      display: flex;
      justify-content: center;
      align-items: flex-start;
    }
    .container {
      margin-top: 200px;
      width: 80%;
    }

    .dialog {
      max-width: 415px;
      width: 80%;
      border: 2px solid #3b99fc;
      border-radius: 6px;
      box-shadow: 1px 7px 11px rgba(118, 118, 118, 0.32);
    }
    .dialog-headline {
      margin: 0 0 20px;
      font-size: 24px;
      font-weight: 400;
    }
    .dialog summary {
      width: 100%;
    }
    .dialog dl {
      margin-top: 20px;
      margin-bottom: 0;
      border-top: 1px solid #3b99fc;
      padding-top: 20px;
    }
    .dialog dt {
      float: left;
      width: 145px;
      margin-right: 10px;
    }
    .dialog dd {
      margin-left: 0;
      margin-bottom: 5px;
    }
  </style>

  <div class="container">
    <dialog class="dialog" open>
      <section>
        <h2 class="dialog-headline">"html5.2-video-recture.mp4" 파일복사</h2>
        <details>
          <summary> 복사중... <progress value="25" max="100"></progress> 25% </summary>
          <dl>
            <dt>초당 전송 속도:</dt><dd>723KB</dd>
            <dt>로컬 파일이름: </dt><dd>/Desktop/html5.2-vidio-recture.mp4</dd>
            <dt>원격 파일이름: </dt><dd>?Backup/html5.2-video-recture.mp4</dd>
            <dt>재생시간: </dt><dd>00:14:38</dd>
            <dt>컬러 프로파일</dt><dd>HD (1-1-1)</dd>
            <dt>해상도(너비x높이)</dt><dd>1680x1050</dd>
          </dl>
        </details>
    </dialog>
  </div>

  ```


  ```html
 <details> 요소
  - 디스클로저 위젯(disclosure widget, 참고: https://goo.gl/uznvFY)으로 정보를 감추거나, 펼쳐서 보여준다.
    모든 정보를 일시에 공개하지 않고 사용자의 요구에 맞춰 정보를 공개할 수 있다. (화면의 복잡함을 줄임)
    아코디언(Accordion) 컴포넌트와 비슷하게 작동한다.

    참고로 각주(footnote)에는 적합하지 않다.

  [속성]
    open - 페이지 로딩 시, 위젯을 펼쳐 표시하도록 설정

  [사용 예시]
    <details open>
      ...
    </details>

  <summary> 요소
  - <details> 요소의 레이블/캡션(제목), 서머리(요약) 등을 표시한다.
    폼 <fieldset> 요소의 제목을 <legend>가 표시하듯 비슷하다.

  [사용 예시]
    
    <section class="progress window">
      <h1>"Really Achieving Your Childhood Dreams" 파일 복사</h1>
      <details>
      <summary>복사중... <progress max="375505392" value="97543282"></progress> 25%</summary>
      <dl>
        <dt>초당 전송 속도:</dt>
        <dd>452KB/s</dd>
        <dt>로컬 파일이름:</dt>
        <dd>/home/rpausch/raycd.m4v</dd>
        <dt>원격 파일이름:</dt>
        <dd>/var/www/lectures/raycd.m4v</dd>
        <dt>재생시간:</dt>
        <dd>01:16:27</dd>
        <dt>컬러 프로파일:</dt>
        <dd>SD (6-1-6)</dd>
        <dt>영상 크기(너비×높이):</dt>
        <dd>640×480</dd>
      </dl>
      </details>
    </section>
  ```

#### [스크립팅 요소들]

  - HTML에서는 자바스크립트라고 입력을 안해도 자바 스크립트라고 인식하기 때문에 따로 명시할 필요가 없습니다. type="application/ecmascript
  - LINK 태그에 rel 관계성 stylesheet를 명시
  - 크롬 설정에서 debugger에서 disable javascript를 사용하게 되면 자바스크립트가 안되게 환경을 잡아줄 수 있습니다.
  - canvas는 API가 방대하고 비트맵을 그릴 때 사용합니다.

  ```javascript
  js/app.js

  console.log('<script> 요소를 사용해 js/app.js 파일을 HTML 문서에 읽어들였습니다.');
  var bgColor = window.prompt('문서의 배경 색상을 입력해주시겠습니까?', '#eced00');
  document.querySelector('body').style.cssText = 'background: ' + bgColor;
  console.log('<body> 요소에 CSS 스타일을 적용하여 배경 색을 ' + bgColor + ' 색상으로 변경 처리했습니다.');
  ```

  ```css
  css/app.css

  html {
    background: #222;
    height: 100%;
  }

  body {
    height: 50%;
    margin: 0;
  } 
  ```

  ```html
  <link rel="stylesheet" href="css/app.css">

  ```

  ```html
  <stlye>
    body {
       background-color:#96e72a; 
       margin:0; 
       min-height: 100vh; 
       width: 100ww
    }
  </stlye>

  <body>

  <scrpt src="js/app.js"></script>

  <script>
    // JavaScript 코드
    console.log('JavaScript 코드를 실행했습니다.');
    console.log(document.characterSet);
    console.log(document.doctype);
  </script>

  <noscript>
    <p>JavaScript를 지원하지 않습니다.</p>
  <noscript>
  ```

  ```html
 <noscript> 요소
    - 사용자의 웹 브라우저 환경에서 스크립트를 지원되지 않거나, 스크립트가 꺼져있는 경우, 문서에 표시될 문구를 삽입한다.

    [코드 예시]
      <noscript>
        <p>JavaScript를 지원하지 않습니다.</p>
      </noscript>


  <canvas> 요소
    - JavaScript를 사용하여 그래픽(비트맵)을 그릴 때 사용한다.
      <canvas> 요소로부터 2D 또는 WebGL 컨텍스트 객체를 추출해 그래픽을 그릴 수 있다.

    [코드 예시]

      <canvas width="800" height="600"></canvas>

      <script>
        // canvas 드로잉
        var canvas = document.querySelector('canvas');
        var ctx = canvas.getContext('2d');
        ctx.translate(200, 40);
        ctx.beginPath();
        ctx.moveTo(180, 175);
        ctx.fillStyle = '#ff0';
        ctx.arc(180, 175, 60, Math.PI * -0.35, Math.PI * -1.05, true);
        ctx.fill();
        ctx.beginPath();
        ctx.moveTo(190, 190);
        ctx.fillStyle = '#ff0';
        ctx.arc(190, 190, 100, Math.PI * -0.35, Math.PI * 0.95);
        ctx.fill();
      </script>

  ```
#### [유저 인터랙션 속성]
  
  - tabIndex="0"는 포커스를 가질수 없는 요소 이지만 포커스를 가질수 있게해준다. -1을 속성값으로 할시 포커스에서 제외할 수 있습니다.
  - 이미지는 포커스 요소가 아니지만 탭으로 포커스가 가능하게 할 수 있습니다
  - 해당 tabIndex 속성을 해당 요소에 포커스를 없앴다가 생기게 자바스크립트로 해서 유용한 개발을 할 수 있습니다.
  - 논리적 흐름을 방해하지 않도록 해야한다. 위에 나온 흐름대로 해야 한다. tabIndex는 양수를 안 사용 하는 것이 좋다.

  - accessKey같은 경우 사용자 경험이 다릅니다.
  - accessKey는 키보드 단축키를 사용할 수 있다.

  ```
  hidden 속성
      - 모든 HTML 요소들은 hidden 속성을 가질 수 있으며, 요소에 설정되면 요소가
        아직 페이지의 현재 상태와 직접적으로 관련이 없거나 페이지의 다른 부분에서
        내용을 재사용하도록 선언하는 데 사용된다. 브라우저는 hidden 속성이 설정된
        요소를 화면에 렌더링하지 않는다.

        [사용 예시]
          <h1>hidden 속성 사용 예</h1>
          <section id="login">
            <h2>로그인</h2>
            <form>
            ...
            </form>
            <script>
              function login() {
                // 화면 변경
                document.querySelector('#login').hidden = true;
                document.querySelector('#game').hidden  = false;
              }
            </script>
          </section>
          <section id="game" hidden>
            <h2>게임 시작</h2>
            ...
          </section>


    tabindex 속성
      - 요소를 키보드로 탐색할 수 있도록 설정하거나, 제외 또는 순서대로 탐색할 수 있도록 설정할 수 있다.
        "탭(Tab) 이동"이란 용어는 순차적 포커스 탐색을 사용하여 포커스 가능(Focusable) 요소 사이를
        이동하는 것을 의미한다.

        [기본적으로 포커스 가능한 요소들](참고: https://allyjs.io/data-tables/focusable.html)
          폼 컨트롤 요소들           : input, button, textarea, select 등
          href 속성을 가진 요소들     : a, area
          controls 속성을 가진 요소들 : video, audio

        [사용 예시]

          // [양수] 탭 포커스 순서(2번째)를 설정한다.
          // (논리적 포커스 흐름에 방해가 되기에 사용을 권장하지 않음)
          <button
            type="button"
            class="button is-play"
            tabindex="2">재생</button>

          // [0] div 요소는 포커스를 가지지 않는 요소이지만, 포커스를 적용할 수 있게 된다.
          // 컴포넌트 제작 시, 비 포커스 요소에 포커스를 적용해야 할 경우 유용하게 사용됨.
          <div tabindex="0"></div>

          // [-1] 일반적인 포커스 순서에서 제외시킬 수 있다.
          // (JavaScript 프로그래밍으로 포커스 처리 가능)
          // 컴포넌트의 일부 요소를 일시적으로 포커스 순서에서 제외한 후,
          // 목표에 따라 포커스를 다시 활성화 처리할 수 있다.
          <ol class="TOC">
            <li><a href="#pinch">위기</a></li>
            <li><a href="#overcome" tabindex="-1">극복</a></li>
          </ol>


    accesskey 속성
      - 모든 HTML 요소는 accesskey 속성을 가질 수있다. 속성 값은 키보드 단축키로 설정된다.
        하지만 accesskey 속성의 단축키는 브라우저와 운영체제 플랫폼에 의존하고 있어 운영체제마다
        사용자 경험이 달라진다. 쉽게 말해 Windows 사용자와 Mac OSX 사용자가 사용하는
        단축키는 달라진다. (iPhone과 Android 사용자 경험이 다른 것처럼)

        [브라우저 × 운영체제 플랫폼]
          Windows
            Chrome  : Alt + 단축키
            IE      : Alt + 단축키
            Safari  : Alt + 단축키
            Opera   : Alt + 단축키
            Firefox : Alt + Shift + 단축키
          Mac OSX
            Chrome  : Control + Alt + 단축키
            Safari  : Control + Alt + 단축키
            Opera   : Control + Alt + 단축키
            Firefox : Control + 단축키
          Linux
            Chrome  : Alt + 단축키
            Opera   : Alt + 단축키
            Firefox : Alt + Shift + 단축키

        [사용 예시]
          <button
            type="button"
            class="button is-collect"
            accesskey="C"
            onclick="collect()">
            수집
          </button>


    contenteditable 속성
      - contenteditable 속성이 설정된 요소는 사용자가 직접 편집할 수 있도록 만들어 준다.
        값이 true 또는 빈 문자열("")일 경우 편집 허용.
        값이 false 일 경우 편집을 허용하지 않음.

        [사용 예시]
        <p contenteditable>
          ...
        </p>


    draggable 속성
      - 모든 HTML 요소는 draggable 속성을 가질 수 있다.
        값이 true 일 경우 드래그(Drag) 가능.
        값이 false 또는 빈 문자열("")일 경우 드래그 불가능.

        [사용 예시]
        <p draggable="true">
          ...
        </p>
  ```

  ```html
  <button type="button" accesskey="V" class="button is-show">컨테이너 표시</button>

  <div class="container">

    <img
      class="drag-element"
      src="images/fashion-model-pose.png"
      alt="패션 모델"
      width="276" height="417">

    <div class="dropzone">
      <p>Drop Zone</p>
    </div>

  </div>
  ```

  ```css
  css/App.css
  <style>
    html, body {
      height: 100%;
    }
    body {
      margin: 0;
    }
    .demo {
      display: flex;
      justify-content: center;
      align-items: center;
    }
    .button.is-show {
      cursor: pointer;
      position: fixed;
      top: 40px;
      left: 40px;
      border: 1px solid transparent;
      border-radius: 4px;
      padding: 1em 1.4em;
      font-family: "Spoqa Han Sans";
      font-weight: 400;
      font-size: 15px;
      color: #454545;
      background: #eeeeee;
      transition: all 0.1s ease-out;
    }
    .button.is-show:hover {
      background: #11a981;
      color: #fff;
    }
    .button.is-show:active {
      transform: scale(0.98);
      opacity: 0.8;
    }
    .button.is-show:focus {
      outline: none;
      border-color: #11a981;
    }

    .container {
      display: flex;
      justify-content: space-around;
      align-items: center;
      flex-flow: row wrap;
      width: 100vw;
    }
    .container[hidden] {
      display: none;
    }
    .dropzone {
      position: relative;
      display: flex;
      justify-content: center;
      align-items: center;
      width: 400px;
      height: 500px;
      border: 10px solid #eee;
      transition: all 0.24s ease-in-out;
    }
    .dropzone p::selection {
      background: #eee;
      color: #454545;
    }
    .dropzone p {
      position: absolute;
      z-index: -1;
      margin: 0;
      font-size: 56px;
      font-weight: 900;
      color: #eee;
    }
    .drag-element {
      user-select: none;
    }
  </style>
  ```

  ```javascript
  function hiddenDemo() {
    var showButton = document.querySelector('.button.is-show');
    var container  = document.querySelector('.container');
    showButton.addEventListener('click', function(){
      container.removeAttribute('hidden');
    });
  }

  function dragDemo() {

    var draggableEl = document.querySelector('img[draggable="true"]');
    var dropZone    = document.querySelector('.dropzone');

    if (!draggableEl) { return; }

    function onDragStart(e) {
      console.log('드래그 스타트(Drag Start)');
      var src    = e.target.getAttribute('src');
      var alt    = e.target.getAttribute('alt');
      var width  = e.target.getAttribute('width');
      var height = e.target.getAttribute('height');
      e.dataTransfer.setData('src', src);
      e.dataTransfer.setData('alt', alt);
      e.dataTransfer.setData('width', width);
      e.dataTransfer.setData('height', height);
    }

    function onDragOver(e) {
      console.log('드래그 오버(Drag Over)');
      e.preventDefault();
    }

    function onDragEnter(e) {
      console.log('드래그 엔터(Drag Enter)');
      e.preventDefault();
      e.target.style.borderColor = '#11a981';
    }

    function onDragLeave(e) {
      console.log('드래그 리브(Drag Leave)');
      e.preventDefault();
      dropZone.style.borderColor = '#eee';
    }

    function onDragEnd(e) {
      console.log('드래그 엔드(Drag End)');
      e.preventDefault();
      dropZone.style.borderColor = '#eee';
    }

    function onDrop(e) {
      console.log('드롭(Drag Drop)');
      e.preventDefault();
      var src    = e.dataTransfer.getData('src');
      var alt    = e.dataTransfer.getData('alt');
      var width  = e.dataTransfer.getData('width');
      var height = e.dataTransfer.getData('height');
      var img = new Image();
      img.setAttribute('src', src);
      img.setAttribute('alt', alt);
      img.setAttribute('width', width);
      img.setAttribute('height', height);
      e.target.appendChild(img);
      draggableEl.style.opacity = 0;
    }

    var img = null;

    function onKeyUp(e) {
      if ( !img && e.key.toLowerCase() === 'arrowright' ) {
        console.log('오른쪽 방향 화살표(→) 키를 눌렀습니다.');
        img = new Image();
        var target = e.target;
        img.setAttribute('src', target.src);
        img.setAttribute('alt', target.alt);
        img.setAttribute('width', target.width);
        img.setAttribute('height', target.height);
        dropZone.appendChild(img);
        draggableEl.style.opacity = 0;
        draggableEl.setAttribute('tabindex', -1);
        img.addEventListener('keyup', onKeyUp);
        img.setAttribute('tabindex', 0);
      }
      if ( img && e.key.toLowerCase() === 'arrowleft' ) {
        console.log('왼쪽 방향 화살표(←) 키를 눌렀습니다.');
        dropZone.removeChild(img);
        draggableEl.style.opacity = 1;
        draggableEl.setAttribute('tabindex', 0);
        img = null;
      }
    }

    draggableEl.addEventListener('keyup', onKeyUp);
    draggableEl.addEventListener('dragstart', onDragStart);
    draggableEl.addEventListener('dragend', onDragEnd);
    dropZone.addEventListener('dragover', onDragOver);
    dropZone.addEventListener('dragenter', onDragEnter);
    dropZone.addEventListener('dragleave', onDragLeave);
    dropZone.addEventListener('drop', onDrop);

  }

  hiddenDemo();
  dragDemo();
  ````
#### [문서 메타데이터 요소들]
  
  ```html
    <meta name="description" content="웹페이지 내용을 요약해서 기술">
    <meta name="keywords" content="웹페이지에 주요 키워드를 콤마(,)로 구분하여 작성">
    <meta name="author" content="웹페이지 제작자">
    <meta name="robots" content="index">
    <meta name="viewport" content="width="device-width, intial-scale=1"">
    <link href="default.css" rel="stylesheet" title="기본 스타일">
    <link href="fancy.css" rel="alternate stylesheet" title="팬시">
    <link href="basic.css" rel="alternate stylesheet" title="베이직"> 
    <base target="_blank" href="http://www.example.com/">
  ```

  - 메타요소는 헤더에 정의되는 문서 정보를 보여주는 요소입니다.
  - 대부분 브라우저 요소는 head를 자동으로 생성해 줍니다.
  - title Bar에서는 어떠한 태그를 쓰더라도 생략이 됩니다.
  - description, keywords, author 검색엔진 최적화 관점에서 매우 유용한 네임들 입니다.
  - viewport를 설정하지 않는다면 양쪽 여백을 자동으로 지정해줍니다. width="device-width, intial-scale=1"
  - base를 쓰게되면 기본 url주소를 설정할 수 있습니다.

  ```html
    <head> 요소
      - 문서의 제목과 스타일시트, 스크립트 링크 또는 선언을 포함하는 문서의 일반적인 정보(메타데이터)를 제공한다.
        대부분 브라우저는 마크업에서 <head> 요소가 생략될 경우, 자동으로 <head> 요소를 생성하지만 일부는 그렇지 않다.

        [자동으로 <head> 요소를 생성하지 않는 브라우저 환경]
          - Android <= 1.6
          - iPhone  <= 3.1.3
          - Opera   <= 9.27
          - Safari  <= 3.2.1.
          - Nokia 90


    <title> 요소
      - 브라우저의 타이틀 바(Title Bar)나 페이지 탭에 보여지는 문서의 제목을 정의.
        텍스트만 포함할 수 있으며 포함된 태그들은 해석되지 않음.


    <meta> 요소
      - 다른 메타 요소들(<title>, <base>, <link>, <style>)로 나타낼 수 없는 메타데이터를 정의할 때 사용.

        [메타데이터의 종류]

          - charset이 설정된 경우:
              charset 선언. 즉 웹페이지를 작성하는 일련의 형식에 사용되는 문자 인코딩(charset)에 대한 설정.
              이 속성보다 요소의 lang 속성이 우선하여 적용됨. (즉, 덮어쓰기 됨. 예: <div lang="fr">)

          - http-equiv 속성이 설정된 경우:
              pragma 지시어(Directive)로 일반적으로 웹서버가 제공하는 웹페이지가
              어떻게 제공되어야 하는지에 대한 정보를 제공.

              [예시]
                ✤ HTML 5에서는 더 이상 아래와 같이 사용되길 권장하지 않음.
                  <meta http-equiv="Content-Type" content="text/html;charset=UTF-8">
                ✤ 3초 뒤에 url 값에 설정된 페이지로 이동하게 됨.
                  <meta http-equiv="refresh" content="3;url=https://google.com">

          - name 속성이 설정된 경우:
              문서 수준 메타 데이터의 이름을 정의하며, content 속성 값을 통해 설정.

        [속성]
          - charset
          - http-equiv
          - content
              이 속성은 컨텍스트에 따라 http-equiv또는 name속성 과 연결된 값을 제공.
          - name
            - application name:
                웹 페이지에서 실행중인 웹 애플리케이션 이름 정의.
                간단한 웹 페이지는 application-name 메타를 정의해서는 안됨.
            - description
                페이지의 내용에 대한 짧고 정확한 요약을 설정.
            - keywords
                쉼표로 구분된 문자열로 페이지의 내용과 관련된 키워드를 설정.
            - author
                문서 작성자의 이름을 정의.
            - robots
                검색 로봇이 웹 페이지를 크롤링하는 동작에 대한 정의.
                  - index
                  - noindex
                  - follow
                  - nofollow
                  - noarchive
                  - nosnippet
                  - noimageindex
            - viewport
                (비표준) 초기 viewport 크기 설정에 관한 힌트를 제공.
                이 속성은 몇 개의 모바일 디바이스에 의해서만 사용됨.
                  - width
                  - height
                  - initial-scale
                  - maximum-scale
                  - minimum-scale
                  - user-scalable


    <link> 요소
      - 현재 문서와 외부 리소스와의 관계(relation)를 명시.
        이 요소는 스타일시트를 링크 하는데 가장 많이 사용됨.

        [속성]
          - rel      : 문서와의 관계 명시.
          - type     : 링크된 리소스 MIME 타입 정의. (기본 적용: text/css)
          - href     : 링크된 리소스 URL 설정.
          - hreflang : 링크된 리소스의 언어 설정.
          - media    : 링크된 리소스가 적용될 미디어(media)를 설정.

        [사용 예시]

          기본 스타일시트 설정
            <link href="style.css" rel="stylesheet">

          대체 스타일시트 설정: View > Page Style 메뉴에서 사용할 스타일시트를 고를 수 있다. (Chrome은 해당 X)
            <link href="default.css" rel="stylesheet" title="기본 스타일">
            <link href="fancy.css" rel="alternate stylesheet" title="팬시">
            <link href="basic.css" rel="alternate stylesheet" title="베이직">


    <style> 요소
      - 문서나 문서 일부에 대한 스타일 정보를 포함.
        기본적으로 CSS 언어가 사용됨.

        [속성]
          - type
          - media
          - scoped
          - title
          - disabled

        [사용 예시]

          일반적인 사용 예:
            <style type="text/css">
              body {
                color: #323232;
              }
            </style>

          scoped 속성 사용 예: ❖ 현재 제대로 지원하는 브라우저 없음.
            <section>
              <style scoped>
                p { color: #902c1f; }
              </style>
              <p> ... </p>
            </section>


    <base> 요소
      - 문서에 포함된 모든 상대 URL들의 기준 URL을 나타냄.
        한 문서에 하나의 <base> 요소만 존재해야 함.

        [사용 예시]
          <base target="_blank" href="http://www.example.com/">
  ```
</details>