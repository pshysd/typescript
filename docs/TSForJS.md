# 타입 추론

```typescript
let helloWorld = 'Hello World';

// ^?
```

# 타입 정의

name: string과 id: number를 포함하는 추론 타입을 객체를 생성하는 예제

```typescript
const user = {
	name: 'Hayes',
	id: 0,
};
```

이 객체의 형태를 명시적으로 나타내기 위해서는 interface로 선언한다.

```typescript
interface User {
	name: string;
	id: number;
}
```

이제 변수 선언 뒤에 `: TypeName`의 구문을 사용해 JavaScript 객체가 새로운 interface의 형태를 따르고 있음을 선언할 수 있다.

```typescript
interface User {
	name: string;
	id: number;
}

const user: User = {
	name: 'Hayes',
	id: 0,
};
```

해당 interface에 맞지 않는 객체를 생성하면 TypeScript는 화를 냄

```ts
interface User {
	name: string;
	id: number;
}

const user: User = {
	username: 'Hayes', // @errors: 2322
	id: 0,
};
```

JavaScript는 Class와 OOP를 지원하기 때문에, TypeScript 또한 동일하다<br>

> interface는 class로도 선언할 수 있다.

```ts
interface User {
	name: string;
	id: number;
}

class UserAccount {
	name: string;
	id: number;

	constructor(name: string, id: number) {
		name;
		id;
	}
}

const user: User = new UserAccount('Murphy', 1);
```

인터페이스는 함수에서 매개 변수와 리턴 값을 명시하는데 사용되기도 한다.
