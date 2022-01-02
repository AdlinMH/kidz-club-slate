---
title: KidzClub API Reference

# language_tabs: # must be one of https://git.io/vQNgJ
#   - shell

toc_footers:
  - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true

code_clipboard: true

meta:
  - name: description
    content: Documentation for the KidzClub API
---

# Introduction

Welcome to the KidzClub API! You can use our API to access KidzClub API endpoints. You can view code examples in the dark area to the right.





# Authentication

## POST: Login

> Example Request:

```json
{
	"email": "randymuhroji@gmail.com",
	"password": "q",
    "notificationToken": "1234asd"
}
```

> Example Response:

```json
{
  "data": {
    "token": "Bearer eyJhbGciOiJIXVCJ9.eyJ1c2VySWQiOiAyNGE0NGEwYjBlOT",
    "user": {
      "firstname": "Randy",
      "lastname": "M",
      "avatar": "6039da4f64ca9f4e91cae373",
      "lastSeenAt": "2021-12-31T03:41:49.365Z", // Please remove this
      "lastLoginAt": "2021-12-31T03:41:49.365Z", // Please remove this
      "_id": "5f0ec6af024a44a0b0e90159", // Please remove this
      "email": "randymuhroji@gmail.com",
      "lastLoginIp": "140.213.229.117", // Please remove this
      "updatedAt": "2021-12-31T03:41:49.365Z", // Please remove this
      "deleted": false, // Please remove this
      "id": "5f0ec6af024a44a0b0e90159" // Please remove this
    }
  },
  "success": true,
  "error": null,
  "msg": ""
}
```

`POST /front/v2/login`

### Request Schema

<aside class="white">
{
  <br /><space /><strong>"email"</strong>: string
  <br /><space /><strong>"password"</strong>: string
  <br /><space /><strong>"notificationToken"</strong>: string | null
  <br />
}
</aside>

### Response Schema

<aside class="white">
{
  <br /><space /><strong>"data"</strong>: {
  <br /><space /><strong><space />"token"</strong>: string,
  <br /><space /><strong><space />"user"</strong>: {
  <br /><space /><strong><space /><space />"firstname"</strong>: string,
  <br /><space /><strong><space /><space />"lastname"</strong>: string,
  <br /><space /><strong><space /><space />"avatar"</strong>: string,
  <br /><space /><strong><space /><space />"email"</strong>: string,
  <br /><space />}
  },
  <br /><space /><strong>"success"</strong>: boolean,
  <br /><space /><strong>"error"</strong>: ErrorObject | null,
  <br /><space /><strong>"msg"</strong>: string
  <br />
}
</aside>




## POST: Register

> Example Request:

```json
{
  "childName": "Randy Junior",
  "parentName": "Randy Muhroji",
  "parentEmail": "randy@elemes.id",
  "password": "q",
  "notificationToken": null
}
```

> Example Response:

```json
{
  "data": {},
  "success": true,
  "error": null,
  "msg": "updated successfully"
}

```

`POST /front/v2/register`
### Request Schema

<aside class="white">
{
  <br /><space /><strong>"childName"</strong>: string
  <br /><space /><strong>"parentName"</strong>: string
  <br /><space /><strong>"parentEmail"</strong>: string
  <br /><space /><strong>"password"</strong>: string
  <br /><space /><strong>"notificationToken"</strong>: string | null
  <br />
}
</aside>

### Response Schema

<aside class="white">
{
  <br /><space /><strong>"data"</strong>: {},
  <br /><space /><strong>"success"</strong>: boolean,
  <br /><space /><strong>"error"</strong>: ErrorObject | null,
  <br /><space /><strong>"msg"</strong>: string
  <br />
}
</aside>



## POST: Reset Pass

> Example Request:

```json
{
  "email": "randy@elemes.id",
}
```

> Example Response:

```json
{
  "data": {},
  "success": true,
  "error": null,
  "msg": "reset form sent to your email"
}

```

`POST /front/v2/resetpass`

<aside class="success">
  Require `header: { Authorization }`
</aside>

### Request Schema

<aside class="white">
{
  <br /><space /><strong>"email"</strong>: string
  <br />
}
</aside>

### Response Schema

<aside class="white">
{
  <br /><space /><strong>"data"</strong>: {},
  <br /><space /><strong>"success"</strong>: boolean,
  <br /><space /><strong>"error"</strong>: ErrorObject | null,
  <br /><space /><strong>"msg"</strong>: string
  <br />
}
</aside>



## PUT: ChangePass

> Example Request:

```json
{
  "currPassword": "old_xxx",
  "newPassword": "new_yyy",
}
```

> Example Response:

```json
{
  "data": {},
  "success": true,
  "error": null,
  "msg": "updated successfully"
}

```

`PUT /front/v2/changepass`

<aside class="success">
  Require `header: { Authorization }`
</aside>

### Request Schema

<aside class="white">
{
  <br /><space /><strong>"currPassword"</strong>: string
  <br /><space /><strong>"newPassword"</strong>: string
  <br />
}
</aside>

### Response Schema

<aside class="white">
{
  <br /><space /><strong>"data"</strong>: {},
  <br /><space /><strong>"success"</strong>: boolean,
  <br /><space /><strong>"error"</strong>: ErrorObject | null,
  <br /><space /><strong>"msg"</strong>: string
  <br />
}
</aside>


<!-- # Notes

<aside class="success">
Don't forget that some API needs to supplied with <code>Authorization</code>.
</aside>
<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>
<aside class="warning">
Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.
</aside>
 -->

# Dashboard

## GET: Dashboard

> Example Response:

```json
{
  "data": {
    "title": "Hai Mom and Dad",
    "subtitle": "Nikmati konten webinar menarik nan seru cukup dengan 1 coin kidzclub",
    "guide": {
      "text": "Lihat panduan belajar",
      "link": "https://www.youtube.com/"
    },
    "banners": [
      {
        "bannerUri": "https://www.ilmubahasainggris.com/wp-content/uploads/2017/03/NGC.jpg",
        "onPress": {
          "type": "in-app-navigation",
          "screen": "detail",
          "screenArgs": {},
        }
      },
      {
        "bannerUri": "in-app-toast",
        "onPress": {
          "type": "in-app-toast",
          "text": "coming soon",
        }
      },
      {
        "bannerUri": "https://www.ilmubahasainggris.com/wp-content/uploads/2017/03/NGC.jpg",
        "onPress": {
          "type": "link",
          "link": "https://www.youtube.com/"
        }
      }
    ],
    "clubCategories": [
      {
        "onPress": {
          "type": "in-app-toast",
          "text": "coming soon",
        },
        "iconUri": "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcR_FUNpkbm3tJHYt4I6WjtOtdizk-LcgPi0YA&usqp=CAU",
        "title": "category 1",
      },
      {
        "onPress": {
          "type": "in-app-toast",
          "text": "coming soon",
        },
        "iconUri": "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcR_FUNpkbm3tJHYt4I6WjtOtdizk-LcgPi0YA&usqp=CAU",
        "title": "category 2",
      }
    ],
    "todaysWebinar": {
      "bannerUri": "https://www.ilmubahasainggris.com/wp-content/uploads/2017/03/NGC.jpg",
      "title": "Cerita si Kancil si cerdik dan Buaya yang malang",
      "speaker": "Ruri Sinuri",
      "episode": "3",
      "startTime": "123456677"
    },
    "upcomingWebinar": [
      {
        "bannerUri": "https://www.ilmubahasainggris.com/wp-content/uploads/2017/03/NGC.jpg",
        "title": "If we synthesize the driver, we can get to the COM",
        "titleTag": "EXCLUSIVE",
        "clubCategory": "Club Membaca",
        "scheduleDate": "12122433232",
        "scheduleTime": ["15:00", "16:00"]
      },
      {
        "bannerUri": "https://www.ilmubahasainggris.com/wp-content/uploads/2017/03/NGC.jpg",
        "title": "If we synthesize the driver, we can get to the COM",
        "titleTag": "EXCLUSIVE",
        "clubCategory": "Club Membaca",
        "scheduleDate": "12122433232",
        "scheduleTime": ["15:00", "16:00"]
      },
    ]
  },
  "success": true,
  "error": null,
  "msg": ""
}
```

`GET /front/v2/dashboard`

<aside class="success">
  Require `header: { Authorization }`
</aside>

### Query Parameters

Parameter | Description
--------- | -----------
none |


### Response Schema

<aside class="white">
{
<br /><space /><strong>"data"</strong>: {
<br /><space /><space /><strong>"title"</strong>: string
<br /><space /><space /><strong>"subtitle"</strong>: string
<br /><space /><space /><strong>"guide"</strong>: {
<br /><space /><space /><space /><strong>"text"</strong>: string
<br /><space /><space /><space /><strong>"link"</strong>: string
<br /><space /><space />}
<br /><space /><space /><strong>"banners"</strong>: [
<br /><space /><space /><space />{
<br /><space /><space /><space /><space /><strong>"bannerUri"</strong>: string
<br /><space /><space /><space /><space /><strong>"onPress"</strong>: DynamicNavigationType
<br /><space /><space /><space />},
<br /><space /><space /><space />...
<br /><space /><space />]
<br /><space /><space /><strong>"clubCategories"</strong>: [
<br /><space /><space /><space />{
<br /><space /><space /><space /><space /><strong>"onPress"</strong>: DynamicNavigationType
<br /><space /><space /><space /><space /><strong>"iconUri"</strong>: string
<br /><space /><space /><space /><space /><strong>"title"</strong>: string
<br /><space /><space /><space />},
<br /><space /><space /><space />...
<br /><space /><space />]
<br /><space /><space /><strong>"todaysWebinar"</strong>: {
<br /><space /><space /><space /><strong>"bannerUri"</strong>: string
<br /><space /><space /><space /><strong>"title"</strong>: string
<br /><space /><space /><space /><strong>"speaker"</strong>: string
<br /><space /><space /><space /><strong>"episode"</strong>: string
<br /><space /><space /><space /><strong>"startTime"</strong>: string
<br /><space /><space />}
<br /><space /><space /><strong>"upcomingWebinar"</strong>: [
<br /><space /><space /><space />{
<br /><space /><space /><space /><space /><strong>"bannerUri"</strong>: string
<br /><space /><space /><space /><space /><strong>"clubCategory"</strong>: string
<br /><space /><space /><space /><space /><strong>"title"</strong>: string
<br /><space /><space /><space /><space /><strong>"titleTag"</strong>: string
<br /><space /><space /><space /><space /><strong>"scheduleDate"</strong>: string
<br /><space /><space /><space /><space /><strong>"scheduleTime"</strong>: string[]
<br /><space /><space /><space />},
<br /><space /><space /><space />...
<br /><space /><space />]
<br /><space />},
<br /><space /><strong>"success"</strong>: boolean
<br /><space /><strong>"error"</strong>: ErrorObject | null
<br /><space /><strong>"msg"</strong>: string
<br />
}
</aside>





# Webinar

## GET: List

> Example HttpRequest:

```shell
GET: {{base_url}}front/v2/webinar/list?category_ids=1,2,3,4&schedule_days=0,1,2,3
```

> Example Response:

```json
{
  "data": [
  {
    "bannerUri": "https://www.ilmubahasainggris.com/wp-content/uploads/2017/03/NGC.jpg",
    "clubCategory": "Club Membaca",
    "title": "If we synthesize the driver, we can get tot the COM internationalization of everything. the teorytical",
    "titleTag": "EXCLUSIVE",
    "scheduleDate": "Rabu, 9 September",
    "scheduleTime": ["15:00", "16:00"]
  },
  {
    "bannerUri": "https://www.ilmubahasainggris.com/wp-content/uploads/2017/03/NGC.jpg",
    "clubCategory": "Club Membaca",
    "title": "Try to calculate the transmitter of value between A and B",
    "titleTag": "EPISODE 2",
    "scheduleDate": "Rabu, 9 September",
    "scheduleTime": ["15:00", "16:00"]
  },
],
  "success": true,
  "error": null,
  "msg": ""
}
```

`GET /front/v2/webinar/list`

<aside class="success">
  Require `header: { Authorization }`
</aside>

### Query Parameters

Parameter | Description
--------- | -------
category_ids | (optional) use for filtering by category id
schedule_days | (optional) use for filtering by schedule days. 0 = Sunday.


### Response Schema

<aside class="white">
{
<br /><space /><strong>"data"</strong>: [
<br /><space />{
<br /><space /><space /><strong>"bannerUri"</strong>: string
<br /><space /><space /><strong>"clubCategory"</strong>: string
<br /><space /><space /><strong>"title"</strong>: string
<br /><space /><space /><strong>"titleTag"</strong>: string
<br /><space /><space /><strong>"scheduleDate"</strong>: string
<br /><space /><space /><strong>"scheduleTime"</strong>: string
<br /><space />},
<br /><space />...
<br />],
<br /><space /><strong>"success"</strong>: boolean
<br /><space /><strong>"error"</strong>: ErrorObject | null
<br /><space /><strong>"msg"</strong>: string
<br />
}
</aside>





# Universal Response
> Example Response:

```json
{
  "data": null,
  "success": true,
  "error": null,
  "msg": ""
}
```
### Schema

<aside class="white">
{
  <br /><space /><strong>"data"</strong>: any | array | object | string,
  <br /><space /><strong>"success"</strong>: boolean,
  <br /><space /><strong>"error"</strong>: ErrorObject | null,
  <br /><space /><strong>"msg"</strong>: string
  <br />
}
</aside>

### ErrorObject Schema

<aside class="white">
{
  <br /><space /><strong>"statusCode"</strong>:?: number | string,
  <br /><space /><strong>"error"</strong>:?: string,
  <br /><space /><strong>"message"</strong>:?: string
  <br />
}
</aside>

### DynamicNavigationType Schema

<aside class="white">
{
<br /><space /><strong>"type"</strong>: 'in-app-navigation' | 'in-app-toast' | 'link'
<br /><space /><strong>"screen"</strong>: string
<br /><space /><strong>"screenArgs"</strong>?: any[]
<br /><space /><strong>"link"</strong>?: string
<br /><space /><strong>"text"</strong>?: string
<br />
}
</aside>




