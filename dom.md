> 참고한 사이트 : https://www.w3schools.com/js/js_htmldom.asp

![image](https://user-images.githubusercontent.com/63496777/148941663-86a4ca01-cfb2-4ded-b69f-5b857a608e8c.png)

HTML DOM을 한마디로 정의하자면,
The HTML DOM is a standard for how to get, change, add, or delete HTML elements.
라고 할 수 있다.
더 짧게 표현하면, "HTML DOM - standard model for HTML documents" 라고 할 수 있겠다.

가장 기본적인, innerHTML을 사용한 코드를 보자.
```html
<html>
<body>

<p id="demo"></p>

<script>
document.getElementById("demo").innerHTML = "Hello World!";
</script>

</body>
</html>
```
***
다음으로는 HTML DOM Document Object에 대해 살펴보자.
![image](https://user-images.githubusercontent.com/63496777/148942245-1239c79a-9e99-44de-8722-7038661ec4f2.png)
![image](https://user-images.githubusercontent.com/63496777/148942277-2183fcba-588f-4531-8f67-302533a344c3.png)
추가적으로, html objects를 찾는 법이 궁금하다면 https://www.w3schools.com/js/js_htmldom_document.asp 을 참고하자.
***
Finding HTML elements by id / tag name / class name / CSS selectors / HTML object collections
어떻게 사용하는 법은 다 알고 있으니 그때 그때 찾아보면서 꺼내쓰면 될 거 같다. https://www.w3schools.com/js/js_htmldom_elements.asp 참고
찾은 object는 css도 바꿀 수 있고, event도 추가할 수 있다.
