# Info and Formatting

Shows how every file should be formatted

## [/data/main_menu.json](/data/main_menu.json)

A json object that has an ``announcements`` array in the following format:

```json
"announcements" : [
    {
        "name" : "Name of announcement",
        "description" : "Description of object.",
        "date" : "01 January 1970",
        "link" : "https://www.linkthatactivateswhenclicked.net"
    }
]
```

This object also has a ``mod_info`` object in the following format:

(Note ``latest_version_description`` and ``latest_version_release_date`` are currently unused)

```json
"mod_info" : {
    "latest_version" : "prealpha-v0.0.1",
    "latest_version_description" : "Description of latest version",
    "latest_version_release_date" : "01 January 1970"
},
```

## [/data/constants/bits_shop.json](/data/constants/bits_shop.json)

A json object that contains a ``bits_shop`` object, that has the id of each of the items that is sold in the community centre bit cost, with the associated cost in bits.

Example:

```json
"bits_shop": {
    "ITEM_ID": -1
}
```

## [/data/constants/dungeons_player_rate_pattern_strings.json](/data/constants/dungeons_player_rate_pattern_strings.json)

A json object containing both an object named ``positive_strings`` and an object named ``negative_strings``. Both of these objects contain strings in the pattern with the key being ``{player}``. These strings also contain a category, that is formatted with Title Case and with plurarilty.

Example:

```json
"positive_strings" : {
    "{player} has obtained Wither Key!" : "Keys"
},

"negative_strings" : {
    "☠️ {player} died" : "Deaths"
}
```

## [/data/constants/mathematical_hoes.json](/data/constants/mathematical_hoes.json)

An object containing an array named ``hoes`` that dictates all mathematical hoes that have are used to farm and have a function when right clicked.

Example:

```json
"hoes": [
    "ITEM_ID"
]
```

## [/data/constants/skymart_copper.json](/data/constants/skymart_copper.json)

An object containing an object named ``skymart`` containing the the id of items in the skymart that can be bought with copper, and their cost in copper

Example:

```json
"skymart" : {
    "GARDEN_SCYTHE": 20,
}
```

## [/data/constants/minion_data.json](/data/constants/minion_data.json)

A ``"minion"`` object containing an object with each minion's id and information about the minion and a ``"fuel"`` object containing information about the minion fuels. Infinite minion fuels have a ``"duration"`` of ``-1``.

Example:

```json
"minions" : {
    "COW_GENERATOR" : {
        "displayName" : "Example Cow Minion",
        "drops" : [
            "RAW_BEEF",
        ],
        "upgrades" : {
            "superCompactor" : false,
            "autoSmelter" : false,
            "compactor" : false
        },
        "maxTier" : 1,
        "cooldown" : {
            "1" : 26,
        }
    }
}

"fuel": {
    "COAL" : {
        "speed_upgrade" : 0.05,
        "duration" : 30
    },

    "PLASMA_BUCKET" : {
        "speed_upgrade" : 0.35,
        "duration" : -1
    }
}

```
