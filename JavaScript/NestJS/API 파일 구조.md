해당 파일 구조는 [[GraphQL in NestJS|NestJS의 GraphQL]] 파일 구조에 대한 설명

# 폴더 구조
![[NestJS GraphQL 폴더 구조.png]]
- 각 api별로 폴더를 만든 후 module, resolver, service를 세트로 구성
- 만든 api폴더들을 apis 폴더에 한곳으로 저장
- commons폴더에는 생성될 gql파일이 있을 공간을 만들어줌

--- 
# Service

**예시코드**
```typescript
import { Injectable } from '@nestjs/common';

@Injectable() 
export class BoardsService { 
	findAll(): Board[] { // 게시물 조회 기능
		...
		return boards;
	}
	
	create(...): string { // 게시물 등록 기능
		...
		return '게시물 등록에 성공하였습니다.';
	}
}
```
- @Injectable() [[Decorator]]를 통해 해당 클래스가 서비스 클래스인 것으로 선언됨
- 핵심 비즈니스 로직을 각 함수로 구현

--- 
# Resolver(Controller)

**예시코드**
```typescript
import { BoardsService } from './boards.service';
import { Args, Mutation, Query, Resolver } from '@nestjs/graphql';

@Resolver()
export class BoardsResolver {
	constructor(private readonly boardsService: BoardsService) {}

	@Query(() => [Board], { nullable: true })
	fetchBoards(): Board[] {
		return this.boardsService.findAll();
	}

	@Mutation(() => String)
	createBoard(@Args('???') ???: ???, ...): string {
		return this.boardsService.create(...);
	}
}
```
- @Resolver() [[Decorator]]를 통해 해당 클래스가 컨트롤러 클래스인 것으로 선언됨
- Query(조회 기능)과 Mutation(수정 기능)을 나누어 구현
- @Args [[Decorator]]를 사용하여 API에서 받은 인자를 사용 가능

--- 
# Module

**예시코드**
```typescript
import { Module } from '@nestjs/common';
import { BoardsResolver } from './boards.resolver';
import { BoardsService } from './boards.service';

@Module({
	imports: [],
	controllers: [],
	providers: [BoardsResolver, BoardsService],
})
export class BoardsModule {}
```
- @Module() [[Decorator]]를 통해 해당 클래스가 모듈 클래스인 것으로 선언됨
- providers 부분에 구현한 Resolver와 Service를 둘 다 넣어줌

--- 
# 추가 사항

추가적으로 Entity와 DTO, Interface의 구현 가능