---
external: false
title: "Callback과 Promise, 그리고 Async/Await"
description: "자바스크립트에서 비동기 처리를 하는 세 가지 방식"
date: 2023-09-09
---

## Callback은 콜백 지옥의 문제점이, 더 나아진 Promise. 그러나 역시 점점 들여쓰여지는 코드. 그보다도 더 읽기 쉬운 Async 함수

기본적으로 자바스크립트에서 비동기 처리를 하기 위해서는 함수의 인자로 Callback을 주어, 이 주어진 Callback을 원하는 타이밍에 사용하는 방법이 있다.  
다만, 여러번의 Callback 처리를 하게 되면 코드가 복잡해지는 문제점이 발생한다.  
그 대안으로 ES6이후 도입된 Promise 객체가 있는데, 인자로 resolve, reject를 갖는 함수를 받는다.  
Promise를 통해 비동기 처리 후 데이터를 원하는 타이밍에 resolve를 처리하고 reject로 에러를 처리하며 이를 각각 then과 catch 체이닝으로 받아 사용할 수 있다.  
다만, then과 catch 역시 여러번 사용되면 코드를 복잡하게 만든다.  
이에 따라서, ES2017에 새로 도입된 sugar syntax문법으로 Async/Await 문법이 있다.  
무조건 Promise 객체를 반환하는 Async 함수는 내부에 비동기 처리를 원하는 부분에 await를 앞에 붙이게 되고, 그 뒤로 이어지는 코드들은 마치 Promise의 then 내부의 코드들처럼 await 줄의 실행이 끝나고 실행되게 된다.
