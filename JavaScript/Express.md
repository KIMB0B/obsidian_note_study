# 정의
> JavaScript에서 [[Rest API]] 서버 개발을 하게 해주는 프레임워크 중 하나.
---
# 설치
### [[NPM]]
```
npm install express
```
### [[YARN]]
```
yarn add express
```

---

# 초기설정
### 기초
```
import express from `express`;

const app = express();
```
### 미들웨어
[공식문서 참조](https://expressjs.com/ko/api.html#express)
```
app.use(express.json());
app.use(express.raw());
app.use(express.Router());
app.use(express.static());
app.use(express.text());
app.use(express.urlencoded());
```
### [[Swagger]]
swagger란 폴더를 만들고 그 안에 설정파일과 ~.swagger.js형식의 Swagger파일을 만듦

- 설정파일
```
export const options = { 
	definition: { 
		openapi: '3.0.0', 
		info: { 
			title: '나만의 미니프로젝트 API 명세서!!', 
			version: '1.0.0', 
		}, 
	}, 
	apis: ['./swagger/*.swagger.js'], 
};
```

- 메인코드에 적용
```
...
import swaggerUi from 'swagger-ui-express';
import swaggerJSDoc from 'swagger-jsdoc';
import { options } from './swagger/config.js';

...
app.use('/api-docs', swaggerUi.serve, swaggerUi.setup(swaggerJSDoc(options)));
```
### [[CORS]]
```
...
import cors from 'cors';

...
app.use(cors());            //모든 Origin 허용
app.use(cors({origin: ~})); //특정 Origin만 허용
```
---
# 메서드 구현
### GET
```
// localhost:3000/user?name=철수
app.get("/user", (req, res) => {
	const name = req.query.name;
	res.status(200);
	res.send(users.filter( user => name));
});
```
### POST
```
// localhost:3000
// {
// 	 name: "철수"
// }
app.post("/user", (req, res) => {
	const newUser = req.body;
	users.push(newUser);
	res.status(200);
	res.send(`${newUser.name} 사용자 추가 성공`);
});
```