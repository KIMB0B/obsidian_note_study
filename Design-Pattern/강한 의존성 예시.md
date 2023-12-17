---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
// index.js

import express from 'express'
import { ProductController } from './mvc/controllers/product.controller.js'

const app = express()

// 상품 API
const productController = new ProductController()
app.post("/products/buy", productController.buyProduct) // 상품 구매하기
app.post("/products/refund", productController.refundProduct) // 상품 환불하기


app.listen(3000, () => {
    console.log("백엔드 API 서버거 켜졌어요!!!")
}) ^3sWOLDWX

// product.controller.js

import { CashService } from "./services/cash.service.js";
import { ProductService } from "./services/product.service.js";

export class ProductController {
  buyProduct = (req, res) => {
    // 1. 가진돈 검증하는 코드
    const cashService = new CashService();
    const hasMoney = cashService.checkValue();

    // 2. 판매여부 검증하는 코드
    const productService = new ProductService();
    const isSoldout = productService.checkSoldout();
    
    // 3. 상품 구매하는 코드
    if (hasMoney && !isSoldout) {
      res.send("상품 구매 완료!!");
    }
  };

  refundProduct = (req, res) => {
    // 1. 판매여부 검증하는 코드 
    const productService = new ProductService();
    const isSoldout = productService.checkSoldout();
    // 2. 상품 환불하는 코드
    if (isSoldout) {
      res.send("상품 환불 완료!!");
    }
  };
} ^NMl9nw6S

컨트롤러 ^f53H6Um9

Index 파일 ^IOkHk4u7

API 안에 작성해야 할 구현 코드가 ^aDfMA0Os

컨트롤러에게 감 ^j9Kaf0N6

서비스 ^6jI508y5

// cash.servie.js

export class CashService {
    checkValue = () => {
        ...
    };
}
 ^EW3ufdkw

// product.service.js

export class ProductService {
    checkSoldOut = () => {
        ...
    };
} ^OHiCUX9C

여러 번 사용할 만한 비즈니스 로직은 ^4k46bYqp

서비스에서 단위별로 구현하여 사용함 ^ULe3jz6L

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.0.10",
	"elements": [
		{
			"type": "rectangle",
			"version": 98,
			"versionNonce": 1920034416,
			"isDeleted": false,
			"id": "UY5kuuc66fKixc3JYS_H5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -871.0803375244147,
			"y": -355.54914474487333,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 763.5416412353522,
			"height": 366.66664123535196,
			"seed": 1634147472,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1702745571740,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 185,
			"versionNonce": 513831536,
			"isDeleted": false,
			"id": "NUB9Hyzgvtg6kSog-eWrE",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -3.3719787597653976,
			"y": -371.174068450928,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 611.4584350585942,
			"height": 630.208358764649,
			"seed": 932706448,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1702747836191,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 329,
			"versionNonce": 52534384,
			"isDeleted": false,
			"id": "3sWOLDWX",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -834.1863098144535,
			"y": -326.5237564086916,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 707.0701904296875,
			"height": 307.2,
			"seed": 429053040,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702745781164,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 3,
			"text": "// index.js\n\nimport express from 'express'\nimport { ProductController } from './mvc/controllers/product.controller.js'\n\nconst app = express()\n\n// 상품 API\nconst productController = new ProductController()\napp.post(\"/products/buy\", productController.buyProduct) // 상품 구매하기\napp.post(\"/products/refund\", productController.refundProduct) // 상품 환불하기\n\n\napp.listen(3000, () => {\n    console.log(\"백엔드 API 서버거 켜졌어요!!!\")\n})",
			"rawText": "// index.js\n\nimport express from 'express'\nimport { ProductController } from './mvc/controllers/product.controller.js'\n\nconst app = express()\n\n// 상품 API\nconst productController = new ProductController()\napp.post(\"/products/buy\", productController.buyProduct) // 상품 구매하기\napp.post(\"/products/refund\", productController.refundProduct) // 상품 환불하기\n\n\napp.listen(3000, () => {\n    console.log(\"백엔드 API 서버거 켜졌어요!!!\")\n})",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "// index.js\n\nimport express from 'express'\nimport { ProductController } from './mvc/controllers/product.controller.js'\n\nconst app = express()\n\n// 상품 API\nconst productController = new ProductController()\napp.post(\"/products/buy\", productController.buyProduct) // 상품 구매하기\napp.post(\"/products/refund\", productController.refundProduct) // 상품 환불하기\n\n\napp.listen(3000, () => {\n    console.log(\"백엔드 API 서버거 켜졌어요!!!\")\n})",
			"lineHeight": 1.2,
			"baseline": 303
		},
		{
			"type": "text",
			"version": 199,
			"versionNonce": 1664919696,
			"isDeleted": false,
			"id": "NMl9nw6S",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 7.4597778320314205,
			"y": -352.7904891967777,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 590.625,
			"height": 595.1999999999999,
			"seed": 1880622224,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "SYiSM4WZfVUjwtMXwW-V8",
					"type": "arrow"
				}
			],
			"updated": 1702747902858,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 3,
			"text": "// product.controller.js\n\nimport { CashService } from \"./services/cash.service.js\";\nimport { ProductService } from \"./services/product.service.js\";\n\nexport class ProductController {\n  buyProduct = (req, res) => {\n    // 1. 가진돈 검증하는 코드\n    const cashService = new CashService();\n    const hasMoney = cashService.checkValue();\n\n    // 2. 판매여부 검증하는 코드\n    const productService = new ProductService();\n    const isSoldout = productService.checkSoldout();\n    \n    // 3. 상품 구매하는 코드\n    if (hasMoney && !isSoldout) {\n      res.send(\"상품 구매 완료!!\");\n    }\n  };\n\n  refundProduct = (req, res) => {\n    // 1. 판매여부 검증하는 코드 \n    const productService = new ProductService();\n    const isSoldout = productService.checkSoldout();\n    // 2. 상품 환불하는 코드\n    if (isSoldout) {\n      res.send(\"상품 환불 완료!!\");\n    }\n  };\n}",
			"rawText": "// product.controller.js\n\nimport { CashService } from \"./services/cash.service.js\";\nimport { ProductService } from \"./services/product.service.js\";\n\nexport class ProductController {\n  buyProduct = (req, res) => {\n    // 1. 가진돈 검증하는 코드\n    const cashService = new CashService();\n    const hasMoney = cashService.checkValue();\n\n    // 2. 판매여부 검증하는 코드\n    const productService = new ProductService();\n    const isSoldout = productService.checkSoldout();\n    \n    // 3. 상품 구매하는 코드\n    if (hasMoney && !isSoldout) {\n      res.send(\"상품 구매 완료!!\");\n    }\n  };\n\n  refundProduct = (req, res) => {\n    // 1. 판매여부 검증하는 코드 \n    const productService = new ProductService();\n    const isSoldout = productService.checkSoldout();\n    // 2. 상품 환불하는 코드\n    if (isSoldout) {\n      res.send(\"상품 환불 완료!!\");\n    }\n  };\n}",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "// product.controller.js\n\nimport { CashService } from \"./services/cash.service.js\";\nimport { ProductService } from \"./services/product.service.js\";\n\nexport class ProductController {\n  buyProduct = (req, res) => {\n    // 1. 가진돈 검증하는 코드\n    const cashService = new CashService();\n    const hasMoney = cashService.checkValue();\n\n    // 2. 판매여부 검증하는 코드\n    const productService = new ProductService();\n    const isSoldout = productService.checkSoldout();\n    \n    // 3. 상품 구매하는 코드\n    if (hasMoney && !isSoldout) {\n      res.send(\"상품 구매 완료!!\");\n    }\n  };\n\n  refundProduct = (req, res) => {\n    // 1. 판매여부 검증하는 코드 \n    const productService = new ProductService();\n    const isSoldout = productService.checkSoldout();\n    // 2. 상품 환불하는 코드\n    if (isSoldout) {\n      res.send(\"상품 환불 완료!!\");\n    }\n  };\n}",
			"lineHeight": 1.2,
			"baseline": 591
		},
		{
			"type": "arrow",
			"version": 151,
			"versionNonce": 803516528,
			"isDeleted": false,
			"id": "SYiSM4WZfVUjwtMXwW-V8",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 4.241305578817531,
			"y": -219.02296124345264,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 351.3634369264736,
			"height": 56.182098969282606,
			"seed": 2116932208,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702745771365,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "GmHooy_Re4bIciTaIbbXH",
				"focus": 0.15908501445400544,
				"gap": 2.955196113187533
			},
			"endBinding": {
				"elementId": "Lbrkx-CdoGg4LykaL9FpL",
				"focus": -0.024644118617546486,
				"gap": 6.589267688974182
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-271.15500186787983,
					13.473740204634169
				],
				[
					-351.3634369264736,
					56.182098969282606
				]
			]
		},
		{
			"type": "arrow",
			"version": 363,
			"versionNonce": 62152848,
			"isDeleted": false,
			"id": "XEQ7SWOqdv37_rV6gfav3",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 7.289356727233013,
			"y": 57.486101303227656,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 335.9956883176676,
			"height": 160.9568367638576,
			"seed": 1887320720,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702746993870,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "kKWCOmhXa6u13IsllzWJd",
				"focus": -0.5943015857175983,
				"gap": 5.9534343881906295
			},
			"endBinding": {
				"elementId": "sJq9WUA-g5cABa-pMxvEz",
				"focus": 0.20063655615769532,
				"gap": 1.0449615205787435
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-247.11992313348279,
					-72.41024604810063
				],
				[
					-335.9956883176676,
					-160.9568367638576
				]
			]
		},
		{
			"type": "ellipse",
			"version": 57,
			"versionNonce": 1263402608,
			"isDeleted": false,
			"id": "GmHooy_Re4bIciTaIbbXH",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 7.044738769531932,
			"y": -233.67422103881847,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 128.125,
			"height": 27.083358764648438,
			"seed": 995144336,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"id": "SYiSM4WZfVUjwtMXwW-V8",
					"type": "arrow"
				}
			],
			"updated": 1702745771365,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 142,
			"versionNonce": 2009681008,
			"isDeleted": false,
			"id": "kKWCOmhXa6u13IsllzWJd",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 12.253021240235057,
			"y": 41.32577896118187,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 143.75,
			"height": 42,
			"seed": 551301232,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"id": "XEQ7SWOqdv37_rV6gfav3",
					"type": "arrow"
				}
			],
			"updated": 1702746971523,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 33,
			"versionNonce": 1858219632,
			"isDeleted": false,
			"id": "Lbrkx-CdoGg4LykaL9FpL",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -433.58041381835915,
			"y": -158.67422103881847,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 109.375,
			"height": 27.083358764648438,
			"seed": 873706096,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"id": "SYiSM4WZfVUjwtMXwW-V8",
					"type": "arrow"
				}
			],
			"updated": 1702745706207,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 49,
			"versionNonce": 1143327344,
			"isDeleted": false,
			"id": "sJq9WUA-g5cABa-pMxvEz",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -401.2886962890623,
			"y": -135.7575798034669,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 140.625,
			"height": 31.250000000000114,
			"seed": 618966160,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"id": "XEQ7SWOqdv37_rV6gfav3",
					"type": "arrow"
				}
			],
			"updated": 1702746979218,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 161,
			"versionNonce": 1056418277,
			"isDeleted": false,
			"id": "f53H6Um9",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 214.3363037109384,
			"y": -474.2276583484722,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 166.7271728515625,
			"height": 75.92015483895042,
			"seed": 2111246480,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702748508268,
			"link": null,
			"locked": false,
			"fontSize": 63.26679569912535,
			"fontFamily": 4,
			"text": "컨트롤러",
			"rawText": "컨트롤러",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "컨트롤러",
			"lineHeight": 1.2,
			"baseline": 60
		},
		{
			"type": "text",
			"version": 131,
			"versionNonce": 219943659,
			"isDeleted": false,
			"id": "IOkHk4u7",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 6.280469063411055,
			"x": -607.538786928965,
			"y": -452.37856993869764,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 229.585205078125,
			"height": 68.20000000000007,
			"seed": 1621966480,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702748508269,
			"link": null,
			"locked": false,
			"fontSize": 56.83333333333339,
			"fontFamily": 4,
			"text": "Index 파일",
			"rawText": "Index 파일",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Index 파일",
			"lineHeight": 1.2,
			"baseline": 53
		},
		{
			"type": "text",
			"version": 153,
			"versionNonce": 1888691525,
			"isDeleted": false,
			"id": "aDfMA0Os",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -645.0386962890625,
			"y": 288.2008552551273,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 411.0841979980469,
			"height": 43.199999999999996,
			"seed": 122833552,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "HFw17sHKOcrAqq_Lr8TUU",
					"type": "arrow"
				}
			],
			"updated": 1702748508271,
			"link": null,
			"locked": false,
			"fontSize": 36,
			"fontFamily": 4,
			"text": "API 안에 작성해야 할 구현 코드가",
			"rawText": "API 안에 작성해야 할 구현 코드가",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "API 안에 작성해야 할 구현 코드가",
			"lineHeight": 1.2,
			"baseline": 34
		},
		{
			"type": "text",
			"version": 98,
			"versionNonce": 1905294731,
			"isDeleted": false,
			"id": "j9Kaf0N6",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 172.66973876953193,
			"y": 288.2008552551273,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 189.75607299804688,
			"height": 43.199999999999996,
			"seed": 555736208,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "HFw17sHKOcrAqq_Lr8TUU",
					"type": "arrow"
				}
			],
			"updated": 1702748508272,
			"link": null,
			"locked": false,
			"fontSize": 36,
			"fontFamily": 4,
			"text": "컨트롤러에게 감",
			"rawText": "컨트롤러에게 감",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "컨트롤러에게 감",
			"lineHeight": 1.2,
			"baseline": 34
		},
		{
			"type": "arrow",
			"version": 232,
			"versionNonce": 1220119664,
			"isDeleted": false,
			"id": "HFw17sHKOcrAqq_Lr8TUU",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -218.99697875976517,
			"y": 318.45331182735896,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 387.4998474121096,
			"height": 4.881349503368739,
			"seed": 1173674096,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702746941026,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "aDfMA0Os",
				"focus": 0.47252857348354166,
				"gap": 14.957519531250455
			},
			"endBinding": {
				"elementId": "j9Kaf0N6",
				"focus": -0.11070035838887857,
				"gap": 4.1668701171875
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					387.4998474121096,
					-4.881349503368739
				]
			]
		},
		{
			"type": "text",
			"version": 78,
			"versionNonce": 199767205,
			"isDeleted": false,
			"id": "6jI508y5",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 998.711456298829,
			"y": -477.3725068952382,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 129.38136291503906,
			"height": 77.52343844431013,
			"seed": 384394352,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702748508273,
			"link": null,
			"locked": false,
			"fontSize": 64.60286537025844,
			"fontFamily": 4,
			"text": "서비스",
			"rawText": "서비스",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "서비스",
			"lineHeight": 1.2,
			"baseline": 61
		},
		{
			"type": "text",
			"version": 190,
			"versionNonce": 1110446736,
			"isDeleted": false,
			"id": "EW3ufdkw",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 798.7114562988288,
			"y": -327.9241447448733,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 243.75,
			"height": 153.6,
			"seed": 599021200,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702746822733,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 3,
			"text": "// cash.servie.js\n\nexport class CashService {\n    checkValue = () => {\n        ...\n    };\n}\n",
			"rawText": "// cash.servie.js\n\nexport class CashService {\n    checkValue = () => {\n        ...\n    };\n}\n",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "// cash.servie.js\n\nexport class CashService {\n    checkValue = () => {\n        ...\n    };\n}\n",
			"lineHeight": 1.2,
			"baseline": 150
		},
		{
			"type": "rectangle",
			"version": 81,
			"versionNonce": 1480227952,
			"isDeleted": false,
			"id": "eUfOL9weglPOBKz0NixTx",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 777.8780212402351,
			"y": -346.1741447448733,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 288.5418701171877,
			"height": 175.00000000000023,
			"seed": 1842204816,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1702746854074,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 86,
			"versionNonce": 1951915152,
			"isDeleted": false,
			"id": "3dBZELicih1Nbo48abuN_",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 853.9195861816413,
			"y": -122.21578598022461,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 315.6250000000002,
			"height": 195.83328247070335,
			"seed": 2128538768,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1702746846466,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 97,
			"versionNonce": 1631415408,
			"isDeleted": false,
			"id": "OHiCUX9C",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 876.8364562988288,
			"y": -89.92414474487305,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 271.875,
			"height": 134.4,
			"seed": 1505157264,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702746839957,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 3,
			"text": "// product.service.js\n\nexport class ProductService {\n    checkSoldOut = () => {\n        ...\n    };\n}",
			"rawText": "// product.service.js\n\nexport class ProductService {\n    checkSoldOut = () => {\n        ...\n    };\n}",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "// product.service.js\n\nexport class ProductService {\n    checkSoldOut = () => {\n        ...\n    };\n}",
			"lineHeight": 1.2,
			"baseline": 131
		},
		{
			"type": "ellipse",
			"version": 40,
			"versionNonce": 1251727504,
			"isDeleted": false,
			"id": "X7bAnwPFu7b8qyrCG-AU0",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 825.7945861816413,
			"y": -278.4657859802247,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 114.58343505859375,
			"height": 35.41664123535156,
			"seed": 639855248,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"id": "2eH-B2juaeY_CA9niJeF5",
					"type": "arrow"
				}
			],
			"updated": 1702747100697,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 25,
			"versionNonce": 598982256,
			"isDeleted": false,
			"id": "krqECj3Fq_xJnVALXrod1",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 904.9614562988288,
			"y": -38.88242721557606,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 134.37500000000023,
			"height": 36.458282470703125,
			"seed": 193571984,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"id": "U1xdhewNDWiOtCOnxAfA4",
					"type": "arrow"
				}
			],
			"updated": 1702747965056,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 46,
			"versionNonce": 1432700048,
			"isDeleted": false,
			"id": "QQJ2gmFOX-3CIiffyehct",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 304.96145629882835,
			"y": -184.7157859802246,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 132.29171752929685,
			"height": 32.29164123535156,
			"seed": 1480509040,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"id": "2eH-B2juaeY_CA9niJeF5",
					"type": "arrow"
				}
			],
			"updated": 1702747135498,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 72,
			"versionNonce": 1709879952,
			"isDeleted": false,
			"id": "ruUcz8ydHH2sjkE29Dzgh",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 348.71145629882835,
			"y": -104.50750350952148,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 144.7917175292971,
			"height": 31.250076293945312,
			"seed": 261428336,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"id": "x09VPTqXBrKn5sf2M3gns",
					"type": "arrow"
				}
			],
			"updated": 1702747124114,
			"link": null,
			"locked": false
		},
		{
			"type": "arrow",
			"version": 111,
			"versionNonce": 693030544,
			"isDeleted": false,
			"id": "2eH-B2juaeY_CA9niJeF5",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 824.7530212402351,
			"y": -256.5907859802247,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 374.9998474121096,
			"height": 83.33335876464855,
			"seed": 1131324528,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702747135975,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "X7bAnwPFu7b8qyrCG-AU0",
				"focus": 0.4033142900681775,
				"gap": 2.20165762757879
			},
			"endBinding": {
				"elementId": "QQJ2gmFOX-3CIiffyehct",
				"focus": 0.5857398088637972,
				"gap": 13.152383961724865
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-374.9998474121096,
					83.33335876464855
				]
			]
		},
		{
			"type": "arrow",
			"version": 75,
			"versionNonce": 1224392848,
			"isDeleted": false,
			"id": "x09VPTqXBrKn5sf2M3gns",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 907.0445861816413,
			"y": -21.174144744872933,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 405.1881273604279,
			"height": 71.87500000000011,
			"seed": 730089584,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702747127051,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "ruUcz8ydHH2sjkE29Dzgh",
				"focus": -0.9142291405204979,
				"gap": 9.066102534204902
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-405.1881273604279,
					-71.87500000000011
				]
			]
		},
		{
			"type": "ellipse",
			"version": 52,
			"versionNonce": 515716720,
			"isDeleted": false,
			"id": "qpxFzkbUoapcOIsG7sdpq",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 119.23548126220714,
			"y": -261.8367245627312,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 184.375,
			"height": 35.416641235351555,
			"seed": 625297008,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"id": "uhJW48strgzEdC4P8G2Tc",
					"type": "arrow"
				}
			],
			"updated": 1702747547526,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 39,
			"versionNonce": 593011312,
			"isDeleted": false,
			"id": "qosTut_UONiKTMsdElGmB",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 917.1520462036134,
			"y": -299.3367245627312,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 117.70843505859364,
			"height": 32.29164123535156,
			"seed": 1624108656,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"id": "BiEHCI4cbYa0LRUfX5AT7",
					"type": "arrow"
				}
			],
			"updated": 1702747615342,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 29,
			"versionNonce": 517045392,
			"isDeleted": false,
			"id": "bLOVCv71tDChD-lq8Jnc9",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 992.1520462036134,
			"y": -59.75336579808277,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 151.04156494140614,
			"height": 29.166641235351562,
			"seed": 516856432,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"id": "z82Uzb82OfgpZh6nyRD_Z",
					"type": "arrow"
				},
				{
					"id": "mHan8UOJ8IPKaebr8t8w2",
					"type": "arrow"
				}
			],
			"updated": 1702747951667,
			"link": null,
			"locked": false
		},
		{
			"type": "arrow",
			"version": 388,
			"versionNonce": 1673021584,
			"isDeleted": false,
			"id": "uhJW48strgzEdC4P8G2Tc",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 145.2770462036134,
			"y": -260.79500703343433,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 621.875,
			"height": 70.83328247070312,
			"seed": 1052110992,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702747596006,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "qpxFzkbUoapcOIsG7sdpq",
				"focus": 1.0626367455182537,
				"gap": 4.251588722966421
			},
			"endBinding": {
				"elementId": "c9usJRp88VjAUWaz5fDAJ",
				"focus": -1.1774006574980578,
				"gap": 8.33939528687869
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-191.66656494140636,
					7.291603088378906
				],
				[
					-621.875,
					70.83328247070312
				]
			]
		},
		{
			"type": "ellipse",
			"version": 35,
			"versionNonce": 600307344,
			"isDeleted": false,
			"id": "c9usJRp88VjAUWaz5fDAJ",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -565.139518737793,
			"y": -181.62840394505542,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 182.29171752929688,
			"height": 30.208358764648438,
			"seed": 769022576,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"id": "uhJW48strgzEdC4P8G2Tc",
					"type": "arrow"
				}
			],
			"updated": 1702747585078,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 42,
			"versionNonce": 998688368,
			"isDeleted": false,
			"id": "jnuh6gpA1qKf4LTP8pQdp",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 260.9021987915039,
			"y": -209.75340394505542,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 123.9581298828125,
			"height": 33.33335876464844,
			"seed": 1706081904,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"id": "BiEHCI4cbYa0LRUfX5AT7",
					"type": "arrow"
				}
			],
			"updated": 1702747615342,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 34,
			"versionNonce": 913525392,
			"isDeleted": false,
			"id": "fiQMa7icI_woLZCP5gK4p",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 286.94376373291016,
			"y": -134.75340394505542,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 151.04156494140625,
			"height": 36.45835876464844,
			"seed": 391528560,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"id": "z82Uzb82OfgpZh6nyRD_Z",
					"type": "arrow"
				}
			],
			"updated": 1702747624686,
			"link": null,
			"locked": false
		},
		{
			"type": "arrow",
			"version": 107,
			"versionNonce": 1877494928,
			"isDeleted": false,
			"id": "BiEHCI4cbYa0LRUfX5AT7",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 930.6936111450195,
			"y": -297.2533276511101,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 578.1248474121094,
			"height": 87.5,
			"seed": 1720411280,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702747617846,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "qosTut_UONiKTMsdElGmB",
				"focus": 0.9578478130046788,
				"gap": 3.578490854692742
			},
			"endBinding": {
				"elementId": "jnuh6gpA1qKf4LTP8pQdp",
				"focus": -0.4650036782665453,
				"gap": 2.014968404706302
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-217.7081298828125,
					7.2916412353515625
				],
				[
					-578.1248474121094,
					87.5
				]
			]
		},
		{
			"type": "arrow",
			"version": 55,
			"versionNonce": 1831689360,
			"isDeleted": false,
			"id": "z82Uzb82OfgpZh6nyRD_Z",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 995.2770462036133,
			"y": -56.62832765111011,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 566.6665649414062,
			"height": 70.83335876464844,
			"seed": 1406301808,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702747624686,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "bLOVCv71tDChD-lq8Jnc9",
				"focus": 0.1386596370434118,
				"gap": 6.435790768531284
			},
			"endBinding": {
				"elementId": "fiQMa7icI_woLZCP5gK4p",
				"focus": -0.9355640285261522,
				"gap": 1.9684109328998431
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-566.6665649414062,
					-70.83335876464844
				]
			]
		},
		{
			"type": "text",
			"version": 115,
			"versionNonce": 761173035,
			"isDeleted": false,
			"id": "4k46bYqp",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 75.48548126220703,
			"y": 396.49651976099926,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 422.85614013671875,
			"height": 43.199999999999996,
			"seed": 731630736,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702748508277,
			"link": null,
			"locked": false,
			"fontSize": 36,
			"fontFamily": 4,
			"text": "여러 번 사용할 만한 비즈니스 로직은",
			"rawText": "여러 번 사용할 만한 비즈니스 로직은",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "여러 번 사용할 만한 비즈니스 로직은",
			"lineHeight": 1.2,
			"baseline": 34
		},
		{
			"type": "text",
			"version": 149,
			"versionNonce": 1285838853,
			"isDeleted": false,
			"id": "ULe3jz6L",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 829.6520462036133,
			"y": 395.454954819593,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 431.06414794921875,
			"height": 43.199999999999996,
			"seed": 136265872,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702748508278,
			"link": null,
			"locked": false,
			"fontSize": 36,
			"fontFamily": 4,
			"text": "서비스에서 단위별로 구현하여 사용함",
			"rawText": "서비스에서 단위별로 구현하여 사용함",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "서비스에서 단위별로 구현하여 사용함",
			"lineHeight": 1.2,
			"baseline": 34
		},
		{
			"type": "arrow",
			"version": 39,
			"versionNonce": 1518765712,
			"isDeleted": false,
			"id": "5NuX7FBfkgoMTkr1MY4w8",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 515.0687637329102,
			"y": 424.6216723488899,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 295.8332824707031,
			"height": 3.125,
			"seed": 1722957424,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702747794661,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					295.8332824707031,
					-3.125
				]
			]
		},
		{
			"type": "ellipse",
			"version": 75,
			"versionNonce": 1019929200,
			"isDeleted": false,
			"id": "rnp0wP6f7XRx4h-Gb7fSF",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 353.61063385009766,
			"y": 105.87167234888989,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 136.45843505859375,
			"height": 26.04171752929687,
			"seed": 845039728,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"id": "U1xdhewNDWiOtCOnxAfA4",
					"type": "arrow"
				}
			],
			"updated": 1702747965057,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 70,
			"versionNonce": 1810339984,
			"isDeleted": false,
			"id": "DXHfsmPROEqBDcAXpRZrA",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 297.36048126220703,
			"y": 80.87167234888989,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 156.25,
			"height": 31.25,
			"seed": 1227405968,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"id": "mHan8UOJ8IPKaebr8t8w2",
					"type": "arrow"
				}
			],
			"updated": 1702747951667,
			"link": null,
			"locked": false
		},
		{
			"type": "arrow",
			"version": 359,
			"versionNonce": 1395635824,
			"isDeleted": false,
			"id": "mHan8UOJ8IPKaebr8t8w2",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1146.3186111450195,
			"y": -41.00332765111011,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 688.5415649414062,
			"height": 134.375,
			"seed": 1819815024,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702748006402,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "bLOVCv71tDChD-lq8Jnc9",
				"focus": -1.0784467929151333,
				"gap": 4.394262773865691
			},
			"endBinding": {
				"elementId": "DXHfsmPROEqBDcAXpRZrA",
				"focus": 0.2392521283163058,
				"gap": 4.798037331365691
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-93.75,
					82.29164123535156
				],
				[
					-688.5415649414062,
					134.375
				]
			]
		},
		{
			"type": "arrow",
			"version": 244,
			"versionNonce": 1570825328,
			"isDeleted": false,
			"id": "U1xdhewNDWiOtCOnxAfA4",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 903.6101760864258,
			"y": -12.8782513571648,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 405.2081298828125,
			"height": 134.375,
			"seed": 1599735952,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702747993068,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "krqECj3Fq_xJnVALXrod1",
				"focus": 0.5400520535111011,
				"gap": 4.742768588224784
			},
			"endBinding": {
				"elementId": "rnp0wP6f7XRx4h-Gb7fSF",
				"focus": 1.0656715737894438,
				"gap": 8.64108577727373
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-186.45828247070312,
					64.58328247070312
				],
				[
					-405.2081298828125,
					134.375
				]
			]
		}
	],
	"appState": {
		"theme": "dark",
		"viewBackgroundColor": "#ffffff",
		"currentItemStrokeColor": "#e03131",
		"currentItemBackgroundColor": "transparent",
		"currentItemFillStyle": "solid",
		"currentItemStrokeWidth": 4,
		"currentItemStrokeStyle": "solid",
		"currentItemRoughness": 2,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 4,
		"currentItemFontSize": 36,
		"currentItemTextAlign": "left",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": 1077.9585609436035,
		"scrollY": 903.0083514075212,
		"zoom": {
			"value": 0.35000000000000003
		},
		"currentItemRoundness": "round",
		"gridSize": null,
		"gridColor": {
			"Bold": "#C9C9C9FF",
			"Regular": "#EDEDEDFF"
		},
		"currentStrokeOptions": null,
		"previousGridSize": null,
		"frameRendering": {
			"enabled": true,
			"clip": true,
			"name": true,
			"outline": true
		}
	},
	"files": {}
}
```
%%