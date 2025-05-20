---

excalidraw-plugin: parsed

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
TE [ x:=1; if x = 0 then x:=x+1 else x:=x-1 ] = 
TE [ x:=1 ] : TE [ if x = 0 then x:=x+1 else x:=x-1 ] =
PUSH-1 : STORE-x : TE [ if x = 0 then x:=x+1 else x:=x-1 ] =
PUSH-1 : STORE-x : TB [ x = 0 ] : BRANCH( TE [ x:=x+1 ], TE [ x:=x-1 ] ) =  ^qic3eNdp

Preklad ^5kWjcgoA

PUSH-1 : STORE-x : FETCH-x : PUSH-0 : EQ : BRANCH( FETCH-x : PUSH-1 : ADD : STORE-x , FETCH-x : PUSH-1 : SUB : STORE-x ) =
c ^CJ8Xof9v

Vykonanie ^37RDLI5b

<PUSH-1 : ... ,[ ],[ ]> =>>
<STORE-x: ... ,[ 1 ],[ ]> =>>
<FETCH-x: ... ,[ ],[ x |-> 1 ]> =>>
<PUSH-0: ... ,[ 1 ],[ x |-> 1 ]> =>>
<EQ: ... ,[ 0 , 1 ],[ x |-> 1 ]> =>>
<BRANCH ( ... , FETCH-x : PUSH-1 : SUB : STORE-x ) ,[ false ],[ x |-> 1 ]> =>>
<FETCH-x : PUSH-1 : SUB : STORE-x ,[  ],[ x |-> 1 ]> =>>
<PUSH-1 : SUB : STORE-x ,[ 1 ],[ x |-> 1 ]> =>>
<SUB : STORE-x ,[ 1,1 ],[ x |-> 1 ]> =>>
<STORE-x ,[ 0 ],[ x |-> 1 ]> =>>
< e ,[ ],[ x |-> 0 ]> ^d4ZWAMou

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.0.18",
	"elements": [
		{
			"type": "text",
			"version": 836,
			"versionNonce": 1875869677,
			"isDeleted": false,
			"id": "qic3eNdp",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -287.75006103515625,
			"y": -60.79998779296875,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 633.564453125,
			"height": 100,
			"seed": 998988424,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1747751025803,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "TE [ x:=1; if x = 0 then x:=x+1 else x:=x-1 ] = \nTE [ x:=1 ] : TE [ if x = 0 then x:=x+1 else x:=x-1 ] =\nPUSH-1 : STORE-x : TE [ if x = 0 then x:=x+1 else x:=x-1 ] =\nPUSH-1 : STORE-x : TB [ x = 0 ] : BRANCH( TE [ x:=x+1 ], TE [ x:=x-1 ] ) = ",
			"rawText": "TE [ x:=1; if x = 0 then x:=x+1 else x:=x-1 ] = \nTE [ x:=1 ] : TE [ if x = 0 then x:=x+1 else x:=x-1 ] =\nPUSH-1 : STORE-x : TE [ if x = 0 then x:=x+1 else x:=x-1 ] =\nPUSH-1 : STORE-x : TB [ x = 0 ] : BRANCH( TE [ x:=x+1 ], TE [ x:=x-1 ] ) = ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "TE [ x:=1; if x = 0 then x:=x+1 else x:=x-1 ] = \nTE [ x:=1 ] : TE [ if x = 0 then x:=x+1 else x:=x-1 ] =\nPUSH-1 : STORE-x : TE [ if x = 0 then x:=x+1 else x:=x-1 ] =\nPUSH-1 : STORE-x : TB [ x = 0 ] : BRANCH( TE [ x:=x+1 ], TE [ x:=x-1 ] ) = ",
			"lineHeight": 1.25,
			"baseline": 96
		},
		{
			"type": "text",
			"version": 110,
			"versionNonce": 1457160547,
			"isDeleted": false,
			"id": "5kWjcgoA",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -293.25,
			"y": -141.19998168945312,
			"strokeColor": "#5f3dc4",
			"backgroundColor": "transparent",
			"width": 169.228515625,
			"height": 65.00000000000001,
			"seed": 381907960,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1747751025804,
			"link": null,
			"locked": false,
			"fontSize": 52.00000000000001,
			"fontFamily": 1,
			"text": "Preklad",
			"rawText": "Preklad",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Preklad",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "text",
			"version": 118,
			"versionNonce": 2064841293,
			"isDeleted": false,
			"id": "CJ8Xof9v",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -288.3689720517112,
			"y": 39.238057454427235,
			"strokeColor": "#5c940d",
			"backgroundColor": "transparent",
			"width": 1123.134765625,
			"height": 50,
			"seed": 757524104,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1747751025804,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "PUSH-1 : STORE-x : FETCH-x : PUSH-0 : EQ : BRANCH( FETCH-x : PUSH-1 : ADD : STORE-x , FETCH-x : PUSH-1 : SUB : STORE-x ) =\nc",
			"rawText": "PUSH-1 : STORE-x : FETCH-x : PUSH-0 : EQ : BRANCH( FETCH-x : PUSH-1 : ADD : STORE-x , FETCH-x : PUSH-1 : SUB : STORE-x ) =\nc",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "PUSH-1 : STORE-x : FETCH-x : PUSH-0 : EQ : BRANCH( FETCH-x : PUSH-1 : ADD : STORE-x , FETCH-x : PUSH-1 : SUB : STORE-x ) =\nc",
			"lineHeight": 1.25,
			"baseline": 46
		},
		{
			"type": "text",
			"version": 199,
			"versionNonce": 795499779,
			"isDeleted": false,
			"id": "37RDLI5b",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -287.9832948230563,
			"y": 87.80953616187702,
			"strokeColor": "#5f3dc4",
			"backgroundColor": "transparent",
			"width": 237.833984375,
			"height": 65.00000000000001,
			"seed": 1243402120,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1747751025804,
			"link": null,
			"locked": false,
			"fontSize": 52.00000000000001,
			"fontFamily": 1,
			"text": "Vykonanie",
			"rawText": "Vykonanie",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Vykonanie",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "text",
			"version": 246,
			"versionNonce": 414722221,
			"isDeleted": false,
			"id": "d4ZWAMou",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -284.5833100818454,
			"y": 172.0095025925411,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 664.43359375,
			"height": 275,
			"seed": 1518378888,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1747751025804,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "<PUSH-1 : ... ,[ ],[ ]> =>>\n<STORE-x: ... ,[ 1 ],[ ]> =>>\n<FETCH-x: ... ,[ ],[ x |-> 1 ]> =>>\n<PUSH-0: ... ,[ 1 ],[ x |-> 1 ]> =>>\n<EQ: ... ,[ 0 , 1 ],[ x |-> 1 ]> =>>\n<BRANCH ( ... , FETCH-x : PUSH-1 : SUB : STORE-x ) ,[ false ],[ x |-> 1 ]> =>>\n<FETCH-x : PUSH-1 : SUB : STORE-x ,[  ],[ x |-> 1 ]> =>>\n<PUSH-1 : SUB : STORE-x ,[ 1 ],[ x |-> 1 ]> =>>\n<SUB : STORE-x ,[ 1,1 ],[ x |-> 1 ]> =>>\n<STORE-x ,[ 0 ],[ x |-> 1 ]> =>>\n< e ,[ ],[ x |-> 0 ]>",
			"rawText": "<PUSH-1 : ... ,[ ],[ ]> =>>\n<STORE-x: ... ,[ 1 ],[ ]> =>>\n<FETCH-x: ... ,[ ],[ x |-> 1 ]> =>>\n<PUSH-0: ... ,[ 1 ],[ x |-> 1 ]> =>>\n<EQ: ... ,[ 0 , 1 ],[ x |-> 1 ]> =>>\n<BRANCH ( ... , FETCH-x : PUSH-1 : SUB : STORE-x ) ,[ false ],[ x |-> 1 ]> =>>\n<FETCH-x : PUSH-1 : SUB : STORE-x ,[  ],[ x |-> 1 ]> =>>\n<PUSH-1 : SUB : STORE-x ,[ 1 ],[ x |-> 1 ]> =>>\n<SUB : STORE-x ,[ 1,1 ],[ x |-> 1 ]> =>>\n<STORE-x ,[ 0 ],[ x |-> 1 ]> =>>\n< e ,[ ],[ x |-> 0 ]>",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "<PUSH-1 : ... ,[ ],[ ]> =>>\n<STORE-x: ... ,[ 1 ],[ ]> =>>\n<FETCH-x: ... ,[ ],[ x |-> 1 ]> =>>\n<PUSH-0: ... ,[ 1 ],[ x |-> 1 ]> =>>\n<EQ: ... ,[ 0 , 1 ],[ x |-> 1 ]> =>>\n<BRANCH ( ... , FETCH-x : PUSH-1 : SUB : STORE-x ) ,[ false ],[ x |-> 1 ]> =>>\n<FETCH-x : PUSH-1 : SUB : STORE-x ,[  ],[ x |-> 1 ]> =>>\n<PUSH-1 : SUB : STORE-x ,[ 1 ],[ x |-> 1 ]> =>>\n<SUB : STORE-x ,[ 1,1 ],[ x |-> 1 ]> =>>\n<STORE-x ,[ 0 ],[ x |-> 1 ]> =>>\n< e ,[ ],[ x |-> 0 ]>",
			"lineHeight": 1.25,
			"baseline": 271
		}
	],
	"appState": {
		"theme": "dark",
		"viewBackgroundColor": "#ffffff",
		"currentItemStrokeColor": "#000000",
		"currentItemBackgroundColor": "transparent",
		"currentItemFillStyle": "hachure",
		"currentItemStrokeWidth": 1,
		"currentItemStrokeStyle": "solid",
		"currentItemRoughness": 1,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 1,
		"currentItemFontSize": 20,
		"currentItemTextAlign": "left",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": 324.24210321335556,
		"scrollY": 216.05773344494037,
		"zoom": {
			"value": 1
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