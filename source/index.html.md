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

`/front/v2/login`

### Body Request

<aside class="white">
{
  <br /><space /><strong>"email"</strong>: string
  <br /><space /><strong>"password"</strong>: string
  <br /><space /><strong>"notificationToken"</strong>: null
  <br />
}
</aside>

### Response

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
  <br /><space /><strong>"success"</strong>: true,
  <br /><space /><strong>"error"</strong>: null,
  <br /><space /><strong>"msg"</strong>: ""
<br />}
</aside>

<aside class="white">
{
  <br /><space /><strong>"email"</strong>: string
  <br /><space /><strong>"password"</strong>: string
  <br /><space /><strong>"notificationToken"</strong>: string | null
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

```

### HTTP Request

`POST /front/v2/login`

### Body

Field | isRequired | Description
--------- | ------- | -----------
email | YES
password | YES
notificationToken | NO 



# Notes

<aside class="notice">
Don't forget that some API needs to supplied with <code>Authorization</code>.
</aside>
<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>
<aside class="warning">
Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.
</aside>

