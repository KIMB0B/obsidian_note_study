# 정의

> [[MongoDB]]와 [[Express]] 웹 애플리케이션 프레임워크 간 연결을 생성하는 라이브러리
> [[MongoDB]]의 쿼리문을 내가 작성한 코드를 보고 대신 실행해주는 역할

---
# 설치

### [[NPM]]
```bash
npm install mongoose
```
### [[Yarn]]
```bash
yarn add mongoose
```

---
# 사용법

### 연결
```javascript
import mongoose from "mongoose";

mongoose.connect('mongodb://localhost:27017/schema')
	.then(() => )//접속 성공한 경우
	.catch(() => )//접속 실패한 경우
```

### 스키마 생성
```javascript
const schema = new Schema({
  name: String,
  binary: Buffer,
  living: Boolean,
  updated: { type: Date, default: Date.now },
  age: { type: Number, min: 18, max: 65 },
  mixed: Schema.Types.Mixed,
  _someId: Schema.Types.ObjectId,
  decimal: Schema.Types.Decimal128,
  array: [],
  ofString: [String],
  ofNumber: [Number],
  ofDates: [Date],
  ofBuffer: [Buffer],
  ofBoolean: [Boolean],
  ofMixed: [Schema.Types.Mixed],
  ofObjectId: [Schema.Types.ObjectId],
  ofArrays: [[]],
  ofArrayOfNumbers: [[Number]],
  nested: {
    stuff: { type: String, lowercase: true, trim: true }
  },
  map: Map,
  mapOfString: {
    type: Map,
    of: String
  }
});
```

### 모델 생성
```javascript
const Model = mongoose.model("Model", schema);
```

### 조회
```javascript
Model.find();
```

### 등록
```javascript
const model = new Model({ ... });
model.save();
```

### 디버그
```javascript
mongoose.set("debug", true);
```