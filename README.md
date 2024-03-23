# Minecraft.net Marketplace view API documentation

## API Endpoints

➡️ **All requests are GET requests.**

➡️ **The user-agent header is REQUIRED. The minimal is browser/version for example, "Firefox/86".**

| Endpoint | Description | Requirements | Status Codes |
|-|-|-|-|
`/bin/minecraft/productmanagement.productdetails.json`| Returns the item details of the provided item id | id (Item ID) | 200 OK, 404 Not Found
`/bin/minecraft/productmanagement.autosuggest.json`| Returns Marketplace items based on the search term | locate, term (Not required but always null if not there) | 200 OK, 404 Not Found
`/bin/minecraft/productmanagement.productsinfobytype.json`| Returns items with the same type provided | locate, type | 200 OK, 404 Not Found
`/bin/minecraft/productmanagement.productsbydescrpition.json`| (They misspelled description) Returns Marketplace items based on the search term, description based | locate, term (not required but always null if not there), limit (If no limit, the request returns the same item everytime) | 200 OK, 404 Not Found
`/bin/minecraft/productmanagement.uuiddata.json`| Returns an item based an uuid from packIdentity | locate, uuid (UUID from the packIdentity property), type (Required, but can be set to any value without affecting the result) | 200 OK, 404 Not Found
`/bin/minecraft/productmanagement.categorydata.json`| Returns all of the items from a specific category | locate, category | 200 OK, 404 Not Found
`/bin/minecraft/productmanagement.filterproduct.json`| Shows all the items for a specific creator | locate, creatorId (Creator name), limit, skip | 200 OK, 404 Not Found, 500 Invalid Input
`/bin/minecraft/productmanagement.promotiondetails.json`| Returns the current front page items of the Marketplace | locale | 200 OK, 404 Not Found
`/bin/minecraft/productmanagement.mostpopproducts.json`| Returns the current most popular item | locate | 200 OK, 404 Not Found
`/bin/minecraft/productmanagement.freeproducts.json`| Returns free Marketplace items | locate | 200 OK, 404 Not Found
`/bin/minecraft/productmanagement.saleproducts.json`| (Disabled) Shows the current active sales | locate, id (Has to be an array, promotion ID/ETag property) | 200 OK, 404 Not Found, 500 Invalid Input

### Query Strings

- **locale** (Area code)

- **type** (Item type)

- **limit** (Number of items to view | The number of items are one less than the input | Defaults to 10 or 4 depending on the endpoint)

- **skip** (Skip the first items | Defaults to 0)

- **currentDate** (ISO date format)

- **term** (Search term | Defaults to "null")

### Possible Types

- **all** (Most Popular)
- **resourcepack** (Texture Packs)
- **addon** (Add-ons)
- **mashup** (Mash-ups)
- **skinpack** (Skin Packs)
- **mini_game_world** (Mini Games)
- **adventure_world** (Adventure Maps)
- **survival_spawn_world** (Survival Spawns)
- **bundle** (Bundles)
- **genre.educational** (Educational content)

### Possible Categories

- **Most Popular Minecraft Skins**
- **Most Popular Minecraft Resources**
- **Most Popular Minecraft Add-ons**
- **Most Popular Minecraft Mash-ups**
- **Most Popular Adventure**
- **Most Popular Minigames**
- **Most Popular Survival Spawn**

### Examples

**Get item details:**
<https://www.minecraft.net/bin/minecraft/productmanagement.productdetails.json?id=8500d60c-bf43-48dd-b6e9-a97cb35e41f8>

**Search:**
<https://www.minecraft.net/bin/minecraft/productmanagement.autosuggest.json?locale=en-us&term=help>

**Search by description:**
<https://www.minecraft.net/bin/minecraft/productmanagement.productsbydescrpition.json?locale=en-us&term=help&limit=10>

**Creator search:**
<https://www.minecraft.net/bin/minecraft/productmanagement.filterproduct.json?limit=10&creatorId=Yeggs&locale=en-us&skip=0>

**Shows the first 99 skin packs:**
<https://www.minecraft.net/bin/minecraft/productmanagement.productsinfobytype.json?type=skinpack&locale=en-us&limit=100&skip=0>

**Shows the first 119 items and doesnt show the first 20:**
<https://www.minecraft.net/bin/minecraft/productmanagement.productsinfobytype.json?type=skinpack&locale=en-us&limit=100&skip=20>

**Category search:**
<https://www.minecraft.net/bin/minecraft/productmanagement.categorydata.json?locale=en-us&category=Most%20Popular%20Minecraft%20Skins>

**Current front page:**
<https://www.minecraft.net/bin/minecraft/productmanagement.promotiondetails.json?locale=en-us>

**Free items:**
<https://www.minecraft.net/bin/minecraft/productmanagement.freeproducts.json?locale=en-us&limit=25>
