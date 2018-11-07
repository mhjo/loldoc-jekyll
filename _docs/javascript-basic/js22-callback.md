---
title: "JavaScript 콜백함수"
course: "javascript-basic"
date:   2018-06-26 14:00:00 +0900
---




Javascript에서 함수는 일급 객체입니다. 따라서 함수 자체를 다른 함수의 파라미터로 넘길 수 있고, 넘겨받은 함수를 언제 실행할지 결정할 수도 있습니다. 이렇게 다른 함수에 인수로 넘겨지는 함수를 콜백함수 (Callback Function) 라고 부릅니다.



## 콜백함수의 기본

```js
// 함수 선언
function sum(a, b, callback) {
  var result = a + b;
  callback(result);
  return result;
}
```

위의 예에서 정의한 `sum` 함수는 인수 a와 b의 합을 구한 후 결과값을 리턴하는 함수입니다. 그리고 그전에 callback을 이용해서 결과값을 전달하고 있습니다.

이렇게 콜백함수를 사용하면 함수 내부에서는 넘겨받은 함수를 언제 실행할지 결정할 수 있습니다. 이를 통해 특정한 명령의 실행을 마친 후에 넘겨받은 콜백함수를 실행하는 방식으로 콜백함수에 특정 처리의 제어권을 넘길 수 있습니다.



함수 사용하기

위에 정의한 `sum` 함수를 사용해 보겠습니다. 함수에 정의한 콜백함수의 인자값으로 넘겨준 함수의 결과값을 이용해 추가적인 조치를 실행하는 모습입니다.

```js
var r = sum(10, 20, function(result) {
  console.log('SUM ' + result);  // 'SUM 30'
});
console.log(r);  // 30
```



이렇게 콜백함수를 이용하면 함수의 처리가 끝난 후, 특정한 콜백 함수를 실행해 주도록 요청하는 작업을 처리할 수 있습니다. 이러한 특성을 이용해 콜백함수는 사용자 이벤트 처리 및 비동기 처리 등에 폭넓게 사용되고 있습니다.


