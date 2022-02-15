> 참고한 사이트 : [Vanilla Javascript로 웹 컴포넌트 만들기](https://junilhwang.github.io/TIL/Javascript/Design/Vanilla-JS-Component/#_1-%E1%84%8F%E1%85%A5%E1%86%B7%E1%84%91%E1%85%A9%E1%84%82%E1%85%A5%E1%86%AB%E1%84%90%E1%85%B3%E1%84%8B%E1%85%AA-%E1%84%89%E1%85%A1%E1%86%BC%E1%84%90%E1%85%A2%E1%84%80%E1%85%AA%E1%86%AB%E1%84%85%E1%85%B5)

# Make web component with vanilla js
##### JS 문법적으로나 개념적으로 어려웠던 점에 대하여 



### EX 1
1. 아래 코드

```js
const { items } = state; 
```
의 의미가 정확히 무엇인가?

> state 라는 객체에서 items라는 key의 value를 가지는 변수 items를 선언하는 느낌이랄까.. state 객체 안의 items를 꺼내쓰는 것!
> 원래라면 state.items로 접근해야 하는데 그냥 items로 접근할 수 있게 해줌.

2. 전개 연산자 ...를 굳이 붙이는 이유가 뭘까?  
  [JavaScript - 전개연산자(spread)와 와 나머지 매개변수(rest)](https://velog.io/@bigbrothershin/JavaScript-%ED%95%A8%EC%88%98-%EC%8B%AC%ED%99%94-%EB%82%98%EB%A8%B8%EC%A7%80-%EB%A7%A4%EA%B0%9C%EB%B3%80%EC%88%98%EC%99%80-%EC%A0%84%EA%B0%9C-%EC%97%B0%EC%82%B0%EC%9E%90)  
  [자바스크립트 {...} [...] 문법 (비구조화 할당/구조분해 할당)](https://yuddomack.tistory.com/entry/%EC%9E%90%EB%B0%94%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8-%EB%AC%B8%EB%B2%95-%EB%B9%84%EA%B5%AC%EC%A1%B0%ED%99%94-%ED%95%A0%EB%8B%B9)  


