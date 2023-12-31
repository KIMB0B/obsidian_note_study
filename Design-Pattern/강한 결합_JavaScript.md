---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
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

new를 통해 각각 선언함 ^Y1wl7cPX

만약 ProductService()를 다른 서비스로 바꾸려 한다면?
 - 컨트롤러에 ProductService를 쓴 곳을 하나하나 다 찾아야 함 ^bvzXsHKW

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
			"version": 250,
			"versionNonce": 61814942,
			"isDeleted": false,
			"id": "NUB9Hyzgvtg6kSog-eWrE",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -416.91354370117165,
			"y": -363.8823890686038,
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
			"updated": 1702826756208,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 264,
			"versionNonce": 1891267806,
			"isDeleted": false,
			"id": "NMl9nw6S",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -406.08178710937483,
			"y": -345.49880981445347,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 590.625,
			"height": 595.1999999999999,
			"seed": 1880622224,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702826756208,
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
			"type": "text",
			"version": 226,
			"versionNonce": 166033218,
			"isDeleted": false,
			"id": "f53H6Um9",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -199.20526123046784,
			"y": -466.93597896614796,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 166.7271728515625,
			"height": 75.92015483895042,
			"seed": 2111246480,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702826756209,
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
			"version": 143,
			"versionNonce": 553694814,
			"isDeleted": false,
			"id": "6jI508y5",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 585.1698913574228,
			"y": -470.08082751291397,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 129.38136291503906,
			"height": 77.52343844431013,
			"seed": 384394352,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702826756209,
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
			"version": 255,
			"versionNonce": 1968367234,
			"isDeleted": false,
			"id": "EW3ufdkw",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 385.16989135742256,
			"y": -320.63246536254906,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 243.75,
			"height": 153.6,
			"seed": 599021200,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702826756209,
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
			"version": 146,
			"versionNonce": 1788230302,
			"isDeleted": false,
			"id": "eUfOL9weglPOBKz0NixTx",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 364.3364562988288,
			"y": -338.88246536254906,
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
			"updated": 1702826756209,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 151,
			"versionNonce": 1559676482,
			"isDeleted": false,
			"id": "3dBZELicih1Nbo48abuN_",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 440.37802124023506,
			"y": -114.92410659790039,
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
			"updated": 1702826756209,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 162,
			"versionNonce": 661731038,
			"isDeleted": false,
			"id": "OHiCUX9C",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 463.29489135742256,
			"y": -82.63246536254883,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 271.875,
			"height": 134.4,
			"seed": 1505157264,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702826756209,
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
			"version": 104,
			"versionNonce": 1997002718,
			"isDeleted": false,
			"id": "qosTut_UONiKTMsdElGmB",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 503.61048126220714,
			"y": -292.045045180407,
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
			"updated": 1702826756210,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 94,
			"versionNonce": 1072209154,
			"isDeleted": false,
			"id": "bLOVCv71tDChD-lq8Jnc9",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 578.6104812622071,
			"y": -52.46168641575855,
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
			"updated": 1702826756210,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 107,
			"versionNonce": 1681782878,
			"isDeleted": false,
			"id": "jnuh6gpA1qKf4LTP8pQdp",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -152.63936614990234,
			"y": -202.4617245627312,
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
			"updated": 1702826756210,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 99,
			"versionNonce": 16958594,
			"isDeleted": false,
			"id": "fiQMa7icI_woLZCP5gK4p",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -126.5978012084961,
			"y": -127.4617245627312,
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
			"updated": 1702826756210,
			"link": null,
			"locked": false
		},
		{
			"type": "arrow",
			"version": 302,
			"versionNonce": 417021086,
			"isDeleted": false,
			"id": "BiEHCI4cbYa0LRUfX5AT7",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 517.1520462036133,
			"y": -289.9616482687859,
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
			"updated": 1702826756210,
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
			"version": 250,
			"versionNonce": 1660609602,
			"isDeleted": false,
			"id": "z82Uzb82OfgpZh6nyRD_Z",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 581.735481262207,
			"y": -49.33664826878589,
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
			"updated": 1702826756210,
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
			"type": "ellipse",
			"version": 135,
			"versionNonce": 614979934,
			"isDeleted": false,
			"id": "DXHfsmPROEqBDcAXpRZrA",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -116.18108367919922,
			"y": 88.1633517312141,
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
			"updated": 1702826756210,
			"link": null,
			"locked": false
		},
		{
			"type": "arrow",
			"version": 752,
			"versionNonce": 1029927810,
			"isDeleted": false,
			"id": "mHan8UOJ8IPKaebr8t8w2",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 724.4436388882723,
			"y": -27.651079199183634,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 680.2081576260653,
			"height": 137.5947085293858,
			"seed": 1819815024,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702826756210,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "bLOVCv71tDChD-lq8Jnc9",
				"focus": -1.0097217400149654,
				"gap": 4.469666254351651
			},
			"endBinding": {
				"elementId": "DXHfsmPROEqBDcAXpRZrA",
				"focus": -0.28162639016235147,
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
					-87.68943093039775,
					137.5947085293858
				],
				[
					-680.2081576260653,
					128.31443093039775
				]
			]
		},
		{
			"type": "ellipse",
			"version": 35,
			"versionNonce": 1299034946,
			"isDeleted": false,
			"id": "W8BM05md3U0ECQl_uYDB8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -192.906903006814,
			"y": -203.45682901633836,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 53.03022904829538,
			"height": 40.90909090909088,
			"seed": 1138850334,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"id": "T2DYcHvSPYgI3PSnNsdFg",
					"type": "arrow"
				}
			],
			"updated": 1702826756210,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 21,
			"versionNonce": 1340840414,
			"isDeleted": false,
			"id": "JvszD29tIIRZbyIlbSkp5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -161.84633393721174,
			"y": -122.39620446023036,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 43.93943093039775,
			"height": 33.333296342329504,
			"seed": 1687260766,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"id": "7lvCj9sxO8h43EUkRWYHZ",
					"type": "arrow"
				}
			],
			"updated": 1702826756210,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 34,
			"versionNonce": 697957122,
			"isDeleted": false,
			"id": "svDe-u7Z85NjvJDLlf4hZ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -170.1796302795413,
			"y": 88.9674319034059,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 56.81818181818181,
			"height": 34.09090909090912,
			"seed": 1783203614,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"id": "DG4nY4BasfgtUy18jO1Ru",
					"type": "arrow"
				}
			],
			"updated": 1702826756210,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 397,
			"versionNonce": 1364766238,
			"isDeleted": false,
			"id": "Y1wl7cPX",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -247.45246852528004,
			"y": -538.3052398828155,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 283.5001220703125,
			"height": 43.199999999999996,
			"seed": 807074242,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "T2DYcHvSPYgI3PSnNsdFg",
					"type": "arrow"
				},
				{
					"id": "7lvCj9sxO8h43EUkRWYHZ",
					"type": "arrow"
				}
			],
			"updated": 1702826756211,
			"link": null,
			"locked": false,
			"fontSize": 36,
			"fontFamily": 4,
			"text": "new를 통해 각각 선언함",
			"rawText": "new를 통해 각각 선언함",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "new를 통해 각각 선언함",
			"lineHeight": 1.2,
			"baseline": 34
		},
		{
			"type": "rectangle",
			"version": 229,
			"versionNonce": 275204802,
			"isDeleted": false,
			"id": "Q5Z_eFzPmzh4yKSzGuHcO",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -266.3917884826664,
			"y": -548.1537339790514,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 316.6665926846591,
			"height": 68.93931995738637,
			"seed": 1790398082,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "7lvCj9sxO8h43EUkRWYHZ",
					"type": "arrow"
				},
				{
					"id": "DG4nY4BasfgtUy18jO1Ru",
					"type": "arrow"
				}
			],
			"updated": 1702826756211,
			"link": null,
			"locked": false
		},
		{
			"type": "arrow",
			"version": 58,
			"versionNonce": 77150814,
			"isDeleted": false,
			"id": "T2DYcHvSPYgI3PSnNsdFg",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -188.3614484613595,
			"y": -200.42654448153723,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 45.45454545454544,
			"height": 279.54542680220163,
			"seed": 1796131138,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702826756211,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "W8BM05md3U0ECQl_uYDB8",
				"focus": -0.7161067513354449,
				"gap": 4.321025290682524
			},
			"endBinding": {
				"elementId": "Y1wl7cPX",
				"focus": 0.9230648032541166,
				"gap": 15.133268599076615
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
					-45.45454545454544,
					-279.54542680220163
				]
			]
		},
		{
			"type": "arrow",
			"version": 449,
			"versionNonce": 410296962,
			"isDeleted": false,
			"id": "7lvCj9sxO8h43EUkRWYHZ",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -163.3614484613595,
			"y": -108.00228356179286,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 126.51522549715912,
			"height": 372.4242331764915,
			"seed": 1918030430,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702826756211,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "JvszD29tIIRZbyIlbSkp5",
				"focus": -0.8385268765673577,
				"gap": 1.6959336947982209
			},
			"endBinding": {
				"elementId": "Y1wl7cPX",
				"focus": 1.0012855613017244,
				"gap": 14.67872314453112
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
					-126.51522549715912,
					-155.75755726207382
				],
				[
					-93.18192915482956,
					-372.4242331764915
				]
			]
		},
		{
			"type": "arrow",
			"version": 294,
			"versionNonce": 1350450846,
			"isDeleted": false,
			"id": "DG4nY4BasfgtUy18jO1Ru",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -173.21008127385937,
			"y": 105.17953462002492,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 199.99988902698863,
			"height": 601.5151422674005,
			"seed": 132573634,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702826756211,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "svDe-u7Z85NjvJDLlf4hZ",
				"focus": -0.8580498671985011,
				"gap": 3.0566038316777124
			},
			"endBinding": {
				"elementId": "Q5Z_eFzPmzh4yKSzGuHcO",
				"focus": 0.7436930790988809,
				"gap": 3.7879527698862034
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
					-124.2423872514205,
					-100
				],
				[
					-199.99988902698863,
					-315.9090909090909
				],
				[
					-169.696932705966,
					-531.060596812855
				],
				[
					-96.96965997869324,
					-601.5151422674005
				]
			]
		},
		{
			"type": "text",
			"version": 383,
			"versionNonce": 518404958,
			"isDeleted": false,
			"id": "bvzXsHKW",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 236.63855153864006,
			"y": 154.42192187144565,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 775.26025390625,
			"height": 86.39999999999999,
			"seed": 1116591618,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702826770364,
			"link": null,
			"locked": false,
			"fontSize": 36,
			"fontFamily": 4,
			"text": "만약 ProductService()를 다른 서비스로 바꾸려 한다면?\n - 컨트롤러에 ProductService를 쓴 곳을 하나하나 다 찾아야 함",
			"rawText": "만약 ProductService()를 다른 서비스로 바꾸려 한다면?\n - 컨트롤러에 ProductService를 쓴 곳을 하나하나 다 찾아야 함",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "만약 ProductService()를 다른 서비스로 바꾸려 한다면?\n - 컨트롤러에 ProductService를 쓴 곳을 하나하나 다 찾아야 함",
			"lineHeight": 1.2,
			"baseline": 77
		},
		{
			"type": "rectangle",
			"version": 143,
			"versionNonce": 2072190878,
			"isDeleted": false,
			"id": "ixzIIj5KiwpH8z82vpC-j",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 207.09298602017418,
			"y": 148.36129731533777,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 824.9999999999999,
			"height": 112.12124911221588,
			"seed": 563677058,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1702826770364,
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
		"scrollX": 484.64111380143646,
		"scrollY": 662.9299242150707,
		"zoom": {
			"value": 0.6000000000000001
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