T4G-API-Wrapper
===============

A PHP Wrapper for the Tools4Games API

Examples are in test.php

You need to create an API Key @ http://blacklist.tools4games.com

```php
$api = new API;
$api->auth('api_key', 'api_secret');

$test = $api->getBlacklist(); // <- Get the Blacklist Section of the API (Currently the only one)
$test = $test->getServer(['serverId' => 16]); // <- Get the Server, either by serverId or bookmarkLink
$test = $test->events(); // <- Fetches the Server Events
$test = $test->status(); // <- Fetches the Server Status
$test = $test->players(); // <- Fetches the Server Players
$test = $test->chat(); // <- Fetches the Server Chat
$test = $test->kicklog(); // <- Fetches the Server Kicklog

$test = $text->execute(); // <- Execute the Command and return the Response as PHP Object
```

Example Response:
```javascript
{
    "success": true,
    "info": {
        "hoster": "leetservers",
        "country": "DE",
        "bookmarkLink": "17a6ef60-3da2-4b77-b31f-9f4751622a75",
        "online": true,
        "disabled": false,
        "noLogin": false,
        "pbucon": {
            "enabled": true,
            "lastHeartbeat": "05.05.2014 20:21:42",
            "tick": {
                "period": 300,
                "type": "seconds"
            }
        },
        "backend": {
            "duration": "0.093081",
            "lastHeartbeat": "05.05.2014 20:25:13",
            "tick": {
                "period": 1,
                "type": "seconds"
            }
        },
        "blacklist": {
            "blacklists": [
                {
                    "blacklistId": "1",
                    "kicks": "3340",
                    "label": "Cheating"
                },
                ...
            ],
            "whitelist": [

            ]
        }
    },
    "status": {
        "name": "P4F Tools #2 - Sharqi Rush (NO SHOTGUNS) \/ Leetservers",
        "map": "sharqi",
        "gameMode": "gpm_rush",
        "players": {
            "current": "27",
            "max": "32",
            "joining": "1"
        },
        "tickets": {
            "RU": "24",
            "US": "-9899"
        },
        "time": {
            "elapsed": "127",
            "remaining": "-1"
        }
    },
    "chat": [
        {
            "hash": "4c7038e530fbb72ba631a3b9260416bfac45f031",
            "origin": "hallo????",
            "type": "Global",
            "time": "1399314212",
            "message": "hacker",
            "index": "11"
        },
        ...
    ],
    "players": [
        {
            "index": "5",
            "team": "RU",
            "ping": "148",
            "connected": "1",
            "alive": "1",
            "manDown": "0",
            "profileId": "808581318",
            "suicide": "0",
            "timeToSpawn": "0",
            "score": "600",
            "nucleusId": "2807858490",
            "vip": "0",
            "kills": "3",
            "deaths": "0",
            "suicides": "0",
            "revives": "0",
            "damageAssists": "0",
            "passengerAssists": "0",
            "targetAssists": "0",
            "cpCaptures": "0",
            "cpDefends": "0",
            "cpAssists": "0",
            "cpNeutralizes": "0",
            "cpNeutralizeAssists": "0",
            "joined": "1399314052",
            "playingFor": 262,
            "soldiers": [
                {
                    "kit": "1",
                    "level": "0",
                    "name": "ACO78"
                },
                {
                    "kit": "0",
                    "level": "25",
                    "name": "AS78"
                }
            ]
        },
        ...
    ],
    "events": [
        {
            "date": "1399314310",
            "profileId": "497184881",
            "event": "damageAssist"
        },
        {
            "date": "1399314310",
            "profileId": "517588597",
            "event": "death"
        },
        ...
    ],
    "kicklog": [
        {
            "soldierId": "820131201",
            "name": "azefdf",
            "nucleusId": "2815327564",
            "date": "1399309656",
            "ban": {
                "type": "Cheating",
                "since": "1366228383"
            }
        },
        ...
    ]
}
