# GamePortalAPIs

These are APIs for a game portal.

Run `npm install` to install all required packages

Run `npm start` to start running.

APIs will return JSON as a response.

---

**Managing Game Entities** `/games`

**List all games**

Request URL: `localhost:3000/games`

Request type: `GET`

**List one game**

Request URL: `localhost:3000/games/:gameId`

Request type: `GET`

**Create a new game entity**

Request URL: `localhost:3000/games`

Request type: `POST`

Request body:
```
{
    "title": "String",
    "firstLoginBonusCoin": "String",
    "firstLoginBonusStar": "String"
}
```

**Edit game details**

Request URL: `localhost:3000/games/:gameId`

Request type: `PATCH`

Request body:
```
[
    {
        "propName": "FIELD_TO_EDIT",
        "value": "VALUE_TO_EDIT"
    }
]
```

**Remove a game entity**

Request URL: `localhost:3000/games/:gameId`

Request type: `DELETE`

---

**Managing Event Entities** `events`

**List all events**

Request URL: `localhost:3000/events`

Request type: `GET`

**List one event**

Request URL: `localhost:3000/events/:eventId`

Request type: `GET`

**List all events from one game**

Request URL: `localhost:3000/events/onegameallevents/:gameId`

Request type: `GET`

**Create a new event entity**

Request URL: `localhost:3000/events`

Request type: `POST`

Request body:
```
{
    "title": "String",
    "eventStart": "String",
    "eventEnd": "String",
    "starReward": "Number",
    "gameId": "String"
}
```
The `eventStart` and `eventEnd` fields are input as HH:mm:ss DD-MM-YYYY UTC +0 format but keep as unix time stamp in the system

**Edit event details**

Request URL: `localhost:3000/events/:eventId`

Request type: `PATCH`

Request body:
```
[
    {
        "propName": "FIELD_TO_EDIT",
        "value": "VALUE_TO_EDIT"
    }
]
```

**Remove a event entity**

Request URL: `localhost:3000/events/:eventId`

Request type: `DELETE`

---

**Managing Profile Entities** `/profiles`

**List all profiles**

Request URL: `localhost:3000/profiles`

Request type: `GET`

**List one profile**

Request URL: `localhost:3000/profiles/:profileId`

Request type: `GET`

**List one profile informations for a specific game**

Request URL: `localhost:3000/profiles/profileforspecificgame/:gameId/:profileId`

Request type: `GET`

**Create a new profile entity**

Request URL: `localhost:3000/profiles`

Request type: `POST`

Request body:
```
{
    "fullName": "String",
    "recentLogin": "String", 
    "profileCoins": "Number",
    "profileStars": "Number",
    "gameId": ["String","String","..."]
}
```
The `recentLogin` field is input as HH:mm:ss DD-MM-YYYY UTC +0 format but keeps as unix time stamp in the system


**Edit a profile detail**

Request URL: `localhost:3000/profiles/:profileId`

Request type: `PATCH`

Request body:
```
[
    {
        "propName": "FIELD_TO_EDIT",
        "value": "VALUE_TO_EDIT"
    }
]
```

**Edit a profile detail from a specific game**

Request URL: `localhost:3000/profileforspecificgame/:gameId/:profileId`

Request type: `PATCH`

Request body:
```
[
    {
        "propName": "FIELD_TO_EDIT",
        "value": "VALUE_TO_EDIT"
    }
]
```

**Player get reward from an event**

Request URL: `localhost:3000/getEventRewards/:profileId/:eventId`

Request type: `PATCH`

No request body is needed

**Remove a profile entity**

Request URL: `localhost:3000/profiles/:profileId`

Request type: `DELETE`