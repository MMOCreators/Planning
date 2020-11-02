### Login System
#### Reason
By Placing in all the Functionality required for a user to login/register, reset password, use forget username. We can seperate the complexity from the main User System, allowing the for only user login/validation to happen while all of the actual user functionality sites within the User System, makes it alot easier to handle overall.

Though if I was using Elixir, I would shuve it all into 1 App cause.. Yeah. Elixir Rocks.
#### Endpoints
* /api/login [POST]
	* Reason:
	* Security: rate-limit-by-ip, payload validation, payload sanitization
	* Payload:
		* username [string] **REQUIRED**
		* password [string] **REQUIRED**
		* build_id [string] **REQUIRED**
* /api/login/validate [POST]
	* Reason: Uses the MFA TOTP to Login
	* Security: rate-limit-by-ip, payload validation, payload sanitization
	* Payload:
		* code [string] **REQUIRED**
		* build_id [string] **REQUIRED**
* /api/register [POST]
	* Reason: Allows a user to register with the System.
	* Security: rate-limit-by-ip, payload validation, payload sanitization
	* Payload:
		* username [string] **REQUIRED**
		* password [string] **REQUIRED**
		* email [string] **REQUIRED**
		* build_id [string] **REQUIRED**
* /api/register/verify [POST]
	* Reason: Verify that the Email you used, is a valid Email.
	* Security: rate-limit-by-ip, payload validation, payload sanitization
	* Payload:
		* token [string] **REQUIRED**
		* build_id [string] **REQUIRED**
* /api/password/verify [POST]
	* Reason: Validate the changing of your Password.
	* Security: rate-limit-by-ip, payload validation, payload sanitization
	* Payload:
		* token [string] **REQUIRED**
		* build_id [string] **REQUIRED**
* /api/resetpassword [POST]
	* Reason: Triggering the Resetting of the User's Password
	* Security: rate-limit-by-ip, payload validation, payload sanitization
	* Payload:
		* username [string] **REQUIRED**
		* email [string] **REQUIRED**
		* build_id [string] **REQUIRED**
* /api/resetpassword/verify [POST]
	* Reason: Verify the User did in-deed want to Reset their Password.
	* Security: rate-limit-by-ip, payload validation, payload sanitization
	* Payload:
		* token [string] **REQUIRED**
		* build_id [string] **REQUIRED**
* /api/forgotusername [POST]
	* Reason: User wants to know their forgotten username.
	* Security: rate-limit-by-ip, payload validation, payload sanitization
	* Payload:
		* email [string] **REQUIRED**
		* build_id [string] **REQUIRED**