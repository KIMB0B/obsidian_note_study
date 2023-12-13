# 정의
> JavaScript에서 [[Rest API]] 서버 개발을 하게 해주는 프레임워크 중 하나.

# 설치
### [[NPM]]
```
npm install express
```
### [[YARN]]
```
yarn add express
```

# 초기설정
### 기초
```
import express from `express`;

const app = express();
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