---
external: false
title: "JS의 클로저란?"
description: "자바스크립트의 클로저(Closure)에 대해서 알아보기"
date: 2023-08-26
---

## 자바스크립트의 클로저는 접근할 수 없는 외부 영역에 선언된 변수에 접근할 수 있는 매커니즘이다.

클로저는 함수 내부에서 선언된 변수를 함수 외부에서 접근할 수 있는 경우를 의미한다.  
예를 들면, 함수를 반환하는 함수를 선언했을 때, 함수는 일급 객체의 성질을 갖기 때문에 반환된 함수가 변수에 할당될 수 있다.  
이때, 반환된 함수 내부에 선언된 변수는 원래대로라면 접근이 불가능한 변수가 되지만, 이 경우 변수에 할당된 함수를 통해서 외부에서 참조할 수 있다.  
이 경우 클로저가 생성이 되고 이를 private 변수를 구현하는데 사용할 수 있다.

```js
const closure = () => {
  let count = 0;
  function showCount() {
    // 내부함수이며 클로저
    return count;
  }
  function counting() {
    // 역시 내부함수이며 클로저, 함수 내부의 변수를 바꾼다.
    count++;
  }
  // showCount(); 만든 함수는 바로 실행하거나 리턴하여 사용하여야 한다.
  return {
    // 만든 여러개의 함수를 외부에서 사용할 수 있도록 객체로 반환
    showCount: showCount,
    counting: counting,
  };
};

count1 = closure();
count2 = closure();

console.log(count1.showCount(), count2.showCount()); // 0 0 출력
count1.counting(); // count1 함수의 count값만 변경
console.log(count1.showCount(), count2.showCount()); // 1 0 출력
```

- 예제 출처: https://velog.io/@citron03/%ED%81%B4%EB%A1%9C%EC%A0%80Closure
