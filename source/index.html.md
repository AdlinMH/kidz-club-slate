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

