# 반응형 웹 디자인의 이해

## 1. 미디어 쿼리(Media Queries)

### 기본 개념

미디어 쿼리는 웹사이트를 다양한 화면 크기와 디바이스에 최적화하기 위한 CSS3의 핵심 기능입니다. 사용자의 디바이스 특성에 따라 다른 스타일을 적용할 수 있게 해줍니다.

### 기본 문법

```css
@media screen and (조건) {
  /* CSS 규칙 */
}
```

### 주요 breakpoint

일반적으로 사용되는 breakpoint는 다음과 같습니다:

```css
/* 모바일 스타일 */
@media screen and (max-width: 767px) {
  .container {
    width: 100%;
    padding: 0 15px;
  }
}

/* 태블릿 스타일 */
@media screen and (min-width: 768px) and (max-width: 1023px) {
  .container {
    width: 750px;
    margin: 0 auto;
  }
}

/* 데스크톱 스타일 */
@media screen and (min-width: 1024px) {
  .container {
    width: 1000px;
    margin: 0 auto;
  }
}
```

### 미디어 쿼리 조건의 종류

- `min-width`: 최소 너비
- `max-width`: 최대 너비
- `orientation`: 디바이스 방향(portrait/landscape)
- `aspect-ratio`: 화면 비율
- `resolution`: 해상도

## 2. Viewport 단위

### 기본 개념

Viewport는 웹 페이지가 표시되는 브라우저의 가시 영역을 의미합니다. Viewport 단위를 사용하면 디바이스의 화면 크기에 따라 요소의 크기를 자동으로 조절할 수 있습니다.

### 주요 단위

- `vw` (viewport width): viewport 너비의 1%
- `vh` (viewport height): viewport 높이의 1%
- `vmin`: vw와 vh 중 작은 값
- `vmax`: vw와 vh 중 큰 값

### 사용 예시

```css
/* 전체 화면 높이의 hero 섹션 */
.hero {
  height: 100vh;
  width: 100vw;
}

/* 화면 너비의 50%를 차지하는 컨테이너 */
.half-width {
  width: 50vw;
  margin: 0 auto;
}

/* 최소 높이 설정 */
.min-height {
  min-height: 50vh;
}
```

## 3. 모바일 퍼스트 접근

### 기본 개념

모바일 퍼스트는 모바일 디바이스를 위한 디자인을 먼저 하고, 그 다음 더 큰 화면을 위한 디자인을 추가하는 방식입니다.

### 장점

1. 성능 최적화
2. 콘텐츠 중심의 설계
3. 점진적 향상

### 구현 예시

```css
/* 기본 스타일 (모바일) */
.container {
  width: 100%;
  padding: 15px;
}

/* 태블릿 이상 */
@media screen and (min-width: 768px) {
  .container {
    width: 750px;
    padding: 0;
    margin: 0 auto;
  }
}

/* 데스크톱 */
@media screen and (min-width: 1024px) {
  .container {
    width: 1000px;
  }
}
```

## 4. 실전 팁

### 메타 태그 설정

반응형 웹 디자인을 위해서는 HTML 파일의 head 섹션에 다음 메타 태그를 추가해야 합니다:

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
```

### 유연한 이미지

이미지를 반응형으로 만드는 기본적인 CSS:

```css
img {
  max-width: 100%;
  height: auto;
}
```

### 텍스트 크기 조정

뷰포트 크기에 따라 자동으로 조정되는 텍스트 크기:

```css
.responsive-text {
  font-size: calc(16px + 1vw);
}
```
