> Source: https://docs.ns-api.com/docs/getting-started

The NetSapiens API supports three types of authentication methods, each with its own set of benefits and considerations. These methods are detailed in the following guides:

1. [OAuth2 Based Access and Refresh Tokens](/docs/access-tokens)

   * Legacy format also supported by v1 applications.
   * Timed tokens suitable for various application types and scopes.
   * Requires a username and password to be granted an access token.
2. [JWT Tokens (JSON Web Tokens)](/docs/jwt-tokens)

   * Timed tokens with parseable token information.
   * Non-session-based, placing a lighter load on the system.
   * Particularly well-suited for end-user access to web applications.
3. [API Keys](/docs/api-keys)

   * Suitable for server-to-server applications where the API key can remain secure.
   * Ideal for applications requiring office manager, reseller, or super user access.
   * No username and password needed for authentication.
   * Can be restricted using read-only options and IP restrictions if required.
   * Usage is tracked and monitored through iNSight.

Each authentication method serves different use cases, providing flexibility and security based on your application's requirements.