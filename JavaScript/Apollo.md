# 정의
> JavaScript에서 [[GraphQL]] 서버 개발을 하게 해주는 프레임워크 중 하나.
> Swagger같은 Dosc가 필요없고, 함수를 사용하는것과 비슷함.

# 설치
### [[NPM]]
```
npm install @apollo/server
```
### [[Yarn]]
```
yarn add @apollo/server
```

# 초기설정
### 기초
```
import { ApolloServer } from '@apollo/server';
import { startStandaloneServer } from '@apollo/server/standalone';

const typeDefs = `#graphql
	type Query { 
		...
	}, 
	type Mutation {
		...
	}
` 
const resolvers = { 
	Query: { 
		...
	}, 
	Mutation: {
		...
	}
} 

const server = new ApolloServer({ 
	typeDefs: typeDefs, 
	resolvers: resolvers,
}) 

startStandaloneServer(server) //기본적으로 4000번 포트
```

### [[CORS]]
```
...
const server = new ApolloServer({ 
	typeDefs: typeDefs, 
	resolvers: resolvers,
	cors: true,
}) 
...
```