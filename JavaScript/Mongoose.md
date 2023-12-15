# 정의

> [[MongoDB]]와 [[Express]] 웹 애플리케이션 프레임워크 간 연결을 생성하는 라이브러리

---
# 설치

### [[NPM]]
```
npm install mongoose
```
### [[Yarn]]
```
yarn add mongoose
```

---
# 사용법

### 연결
```
import mongoose from "mongoose";

mongoose.connect('mongodb://localhost:27017/schema')
```

### 스키마 생성
```
const testschema = new mongoose.Schema({
	name: String,
	age: { type: Number, min: 18, max: 65 },
	updated: {type: Date, default: Date.now }
})
```