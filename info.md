# Info and Formatting

Shows how every file should be formatted

## /data/main_menu.json

A json object that has an ``announcements`` array in the following format:

```
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

```
"mod_info" : {
    "latest_version" : "prealpha-v0.0.1",
    "latest_version_description" : "Description of latest version",
    "latest_version_release_date" : "01 January 1970"
},
```

## /data/constants/bits_shop.json

A json object that contains a ``bits_shop`` object, that has the id of each of the items that is sold in the community centre bit cost, with the associated cost in bits.

Example: 

```
"bits_shop": {
    "ITEM_ID": -1
}
```

## /data/constants/dungeons_player_rate_pattern.json

A json object containing both an object named ``positive_strings`` and an object named ``negative_strings``. Both of these objects contain strings in the pattern with the key being ``{player}``. These strings also contain a category, that is formatted with Title Case and with plurarilty. 

Example:

```
"positive_strings" : {
    "{player} has obtained Wither Key!" : "Keys"
},

"negative_strings" : {
    "☠️ {player} died" : "Deaths"
}
```

## /data/constants/mathematical_hoes.json

An object containing an array named ``hoes`` that dictates all mathematical hoes that have are used to farm and have a function when right clicked.

Example: 

```
"hoes": [
    "ITEM_ID"
]
```

## /data/constants/skymart_copper.json

An object containing an object named ``skymart`` containing the the id of items in the skymart that can be bought with copper, and their cost in copper

Example: 

```
"skymart" : {
    "GARDEN_SCYTHE": 20,
}
```
