# HTML DOM(Document Object Model)

![image-20220109234322901](C:\Users\gkgpa\AppData\Roaming\Typora\typora-user-images\image-20220109234322901.png)

- DOM의 개체 구조는 노드 트리로 표현된다.

### DOM Methods

- property는 get 또는 set할 수 있는 값이다. 예) innerHTML
- method는 action이다. 예) getElementById

### DOM Document

- HTML 속성 가져오기

| Method                                  | Description                   |
| :-------------------------------------- | :---------------------------- |
| document.getElementById(*id*)           | Find an element by element id |
| document.getElementsByTagName(*name*)   | Find elements by tag name     |
| document.getElementsByClassName(*name*) | Find elements by class name   |

- HTML 속성 변경하기

| Property                                   | Description                                   |
| :----------------------------------------- | :-------------------------------------------- |
| *element*.innerHTML = *new html content*   | Change the inner HTML of an element           |
| *element*.*attribute = new value*          | Change the attribute value of an HTML element |
| *element*.style.*property = new style*     | Change the style of an HTML element           |
| Method                                     | Description                                   |
| *element*.setAttribute*(attribute, value)* | Change the attribute value of an HTML element |

- 속성 추가 및 삭제

| Method                            | Description                       |
| :-------------------------------- | :-------------------------------- |
| document.createElement(*element*) | Create an HTML element            |
| document.removeChild(*element*)   | Remove an HTML element            |
| document.appendChild(*element*)   | Add an HTML element               |
| document.replaceChild(*new, old*) | Replace an HTML element           |
| document.write(*text*)            | Write into the HTML output stream |

- 이벤트 핸들러 추가

| Method                                                     | Description                                   |
| :--------------------------------------------------------- | :-------------------------------------------- |
| document.getElementById(*id*).onclick = function(){*code*} | Adding event handler code to an onclick event |

### DOM Elements

- id, tag name, class name, CSS selectors, HTML object collections를 사용하여 HTML element를 가져올 수 있다.

  ```
  const element = document.getElementById("intro");
  const element = document.getElementsByTagName("p");
  const x = document.getElementsByClassName("intro");
  const x = document.querySelectorAll("p.intro");
  ```

  

### DOM HTML

- HTML 내용 변경하기

  `document.getElementById(id).innetHTML = "abc";`

- 속성값 변경하기

  `document.getElementById(id).src = "abc.jpg";`

- 동적 콘텐츠

  `document.getElementById("demo").innerHTML = "Date : " + Date();`

- output 출력하기

  `document.write(내용);`

### DOM Forms

- required: 폼이 empty한 경우를 방지할 수 있다.

  ```
  <form action="/action_page.php" method="post">
    <input type="text" name="fname" required>
    <input type="submit" value="Submit">
  </form>
  ```

- 데이터 유효성 검증
  - 필요한 필드를 채웠는가?
  - 올바른 date를 입력했는가?
  - numeric field에 text를 입력했는가?

- HTML 제약 조건 유효성 검증

  | Attribute | Description                                         |
  | :-------- | :-------------------------------------------------- |
  | disabled  | Specifies that the input element should be disabled |
  | max       | Specifies the maximum value of an input element     |
  | min       | Specifies the minimum value of an input element     |
  | pattern   | Specifies the value pattern of an input element     |
  | required  | Specifies that the input field requires an element  |
  | type      | Specifies the type of an input element              |

  

- CSS 제약 조건 유효성 검증

  | Selector  | Description                                                  |
  | :-------- | :----------------------------------------------------------- |
  | :disabled | Selects input elements with the "disabled" attribute specified |
  | :invalid  | Selects input elements with invalid values                   |
  | :optional | Selects input elements with no "required" attribute specified |
  | :required | Selects input elements with the "required" attribute specified |
  | :valid    | Selects input elements with valid values                     |

## DOM CSS

- HTML 스타일 변경하기

  `document.getElementById(id).style.property = new style`
  
- 이벤트를 사용하여 변경하기

  ```
  <!DOCTYPE html>
  <html>
  <body>
  
  <h1 id="id1">My Heading 1</h1>
  
  <button type="button"
  onclick="document.getElementById('id1').style.color = 'red'">
  Click Me!</button>
  
  </body>
  </html>
  ```

  

## DOM Animations

- HTML의 id를 지정한 후, CSS 파일에서 #id명 으로 지정한다.

  ```
  <div id ="container">
    <div id ="animate">My animation will go here</div>
  </div>
  ```

  ```
  #container {
    width: 400px;
    height: 400px;
    position: relative;
    background: yellow;
  }
  #animate {
    width: 50px;
    height: 50px;
    position: absolute;
    background: red;
  }
  ```

- 애니메이션 코드

  - frame() 함수 실행 시간 간격을 5ms로 지정한 것이다.

  ```
  id = setInterval(frame, 5);
  
  function frame() {
    if (/* test for finished */) {
      clearInterval(id);
    } else {
      /* code to change the element style */ 
    }
  }
  ```

  

## DOM Events

- JavaScript는 HTML 요소를 클릭할 때와 같이 이벤트가 발생할 때 실행할 수 있다.
  
  - 이벤트 예시: 클릭, 웹 페이지 로드, 이미지 로드, 마우스 오버, 폼 제출
  
  ```
  <!DOCTYPE html>
  <html>
  <body>
  
  <h1 onclick="this.innerHTML = 'Ooops!'">Click on this text!</h1>
  
  </body>
  </html>
  ```
  
  - 다음과 같이 함수를 만들 수도 있다.
  
  ```
  <!DOCTYPE html>
  <html>
  <body>
  
  <h1 onclick="changeText(this)">Click on this text!</h1>
  
  <script>
  function changeText(id) {
    id.innerHTML = "Ooops!";
  }
  </script>
  
  </body>
  </html>
  ```

- HTML 이벤트

  ```
  <button onclick="displayDate()">Try it</button>
  ```

- HTML DOM을 이용한 이벤트

  ```
  <script>
  document.getElementById("myBtn").onclick = displayDate;
  </script>
  ```

- onload, onunload 이벤트: 사용자가 입력하거나 페이지를 떠날 때 발생

  ```
  <!DOCTYPE html>
  <html>
  <body onload="checkCookies()">
  
  <h2>JavaScript HTML Events</h2>
  
  <p id="demo"></p>
  
  <script>
  function checkCookies() {
    var text = "";
    if (navigator.cookieEnabled == true) {
      text = "Cookies are enabled.";
    } else {
      text = "Cookies are not enabled.";
    }
    document.getElementById("demo").innerHTML = text;
  }
  </script>
  
  </body>
  </html> 
  ```

- onchange 이벤트: 입력 필드의 유효성을 검증할 때 사용

  - 대문자로 변환시켜 주는 이벤트

  ```
  <!DOCTYPE html>
  <html>
  <body>
  
  <h2>JavaScript HTML Events</h2>
  Enter your name: <input type="text" id="fname" onchange="upperCase()">
  <p>When you leave the input field, a function is triggered which transforms the input text to upper case.</p>
  
  <script>
  function upperCase() {
    const x = document.getElementById("fname");
    x.value = x.value.toUpperCase();
  }
  </script>
  
  </body>
  </html>
  ```

- 이 외에, onmouseover, onmouseout, onmousedown, onmouseup 이벤트 등이 존재한다.



## DOM Event Listener

- addEventListener()는 해당 요소에 이벤트를 연결하는데, 기존에 연결된 이벤트에 덮어쓰기를 하지 않는다. 즉, 여러 개의 이벤트를 하나의 요소에 연결할 수 있다. 매개변수 useCapture(true/false)는 event bubbling, event capturing 사용을 결정한다. 선택 사항이다.

  ```
  element.addEventListener(event, function, useCapture);
  ```

- removeEventListener()를 이용하여 이벤트를 삭제할 수 있다.

  ```
  element.removeEventListener("mousemove", myFunction);
  ```

## DOM Navigation

- 노드 관계

  - 최상위 노드를 루트 노드라고 한다.
  - 모든 노드는 루트를 제외하고 하나의 부모를 가진다.
  - 노드는 여러 자식을 가질 수 있다.
  - 부모가 같은 노드를 sibling라고 한다.

  ![Node tree](https://www.w3schools.com/js/pic_navigate.gif)

  ```
  <html>
  
    <head>
      <title>DOM Tutorial</title>
    </head>
  
    <body>
      <h1>DOM Lesson one</h1>
      <p>Hello world!</p>
    </body>
  
  </html>
  ```

- 노드 탐색에 사용되는 속성

  - `parentNode`
  - `childNodes[*nodenumber*]`
  - `firstChild`
  - `lastChild`
  - `nextSibling`
  - `previousSibling`

- 예시: 아래 세 줄은 같은 값을 가져온다.

  ```
  myTitle = document.getElementById("demo").innerHTML;
  myTitle = document.getElementById("demo").firstChild.nodeValue;
  myTitle = document.getElementById("demo").childNodes[0].nodeValue;
  ```

- 전체 document 접근하기

  ```
  document.body.innerHTML
  document.documentElement.innerHTML
  ```

- nodeName

  - nodeName은 읽기 전용이다.
  - element 노드의 nodeName은 태그 이름과 동일하다.
  - attribute 노드의 nodeName은 속성 이름이다.
  - 텍스트 노드의 nodeName은 #text이다.
  - documen 노드의 nodeName은 #document이다.

  ```
  document.getElementById("id01").nodeName
  ```

- nodeValue
  - element 노드의 nodeValue는 `null`이다.
  - 텍스트 노드의 nodeValue는 텍스트 자체이다.
  - attribute 노드의 nodeValue는 attribute 값이다.

- nodeType

  | Node               | Type | Example                                         |
  | :----------------- | :--- | :---------------------------------------------- |
  | ELEMENT_NODE       | 1    | <h1 class="heading">W3Schools</h1>              |
  | ATTRIBUTE_NODE     | 2    | class = "heading" (deprecated)                  |
  | TEXT_NODE          | 3    | W3Schools                                       |
  | COMMENT_NODE       | 8    | <!-- This is a comment -->                      |
  | DOCUMENT_NODE      | 9    | The HTML document itself (the parent of <html>) |
  | DOCUMENT_TYPE_NODE | 10   | <!Doctype html>                                 |

## DOM Nodes

- HTML element 새로 만들기: 부모 노드의 마지막 child 추가하기

  ```
  <div id="div1">
    <p id="p1">This is a paragraph.</p>
    <p id="p2">This is another paragraph.</p>
  </div>
  
  <script>
  const para = document.createElement("p");
  const node = document.createTextNode("This is new.");
  para.appendChild(node);
  
  const element = document.getElementById("div1");
  element.appendChild(para);
  </script>
  ```

  - 먼저, <p> element를 만든다.
  - 텍스트를 생성하고 appendChild를 수행하여 텍스트 노드를 추가한다.

- insertBefore()를 사용하면 원하는 위치에 child를 추가할 수 있다.

- HTML element 제거하기

  ```
  <div>
    <p id="p1">This is a paragraph.</p>
    <p id="p2">This is another paragraph.</p>
  </div>
  
  <script>
  const elmnt = document.getElementById("p1"); elmnt.remove();
  </script>
  ```

- remove()를 지원하지 않는 경우

  ```
  <div id="div1">
    <p id="p1">This is a paragraph.</p>
    <p id="p2">This is another paragraph.</p>
  </div>
  
  <script>
  const parent = document.getElementById("div1");
  const child = document.getElementById("p1");
  parent.removeChild(child);
  </script>
  ```

- HTML element 교체하기

  ```
  <div id="div1">
    <p id="p1">This is a paragraph.</p>
    <p id="p2">This is another paragraph.</p>
  </div>
  
  <script>
  const para = document.createElement("p");
  const node = document.createTextNode("This is new.");
  para.appendChild(node);
  
  const parent = document.getElementById("div1");
  const child = document.getElementById("p1");
  parent.replaceChild(para, child);
  </script>
  ```

  

## DOM Collections

- `HTMLCollection`객체는 HTML element의 배열과 같은 리스트이다.

  ```[]
  const myCollection = document.getElementsByTagName("p");
  ```

- length를 이용해 컬렉션 element 색상 변경하기

  ```
  const myCollection = document.getElementsByTagName("p");
  for (let i = 0; i < myCollection.length; i++) {
    myCollection[i].style.color = "red";
  }
  ```

  

## DOM Node Lists

- `NodeList` 객체는 문서로부터 추출된 노드의 리스트이다.

  ```
  const myNodeList = document.querySelectorAll("p");
  ```

  ```
  const myNodelist = document.querySelectorAll("p");
  for (let i = 0; i < myNodelist.length; i++) {
    myNodelist[i].style.color = "red";
  }
  ```



- HTMLCollection과 NodeList 차이점?
  - HTMLCollection은 HTML element
  - NodeList는 document node
  - 거의 비슷하다.