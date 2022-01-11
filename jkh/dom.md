# DOM (Document Object Model)
- 페이지가 로드될 때, 브라우저는 페이지의 DOM을 생성
- DOM이란 트리 형식으로 구성된 객체 모델
- W3C의 표준으로 프로그램과 스크립트가 문서의 콘첸츠, 구조 및 스타일에 동적으로 엑세스하고 업데이트할 수 있도록 하는 플랫폼 및 언어 중립적 인터페이스
    1. Core DOM : 모든 문서 유형에 대한 표준 모델
    2. XML DOM : XML 문서의 표준 모델
    3. HTML DOM : HTML 문서의 표준 모델
- HTML DOM은 HTML 요소를 가져오고, 변경하고, 추가하거나 삭제하는 방법에 대한 표준

## HTML DOM 메소드
- HTML DOM 메소드는 HTML 요소에서 수행할 수 있는 작업
- HTML DOM 속성은 설정하거나 변경할 수 있는 HTML 요소의 값
- DOM에서 모든 HTML 요소는 객체로 정의
- 프로그래밍 인터페이스는 각 객체의 속성과 메소드
    1. 속성 : HTML 요소의 내용을 변경하는 등 가져오거나 설정할 수 있는 값
    2. 메소드 : 추가 또는 HTML 요소를 삭제하는 등 의 작업
```
<html>
<body>

<p id="demo"></p>

<script>
document.getElementById("demo").innerHTML = "Hello World!";
</script>

</body>
</html>
```
- 여기서 getElementByID는 메소드, innerHTML은 속성을 나타낸다.
- getElementByID : HTML 요소에 액세스하는 가장 일반적인 방법으로 id를 받아오는 방법
- innerHTML : 요소의 내용을 가져오는 가장 일반적인 방법. HTML 요소의 내용을 가져오거나 바꾸는데 유용