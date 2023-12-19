# Minecraft.net Marketplace view API documentation

## API Endpoints

All requests are GET requests.
| Endpoint | Description | Requirements | Status Codes |
|-|-|-|-|
`/bin/minecraft/productmanagement.productsinfobytype.json`| Returns items with the same type provided | locate, type | 200 OK, 404 Not Found
`/bin/minecraft/productmanagement.mostpopproducts.json`| Returns the current most popular item | locate | 200 OK, 404 Not Found
`/bin/minecraft/productmanagement.promotiondetails.json`| Returns the current front page items of the Marketplace | locale | 200 OK, 404 Not Found
`/bin/minecraft/productmanagement.autosuggest.json`| Returns Marketplace items based on the search term | locate, term (not required but always null if not there) | 200 OK, 404 Not Found
`/bin/minecraft/productmanagement.freeproducts.json`| Returns free Marketplace items | locate | 200 OK, 404 Not Found
`/bin/minecraft/productmanagement.productsbydescrpition.json`| Returns Marketplace items based on the search term (description based) | locate, term (not required but always null if not there) | 200 OK, 404 Not Found
`/bin/minecraft/productmanagement.uuiddata.json`| Returns an item based an uuid from packIdentity | locate, uuid (uuid from the packIdentity property), type (required but can set to anything) | 200 OK, 404 Not Found
`/bin/minecraft/productmanagement.filterproduct.json`| Unknown | locate, creatorId (search term) | 200 OK, 404 Not Found
`/bin/minecraft/productmanagement.saleproducts.json`| Unknown | locate, id (promotion ID) | 200 OK, 404 Not Found
`/bin/minecraft/productmanagement.categorydata.json`| Unknown | locate, id, category | 200 OK, 404 Not Found

### Query Strings

- **locale** (Area code)

- **type** (Item type)

- **limit** (Number of items to view | the number of items are one less than the input | defaults to 10)

- **skip** (Skip the first items | defaults to 0)

- **currentDate** (ISO date format)

- **term** (Search term | defaults to null)

### Possible types

- **all** (Most Popular)
- **resourcepack** (Texture Packs)
- **mashup** (Mash-ups)
- **skinpack** (Skin Packs)
- **mini_game_world** (Mini Games)
- **adventure_world** (Adventure Maps)
- **survival_spawn_world** (Survival Spawns)
- **bundle** (Bundles)
- **genre.educational** (Educational content)

### Examples

Shows the first 99 skin packs:
<https://www.minecraft.net/bin/minecraft/productmanagement.productsinfobytype.json?type=skinpack&locale=en-us&limit=100&skip=0>

Shows the first 119 items and doesnt show the first 20:
<https://www.minecraft.net/bin/minecraft/productmanagement.productsinfobytype.json?type=skinpack&locale=en-us&limit=100&skip=20>

Current front page:
<https://www.minecraft.net/bin/minecraft/productmanagement.promotiondetails.json?locale=en-us>
