# 이번 강의에서 배운 것
### 단위
`fr`단위는 컨테이너 내의 공간 비율을 분수(fraction)로 나타낸 것입니다.
`%` 단위는 상속된 사이즈, 혹은 디폴트 사이즈에 대한 상대적인 비율입니다.
### 함수
`repeat(x, y)`는 y를 x번 반복합니다.
``` css
.container {
    grid-template-columns: repeat(5, 1fr)
}
```

### 컨테이너 CSS 속성
#### grid-template-columns, rows
컨테이너에 grid 트랙의 크기를 지정하는 속성입니다.
``` css
.container {
    grid-template-rows: 100px 100px 100px /* row가 3개! */
}
```

#### column, row-gap, gap
안 쪽 요소들 간의 간격을 설정합니다.
```
.container {
    row-gap: 10px
}
```

### 컨테이너 내부 요소 CSS 속성
#### grid-column, row
해당 요소가 얼마만큼의 column 혹은 row를 차지할 지 결정합니다. 번호는 아래와 같습니다.
```
 1    2    3    4    5
1+----+----+----+----+
 |    |    |    |    |
2+----+----+----+----+
 |    |    |    |    |
3+----+----+----+----+
```

``` css
.item2 {
    grid-column: 2 / 3; /* 2열부터 3열을 차지 */
    grid-row: 2 / -1; /* 2행부터 마지막 행까지 차지 */
    grid-column: 2 / span 1; /* 2열부터 한 칸 차지, 위와 동일 */
}
```

#### grid-area
우선 부모 요소에서 `grid-template-area`를 지정해줘야 합니다.
``` css
.container {
    grid-template-areas:
    'a a'
    'b g'
    'c d'
    'e f';
}
```
이후 `grid-area`를 통해 어디에 위치할 지 정할 수 있습니다.
``` css
.item2 {
    grid-area: d
}
```
만약 상기 예제에서 `a`를 택한다면 두 칸을 차지합니다.