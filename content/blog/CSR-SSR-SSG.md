---
external: false
title: "CSR, SSR, SSG"
description: "CSR, SSR은 렌더링 되는 위치, SSR, SSG는 html이 생성되는 시점에 따라 다르다."
date: 2023-09-16
---

## CSR (Client-Side Rendering), SSR (Server-Side Rendering), SSG (Static Site Generation)는 웹 사이트를 만드는 다양한 방법들 중 대표적인 것들로, 필요에 따라 적절한 기술을 선택할 수 있다.

CSR은 사용자와의 상호작용을 중요시할 때 사용된다. 서버로부터 기본적인 데이터만 지니고 내용이 없는 html을 받는다.  
(React를 예로 들면, id가 root인 빈 div 태그만 body에 존재한다)  
다만, 초기에 크기가 큰 js 파일을 내려받아야 하고 빈 내용물 때문에 SEO 최적화에 불리하다.

SSR은 반면에 서버로부터 완성된, 데이터를 모두 지니는 html을 받는다.  
때문에 초기 로딩이 빠르고 SEO 최적화에 적절하다.  
다만, 매번 새로운 페이지에 접근하면 html을 내려받아야 한다.  
(next.js는 SSR을 사용하지만, 내려받은 html과 js을 연동하여 React화 하는 과정을 거치기에 페이지를 내려 받은 후에는 CSR처럼 작동한다)

SSG는 미리 모든 페이지를 빌드하여 정적 웹 사이트를 구현하는 방법이다.  
미리 정해지고 바뀔일이 없는 페이지를 생성하는데 유리하며, SSR에 비해서 미리 생성된 html을 내려받기에 더 빠르다.  
다만, 동적으로 데이터가 변경되는 경우에는 적절하지 않을 수 있다.
