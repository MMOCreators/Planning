### Login System
#### Reason
#### Endpoints
* /api/login [POST]
	* Reason:
	* Security: rate-limit-by-ip, payload validation, payload sanitization
	* Payload:
		* username [string] **REQUIRED**
		* password [string] **REQUIRED**
		* client_id [string] **REQUIRED**
* /api/login/validate [POST]
	* Reason:
	* Security: rate-limit-by-ip, payload validation, payload sanitization
	* Payload:
		* code [string] **REQUIRED**
		* client_id [string] **REQUIRED**
* /api/register [POST]
	* Reason:
	* Security: rate-limit-by-ip, payload validation, payload sanitization
	* Payload:
		* username [string] **REQUIRED**
		* password [string] **REQUIRED**
		* email [string] **REQUIRED**
		* client_id [string] **REQUIRED**
* /api/register/verify [POST]
	* Reason:
	* Security: rate-limit-by-ip, payload validation, payload sanitization
	* Payload:
		* token [string] **REQUIRED**
		* client_id [string] **REQUIRED**
* /api/profile [GET]
	* Reason:
	* Security: rate-limit-by-ip, payload validation, payload sanitization, jwt-auth-header
	* Headers:
		* Authorization [string] **REQUIRED**
	* Payload: NONE
* /api/profile [POST]
	* Reason:
	* Security: rate-limit-by-ip, payload validation, payload sanitization, jwt-auth-header
	* Headers:
		* Authorization [string] **REQUIRED**
		* client_id [string] **REQUIRED**
	* Payload:
		* display_name [string] **REQUIRED**
* /api/profile/password [POST]
	* Reason:
	* Security: rate-limit-by-ip, payload validation, payload sanitization, jwt-auth-header
	* Headers:
		* Authorization [string] **REQUIRED**
		* client_id [string] **REQUIRED**
	* Payload:
		* old_password [string] **REQUIRED**
		* new_password [string] **REQUIRED**
* /api/resetpassword [POST]
	* Reason:
	* Security: rate-limit-by-ip, payload validation, payload sanitization
	* Payload:
		* username [string] **REQUIRED**
		* email [string] **REQUIRED**
		* client_id [string] **REQUIRED**
* /api/forgotusername [POST]
	* Reason:
	* Security: rate-limit-by-ip, payload validation, payload sanitization
	* Payload:
		* email [string] **REQUIRED**
		* client_id [string] **REQUIRED**