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

### 2.7 Grid Template

- fr은 fraction이며, 사용 가능한 공간을 뜻한다.(grid에서 가능한 공간을 차지한다는 뜻)
- fr은 width값은 없어도 괜찮으나, height값은 있어야 한다.
- fr을 사용하면 비율로 공간을 설정하기때문에 화면 크기가 달라져도 layout 화면이 유지된다
- grid-template에서는 grid-area의 이름을 사용한다. 그리고 row의 높이를 지정한다.
- grid-template을 사용하면 grid-area의 이름으로 그림을 그리듯 layout을 구성할 수 있다.

### 2.8 Place Items

- justify-items(수평, 가로)의 기본값은 stretch
- align-items(수직, 세로)의 기본값은 stretch
- grid는 자식을 가지고 그 자식들을 늘여서(stretch) 본인을 채운다.
- grid 자식의 내용이 없으면 보이지 않는다(width, height가 설정되지 않은경우)
- 반대로 grid 자식의 내용이 없어도 width와 height가 있으면 보인다.

### 2.9 Place Content

- place-items(justify-items, align-items)는 grid의 cell(각 자식 item)을 설정하는 property이며\
  place-content(justify-content, align-content)는 grid자체를 설정한다.\
  ex) grid-container는 100% width를 가지며, justify-content: center;시 grid가 가운데로 정렬된다.
- place-content(justify-content, align-content)는 grid를 정렬하는 property

### 2.10 Auto Columns and Rows

- place-self(align-self, justify-self)는 place-items, place-content와 다르게 grid item 개별적으로 적용된다.
- grid-auto-rows는 grid-template-rows에 지정한 rows보다 많은 데이터가 있을경우 설정한 값으로 row를 설정하는 property
- grid-auto-flow는 설정한 rows보다 많은 데이터가 있을경우 row가 아닌 columns으로 배치되게 해준다.\
  ex) grid-auto-flow: column => 정렬 direction도 바뀐다.\
  auto: 수평, column: 수직

### 2.11 minmax

- minmax는 최소, 최대사이즈를 설정해준다.
