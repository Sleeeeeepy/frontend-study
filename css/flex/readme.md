# 이번 강의에서 배운 것
## 과거
css에 레이아웃 관련 기능이 없을 때 텍스트와 이미지를 배치하는 용도로 사용되는 `float`를 이용했습니다. 그러나 `flex`가 도입되고 `flex`를 이용합니다.

## flex
### 컨테이너 CSS 속성
#### flex-direction
flex 박스의 방향을 지정합니다. `row`로 지정하면 아이템들이 행을 기준으로 일렬로 나열되며, `column`으로 지정하면 아이템들이 열을 기준으로 일렬로 나열합니다. 방향을 반대로 지정하려고 한다면 `row-reverse`, `column-reverse`로 지정합니다.
``` css
.container {
    flex-direction: row;
}
```
#### flex-wrap
`flex-direction`에 따라 아이템을 지정한다고 하면, 넘치는 아이템을 어떻게 할 지 `flex-wrap`을 통해 지정할 수 있습니다. 기본값은 `nowrap`이고 `wrap`으로 설정한다면 스크롤바가 생기지 않고 아이템이 다음 라인으로 넘어갑니다.
``` css
.container {
    flex-wrap: wrap;
}
```

#### justify-content
중심축에서 아이템을 어떻게 배치해야 하는지를 지정합니다. 주요 속성에는 `start`, `end`, `center`가 있습니다.

``` css
.container {
    justify-content: center;
}
```

#### align-items
반대축을 기준으로 아이템을 정렬합니다. 주요 속성에는 `start`, `end`, `center`, `baseline`이 있는데, `baseline`의 경우, 텍스트에 위치에 맞게 배치를 합니다. `justify-content`의 수직축 버전이라고 생각하면 됩니다.

``` css
.container {
    align-items: center;
}
```

#### align-content
반대축 상에 여분 공간이 있는 경우 flex 컨테이너 사이의 간격을 조절합니다.

``` css
.container {
    align-content: center;
}
```

#### align-items vs align-content
`align-items`는 아이템이 컨테이너 내에서 전체적으로 정렬되는 방식을 결정하지만, `align-content`는 수직축을 기준으로 줄 사이의 간격을 결정합니다. 그래서 하나의 라인만 있다면 `align-content`는 효과가 없습니다.

### 아이템 CSS 속성
#### flex-grow
남는 여백을 분배해서 주어진 비율대로 채웁니다.

#### order
아이템의 순서를 임의로 변경합니다.

#### flex-shrink
아이템이 줄어들 때 어떤 비율로 줄어들어야 하는지 지정합니다.

#### flex-basis
아이템이 커지거나 줄어들 때 어떤 비율로 늘어나고 커져야하는 지를 지정합니다.

#### flex
`flex-grow`, `flex-shrink`, `flex-basis`를 한번에 지정합니다.
```css
.container {
    flex: 2 2 auto
}
```

#### align-self
해당 아이템을 정렬합니다. 특정 아이템만 정렬하고 싶다면 `align-self`를 이용합니다.