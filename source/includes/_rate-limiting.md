# Rate Limiting

The Candide Marketplace API is rate limited to prevent bursts of traffic that may degrade our ability to maintain consistent API performance for all users. By default, each account is limited at 60 requests per minute.

Accounts that exceed this limit may see error responses with the 429 status code.
