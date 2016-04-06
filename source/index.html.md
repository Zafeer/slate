---
title: Ion API Docs

language_tabs:
  - shell
---

# Introduction

Welcome to the Ion API! You can use our API to access Ion API endpoints, which can get information on various challenges, progress,rewards and recommendations in our database.

We have language bindings in Shell You can view code examples in the dark area to the right

### Sample Data:

BASE URL :: 54.255.165.21

Id | Name
--------- | -----------
1 | Malhar
2 | Manish
3 | Ashutosh


# Challenges

## Get Random Event

```shell
curl -i -X GET http://localhost:4567/services/get_randomevent/
```

> The above command returns JSON structured like this:

```json
{"status": 0, "BYTES": {"value": 48, "time": "2016-04-06T19:40:42.140321"}}
]
```

### HTTP Request

`GET /services/get_randomevent`

### Url Parameters

### Data Parameters


