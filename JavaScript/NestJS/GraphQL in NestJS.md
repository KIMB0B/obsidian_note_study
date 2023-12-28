# 설치
### [[NPM]]
```bash
npm install @nestjs/graphql @nestjs/apollo graphql apollo-server-express
```

### [[Yarn]]
```bash
yarn add @nestjs/graphql @nestjs/apollo graphql apollo-server-express
```

--- 

# 빌드 방식

###  Schema First
> graphql의 schema를 먼저 직접 정의하고, 그 schema 정의에 맞게 코드를 작성하는 방법

### Code First
> 데코레이터와 TypeScript 클래스를 사용하여 먼저 작성한 Resolver 을 기반으로 해당 GraphQL 스키마를 자동 생성하는 방법

--- 

# 설정

app.module.ts에서 설정이 가능함

```typescript
import { ApolloDriver, ApolloDriverConfig } from '@nestjs/apollo'; 
import { Module } from '@nestjs/common'; 
import { GraphQLModule } from '@nestjs/graphql'; 

@Module({ 
	imports: [ 
		... // 여러 
		GraphQLModule.forRoot<ApolloDriverConfig>({ 
			driver: ApolloDriver, 
			autoSchemaFile: 'src/commons/graphql/schema.gql',
		}),
	],
})
export class AppModule {}
```