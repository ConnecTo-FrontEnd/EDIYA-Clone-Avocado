# 🥑 팀 아보카도 EDIYA 클론 코딩

![원본](https://velog.velcdn.com/images/jiseung/post/305c4318-6020-4940-931d-18cec19ed20e/image.png)

EDIYA 메인 페이지를 구현하는 프로젝트

원본 페이지: https://seulbinim.github.io/EDIYA/  
팀 아보카도 페이지: https://connecto-frontend.github.io/EDIYA-Clone-Avocado/

## 🛠 기술 스택

HTML, SCSS

## 🗓 진행 기간

2022.07.27 - 2022.07.29

## 📝 진행 과정

### 2022.07.27

#### 프로젝트 목표 설정

- '협업'에 목표를 두자. 최대한 컴포넌트 단위로 역할을 나누고, 서로의 진행 상황을 자주 팔로업하자
- 메인 페이지 하나를 만들더라도 제대로 만드는 것을 목표로 하자
- SCSS를 사용해 재사용성을 높여보자

#### 토의 내용

1. 어떻게 SCSS로 협업을 할 수 있을까?

- 가장 기본적인 SCSS를 먼저 작업해놓고 진행을 시작하자
- 가장 기본적인 SCSS? color, space, size등을 변수로 빼놓고, 첫번째 페이지를 진행할 때 꼼꼼하게 mixin을 빼두어 다른 페이지를 좀 더 편하게 작업할 수 있도록 하자

2. 어떻게 역할을 분담할까?

- 컴포넌트 단위로 페이지를 잘게 쪼개자
- 컴포넌트 단위? 헤더, 푸터, 메인 컨텐츠 단위
- 마크업, 스타일 모두 컴포넌트 단위로 작업하고 합치자

3. 더 나은 협업을 위해

- 짧은 간격으로 각자의 진행 상황, 작업에 대해 공유하자
- 어려움이 있으면 빠르게 돕자

### 2022.07.28

#### 메인페이지 마크업 및 초기 세팅<br>

![마크업](https://velog.velcdn.com/images/jiseung/post/cfc7f5d7-d18f-4aaf-b0e7-28e8bd158979/image.png)

- 백남헌 : Header, Footer 마크업
- 김민석 : 메인 콘텐츠 마크업
- 강지승, 박지윤 : SASS 초기 세팅 및 스타일 리셋. 자주 쓰이는 변수 및 믹스인 세팅
  <br>

> 완성된 마크업을 두고 토의를 통해 더 나은 방향으로 마크업을 개선시켜 나감. (마크업 순서, 시맨틱 태그 등을 고려)

<br>

#### 메인 페이지 스타일 및 뉴스, 수상내역 페이지 마크업<br>

![1차 완성](https://velog.velcdn.com/images/jiseung/post/aa7d6a09-addd-4c99-8ca0-fdc31c7a6414/image.png)

![1차 완성](https://velog.velcdn.com/images/jiseung/post/c009369a-d23c-465b-950e-5b137b6edbd6/image.png)

![1차 완성](https://velog.velcdn.com/images/jiseung/post/84de42d6-7990-4787-a390-a9abd3cd2bbe/image.png)

![뉴스 페이지 마크업](https://velog.velcdn.com/images/jiseung/post/cde5ca9e-3ef5-495a-9010-806081ac362f/image.png)

![수상 내역 마크업](https://velog.velcdn.com/images/jiseung/post/7969458c-5a45-412a-bf79-70dce2415315/image.png)

- 박지윤 : Header, Footer 스타일
- 강지승 : 메인 콘텐츠 상단 스타일
- 김민석 : 메인 콘텐츠 하단 스타일
- 백남헌 : 메인 콘텐츠 애니메이션, 뉴스/수상내역 페이지 마크업
  <br>

> SASS 변수, mixins를 활용해 반응형 스타일 완성.<br>
> git 관련 협의가 없어서 merge 시 충돌을 해결하느라 어려움을 겪음

#### 병합 과정에서 겪은 트러블 슈팅

이슈 : 병합된 파일에서 서로 스타일이 다르게 보였다!
원인 : 각자 설정된 기본 브라우저 폰트 사이즈(rem)이 달랐는데(16px vs 20px), 따로 기본값을 지정해주지 않아서 생긴 일이었음을 알게 되었다.
해결 : html에 font-size를 지정해 동일하게 스타일을 지정했다.

<br>

#### 메인 페이지 스타일 및 리팩토링<br>

- 어느정도 완성된 스타일로 리팩토링 진행
- SCSS Structure에 대해 스터디

| 폴더       | 스터디 내용                                                          | 토의 내용                                                                                                                |
| ---------- | -------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| base       | 모든 페이지에 default가 될 CSS 스타일을 저장                         | typography.css로 전체 폰트를 관리하는 파일에 대해 고민                                                                   |
| components | 공통되는 스타일 묶음. 버튼, 로그인 폼 등에서 사용할 수 있을 것 같다. | 메인 페이지만 작업해서 컴포넌트로 분리할 수 있는 것을 아직 찾지 못했지만 페이지를 더 작업하면서 사용하기 위해 생성해두자 |
| layout     | Header, Footer 등의 레이아웃                                         | 한 섹션을 차지할 만한 스타일들의 묶음을 넣어두자                                                                         |
| pages      | 특정 페이지에만 사용되는 스타일들을 모아두자                         | 특정 페이지에 사용되는 스타일들을 모두 페이지 단위로 `@use`를 사용해 불러들이자                                          |
| utils      | 변수, 믹스인 등의 공용으로 사용되는 SCSS들                           | abstracts와 utils의 차이에 대해 고민했고, 조금 더 포괄적인 의미의 utils로 네이밍해보자                                   |

> Q. 폴더 구조를 공부하면서 왜 모든 SCSS 파일을 하나의 main.scss로 묶어서 하나의 CSS 파일을 형성하는가에 대해 의문이 생겼다. HTML별로 필요한 CSS만 불러들이는게 빠르지 않을까?<br><br>
> A. HTML 파일이 여러개더라도 단 하나의 CSS 파일을 연결시키자. 처음 불러들인 스타일시트를 캐시해두기 때문에 보다 빠른 렌더링이 가능해진다.

**리팩토링 전**

```bash
    │   ├── base
    │   │   ├── _default.scss
    │   │   ├── _index.scss
    │   │   ├── _normalize.scss
    │   │   └── _reset.scss
    │   ├── components
    │   │   └── _index.scss
    │   ├── index.scss
    │   ├── layout
    │   │   ├── _footer.scss
    │   │   ├── _header.scss
    │   │   ├── _index.scss
    │   │   ├── _newmenu.scss
    │   │   └── _notice.scss
    │   ├── pages
    │   │   └── _index.scss
    │   └── utils
    │       ├── _a11y.scss
    │       ├── _color.scss
    │       ├── _flexbox.scss
    │       ├── _index.scss
    │       ├── _media-query.scss
    │       ├── _mixin.scss
    │       ├── _unit.scss
    │       └── _variable.scss
    └── style
        ├── index.css
        └── index.css.map
```

**리팩토링 후**

```bash
    ├── scss
    │   ├── base
    │   │   ├── _default.scss
    │   │   ├── _index.scss
    │   │   ├── _normalize.scss
    │   │   └── _reset.scss
    │   ├── components
    │   │   └── _index.scss
    │   ├── layout
    │   │   ├── _footer.scss
    │   │   ├── _header.scss
    │   │   └── _index.scss
    │   ├── main.scss
    │   ├── pages
    │   │   ├── _home.scss
    │   │   ├── _index.scss
    │   │   └── _news-media.scss
    │   └── utils
    │       ├── _a11y.scss
    │       ├── _color.scss
    │       ├── _flexbox.scss
    │       ├── _index.scss
    │       ├── _media-query.scss
    │       ├── _mixin.scss
    │       ├── _unit.scss
    │       └── _variable.scss
```
