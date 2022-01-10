# 

# DOM

---

    DOM이라는 것은 Document Object Model의 약자로 문서를 특정 Object들로 이루어진 Model의 형태로 구성하는 방식(?)인것 같다. 그 중에서도 HTML DOM에 대해서 알아 볼건데 HTML DOM은 Object들이 Tree형태로 이루어 져있는 model이다.

<p align="center">HTML DOM Tree</p>

<img title="" src="./DOM tree.jpg" alt="" data-align="center">

영어로 쉽게 요약하면

**The HTML DOM is a standard for how to get, change, add, or delete HTML elements.**

> 한국어로는 HTML 엘레멘트를 얻고 바꾸고 추가하고 지우는 기준? 기본?

## DOM Programming Interface

---

    HTML DOM에서 elements는 objects로 정의되어 있기 때문에 각각의 object는 property와 method를 가지고있다. 대표적인 것은 getElementById(method), innerHTML(property)가 있다.

## Finding HTML Elements

| Method                                | 설명                       |
| ------------------------------------- | ------------------------ |
| document.getElementById(id)           | id로 element 찾기           |
| document.getElementsByTagName(name)   | tag name으로 elements 찾기   |
| document.getElementsByClassName(name) | class name으로 elements 찾기 |

## Changing HTML Elements

| Property                                 | 설명                        |
| ---------------------------------------- | ------------------------- |
| *element*.innerHTML =  new html content  | Element의 내부HTML 변경        |
| *element*.attribute = new value          | Element의 특정 속성을 변경        |
| *element*.style.property = new style     | Element의 스타일의 속성을 변경      |
| Method                                   | 설명                        |
| *element*.setAttribute(attribute, value) | attibute의 value를 설정하는 메소드 |

## Adding and Deleting Elements

| Method                            | 설명                                |
| --------------------------------- | --------------------------------- |
| document.createElement(*element*) | Element 생성                        |
| document.removeChild(*element*)   | Element 삭제                        |
| document.appendChild(*element*)   | Element 추가                        |
| document.replaceChild(*new, old*) | Element 바꾸기                       |
| document.write(*text*)            | Write into the HTML output stream |

> write는 정확히 어떻게 되는지 모르겠다. 그냥 text를 적는 메쏘드인거같다.

## Adding Events Handlers

| Method                                                     | Description                |
| ---------------------------------------------------------- | -------------------------- |
| document.getElementById(*id*).onclick = function(){*code*} | onclick 이라는 이벤트에 함수를 추가한다. |
| element.addEventListener(event, function, useCapture)      | Element에 이벤트를 추가하는 메쏘드     |

> 아마 이외에도 다른 이벤트에도 같은 형식으로 이벤트 핸들러를 추가 가능할 것이다.removeEventListener(event) 도 있다.

## DOM Nodes and Relationships

<center>DOM Relationships</center>

<img title="DOM Relationships" src="./DOM Relationships.jpg" alt="" data-align="center">

    Attribute(더이상 사용하지 않음), Element, Text 모두 각각 하나의 Node이다. 각각의 노드들의 관계는 위 그림과 같다.

## Node Name, Value, Type

- Node name
  
  - read-only
  
  - tag-name (element)
  
  - attribute name
  
  - #text
  
  - #document

- Node value
  
  - null (element)
  
  - text itself
  
  - attribute value

- Node type

| Node               | Type | Example                                         |
| ------------------ | ---- | ----------------------------------------------- |
| ELEMENT_NODE       | 1    | <h1 class="heading">W3Schools</h1>              |
| ATTRIBUTE_NODE     | 2    | class = "heading" (deprecated)                  |
| TEXT_NODE          | 3    | W3Schools                                       |
| COMMENT_NODE       | 8    | <!-- This is a comment -->                      |
| DOCUMENT_NODE      | 9    | The HTML document itself (the parent of <html>) |
| DOCUMENT_TYPE_NODE | 10   | <!Doctype html>                                 |

## HTML Collection vs HTML DOM Node List

- HTMLCollection
  
  - getElementsByTagname()
  
  - It's a object
  
  - array-like list of HTML elements
  
  - name, id, index 로 접근 가능

- NodeList
  
  - almost the smae as an HTMLCollection object
  
  - document.querySelectorAll(tagname)
  
  - index number 만으로만 접근 가능
  
  - attribute nodes and text nodes를 포함

> 두가지 모두 array가 아니기 때문에 valueOf(), push(), pop(), join() 과 같은 method를 사용하지 못한다.
