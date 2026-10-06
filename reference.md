# Reference
## Marketplace
<details><summary><code>client.Marketplace.GetMarketplace() -> *marketsdk.MarketplaceObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Settings are changed in the dashboard, separately for test and live.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
client.Marketplace.GetMarketplace(
    context.TODO(),
)
```
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Sellers
<details><summary><code>client.Sellers.ListSellers() -> *marketsdk.SellerList</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.ListSellersRequest{}
client.Sellers.ListSellers(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**limit:** `*float64` 
    
</dd>
</dl>

<dl>
<dd>

**startingAfter:** `*string` — The `next_cursor` of the previous page.
    
</dd>
</dl>

<dl>
<dd>

**externalID:** `*string` — Find the seller with this external id.
    
</dd>
</dl>

<dl>
<dd>

**status:** `*marketsdk.ListSellersRequestStatus` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Sellers.CreateSeller(request) -> *marketsdk.SellerObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.CreatePartyDto{
    ExternalID: "external_id",
}
client.Sellers.CreateSeller(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `*marketsdk.CreatePartyDto` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Sellers.GetSeller(ID) -> *marketsdk.SellerObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.GetSellerRequest{
    ID: "id",
}
client.Sellers.GetSeller(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Sellers.EraseSeller(ID) -> *marketsdk.SellerObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Removes the name, external id, metadata, storefront, and review text, and takes the listings down. Orders and reputation stay, without personal data.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.EraseSellerRequest{
    ID: "id",
}
client.Sellers.EraseSeller(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Sellers.UpdateSeller(ID, request) -> *marketsdk.SellerObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.UpdateSellerRequest{
    ID: "id",
    Body: &marketsdk.UpdatePartyDto{},
}
client.Sellers.UpdateSeller(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**request:** `*marketsdk.UpdatePartyDto` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Sellers.PutStorefront(ID, request) -> *marketsdk.StorefrontObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.StorefrontDto{
    ID: "id",
    Name: "name",
    Slug: "jane-templates",
}
client.Sellers.PutStorefront(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**name:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**slug:** `string` — Lowercase letters, digits, and hyphens. Unique per marketplace.
    
</dd>
</dl>

<dl>
<dd>

**description:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**metadata:** `map[string]string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Sellers.CreateOnboardingLink(ID, request) -> *marketsdk.OnboardingLinkObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

The first link creates the seller's connected account on your Stripe account: Express, with Stripe collecting what the law requires, your platform paying Stripe's fees and bearing losses, and only transfers requested. Send the seller to the link; their payouts status follows as Stripe reports it.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.OnboardingLinkDto{
    ID: "id",
    ReturnURL: "return_url",
    RefreshURL: "refresh_url",
}
client.Sellers.CreateOnboardingLink(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**returnURL:** `string` — Where Stripe sends the seller when they finish or leave onboarding.
    
</dd>
</dl>

<dl>
<dd>

**refreshURL:** `string` — Where Stripe sends the seller if the link expired. Create a new link there.
    
</dd>
</dl>

<dl>
<dd>

**country:** `*string` — The seller's country, two letters. Used only when the seller's Stripe account is created, on the first link. Defaults to your Stripe account's country.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Sellers.GetSellerProfile(ID) -> *marketsdk.SellerProfileObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Callable with a publishable key. Shows only what a buyer may see.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.GetSellerProfileRequest{
    ID: "id",
}
client.Sellers.GetSellerProfile(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Buyers
<details><summary><code>client.Buyers.ListBuyers() -> *marketsdk.BuyerList</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.ListBuyersRequest{}
client.Buyers.ListBuyers(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**limit:** `*float64` 
    
</dd>
</dl>

<dl>
<dd>

**startingAfter:** `*string` — The `next_cursor` of the previous page.
    
</dd>
</dl>

<dl>
<dd>

**externalID:** `*string` — Find the buyer with this external id.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Buyers.CreateBuyer(request) -> *marketsdk.BuyerObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.CreatePartyDto{
    ExternalID: "external_id",
}
client.Buyers.CreateBuyer(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `*marketsdk.CreatePartyDto` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Buyers.GetBuyer(ID) -> *marketsdk.BuyerObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.GetBuyerRequest{
    ID: "id",
}
client.Buyers.GetBuyer(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Buyers.EraseBuyer(ID) -> *marketsdk.BuyerObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.EraseBuyerRequest{
    ID: "id",
}
client.Buyers.EraseBuyer(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Buyers.UpdateBuyer(ID, request) -> *marketsdk.BuyerObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.UpdateBuyerRequest{
    ID: "id",
    Body: &marketsdk.UpdatePartyDto{},
}
client.Buyers.UpdateBuyer(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**request:** `*marketsdk.UpdatePartyDto` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Categories
<details><summary><code>client.Categories.ListCategories() -> *marketsdk.CategoryList</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.ListCategoriesRequest{}
client.Categories.ListCategories(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**limit:** `*float64` 
    
</dd>
</dl>

<dl>
<dd>

**startingAfter:** `*string` — The `next_cursor` of the previous page.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Categories.CreateCategory(request) -> *marketsdk.CategoryObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.CreateCategoryDto{
    Key: "ui-kits",
    Name: "name",
}
client.Categories.CreateCategory(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**key:** `string` — Your key for the category. Unique per marketplace.
    
</dd>
</dl>

<dl>
<dd>

**name:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**description:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**parent:** `*string` — Another category of this marketplace.
    
</dd>
</dl>

<dl>
<dd>

**attributeSchema:** `*marketsdk.AttributeSchemaObject` 
    
</dd>
</dl>

<dl>
<dd>

**fee:** `*marketsdk.CategoryFeeDto` — Overrides the marketplace's platform fee for listings in this category. Null uses the marketplace fee.
    
</dd>
</dl>

<dl>
<dd>

**prohibited:** `*bool` — Listings in a prohibited category cannot be published (section 9.4).
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Categories.GetCategory(ID) -> *marketsdk.CategoryObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.GetCategoryRequest{
    ID: "id",
}
client.Categories.GetCategory(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Categories.UpdateCategory(ID, request) -> *marketsdk.CategoryObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.UpdateCategoryDto{
    ID: "id",
}
client.Categories.UpdateCategory(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**name:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**description:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**parent:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**fee:** `*marketsdk.CategoryFeeDto` 
    
</dd>
</dl>

<dl>
<dd>

**prohibited:** `*bool` — Listings in a prohibited category cannot be published. Listings already published stay until moderated.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Categories.GetAttributeSchema(ID) -> *marketsdk.AttributeSchemaObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.GetAttributeSchemaRequest{
    ID: "id",
}
client.Categories.GetAttributeSchema(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Categories.PutAttributeSchema(ID, request) -> *marketsdk.AttributeSchemaObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Refused if a listing already in the category would no longer fit.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.PutAttributeSchemaRequest{
    ID: "id",
    Body: &marketsdk.AttributeSchemaObject{
        Attributes: []*marketsdk.AttributeDefinitionObject{
            &marketsdk.AttributeDefinitionObject{
                Key: "format",
                Type: marketsdk.AttributeDefinitionObjectTypeString,
            },
        },
    },
}
client.Categories.PutAttributeSchema(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**request:** `*marketsdk.AttributeSchemaObject` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Listings
<details><summary><code>client.Listings.ListListings() -> *marketsdk.ListingList</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

With a publishable key, only published listings are listed.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.ListListingsRequest{}
client.Listings.ListListings(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**limit:** `*float64` 
    
</dd>
</dl>

<dl>
<dd>

**startingAfter:** `*string` — The `next_cursor` of the previous page.
    
</dd>
</dl>

<dl>
<dd>

**seller:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**category:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**status:** `*marketsdk.ListListingsRequestStatus` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Listings.CreateListing(request) -> *marketsdk.ListingObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.CreateListingDto{
    Seller: "sel_034XtPDs7UJ0TXzTsdaHZa",
    Title: "title",
    Price: &marketsdk.MoneyDto{
        Amount: 4900,
        Currency: "USD",
    },
}
client.Listings.CreateListing(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `*marketsdk.CreateListingDto` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Listings.CreateListings(request) -> *marketsdk.BulkListingsObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.BulkCreateListingsDto{
    Listings: []*marketsdk.CreateListingDto{
        &marketsdk.CreateListingDto{
            Seller: "sel_034XtPDs7UJ0TXzTsdaHZa",
            Title: "title",
            Price: &marketsdk.MoneyDto{
                Amount: 4900,
                Currency: "USD",
            },
        },
    },
}
client.Listings.CreateListings(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**listings:** `[]*marketsdk.CreateListingDto` — All are created, or none.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Listings.GetListing(ID) -> *marketsdk.ListingObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

With a publishable key, only a published listing can be retrieved.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.GetListingRequest{
    ID: "id",
}
client.Listings.GetListing(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Listings.UpdateListing(ID, request) -> *marketsdk.ListingObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.UpdateListingDto{
    ID: "id",
}
client.Listings.UpdateListing(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**category:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**title:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**description:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**price:** `*marketsdk.MoneyDto` 
    
</dd>
</dl>

<dl>
<dd>

**quantity:** `*float64` — The total. Cannot go below what open orders have reserved.
    
</dd>
</dl>

<dl>
<dd>

**attributes:** `map[string]any` 
    
</dd>
</dl>

<dl>
<dd>

**metadata:** `map[string]string` 
    
</dd>
</dl>

<dl>
<dd>

**expiresAt:** `*time.Time` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Listings.PublishListing(ID) -> *marketsdk.ListingObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Needs an active seller, verified when seller verification is on, and a category that is not prohibited.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.PublishListingRequest{
    ID: "id",
}
client.Listings.PublishListing(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Listings.UnpublishListing(ID) -> *marketsdk.ListingObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.UnpublishListingRequest{
    ID: "id",
}
client.Listings.UnpublishListing(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Listings.RemoveListing(ID, request) -> *marketsdk.ListingObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.RemoveListingDto{
    ID: "id",
    Reason: "reason",
}
client.Listings.RemoveListing(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**reason:** `string` — Recorded with the removal.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Listings.ListMedia(ID) -> *marketsdk.MediaList</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.ListMediaRequest{
    ID: "id",
}
client.Listings.ListMedia(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Listings.CreateMedia(ID, request) -> *marketsdk.MediaUploadObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns a signed URL, valid for 10 minutes. PUT the file there, then complete the upload. The file is stored under a path that begins with the marketplace id.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.CreateMediaDto{
    ID: "id",
    ContentType: marketsdk.CreateMediaDtoContentTypeImageJpeg,
    SizeBytes: 1.1,
}
client.Listings.CreateMedia(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**contentType:** `marketsdk.CreateMediaDtoContentType` 
    
</dd>
</dl>

<dl>
<dd>

**sizeBytes:** `float64` — The exact size of the file, in bytes. At most 10 MB.
    
</dd>
</dl>

<dl>
<dd>

**position:** `*float64` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Listings.CompleteMedia(ID) -> *marketsdk.MediaObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Checks the stored file against the declared type and size.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.CompleteMediaRequest{
    ID: "id",
}
client.Listings.CompleteMedia(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Listings.DeleteMedia(ID) -> *marketsdk.MediaObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.DeleteMediaRequest{
    ID: "id",
}
client.Listings.DeleteMedia(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Search
<details><summary><code>client.Search.SearchListings() -> *marketsdk.ListingList</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Full text over title and description, with filters and sorting. Only published listings with something available are returned. Callable with a publishable key.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.SearchListingsRequest{}
client.Search.SearchListings(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**q:** `*string` — Full text over title and description.
    
</dd>
</dl>

<dl>
<dd>

**category:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**seller:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**minPrice:** `*float64` — Minor units.
    
</dd>
</dl>

<dl>
<dd>

**maxPrice:** `*float64` — Minor units.
    
</dd>
</dl>

<dl>
<dd>

**attributes:** `map[string]any` — Attribute filters, as attributes[key]=value for equality, or attributes[key][gte]=n and attributes[key][lte]=n for numbers. Numeric filters need a category.
    
</dd>
</dl>

<dl>
<dd>

**sort:** `*marketsdk.SearchListingsSearchRequestSort` — Relevance needs q. Default newest.
    
</dd>
</dl>

<dl>
<dd>

**limit:** `*float64` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — The next_cursor of the previous page.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Orders
<details><summary><code>client.Orders.ListOrders() -> *marketsdk.OrderList</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.ListOrdersRequest{}
client.Orders.ListOrders(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**limit:** `*float64` 
    
</dd>
</dl>

<dl>
<dd>

**startingAfter:** `*string` — The `next_cursor` of the previous page.
    
</dd>
</dl>

<dl>
<dd>

**buyer:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**seller:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**listing:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**state:** `*marketsdk.ListOrdersRequestState` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Orders.CreateOrder(request) -> *marketsdk.OrderObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

The buyer commits to buy. Quantity is reserved at once. With payments off the order is committed; with payments on it awaits payment.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.CreateOrderDto{
    Listing: "lst_034XtPDs7UJ0TXzTsdaHZa",
    Buyer: "buy_034XtPDs7UJ0TXzTsdaHZa",
}
client.Orders.CreateOrder(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**listing:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**buyer:** `string` — The buyer placing the order. The actor for this transition.
    
</dd>
</dl>

<dl>
<dd>

**quantity:** `*float64` 
    
</dd>
</dl>

<dl>
<dd>

**checkout:** `*marketsdk.CheckoutURLsDto` — Payments on only. With these, the order's payment includes a Stripe-hosted checkout URL; without them, a client secret for Stripe Elements on your own page.
    
</dd>
</dl>

<dl>
<dd>

**metadata:** `map[string]string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Orders.GetOrder(ID) -> *marketsdk.OrderObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.GetOrderRequest{
    ID: "id",
}
client.Orders.GetOrder(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Orders.ListOrderEvents(ID) -> *marketsdk.OrderEventList</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.ListOrderEventsRequest{
    ID: "id",
}
client.Orders.ListOrderEvents(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Orders.ClaimOrder(ID, request) -> *marketsdk.OrderObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Called from your server. `actor` says which end user is acting; we check they are a party to the order and may make this transition.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.ClaimOrderRequest{
    ID: "id",
    Body: &marketsdk.ActorDto{
        Actor: "buy_034XtPDs7UJ0TXzTsdaHZa",
    },
}
client.Orders.ClaimOrder(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**request:** `*marketsdk.ActorDto` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Orders.ConfirmOrder(ID, request) -> *marketsdk.OrderObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Called from your server. `actor` says which end user is acting; we check they are a party to the order and may make this transition.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.ConfirmOrderRequest{
    ID: "id",
    Body: &marketsdk.ActorDto{
        Actor: "buy_034XtPDs7UJ0TXzTsdaHZa",
    },
}
client.Orders.ConfirmOrder(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**request:** `*marketsdk.ActorDto` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Orders.BackOutOfOrder(ID, request) -> *marketsdk.OrderObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Called from your server. `actor` says which end user is acting; we check they are a party to the order and may make this transition. Writes a backed_out reputation event against the actor.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.BackOutOfOrderRequest{
    ID: "id",
    Body: &marketsdk.ActorDto{
        Actor: "buy_034XtPDs7UJ0TXzTsdaHZa",
    },
}
client.Orders.BackOutOfOrder(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**request:** `*marketsdk.ActorDto` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Orders.ProposeCancel(ID, request) -> *marketsdk.OrderObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Called from your server. `actor` says which end user is acting; we check they are a party to the order and may make this transition. The other party can accept within the agreement window. A declined or lapsed proposal changes nothing.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.ProposeCancelRequest{
    ID: "id",
    Body: &marketsdk.ActorDto{
        Actor: "buy_034XtPDs7UJ0TXzTsdaHZa",
    },
}
client.Orders.ProposeCancel(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**request:** `*marketsdk.ActorDto` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Orders.AcceptCancel(ID, request) -> *marketsdk.OrderObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Called from your server. `actor` says which end user is acting; we check they are a party to the order and may make this transition.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.AcceptCancelRequest{
    ID: "id",
    Body: &marketsdk.ActorDto{
        Actor: "buy_034XtPDs7UJ0TXzTsdaHZa",
    },
}
client.Orders.AcceptCancel(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**request:** `*marketsdk.ActorDto` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Orders.DeclineCancel(ID, request) -> *marketsdk.OrderObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Called from your server. `actor` says which end user is acting; we check they are a party to the order and may make this transition.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.DeclineCancelRequest{
    ID: "id",
    Body: &marketsdk.ActorDto{
        Actor: "buy_034XtPDs7UJ0TXzTsdaHZa",
    },
}
client.Orders.DeclineCancel(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**request:** `*marketsdk.ActorDto` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Orders.ListOrderReviews(ID) -> *marketsdk.ReviewList</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.ListOrderReviewsRequest{
    ID: "id",
}
client.Orders.ListOrderReviews(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Orders.CreateReview(ID, request) -> *marketsdk.ReviewObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Called from your server. `actor` says which end user is acting; we check they are a party to the order and may make this transition. Only on a completed order, inside the review window, once per party. Hidden until both have reviewed or the window closes.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.CreateReviewDto{
    ID: "id",
    Actor: "buy_034XtPDs7UJ0TXzTsdaHZa",
    Rating: 1.1,
}
client.Orders.CreateReview(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**actor:** `string` — The buyer id or seller id of the end user doing this. We check they are a party to the order and may make this transition.
    
</dd>
</dl>

<dl>
<dd>

**rating:** `float64` 
    
</dd>
</dl>

<dl>
<dd>

**body:** `*string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Reviews
<details><summary><code>client.Reviews.ListReviews() -> *marketsdk.ReviewList</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.ListReviewsRequest{
    Subject: "subject",
}
client.Reviews.ListReviews(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**limit:** `*float64` 
    
</dd>
</dl>

<dl>
<dd>

**startingAfter:** `*string` — The `next_cursor` of the previous page.
    
</dd>
</dl>

<dl>
<dd>

**subject:** `string` — The buyer or seller the reviews are about.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Reviews.GetReview(ID) -> *marketsdk.ReviewObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.GetReviewRequest{
    ID: "id",
}
client.Reviews.GetReview(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Reputation
<details><summary><code>client.Reputation.ListReputationEvents() -> *marketsdk.ReputationEventList</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.ListReputationEventsRequest{
    Party: "party",
}
client.Reputation.ListReputationEvents(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**limit:** `*float64` 
    
</dd>
</dl>

<dl>
<dd>

**startingAfter:** `*string` — The `next_cursor` of the previous page.
    
</dd>
</dl>

<dl>
<dd>

**party:** `string` — The buyer or seller whose events to list.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Reputation.VoidReputationEvent(ID, request) -> *marketsdk.ReputationEventObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

For the customer's team. Writes a second event pointing at the first. The voided event stops counting. Nothing is deleted.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.VoidDto{
    ID: "id",
    Reason: "reason",
}
client.Reputation.VoidReputationEvent(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**reason:** `string` — Why the event is voided. Recorded on the voiding event.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Payments
<details><summary><code>client.Payments.ListPayments() -> *marketsdk.PaymentList</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.ListPaymentsRequest{}
client.Payments.ListPayments(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**limit:** `*float64` 
    
</dd>
</dl>

<dl>
<dd>

**startingAfter:** `*string` — The `next_cursor` of the previous page.
    
</dd>
</dl>

<dl>
<dd>

**order:** `*string` — Only the payment for this order.
    
</dd>
</dl>

<dl>
<dd>

**status:** `*marketsdk.ListPaymentsRequestStatus` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Payments.GetPayment(ID) -> *marketsdk.PaymentObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.GetPaymentRequest{
    ID: "id",
}
client.Payments.GetPayment(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Payments.UpdatePayment(ID, request) -> *marketsdk.PaymentObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.UpdatePaymentRequest{
    ID: "id",
    Body: &marketsdk.UpdateMetadataDto{
        Metadata: map[string]string{
            "key": "value",
        },
    },
}
client.Payments.UpdatePayment(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**request:** `*marketsdk.UpdateMetadataDto` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Payments.RetryPaymentRelease(ID) -> *marketsdk.PaymentObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

For a release that failed, for example because the seller could not yet receive transfers. A release is also tried again by itself when the seller becomes able to receive payouts.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.RetryPaymentReleaseRequest{
    ID: "id",
}
client.Payments.RetryPaymentRelease(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Payments.ListRefunds() -> *marketsdk.RefundList</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.ListRefundsRequest{}
client.Payments.ListRefunds(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**limit:** `*float64` 
    
</dd>
</dl>

<dl>
<dd>

**startingAfter:** `*string` — The `next_cursor` of the previous page.
    
</dd>
</dl>

<dl>
<dd>

**payment:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**order:** `*string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Payments.CreateRefund(request) -> *marketsdk.RefundObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Recorded at once with status `pending`, then made at Stripe. If the seller's share was already released, the transfer is reversed in the same proportion, so your fee is given back in proportion too.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.CreateRefundDto{}
client.Payments.CreateRefund(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**payment:** `*string` — The payment to refund. Give this or `order`.
    
</dd>
</dl>

<dl>
<dd>

**order:** `*string` — The order whose payment to refund. Give this or `payment`.
    
</dd>
</dl>

<dl>
<dd>

**amount:** `*float64` — Minor units. Defaults to everything not yet refunded.
    
</dd>
</dl>

<dl>
<dd>

**reason:** `*marketsdk.CreateRefundDtoReason` 
    
</dd>
</dl>

<dl>
<dd>

**metadata:** `map[string]string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Payments.GetRefund(ID) -> *marketsdk.RefundObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.GetRefundRequest{
    ID: "id",
}
client.Payments.GetRefund(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Payments.UpdateRefund(ID, request) -> *marketsdk.RefundObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.UpdateRefundRequest{
    ID: "id",
    Body: &marketsdk.UpdateMetadataDto{
        Metadata: map[string]string{
            "key": "value",
        },
    },
}
client.Payments.UpdateRefund(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**request:** `*marketsdk.UpdateMetadataDto` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Trust
<details><summary><code>client.Trust.CreateVerification(ID, request) -> *marketsdk.VerificationObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Creates a Stripe Identity session on your Stripe account and returns its page, once. Only the outcome and the session id are kept; no document image or document data. When seller verification is on, a seller can publish only once verified.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.CreateVerificationDto{
    ID: "id",
}
client.Trust.CreateVerification(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**returnURL:** `*string` — Where Stripe sends the seller after the verification page.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Trust.ListVerifications() -> *marketsdk.VerificationList</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.ListVerificationsRequest{}
client.Trust.ListVerifications(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**limit:** `*float64` 
    
</dd>
</dl>

<dl>
<dd>

**startingAfter:** `*string` — The `next_cursor` of the previous page.
    
</dd>
</dl>

<dl>
<dd>

**seller:** `*string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Trust.GetVerification(ID) -> *marketsdk.VerificationObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.GetVerificationRequest{
    ID: "id",
}
client.Trust.GetVerification(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Trust.CancelVerification(ID) -> *marketsdk.VerificationObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.CancelVerificationRequest{
    ID: "id",
}
client.Trust.CancelVerification(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Trust.ListDisputes() -> *marketsdk.DisputeList</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Filter by `stage` for a queue.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.ListDisputesRequest{}
client.Trust.ListDisputes(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**limit:** `*float64` 
    
</dd>
</dl>

<dl>
<dd>

**startingAfter:** `*string` — The `next_cursor` of the previous page.
    
</dd>
</dl>

<dl>
<dd>

**stage:** `*marketsdk.ListDisputesRequestStage` 
    
</dd>
</dl>

<dl>
<dd>

**order:** `*string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Trust.GetDispute(ID) -> *marketsdk.DisputeObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.GetDisputeRequest{
    ID: "id",
}
client.Trust.GetDispute(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Trust.ListDisputeEvidence(ID) -> *marketsdk.DisputeEvidenceList</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.ListDisputeEvidenceRequest{
    ID: "id",
}
client.Trust.ListDisputeEvidence(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Trust.AddDisputeEvidence(ID, request) -> *marketsdk.DisputeEvidenceObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Only while the dispute is in its evidence stage.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.AddEvidenceDto{
    ID: "id",
    Actor: "actor",
    Body: "body",
}
client.Trust.AddDisputeEvidence(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**actor:** `string` — The buyer or seller giving evidence.
    
</dd>
</dl>

<dl>
<dd>

**body:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**links:** `[]string` — Links to files the party provided, such as photos you store. HTTPS only.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Trust.CloseDisputeEvidence(ID) -> *marketsdk.DisputeObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.CloseDisputeEvidenceRequest{
    ID: "id",
}
client.Trust.CloseDisputeEvidence(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Trust.DecideDispute(ID, request) -> *marketsdk.DisputeObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Your team's decision: who it went against, in writing, and with payments on, how much goes back to the buyer. On a claimed order, deciding against the party who disputed upholds the claim and completes the order; deciding against the claimant cancels it.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.DecideDisputeDto{
    ID: "id",
    Against: marketsdk.DecideDisputeDtoAgainstBuyer,
    Note: "note",
}
client.Trust.DecideDispute(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**against:** `marketsdk.DecideDisputeDtoAgainst` — Who the decision went against. They get a dispute_lost reputation event; the other party gets dispute_won.
    
</dd>
</dl>

<dl>
<dd>

**note:** `string` — The written decision, kept with the dispute.
    
</dd>
</dl>

<dl>
<dd>

**refundAmount:** `*float64` — Payments on only. Minor units to refund to the buyer; the rest goes to the seller. Defaults: a claimed order whose claim is upheld refunds nothing; one whose claim is rejected refunds everything; a dispute on a completed order refunds nothing.
    
</dd>
</dl>

<dl>
<dd>

**decidedBy:** `*string` — Who on your team decided, for the record. Up to 200 characters.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Trust.OpenDispute(ID, request) -> *marketsdk.DisputeObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

On a claimed order, by the party who did not claim: the order becomes disputed. On a completed order, by either party inside the dispute window: the order stays completed.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.OpenDisputeDto{
    ID: "id",
    Actor: "buy_034XtPDs7UJ0TXzTsdaHZa",
    Reason: "reason",
}
client.Trust.OpenDispute(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**actor:** `string` — The buyer or seller opening the dispute.
    
</dd>
</dl>

<dl>
<dd>

**reason:** `string` — What went wrong, in their words.
    
</dd>
</dl>

<dl>
<dd>

**metadata:** `map[string]string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Moderation
<details><summary><code>client.Moderation.ListFlags() -> *marketsdk.FlagList</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.ListFlagsRequest{}
client.Moderation.ListFlags(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**limit:** `*float64` 
    
</dd>
</dl>

<dl>
<dd>

**startingAfter:** `*string` — The `next_cursor` of the previous page.
    
</dd>
</dl>

<dl>
<dd>

**status:** `*marketsdk.ListFlagsRequestStatus` 
    
</dd>
</dl>

<dl>
<dd>

**target:** `*string` — Only flags on this listing, seller, or review.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Moderation.CreateFlag(request) -> *marketsdk.FlagObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

On behalf of the end user who reported it.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.CreateFlagDto{
    Target: "lst_034XtPDs7UJ0TXzTsdaHZa",
    Reporter: "buy_034XtPDs7UJ0TXzTsdaHZa",
    Reason: marketsdk.CreateFlagDtoReasonProhibitedItem,
}
client.Moderation.CreateFlag(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**target:** `string` — A listing, seller, or review id.
    
</dd>
</dl>

<dl>
<dd>

**reporter:** `string` — The end user reporting it: a buyer id or a seller id.
    
</dd>
</dl>

<dl>
<dd>

**reason:** `marketsdk.CreateFlagDtoReason` 
    
</dd>
</dl>

<dl>
<dd>

**note:** `*string` — The reporter's own words.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Moderation.GetFlag(ID) -> *marketsdk.FlagObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.GetFlagRequest{
    ID: "id",
}
client.Moderation.GetFlag(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Moderation.GetModerationQueue() -> *marketsdk.ModerationQueueObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.GetModerationQueueRequest{}
client.Moderation.GetModerationQueue(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**targetType:** `*marketsdk.GetModerationQueueRequestTargetType` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Moderation.ListModerationActions() -> *marketsdk.ModerationActionList</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.ListModerationActionsRequest{}
client.Moderation.ListModerationActions(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**limit:** `*float64` 
    
</dd>
</dl>

<dl>
<dd>

**startingAfter:** `*string` — The `next_cursor` of the previous page.
    
</dd>
</dl>

<dl>
<dd>

**target:** `*string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Moderation.CreateModerationAction(request) -> *marketsdk.ModerationActionObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Resolves the target's open flags and logs who acted and why.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.CreateModerationActionDto{
    Target: "target",
    Action: marketsdk.CreateModerationActionDtoActionDismiss,
    Reason: "reason",
    Actor: "actor",
}
client.Moderation.CreateModerationAction(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**target:** `string` — The listing, seller, or review acted on.
    
</dd>
</dl>

<dl>
<dd>

**action:** `marketsdk.CreateModerationActionDtoAction` — `dismiss` closes the open flags and changes nothing else. `remove_content` removes a listing or a review; a removed review stops counting toward reputation. `suspend_seller` suspends the seller, or the seller of a listing, or a seller who wrote a review: they cannot publish or take orders, and their listings leave search. `reinstate_seller` lifts a suspension.
    
</dd>
</dl>

<dl>
<dd>

**reason:** `string` — Why. Kept with the action.
    
</dd>
</dl>

<dl>
<dd>

**actor:** `string` — Who on your team took the action, for the log.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Webhooks
<details><summary><code>client.Webhooks.ListWebhookEndpoints() -> *marketsdk.WebhookEndpointList</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.ListWebhookEndpointsRequest{}
client.Webhooks.ListWebhookEndpoints(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**limit:** `*float64` 
    
</dd>
</dl>

<dl>
<dd>

**startingAfter:** `*string` — The `next_cursor` of the previous page.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Webhooks.CreateWebhookEndpoint(request) -> *marketsdk.WebhookEndpointObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns the signing secret, once. Every delivery carries `MarketSDK-Signature: t=<time>,v1=<HMAC-SHA256 of "<time>.<body>">`.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.CreateWebhookEndpointDto{
    URL: "https://shop.example/marketsdk/webhooks",
    EnabledEvents: []marketsdk.CreateWebhookEndpointDtoEnabledEventsItem{
        marketsdk.CreateWebhookEndpointDtoEnabledEventsItemAll,
    },
}
client.Webhooks.CreateWebhookEndpoint(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**url:** `string` — An HTTPS URL on the public internet.
    
</dd>
</dl>

<dl>
<dd>

**enabledEvents:** `[]marketsdk.CreateWebhookEndpointDtoEnabledEventsItem` — Event types to send, or `*` for all.
    
</dd>
</dl>

<dl>
<dd>

**description:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**metadata:** `map[string]string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Webhooks.GetWebhookEndpoint(ID) -> *marketsdk.WebhookEndpointObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.GetWebhookEndpointRequest{
    ID: "id",
}
client.Webhooks.GetWebhookEndpoint(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Webhooks.DeleteWebhookEndpoint(ID) -> *marketsdk.DeletedWebhookEndpointObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.DeleteWebhookEndpointRequest{
    ID: "id",
}
client.Webhooks.DeleteWebhookEndpoint(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Webhooks.UpdateWebhookEndpoint(ID, request) -> *marketsdk.WebhookEndpointObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.UpdateWebhookEndpointDto{
    ID: "id",
}
client.Webhooks.UpdateWebhookEndpoint(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**url:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**enabledEvents:** `[]marketsdk.UpdateWebhookEndpointDtoEnabledEventsItem` 
    
</dd>
</dl>

<dl>
<dd>

**description:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**status:** `*marketsdk.UpdateWebhookEndpointDtoStatus` — Turn the endpoint off, or back on after it was turned off.
    
</dd>
</dl>

<dl>
<dd>

**metadata:** `map[string]string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Webhooks.RotateWebhookSecret(ID) -> *marketsdk.WebhookEndpointObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns the new secret, once. The old one stops at once.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.RotateWebhookSecretRequest{
    ID: "id",
}
client.Webhooks.RotateWebhookSecret(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Webhooks.ListWebhookDeliveries() -> *marketsdk.WebhookDeliveryList</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.ListWebhookDeliveriesRequest{}
client.Webhooks.ListWebhookDeliveries(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**limit:** `*float64` 
    
</dd>
</dl>

<dl>
<dd>

**startingAfter:** `*string` — The `next_cursor` of the previous page.
    
</dd>
</dl>

<dl>
<dd>

**endpoint:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**status:** `*marketsdk.ListWebhookDeliveriesRequestStatus` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Webhooks.GetWebhookDelivery(ID) -> *marketsdk.WebhookDeliveryObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.GetWebhookDeliveryRequest{
    ID: "id",
}
client.Webhooks.GetWebhookDelivery(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Webhooks.ReplayWebhookDelivery(ID) -> *marketsdk.WebhookDeliveryObject</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Creates a new delivery of the same event to the same endpoint.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.ReplayWebhookDeliveryRequest{
    ID: "id",
}
client.Webhooks.ReplayWebhookDelivery(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Webhooks.ListEvents() -> *marketsdk.EventList</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.ListEventsRequest{}
client.Webhooks.ListEvents(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**limit:** `*float64` 
    
</dd>
</dl>

<dl>
<dd>

**startingAfter:** `*string` — The `next_cursor` of the previous page.
    
</dd>
</dl>

<dl>
<dd>

**type_:** `*marketsdk.ListEventsRequestType` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Webhooks.GetEvent(ID) -> *marketsdk.EventObject</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &marketsdk.GetEventRequest{
    ID: "id",
}
client.Webhooks.GetEvent(
    context.TODO(),
    request,
)
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

