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

  





https://www.w3schools.com/js/js_htmldom.asp