# css-layout-master

## 1 FLEXBOX

### 1.1 First Rule of Flexbox

- display: flex => flex container 생성
- flex container는 display: inline-block 과 동일하다
- flex container는 바로 붙어있는 부모여야 한다.

### 1.2 Main Axis and Cross Axis

- flex container의 default flex-direction은 row이다.
- default direction이 row => main axis(horizontal), cross axis(vertical)
- justify-content: main axis방향으로 item을 옮긴다.
- align-items: cross axis방향으로 item을 옮긴다.

### 1.3 Column and Row

- flex-direction이 column이면 row와 반대로 된다.
- flex-direction: row => main axis(horizontal), cross axis(vertical)
- flex-direction: column => main axis(vertical), cross axis(horizontal)

### 1.4 align-self and order

- align-self는 align-item와 같이 cross axis 방향으로 item을 옮긴다.

### 1.5 wrap, nowrap, reverse, align-content

- flex-wrap:nowrap는 flex-box의 child item을 한 줄(row)에 나타내기 위해 설정된 width값을 무시할 수 있는 property(default)
- flex-wrap:wrap은 flex-box의 child item의 설정을 유지할 수 있도록 하는 property
- align-content는 flex-box해당 라인에 대한 property

### 1.6 flex-grow, flex-shrink

- shrink:수축
- flex-grow, flex-shrink는 child에 적용하는 property
- flex-shrink는 ui화면 공간이 줄어들 경우 설정한 number만큼 더 줄어드는 property(default:1)
- flex-grow는 box 주변 여분의 공간이 있으면 설정한 number만큼 차지하는 property(default:0)
- flex box는 child item을 한 줄(row)에 표기하며 모든 property는 row가 기준이 된다.

### 1.7 flex-basis

- flex-basis는 child에 적용하는 property
- flex-basis는 처음 element에 주는 크기 property
- flex-basis는 main axios에만 작동한다. (flex-direction: row => 가로, flex-direction: column => 세로)
- flex-direction에 따라 width와 height와 연결된다.

---

## 2 GRID

### 2.1 Life Before Grid

- flexBox로는 grid를 구현하기 어렵다.

### 2.2 CSS Grid Basic Concepts

- flexBox와 유사하게 부모 element에서부터 시작된다.
- grid-template-columns를 사용하여 column을 정의할 수 있다\
  ex) grid-template-columns: 20px 20px 20px => 20px 3개의 column을 가진 grid
- column-gap은 column간의 간격을 설정하는 property
- row-gap은 row간의 간격을 설정하는 property
- gap만 사용하면 column/row의 모든 간격을 설정하는 property
- grid-template-rows를 사용하여 row를 정의할 수 있다.\
  ex) grid-template-columns와 동일하게 설정

### 2.3 Grid Template Areas

- grid-template-columns로 column을 정의할 수 있다(+repeat()사용)
- grid-template-rows로 row를 정의할 수 있다.(+repeat()사용)
- grid-template-areas로 layout을 설정할 수 있다.\
  각 class별 name으로 layout을 설정 할 수 있다.\
  ex) "header header header header"\
   "content content content content"...

### 2.4 Rows and Columns

- grid-template-area를 사용하지 않고 grid-columns-start/end 와 grid-rows-start/end로 동일하게 설정할 수 있다.
- grid-columns-start/end로 영역을 지정할 수 있다.(선이 기준)\
  ex) start:1, end: 2 => 1column~2column까지 설정이 아니라 1번째 라인~2번째 라인까지 영역을 설정함을 의미
- grid-rows-start/end도 동일하게 설정

### 2.5 Shortcuts

- grid-columns-start/end와 grid-rows-start/end를 사용하지 않고 grid-column와 grid-row로 대체할 수 있다.\
  ex) grid-column: 1 / 5, grid-row: 2 / 4
- end값은 -1로 대체할 수 있고 , -1, -2형태도 가능하다.(라인의 수를 셀 필요가 없다.)
- span을 이용하여 영역을 설정할 수 있다.
  ex) grid-column: span 4; => 4개 column영역을 할당함을 의미

### 2.6 Line Naming

- grid-template-columns와 grid-template-rows에 line naming을 하여 grid-column, grid-row에서 활용할 수 있으나, 2.4, 2.5 방법이 훨씬 이해가 쉽고 간편하다. 그럼으로 skip
