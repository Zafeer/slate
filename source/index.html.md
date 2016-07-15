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
---| -----| -------
57054e1bba521b36361aeca2 | Manish Law | manishlaw@gmail.com
57054e1bba521b36361aeca3 | Malhar Ganla | mganla@gmail.com
57054e1bba521b36361aeca4 | Ashutosh Maurya | ashutoshmaurya05@gmail.com

#Events

##Get Random Event

```shell
curl -i -X GET http://54.255.165.21:2021/services/get_randomevent
```

> The above command returns JSON structured like this:

```json
{  
   "status":0,
   "BYTES":{  
      "value":48,
      "time":"2016-04-06T19:40:42.140321"
   }
}
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
{  
   "status":0,
   "message":"Event Created Successfully",
   "BYTES":[  

   ]
}

OR

{
   "status":0,
   "message":"Event Created Successfully",
   "BYTES":[
      {
         "status":"F",
         "users":[
            {
               "username":"3001128428",
               "name":"Manish Law",
               "is_active":true,
               "id":"57054e1bba521b36361aeca2",
               "created_on":"2016-04-07T17:56:00.492000",
               "last_login":"2016-04-07T12:26:45.463000",
               "email":"manishlaw@gmail.com",
               "date_joined":"2016-04-07T12:26:45.463000"
            }
         ],
         "expireAt":"9999-12-31T23:59:59.999000",
         "startingAt":"2016-04-07T17:56:00.493000",
         "created_on":"2016-04-07T17:56:00.493000",
         "created_by":{
            "username":"2001681269",
            "name":"Public User",
            "is_active":true,
            "id":"57054e1bba521b36361aeca1",
            "created_on":"2016-04-07T17:56:00.492000",
            "last_login":"2016-04-07T12:26:45.119000",
            "email":"public@gmail.com",
            "date_joined":"2016-04-07T12:26:45.129000"
         },
         "accomplished":"F",
         "goal_id":{
            "tracking_variable":"steps",
            "generated_by":"S",
            "type_of_goal":"S",
            "achievement_id":{
               "id":"570652053b0498734c62af5a",
               "name":"Bronze"
            },
            "id":"570652053b0498734c62af5d",
            "condition":100
         },
         "id":"570652053b0498734c62af60"
      }
   ]
}
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
{
   "status":0,
   "message":"Events Sent Successfully",
   "BYTES":[
      {
         "created_on":"2016-04-08T00:52:47.616000",
         "id":"5706b3873b049801a5783a90",
         "value":11
      }
   ]
}
```

### HTTP Request

`GET /services/get_events/:userId`

### Url Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------
userId |  | True | String | User Id of User DB. 

### Data Parameters



#Goals


##Search Goals

```shell
curl -i -X GET http://54.255.165.21:2021/services/search_goals/57054e1bba521b36361aeca2
```

> The above command returns JSON structured like this:

```json
{
   "status":0,
   "message":"Search Goals Successfull",
   "BYTES":[
      {
         "tracking_variable":"steps",
         "generated_by":"S",
         "type_of_goal":"S",
         "condition":100,
         "id":"5706b3553b04987ef7d88278",
         "achievement":{
            "id":"5706b3553b04987ef7d88277",
            "name":"Bronze"
         }
      },
      {
         "tracking_variable":"steps",
         "generated_by":"S",
         "type_of_goal":"S",
         "condition":500,
         "id":"5706b3553b04987ef7d88279",
         "achievement":{
            "id":"5706b3553b04987ef7d88276",
            "name":"Silver"
         }
      },
      {
         "tracking_variable":"steps",
         "generated_by":"S",
         "type_of_goal":"S",
         "condition":1000,
         "id":"5706b3553b04987ef7d8827a",
         "achievement":{
            "id":"5706b3553b04987ef7d88277",
            "name":"Bronze"
         }
      }
   ]
}
```

### HTTP Request

`GET /search_goals/:userId`

### Url Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------
userId |  | True | String | User Id of User DB.

### Data Parameters



#Challenges

##Get Users To Challenge

```shell
curl -i -X GET http://54.255.165.21:2021/services/get_users_to_challenge/57054e1bba521b36361aeca2
```

> The above command returns JSON structured like this:

```json
{
   "status":0,
   "message":"Users Sent Successfully",
   "BYTES":[
      {
         "is_active":true,
         "id":"57054e1bba521b36361aeca4",
         "created_on":"2016-04-08T01:09:01.623821",
         "last_login":"2016-04-07T19:39:10.294875+00:00",
         "email":"ashutoshmaurya05@gmail.com",
         "date_joined":"2016-04-07T19:39:10.294916+00:00"
      },
      {
         "is_active":true,
         "id":"57054e1bba521b36361aeca3",
         "created_on":"2016-04-08T01:09:01.623821",
         "last_login":"2016-04-07T19:39:10.295110+00:00",
         "email":"mganla@gmail.com",
         "date_joined":"2016-04-07T19:39:10.295145+00:00"
      },
      {
         "is_active":true,
         "id":"57054e1bba521b36361aeca1",
         "created_on":"2016-04-08T01:09:01.623821",
         "last_login":"2016-04-07T19:39:10.295326+00:00",
         "email":"public@gmail.com",
         "date_joined":"2016-04-07T19:39:10.295367+00:00"
      }
   ]
}
```

### HTTP Request

`GET /get_users_to_challenge/:userId`

### Url Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------
userId |  | True | String | User Id of User DB.


##Get Challenges

```shell
curl -i -X GET http://54.255.165.21:2021/services/get_challenges/57054e1bba521b36361aeca2
```

> The above command returns JSON structured like this:
>  status  = ( ('A', 'Active'),('F', 'Finished'),('P','Pending') )
>  accomplished  = ( ('F', 'Finished'), ('U', 'Unfinished') )
>  type_of_goal = ( ('S', 'System'),('U', 'User') )
>  generated_by = ( ('S', 'Single'),('G', 'Group') )
>  starting At = When the challenge will start
>  expireAt = When the challenge will end
>  created_by = Who has created the challenge

```json
{
   "status":0,
   "message":"Unfinished Challenges Fetched Successfully",
   "BYTES":[

   ]
}

OR

{
   "status":0,
   "message":"Unfinished Challenges Fetched Successfully",
   "BYTES":[
      {
         "status":"A",
         "users":[
            {
               "username":"2885528751",
               "name":"Manish Law",
               "is_active":true,
               "id":"57054e1bba521b36361aeca2",
               "created_on":"2016-04-08T00:51:31.932000",
               "last_login":"2016-04-07T19:21:57.145000",
               "email":"manishlaw@gmail.com",
               "date_joined":"2016-04-07T19:21:57.145000"
            }
         ],
         "expireAt":"9999-12-31T23:59:59.999000",
         "startingAt":"2016-04-08T00:51:31.933000",
         "created_on":"2016-04-08T00:51:31.933000",
         "created_by":{
            "username":"1499495072",
            "name":"Public User",
            "is_active":true,
            "id":"57054e1bba521b36361aeca1",
            "created_on":"2016-04-08T00:51:31.932000",
            "last_login":"2016-04-07T19:21:57.053000",
            "email":"public@gmail.com",
            "date_joined":"2016-04-07T19:21:57.053000"
         },
         "accomplished":"U",
         "id":"5706b3553b04987ef7d8827b",
         "goal":{
            "tracking_variable":"steps",
            "generated_by":"S",
            "type_of_goal":"S",
            "condition":100,
            "id":"5706b3553b04987ef7d88278",
            "achievement":{
               "id":"5706b3553b04987ef7d88277",
               "name":"Bronze"
            }
         }
      }
   ]
}

OR

{
   "status":0,
   "message":"Unfinished Challenges Fetched Successfully",
   "BYTES":[
      {
         "status":"A",
         "users":[
            {
               "username":"2885528751",
               "name":"Manish Law",
               "is_active":true,
               "id":"57054e1bba521b36361aeca2",
               "created_on":"2016-04-08T00:51:31.932000",
               "last_login":"2016-04-07T19:21:57.145000",
               "email":"manishlaw@gmail.com",
               "date_joined":"2016-04-07T19:21:57.145000"
            }
         ],
         "expireAt":"9999-12-31T23:59:59.999000",
         "startingAt":"2016-04-08T00:51:31.933000",
         "created_on":"2016-04-08T00:51:31.933000",
         "created_by":{
            "username":"1499495072",
            "name":"Public User",
            "is_active":true,
            "id":"57054e1bba521b36361aeca1",
            "created_on":"2016-04-08T00:51:31.932000",
            "last_login":"2016-04-07T19:21:57.053000",
            "email":"public@gmail.com",
            "date_joined":"2016-04-07T19:21:57.053000"
         },
         "accomplished":"F",
         "id":"5706b3553b04987ef7d8827b",
         "goal":{
            "tracking_variable":"steps",
            "generated_by":"S",
            "type_of_goal":"S",
            "condition":100,
            "id":"5706b3553b04987ef7d88278",
            "achievement":{
               "id":"5706b3553b04987ef7d88275",
               "name":"Gold"
            }
         }
      },
      {
         "status":"A",
         "users":[
            {
               "username":"2885528751",
               "name":"Manish Law",
               "is_active":true,
               "id":"57054e1bba521b36361aeca2",
               "created_on":"2016-04-08T00:51:31.932000",
               "last_login":"2016-04-07T19:21:57.145000",
               "email":"manishlaw@gmail.com",
               "date_joined":"2016-04-07T19:21:57.145000"
            }
         ],
         "expireAt":"9999-12-31T23:59:59.999000",
         "startingAt":"2016-04-08T01:18:50.968000",
         "created_on":"2016-04-08T01:18:43.751000",
         "created_by":{
            "username":"2885528751",
            "name":"Manish Law",
            "is_active":true,
            "id":"57054e1bba521b36361aeca2",
            "created_on":"2016-04-08T00:51:31.932000",
            "last_login":"2016-04-07T19:21:57.145000",
            "email":"manishlaw@gmail.com",
            "date_joined":"2016-04-07T19:21:57.145000"
         },
         "accomplished":"F",
         "id":"5706b9a43b04983dbb26abc2",
         "goal":{
            "tracking_variable":"steps",
            "generated_by":"S",
            "type_of_goal":"S",
            "condition":100,
            "id":"5706b3553b04987ef7d88278",
            "achievement":{
               "id":"5706b3553b04987ef7d88275",
               "name":"Gold"
            }
         }
      },
      {
         "status":"A",
         "users":[
            {
               "username":"2885528751",
               "name":"Manish Law",
               "is_active":true,
               "id":"57054e1bba521b36361aeca2",
               "created_on":"2016-04-08T00:51:31.932000",
               "last_login":"2016-04-07T19:21:57.145000",
               "email":"manishlaw@gmail.com",
               "date_joined":"2016-04-07T19:21:57.145000"
            }
         ],
         "expireAt":"9999-12-31T23:59:59.999000",
         "startingAt":"2016-04-08T01:31:01.726000",
         "created_on":"2016-04-08T01:31:01.721000",
         "created_by":{
            "username":"2885528751",
            "name":"Manish Law",
            "is_active":true,
            "id":"57054e1bba521b36361aeca2",
            "created_on":"2016-04-08T00:51:31.932000",
            "last_login":"2016-04-07T19:21:57.145000",
            "email":"manishlaw@gmail.com",
            "date_joined":"2016-04-07T19:21:57.145000"
         },
         "accomplished":"F",
         "id":"5706bc7d3b04985901510391",
         "goal":{
            "tracking_variable":"steps",
            "generated_by":"S",
            "type_of_goal":"S",
            "condition":500,
            "id":"5706b3553b04987ef7d88279",
            "achievement":{
               "id":"5706b3553b04987ef7d88276",
               "name":"Silver"
            }
         }
      }
   ]
}
```

### HTTP Request

`GET /get_challenges/:userId`

### Url Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------
userId |  | True | String | User Id of User DB.


##Get Active Challenges

```shell
curl -i -X GET http://54.255.165.21:2021/services/get_active_challenges/57054e1bba521b36361aeca2
```

> The above command returns JSON structured like this:

```json

{
   "status":0,
   "message":"Active Challenges Fetched Successfully",
   "BYTES":[

   ]
}

OR


```

### HTTP Request

`GET /get_active_challenges/:userId`

### Url Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------
userId |  | True | String | User Id of User DB.



##Get Challenges To Me

```shell
curl -i -X GET http://54.255.165.21:2021/services/get_challenges_to_me/57054e1bba521b36361aeca2
```

> The above command returns JSON structured like this:

```json

{
   "status":0,
   "message":"Challenges To Me Fetched Successfully",
   "BYTES":[

   ]
}

OR

{
   "status":0,
   "message":"Active Challenges Fetched Successfully",
   "BYTES":[
      {
         "status":"A",
         "users":[
            {
               "username":"2309331269",
               "name":"Manish Law",
               "is_active":true,
               "id":"57054e1bba521b36361aeca2",
               "created_on":"2016-04-20T13:15:57.143000",
               "last_login":"2016-04-20T07:46:15.003000",
               "email":"manishlaw@gmail.com",
               "date_joined":"2016-04-20T07:46:15.003000"
            }
         ],
         "expireAt":"9999-12-31T23:59:59.999000",
         "startingAt":"2016-04-20T13:15:57.144000",
         "created_on":"2016-04-20T13:15:57.144000",
         "created_by":{
            "username":"2099003318",
            "name":"Public User",
            "is_active":true,
            "id":"57054e1bba521b36361aeca1",
            "created_on":"2016-04-20T13:15:57.143000",
            "last_login":"2016-04-20T07:46:14.830000",
            "email":"public@gmail.com",
            "date_joined":"2016-04-20T07:46:14.831000"
         },
         "accomplished":"U",
         "id":"571733c73b049866bbeb7bde",
         "goal":{
            "tracking_variable":"steps",
            "generated_by":"S",
            "type_of_goal":"S",
            "condition":100,
            "id":"5706b3553b04987ef7d88278",
            "achievement":{
               "id":"571733c73b049866bbeb7bdb",
               "name":"Bronze"
            }
         }
      }
   ]
}

```

### HTTP Request

`GET /get_challenges_to_me/:userId`

### Url Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------
userId |  | True | String | User Id of User DB.



##Get Challenges By Me

```shell
curl -i -X GET http://54.255.165.21:2021/services/get_challenges_by_me/57054e1bba521b36361aeca2
```

> The above command returns JSON structured like this:

```json

{
   "status":0,
   "message":"Challenges By Me Fetched Successfully",
   "BYTES":[

   ]
}

OR


```

### HTTP Request

`GET /get_challenges_by_me/:userId`

### Url Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------
userId |  | True | String | User Id of User DB.


##Accept Challenge

```shell
curl -i -X GET http://54.255.165.21:2021/services/accept_challenge/57054e1bba521b36361aeca2/571733c73b049866bbeb7bde
```

> The above command returns JSON structured like this:

```json

{
   "status":0,
   "message":"Challenge Accepted Successfully",
   "BYTES":[

   ]
}

```

### HTTP Request

`GET /accept_challenge/:userId/:challenge_id`

### Url Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------
userId |  | True | String | User Id of User DB.
challenge_id |  | True | String | Challenge Id.

##Get Challenge Progress

```shell
curl -i -X GET http://54.255.165.21:2021/services/get_challenge_progress/57054e1bba521b36361aeca2/571733c73b049866bbeb7bde
```

> The above command returns JSON structured like this:

```json

{
   "status":0,
   "message":"Progress Got Successfully",
   "BYTES":{
      "challenge":{
         "status":"A",
         "users":[
            {
               "username":"2309331269",
               "name":"Manish Law",
               "is_active":true,
               "id":"57054e1bba521b36361aeca2",
               "created_on":"2016-04-20T13:15:57.143000",
               "last_login":"2016-04-20T07:46:15.003000",
               "email":"manishlaw@gmail.com",
               "date_joined":"2016-04-20T07:46:15.003000"
            }
         ],
         "expireAt":"9999-12-31T23:59:59.999000",
         "startingAt":"2016-04-20T13:15:57.144000",
         "created_on":"2016-04-20T13:15:57.144000",
         "created_by":{
            "username":"2099003318",
            "name":"Public User",
            "is_active":true,
            "id":"57054e1bba521b36361aeca1",
            "created_on":"2016-04-20T13:15:57.143000",
            "last_login":"2016-04-20T07:46:14.830000",
            "email":"public@gmail.com",
            "date_joined":"2016-04-20T07:46:14.831000"
         },
         "accomplished":"U",
         "id":"571733c73b049866bbeb7bde",
         "goal":{
            "tracking_variable":"steps",
            "generated_by":"S",
            "type_of_goal":"S",
            "condition":100,
            "id":"5706b3553b04987ef7d88278",
            "achievement":{
               "id":"571733c73b049866bbeb7bdb",
               "name":"Bronze"
            }
         }
      },
      "value":44
   }
}

```

### HTTP Request

`GET /get_challenge_progress/:userId/:challenge_id`

### Url Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------
userId |  | True | String | User Id of User DB.
challenge_id |  | True | String | Challenge Id.




##Get Challenges History

```shell
curl -i -X GET http://54.255.165.21:2021/services/get_challenges_history/57054e1bba521b36361aeca2
```

> The above command returns JSON structured like this:

```json
{
   "status":0,
   "message":"Challenges Fetched Successfully",
   "BYTES":[

   ]
}

OR

{
   "status":0,
   "message":"Challenges Fetched Successfully",
   "BYTES":[
      {
         "status":"F",
         "users":[
            {
               "username":"2885528751",
               "name":"Manish Law",
               "is_active":true,
               "id":"57054e1bba521b36361aeca2",
               "created_on":"2016-04-08T00:51:31.932000",
               "last_login":"2016-04-07T19:21:57.145000",
               "email":"manishlaw@gmail.com",
               "date_joined":"2016-04-07T19:21:57.145000"
            }
         ],
         "expireAt":"9999-12-31T23:59:59.999000",
         "startingAt":"2016-04-08T00:51:31.933000",
         "created_on":"2016-04-08T00:51:31.933000",
         "created_by":{
            "username":"1499495072",
            "name":"Public User",
            "is_active":true,
            "id":"57054e1bba521b36361aeca1",
            "created_on":"2016-04-08T00:51:31.932000",
            "last_login":"2016-04-07T19:21:57.053000",
            "email":"public@gmail.com",
            "date_joined":"2016-04-07T19:21:57.053000"
         },
         "accomplished":"F",
         "id":"5706b3553b04987ef7d8827b",
         "goal":{
            "tracking_variable":"steps",
            "generated_by":"S",
            "type_of_goal":"S",
            "condition":100,
            "id":"5706b3553b04987ef7d88278",
            "achievement":{
               "id":"5706b3553b04987ef7d88277",
               "name":"Bronze"
            }
         }
      }
   ]
}

OR

{
   "status":0,
   "message":"Challenges Fetched Successfully",
   "BYTES":[
      {
         "status":"F",
         "users":[
            {
               "username":"2885528751",
               "name":"Manish Law",
               "is_active":true,
               "id":"57054e1bba521b36361aeca2",
               "created_on":"2016-04-08T00:51:31.932000",
               "last_login":"2016-04-07T19:21:57.145000",
               "email":"manishlaw@gmail.com",
               "date_joined":"2016-04-07T19:21:57.145000"
            }
         ],
         "expireAt":"9999-12-31T23:59:59.999000",
         "startingAt":"2016-04-08T00:51:31.933000",
         "created_on":"2016-04-08T00:51:31.933000",
         "created_by":{
            "username":"1499495072",
            "name":"Public User",
            "is_active":true,
            "id":"57054e1bba521b36361aeca1",
            "created_on":"2016-04-08T00:51:31.932000",
            "last_login":"2016-04-07T19:21:57.053000",
            "email":"public@gmail.com",
            "date_joined":"2016-04-07T19:21:57.053000"
         },
         "accomplished":"F",
         "id":"5706b3553b04987ef7d8827b",
         "goal":{
            "tracking_variable":"steps",
            "generated_by":"S",
            "type_of_goal":"S",
            "condition":100,
            "id":"5706b3553b04987ef7d88278",
            "achievement":{
               "id":"5706b3553b04987ef7d88275",
               "name":"Gold"
            }
         }
      },
      {
         "status":"F",
         "users":[
            {
               "username":"2885528751",
               "name":"Manish Law",
               "is_active":true,
               "id":"57054e1bba521b36361aeca2",
               "created_on":"2016-04-08T00:51:31.932000",
               "last_login":"2016-04-07T19:21:57.145000",
               "email":"manishlaw@gmail.com",
               "date_joined":"2016-04-07T19:21:57.145000"
            }
         ],
         "expireAt":"9999-12-31T23:59:59.999000",
         "startingAt":"2016-04-08T01:18:50.968000",
         "created_on":"2016-04-08T01:18:43.751000",
         "created_by":{
            "username":"2885528751",
            "name":"Manish Law",
            "is_active":true,
            "id":"57054e1bba521b36361aeca2",
            "created_on":"2016-04-08T00:51:31.932000",
            "last_login":"2016-04-07T19:21:57.145000",
            "email":"manishlaw@gmail.com",
            "date_joined":"2016-04-07T19:21:57.145000"
         },
         "accomplished":"F",
         "id":"5706b9a43b04983dbb26abc2",
         "goal":{
            "tracking_variable":"steps",
            "generated_by":"S",
            "type_of_goal":"S",
            "condition":100,
            "id":"5706b3553b04987ef7d88278",
            "achievement":{
               "id":"5706b3553b04987ef7d88275",
               "name":"Gold"
            }
         }
      },
      {
         "status":"F",
         "users":[
            {
               "username":"2885528751",
               "name":"Manish Law",
               "is_active":true,
               "id":"57054e1bba521b36361aeca2",
               "created_on":"2016-04-08T00:51:31.932000",
               "last_login":"2016-04-07T19:21:57.145000",
               "email":"manishlaw@gmail.com",
               "date_joined":"2016-04-07T19:21:57.145000"
            }
         ],
         "expireAt":"9999-12-31T23:59:59.999000",
         "startingAt":"2016-04-08T01:31:01.726000",
         "created_on":"2016-04-08T01:31:01.721000",
         "created_by":{
            "username":"2885528751",
            "name":"Manish Law",
            "is_active":true,
            "id":"57054e1bba521b36361aeca2",
            "created_on":"2016-04-08T00:51:31.932000",
            "last_login":"2016-04-07T19:21:57.145000",
            "email":"manishlaw@gmail.com",
            "date_joined":"2016-04-07T19:21:57.145000"
         },
         "accomplished":"F",
         "id":"5706bc7d3b04985901510391",
         "goal":{
            "tracking_variable":"steps",
            "generated_by":"S",
            "type_of_goal":"S",
            "condition":500,
            "id":"5706b3553b04987ef7d88279",
            "achievement":{
               "id":"5706b3553b04987ef7d88276",
               "name":"Silver"
            }
         }
      }
   ]
}

```

### HTTP Request

`GET /get_challenges_history/:userId`

### Url Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------
userId |  | True | String | User Id of User DB.


##Create Challenges

```shell
curl -i -X POST http://54.255.165.21:2021/services/create_challenge/57054e1bba521b36361aeca2 -d '{"users" : [] , "status":"A","accomplished":"U","goal":"5706b3553b04987ef7d88278" }'

OR 

curl -i -X POST http://54.255.165.21:2021/services/create_challenge/57054e1bba521b36361aeca2 -d '{"users" : ["57050ec33b049871f5af40b7"] , "status":"A","accomplished":"U","goal":"5706b3553b04987ef7d88278","startingAt":"2016-02-07T20:26:26.763Z"  }'
```

> The above command returns JSON structured like this:

```json
{
   "status":0,
   "message":"Challenge Created Successfully",
   "BYTES":[

   ]
}
```

### HTTP Request

`POST /create_challenge/:userId`

### Url Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------
userId |  | True | String | User Id of User DB.


### Data Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------
users |  | True | List | List of User/Users to CompeteWith
status | A  | False | String | Active or Inactive
goal |  | True | Id | Id of goal
accomplished| U  | False | String | Goal Reached or Not
startingAt| Current Time  | False | String | When is the Challenge Starting
expireAt| Expire Time  | False | String | When is the Challenge Ending


#Achievements


##Get Finished Achievements

```shell
curl -i -X GET http://54.255.165.21:2021/services/get_achievements/57054e1bba521b36361aeca2
```

> The above command returns JSON structured like this:

```json
{
   "status":0,
   "message":"Achievements Fetched Successfully",
   "BYTES":[

   ]
}
OR

{
   "status":0,
   "message":"Achievements Fetched Successfully",
   "BYTES":[
      {
         "status":"F",
         "users":[
            {
               "username":"2885528751",
               "name":"Manish Law",
               "is_active":true,
               "id":"57054e1bba521b36361aeca2",
               "created_on":"2016-04-08T00:51:31.932000",
               "last_login":"2016-04-07T19:21:57.145000",
               "email":"manishlaw@gmail.com",
               "date_joined":"2016-04-07T19:21:57.145000"
            }
         ],
         "expireAt":"9999-12-31T23:59:59.999000",
         "startingAt":"2016-04-08T00:51:31.933000",
         "created_on":"2016-04-08T00:51:31.933000",
         "created_by":{
            "username":"1499495072",
            "name":"Public User",
            "is_active":true,
            "id":"57054e1bba521b36361aeca1",
            "created_on":"2016-04-08T00:51:31.932000",
            "last_login":"2016-04-07T19:21:57.053000",
            "email":"public@gmail.com",
            "date_joined":"2016-04-07T19:21:57.053000"
         },
         "accomplished":"F",
         "id":"5706b3553b04987ef7d8827b",
         "goal":{
            "tracking_variable":"steps",
            "generated_by":"S",
            "type_of_goal":"S",
            "condition":100,
            "id":"5706b3553b04987ef7d88278",
            "achievement":{
               "id":"5706b3553b04987ef7d88277",
               "name":"Bronze"
            }
         }
      }
   ]
}

```

### HTTP Request

`GET /get_achievements/:userId`

### Url Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------
userId |  | True | String | User Id of User DB.

#User

##Get Profile

```shell
curl -i -X GET http://54.255.165.21:2021/services/get_profile/57054e1bba521b36361aeca2
```

> The above command returns JSON structured like this:

```json
{
   "status":0,
   "message":"User Fetched Successfully",
   "BYTES":{
      "username":"2309331269",
      "name":"Manish Law",
      "is_active":true,
      "id":"57054e1bba521b36361aeca2",
      "created_on":"2016-04-20T13:15:57.143000",
      "last_login":"2016-04-20T07:46:15.003000",
      "email":"manishlaw@gmail.com",
      "date_joined":"2016-04-20T07:46:15.003000"
   }
}
```

### HTTP Request

`GET /get_profile/:userId`

### Url Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------
userId |  | True | String | User Id of User DB.


#Feed

##Get Feed

```shell
curl -i -X GET http://54.255.165.21:2021/services/get_feed/57054e1bba521b36361aeca2
```

> The above command returns JSON structured like this:

```json
{
   "status":0,
   "message":"Challenges Feed Fetched Successfully",
   "BYTES":[
      {
         "text":"Challenge Currently in Progress",
         "type":"challenge",
         "id":"571733c73b049866bbeb7bde"
      },
      {
         "text":"Challenge Currently in Progress",
         "type":"challenge",
         "id":"5719debf3b04984bc6984e07"
      }
   ]
}
```

### HTTP Request

`GET /get_feed/:userId`

### Url Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------
userId |  | True | String | User Id of User DB.




