### Email System
#### Reason
By off-loading the Sending of the Emails, that means no templating inside of the Login System. It also means, that there is less complexity due to the fact, un-needed endpoints are moved to their own service. As more emails need to be sent for various reasons, this will make it easy to expand on. This also allows us to make edits, and changes to how things are handled with little to no effort. 

Also by seperating it, we can make the payloads simple, thus it requires no database access. It simply can only send specific emails within specific templates.

I think doing this will be easier in the long-run, but require alittle more setup/work at the beginning.
#### Endpoints
* /api/register [POST]
	* Reason: When a user registers, this will allow them to verify their account.
	* Security: payload validation, payload sanitization, jwt-auth
	* Payload:
		* email [string] **REQUIRED**
		* verify_token [string] **REQUIRED**
        * IP [string] **REQUIRED**
* /api/resetpass [POST]
	* Reason: When a usr wants to reset their password, cause they cannot login, this will send them a email allowing them to reset.
	* Security: payload validation, payload sanitization, jwt-auth
	* Payload:
		* email [string] **REQUIRED**
		* reset_token [string] **REQUIRED**
        * IP [string] **REQUIRED**
* /api/changepass [POST]
	* Reason: When a user wants to change their password to a new password, this will send them a email verifying they wanted this.
	* Security: payload validation, payload sanitization, jwt-auth
	* Payload:
		* email [string] **REQUIRED**
		* validate_token [string] **REQUIRED**
        * IP [string] **REQUIRED**
* /api/forgotuser [POST]
	* Reason: When a user forgets their Username, this will send a email with their information.
	* Security: payload validation, payload sanitization, jwt-auth
	* Payload:
		* email [string] **REQUIRED**
        * user [string] **REQUIRED**
        * IP [string] **REQUIRED**