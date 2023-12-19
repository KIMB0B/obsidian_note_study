# 정의

> JavaScript에 타입을 부여한 언어
> TypeScript 파일을 JavaScript로 변환한 후 실행되는 컴파일 언어

---
# 특징

- [[Type Definition|타입지정]]을 통한 에러 사전 방지
- 코드 가이드 및 자동 완성으로 개발 생산성 향상

---
# 설치
### [[NPM]]
```bash
npm install typescript --dev
npm install ts-node # .ts 파일을 실행시키기 위한 패키지
```
### [[Yarn]]
```bash
yarn add typescript --dev
yarn add ts-node # .ts 파일을 실행시키기 위한 패키지
```

---
# package.json 설정

ts-node를 전역설치를 한 게 아니기 때문에 package.json의 scripts에 실행 명령어를 지정해줌
```json
// 예시
{ 
	"name": "project", 
	"version": "1.0.0", 
	"main": "index.js", 
	"license": "MIT", 
	"scripts": { 
		"start:dev": "ts-node index.ts" 
	}, 
	"devDependencies": { 
		"typescript": "^4.8.4" 
	}, 
	"dependencies": { 
		"ts-node": "^10.9.1" 
	} 
}
```

---
# tsconfig.json 설정

### tsconfig.json 생성
```bash
yarn tsc --init
```

### 생성된 예시
```json
{ 
	"compilerOptions": { 
		"target": "es2016", 
		"module": "commonjs", 
		"esModuleInterop": true, 
		"forceConsistentCasingInFileNames": true, 
		"strict": true, 
		"skipLibCheck": true, 
	} 
}
```
