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

> Response (204 No Content)

Modifies a listing.

### HTTP Request

`PATCH http://marketplace-api.candideapp.com/listing?sku=<ID>`

### URL Parameters

| Parameter        | Description                                 |
| ---------------- | ------------------------------------------- |
| SKU _(required)_ | The ID used by your shop to track inventory |

### Arguments

| Parameter | Type   | Decription                                                                           |
| --------- | ------ | ------------------------------------------------------------------------------------ |
| quantity  | number | A nonnegative integer representing the number of units available for a given Listing |

<aside class="notice">
Currently only updating quantity is supported.
</aside>

## Batch Operations

> Example Request. Updates the quanity of one listing, and deletes another.

```shell
curl "https://marketplace-api.candideapp.com/listings/batch" \
  -X POST \
  -H 'Content-Type: application/json' \
  -H "Authorization: Bearer plants-plants-plants" \
  --data-binary @- << EOF
{
  "requests": [
    {
      "method": "UPDATE",
      "sku": "abc-123",
      "data": {
        "quantity": 10,
      },
    },
    {
      "method": "DELETE",
      "sku": "abc-123",
    },
  ];
}
EOF
```

> Response (204 No Content)

You can create, update and delete multiple listings with a single HTTP call using batch updates.

### HTTP Request

`POST http://marketplace-api.candideapp.com/listings/batch`

### Arguments

| Parameter         | Type   | Decription                                                |
| ----------------- | ------ | --------------------------------------------------------- |
| requests          | object | A JSON object containing all requests.                    |
| requests[].sku    | string | The ID used by your shop to track inventory               |
| requests[].method | string | CREATE, UPDATE, DELETE                                    |
| requests[].data   | object | A JSON object containing fields and values for a listing. |

<aside class="notice">
Currently only update operations that modify quantity are supported.
</aside>
