## Database Design
The simplier you make it, the easier it is overall. Limit the number of features, for v1.0 rather then trying to build everything.
## Information
* Database: Postgres

![v1 Database Layout Diagram](https://github.com/MMOCreators/Planning/blob/develop/files/v1-database-layout.png)

### Users
* id
* username
* password
* email
* banned_on
* deleted_on
* updated_on
* created_on
### Profiles
* id
* user_id
* display_name
* updated_on
* created_on
### Login_Verfications
* id
* user_id
* client_id
* totp
* expires_on
* created_on
### Account_Verifications
* id
* user_id
* client_id
* email
* jwtid
* verified_on
* expires_on
* created_on
### Sessions
* id
* user_id
* client_id
* build_id
* token
* destroyed_on
* created_on
### Realms
* id
* name
* disabled
* last_restart_on
* shutdown_on
* created_on
### Servers
* id
* name
* realm_id
* population
* capacity
* last_restarted_on
* updated_on
* created_on
### Server_Connections
* id
* server_id
* location_token
* disabled_on
* created_on
### Characters
* id
* user_id
* realm_id
* name
* x
* y
* z
* w
* updated_on
* deleted_on
* created_on
### Character_Inventory
* id
* character_id
* item_id
* added_on
* removed_on
* created_on
### Character_Location
* id
* character_id
* server_id
* created_on
### Items
* id
* name
* description
* data
* hash
* created_on
### Clients
* id
* uid
* name
* disabled_on
* created_on
### Builds
* id
* uid
* client_id
* created_on