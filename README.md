# css-layout-master

## FLEXBOX

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
