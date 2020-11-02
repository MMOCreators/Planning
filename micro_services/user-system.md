### User System
#### Reason
#### Endpoints
* /api/profile [GET]
	* Reason:
	* Security: rate-limit-by-ip, payload validation, payload sanitization, jwt-auth-header
	* Headers:
		* Authorization [string] **REQUIRED**
		* build_id [string] **REQUIRED**
	* Payload: NONE
* /api/profile [POST]
	* Reason:
	* Security: rate-limit-by-ip, payload validation, payload sanitization, jwt-auth-header
	* Headers:
		* Authorization [string] **REQUIRED**
		* build_id [string] **REQUIRED**
	* Payload:
		* display_name [string] **REQUIRED**
* /api/profile/password [POST]
	* Reason:
	* Security: rate-limit-by-ip, payload validation, payload sanitization, jwt-auth-header
	* Headers:
		* Authorization [string] **REQUIRED**
		* build_id [string] **REQUIRED**
	* Payload:
		* old_password [string] **REQUIRED**
		* new_password [string] **REQUIRED**