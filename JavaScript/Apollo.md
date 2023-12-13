# 정의
> JavaScript에서 [[GraphQL]] 서버 개발을 하게 해주는 프레임워크 중 하나

# 설치
### [[NPM]]
```
npm install @apollo/server
```
### [[YARN]]
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
		qqq: String 
	} 
` 
const resolvers = { 
	Query: { 
		qqq: () => { 
			return "zxcvㅁㄴㅇㄹㅁㄴㅇㄹㅁㄴㅇㄹzxvzxㄴ" 
		} 
	} 
} 

const server = new ApolloServer({ 
	typeDefs: typeDefs, 
	resolvers: resolvers 
}) 

startStandaloneServer(server) //기본적으로 4000번 포트
```