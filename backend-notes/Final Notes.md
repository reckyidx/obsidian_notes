
Authorization
	what resource and access user is permitted to access
	 Methods
		 - Role based access control
		 - security assertion markup language
		 - OpenId Authorization (third party access)
		 - OAuth (guest user access certain)
		 - Device Permission (camera, location)


Authentication
	confirm person identity
		method
		- password based authentication
		- multi factor authentication
		- biometric 
		- token based 
			- JWT
				- header, payload, signature. two types (symmetric  or HS256
					(server validates)and asymetric RS256
					both server and client validates))
				 
		- OAuth connect

Rate limiter
	Person can access the api within 