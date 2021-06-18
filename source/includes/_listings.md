# Listings

## Update a Listing

> Example Request

```shell
curl "https://marketplace-api.candideapp.com/listing?sku=93A-123" \
  -X PATCH \
  -H 'Content-Type: application/json' \
  -H "Authorization: Bearer plants-plants-plants"
  -d '{"quantity": 42}'
```

> Response
> {
> "id": "352de449-a943-4651-937b-52b7ad3246e6",
> "sku": "93A-123",
> "quantity": 42,
> "updatedAt": "2021-06-17T15:53:14.735Z"
> }

Modifies a listing.

### HTTP Request

`PATCH http://marketplace-api.candideapp.com/listing?sku=<ID>`

### URL Parameters

| Parameter        | Description                                 |
| ---------------- | ------------------------------------------- |
| SKU _(required)_ | The ID used by your shop to track inventory |

### Arguments

| Parameter | Type   | Description                                                                           |
| --------- | ------ | ------------------------------------------------------------------------------------- |
| quantity  | number | A non-negative integer representing the number of units available for a given Listing |

<aside class="notice">
Currently only updating quantity is supported.
</aside>

## Batch Operations

> Example Request. Updates the quantity of two listings.

```shell
curl "https://marketplace-api.candideapp.com/listings/batch-update" \
  -X POST \
  -H 'Content-Type: application/json' \
  -H "Authorization: Bearer plants-plants-plants" \
  --data-binary @- << EOF
{
  "requests": [
    {
      "sku": "93A-123",
      "quantity": 15,
    },
    {
      "sku": "94A-123",
      "quantity": 10,
    },
    {
      "sku": "SKU-fake",
      "quantity": 10,
    },
  ];
}
EOF
```

> Response
> {
> "totalOperations": 3,
> "totalSucceeded": 2,
> "totalFailed": 1,
> "failedSKUs": ["SKU-fake"]
> }

You can update multiple listings with a single HTTP call using batch updates.

### HTTP Request

`POST http://marketplace-api.candideapp.com/listings/batch-update`

### Arguments

| Parameter           | Type   | Decription                                                                            |
| ------------------- | ------ | ------------------------------------------------------------------------------------- |
| requests            | object | A JSON object containing all requests.                                                |
| requests[].sku      | string | The ID used by your shop to track inventory                                           |
| requests[].quantity | number | A non-negative integer representing the number of units available for a given Listing |

<aside class="notice">
Currently only update operations that modify quantity are supported.
</aside>
