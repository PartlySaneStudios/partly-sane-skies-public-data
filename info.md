# Info and Formatting

Shows how every file should be formatted

## [/data/](/data/)

### [/data/main_menu.json](/data/main_menu.json)

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
If you don't know how to update the list, consider watching this [video](https://1drv.ms/v/s!AuWyYgAuSoGDgqZv9dlJPpc8CL1A_A?e=fkeK57).

Please note that there will always be a max amount of 2 accouncements at any time. The upper announcement is always the newest patch, while the lower annoucement is the newest, big update (for example: 1.19.0 Update). If the newest announcement happens to be a big one, it will be put as the upper announcement, while the newest patch is now second in the list.


This object has a ``mod_info`` object in the following format:

(Note ``latest_version_description`` and ``latest_version_release_date`` are currently unused)

```json
"mod_info" : {
    "latest_version" : "prealpha-v0.0.1",
    "latest_version_description" : "Description of latest version",
    "latest_version_release_date" : "01 January 1970",

    "discord_invite_full": "https://discord.gg/v4PU3WeH7z",
    "discord_invite_short_link": "discord.gg/v4PU3WeH7z",
    "discord_invite_code": "v4PU3WeH7z"
},
```

This object has a ``prank_sound`` boolean,
it's a kill switch for the sound prank feature, incase something goes wrong.

Format:

```json
"prank_sound": false,
```

This object has a ``prerelease_channel`` object which contains the exact same format as the first half of the ``mod_info`` object but is updated with the latest version from the prerelease channel 

(Note ``latest_version_description`` and ``latest_version_release_date`` are currently unused. You are also required to update the latest release version in the prerelease channel)


### [/data/mods.json](/data/constants/mods.json)

A ``"mods"`` object containing an object with the mod id. The mod object has a ``name`` field which has a display name for the mod, the ``download`` field which has a the download link for the mod, a ``"versions"`` object containing the version as the key and the file sha as the value. The ``betaVersions`` object is the same, except it is for the beta channel.
You can use ``/modchecker`` ingame and paste the data automatically copied to your clipboard into a file to see unknown mods or versions.

Example:

```json
"partlysaneskies": {
            "name": "Partly Sane Skies",
            "download": "https://github.com/PartlySaneStudios/partly-sane-skies/",
            "versions": {
                "beta-v0.4.1": "89f33940388058bf3d68b110188bb6fea9fc158e74654e7e6db857df6238867c",
            },
            "betaVersions": {
                "beta-v0.4.1": "89f33940388058bf3d68b110188bb6fea9fc158e74654e7e6db857df6238867c",
            }
        },
```

## [/data/constants/](/data/constants/)


### [/data/constants/bits_shop.json](/data/constants/bits_shop.json)

A json object that contains a ``bits_shop`` object, that has the id of each of the items that is sold in the community centre bit cost, with the associated cost in bits.

Example:

```json
"bits_shop": {
    "ITEM_ID": -1
}
```


### [/data/constants/dungeons_player_rate_pattern_strings.json](/data/constants/dungeons_player_rate_pattern_strings.json)

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

### [/data/constants/mathematical_hoes.json](/data/constants/mathematical_hoes.json)

An object containing an array named ``hoes`` that dictates all mathematical hoes that have are used to farm and have a function when right clicked.

Example:

```json
"hoes": [
    "ITEM_ID"
]
```


### [/data/constants/minion_data.json](/data/constants/minion_data.json)

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

"fuels": {
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


### [/data/constants/skymart_copper.json](/data/constants/skymart_copper.json)

An object containing an object named ``skymart`` containing the the id of items in the skymart that can be bought with copper, and their cost in copper

Example:

```json
"skymart" : {
    "GARDEN_SCYTHE": 20,
}
```

## [/data/constants/sanity_check_data.json](/data/constants/sanity_check_data.json)

A ``"sanity_check_data"`` object containing the values necessary to perform a(n ultimately) silly sanity check on a player's profile. Currently remains dormant until the Hypixel API v2 transition is fully finished.

More data points may be added later on; please try to keep them as ints/longs.

Example:

```json
{
  "highestnwlong": 360567766418,
  "oldestprofileunixlong": 1560276201428
}
```

## [/data/constants/booster_cookie_price.json](/data/constants/booster_cookie_price.json)

A ``"booster_cookie_price"`` object contains the values necessary to "convert" SkyBlock coins into various currencies of IRL cash via the ``/coins2cookies`` command from PSS in-game solely for educational purposes. Much of this data is based off of what's on store.hypixel.net.

The nested ``"ingame"`` and ``"storehypixelnet"`` objects are meant to store various constants, from the cost of gems per batch of booster cookies to the IRL price of the smallest SkyBlock gem bundle to the currencies supported by store.hypixel.net.

In the unlikely event that Hypixel adds currencies to their store, please *append* to:
- The ``"order"`` array (containing three letter abbreviations of currencies as strings)
_ The nested ``"currencysymbols"`` object (containing the IRL cost of the 675 gems bundle in each currency before discounts, taxes, or othern fees)
- The nested ``"currencysymbols"`` object (containing the [Minecraft-supported] currency symbol as strings)
- The nested ``"currencysymbolsprecedes"`` object (containing whether the currency symbol should be placed before or after the monetary value as booleans)

An abridged example of the object is provided below.

Example:
```json
{
  "ingame": {
    "onecookiegem": 325,
    "sixcookiesgem": 1950,
    "twelvecookiesgem": 3900
  },
  "storehypixelnet": {
    "baseurl": "https://store.hypixel.net/category/skyblock-gems?currency=",
    "smallestgembundle": 675,
    "order": [
      "AUD"
    ],
    "AUD": 7.87
  },
  "currencysymbols": {
    "AUD": "AU$"
  },
  "currencysymbolprecedes": {
    "AUD": true
  }
}
```
