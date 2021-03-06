# Planning
Readme, UI markup, etc.

## MVP
Prototype (live) https://share.proto.io/6EKL8B/

## Server routes
Url | Method | Description
--- | --- | ---
\ingredients | GET | Get all ingredients

Response example
```
[
  {id: 1, ingredient: 'tomato'},
  {id: 2, ingredient: 'apple'},
  {id: 3, ingredient: 'cucumber'}
]
```

Url | Method | Description
--- | --- | ---
\ingredients | POST | Add an ingredient to an user, create a new ingredient if it does not exist

Request example
```
{
  username: 'bob',
  ingredient: 'cheese',
  qty: 5.5
}
```

Response example
```
{
  id: 5, username: 'bob', ingredient: 'cheese', qty: 5.5
}
```

Url | Method | Description
--- | --- | ---
\skills | GET | Get all skills

Response example
```
[
  {id: 1, skill: 'Chef'},
  {id: 2, skill: 'Master Chef'},
  {id: 3, skill: 'Kitchen hand'}
]
```


Url | Method | Description
--- | --- | ---
\locations | GET | Get all locations

Response example
```
[
  {id: 1, location: '22 aaa ave'},
  {id: 2, location: 'A kitchen'},
  {id: 3, location: 'The shed'}
]
```

Url | Method | Description
--- | --- | ---
\events | GET | Get all events

Response example
```
[
  {id: 1, date: 17/AUG/2017, is_am: true, description: 'a brand new day', location: '22 aaa ave', skills:[{id: 1, skill: 'Chef' }], ingredients: [{id: 1, ingredient: 'tomato'}]},
  {id: 2, date: 27/AUG/2017, is_am: true, description: 'a brand new day', location: '22 aaa ave', skills:[{id: 1, skill: 'Chef' }], ingredients: [{id: 1, ingredient: 'tomato'}]},
]
```

Url | Method | Description
--- | --- | ---
\events\:id | GET | Get an event by id

Response example
Request url: `\events\1`
```
{
  id: 1, date: 17/AUG/2017, is_am: true, description: 'a brand new day', location: '22 aaa ave', skills:[{id: 1, skill: 'Chef' }], ingredients: [{id: 1, ingredient: 'tomato'}]
}
```

Url | Method | Description
--- | --- | ---
\events\:id | POST | Edit an event by id

Request example
Request url: `\events\1`
```
{
  description: 'a brand new apple pie',
  is_confirmed: true
}
```


Response example
```
{
  id: 1, date: 17/AUG/2017, is_am: true, description: 'a brand new apple pie', location: '22 aaa ave', skills:[{id: 1, skill: 'Chef' }], ingredients: [{id: 1, ingredient: 'tomato'}], is_confirmed: true
}
```


Url | Method | Description
--- | --- | ---
\events | POST | Create a new event

Request example
```
{
  date: 17/AUG/2017, is_am: true, description: 'a brand new day', location: '22 aaa ave', skills:[{id: 1, skill: 'Chef' }], ingredients: [{id: 1, ingredient: 'tomato'}]
}
```

Response example
```
{
  id: 5, date: 17/AUG/2017, is_am: true, description: 'a brand new day', location: '22 aaa ave', skills:[{id: 1, skill: 'Chef' }], ingredients: [{id: 1, ingredient: 'tomato'}], is_confirmed: false
}
```

## Table schemas

### users table
Column names | id | username | hash | address | email | phone
--- | --- | --- | --- | --- | --- | ---
Types | Primary key | string | binary | string | string | string

### ingredients table
Column names | id | ingredient
--- | --- | --- 
Types | Primary key | string 

### skills table
Column names | id | skill
--- | --- | --- 
Types | Primary key | string 

### locations table
Column names | id | address | user_id 
--- | --- | --- |---
Types | Primary key | string | integer (foreign key to users table)

### user_ingredient table
Column names | id | user_id | ingredient_id | qty 
--- | --- | --- | --- | --- 
Types | Primary key | integer (foreign key to users table) | integer (foreign key to ingredients table) | float

### user_skill table
Column names | id | user_id | skill_id
--- | --- | --- | --- 
Types | Primary key | integer (foreign key to users table) | integer (foreign key to skill table)

### events table
Column names | id | date | is_am | location_id
--- | --- | --- | --- | --- 
Types | Primary key | datetime | boolean | integer (foreign key to locations table)

### eventinfos table
Column names | id | event_id | ingredient_id | skill_id | is_confirmed
--- | --- | --- | --- | --- | --- 
Types | Primary key | integer (foreign key to events table) | integer (foreign key to ingredients table) | integer (foreign key to skills table) | boolean 



## Roles
Carla: Scrum master
Gabe: Product owner
Annelise: Fun master
Chris: Mentor

## Learning objectives
Gabe: Auth, testing
Carla: Auth, React + Redux
Annelise: React + Redux, testing
Chris: Mentoring, CSS, testing

## Meeting minutes
![Wed initial discussion](https://github.com/SizzleDevelopers/planning/raw/master/assets/23aug2017-discussion.jpg)
![Thur discussion on tables and routes](https://github.com/SizzleDevelopers/planning/raw/master/assets/24aug2017-discussion.jpg)
