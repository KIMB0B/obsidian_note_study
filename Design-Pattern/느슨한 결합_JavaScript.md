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

// DI 추가 부분
const cashService = new CashService()
const productService = new ProductService()

// 상품 API
const productController = new ProductController(cashService, productService)
app.post("/products/buy", productController.buyProduct) // 상품 구매하기
app.post("/products/refund", productController.refundProduct) // 상품 환불하기


app.listen(3000, () => {
    console.log("백엔드 API 서버거 켜졌어요!!!")
}) ^3sWOLDWX

// product.controller.js

import { CashService } from "./services/cash.service.js";
import { ProductService } from "./services/product.service.js";

export class ProductController {
  // DI 추가 부분
  constructor(paymentService, productService) {
    this.paymentService = paymentService;
    this.productService = productService;
  } 

  buyProduct = (req, res) => {
    // 1. 가진돈 검증하는 코드
    const hasMoney = this.paymentService.checkValue();

    // 2. 판매여부 검증하는 코드
    const isSoldout = this.productService.checkSoldout();
    
    // 3. 상품 구매하는 코드
    if (hasMoney && !isSoldout) {
      res.send("상품 구매 완료!!");
    }
  };

  refundProduct = (req, res) => {
    // 1. 판매여부 검증하는 코드 
    const isSoldout = this.productService.checkSoldout();
    // 2. 상품 환불하는 코드
    if (isSoldout) {
      res.send("상품 환불 완료!!");
    }
  };
} ^NMl9nw6S

컨트롤러 ^f53H6Um9

Index 파일 ^IOkHk4u7

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

1. 서비스가 컨트롤러가 아닌 index에서 한번에 new된다. ^3omDPfx9

2. 컨트롤러의 생성자를 통해 서비스가 
   들어가게 되어 느슨한 결합이 된다. ^1Tk8SNTQ

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
			"version": 122,
			"versionNonce": 641166110,
			"isDeleted": false,
			"id": "UY5kuuc66fKixc3JYS_H5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -870.0387725830085,
			"y": -354.358610425677,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 763.5416412353522,
			"height": 454.166641235352,
			"seed": 1634147472,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1702828401751,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 213,
			"versionNonce": 251371970,
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
			"height": 682.2916412353521,
			"seed": 932706448,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1702828397151,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 493,
			"versionNonce": 693752670,
			"isDeleted": false,
			"id": "3sWOLDWX",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -835.2280273437503,
			"y": -326.5237564086916,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 712.5,
			"height": 384,
			"seed": 429053040,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702828397151,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 3,
			"text": "// index.js\n\nimport express from 'express'\nimport { ProductController } from './mvc/controllers/product.controller.js'\n\nconst app = express()\n\n// DI 추가 부분\nconst cashService = new CashService()\nconst productService = new ProductService()\n\n// 상품 API\nconst productController = new ProductController(cashService, productService)\napp.post(\"/products/buy\", productController.buyProduct) // 상품 구매하기\napp.post(\"/products/refund\", productController.refundProduct) // 상품 환불하기\n\n\napp.listen(3000, () => {\n    console.log(\"백엔드 API 서버거 켜졌어요!!!\")\n})",
			"rawText": "// index.js\n\nimport express from 'express'\nimport { ProductController } from './mvc/controllers/product.controller.js'\n\nconst app = express()\n\n// DI 추가 부분\nconst cashService = new CashService()\nconst productService = new ProductService()\n\n// 상품 API\nconst productController = new ProductController(cashService, productService)\napp.post(\"/products/buy\", productController.buyProduct) // 상품 구매하기\napp.post(\"/products/refund\", productController.refundProduct) // 상품 환불하기\n\n\napp.listen(3000, () => {\n    console.log(\"백엔드 API 서버거 켜졌어요!!!\")\n})",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "// index.js\n\nimport express from 'express'\nimport { ProductController } from './mvc/controllers/product.controller.js'\n\nconst app = express()\n\n// DI 추가 부분\nconst cashService = new CashService()\nconst productService = new ProductService()\n\n// 상품 API\nconst productController = new ProductController(cashService, productService)\napp.post(\"/products/buy\", productController.buyProduct) // 상품 구매하기\napp.post(\"/products/refund\", productController.refundProduct) // 상품 환불하기\n\n\napp.listen(3000, () => {\n    console.log(\"백엔드 API 서버거 켜졌어요!!!\")\n})",
			"lineHeight": 1.2,
			"baseline": 380
		},
		{
			"type": "text",
			"version": 407,
			"versionNonce": 275126658,
			"isDeleted": false,
			"id": "NMl9nw6S",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 7.4597778320314205,
			"y": -353.83213043212925,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 590.625,
			"height": 652.8,
			"seed": 1880622224,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702828397151,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 3,
			"text": "// product.controller.js\n\nimport { CashService } from \"./services/cash.service.js\";\nimport { ProductService } from \"./services/product.service.js\";\n\nexport class ProductController {\n  // DI 추가 부분\n  constructor(paymentService, productService) {\n    this.paymentService = paymentService;\n    this.productService = productService;\n  } \n\n  buyProduct = (req, res) => {\n    // 1. 가진돈 검증하는 코드\n    const hasMoney = this.paymentService.checkValue();\n\n    // 2. 판매여부 검증하는 코드\n    const isSoldout = this.productService.checkSoldout();\n    \n    // 3. 상품 구매하는 코드\n    if (hasMoney && !isSoldout) {\n      res.send(\"상품 구매 완료!!\");\n    }\n  };\n\n  refundProduct = (req, res) => {\n    // 1. 판매여부 검증하는 코드 \n    const isSoldout = this.productService.checkSoldout();\n    // 2. 상품 환불하는 코드\n    if (isSoldout) {\n      res.send(\"상품 환불 완료!!\");\n    }\n  };\n}",
			"rawText": "// product.controller.js\n\nimport { CashService } from \"./services/cash.service.js\";\nimport { ProductService } from \"./services/product.service.js\";\n\nexport class ProductController {\n  // DI 추가 부분\n  constructor(paymentService, productService) {\n    this.paymentService = paymentService;\n    this.productService = productService;\n  } \n\n  buyProduct = (req, res) => {\n    // 1. 가진돈 검증하는 코드\n    const hasMoney = this.paymentService.checkValue();\n\n    // 2. 판매여부 검증하는 코드\n    const isSoldout = this.productService.checkSoldout();\n    \n    // 3. 상품 구매하는 코드\n    if (hasMoney && !isSoldout) {\n      res.send(\"상품 구매 완료!!\");\n    }\n  };\n\n  refundProduct = (req, res) => {\n    // 1. 판매여부 검증하는 코드 \n    const isSoldout = this.productService.checkSoldout();\n    // 2. 상품 환불하는 코드\n    if (isSoldout) {\n      res.send(\"상품 환불 완료!!\");\n    }\n  };\n}",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "// product.controller.js\n\nimport { CashService } from \"./services/cash.service.js\";\nimport { ProductService } from \"./services/product.service.js\";\n\nexport class ProductController {\n  // DI 추가 부분\n  constructor(paymentService, productService) {\n    this.paymentService = paymentService;\n    this.productService = productService;\n  } \n\n  buyProduct = (req, res) => {\n    // 1. 가진돈 검증하는 코드\n    const hasMoney = this.paymentService.checkValue();\n\n    // 2. 판매여부 검증하는 코드\n    const isSoldout = this.productService.checkSoldout();\n    \n    // 3. 상품 구매하는 코드\n    if (hasMoney && !isSoldout) {\n      res.send(\"상품 구매 완료!!\");\n    }\n  };\n\n  refundProduct = (req, res) => {\n    // 1. 판매여부 검증하는 코드 \n    const isSoldout = this.productService.checkSoldout();\n    // 2. 상품 환불하는 코드\n    if (isSoldout) {\n      res.send(\"상품 환불 완료!!\");\n    }\n  };\n}",
			"lineHeight": 1.2,
			"baseline": 649
		},
		{
			"type": "text",
			"version": 163,
			"versionNonce": 600029086,
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
			"updated": 1702828397151,
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
			"version": 133,
			"versionNonce": 892049730,
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
			"updated": 1702828397151,
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
			"version": 110,
			"versionNonce": 937890782,
			"isDeleted": false,
			"id": "6jI508y5",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 874.6375630696623,
			"y": -466.26139578412705,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 129.38136291503906,
			"height": 77.52343844431013,
			"seed": 384394352,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702828397152,
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
			"version": 192,
			"versionNonce": 1823154434,
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
			"updated": 1702828397152,
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
			"version": 84,
			"versionNonce": 1607788574,
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
			"boundElements": [
				{
					"id": "Di8RlQb5ddq5BjgV5pntU",
					"type": "arrow"
				}
			],
			"updated": 1702828397152,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 88,
			"versionNonce": 1650700482,
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
			"updated": 1702828397152,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 99,
			"versionNonce": 729691230,
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
			"updated": 1702828397152,
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
			"type": "line",
			"version": 90,
			"versionNonce": 2046052482,
			"isDeleted": false,
			"id": "K7gROK91slv40ip9cmaeZ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 860.914708273752,
			"y": 72.37578058521262,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 88.09535435267867,
			"height": 154.76187569754484,
			"seed": 413863618,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702828397152,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-88.09535435267867,
					154.76187569754484
				]
			]
		},
		{
			"type": "arrow",
			"version": 474,
			"versionNonce": 78903454,
			"isDeleted": false,
			"id": "Di8RlQb5ddq5BjgV5pntU",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 795.438634055002,
			"y": -164.52895225518944,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 1205.952322823662,
			"height": 589.2857142857148,
			"seed": 1726031042,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702828397152,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "eUfOL9weglPOBKz0NixTx",
				"focus": 0.7249807516330025,
				"gap": 6.645192489683609
			},
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
					-66.66678292410711,
					475.00000000000057
				],
				[
					-472.6191057477681,
					589.2857142857148
				],
				[
					-877.3810686383936,
					441.6666957310273
				],
				[
					-864.2858886718761,
					30.952410016741084
				],
				[
					-1205.952322823662,
					9.523838588169752
				]
			]
		},
		{
			"type": "ellipse",
			"version": 45,
			"versionNonce": 1260120130,
			"isDeleted": false,
			"id": "ZZjRwo2nsXKcHVWoXaiiJ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -618.8470802307137,
			"y": -185.95752368376088,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 210.714285714286,
			"height": 63.09517996651789,
			"seed": 2037981826,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702828397152,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 73,
			"versionNonce": 1707884482,
			"isDeleted": false,
			"id": "yCSH9kRZWSWzUjcrTd382",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 19.246399470737174,
			"y": -219.83816434945084,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 442.361043294271,
			"height": 87.5,
			"seed": 242687262,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "94rLyDrUHvQvVCyYXC-FV",
					"type": "arrow"
				}
			],
			"updated": 1702828397152,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 102,
			"versionNonce": 1542067550,
			"isDeleted": false,
			"id": "EH5UXR_dvfwkbOq8-5r-g",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -594.6424555097319,
			"y": -101.78259183968515,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 479.8610432942712,
			"height": 27.777760823567746,
			"seed": 239687938,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "94rLyDrUHvQvVCyYXC-FV",
					"type": "arrow"
				}
			],
			"updated": 1702828397152,
			"link": null,
			"locked": false
		},
		{
			"type": "arrow",
			"version": 92,
			"versionNonce": 1064499074,
			"isDeleted": false,
			"id": "94rLyDrUHvQvVCyYXC-FV",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -111.3091221763982,
			"y": -97.61592517301835,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 127.7777099609375,
			"height": 297.8186011261854,
			"seed": 1562058498,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702828397152,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "EH5UXR_dvfwkbOq8-5r-g",
				"focus": 0.9978604435689044,
				"gap": 3.4722900390625
			},
			"endBinding": {
				"elementId": "yCSH9kRZWSWzUjcrTd382",
				"focus": -0.9513319361815926,
				"gap": 2.7778116861978788
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
					50.3361683800116,
					-297.8186011261854
				],
				[
					127.7777099609375,
					-75.69442749023438
				]
			]
		},
		{
			"type": "text",
			"version": 170,
			"versionNonce": 1593555358,
			"isDeleted": false,
			"id": "3omDPfx9",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 8.81876373291027,
			"y": 464.9820386422025,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 675.936279296875,
			"height": 43.199999999999996,
			"seed": 115339330,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702828397152,
			"link": null,
			"locked": false,
			"fontSize": 36,
			"fontFamily": 4,
			"text": "1. 서비스가 컨트롤러가 아닌 index에서 한번에 new된다.",
			"rawText": "1. 서비스가 컨트롤러가 아닌 index에서 한번에 new된다.",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1. 서비스가 컨트롤러가 아닌 index에서 한번에 new된다.",
			"lineHeight": 1.2,
			"baseline": 34
		},
		{
			"type": "text",
			"version": 312,
			"versionNonce": 1793898306,
			"isDeleted": false,
			"id": "1Tk8SNTQ",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -291.18123626708973,
			"y": -493.351205681528,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 442.98016357421875,
			"height": 86.39999999999999,
			"seed": 1032484318,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702828397152,
			"link": null,
			"locked": false,
			"fontSize": 36,
			"fontFamily": 4,
			"text": "2. 컨트롤러의 생성자를 통해 서비스가 \n   들어가게 되어 느슨한 결합이 된다.",
			"rawText": "2. 컨트롤러의 생성자를 통해 서비스가 \n   들어가게 되어 느슨한 결합이 된다.",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "2. 컨트롤러의 생성자를 통해 서비스가 \n   들어가게 되어 느슨한 결합이 된다.",
			"lineHeight": 1.2,
			"baseline": 77
		},
		{
			"id": "P-apE6BP6X94XVY1j13-U",
			"type": "rectangle",
			"x": -322.9521713256835,
			"y": -511.6438028800143,
			"width": 492.70843505859375,
			"height": 115.625,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"seed": 455222338,
			"version": 45,
			"versionNonce": 1768720706,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702828430734,
			"link": null,
			"locked": false
		},
		{
			"id": "rUI3TXq2Qi2XNwXH85KR7",
			"type": "rectangle",
			"x": -21.910453796386605,
			"y": 450.85615897301307,
			"width": 727.0832824707031,
			"height": 71.875,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"seed": 1263407362,
			"version": 38,
			"versionNonce": 238004162,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702828437871,
			"link": null,
			"locked": false
		}
	],
	"appState": {
		"theme": "dark",
		"viewBackgroundColor": "#ffffff",
		"currentItemStrokeColor": "#1971c2",
		"currentItemBackgroundColor": "transparent",
		"currentItemFillStyle": "solid",
		"currentItemStrokeWidth": 2,
		"currentItemStrokeStyle": "solid",
		"currentItemRoughness": 2,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 4,
		"currentItemFontSize": 36,
		"currentItemTextAlign": "left",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": 1017.7600631713866,
		"scrollY": 766.2336466300143,
		"zoom": {
			"value": 0.4
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