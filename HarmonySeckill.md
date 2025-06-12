---
title: HarmonySeckill
language_tabs:
  - shell: Shell
  - http: HTTP
  - javascript: JavaScript
  - ruby: Ruby
  - python: Python
  - php: PHP
  - java: Java
  - go: Go
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: "@tarslib/widdershins v4.0.30"

---

# HarmonySeckill

Base URLs:  
http://120.24.168.13:25565/

# Authentication

# 用户认证控制器

## POST 用户注册接口

POST /api/user/register

> Body 请求参数

```json
{
  "userId": "string",
  "username": "string",
  "password": "string",
  "email": "string",
  "phone": "string",
  "realName": "string",
  "idCard": "string",
  "registerTime": "string",
  "lastLogin": "string",
  "status": 0
}
```

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|Authorization|header|string| 否 |none|
|body|body|[User](#schemauser)| 否 |none|

> 返回示例

> 200 Response

```json
{
  "code": 0,
  "msg": "",
  "data": {}
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Result](#schemaresult)|

## POST 用户登录接口

POST /api/user/login

> Body 请求参数

```json
{
  "username": "string",
  "password": "string"
}
```

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|Authorization|header|string| 否 |none|
|body|body|[LoginParams](#schemaloginparams)| 否 |none|

> 返回示例

> 200 Response

```json
{
  "code": 0,
  "msg": "",
  "data": {}
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Result](#schemaresult)|

# 评论控制器

## POST insertReview

POST /api/reviews/insert

> Body 请求参数

```json
{
  "reviewId": "string",
  "jingdianId": 0,
  "userId": "string",
  "rating": 0,
  "content": "string",
  "reviewTime": "string",
  "images": [
    "string"
  ],
  "likes": 0,
  "user": {
    "userId": "string",
    "username": "string",
    "password": "string",
    "email": "string",
    "phone": "string",
    "realName": "string",
    "idCard": "string",
    "registerTime": "string",
    "lastLogin": "string",
    "status": 0
  }
}
```

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|Authorization|header|string| 否 |none|
|body|body|[Review](#schemareview)| 否 |none|

> 返回示例

> 200 Response

```json
{
  "code": 0,
  "msg": "",
  "data": {}
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Result](#schemaresult)|

# 商品管理控制器

## GET 多条件查询商品列表

GET /api/product

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|productName|query|string| 否 |商品名称（模糊查询）|
|opid|query|string| 否 |商家ID|
|Authorization|header|string| 否 |none|

> 返回示例

> 200 Response

```json
{
  "code": 0,
  "msg": "",
  "data": [
    {
      "proId": "",
      "proName": "",
      "type": "",
      "description": "",
      "originPrice": 0,
      "discountPrice": 0,
      "bookRule": "",
      "infrastructureList": [
        ""
      ],
      "openHour": "",
      "serList": [
        ""
      ],
      "shortcutList": [
        ""
      ],
      "tele": "",
      "Addr": "",
      "opId": "",
      "stock": 0
    }
  ]
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[ResponseEntityApiResponseListProduct](#schemaresponseentityapiresponselistproduct)|

## GET findProductsByType

GET /api/product/type/{type}

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|type|path|string| 是 |none|
|Authorization|header|string| 否 |none|

> 返回示例

> 200 Response

```json
{
  "code": 0,
  "msg": "",
  "data": [
    {
      "proId": "",
      "proName": "",
      "type": "",
      "description": "",
      "originPrice": 0,
      "discountPrice": 0,
      "bookRule": "",
      "infrastructureList": [
        ""
      ],
      "openHour": "",
      "serList": [
        ""
      ],
      "shortcutList": [
        ""
      ],
      "tele": "",
      "Addr": "",
      "opId": "",
      "stock": 0
    }
  ]
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[ResponseEntityApiResponseListProduct](#schemaresponseentityapiresponselistproduct)|

## GET 获取商品详情

GET /api/product/{proId}

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|proId|path|string| 是 |商品ID|
|Authorization|header|string| 否 |none|

> 返回示例

> 200 Response

```json
{
  "code": 0,
  "msg": "",
  "data": {
    "proId": "",
    "proName": "",
    "type": "",
    "description": "",
    "originPrice": 0,
    "discountPrice": 0,
    "bookRule": "",
    "infrastructureList": [
      ""
    ],
    "openHour": "",
    "serList": [
      ""
    ],
    "shortcutList": [
      ""
    ],
    "tele": "",
    "Addr": "",
    "opId": "",
    "stock": 0
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[ResponseEntityApiResponseProduct](#schemaresponseentityapiresponseproduct)|

## POST 直接创建商品（持久化到数据库）

POST /api/product/add

> Body 请求参数

```json
{
  "proId": "string",
  "proName": "string",
  "type": "string",
  "description": "string",
  "originPrice": 0,
  "discountPrice": 0,
  "bookRule": "string",
  "infrastructureList": [
    "string"
  ],
  "openHour": "string",
  "serList": [
    "string"
  ],
  "shortcutList": [
    "string"
  ],
  "tele": "string",
  "Addr": "string",
  "opId": "string",
  "stock": 0
}
```

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|Authorization|header|string| 否 |none|
|body|body|[Product](#schemaproduct)| 否 |none|

> 返回示例

> 200 Response

```json
{
  "code": 0,
  "msg": "",
  "data": {
    "proId": "",
    "proName": "",
    "type": "",
    "description": "",
    "originPrice": 0,
    "discountPrice": 0,
    "bookRule": "",
    "infrastructureList": [
      ""
    ],
    "openHour": "",
    "serList": [
      ""
    ],
    "shortcutList": [
      ""
    ],
    "tele": "",
    "Addr": "",
    "opId": "",
    "stock": 0
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[ResponseEntityApiResponseProduct](#schemaresponseentityapiresponseproduct)|

## POST 更新商品信息

POST /api/product/update/{proId}

> Body 请求参数

```json
{
  "proId": "string",
  "proName": "string",
  "type": "string",
  "description": "string",
  "originPrice": 0,
  "discountPrice": 0,
  "bookRule": "string",
  "infrastructureList": [
    "string"
  ],
  "openHour": "string",
  "serList": [
    "string"
  ],
  "shortcutList": [
    "string"
  ],
  "tele": "string",
  "Addr": "string",
  "opId": "string",
  "stock": 0
}
```

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|proId|path|string| 是 |商品ID|
|Authorization|header|string| 否 |none|
|body|body|[Product](#schemaproduct)| 否 |none|

> 返回示例

> 200 Response

```json
{
  "code": 0,
  "msg": "",
  "data": {
    "proId": "",
    "proName": "",
    "type": "",
    "description": "",
    "originPrice": 0,
    "discountPrice": 0,
    "bookRule": "",
    "infrastructureList": [
      ""
    ],
    "openHour": "",
    "serList": [
      ""
    ],
    "shortcutList": [
      ""
    ],
    "tele": "",
    "Addr": "",
    "opId": "",
    "stock": 0
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[ResponseEntityApiResponseProduct](#schemaresponseentityapiresponseproduct)|

## POST 删除商品

POST /api/product/delete/{proId}

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|proId|path|string| 是 |商品ID|
|Authorization|header|string| 否 |none|

> 返回示例

> 200 Response

```json
{
  "code": 0,
  "msg": "",
  "data": ""
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[ResponseEntityApiResponseString](#schemaresponseentityapiresponsestring)|

# 活动管理控制器

## POST 创建新活动

POST /api/activities/add

> Body 请求参数

```json
{
  "actId": "string",
  "actName": "string",
  "desc": "string",
  "rule": "string",
  "openHour": "string",
  "total": 0,
  "tele": "string",
  "shortcutList": [
    [
      [
        {}
      ]
    ]
  ],
  "location": "string"
}
```

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|Authorization|header|string| 否 |none|
|body|body|[Activity](#schemaactivity)| 否 |none|

> 返回示例

> 200 Response

```json
{
  "code": 0,
  "msg": "",
  "data": ""
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[ResponseEntityApiResponseString](#schemaresponseentityapiresponsestring)|

## GET 根据ID获取活动详情

GET /api/activities/{actId}

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|actId|path|string| 是 |活动ID|
|Authorization|header|string| 否 |none|

> 返回示例

> 200 Response

```json
{
  "code": 0,
  "msg": "",
  "data": {
    "actId": "",
    "actName": "",
    "desc": "",
    "rule": "",
    "openHour": "",
    "total": 0,
    "tele": "",
    "shortcutList": [
      [
        []
      ]
    ],
    "location": ""
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[ResponseEntityApiResponseActivity](#schemaresponseentityapiresponseactivity)|

## POST 更新活动信息

POST /api/activities/update

> Body 请求参数

```json
{
  "actId": "string",
  "actName": "string",
  "desc": "string",
  "rule": "string",
  "openHour": "string",
  "total": 0,
  "tele": "string",
  "shortcutList": [
    [
      [
        {}
      ]
    ]
  ],
  "location": "string"
}
```

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|Authorization|header|string| 否 |none|
|body|body|[Activity](#schemaactivity)| 否 |none|

> 返回示例

> 200 Response

```json
{
  "code": 0,
  "msg": "",
  "data": ""
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[ResponseEntityApiResponseString](#schemaresponseentityapiresponsestring)|

## GET 条件查询活动列表

GET /api/activities/search

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|actName|query|string| 否 |活动名称（模糊查询）|
|tele|query|string| 否 |联系电话|
|minTotal|query|integer| 否 |最小名额数|
|Authorization|header|string| 否 |none|

> 返回示例

> 200 Response

```json
{
  "code": 0,
  "msg": "",
  "data": [
    {
      "actId": "",
      "actName": "",
      "desc": "",
      "rule": "",
      "openHour": "",
      "total": 0,
      "tele": "",
      "shortcutList": [
        [
          []
        ]
      ],
      "location": ""
    }
  ]
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[ResponseEntityApiResponseListActivity](#schemaresponseentityapiresponselistactivity)|

## GET 分页查询活动列表

GET /api/activities/page

> Body 请求参数

```json
{
  "key": {}
}
```

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|page|query|integer| 是 |当前页码（从1开始）|
|size|query|integer| 是 |每页数量|
|Authorization|header|string| 否 |none|
|body|body|[MapObject](#schemamapobject)| 否 |none|

> 返回示例

> 200 Response

```json
{
  "code": 0,
  "msg": "",
  "data": [
    {
      "actId": "",
      "actName": "",
      "desc": "",
      "rule": "",
      "openHour": "",
      "total": 0,
      "tele": "",
      "shortcutList": [
        [
          []
        ]
      ],
      "location": ""
    }
  ]
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[ResponseEntityApiResponseListActivity](#schemaresponseentityapiresponselistactivity)|

## POST 删除活动

POST /api/activities/delete/{actId}

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|actId|path|string| 是 |活动ID|
|Authorization|header|string| 否 |none|

> 返回示例

> 200 Response

```json
{
  "code": 0,
  "msg": "",
  "data": ""
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[ResponseEntityApiResponseString](#schemaresponseentityapiresponsestring)|

## POST 更新活动名额

POST /api/activities/total/{actId}

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|actId|path|string| 是 |活动ID|
|total|query|integer| 是 |新的名额数量|
|Authorization|header|string| 否 |none|

> 返回示例

> 200 Response

```json
{
  "code": 0,
  "msg": "",
  "data": ""
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[ResponseEntityApiResponseString](#schemaresponseentityapiresponsestring)|

# 攻略管理控制器，提供对攻略（Strategy）实体的增删改查操作。

## GET 根据攻略ID查询攻略详情。

GET /api/strategies/{secId}

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|secId|path|string| 是 |攻略ID|
|Authorization|header|string| 否 |none|

> 返回示例

> 200 Response

```json
{
  "code": 0,
  "msg": "",
  "data": {
    "secId": "",
    "userId": "",
    "content": "",
    "nickName": "",
    "avatar": ""
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[ResponseEntityApiResponseStrategy](#schemaresponseentityapiresponsestrategy)|

## POST 添加新攻略。

POST /api/strategies/add

> Body 请求参数

```json
{
  "secId": "string",
  "userId": "string",
  "content": "string",
  "nickName": "string",
  "avatar": "string"
}
```

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|Authorization|header|string| 否 |none|
|body|body|[Strategy](#schemastrategy)| 否 |none|

> 返回示例

> 200 Response

```json
{
  "code": 0,
  "msg": "",
  "data": ""
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[ResponseEntityApiResponseString](#schemaresponseentityapiresponsestring)|

## POST 更新攻略信息。

POST /api/strategies/update

> Body 请求参数

```json
{
  "secId": "string",
  "userId": "string",
  "content": "string",
  "nickName": "string",
  "avatar": "string"
}
```

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|Authorization|header|string| 否 |none|
|body|body|[Strategy](#schemastrategy)| 否 |none|

> 返回示例

> 200 Response

```json
{
  "code": 0,
  "msg": "",
  "data": ""
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[ResponseEntityApiResponseString](#schemaresponseentityapiresponsestring)|

## POST 根据ID删除攻略。

POST /api/strategies/delete/{secId}

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|secId|path|string| 是 |攻略ID|
|Authorization|header|string| 否 |none|

> 返回示例

> 200 Response

```json
{
  "code": 0,
  "msg": "",
  "data": ""
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[ResponseEntityApiResponseString](#schemaresponseentityapiresponsestring)|

## GET 根据条件查询攻略列表。

GET /api/strategies/search

> Body 请求参数

```json
{
  "key": {}
}
```

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|Authorization|header|string| 否 |none|
|body|body|[MapObject](#schemamapobject)| 否 |none|

> 返回示例

> 200 Response

```json
{
  "code": 0,
  "msg": "",
  "data": [
    {
      "secId": "",
      "userId": "",
      "content": "",
      "nickName": "",
      "avatar": ""
    }
  ]
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[ResponseEntityApiResponseListStrategy](#schemaresponseentityapiresponseliststrategy)|

# 数据模型

<h2 id="tocS_Result">Result</h2>

<a id="schemaresult"></a>
<a id="schema_Result"></a>
<a id="tocSresult"></a>
<a id="tocsresult"></a>

```json
{
  "code": 0,
  "msg": "string",
  "data": {}
}

```

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|code|integer|false|none||状态码 200成功 400失败|
|msg|string|false|none||返回消息|
|data|object|false|none||返回数据|

<h2 id="tocS_User">User</h2>

<a id="schemauser"></a>
<a id="schema_User"></a>
<a id="tocSuser"></a>
<a id="tocsuser"></a>

```json
{
  "userId": "string",
  "username": "string",
  "password": "string",
  "email": "string",
  "phone": "string",
  "realName": "string",
  "idCard": "string",
  "registerTime": "string",
  "lastLogin": "string",
  "status": 0
}

```

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|userId|string|false|none||用户ID|
|username|string|false|none||用户名|
|password|string|false|none||密码|
|email|string|false|none||邮箱|
|phone|string|false|none||电话|
|realName|string|false|none||真实姓名|
|idCard|string|false|none||身份证号|
|registerTime|string|false|none||注册时间|
|lastLogin|string|false|none||最后登录时间|
|status|integer|false|none||状态：1-正常, 0-禁用|

<h2 id="tocS_LoginParams">LoginParams</h2>

<a id="schemaloginparams"></a>
<a id="schema_LoginParams"></a>
<a id="tocSloginparams"></a>
<a id="tocsloginparams"></a>

```json
{
  "username": "string",
  "password": "string"
}

```

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|username|string|false|none||none|
|password|string|false|none||none|

<h2 id="tocS_Review">Review</h2>

<a id="schemareview"></a>
<a id="schema_Review"></a>
<a id="tocSreview"></a>
<a id="tocsreview"></a>

```json
{
  "reviewId": "string",
  "jingdianId": 0,
  "userId": "string",
  "rating": 0,
  "content": "string",
  "reviewTime": "string",
  "images": [
    "string"
  ],
  "likes": 0,
  "user": {
    "userId": "string",
    "username": "string",
    "password": "string",
    "email": "string",
    "phone": "string",
    "realName": "string",
    "idCard": "string",
    "registerTime": "string",
    "lastLogin": "string",
    "status": 0
  }
}

```

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|reviewId|string|false|none||评论ID|
|jingdianId|integer|false|none||景点ID|
|userId|string|false|none||用户ID|
|rating|integer|false|none||评分(1-5星)|
|content|string|false|none||评论内容|
|reviewTime|string|false|none||评论时间|
|images|[string]|false|none||评论图片列表|
|likes|integer|false|none||点赞数|
|user|[User](#schemauser)|false|none||none|

<h2 id="tocS_Product">Product</h2>

<a id="schemaproduct"></a>
<a id="schema_Product"></a>
<a id="tocSproduct"></a>
<a id="tocsproduct"></a>

```json
{
  "proId": "string",
  "proName": "string",
  "type": "string",
  "description": "string",
  "originPrice": 0,
  "discountPrice": 0,
  "bookRule": "string",
  "infrastructureList": [
    "string"
  ],
  "openHour": "string",
  "serList": [
    "string"
  ],
  "shortcutList": [
    "string"
  ],
  "tele": "string",
  "Addr": "string",
  "opId": "string",
  "stock": 0
}

```

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|proId|string|false|none||商品ID|
|proName|string|false|none||商品名称|
|type|string|false|none||商品类型|
|description|string|false|none||商品描述|
|originPrice|number|false|none||原价|
|discountPrice|number|false|none||折扣价|
|bookRule|string|false|none||入住须知|
|infrastructureList|[string]|false|none||设施列表|
|openHour|string|false|none||营业时间|
|serList|[string]|false|none||服务列表|
|shortcutList|[string]|false|none||商品图片列表|
|tele|string|false|none||联系电话|
|Addr|string|false|none||地址|
|opId|string|false|none||商家id|
|stock|integer|false|none||库存|

<h2 id="tocS_ResponseEntityApiResponseListProduct">ResponseEntityApiResponseListProduct</h2>

<a id="schemaresponseentityapiresponselistproduct"></a>
<a id="schema_ResponseEntityApiResponseListProduct"></a>
<a id="tocSresponseentityapiresponselistproduct"></a>
<a id="tocsresponseentityapiresponselistproduct"></a>

```json
{
  "code": 0,
  "msg": "string",
  "data": [
    {
      "proId": "string",
      "proName": "string",
      "type": "string",
      "description": "string",
      "originPrice": 0,
      "discountPrice": 0,
      "bookRule": "string",
      "infrastructureList": [
        "string"
      ],
      "openHour": "string",
      "serList": [
        "string"
      ],
      "shortcutList": [
        "string"
      ],
      "tele": "string",
      "Addr": "string",
      "opId": "string",
      "stock": 0
    }
  ]
}

```

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|code|integer|false|none||none|
|msg|string|false|none||none|
|data|[[Product](#schemaproduct)]|false|none||none|

<h2 id="tocS_ResponseEntityApiResponseProduct">ResponseEntityApiResponseProduct</h2>

<a id="schemaresponseentityapiresponseproduct"></a>
<a id="schema_ResponseEntityApiResponseProduct"></a>
<a id="tocSresponseentityapiresponseproduct"></a>
<a id="tocsresponseentityapiresponseproduct"></a>

```json
{
  "code": 0,
  "msg": "string",
  "data": {
    "proId": "string",
    "proName": "string",
    "type": "string",
    "description": "string",
    "originPrice": 0,
    "discountPrice": 0,
    "bookRule": "string",
    "infrastructureList": [
      "string"
    ],
    "openHour": "string",
    "serList": [
      "string"
    ],
    "shortcutList": [
      "string"
    ],
    "tele": "string",
    "Addr": "string",
    "opId": "string",
    "stock": 0
  }
}

```

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|code|integer|false|none||none|
|msg|string|false|none||none|
|data|[Product](#schemaproduct)|false|none||com.guet.harmonynext.entity.Product|

<h2 id="tocS_ResponseEntityApiResponseString">ResponseEntityApiResponseString</h2>

<a id="schemaresponseentityapiresponsestring"></a>
<a id="schema_ResponseEntityApiResponseString"></a>
<a id="tocSresponseentityapiresponsestring"></a>
<a id="tocsresponseentityapiresponsestring"></a>

```json
{
  "code": 0,
  "msg": "string",
  "data": "string"
}

```

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|code|integer|false|none||none|
|msg|string|false|none||none|
|data|string|false|none||none|

<h2 id="tocS_Activity">Activity</h2>

<a id="schemaactivity"></a>
<a id="schema_Activity"></a>
<a id="tocSactivity"></a>
<a id="tocsactivity"></a>

```json
{
  "actId": "string",
  "actName": "string",
  "desc": "string",
  "rule": "string",
  "openHour": "string",
  "total": 0,
  "tele": "string",
  "shortcutList": [
    [
      [
        {}
      ]
    ]
  ],
  "location": "string"
}

```

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|actId|string|false|none||活动ID|
|actName|string|false|none||活动名称|
|desc|string|false|none||活动描述|
|rule|string|false|none||活动规则|
|openHour|string|false|none||举办时间|
|total|integer|false|none||名额|
|tele|string|false|none||联系方式|
|shortcutList|[array]|false|none||活动样图|
|location|string|false|none||活动地点|

<h2 id="tocS_ResponseEntityApiResponseActivity">ResponseEntityApiResponseActivity</h2>

<a id="schemaresponseentityapiresponseactivity"></a>
<a id="schema_ResponseEntityApiResponseActivity"></a>
<a id="tocSresponseentityapiresponseactivity"></a>
<a id="tocsresponseentityapiresponseactivity"></a>

```json
{
  "code": 0,
  "msg": "string",
  "data": {
    "actId": "string",
    "actName": "string",
    "desc": "string",
    "rule": "string",
    "openHour": "string",
    "total": 0,
    "tele": "string",
    "shortcutList": [
      [
        [
          {}
        ]
      ]
    ],
    "location": "string"
  }
}

```

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|code|integer|false|none||none|
|msg|string|false|none||none|
|data|[Activity](#schemaactivity)|false|none||none|

<h2 id="tocS_ResponseEntityApiResponseListActivity">ResponseEntityApiResponseListActivity</h2>

<a id="schemaresponseentityapiresponselistactivity"></a>
<a id="schema_ResponseEntityApiResponseListActivity"></a>
<a id="tocSresponseentityapiresponselistactivity"></a>
<a id="tocsresponseentityapiresponselistactivity"></a>

```json
{
  "code": 0,
  "msg": "string",
  "data": [
    {
      "actId": "string",
      "actName": "string",
      "desc": "string",
      "rule": "string",
      "openHour": "string",
      "total": 0,
      "tele": "string",
      "shortcutList": [
        [
          [
            {}
          ]
        ]
      ],
      "location": "string"
    }
  ]
}

```

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|code|integer|false|none||none|
|msg|string|false|none||none|
|data|[[Activity](#schemaactivity)]|false|none||none|

<h2 id="tocS_MapObject">MapObject</h2>

<a id="schemamapobject"></a>
<a id="schema_MapObject"></a>
<a id="tocSmapobject"></a>
<a id="tocsmapobject"></a>

```json
{
  "key": {}
}

```

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|key|object|false|none||none|

<h2 id="tocS_Strategy">Strategy</h2>

<a id="schemastrategy"></a>
<a id="schema_Strategy"></a>
<a id="tocSstrategy"></a>
<a id="tocsstrategy"></a>

```json
{
  "secId": "string",
  "userId": "string",
  "content": "string",
  "nickName": "string",
  "avatar": "string"
}

```

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|secId|string|false|none||攻略ID|
|userId|string|false|none||用户ID|
|content|string|false|none||攻略内容|
|nickName|string|false|none||昵称|
|avatar|string|false|none||头像|

<h2 id="tocS_ResponseEntityApiResponseStrategy">ResponseEntityApiResponseStrategy</h2>

<a id="schemaresponseentityapiresponsestrategy"></a>
<a id="schema_ResponseEntityApiResponseStrategy"></a>
<a id="tocSresponseentityapiresponsestrategy"></a>
<a id="tocsresponseentityapiresponsestrategy"></a>

```json
{
  "code": 0,
  "msg": "string",
  "data": {
    "secId": "string",
    "userId": "string",
    "content": "string",
    "nickName": "string",
    "avatar": "string"
  }
}

```

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|code|integer|false|none||none|
|msg|string|false|none||none|
|data|[Strategy](#schemastrategy)|false|none||none|

<h2 id="tocS_ResponseEntityApiResponseListStrategy">ResponseEntityApiResponseListStrategy</h2>

<a id="schemaresponseentityapiresponseliststrategy"></a>
<a id="schema_ResponseEntityApiResponseListStrategy"></a>
<a id="tocSresponseentityapiresponseliststrategy"></a>
<a id="tocsresponseentityapiresponseliststrategy"></a>

```json
{
  "code": 0,
  "msg": "string",
  "data": [
    {
      "secId": "string",
      "userId": "string",
      "content": "string",
      "nickName": "string",
      "avatar": "string"
    }
  ]
}

```

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|code|integer|false|none||none|
|msg|string|false|none||none|
|data|[[Strategy](#schemastrategy)]|false|none||none|

