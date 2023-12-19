# Minecraft.net Marketplace view API documentation

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
## API Endpoints
| Endpoint | Description | Requirements | Status Codes |
|-|-|-|-|
`/bin/minecraft/productmanagement.productsinfobytype.json`| Returns items with the same type provided | locate, type | 200 OK, 404 Not Found
`/bin/minecraft/productmanagement.mostpopproducts.json`| Returns the current most popular item | locate | 200 OK, 404 Not Found
`/bin/minecraft/productmanagement.promotiondetails.json`| Returns the current front page items of the Marketplace | locale | 200 OK, 404 Not Found
`/bin/minecraft/productmanagement.autosuggest.json`| Returns Marketplace items based on the search term | locate | 200 OK, 404 Not Found
`/bin/minecraft/productmanagement.freeproducts.json`| Returns free Marketplace items | locate | 200 OK, 404 Not Found
`/bin/minecraft/productmanagement.filterproduct.json`| Returns free Marketplace items | locate | 200 OK, 404 Not Found
`/bin/minecraft/productmanagement.productsbydescrpition.json`| Returns free Marketplace items | locate | 200 OK, 404 Not Found
`/bin/minecraft/productmanagement.saleproducts.json`| Returns free Marketplace items | locate | 200 OK, 404 Not Found
`/bin/minecraft/productmanagement.uuiddata.json`| Returns free Marketplace items | locate | 200 OK, 404 Not Found
`/bin/minecraft/productmanagement.categorydata.json`| Returns free Marketplace items | locate, id | 200 OK, 404 Not Found
