---
title: 	"JavaScript 객체와 배열"
course: "javascript-basic"
date: 	2018-06-21 13:00:00 +0900
---



자바스크립트에서 원시 자료형(string, number, boolean 등)을 제외한 모든 자료형은 객체 (Object) 라고 하고, 참조 자료형 (Reference Data Type)이라고도 해요. 자바스크립트의 객체의 여러가지 형태로는 객체 (Object), 함수 (Function), 배열 (Array) 등이 있어요.

사실 객체라는 표현은 아주 광범위한 표현이고, 자료형의 하나를 넘어서 프로그래밍 패러다임을 규정짓기 위한 하나의 용어이기도 한데, 자바스크립트에서는 개념이 혼재되어 있어서 다른 언어를 사용하시던 분들은 헷갈릴 수 도 있어요. 우선은 참조 자료형의 하나로 생각해보죠. 





## 객체 (Object)

객체는 사전에 비유할 수 있어요. (실제로 파이썬이라는 프로그래밍 언어에서는 Dictionary 라는 자료형으로 사용하기도 하구요). 우리가 사전에서 단어를 찾으면 그 단어에 대한 설명이 적혀 있죠. 그리고 이러한 단어와 설명의 모음이 사전이 되는 것이구요. 여기서 단어를 키, 설명을 밸류라고 불러요.

즉, 객체는 키 (Key)와 값 (Value)의 쌍으로 이루어진 데이터의 집합이에요. 다시 말하면, 이름(Key)이 붙어있는 데이터 값 (Value) 들의 모음이에요.



지금까지 설명한 객체는 아래처럼 나타내요.

```js
var alice = {
  name: "Alice",
  age: 7
}
```

간단하죠? alice 라는 객체를 정의하고, 객체 내부에 키와 값은 콜론(:)으로 구분해 작성하며, 각각의 항목들은 콤마로 구분해요. 여기서 키는 프로퍼티 (property) 라고도 불려요. 

여기서 키 (Key) 는 어떠한 값을 불러오기 위한 방법이고, 객체 내에서 유일해야 해요. alice의 나이를 알고 싶은데 age라는 항목이 여러 개 인데다가 값이 다르면 어떤게 진짜 alice의 나이인지 알 수 없잖아요? 그러니까 키로 쓰이는 이름은 객체 내에서 하나만 존해해야 해요. 마치 변수와 비슷하죠. 변수명도 중복되면 의미가 없잖아요.

값(Value)은 키에 대한 값이에요. alice의 age는 7 인거죠. alice의 name은요? `"Alice"` 라는 문자열이에요. 값에는 어떠한 자료형의 값이든 사용할 수 있어요. 숫자, 문자열, 불리언과 같은 원시 자료형만이 아니라, 앞으로 배울 배열이나 함수, 다른 객체 등도 객체 내부에서 값으로 사용될 수 있어요.



### 객체 사용하기

객체는 중괄호(`{}`)를 이용해서 선언해요. 객체 내부에 아무런 값이 없는 비어있는 객체는 아래처럼 변수에 `{}` 를 이용해 선언할 수 있어요.

```js
// 비어있는 객체 선언
var obj = {};
```



객체 내부의 프로퍼티 값을 불러오려면 객체의 이름뒤에 점(.)을 찍고 키를 명시해 주면 되요. 즉 alice의 나이를 알고 싶다면 이렇게 해요.

```js
alice.age
//=> 7
```

혹은 대괄호를 이용해서 원하는 값을 조회할 수도 있어요.

```js
alice["age"]
//=> 7
```



객체에 새로운 프로퍼티와 값을 추가할 수도 있어요.

아래와 같이 추가하려고 하는 프로퍼티 이름에 값을 대입하면 새로운 프로퍼티가 객체에 추가되요. 만약 해당 프로퍼티가 이미 존재한다면 값을 덮어씌우게 되요.

```js
alice.gender = "female";
console.log(alice);  //-> { name: 'Alice', age: 7, gender: 'female' }
```



프로퍼티를 삭제할 때는 `delete` 연산자를 사용할 수 있어요.

```js
delete alice.gender;
```

이렇게 하면 alice 객체에서 gender 키-값 쌍은 삭제되는 거죠.





## 배열 (Array)

배열은 기능이 추가된 특수한 형태의 객체로, 데이터 값들만의 모음이라고 할 수 있어요. 

```javascript
var arr = ["Alice", 7, true];
```

배열은 대괄호를 이용해 선언하며, 각 배열의 요소는 콤마를 이용해 구분하며, 배열의 각 항목에는 어떠한 자료형의 값이 와도 상관 없어요.



### 배열 사용하기

변수를 선언하고 어떠한 값도 입력하지 않으면 비어있는 배열을 선언하는 거죠.

```js
// 비어있는 배열 선언
var emptyArr = [];
```



배열의 각 데이터 값에는 0부터 시작하는 인덱스 번호가 있어서 각 데이터 값을 확인할 수 있어요. 인덱스 값은 객체에서 키의 역할을 하는거죠. 우리는 이걸 배열의 요소에 접근한다고 표현해요. 즉 배열의 0번째 값 (즉, 첫번째 값)에 접근하기 위해서는 아래와 같이 해요.

```js
//배열 요소 접근
arr[0];
//=> 'Alice'
```

> 프로그래밍 언어에서 인덱스는 보통 0부터 시작해요. 배열의 첫 번째 요소의 인덱스는 1이 아니라 0인 거죠. 자바스크립트만 그런 것이 아니라 거의 대부분의 프로그래미이 언어가 그래요.



배열에 있는 요소의 개수는 length라는 프로퍼티를 이용해서 알 수 있어요. 우리가 만든 `arr` 라는 배열에는 세개의 값이 들어 있죠.

```js
// 배열 요소의 개수 구하기
arr.length;  
//=> 3
```





## 원시 자료형과 참조 자료형

원시 자료형과 참조 자료형을 나누는 기준이 뭘까요?

변수에 원시자료형의 값을 할당하면 값은 변수에게 할당된 메모리내의 구역에 저장되요. 즉, 변수라는 상자를 하나 만들고, 어떠한 물건을 변수 상자에 넣어 놓는 것으로 생각할 수 있어요.

```js
var primitive = 10;
var another = primitive;
console.log(primitive);  // 10
console.log(another);    // 10

primitive = 11;
console.log(primitive);  // 11
console.log(another);    // 10
```

primitive라는 변수를 선언하고 10이라는 값을 할당했어요. 그리고 another라는 변수를 선언하고 primitive 변수를 할당하게 되면 another에는 primitive의 값인 10이 복사되서 들어가게 되요.

이때 primitive의 값을 11로 변경하더라도 another 변수의 값은 여전히 10이에요. 이미 another라는 상자에다가 10이라는 값을 복사해 놓았으니 primitive의 값이 어떻게 되던지 상관없는 거죠.



하지만 변수에 참조 자료형의 값을 할당하게 되면 값은 메모리의 어딘가에 존재하게 되고, 변수는 이 참조 자료형이 있는 위치 정보만을 저장하게 되요. 즉, 변수 상자에는 물건이 있는 주소만 적혀있고, 실제 물건은 다른 곳에 존재하는 거죠. 

참조 자료형은 메모리의 주소를 이용해서 값을 참조하므로 각각의 다른 변수가 하나의 참조 자료형을 참조할 수 있어요.

```js
var primitive = { name: "Alice" };
var another = primitive;
console.log(primitive);  // { name: 'Alice' }
console.log(another);    // { name: 'Alice' }

primitive.name = "Dinah";
console.log(primitive);  // { name: 'Dinah' }
console.log(another);    // { name: 'Dinah' }
```



