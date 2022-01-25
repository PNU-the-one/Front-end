```
hello = function() {
  return "Hello World!";
}
```
arrow function으로 쓰면
```
hello = () => {
  return "Hello World!";
}
```
더 짧게 하려면 return 생략 가능
```
hello = () => "Hello World!";
```
참고로 함수에 명령문이 하나만 있는 경우에만 작동

- 매개변수가 있는 경우
```
hello = (val) => "Hello " + val;
```

- 매개 변수가 하나만 있다면 괄호도 생략 가능
```
hello = val => "Hello " + val;
```

## this 활용법
- this의 처리도 일반 함수와 비교했을 때 화살표 함수에서는 매우 다른 모습을 띈다.
- 화살표 함수에는 this의 바인딩이 없다.
- 일반 함수에서 this 키워드는 함수를 호출한 개체를 나타낸다.
- 화살표 함수에서 this 키워드는 항상 화살표 함수를 정의한 객체를 나타낸다.
- 아래의 예를 보며 차이점을 알아보자.

```
// Regular Function:
hello = function() {
  document.getElementById("demo").innerHTML += this;
}

// The window object calls the function:
window.addEventListener("load", hello);

// A button object calls the function:
document.getElementById("btn").addEventListener("click", hello);
```
실행결과 <br>![regular](.img/noarrow.PNG)<br>
- 위 코드는 페이지가 로드될 때 먼저 메소드를 호출하고 사용자가 버튼을 클릭할  때 다시 한 번 메소드를 두번 호출하는 코드이다.
- 일반 함수에서의 this는 함수를 호출하는 객체를 나타낸다.

```
// Arrow Function:
hello = () => {
  document.getElementById("demo").innerHTML += this;
}

// The window object calls the function:
window.addEventListener("load", hello);

// A button object calls the function:
document.getElementById("btn").addEventListener("click", hello);
```
실행결과 <br>![arrow](.img/arrow.PNG)<br>
- 화살표 함수의 this는 함수 소유자를 나타낸다.
- window 객체가 함수의 소유자이기 때문에 window를 2번 호출하게 된다.