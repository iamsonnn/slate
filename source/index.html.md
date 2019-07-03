---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - jsonnet : request
  - json: response

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

API For Fullfillment

# HUB Backend

## Authentication

Đăng nhập

`POST /api-token-auth/`

User: 

Username: vantrong291

Password: vantrong291

```jsonnet
{
    "username": "vantrong291",
    "password": "vantrong291"
}
```


```json
{
    "token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyX2lkIjoxLCJ1c2VybmFtZSI6InZhbnRyb25nMjkxIiwiZXhwIjoxNTYyMTI4OTA4LCJlbWFpbCI6InZhbnRyb25nMjkxQGdtYWlsLmNvbSJ9.WtL-o04tnZ_x0JYvw6EbxeZhAB9-YDB9VA59QxZGrVk"
}
```

## Products

API cho quản lý và tạo product

Sử dụng Header
`Authorization`
`Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyX2lkIjoxLCJ1c2VybmFtZSI6InZhbnRyb25nMjkxIiwiZXhwIjoxNTYyMTI4OTA4LCJlbWFpbCI6InZhbnRyb25nMjkxQGdtYWlsLmNvbSJ9.WtL-o04tnZ_x0JYvw6EbxeZhAB9-YDB9VA59QxZGrVk`

### Get List Product Categories

Lấy danh sách Product Categories

`GET /api/v1/products/product-categories/`

```jsonnet
None
```

```json
{
    "abstract_category": [
        {
            "id": 1,
            "title": "Áo thời trang nữ",
            "description": "Sơ mi chất liệu thoáng mát, đường may tinh tế, chắc chắn. Thiết kế trẻ trung bẹt vai gợi cảm, năng động. Họa tiết sắc màu trên nền trang nhã, trẻ trung. Sản phẩm mix cùng với short, juyp xòe...tạo nên nét năng động, trẻ trung, cá tính.",
            "preview_image_url": "http://112.137.131.12:8000/wp-content/uploads/2019/06/regular-3.jpg",
            "is_active": true,
            "update_time": "2019-06-30T13:00:33.295185Z",
            "create_time": "2019-06-30T13:00:33.295163Z"
        },
        {
            "id": 2,
            "title": "Áo thời trang nam",
            "description": "Sơ mi chất liệu thoáng mát, đường may tinh tế, chắc chắn. Thiết kế trẻ trung bẹt vai gợi cảm, năng động. Họa tiết sắc màu trên nền trang nhã, trẻ trung. Sản phẩm mix cùng với short, juyp xòe...tạo nên nét năng động, trẻ trung, cá tính.",
            "preview_image_url": "https://nemshop.vn/upload/image/product/san-pham-6183212309244-01547455581.jpg",
            "is_active": true,
            "update_time": "2019-06-30T13:00:53.910876Z",
            "create_time": "2019-06-30T13:00:53.910851Z"
        }
    ]
}
```

### Get List Product

Lấy danh sách Products

`GET /api/v1/products/products/`

```jsonnet
None
```

```json
{
    "abstract_product": [
        {
            "id": 1,
            "category": "Áo thời trang nữ",
            "description": "",
            "base_cost": 50000,
            "currency": "vnd",
            "default_variant": {
                "id": 1,
                "name": "Variant: 1 | Product: NEM LIFE - SƠ MI SM11211"
            },
            "is_active": true,
            "update_time": "2019-06-30T13:01:27.580024Z",
            "create_time": "2019-06-30T13:01:27.580006Z"
        },
        {
            "id": 2,
            "category": "Áo thời trang nữ",
            "description": "",
            "base_cost": 10000,
            "currency": "vnd",
            "default_variant": {
                "id": 1,
                "name": "Variant: 1 | Product: NEM LIFE - SƠ MI SM11211"
            },
            "is_active": true,
            "update_time": "2019-06-30T13:01:53.782655Z",
            "create_time": "2019-06-30T13:01:53.782637Z"
        }
    ]
}
```
### Get Product Info

Lấy danh sach variant của 1 product

`GET /api/v1/products/product-variant/`

```json
{
    "count": 4,
    "next": null,
    "previous": null,
    "results": [
        {
            "id": 4,
            "product": 2,
            "description": "1234",
            "base_cost": "23.00",
            "currency": "vnd",
            "attributes_value": [],
            "product_side": []
        },
        {
            "id": 3,
            "product": 2,
            "description": "1234",
            "base_cost": "120000.00",
            "currency": "vnd",
            "attributes_value": [],
            "product_side": []
        },
        {
            "id": 2,
            "product": 1,
            "description": "Áo sơ mi chất liệu cao cấp, thoáng mát, đường may tỉ mỉ, tinh tế. Kiểu dáng cơ bản nên dễ kết hợp cùng với chân váy (xòe, chữ A...) hay quần công sở (quần suông, quần ống côn, quần lửng, culottes...). Sản phẩm sử dụng tông màu đỏ trẻ trung xuyên suốt đơn giản, thanh lịch. Thiết kế vai cut-out trẻ trung, nữ tính.",
            "base_cost": "120000.00",
            "currency": "vnd",
            "attributes_value": [
                {
                    "id": 2,
                    "attribute_name": "Color",
                    "value": "Green",
                    "attribute": 1
                },
                {
                    "id": 4,
                    "attribute_name": "Size",
                    "value": "XL",
                    "attribute": 2
                },
                {
                    "id": 7,
                    "attribute_name": "Size",
                    "value": "M",
                    "attribute": 4
                },
                {
                    "id": 8,
                    "attribute_name": "Size",
                    "value": "XL",
                    "attribute": 4
                }
            ],
            "product_side": [
                {
                    "id": 3,
                    "type": "Front",
                    "preview_image_url": "http://112.137.131.12:8000/wp-content/uploads/2019/06/regular-3.jpg"
                }
            ]
        },
        {
            "id": 1,
            "product": 1,
            "description": "Áo sơ mi chất liệu cao cấp, thoáng mát, đường may tỉ mỉ, tinh tế. Kiểu dáng cơ bản nên dễ kết hợp cùng với chân váy (xòe, chữ A...) hay quần công sở (quần suông, quần ống côn, quần lửng, culottes...). Sản phẩm sử dụng tông màu đỏ trẻ trung xuyên suốt đơn giản, thanh lịch. Thiết kế vai cut-out trẻ trung, nữ tính.",
            "base_cost": "10000.00",
            "currency": "vnd",
            "attributes_value": [
                {
                    "id": 1,
                    "attribute_name": "Size",
                    "value": "Brown",
                    "attribute": 4
                },
                {
                    "id": 3,
                    "attribute_name": "Size",
                    "value": "M",
                    "attribute": 2
                }
            ],
            "product_side": [
                {
                    "id": 1,
                    "type": "Front",
                    "preview_image_url": "http://112.137.131.12:8000/wp-content/uploads/2019/06/regular-3.jpg"
                },
                {
                    "id": 2,
                    "type": "Back",
                    "preview_image_url": "https://nemshop.vn/upload/image/product/san-pham-6183212309244-01547455581.jpg"
                }
            ]
        }
    ]
}
```
### Generate Mockup

Ghép ảnh mockup và ảnh trắng, sinh ra ảnh mockup của variants

`GET /api/v1/seller/mockup-gennerater/`

```jsonnet
{	
	"artwork_base64": "data:image/png;base64,iVBORw0KGgoA.........CYII=",
	"product_id": 1
}
```

```json
{
    "success": true,
    "data": [
        {
            "attribute_name": "Color",
            "atribute_value_id": 1,
            "attribute_value": "Green",
            "images": [
                {
                    "side": "Front",
                    "preview_mockup_url": "127.0.0.1:8000/media/mockup/mockup_Green_Front.png"
                },
                {
                    "side": "Back",
                    "preview_mockup_url": "127.0.0.1:8000/media/mockup/mockup_Green_Back.png"
                }
            ]
        },
        {
            "attribute_name": "Color",
            "atribute_value_id": 2,
            "attribute_value": "Blue",
            "images": [
                {
                    "side": "Front",
                    "preview_mockup_url": "127.0.0.1:8000/media/mockup/mockup_Blue_Front.png"
                }
            ]
        }
    ]
}
```
### Create Seller Product

> To authorize, use this code:

```json
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> Make sure to replace `meowmeowmeow` with your API key.

Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

# Kittens

## Get All Kittens

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get()
```

```shell
curl "http://example.com/api/kittens"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let kittens = api.kittens.get();
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all kittens.

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

## Delete a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -X DELETE
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted" : ":("
}
```

This endpoint deletes a specific kitten.

### HTTP Request

`DELETE http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to delete

