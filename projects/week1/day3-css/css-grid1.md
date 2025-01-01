# CSS Grid

<br>

## Grid 란??

- 웹페이지의 2차원 레이아웃을 만들기 위한 가장 강력한 도구!!
- Flexbox가 1차원(행 또는 열)의 레이아웃을 다루고 Grid는 행과 열 모두를 동시에 다룰 수 있다.
- Flexbox -> 1차원 레이아웃(한 방향)
- Grid -> 2차원 레이아웃(두 방향)
  <br>

---

  <br>

## 기본 개념 용어

### Grid Container (그리드 컨테이너)

- `display: grid` 또는 `display: inline-grid`가 적용된 부모 요소
- 그리드 시스템의 가장 바깥쪽 요소
- 모든 그리드 항목의 콘텐츠를 담는 컨테이너

```css
.container {
  display: grid;
  /* 또는 */
  display: inline-grid;
}
```

<br>

### Grid Item (그리드 아이템)

- 그리드 컨테이너의 직계 자식 요소
- 그리드 라인으로 구분된 각각의 칸에 배치되는 콘텐츠
  <br>

### Grid Line (그리드 라인)

- 그리드의 구조를 형성하는 수직 및 수평선
- 열(column) 라인과 행(row) 라인으로 구성
- 1부터 시작하는 번호가 자동으로 할당됨
  <br>

### Grid Cell (그리드 셀)

- 4개의 그리드 라인으로 둘러싸인 가장 작은 단위의 공간
- 하나의 그리드 아이템이 기본적으로 차지하는 공간
  <br>

### Grid Track (그리드 트랙)

- 두 개의 인접한 그리드 라인 사이의 공간
- 행(row) 트랙: 수평 트랙
- 열(column) 트랙: 수직 트랙

```css
.container {
  /* 열 정의 */
  grid-template-columns: 200px 200px 200px;
  /* 또는 */
  grid-template-columns: repeat(3, 1fr);

  /* 행 정의 */
  grid-template-rows: 100px auto;

  /* 간격 설정 */
  gap: 20px;
  /* 또는 */
  row-gap: 20px;
  column-gap: 10px;
}
```

<br>

### Grid Area (그리드 영역)

- 4개의 그리드 라인으로 둘러싸인 직사각형 영역
- 여러 개의 그리드 셀로 구성될 수 있음
- `grid-area` 속성을 사용하여 이름 지정 가능
  <br>
  <br>

---

<br>

## 크기 단위

### fr (fraction)

- 사용 가능한 공간을 비율로 나누는 단위
- 예: `1fr 2fr 1fr`은 1:2:1 비율로 공간 분배

```css
.container {
  display: grid;
  /* 1:2:1 비율로 공간 분배 */
  grid-template-columns: 1fr 2fr 1fr;
}
```

<br>

### 고정 단위

- `px`, `em`, `rem` 등의 일반적인 CSS 단위
- 고정된 크기를 지정할 때 사용
  <br>

### minmax()

- 최소값과 최대값을 지정하는 함수
- 예: `minmax(100px, 1fr)`
  <br>
  <br>

---

<br>

## 간격

### gap

- 그리드 셀 사이의 간격을 지정
- `row-gap`: 행 간격
- `column-gap`: 열 간격
- `gap`: 행/열 간격을 한 번에 지정
  <br>
  <br>

---

<br>

## 자주 사용되는 함수

### repeat()

- 트랙 리스트의 전체 또는 일부를 반복
- 예: `repeat(3, 1fr)` = `1fr 1fr 1fr`
  <br>

### auto-fit / auto-fill

- 사용 가능한 공간에 맞춰 자동으로 트랙 개수 조절
- 반응형 그리드 레이아웃 구현에 유용
