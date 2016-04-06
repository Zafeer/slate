---
title: Ion API Docs

language_tabs:
  - shell
---

# Introduction

Welcome to the Ion API! You can use our API to access Ion API endpoints, which can get information on various challenges, progress,rewards and recommendations in our database.

We have language bindings in Shell You can view code examples in the dark area to the right

### Sample Data:

BASE URL :: 54.255.165.21:2021

Id | Name | Email
--------- | -----------
57054e1bba521b36361aeca2 | Manish Law | manishlaw@gmail.com
57054e1bba521b36361aeca3 | Malhar Ganla | mganla@gmail.com
57054e1bba521b36361aeca4 | Ashutosh Maurya | ashutoshmaurya05@gmail.com

#Events

##Get Random Event

```shell
curl -i -X GET http://54.255.165.21:2021/services/get_randomevent/
```

> The above command returns JSON structured like this:

```json
{"status": 0, "BYTES": {"value": 48, "time": "2016-04-06T19:40:42.140321"}}
```

### HTTP Request

`GET /services/get_randomevent`

### Url Parameters

### Data Parameters

##Create Event

```shell
curl -i -X POST http://54.255.165.21:2021/services/create_event/57054e1bba521b36361aeca2 -d '{"value" : 11}'
```

> The above command returns JSON structured like this:

```json
{"status": 0, "BYTES": {"value": 48, "time": "2016-04-06T19:40:42.140321"}}
```

### HTTP Request

`POST /services/create_event/:userId`

### Url Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------
userId |  | True | String | User Id of User DB. 

### Data Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------
value |  | True | Integer | Value of steps 
metric | steps  | False | String | Measurement Value

##Get Events

```shell
curl -i -X GET http://54.255.165.21:2021/services/get_events/57054e1bba521b36361aeca2
```

> The above command returns JSON structured like this:

```json
{"status": 0, "message": "Events Sent Successfully", "BYTES": "[{\"created_on\": {\"$date\": 1459986752771}, \"value\": 11}]"}
```

### HTTP Request

`GET /services/get_events/:userId`

### Url Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------
userId |  | True | String | User Id of User DB. 

### Data Parameters




