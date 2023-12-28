해당 파일 구조는 [[GraphQL in NestJS|NestJS의 GraphQL]] 파일 구조에 대한 설명

# 폴더 구조
![[NestJS GraphQL 폴더 구조.png]]
- 각 api별로 폴더를 만든 후 module, resolver, service를 세트로 구성
- 만든 api폴더들을 apis 폴더에 한곳으로 저장
- commons폴더에는 생성될 gql파일이 있을 공간을 만들어줌

--- 
# Service

예시코드
```typescript
import { Injectable, Scope } from '@nestjs/common';

@Injectable() 
export class BoardsService { qqq(): string { return 'Hello World!'; } }
```