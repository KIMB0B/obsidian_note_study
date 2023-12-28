# 설치
### [[NPM]]
```bash
npm install @nestjs/graphql @nestjs/apollo graphql apollo-server-express
```

### [[Yarn]]
```bash
yarn add @nestjs/graphql @nestjs/apollo graphql apollo-server-express @apollo/server
```

--- 
# 빌드 방식

###  Schema First
> [[GraphQL]]의 schema를 먼저 직접 정의하고, 그 schema 정의에 맞게 코드를 작성하는 방법

### Code First
> [[Decorator]]와 TypeScript 클래스를 사용하여 먼저 작성한 Resolver 을 기반으로 해당 GraphQL 스키마를 자동 생성하는 방법

--- 
# 설정

> app.module.ts에서 설정이 가능함

**예시1)** [[#Schema First]] 방식으로 만든 스키마의 경로를 직접 저장하여 설정한 경우
```typescript
import { ApolloDriver, ApolloDriverConfig } from '@nestjs/apollo'; 
import { Module } from '@nestjs/common'; 
import { GraphQLModule } from '@nestjs/graphql'; 

@Module({ 
	imports: [ 
		... // 여러 API의 모듈들
		GraphQLModule.forRoot<ApolloDriverConfig>({ 
			driver: ApolloDriver, 
			typePaths: ['./*.graphql'],
		}),
	],
})
export class AppModule {}
```

**예시2)** [[#Code First]] 방식으로 원하는 경로에 스키마 파일이 자동으로 생성되도록 설정한 경우
```typescript
import { ApolloDriver, ApolloDriverConfig } from '@nestjs/apollo'; 
import { Module } from '@nestjs/common'; 
import { GraphQLModule } from '@nestjs/graphql'; 

@Module({ 
	imports: [ 
		... // 여러 API의 모듈들
		GraphQLModule.forRoot<ApolloDriverConfig>({ 
			driver: ApolloDriver, 
			autoSchemaFile: 'src/commons/graphql/schema.gql',
		}),
	],
})
export class AppModule {}
```

--- 
# 파일 구조

> 각 API 분류별로 아래 세 파일을 한 세트로 만듦

- `~.module.ts` : **.resolver.ts** + .**service.ts** 합쳐주는 파일
- `~.resolver.ts` : 실질적 API 로직
    - Rest API에서의 ~.controller.ts 와 같은 파일로 이름만 다른 파일
- `~.service.ts` : 핵심 비즈니스 로직