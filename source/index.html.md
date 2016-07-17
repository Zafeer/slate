---
title: Ion API Docs

language_tabs:
  - shell
---

# Introduction

Welcome to the Ion API! You can use our API to access Ion API endpoints, which can get information on various challenges, progress,rewards and recommendations in our database.

We have language bindings in Shell You can view code examples in the dark area to the right

### Sample Data:

BASE URL :: 54.85.251.3:1338

Id | Name | Email
---| -----| -------
57054e1bba521b36361aeca2 | Manish Law | manishlaw@gmail.com
57054e1bba521b36361aeca3 | Malhar Ganla | mganla@gmail.com
57054e1bba521b36361aeca4 | Ashutosh Maurya | ashutoshmaurya05@gmail.com

#Events

##Get Random Event

```shell
curl -i -X POST http://54.85.251.3:1338/services/get_randomevent
```

> The above command returns JSON structured like this:

```json
{  
   "status":0,
   "bytes":{  
      "value":48,
      "time":"2016-04-06T19:40:42.140321"
   }
}
```

### HTTP Request

`POST /services/services/get_randomevent`

### Url Parameters

### Data Parameters


##Create Event

```shell
curl -i -X POST http://54.85.251.3:1338/services/create_event/57054e1bba521b36361aeca2 -d '{"value" : 11}'
```

> The above command returns JSON structured like this:

```json
{  
   "status":0,
   "message":"Event Created Successfully",
   "bytes":[  

   ]
}

OR

{
   "status":0,
   "message":"Event Created Successfully",
   "bytes":[
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

`POST /services/services/create_event/:userId`

### Url Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------
userId |  | True | String | username of User DB. 

### Data Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------
value |  | True | Integer | Value of steps 
metric | steps  | False | String | Measurement Value

##Get Events

```shell
curl -i -X POST http://54.85.251.3:1338/services/get_events
```

> The above command returns JSON structured like this:

```json
{
  "status": 0,
  "message": "Events Fetched Successfully",
  "bytes": []
}
```

### HTTP Request

`POST /services/services/get_event`

### Url Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------

### Url Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------
username |  | True | String | username of User DB. 


#Goals

##Create Goal

```shell
curl -H "Content-Type: application/json" -d  '{}'  http://54.85.251.3:1338/services/create_goal
```

> The above command returns JSON structured like this:

```json
{
  "status": 0,
  "message": "Goal Created Successfully",
  "bytes": [
    {
      "achievement": {
        "name": "Bronze Cup",
        "icon": "",
        "text": "You have been given a bronze",
        "createdAt": "2016-07-16T10:42:28.439Z",
        "updatedAt": "2016-07-16T10:42:28.439Z",
        "id": 1
      },
      "tracking_variable": "steps",
      "type_of_goal": "S",
      "generated_by": "S",
      "condition": 100,
      "text": "Reach a target",
      "createdAt": "2016-07-16T11:07:02.827Z",
      "updatedAt": "2016-07-16T11:07:02.827Z",
      "id": 6
    }
  ]
}
```

### HTTP Request

`POST /services/services/create_goal`

### Url Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------

### Data Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------
tracking_variable |  | False | String | default='steps'.
type_of_goal | 'S'/'G' | False | Enum | default='S' Single or Group.
generated_by | 'S'/'U'  | False | Enum | default='S' System or User.
condition |  | False | String | default=100.Number of steps.
text |  | False | String | describe the goal.
achievement |  | False | String | achievement Id.


##Search Goals

```shell
curl -H "Content-Type: application/json" -d  '{}'  http://54.85.251.3:1338/services/search_goals
```

> The above command returns JSON structured like this:

```json
{
  "status": 0,
  "message": "Goals Fetched Successfully",
  "bytes": [
    {
      "achievement": {
        "name": "Bronze Cup",
        "icon": "",
        "text": "You have been given a bronze",
        "createdAt": "2016-07-16T10:42:28.439Z",
        "updatedAt": "2016-07-16T10:42:28.439Z",
        "id": 1
      },
      "tracking_variable": "steps",
      "type_of_goal": "S",
      "generated_by": "S",
      "condition": 100,
      "text": "Reach a target",
      "createdAt": "2016-07-16T11:07:02.827Z",
      "updatedAt": "2016-07-16T11:07:02.827Z",
      "id": 6
    }
  ]
}
```

### HTTP Request

`POST /services/search_goals`

### Url Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------

### Data Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------
username |  | True | String | username of User DB.



#Challenges

##Get Users To Challenge

```shell
curl -i -X POST http://54.85.251.3:1338/services/get_users_to_challenge
```

> The above command returns JSON structured like this:

```json
{
   "status":0,
   "message":"Users Sent Successfully",
   "bytes":[
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

`POST /services/get_users_to_challenge`

### Url Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------

### Data Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------
username |  | True | String | username of User DB.


##Get Challenges

```shell
curl -i -X POST http://54.85.251.3:1338/services/get_challenges
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
   "bytes":[

   ]
}

OR

{
   "status":0,
   "message":"Unfinished Challenges Fetched Successfully",
   "bytes":[
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
   "bytes":[
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

`POST /services/get_challenges`

### Url Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------

### Data Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------
username |  | True | String | username of User DB.


##Get Active Challenges

```shell
curl -i -X POST http://54.85.251.3:1338/services/get_activeChallenges
```

> The above command returns JSON structured like this:

```json

{
  "status": 0,
  "message": "Active Challenges Fetched Successfully",
  "bytes": []
}

OR


```

### HTTP Request

`POST /services/get_activeChallenges`

### Url Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------

### Data Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------
username |  | True | String | username of User DB.



##Get Challenges To Me

```shell
curl -i -X POST http://54.85.251.3:1338/services/get_challengesToMe
```

> The above command returns JSON structured like this:

```json

{
  "status": 0,
  "message": "Challenges To Me Fetched Successfully",
  "bytes": []
}

OR

{
  "status": 0,
  "message": "Challenges To Me Fetched Successfully",
  "bytes": [
    {
      "goal": {
        "tracking_variable": "steps",
        "type_of_goal": "S",
        "generated_by": "S",
        "condition": 100,
        "text": "Reach a target",
        "achievement": 1,
        "createdAt": "2016-07-16T12:33:52.239Z",
        "updatedAt": "2016-07-16T12:33:52.239Z",
        "id": 1
      },
      "status": "P",
      "accomplished": "U",
      "created_by": "zafeer",
      "createdAt": "2016-07-16T12:29:32.654Z",
      "users": [
        "zafeer",
        "manish"
      ],
      "startingAt": "2016-07-16T12:29:28.636Z",
      "expireAt": "2016-07-16T12:29:28.636Z",
      "updatedAt": "2016-07-16T12:29:32.667Z",
      "id": 2
    }
  ]
}

OR


{  
   "status":1,
   "message":"Error in Getting Challenges To Me!!",
   "bytes":""
}


```

### HTTP Request

`POST /services/get_challengesToMe`

### Url Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------

### Data Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------
username |  | True | String | username of User DB.



##Get Challenges By Me

```shell
curl -i -X POST http://54.85.251.3:1338/services/get_challengesByMe
```

> The above command returns JSON structured like this:

```json

{
  "status": 0,
  "message": "Challenges By Me Fetched Successfully",
  "bytes": []
}

OR

{
  "status": 0,
  "message": "Challenges By Me Fetched Successfully",
  "bytes": [
    {
      "goal": {
        "tracking_variable": "steps",
        "type_of_goal": "S",
        "generated_by": "S",
        "condition": 100,
        "text": "Reach a target",
        "achievement": 1,
        "createdAt": "2016-07-16T12:33:52.239Z",
        "updatedAt": "2016-07-16T12:33:52.239Z",
        "id": 1
      },
      "status": "P",
      "accomplished": "U",
      "created_by": "zafeer",
      "createdAt": "2016-07-16T12:29:32.654Z",
      "users": [
        "zafeer",
        "manish"
      ],
      "startingAt": "2016-07-16T12:29:28.636Z",
      "expireAt": "2016-07-16T12:29:28.636Z",
      "updatedAt": "2016-07-16T12:29:32.667Z",
      "id": 2
    }
  ]
}

OR


{  
   "status":1,
   "message":"Error in Getting Challenges By Me!!",
   "bytes":""
}

```

### HTTP Request

`POST /services/get_challengesByMe`

### Url Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------

### Data Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------
username |  | True | String | username of User DB.


##Update Challenge

```shell
curl -i -X POST http://54.85.251.3:1338/services/update_challenge
```

> The above command returns JSON structured like this:

```json

{
   "status":0,
   "message":"Challenge Updated Successfully",
   "bytes":[

   ]
}

```

### HTTP Request

`POST /services/update_challenge`

### Url Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------

### Data Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------
id |  | True | String | Challenge Id.
status | |True|Enum | 'A'/'R'/'P'/'F' | Accept/Reject/Pending/Finished


##Get Challenge Progress

```shell
curl -i -X POST http://54.85.251.3:1338/services/get_challenge_progress/57054e1bba521b36361aeca2/571733c73b049866bbeb7bde
```

> The above command returns JSON structured like this:

```json

{
   "status":0,
   "message":"Progress Got Successfully",
   "bytes":{
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

`POST /services/get_challenge_progress/:userId/:challenge_id`

### Url Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------
userId |  | True | String | username of User DB.
challenge_id |  | True | String | Challenge Id.




##Get Challenges History

```shell
curl -i -X POST http://54.85.251.3:1338/services/get_challengesHistory
```

> The above command returns JSON structured like this:

```json

{
  "status": 0,
  "message": "Challenges History Fetched Successfully",
  "bytes": []
}

OR

{
  "status": 0,
  "message": "Challenges History Fetched Successfully",
  "bytes": [
    {
      "goal": {
        "tracking_variable": "steps",
        "type_of_goal": "S",
        "generated_by": "S",
        "condition": 100,
        "text": "Reach a target",
        "achievement": 1,
        "createdAt": "2016-07-16T12:33:52.239Z",
        "updatedAt": "2016-07-16T12:33:52.239Z",
        "id": 1
      },
      "status": "P",
      "accomplished": "U",
      "created_by": "zafeer",
      "createdAt": "2016-07-16T12:29:32.654Z",
      "users": [
        "zafeer",
        "manish"
      ],
      "startingAt": "2016-07-16T12:29:28.636Z",
      "expireAt": "2016-07-16T12:29:28.636Z",
      "updatedAt": "2016-07-16T12:29:32.667Z",
      "id": 2
    }
  ]
}

OR


{  
   "status":1,
   "message":"Error in Getting Challenges History!!",
   "bytes":""
}


```

### HTTP Request

`POST services/get_challengesHistory`

### Url Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------

### Data Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------
username |  | True | String | username of User DB.


##Create Challenge

```shell
curl -H "Content-Type: application/json" -d  '{"users" : [] , "status":"A","accomplished":"U","goal":"1"}'  http://54.85.251.3:1338/services/create_challenge
```

> The above command returns JSON structured like this:

```json
{
   "status":0,
   "message":"Challenge Created Successfully",
   "bytes":[

   ]
}
```

### HTTP Request

`POST /services/create_challenge`

### Url Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------


### Data Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------
users |  | True | List | List of User/Users to CompeteWith
status | A/P  | False | Enum | Active or Inactive
goal |  | True | Id | Id of goal
accomplished| F/U  | False | Enum | Goal Reached or Not
createdAt| Current Time  | False | String | When is the Challenge Starting
expireAt| Expire Time  | False | String | When is the Challenge Ending


#Achievements

##Create Achievement

```shell
curl -i -X POST http://54.85.251.3:1338/services/create_achievement
```

> The above command returns JSON structured like this:

```json

{
  "status": 0,
  "message": "Achievement Created Successfully",
  "bytes": {
    "name": "Bronze Cup",
    "icon": "",
    "text": "You have been given a bronze",
    "createdAt": "2016-07-16T10:42:28.439Z",
    "updatedAt": "2016-07-16T10:42:28.439Z",
    "id": 1
  }
}

OR 

{
   "status":1,
   "message":"Error in Creating Achievement!!",
   "bytes":[]
}
```

### HTTP Request

`POST /services/get_achievements/:userId`

### Url Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------
userId |  | True | String | username of User DB.


##Get Finished Achievements

```shell
curl -H "Content-Type: application/json" -d  '{"username":"zafeer"}'  http://54.85.251.3:1338/services/get_achievements
```

> The above command returns JSON structured like this:

```json

```

### HTTP Request

`POST /services/get_achievements`

### Url Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------


### Data Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------
username |  | True | String | username of User DB.

#User

##Create User

```shell
(echo -n '{"username":"zafeer","phone":"9823218492","password":"password","image1": "'; base64 /opt/health/images/kate.jpg; echo '"}') |curl -H "Content-Type: application/json" -d  @-  http://54.85.251.3:1338/services/create_user
```

> The above command returns JSON structured like this:

```json
{
  "status": 0,
  "message": "User Created Successfully",
  "bytes": {
    "username": "zafeer",
    "phone": "9823218492",
    "createdAt": "2016-07-16T08:03:06.778Z",
    "updatedAt": "2016-07-16T08:03:06.778Z",
    "id": 1,
    "avatarUrl": "http://54.85.251.3:1338/images/avatar/zafeer.jpg"
  }
}

OR

{
  "status": 1,
  "message": "Error in Creating User",
  "bytes": {
    "status": 400,
    "summary": "Encountered an unexpected error",
    "invalidAttributes": {
      "username": [
        {
          "message": "Error.Passport.User.Exists"
        }
      ]
    }
  }
}
```

### HTTP Request

`POST /services/create_user/`

### Url Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------


### Data Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------
username |  | True | String | username.
password |  | True | String | password of user.
phone    |  | True | String | mobile no.
image1   |  | True | Base 64 Image | Base 64 Image.
weight   |  | True | String | Weight of User
height   |  | True | String | Height of User
school   |  | True | String | School of User

##Update User

```shell
curl -H "Content-Type: application/json" -d  '{"username":"zafeer","school":"St Marys"}'  http://54.85.251.3:1338/services/update_user
```

> The above command returns JSON structured like this:

```json
{
  "status": 0,
  "message": "User Updated Successfully",
  "bytes": [
    {
      "username": "zafeer",
      "phone": "9823218492",
      "createdAt": "2016-07-16T08:03:06.778Z",
      "updatedAt": "2016-07-16T09:26:11.344Z",
      "id": 1,
      "school": "St Marys",
      "avatarUrl": "http://54.85.251.3:1338/images/avatar/zafeer.jpg"
    }
  ]
}

OR

{
  "status": 1,
  "message": "User Does Not Exist"
}


```

### HTTP Request

`POST /services/update_user`

### Url Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------


### Data Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------
username |  | True | String | username of User DB to upate
variant  |  | False | variant | any other parameter accepted

##Get Profile

```shell
curl -i -X POST http://54.85.251.3:1338/services/get_profile
```

> The above command returns JSON structured like this:

```json
{
  "status": 0,
  "message": "Profile Fetched Successfully",
  "bytes": {
    "username": "zafeer",
    "phone": "9823218492",
    "createdAt": "2016-07-16T08:03:06.778Z",
    "updatedAt": "2016-07-16T10:00:01.024Z",
    "id": 1,
    "school": "St Marys",
    "steps_count": 0,
    "steps_count_quarter": {
      "prev": 0,
      "curr": 0,
      "next": 0
    },
    "rewards": [],
    "avatarUrl": "http://54.85.251.3:1338/images/avatar/zafeer.jpg"
  }
}
```

### HTTP Request

`POST /services/get_profile`

### Url Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------

### Data Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------
username |  | True | String | username of User DB.


##Check Name

```shell
curl -H "Content-Type: application/json" -d  '{"username":"zafeer"}'  http://54.85.251.3:1338/services/checkName
```

> The above command returns JSON structured like this:

```json
{
  "status": 1,
  "message": "Username already taken"
}

OR

{
  "status": 0,
  "message": "UserName Available",
  "bytes": ""
}

```

### HTTP Request

`POST /services/checkName`

### Url Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------

### Data Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------
username |  | True | String | username of User DB.




##Get Friends

```shell
curl -H "Content-Type: application/json" -d  '{"username":"zafeer"}'  http://54.85.251.3:1338/services/get_friends
```

> The above command returns JSON structured like this:

```json
{
  "status": 0,
  "message": "Friends Fetched Successfully",
  "bytes": [
    {
      "username": "manish",
      "phone": "9823218492",
      "createdAt": "2016-07-16T12:28:35.059Z",
      "updatedAt": "2016-07-16T12:28:35.059Z",
      "id": 2,
      "steps": 100,
      "avatarUrl": "http://localhost:1337/images/avatar/manish.jpg"
    }
  ]
}
```

### HTTP Request

`curl -H "Content-Type: application/json" -d  '{"username":"zafeer"}'  http://54.85.251.3:1338/services/get_friends`

### Url Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------

### Data Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------
username |  | True | String | User Name of User DB.

##Get School

```shell
curl -H "Content-Type: application/json" -d  '{"school":"Bishops School"}'  http://54.85.251.3:1338/services/getSchool
```

> The above command returns JSON structured like this:

```json
{
  "status": 0,
  "message": "Schools Fetched Successfully",
  "bytes": [
    {
      "description": "The Bishop's School, Pune, Maharashtra, India",
      "id": "b4a53363485282642239087b960906d7c00bc493",
      "matched_substrings": [
        {
          "length": 19,
          "offset": 0
        }
      ],
      "place_id": "ChIJgan_D0rAwjsRP-g3RH-Ftic",
      "reference": "CkQ7AAAAmjX84LfGhcJ7iYyq2AEtcINdvg1ggmNHSjGBO8JPVsiKdg0jjTKj48hNGAeqUtHsvcOSJC2QA_pvE61eCqLjjhIQPJadsbnsn5pOf6s6ypjyZxoU6qD5dZ1UhTbybgE37PkC6s0z99Q",
      "terms": [
        {
          "offset": 0,
          "value": "The Bishop's School"
        },
        {
          "offset": 21,
          "value": "Pune"
        },
        {
          "offset": 27,
          "value": "Maharashtra"
        },
        {
          "offset": 40,
          "value": "India"
        }
      ],
      "types": [
        "establishment"
      ]
    },
    {
      "description": "The Bishop's Co-Ed School, Pune, Maharashtra, India",
      "id": "7a39e0caca7917a97e5fd38e3f835b5c492dee60",
      "matched_substrings": [
        {
          "length": 25,
          "offset": 0
        }
      ],
      "place_id": "ChIJfWgXvBbBwjsRURn4nJvz-x8",
      "reference": "ClRBAAAA6PjEpTEB_ypVxFWucDnz3SDFTzuiY4apd7aiZUNXIzQg9PvIWtvIOTVzpwgjZF7_iV1OZPMdyaiSvA9aW2-mwl0rXoid_Da4ZWR8uiUr6BkSECAXmJKZcJQqOFImRFjgQzwaFFXNkZhRR-fqqsPhKLZpoAhvRmr_",
      "terms": [
        {
          "offset": 0,
          "value": "The Bishop's Co-Ed School"
        },
        {
          "offset": 27,
          "value": "Pune"
        },
        {
          "offset": 33,
          "value": "Maharashtra"
        },
        {
          "offset": 46,
          "value": "India"
        }
      ],
      "types": [
        "establishment"
      ]
    },
    {
      "description": "The Bishop's School Ground, General Thimayya Road, Camp, Pune, Maharashtra, India",
      "id": "db76e059533675ec8d410e29480332011b88cb17",
      "matched_substrings": [
        {
          "length": 26,
          "offset": 0
        }
      ],
      "place_id": "ChIJl-_XPkrAwjsR7tQ-ds9YySU",
      "reference": "CmRfAAAAFZ3XcyNal2ArscXBPVMDl9w3acHwZGuCC_D0ta0w3FTHvN6zjfUTs9qMwzcBd0auXFyeb3wxEvcFnHyxwW_LwGLKzbR6HZvnFGFXJNXhp1JmMS-1nDb5JM14Jms5jHtjEhAr7fJTHxkO4QXbCRz9ZqbMGhTcYUsGf9jt_wl1Yt9W1LHVp83FvQ",
      "terms": [
        {
          "offset": 0,
          "value": "The Bishop's School Ground"
        },
        {
          "offset": 28,
          "value": "General Thimayya Road"
        },
        {
          "offset": 51,
          "value": "Camp"
        },
        {
          "offset": 57,
          "value": "Pune"
        },
        {
          "offset": 63,
          "value": "Maharashtra"
        },
        {
          "offset": 76,
          "value": "India"
        }
      ],
      "types": [
        "establishment"
      ]
    },
    {
      "description": "Bishop's school ground, General Bhagat Marg, Camp, Pune, Maharashtra, India",
      "id": "f706bab1ee1244391e6146d4ae6c868a400991bc",
      "matched_substrings": [
        {
          "length": 22,
          "offset": 0
        }
      ],
      "place_id": "ChIJy7iQAjbAwjsRPzi-GHq6q04",
      "reference": "CmRZAAAARvDJZM5tFTgbgLhp2ngux30nqUNkLY8J1ZhG1q08s9Wb-DHFdxUETqcXM-NZfHkpD_vGrfKrbGVMP-v6347xGivES11R2Z8ilqMCmbp5keIGk5YmkzeNe4Icem0v3kTbEhB0MqNf8OeGlfTreo8PD4NeGhR5w88i77k_jp2lErL24wRI6z1EPQ",
      "terms": [
        {
          "offset": 0,
          "value": "Bishop's school ground"
        },
        {
          "offset": 24,
          "value": "General Bhagat Marg"
        },
        {
          "offset": 45,
          "value": "Camp"
        },
        {
          "offset": 51,
          "value": "Pune"
        },
        {
          "offset": 57,
          "value": "Maharashtra"
        },
        {
          "offset": 70,
          "value": "India"
        }
      ],
      "types": [
        "establishment"
      ]
    },
    {
      "description": "The Bishops School, Pune, Maharashtra, India",
      "id": "5184d57a3b5d705c67c17ccb66db79ebd22399d6",
      "matched_substrings": [
        {
          "length": 14,
          "offset": 4
        }
      ],
      "place_id": "ChIJaaNdAz_qwjsRTQ9iwjMm2Ac",
      "reference": "CkQ6AAAAbNAToWphs-1H31Xjv8xqZxXXUBxinnQs62yse_tLQX8wIYisnxc3YFc31eimuD5W1W5tu7tzoAmEyc1BKjx9MhIQ_C15Pht5AcUJ9o9nQvGaQhoUZ8lYoiZ3Tt1eYzS_zVJ0UugN6ck",
      "terms": [
        {
          "offset": 0,
          "value": "The Bishops School"
        },
        {
          "offset": 20,
          "value": "Pune"
        },
        {
          "offset": 26,
          "value": "Maharashtra"
        },
        {
          "offset": 39,
          "value": "India"
        }
      ],
      "types": [
        "establishment"
      ]
    }
  ]
}

OR

{
  "status": 1,
  "message": "Error in Getting Schools",
}

```

### HTTP Request

`POST /services/getSchool`

### Url Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------

### Data Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------
school |  | True | String | schoolName to search


##Get LeaderBoard

```shell
curl -H "Content-Type: application/json" -d  '{}'  http://54.85.251.3:1338/services/getLeaderBoard
```

> The above command returns JSON structured like this:

```json
{
  "status": 0,
  "message": "LeaderBoard Fetched Successfully",
  "bytes": [
    {
      "username": "zafeer",
      "phone": "9823218492",
      "createdAt": "2016-07-16T08:03:06.778Z",
      "updatedAt": "2016-07-16T10:00:01.024Z",
      "id": 1,
      "school": "St Marys",
      "steps": 100,
      "avatarUrl": "http://54.85.251.3:1338/images/avatar/zafeer.jpg"
    }
  ]
}

OR



```

### HTTP Request

`POST /services/getLeaderBoard`

### Url Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------

### Data Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------
username |  | True | String | username of User DB.

##Search Friends

```shell
curl -H "Content-Type: application/json" -d  '{"text":"zaf","type":"user"}'  http://54.85.251.3:1338/services/search_friends
curl -H "Content-Type: application/json" -d  '{"text":"St Marys","type":"school"}'  http://54.85.251.3:1338/services/search_friends
```

> The above command returns JSON structured like this:

```json
{
  "status": 0,
  "message": "Friends Fetched Successfully",
  "bytes": [
    {
      "username": "zafeer",
      "phone": "9823218492",
      "createdAt": "2016-07-16T08:03:06.778Z",
      "updatedAt": "2016-07-16T10:00:01.024Z",
      "id": 1,
      "school": "St Marys",
      "avatarUrl": "http://54.85.251.3:1338/images/avatar/zafeer.jpg"
    }
  ]
}

OR

{
  "status": 0,
  "message": "Friends Fetched Successfully",
  "bytes": []
}

```

### HTTP Request

`POST /services/search_friends`

### Url Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------

### Data Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------
text |  | True | String | username to search.
type |  | True | String | 'user' or 'school'


#Feed

##Get Feed

```shell
curl -i -X POST http://54.85.251.3:1338/services/get_feed
```

> The above command returns JSON structured like this:

```json
{
   "status":0,
   "message":"Challenges Feed Fetched Successfully",
   "bytes":[
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

`POST /services/get_feed`

### Url Parameters
Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------
username |  | True | String | username of User DB.




