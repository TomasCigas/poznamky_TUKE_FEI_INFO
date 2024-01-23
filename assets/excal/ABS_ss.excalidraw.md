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
	"source": "https://excalidraw.com",
	"elements": [
		{
			"type": "text",
			"version": 835,
			"versionNonce": 294742152,
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
			"width": 796,
			"height": 99,
			"seed": 998988424,
			"groupIds": [],
			"strokeSharpness": "sharp",
			"boundElements": [],
			"updated": 1705949860737,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "TE [ x:=1; if x = 0 then x:=x+1 else x:=x-1 ] = \nTE [ x:=1 ] : TE [ if x = 0 then x:=x+1 else x:=x-1 ] =\nPUSH-1 : STORE-x : TE [ if x = 0 then x:=x+1 else x:=x-1 ] =\nPUSH-1 : STORE-x : TB [ x = 0 ] : BRANCH( TE [ x:=x+1 ], TE [ x:=x-1 ] ) = ",
			"rawText": "TE [ x:=1; if x = 0 then x:=x+1 else x:=x-1 ] = \nTE [ x:=1 ] : TE [ if x = 0 then x:=x+1 else x:=x-1 ] =\nPUSH-1 : STORE-x : TE [ if x = 0 then x:=x+1 else x:=x-1 ] =\nPUSH-1 : STORE-x : TB [ x = 0 ] : BRANCH( TE [ x:=x+1 ], TE [ x:=x-1 ] ) = ",
			"baseline": 92,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "TE [ x:=1; if x = 0 then x:=x+1 else x:=x-1 ] = \nTE [ x:=1 ] : TE [ if x = 0 then x:=x+1 else x:=x-1 ] =\nPUSH-1 : STORE-x : TE [ if x = 0 then x:=x+1 else x:=x-1 ] =\nPUSH-1 : STORE-x : TB [ x = 0 ] : BRANCH( TE [ x:=x+1 ], TE [ x:=x-1 ] ) = "
		},
		{
			"type": "text",
			"version": 109,
			"versionNonce": 1222454264,
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
			"width": 188,
			"height": 66,
			"seed": 381907960,
			"groupIds": [],
			"strokeSharpness": "sharp",
			"boundElements": [],
			"updated": 1705949516436,
			"fontSize": 52.00000000000001,
			"fontFamily": 1,
			"text": "Preklad",
			"rawText": "Preklad",
			"baseline": 46,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Preklad"
		},
		{
			"type": "text",
			"version": 117,
			"versionNonce": 390517640,
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
			"width": 1333,
			"height": 50,
			"seed": 757524104,
			"groupIds": [],
			"strokeSharpness": "sharp",
			"boundElements": [],
			"updated": 1705949883565,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "PUSH-1 : STORE-x : FETCH-x : PUSH-0 : EQ : BRANCH( FETCH-x : PUSH-1 : ADD : STORE-x , FETCH-x : PUSH-1 : SUB : STORE-x ) =\nc",
			"rawText": "PUSH-1 : STORE-x : FETCH-x : PUSH-0 : EQ : BRANCH( FETCH-x : PUSH-1 : ADD : STORE-x , FETCH-x : PUSH-1 : SUB : STORE-x ) =\nc",
			"baseline": 42,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "PUSH-1 : STORE-x : FETCH-x : PUSH-0 : EQ : BRANCH( FETCH-x : PUSH-1 : ADD : STORE-x , FETCH-x : PUSH-1 : SUB : STORE-x ) =\nc"
		},
		{
			"type": "text",
			"version": 198,
			"versionNonce": 1188389256,
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
			"width": 229,
			"height": 66,
			"seed": 1243402120,
			"groupIds": [],
			"strokeSharpness": "sharp",
			"boundElements": [],
			"updated": 1705949893860,
			"fontSize": 52.00000000000001,
			"fontFamily": 1,
			"text": "Vykonanie",
			"rawText": "Vykonanie",
			"baseline": 46,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Vykonanie"
		},
		{
			"type": "text",
			"version": 245,
			"versionNonce": 432948216,
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
			"width": 790,
			"height": 273,
			"seed": 1518378888,
			"groupIds": [],
			"strokeSharpness": "sharp",
			"boundElements": [],
			"updated": 1705950167723,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "<PUSH-1 : ... ,[ ],[ ]> =>>\n<STORE-x: ... ,[ 1 ],[ ]> =>>\n<FETCH-x: ... ,[ ],[ x |-> 1 ]> =>>\n<PUSH-0: ... ,[ 1 ],[ x |-> 1 ]> =>>\n<EQ: ... ,[ 0 , 1 ],[ x |-> 1 ]> =>>\n<BRANCH ( ... , FETCH-x : PUSH-1 : SUB : STORE-x ) ,[ false ],[ x |-> 1 ]> =>>\n<FETCH-x : PUSH-1 : SUB : STORE-x ,[  ],[ x |-> 1 ]> =>>\n<PUSH-1 : SUB : STORE-x ,[ 1 ],[ x |-> 1 ]> =>>\n<SUB : STORE-x ,[ 1,1 ],[ x |-> 1 ]> =>>\n<STORE-x ,[ 0 ],[ x |-> 1 ]> =>>\n< e ,[ ],[ x |-> 0 ]>",
			"rawText": "<PUSH-1 : ... ,[ ],[ ]> =>>\n<STORE-x: ... ,[ 1 ],[ ]> =>>\n<FETCH-x: ... ,[ ],[ x |-> 1 ]> =>>\n<PUSH-0: ... ,[ 1 ],[ x |-> 1 ]> =>>\n<EQ: ... ,[ 0 , 1 ],[ x |-> 1 ]> =>>\n<BRANCH ( ... , FETCH-x : PUSH-1 : SUB : STORE-x ) ,[ false ],[ x |-> 1 ]> =>>\n<FETCH-x : PUSH-1 : SUB : STORE-x ,[  ],[ x |-> 1 ]> =>>\n<PUSH-1 : SUB : STORE-x ,[ 1 ],[ x |-> 1 ]> =>>\n<SUB : STORE-x ,[ 1,1 ],[ x |-> 1 ]> =>>\n<STORE-x ,[ 0 ],[ x |-> 1 ]> =>>\n< e ,[ ],[ x |-> 0 ]>",
			"baseline": 266,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "<PUSH-1 : ... ,[ ],[ ]> =>>\n<STORE-x: ... ,[ 1 ],[ ]> =>>\n<FETCH-x: ... ,[ ],[ x |-> 1 ]> =>>\n<PUSH-0: ... ,[ 1 ],[ x |-> 1 ]> =>>\n<EQ: ... ,[ 0 , 1 ],[ x |-> 1 ]> =>>\n<BRANCH ( ... , FETCH-x : PUSH-1 : SUB : STORE-x ) ,[ false ],[ x |-> 1 ]> =>>\n<FETCH-x : PUSH-1 : SUB : STORE-x ,[  ],[ x |-> 1 ]> =>>\n<PUSH-1 : SUB : STORE-x ,[ 1 ],[ x |-> 1 ]> =>>\n<SUB : STORE-x ,[ 1,1 ],[ x |-> 1 ]> =>>\n<STORE-x ,[ 0 ],[ x |-> 1 ]> =>>\n< e ,[ ],[ x |-> 0 ]>"
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
		"currentItemStrokeSharpness": "sharp",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"currentItemLinearStrokeSharpness": "round",
		"gridSize": null
	},
	"files": {}
}
```
%%