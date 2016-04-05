---
title: Ion API Docs

language_tabs:
  - shell
  - javascript
  - python

toc_footers:

includes:
  - errors

search: true
---

# Introduction

Welcome to the Ion API! You can use our API to access Ion API endpoints, which can get information on various challenges, progress,rewards and recommendations in our database.

We have language bindings in Shell, Java, and Python! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

### Sample Data:

Id | Name
--------- | -----------
1 | Malhar
2 | Manish
3 | Ashutosh


# Challenges

## Add or Update User

```javascript
 $.ajax({
    url: "/add_or_update_user/1",
    dataType: "json",
    type : "POST",
    success : function(r) {
    }
  });
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

`POST /add_or_update_user/:userId`

### Url Parameters

Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------
userId |  | False | String | User Id of User DB. If userId is blank creates new user else takes the user according to id


### Data Parameters

Parameter | Default | Required | Type | Description
--------- | ------- | -------- | ---- | -----------
lat |  | False | Float | Latitude of User for geo targeting
lon |  | False | Float | Longitude of User for geo targeting
country |  | False | String | Country of User
city |  | False | String | City of User
region |  | False | String | Region of User
friends |  | False | List of user Ids | Friends of User
groups |  | False | List of group Ids | Groups of User

<aside class="success">
Content: { "achievements": {}, "achievement_errors": {} } \n
OR \n
Content:{
  "achievements": {
    "1": {
      "levels_achieved": {
        "1": "2016-04-02T12:10:52.901076"
      },
      "achievementcategory": "",
      "level": 1,
      "new_levels": {
        "1": {
          "rewards": {},
          "properties": {},
          "level": 1
        }
      },
      "internal_name": "invite_users",
      "hidden": false,
      "maxlevel": 1,
      "id": 1
    }
  },
  "achievement_errors": {}
}
</aside>
