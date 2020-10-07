# Sujin's portfolio(진짜최종!!:sweat_smile:)

- [x] Welcome to the course!
- [x] Plan & Design
- [x] Git & Github
- [x] Head
- [x] HTML: Markup
- [x] CSS: Essentials (개념모음집)
- [x] 보너스 챕터
- [] CSS: Styling
- [] JavaScript: Fun dynamics
- [] Last touch
- [] Publish

# Git & Github

---

### :one: Git

- 내가 원하는 시점에서 버전,버전으로 등록할 수 있다.
- Git은 버전별로 파일이 어떻게 저장되는지 모두 기록되어 남는다.
- 즉, 내가 지정한 폴더에 Git이라는 파일이 생성된다.
- 내 PC 자체에 문제 생길때는 어떻게 해야할까?

### :two: Github

- Git으로 관리되는 프로젝트는 대표적으로 두가지이다.
  - Git
  - Bitbucket
- Git하면 Branch를 떼어놓을 수 없다.(:branch란 내가 commit해 나가면서 생기는 줄기로, 한 부분만 커밋해나가면 이 branch는 Master branch가 된다.)
- Master branch에서 기존에 진행되는 코드는 변경하지 않고 다른 버전으로 새로운 커밋을 만들어 나갈 수 있다.

#### [GitHub](http://github.com "깃허브")

#### [GitHub](https://git-scm.com/docs/gittutorial "깃튜토리얼")

---

# Head

---

### :one: Metadata

- defer을 이용하는 것은 html파일이 파싱(pursuing)되는 동안 js파일을 동시에 다운받는다. 다만, html이 파싱이 모두 완료가 된 후에 자바스크립트가 실행되므로 defer가 굉장히 좋은 옵션이다.

```css
<link rel="icon" type="image/png" href="imgs/favicon.png">

font-family: 'Open Sans', sans-serif;
```

[Google Fonts](https://fonts.google.com/ "Google Fonts")

---

# HTML: Markup

---

### :one: BEM

- B: Block(:그 자체)
- E: Element(:'블록 안에 있는' 더이상 나뉠수없는 개개별 객체들)
- M: Modifier(:종류)
- => 즉, 블럭/엘레멘트/모디파이어/로 나눠 이름 작성하는 것을 의미(: block\_\_element--modifier)
- ex:
  - .cards
  - .card
  - .card\_\_img
  - .card\_\_title
  - .card\_\_description
  - .card\_\_button
  - .button\_\_pink
  - .button\_\_blue

:sparkles: 이번 챕터의 핵심 :sparkles:

[BEM](http://getbem.com/introduction/ "BEM")
[BEM 101 by CSS-Tricks](https://css-tricks.com/bem-101/ "BEM 101 by CSS-Tricks")
[10 Common Problems And How To Avoid Them](https://www.smashingmagazine.com/2016/06/battling-bem-extended-edition-common-problems-and-how-to-avoid-them/ "10 Common Problems And How To Avoid Them")

---

### :two: Sectioning(1)

- navbar/about/skills/work/testimonials/contact/처럼 sectioning 작업을 먼저 해준다.

:sparkles: 이번 챕터의 핵심 :sparkles:

```html
<!-- Nav -->
<nav id="navbar"></nav>
<!-- About -->
<section id="about"></section>
<!-- Skills -->
<section id="skills"></section>
<!-- Work -->
<section id="work"></section>
<!-- Testimonials -->
<section id="testimonials"></section>
<!-- Contact -->
<section id="contact"></section>
```

---

### :three: Sectioning(2)

- navbar/about/skills/work/testimonials/contact/처럼 sectioning해줬던 것들을 이용해 안의 내용들을 마크업해보자.

:sparkles: 이번 챕터의 핵심 :sparkles:

```html
<!-- Nav -->
<nav id="navbar">
  <div class="navbar__logo"></div>
  <div class="navbar__menu"></div>
</nav>
```

---

# CSS: Essentials (개념모음집)

---

### :one: Box model

- 내가 설정한 css 스타일링과 달리 너무 사이즈가 너무 변했다면 99%는 Box sizing때문이다.
- `box-sizing: content-box;`가 기본 값이다.
- 컨텐츠의 width와 height을 유지하면서 padding, margin을 넣고 싶다면 `box-sizing: border-box;`를 해줘야한다.

```css
.box3 {
  padding: 20px;
  box-sizing: border-box;
}
```

## [Box model](https://developer.mozilla.org/en-US/docs/Web/CSS/box-sizing "Box model")

### :two: Absolute vs Static

- css에서의 레이아웃에서는 포지션이 너무 중요하다.
- 또한 훗날 flex box, react를 이용할때도 position은 굉장히 중요하다.
- position의 기본값은 `position: static`이다.
- 먼저 `position: reletive`와 `position: absolute`의 차이점을 알고 넘어가자.
- `position: reletive`: 원래 있던 자리를 **유지**하면서 그 자리에서 **상대적으로** 지정한 top, left, right, bottom만큼 위치를 이동한다.
- `position: absolute`: absolute는 relative를 기준으로 하여 이동한다.(기준이 잡혀있지 않으면 position: static이 아닌 부모(즉 기본값인 static이 아닌 body)를 기준으로 삼아 원래 있던 자리를 **유지 못하고** 쏙 빠져나오기에 주변에 함께 있던 아이템들의 재배치가 일어난다.)

[Position](https://developer.mozilla.org/en-US/docs/Web/CSS/position "position")
[containing_Block](https://developer.mozilla.org/en-US/docs/Web/CSS/Containing_Block "Containing_Block")

---

### :three: Sticky vs Fixed

- `position: static`, `position: relative`, `position: sticky`: 그 박스 안에서 포지션 변경이 일어난다.
- `position: absolute`: 들어있는 근접한 부모 박스들 중에 static이 아닌 박스에 포지션 변경이 일어난다.
- `position: fixed`: **부모 박스와 상관 없이** viewport(브라우저) 포지션 변경이 일어난다.
- sticky는 position을 지정해줘야하며, 또 그 자리를 유지하면서 스크롤링 시엔 고정이 되는데, fixed는 완전히 기존의 문서에서 나와 viewport(브라우저)에 포지셔닝된다.

---

### :four: Centering trick(중간정렬)

- **flex box**를 이용할 경우엔 중심축을 정렬하는 justify-content와 반대쪽에서 정렬하는 align-items를 사용하면 되지만 flex box를 이용할 때가 아닐 경우 **수직, 수평 정렬**하는 방법에 대해서 알아보자.
- `margin: auto;`: block레벨일 경우에만 (가로)중간정렬 가능.
- `text-align: center;`: block 레벨이 아닐 경우에만 (가로)중간정렬 가능.
- `transform: translate(50%, 50%);`: 움직이는(lotation) 요소들을 포함한 요소들을 x축 y축 50%씩 지정해서 (세로)중간정렬이 가능.
- `margin: auto;`, `line-height: 100px;`를 같이 사용해야 텍스트일 경우에 중간정렬이 가능.

## [margin](https://developer.mozilla.org/en-US/docs/Web/CSS/margin "margin")

### :five: Responsive background

- Background속성에 대해 조금 더 알아보자.
- `background-repeat: no-repeat;`: 이미지 반복하지 않음.
- `background-position: center;`: 이미지의 중간 부분을 중심으로 해서 배경화면으로 지정.
- `background-size: cover;`: 남은 여백을 차지하면서 늘어난다.
- `background: center/cover no-repeat`: margin-left, margin-right가 아닌 한번에 margin해서 사용할 수 있듯이 center/cover no-repeat으로 작성하면 코드가 더욱 짧고 쉽다.

[background](https://developer.mozilla.org/en-US/docs/Web/CSS/background "background")
[background-image](https://developer.mozilla.org/en-US/docs/Web/CSS/background-image "background-image")

---

### :six: Transformation

- 동적인 요소를 가미하는 방법을 알아보자.
- 원래 있던 모양을 변화시킨다는 것은 transform 옵션을 사용한다.
- `transform: translateX(100px);`: x축으로 100px이동
- `transform: translate(50px, -20px);`: x축으로 50px, y축으로 -20px 이동
- `transform: scale(1.2);`: 1.2배 크기 키움
- `transform: rotate(45deg);`: 45도 각도 기울기
- `transform: translate(100px, 100px) scale(2) rotate(46deg);`: 위 네가지 한줄로 한번에 적용

## [transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform "transform")

### :seven: Magic animation:heart:

- transition을 이용해 **어떤 프로퍼티를**, **몇초동안 할것인지**, **어떤 애니메이션** 줄 것인지를 지정할 수 있다.
- `transition: background-color 300ms linear;`: 배경색을, 300ms동안, linear애니메이션을 줄것이다.
- `transition: all 2s ease;`: 모두 2초동안 ease애니메이션을 줄것이다.

[transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition "transition")
[animation-timing-function](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timing-function "animation-timing-function")
[transition-speed](https://cubic-bezier.com/ "transition-speed")

---

# 보너스 챕터

---

### :one: CSS Variable의 모든 것

- hard coded: 모든 속성마다 일일이 다 작성해주는 것.
- 반복되어져서 사용되는 수치가 있다면 그것을 **상수로 지정**해서 사용하는 것이 훨씬 효율적이다.
- JS에서는 const로 지정해서 사용하는 것 처럼 css에서도 **custom properties**를 통해 상수로 지정해서 사용할 수 있다. `--*`

```css
.first {
  --font-size: 32px;
  font-size: var(--font-size);
}
```

- 이렇게 정의한 변수는 그의 **모든 자식요소에만** 접근이 가능하다.
- 그러나 형제 노드의 자식요소에는 접근이 불가능하므로 전체 접근이 가능할 수 있도록 하기 위해선 가장 높은 노드(body)에 `--*`를 적용시키면 된다.

```css
:root {
  --font-size: 32px;
}

.first {
  font-size: var(--font-size);
}

.second {
  font-size: calc(var(--font-size) * 2);
}
```

- `font-size: calc(var(--font-size) * 2);`에서의 calc는 계산해주는 속성값이다.
- 미디어쿼리를 이용할때 위의 variable들이 유용하게 사용되는데 `:root{}`를 브라우저 크기마다 변수의 값을 재설정해줄 수도 있다는 점이다.

```css
@media screen and (max-width: 768px) {
  :root {
    --background-color: salmon;
    --text-color: whitesmoke;
    --base: 4px;
  }
}
```

## [custom properties](https://developer.mozilla.org/en-US/docs/Web/CSS/--* "custom properties")

### :two: HTML 유용한 Data-

- data attribute는 HTML5에서 추가되었는데, html태그 자체에 제공하는 속성뿐만 아니라 내가 원하는 데이터 DOM요소 속 html 요소에 추가할 수 있다. 내가 원하는 정보를 요소에 추가하고 싶을 때 사용할 수 있다.
- `data-*`처럼 원하는 값을 쓰면 된다.
- [] 속성 선택자를 이용해 속성을 선택해서 사용할 수 있음.
- d

:sparkles: 이번 챕터의 핵심 :sparkles:

> `인라인 코드`

```javascript
function test() {
  console.log("hello world!");
}
```

[Use_data_attributes](https://developer.mozilla.org/en-US/docs/Learn/HTML/Howto/Use_data_attributes "Use_data_attributes")

---

# CSS: Styling

---

### :zero: Global set up & typography(1)

- 우리가 프로그래밍을 하면서 **변수를 지정**하듯이 CSS에서도 변수를 지정해줄 수 있다.
- 페이지 전반에서 사용되는 color, font-size, font-weight등을 한번 정의한 다음 작업할 때 계속적으로 사용이 가능하다. (변경할 스타일이 생길 경우, 사용되어진 곳을 일일이 찾아서 변경하는 것이 아니라 :root에서 Global setting한 곳에서 변경하면 된다.)

```css
/*Global*/
/* Global */
:root {
  /* Color */
  --color-white: #ffffff;
  --color-light-white: #eeeeee;
  --color-dark-white: #bdbdbd;
  --color-pink: #fe918d;
  --color-dark-pink: #ff6863;
  --color-dark-grey: #4d4d4d;
  --color-grey: #616161;
  --color-light-grey: #7c7979;
  --color-blue: #73aace;
  --color-yellow: #fff7d1;
  --color-orange: #feb546;
  --color-black: #000000;

  /* Font size */
  --font-large: 48px;
  --font-medium: 28px;
  --font-regular: 18px;
  --font-small: 16px;
  --font-micro: 14px;

  /* Font weight */
  --weight-bold: 700;
  --weight-semi-bold: 600;
  --weight-regular: 400;

  /* Size */
  --size-border-radius: 4px;

  /* Animation */
  --animation-duration: 300ms;
}
```

- Global setting이 마치고 난 후에는 공통적으로 적용해야할 **Universal tags**도 정의해보자.(`box-sizing: border-box;`은 내가 padding을 줘도 동일한 height과 width되도록 하는것)

```css
/* Universal tags */
* {
  box-sizing: border-box;
}

body {
  font-family: "Open Sans", sans-serif;
  margin: 0;
  cursor: default;
}

a {
  text-decoration: none;
  color: var(--color-white);
}

ul {
  list-style: none;
  padding-left: 0;
}

button {
  background-color: transparent;
  cursor: pointer;
  border: none;
  outline: none;
}
```

---

### :zero: Global set up & typography(2)

- 웹페이지 전체에서 쓰일 h1,h2,h3,p의 스타일링을 먼저 설정하고 시작하자.(=> **typography**라 한다.)

```css
/* Typography */
h1 {
  font-size: var(--font-large);
  font-weight: var(--weight-bold);
  color: var(--color-black);
  margin: 16px 0px;
}

h2 {
  font-size: var(--font-medium);
  font-weight: var(--weight-semi-bold);
  color: var(--color-black);
  margin: 8px 0;
}

h3 {
  font-size: var(--font-regular);
  font-weight: var(--weight-regular);
  color: var(--color-black);
  margin: 8px 0;
}

p {
  font-size: var(--font-regular);
  font-weight: var(--weight-regular);
  color: var(--color-black);
  margin: 4px 0;
}
```

---

### :one: Nav

- 기본적으로 logo와 nav는 block레벨이므로 한줄에 하나씩인 것을 볼 수 있다.
- :star:`cursor: default;`는 웹페이지 전체의 mouse cursor모양을 text cursor모양이 아닌, 우리가 일반적으로 알고 있는 **화살표 모양**으로 바꿔준다.(default는 기본값)

```css
body {
  ...
  cursor: default;
}
```

- menu부분의 active를 하나 추가한 후 navbar**menu**item은 `cursor: pointer;`로 해준다.

```css
.navbar__menu__item {
  ...
  cursor: pointer;
}
```

- active된 상태일 때의 스타일 지정

```css
.navbar__menu__item.active{
  ...
  border:
}
```

```css
/* Navbar */
#navbar {
  display: flex;
  justify-content: space-between;
  background-color: var(--color-pink);
  align-items: center;
  color: var(--color-white);
  padding: 16px;
}

.navbar__logo {
  font-size: var(--font-medium);
  font-weight: var(--weight-semi-bold);
}

.navbar__menu {
  display: flex;
}

.navbar__menu__item {
  padding: 8px 12px;
  margin: 0 4px;
  cursor: pointer;
  border-radius: var(--size-border-radius);
}

.navbar__menu__item.active {
  border: 1px solid var(--color-white);
}

.navbar__menu__item:hover {
  background-color: var(--color-dark-pink);
  border-radius: var(--size-border-radius);
}
```

---

### :two: Home

```css
/* Home */
#home {
  background: url("imgs/home-background.png") center/cover no-repeat;
  padding: 40px;
  text-align: center;
}

.home__avatar {
  width: 250px;
  height: 250px;
  border-radius: 50%;
  border: 2px solid var(--color-light-white);
}

.home__title,
.home__description {
  color: var(--color-white);
}

.home__contact {
  color: var(--color-white);
  font-size: var(--font-regular);
  font-weight: var(--weight-bold);
  margin: 24px;
  padding: 8px 12px;
  border: 2px solid var(--color-white);
  border-radius: var(--size-border-radius);
}
```

- `center/cover no-repeat`은
- `text-align: center;`는

---

### :three: About me

- **Section common**을 지정해보자

```css
.section {
  padding: 50px;
  text-align: center;
  max-width: 1200px;
}
```

- `max-width: 1200px;`을 지정하는 이유는 보통 데스크탑에서 편히 볼 수 있는 너비이다.
- `display: flex;`는 한줄에 하나로 몰아 놓도록 묶어주는 것.

```css
/* About */
.about__majors {
  display: flex;
  justify-content: space-between;
  margin: 80px 0;
}

.major__icon {
  width: 170px;
  height: 170px;
  line-height: 170px;
  font-size: 70px;
  margin: auto;
  border: 2px solid var(--color-blue);
  border-radius: 50%;
  margin-bottom: 16px;
  color: var(--color-blue);
}

.major__icon i {
  transition: all var(--animation-duration) ease;
}

.major__icon:hover i {
  color: var(--color-pink);
  transform: rotate(-30deg) scale(1.1);
}

.major__title,
.major__description {
  color: var(--color-dark-grey);
}

.major__description {
  font-size: var(--font-small);
}

.job {
  display: flex;
  align-items: center;
}

.job__description {
  margin: 0 16px;
  text-align: left;
}

.job__name,
.job__period {
  color: var(--color-light-grey);
}

.job__name {
  font-size: var(--font-small);
}

.job__period {
  font-size: var(--font-micro);
}
```

---

### :four: Skills

- `flex-basis: 60%;` 처럼 분할된 아이템들의 크기가 자동적으로 늘어나게 하기 위해서는 **아이템별로 flex-basis**를 줘야한다.

```css
.skillset__left {
  flex-basis: 60%;
}
.skillset__right {
  flex-basis: 40%;
}
```

```css
/* Skills */
#skills {
  background-color: var(--color-yellow);
}

.skillset {
  display: flex;
  background-color: var(--color-light-grey);
  color: var(--color-light-white);
  margin: 20px 0;
}

.skillset__title {
  color: var(--color-white);
}

.skill__description {
  display: flex;
  justify-content: space-between;
}

.skillset__left {
  flex-basis: 60%;
  background-color: var(--color-dark-grey);
  padding: 20px 40px;
}

.skill {
  margin-bottom: 32px;
}

.skill__bar {
  width: 100%;
  height: 3px;
  background-color: var(--color-grey);
}

.skill__value {
  width: 100%;
  height: 3px;
  background-color: var(--color-orange);
}

.skillset__right {
  flex-basis: 40%;
}

.tools {
  background-color: var(--color-grey);
}

.tools,
.etc {
  padding: 20px;
}
```

---

### :five: Work (projects)

- `active`라는 클래스를 이용해, active되거나 hover되면 색상이 변화되도록 해보자.

```html
<button class="category__btn active"></button>
```

```css
.category__btn.active,
.category__btn:hover {
  background-color: var(--color-pink);
}
```

- **재미있는 효과주기**: `category__btn`이 hover, active인 상태일때 `category__count`의 효과.

```css
.category__btn:active .category__count,
.category__btn:hover .category__count {
  opacity: 1;
  top: 0;
}
```

- `active`

```html
<button class="category__btn active"></button>
```

```css
/* Work */
.work__categories {
  margin: 40px;
}

.category__btn {
  border: 1px solid var(--color-dark-white);
  border-radius: var(--size-border-radius);
  font-size: var(--font-regular);
  padding: 8px 48px;
}

.category__btn.active,
.category__btn:hover {
  background-color: var(--color-pink);
  color: var(--color-white);
}

.category__count {
  background-color: var(--color-orange);
  color: var(--color-white);
  display: inline-block;
  border-radius: 50%;
  width: 24px;
  height: 24px;
  line-height: 24px;
  position: relative;
  top: -20px;
  left: 4px;
  opacity: 0;
  transition: all var(--animation-duration) ease-in;
}

.category__btn.active .category__count,
.category__btn:hover .category__count {
  opacity: 1;
  top: 0;
}

.work__projects {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}

.project {
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 280px;
  height: 250px;
  margin: 2px;
  background-color: var(--color-light-white);
}

.project__img {
  max-width: 100%;
  max-height: 100%;
  align-self: center;
}

.project__description {
  position: absolute;
  background-color: black;
  display: flex;
  flex-direction: column;
  justify-content: center;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
  opacity: 0;
  transform: translateY(10px);
  transition: all var(--animation-duration) ease-in;
}

.project:hover .project__description {
  opacity: 0.8;
  transform: translateY(0px);
}

.project__description h3 {
  color: var(--color-white);
}

.project__description h3:after {
  content: "";
  display: block;
  position: relative;
  left: 50%;
  width: 25px;
  height: 2px;
  margin-left: -12px;
  margin-top: 8px;
  background-color: var(--color-dark-white);
}
```

---

### :six: Testimonials

```css
/* Testimonials */
#testimonials {
  background-color: var(--color-light-white);
}

.testimonials {
  margin: 40px;
}

.testimonial {
  display: flex;
  margin: 32px 0;
}

.testimonial__avatar {
  width: 150px;
  height: 150px;
  border-radius: 50%;
}

.testimonial__avatar:nth-child(odd) {
  margin-right: 40px;
}

.testimonial__avatar:nth-child(even) {
  margin-left: 40px;
}

.testimonial__speech-bubble {
  padding: 18px;
  background-color: var(--color-white);
  border-radius: var(--size-border-radius);
}

.testimonial__speech-bubble {
  color: var(--color-light-white);
}

.testimonial__speech-bubble a {
  color: var(--color-pink);
}
```

---

### :seven: Contact

```css
/* Contact */
#contact {
  background-color: var(--color-pink);
}

.contact__title,
.contact__email,
.contact__rights {
  color: var(--color-white);
}

.contact__title {
  margin: 32px 0;
}

.contact__links {
  font-size: var(--font-large);
  margin: 24px 0;
}

.contact__links i {
  transition: var(--animation-duration) ease-in;
}
.contact__links i:hover {
  transform: scale(1.1);
  color: var(--color-yellow);
}
```

---

### :eight: Make it responsive nav

```css
/* Toggle */
.navbar__toggle-btn {
  position: absolute;
  display: none; /* 브라우저 너비가 768px 이상일 경우엔 보이지 않아야 한다. */
  top: 24px;
  right: 32px;
  font-size: 24px;
  color: var(--color-white);
}
```

---

### :nine: Responsive web site

```css
/* For below 768px screen width */
@media screen and (max-width: 768px) {
  .navbar__toggle-btn {
    display: block; /* 보이지 않았던 toggle이 보이게. */
  }

  #navbar {
    flex-direction: column;
    align-items: flex-start;
  }

  .navbar__menu {
    flex-direction: column;
    text-align: center;
    width: 100%;
    display: none;
  }

  .about__majors {
    flex-direction: column;
  }

  .major {
    margin-bottom: 38px;
  }

  .skillset {
    flex-direction: column;
  }

  .project {
    flex-grow: 1;
  }

  .testimonial__avatar {
    width: 80px;
    height: 80px;
  }
}
```

---

# JavaScript: Fun dynamics

---

### :one: Transparent navbar

- **navbar를 투명하게 한 후, 스크롤링 시 진한색상으로 변경되는 효과주기**
- css 먼저.

```css
#navbar {
  display: flex;
  justify-content: space-between;
  background-color: var(--color-pink);
  align-items: center;
  color: var(--color-white);
  padding: 16px;
}
```

:arrow_down_small::arrow_down_small::arrow_down_small:

```css
#navbar {
  position: fixed;
  width: 100%;
  display: flex;
  justify-content: space-between;
  background-color: transparent;
  align-items: center;
  color: var(--color-white);
  padding: 16px;
}
```

- 이제 **JS로 해야하는 것**
- 1. 스크롤링되는 걸 알아야한다. 스크롤링 되면 navbar높이만큼 내려갔을때 navbar를 핑크색상으로 바꿔보자.
- 2. 먼저 윈도우가 스크롤링될 때, navbar의 height를 알아와야 한다. (height만큼 스크롤링 되면 배경색을 바꿔줄 것이므로.)=>**getBoundingClientRect**
- 구글 검색키워드: `javascript scroll position`, `javascript element size`

```javascript
const navbar = document.querySelector("#navbar");
const navbarHeight = navbar.getBoundingClientRect().height;
document.addEventListener("scroll", () => {
  console.log(window.scrollY);
  console.log(`navbarHeight: ${navbarHeight}`);
  if (window.scrollY > navbarHeight) {
    navbar.classList.add("navbar--dark");
  } else {
    navbar.classList.remove("navbar--dark");
  }
});
```

- 이제 **CSS로 해야하는 것**

```css
  ...
  transition: all var(--animation-duration) ease-in-out;
  z-index: 1;
}

#navbar.navbar--dark {
  background-color: var(--color-pink);
  padding: 8px;
}

```

[Window.scrollY](https://developer.mozilla.org/en-US/docs/Web/API/Window/scrollY "Window.scrollY")
[Determining the dimensions of elements](https://developer.mozilla.org/en-US/docs/Web/API/CSS_Object_Model/Determining_the_dimensions_of_elements "Determining the dimensions of elements")

---

### :two: Scroll to section

- 아이템을 **클릭하면 원하는 섹션으로 스크롤링 되는 것**을 해보자.

1. navbarMenu라는 상수에 querySelector로 값을 받아오자.

```javascript
const navbarMenu = document.querySelector(".navbar__menu");
```

2. navbarMenu에 클릭이 되면, 내가 등록한 함수()가 클릭이 되게 할 것이다.(dataset에 data들이 할당되어진다.)

```javascript
const navbarMenu = document.querySelector(".navbar__menu");
navbarMenu.addEventListener("click", (event) => {
  console.log(event.target.dataset.link);
});
```

```html
<ul class="navbar__menu">
  <li class="navbar__menu__item active" data-link="#home">Home</li>
  <li class="navbar__menu__item" data-link="#about">About</li>
  <li class="navbar__menu__item" data-link="#skills">Skills</li>
  <li class="navbar__menu__item" data-link="#work">My work</li>
  <li class="navbar__menu__item" data-link="#testimonials">Testimonials</li>
  <li class="navbar__menu__item" data-link="#contact">Contact</li>
</ul>
```

- 이동하고자 하는 섹션의 id를 받아오긴 했는데 이것들을 통해 어떻게 스크롤링 할 수 있을까?
- 구글검색: `Javascript scroll to id`

```javascript
const navbarMenu = document.querySelector(".navbar__menu");
navbarMenu.addEventListener("click", (event) => {
  console.log(event.target.dataset.link);
  const target = event.target;
  const link = target.dataset.link;
});
```

- 우리가 가려는 element는 scrollTo라는 상수에, document.querySelector()를 이용해 ()안에는 link를 받아와서, scrollTo에 scrollIntoView()로 옵션은 { behavior: "smooth" }를 넣는다.

```javascript
const navbarMenu = document.querySelector(".navbar__menu");
navbarMenu.addEventListener("click", (event) => {
  console.log(event.target.dataset.link);
  const target = event.target;
  const link = target.dataset.link;
  if (link == null) {
    return;
  }
  console.log(event.target.dataset.link);
  const scrollTo = document.querySelector(link);
  scrollTo.scrollIntoView({ behavior: "smooth" });
});
```

[scrollIntoView](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollIntoView "scrollIntoView")

---

### :three: Handle contact me button

- '연락하기'버튼을 클릭했을때, 하단의 Contact 섹션으로 내려가게 하려면 homeContactBtn값을 받아와 querySelector를 이용해서 id값을 받아와야한다.

```javascript
const homeContactBtn = document.querySelector(".home__contact");
```

- homeContactBtn에 event를 추가해서, click이되면 내가 정의한 함수가 호출되도록 한다.

```javascript
homeContactBtn.addEventListener("click", () => {
  const scrollTo = document.querySelector(link);
  scrollTo.scrollIntoView({ behavior: "smooth" });
});
```

- 이런 문법이 계속 반복될거같으니 selector만 추가하면 이동할 수 있는 함수를 추가해보자. 즉, selector만 주면 selector에 맞는 요소를 찾은 다음 스무스하게 이동하는 함수를 추가했다.

```javascript
function scrollIntoView(selector) {
  const scrollTo = document.querySelector(selector);
  scrollTo.scrollIntoView({ behavior: smooth });
}
```

- selector만 추가하면 되니 위의 selector를 추가하고 반복되는 코드들은 리팩토링해보자.

```javascript
const navbarMenu = document.querySelector(".navbar__menu");
navbarMenu.addEventListener("click", (event) => {
  console.log(event.target.dataset.link);
  const target = event.target;
  const link = target.dataset.link;
  if (link == null) {
    return;
  }
  scrollIntoView(link); //selector
});

const homeContactBtn = document.querySelector(".home__contact");
homeContactBtn.addEventListener("click", () => {
  scrollIntoView("#contact"); //selector
});

function scrollIntoView(selector) {
  const scrollTo = document.querySelector(selector);
  scrollTo.scrollIntoView({ behavior: smooth });
}
```

---

### :four: Transparent home

- 브라우저가 아래로 스크롤되면서 점점 투명하게 되는 효과주기
- 1. 먼저 home의 높이를 알아와야하므로 querySelector를 이용해 home의 요소를 가져오자.(#home)

```javascript
const home = document.queryselector("#home");
```

- 2. home의 높이도 지정해서 가져오자.

```javascript
const homeHeight = home.getBoundingClientRect().height;
```

- 3. document에 이벤트를 추가할것인데, scroll하게 되면 내가 등록한 함수를 호출.

```javascript
document.addEventListener("scroll", () => {});
```

- 4. 공식을 하나 만들어보자.=> opacity가 0이면 투명, 1이면 완전 불투명이다. `1 - window.scrollY / homeHeight;`

```javascript
document.addEventListener("scroll", () => {
  home.style.opacity = 1 - window.scrollY.homeHeight;
});
```

---

### :five: Arrow up button

- html, css에서 가장 하단 (css에선 media query바로 위)에 다음과 arrow 아이콘을 위한 코드를 추가한다.

```html
<!-- Arrow up -->
<button class="arrow-up">
  <i class="fas fa-chevron-circle-up"></i>
</button>
```

- 원래는 안보이다가 스크롤링이 되면 보이게 해야하기 때문에 `display: none`을 추가하고 보이는 class, 즉 `.visible`일때만 (보이는 class가 있을 때만) display: block을 할것

```css
/* Scroll(Arrow up) */
.arrow-up {
  position: fixed;
  bottom: 50px;
  right: 50px;
  width: 70px;
  height: 70px;
  font-size: 50px;
  color: var(--color-white);
  background-color: var(--color-pink);
  display: none;
}

.arrow-up.visible {
  display: block;
}
```

- 스크롤링이 되면 arrow가 나타나도록 해보자.

```javascript
const arrowUp = document.querySelector(".arrow-up");
document.addEventListener("scroll", () => {
  if (window.scrollY > homeHeight / 2) {
    arrowUp.classList.add("visible");
  } else {
    arrowUp.classList.remove("visible");
  }
});
```

- css를 조금 추가하고 수정하자.

```css
/* Scroll(Arrow up) */
.arrow-up {
  position: fixed;
  bottom: 50px;
  right: 50px;
  width: 70px;
  height: 70px;
  font-size: 50px;
  color: var(--color-white);
  background-color: var(--color-dark-pink);
  border-radius: 50%;
  opacity: 0;
  pointer-events: none;
  transition: opacity 300ms ease-in;
}

.arrow-up.visible {
  opacity: 1;
  pointer-events: auto;
}
```

- 화살표아이콘 클릭하면 홈으로 올라가게 해보자.

```javascript
arrowUp.addEventListener("click", () => {
  scrollIntoView("#home");
});
```

---

### :six: Project filtering & animation

- 프로젝트 탭을 클릭할 시에 원하는 아이템들만 필터링 되서 띄어지게 해보자. 전체적인 애니메이션이 일어나면서 필터링 된 아이들이 나오게 보이려면 **html에 data를 이용하기**

```html
<div class="work__categories">
  <button class="category__btn active" data-filter="*">
    All<span class="category__count">8</span>
  </button>
  <button class="category__btn" data-filter="front-end">
    Front-end<span class="category__count">3</span>
  </button>
  <button class="category__btn" data-filter="back-end">
    Back-end<span class="category__count">3</span>
  </button>
  <button class="category__btn" data-filter="mobile">
    Mobile<span class="category__count">2</span>
  </button>
</div>
<div class="work__projects">
  <a
    href="https://github.com/sujiny3236lovegit/portfolio.git"
    class="project"
    target="blank"
    data-type="front-end"
  >
    ...
  </a>
</div>
```

- js작업을 해보자.
-
-
- `projects.forEach((project) => {});`는 다음 코드들과 같다.

```javascript
projects.forEach((project) => {});
```

```javascript
for (let project of projects) {
}
```

```javascript
for (let i = 0; i < projects.length; i++) {
  project = projects[i];
}
```

:sparkles: 이번 챕터의 핵심 :sparkles:

> `인라인 코드`

```javascript
function test() {
  console.log("hello world!");
}
```

## [Use_data_attributes](https://developer.mozilla.org/en-US/docs/Learn/HTML/Howto/Use_data_attributes "Use_data_attributes")

---

### :seven: Project filtering

- **projects의 active state위치 수정**과 **navbar에서 아이템들을 선택하면 해당 section들이 하이라이트**되도록 해보자.
- 현재 클릭된 애한테 active가 넘어가도록 해보자.
-
-

:sparkles: 이번 챕터의 핵심 :sparkles:

> `인라인 코드`

```javascript
function test() {
  console.log("hello world!");
}
```

[Box model](https://developer.mozilla.org/en-US/docs/Web/CSS/box-sizing "Box model")

---

### :eight: Navbar toggle button

- Toggle(hamburger) button을 클릭해서 아래로 내려오는 효과를 줘보자.
-
-
-

```javascript
//클릭할 버튼을 감싸고 있는 카테고리 영역을 선택자로 지정하기
const workBtnContainer = document.querySelector('.work__categories');

//버튼을 클릭하여 필터링할 각각의 요소들을 배열로 받아오기
const projects= document.querySelectorAll('.project');

//카테고리 영역에서 현재 클릭 이벤트가 발생한 요소에 함수 호출하기
workBtnContainer.addEventListener('click', (e) => {});

//현재 발생한 이벤트가 요소의 데이터의 필터값을 변수에 할당하기(필더값이 없으면 false가 반환되므로)
//값이 없으면 이벤트가 발생한 요소의 부모 노드의 데이터 필터값을 변수에 할당한다.
const filter = e.target.dataset.filter || e.target.parentNode.dataset.filter;

//필터값이 없으면 아무것도 반환하지 않는다.
if(filter == null){
	return;
}

//배열에 저장된 필터링 될 요소들을 각각 불러온다.
project.forEach((project)=>{});

//필터 값이 '*'와 자료형이 모두 일치하면 true를 반환
if(filter === '*' || filter === project.dataset.type){
}
}
```

[Box model](https://developer.mozilla.org/en-US/docs/Web/CSS/box-sizing "Box model")

---

# Last touch 😎

---

### :one: What's next for Git?

-
-
-
-

:sparkles: 이번 챕터의 핵심 :sparkles:

> `인라인 코드`

```javascript
function test() {
  console.log("hello world!");
}
```

[Git](https://git-scm.com/doc "Git")

### :two: Final Touch 😎 part 1

-
-
-
-

:sparkles: 이번 챕터의 핵심 :sparkles:

> `인라인 코드`

```javascript
function test() {
  console.log("hello world!");
}
```

[Box model](https://developer.mozilla.org/en-US/docs/Web/CSS/box-sizing "Box model")

---

### :three: Final touch 😎 part 2

-
-
-
-

:sparkles: 이번 챕터의 핵심 :sparkles:

> `인라인 코드`

```javascript
function test() {
  console.log("hello world!");
}
```

[Box model](https://developer.mozilla.org/en-US/docs/Web/CSS/box-sizing "Box model")

---
