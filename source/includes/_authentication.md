# Authentication

> To check you are authorised:

```shell
# Will return 200 if authenticated correctly
curl "https://marketplace-api.candideapp.com/" \
-i -H "Authorization: Bearer plants-plants-plants"
```

> Make sure to replace `plants-plants-plants` with your API key.

The Candide Marketplace API uses API keys to authenticate requests. You can view and manage your API keys in the [Seller Portal](https://myshop.candidegardening.com/).

New secret keys are only visible the first time you access them. After that, the Seller Portal redacts the API key. If you lose a secret key, you can't recover it from the Seller Portal and must create another one. Candide allows a maximum of 5 API keys to be created for an account.

The API key must be included in all API requests to the server. Not including your key when making an API request, or using one that is incorrect or outdated, will return an error. All API requests must be made over [HTTPS](https://en.wikipedia.org/wiki/HTTPS). Calls made over plain HTTP will fail.

API keys should be provided using a header that looks like the following:

`Authorization: Bearer plants-plants-plants`

<aside class="notice">
You must replace <code>plants-plants-plants</code> with your account's API key.
</aside>
