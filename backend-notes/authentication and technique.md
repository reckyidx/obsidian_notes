
#### Authtentication- verifies who you are

#### Authorization - Granting access to utilize their resource

##### SSO - Single Sign On

#### SAML - security assertion markup language

#### OAuth - Open Authentication
 - users allow to share their private resource to third party
 - Deprecated
 - 

#### OAuth2.0 - Open Authentication 2.0
 - Authorization code has [clientId, clientSecret, Resource server, Authorization Server]
 - simple, less complex compare to 1.0
 - refresh token for long live access

#### JWT (Json Web Token)
- Used for Authorization and secure info exchange
- Generates normal string that can be passed in header, body or URL
- Token Separated by three dot [header | payload | signature]
	-  header - metadata of [{typ: jwt, alg: HS256}]
	- payload - base 64 encoded not encrypted (called as jwt claims)
		##### - Claims [piece of info about payload]
		1. Register claims
			- iat  - issued at
			- iss - issuer
			- sub - token sub
			- exp - expiry time
			- aud - token audience
			- nbf - not before
			- jti - Unique token identifier
		2. Public claims
			- define and use our own data
		3. Private Claims
			- 

	- Signature - hashing header & payload with secret that kept at server side, used to generate and verify the token [header + payload + secret key]
- How it works ? 
	- user log in -> server generate JWT and sent it back to client -> client store (cookies or local storage) and send it http header request -> server validates without quering the DB
#### Basic authentication
 - simple http auth built into http protocol
 - username + password -> encoded in base 64 format
#### Cookie Based Authentication
- 
