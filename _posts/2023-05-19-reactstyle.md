---
title: React 스타일링 방법 (3가지)
date: 2023-05-19 23:00:00 +0100
categories: [Coding, React]
tags: [react] # TAG names should always be lowercase
author: <author_id>
---

### 기본적인 방법

useState를 이용해서 변수에 true, false 값을 지정해서 클래스를 동적으로 변화시켜서 클래스에 따라 css 지정하기

### Styled Components(서드 파티 라이브러리)

> npm install --save styled-components

설치 후 구문 작성 법

```jsx
import styled from "styled-components";
.
.
.
const Button = styled.button``;
```

백틱 사이에 css작성 하면 styled-components에 의해 겹치지 않는 랜덤 클래스가 자동으로 생성되어서 다른 컴포넌트나 요소에 영향을 주지 않는다.

div에 스타일을 적용하는 경우

```jsx
<FormControl invalid={!isValid}></FormControl>
```

isValid 값을 props로 전달해서

```jsx
background: ${(props) => (props.invalid ? "#ffd7d7" : "transparent")};
```

백틱 내 css 구문 안에서 isValid 값에 따라 다른 색을 리턴하게 만들 수 있다.

단점 : css파일과 js파일이 분리되지 않아서 보기 불편할 수 있음

### CSS Modules

styled components랑 마찬가지로 고유한 className을 생성해서 css가 전역으로 적용되지 않게 해줌

css파일명에 .module을 붙여서 수정한 뒤 다음과 같은 방식으로 불러온다

```jsx
import styles from "./Button.module.css";
.
.
.
<button className={styles.button}/>
```

그다음 적용하고 싶은 className을 styles 뒤에 지정해주면
DOM에선 "Button_button\_\_2lgkF"라는 class가 생성됨

styled component랑 다르게 jsx와 css파일을 분리해서 관리가 쉬움!
