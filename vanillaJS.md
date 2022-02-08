> 참고한 사이트 : [Vanilla Javascript로 웹 컴포넌트 만들기](https://junilhwang.github.io/TIL/Javascript/Design/Vanilla-JS-Component/#_1-%E1%84%8F%E1%85%A5%E1%86%B7%E1%84%91%E1%85%A9%E1%84%82%E1%85%A5%E1%86%AB%E1%84%90%E1%85%B3%E1%84%8B%E1%85%AA-%E1%84%89%E1%85%A1%E1%86%BC%E1%84%90%E1%85%A2%E1%84%80%E1%85%AA%E1%86%AB%E1%84%85%E1%85%B5)

#### Vanilla JS란? 
바닐라 자바스크립트(Vanilla JS)란 프레임워크 또는 라이브러리가 적용되지 않은 순수한 날것의 자바스크립트를 뜻한다.
### 컴포넌트와 상태관리
![image](https://user-images.githubusercontent.com/63496777/152972168-ee7ca30f-1d58-4585-9470-35bbabe10ae9.png)
> 어쨌든 중요한 점은 현 시점의 웹 어플리케이션은 컴포넌트 단위로 설계되고 개발된다는 것이다. 그리고 컴포넌트마다 컴포넌트를 렌더링할 때 필요한 상태를 관리하게 되었으며, Proxy 혹은 Observer Pattern 등을 이용하여 이를 구현한다.
### state - setState - render
setState 라는 메소드를 통해서 state를 기반으로 render를 해주는 코드를 만들어보자.
``` html
<div id="app"></div>
<script>
const $app = document.querySelector('#app');

let state = {
  items: ['item1', 'item2', 'item3', 'item4']
}

const render = () => {
  const { items } = state;
  $app.innerHTML = `
    <ul>
      ${items.map(item => `<li>${item}</li>`).join('')}
    </ul>
    <button id="append">추가</button>
  `;
  document.querySelector('#append').addEventListener('click', () => {
    setState({ items: [ ...items, `item${items.length + 1}` ] })
  })
}

const setState = (newState) => {
  state = { ...state, ...newState };
  render();
}

render();
</script>
```
이 코드의 핵심은 두가지다.
> state는 setState로만 변경해야 한다.  
> state가 변경되면 render를 실행한다.  

이를 지키며 코드를 작성하면, 브라우저에 출력되는 내용은 무조건 state에 종속된다.
즉, DOM을 직접적으로 다룰 필요가 없다.

### 초기 컴포넌트
```javascript
export default class Component {
  $target;
  $state;
  constructor ($target) {
    this.$target = $target;
    this.setup();
    this.render();
  }
  setup () {};
  template () { return ''; }
  render () {
    this.$target.innerHTML = this.template();
    this.setEvent();
  }
  setEvent () {}
  setState (newState) {
    this.$state = { ...this.$state, ...newState };
    this.render();
  }
}
```

### 컴포넌트의 목적
기본적으로 컴포넌트 라는 것은 "재활용"이 목적이다. 그러기 위해선 하나의 컴포넌트가 최대한 작은 단위의 일을 하도록 만들어야 한다.

### 최종 컴포넌트
```javascript
export default class Component {
  $target;
  $props;
  $state;
  constructor ($target, $props) {
    this.$target = $target;
    this.$props = $props; // $props 할당
    this.setup();
    this.setEvent();
    this.render();
  }
  setup () {};
  mounted () {};
  template () { return ''; }
  render () {
    this.$target.innerHTML = this.template();
    this.mounted(); // render 후에 mounted가 실행 된다.
  }
  setEvent () {}
  setState (newState) { /* 생략 */ }
  addEvent (eventType, selector, callback) { /* 생략 */ }
}
```
> mounted를 추가한 이유는 render 이후에 추가적인 기능을 수행하기 위해서이다.  
> $props는 부모 컴포넌트가 자식 컴포넌트에게 상태 혹은 메소드를 넘겨주기 위해서이다.
