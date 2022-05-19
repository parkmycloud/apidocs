HOST: https://console.parkmycloud.com

# ParkMyCloudAPI

# Group API Key API V2

## APIKEY for self [/v2/apikey/]

### POST

+ Request (application/json)
    
    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 201 (application/json)
    + Attributes (APIKey)

+ Response 401 (application/json)

    
    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }

### PUT

+ Request (application/json)
    
    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 201 (application/json)
    + Attributes (APIKey)

+ Response 401 (application/json)

    
    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }

+ Response 404 (application/json) 
    
    + Body

            {
                "code": "NOT_FOUND",
                "detail_code": "",
                "message": "Item not found"
            }

### GET

+ Request (application/json)

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8
    
+ Response 200 (application/json)
    + Attributes (APIKey)

+ Response 401 (application/json)

    
    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }

+ Response 404 (application/json) 
    
    + Body

            {
                "code": "NOT_FOUND",
                "detail_code": "",
                "message": "Item not found"
            }

### DELETE

+ Request (application/json)

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8
    
+ Response 204 (application/json)

+ Response 401 (application/json)

    
    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }

## APIKEY for other user [/v2/apikey/{user_id}]

+ Parameters
  + user_id (number, optional) - user id

### POST

+ Request (application/json)
    
    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 201 (application/json)
    + Attributes (APIKey)

+ Response 401 (application/json)

    
    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }

### PUT

+ Request (application/json)
    
    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 201 (application/json)
    + Attributes (APIKey)

+ Response 401 (application/json)

    
    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }

+ Response 404 (application/json) 
    
    + Body

            {
                "code": "NOT_FOUND",
                "detail_code": "",
                "message": "Item not found"
            }

### GET

+ Request (application/json)

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8
    
+ Response 200 (application/json)
    + Attributes (APIKey)

+ Response 401 (application/json)

    
    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }

+ Response 404 (application/json) 
    
    + Body

            {
                "code": "NOT_FOUND",
                "detail_code": "",
                "message": "Item not found"
            }

### DELETE

+ Request (application/json)

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8
    
+ Response 204 (application/json)

+ Response 401 (application/json)

    
    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }

# Data Structures

## APIKey(object)
 + key: `c42935fbaba1059527d4533d948dbc2addc93e3190a50c9b0c9e94c37484` (string, required) - 60-character alphanumeric secret key for API users.
 + `key_id`: `550e8400-e29b-41d4-a716-446655440000` (string, required) - GUID
 + `user_id`: `4` (number, required) - user_id
# Group Auth API V2

## Login [/v2/auth/login]

### POST

+ Request (application/json)
    
    + Attributes (Login)

+ Response 200 (application/json)
    + Attributes (Token)

# Data Structures

## Login(object)
 + key: `c42935fbaba1059527d4533d948dbc2addc93e3190a50c9b0c9e94c37484` (string, [required](required)) - 60-character alphanumeric secret key for API users.
 + `key_id`: `550e8400-e29b-41d4-a716-446655440000` (string, required) - GUID
 + duration: `43200` (number, optional) - duration of the session in seconds. Min - 900(15 minutes), Max - 129600(36 hours), Default - 43200(12 hours)

## Token(object)
 + token: `7ca57767ae16bb878f62946b0a8bb0385c9607d8` (string, required) - X-Auth-Token
 + expiration_time: `2017-10-02T00:00:00Z` (string, required) - UTC time of token expiration
# Group Auth API - DEPRECATED

## Login [/auth/login]

### POST

If user credentials are correct, the API returns user info and authentication `token`, which must be passed in all subsequent requests to any route that requires authentication. There are three ways to pass it: through `X-Auth-Token` header, using query argument or cookie named `token`. Each time user logs in a session is created for them.

+ Request (application/json)
    
   + Attributes (Login Post)

+ Response 200 (application/json)
    

   + Attributes (Login Response)


## Logout [/auth/logout]

### GET

+ Request

    + Headers

            X-Auth-Token: <Authorization Token>

+ Response 200

User is successfully logged out

    + Body

# Data Structures

## Login Post(object)
+ `username`: `john.doe@example.com` (string, required) - username
+ `password`: `p@ssword` (string, required) - password
+ `app_id`: `bd5dcfa5fdf61b3cc03ae044858b0ac9` (string, required) - API key of your application
 
## Login Role(object)
+ `id`: 1 (number)
+ `name`: `Super Admin` (string)

## Login Company(object)
+ `id`: 1 (number)
+ `name`: `Comany name` (string) 

## Login Response(object)
+ `user_id`: `1` (number),
+ `user_name`: `some@email.com` (string),
+ `token`: `28b3ebe604c6fb8c393a4c3ac93a3765` (string),
+ `first_name`: `John` (string),
+ `last_name`: `Doe` (string),
+ `team_restriction`: `restrict-none` (enum[string]),
    + Members:
        - `restrict-none` - Show all details (Default mode)
        - `restrict-prices` - Hide resource prices and savings
        - `restrict-details` - Hide all prices,savings, and detail
+ `role` (Login Role)
+ `company` (Login Company)
+ `user_pref`: `{}` (string) - User preference field in JSON format defined by Console

# Group Credentials API 

An API that provides operations for interacting with ParkMyCloud credentials.

# Overview

## About

https://parkmycloud.atlassian.net/wiki/spaces/PMCUG/pages/170989/Cloud+Credential+Management

## Authentication

All requests to this API must be authenticated using an authorization token. The
authorization token must be provided using the `X-Auth-Token` request header.
For example:

```http
X-Auth-Token: cd57fa5140a0c7bf0e6f3bed9b109771
```

For details on how to obtain an authorization token, see the documentation for
the `/auth` API.

## List and Create Credentials [/creds{?for}]
A resource representing cloud service provider credentials

### GET

+ Parameters
    + for: `dropdown` (string,optional) - Will show all creds for listing
        + Members
            - `dropdown` - to display in dropdown

+ Request

    + Headers

            X-Auth-Token: <Authorization Token>

+ Response 200 (application/json)
    
    + Attributes (List Credentials)


+ Response 401 (application/json)

    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }

+ Response 403 (application/json)

    + Body
    
            {
                "code": "INVALID_PERMISSIONS",
                "detail_code": "",
                "message": "not authorized to access this route"
            }

### POST

+ Request (application/json)

    + Headers

            X-Auth-Token: <Authorization Token>
    
    + Attributes (Post Credential)

+ Response 200 (application/json)

    New credential was successfully created

    + Attributes (Credential Post Response)

+ Response 400 (application/json)

    Wrong request syntax or data validation failure

    + Body
    
            {
                "code": "INVALID_REQUEST",
                "detail_code": "",
                "message": "Failed to validate users"
            }

+ Response 401 (application/json)

    Invalid authentication token
    
    + Body

+ Response 403 (application/json)

    User is not allowed to create credentials in the provided team. Only users with roles Super Admin and Team Leader are allowed to create credentials.

    + Body
        
            {
              "message_text": "string",
              "data": "string"
            }

+ Response 409 (application/json)

    AWS account of the provided credential already exists in the system
    
    + Body
        
            {
              "message_text": "string",
              "data": "string"
            }

##  Disable Cred By ID [/creds/disable/{id}]

A resource representing a specific credential

+ Parameters
  + id: `1` (number, required) - credential id

### PUT

+ Request (application/json)

    + Headers

            X-Auth-Token: <Authorization Token>

+ Response 204 (application/json)

+ Response 400 (application/json)

    Wrong request syntax or data validation failure

    + Body

            {
              "message_text": "string",
              "data": "string"
            }

+ Response 401 (application/json)

    Invalid authentication token

    + Body

+ Response 403 (application/json)

    User is not allowed to update the credential.

    + Body

            {
              "message_text": "string",
              "data": "string"
            }

+ Response 409 (application/json)

    Duplicate AWS account.

    + Body

            {
              "message_text": "string",
              "data": "string"
            }

##  Update/Delete Creds By ID [/creds/{id}]

A resource representing a specific credential

+ Parameters
  + id: `1` (number, required) - credential id

### PUT

+ Request (application/json)

    + Headers

            X-Auth-Token: <Authorization Token>

    + Attributes (Post Credential)

+ Response 200 (application/json)

    Credential was successfully updated

    + Body           
    
            {
              "message_text": "string",
              "data": "string"
            }
            
+ Response 400 (application/json)

    Wrong request syntax or data validation failure

    + Body
    
            {
              "message_text": "string",
              "data": "string"
            }

+ Response 401 (application/json)

    Invalid authentication token
    
    + Body

+ Response 403 (application/json)

    User is not allowed to update the credential.
    
    + Body
        
            {
              "message_text": "string",
              "data": "string"
            }

+ Response 409 (application/json)

    Duplicate AWS account.
    
    + Body
        
            {
              "message_text": "string",
              "data": "string"
            }

### DELETE

+ Request (application/json)

    + Headers

            X-Auth-Token: <Authorization Token>

    + Attributes (Post Credential)

+ Response 204 (application/json)

    Credential was successfully deleted

    + Body            
            
+ Response 400 (application/json)

    Wrong request syntax or credential can not be deleted for some reason.

    + Body
    
            {
              "message_text": "string",
              "data": "string"
            }

+ Response 401 (application/json)

    Invalid authentication token
    
    + Body

+ Response 403 (application/json)

    User is not allowed to delete the credential
    
    + Body
        
            {
              "message_text": "string",
              "data": "string"
            }

+ Response 409 (application/json)

    Credential can not be deleted, because it is locked by another operation like ingestion.
    
    + Body
        
            {
              "message_text": "string",
              "data": "string"
            }

## Get Example AWS Policy [/creds/example-aws-policy]

Returns recommended IAM Policy for credentials

### GET

+ Request

    + Headers

            X-Auth-Token: <Authorization Token>

+ Response 200 (application/json)
    
    Returns recommended IAM Policy
    
    + Body

## Get Example Azure Role [/creds/example-azure-role]

Returns recommended Azure Policy for credentials

### GET

+ Request

    + Headers

            X-Auth-Token: <Authorization Token>

+ Response 200 (application/json)
    
    Returns recommended Azure Policy
    
    + Body

##  Credential Ingenstion [/creds/ingest/{id}]

A resource representing the ingestion of a given credential

+ Parameters
  + id: `1` (number, required) - credential id

### GET

Get the information about the latest ingestion of the specified credential

+ Request 

    + Headers

            X-Auth-Token: <Authorization Token>
            
+ Response 200 (application/json)

    Returns Ingestion object. If credential has not been ingested yet, returns null.

    + Attributes (Credential Ingestion Status)
            
+ Response 401

    Unauthorized

    + Body

+ Response 403 (application/json)

    User is not allowed to access the credential.
    
    + Attributes (Credential Ingestion No Access)


+ Response 404 

    Credential not found
    
    + Body
    
### POST /creds/ingest/{id}{?force}

Launch process of discovering instances of a credential

+ Parameters
  + id: `1` (number, required) - credential id
  + force: `true` (string, optional) - query parameter to enforce the discovery

+ Request 

    + Headers

            X-Auth-Token: <Authorization Token>

+ Response 200 (application/json)

    Ingestion started

    + Attributes (Credential Ingestion Status)
            

+ Response 400

    Invalid request syntax or invalid credential
    
    + Body

+ Response 401

    Unauthorized

    + Body

+ Response 403 (application/json)

    User is not allowed to ingest the credential.
    
    + Body 
    
+ Response 404 

    Credential not found
    
    + Body
    
+ Response 409 

    Ingestion already in progress
    
    + Body
    
# Data Structures 

## Post Credential(object)
 + `name`: `AWS Dev` (string, required) - credential name
 + `iam_cred_type`: `IAM Role` (enum[string], required) - credential type
   - `IAM Role` - AWS Role
   - `IAM User` - AWS User
   - `g_sa` - GCP Service Account
   - `az_sp` - Azure Service Principal
   - `az_ea` - Azure Enterprise Agreement
   - `ali_arn` - Alibaba RAM Role
 + `default_ingest_team_id`: `1` (number, required) - default team id
 + `provider_id`: `1` (enum[number], required) - cloud service provider id
   - `1` - AWS
   - `2` - GCP
   - `3` - Azure
   - `4` - Alibaba
 + `access_key_id`: `1234` (string) - access key id
 + `discoverable`: `true` (boolean, optional) - optional field to set cred discoverable state, make sense only for update
 + `secret_access_key`: `1234` (string) - secret access key id
 + `partition`: `aws` (string) - AWS Partition, one of `aws` or `aws-cn`
 + `iam_role_external_id`: `1234` (string) - AWS IAM role external id
 + `iam_role_arn`: `1234` (string) - AWS Role ARN
 + `az_subscription_id`: `1234` (string) - Azure subscription id
 + `az_tenant_id`: `1234` (string) - Azure tenant id
 + `az_client_id`: `1234` (string) - Azure client id
 + `az_client_secret`: `1234` (string) - Azure client secret
 + `az_access_key_expire_date`: `2019-12-21T00:00:00+03:00` (string) - Azure expiration access date
 + `az_enrollment_id`: `1234` (string) - Enrollment number for Azure account
 + `az_primary_access_key`: `xxxxx` (string) - Azure primary key
 + `az_primary_access_key_expire_date`: `2019-12-21T00:00:00+03:00` (string) - Azure primary key expiration date
 + `az_secondary_access_key`: `xxxxx` (string) - Azure secondary key
 + `az_secondary_access_key_expire_date`: `2019-12-21T00:00:00+03:00` (string) - Azure secondary key expiration date
 + `gcp_sa_key`: `1234` (string) - GCP SA key
 + `gcp_project_id`: `1234` (string) - GCP project if

## List Credentials(object)
 + `message_text`: `success` (string) - request status
 + `data` (array[Credential]) - list of teams in the requesters organization

## Credential(object)
 + `id`: `123` (number) - team id 
 + `name`: `AWS Dev` (string) - credential name
 + `iam_cred_type`: `IAM Role` (enum[string]) - credential type
   - `IAM Role` - AWS Role
   - `IAM User` - AWS User
   - `g_sa` - GCP Service Account
   - `az_sp` - Azure Service Principal
   - `ali_arn` - Alibaba RAM Role
 + `default_ingest_team_id`: `1` (number) - default team id
 + `last_discovery`: `2019-10-16 09:39:39` (string) - time of last successful discover for the credential in utc
 + `provider_id`: `1` (enum[number]) - cloud service provider id
   - `1` - AWS
   - `2` - GCP
   - `3` - Azure
   - `4` - Alibaba
 + `access_key_id`: `1234` (string) - access key id
 + `partition`: `aws` (string) - AWS Partition, one of `aws` or `aws-cn`
 + `iam_role_external_id`: `1234` (string) - AWS IAM role external id
 + `iam_role_arn`: `1234` (string) - AWS Role ARN

## Credential Post Response
 + `message_text`: `success` (string) - request status
 + `data` (object) - new credential
   + `id`: `1` (number) - new credential id 

## Credential Ingestion Status
 + `cred_id`: `1` (number) - credential id
 + `state`: `completed` (string) - ingestion status
 
## Credential Ingestion No Access
 + `code`: `VALIDATION_ERROR` (string) - A string constant which identifies an error. By convention this code is short and written in all caps.
 + `message`: `string` (string) - An optional human readable string, which can be presented to the user on the client side.
 + `details`: `string` (string) - Arbitrary object with detailed information about the error. For example, in case of validation error, this can be an object, where attributes are field names and values are error messages associated with those fields.
 
 
 
 

# Group Organizations API V2

## Organizations [/v2/organizations]

### Get Policy Application Mode [GET /v2/organizations/policy-mode]

Gets the policy application mode for an organization.

+ Request

    + Headers

            Accept: application/json
            X-Auth-Token: <Authorization Token>

+ Response 200 (application/json)

    + Attributes
        + data (required, PolicyMode)

### Set Policy Application Mode [PUT /v2/organizations/policy-mode]

Sets the policy application mode for an organization.

::: note
Only users with "Super Admin" permissions are allowed to set an organization's
policy application mode.
:::

+ Request

    + Headers
            Accept: application/json
            Content-Type: application/json
            X-Auth-Token: <Authorization Token>

    + Attributes (required, PolicyMode)

+ Response 200 (application/json)

+ Response 403 (application/json)

    + Body
            {
                "code": "FORBIDDEN",
                "detail_code": "",
                "message": "Insufficient permissions"
            }

### Get organization's info [GET /v2/organizations/info]

Gets info of the current user's organization.

+ Request

    + Headers
        Accept: application/json
        X-Auth-Token: <Authorization Token>

+ Response 200 (application/json)

    + Attributes
        + data (Info)

+ Response 403 (application/json)

    + Body
        {
            "code": "FORBIDDEN",
            "detail_code": "",
            "message": "Insufficient permissions"
        }

### Patch organization's info [PATCH /v2/organizations/info]

Patches specific fileds of the current user's organization info.

::: note
Only users with "Super Admin" or "Purchasing" permissions are allowed to patch organization's info.
:::

+ Request

    + Headers
        Accept: application/json
        Content-Type: application/json
        X-Auth-Token: <Authorization Token>

    + Attributes (required, Info)

+ Response 200 (application/json)

+ Response 403 (application/json)

    + Body (object)
        {
            "code": "FORBIDDEN",
            "detail_code": "",
            "message": "Insufficient permissions"
        }


### Get an organization's address [GET /v2/organizations/address]

Gets an address of the current user's organization.

+ Request

    + Headers
        Accept: application/json
        X-Auth-Token: <Authorization Token>

+ Response 200 (application/json)

    + Attributes
        + data (Address)

+ Response 403 (application/json)

    + Body (object)
        {
            "code": "FORBIDDEN",
            "detail_code": "",
            "message": "Insufficient permissions"
        }

### Patch organization's address [PATCH /v2/organizations/address]

Patches specific fields of the current user's organization address.

::: note
Only users with "Super Admin" or "Purchasing" permissions are allowed to patch an organization's
address.
:::

+ Request

    + Headers
        Accept: application/json
        Content-Type: application/json
        X-Auth-Token: <Authorization Token>

    + Attributes (required, Address)

+ Response 200 (application/json)

+ Response 403 (application/json)

    + Body (object)
        {
            "code": "FORBIDDEN",
            "detail_code": "",
            "message": "Insufficient permissions"
        }

### Get Organization Notification Setting [GET /v2/organizations/notification/setting]

Gets the notification settings for an organization.

+ Request

    + Headers

            Accept: application/json
            X-Auth-Token: <Authorization Token>

+ Response 200 (application/json)

    + Attributes (GET Notification Setting)

### Set Organization Notification Setting [PATCH /v2/organizations/notification/setting]

Set/Update the notification settings for an organization.

+ Request

    + Headers

            Accept: application/json
            X-Auth-Token: <Authorization Token>

    + Attributes (required, PATCH Notification Setting)

+ Response 200 (application/json)

    + Attributes (GET Notification Setting)

# Data Structures

## PATCH Notification Setting (object)
+ throttle_error_for: `14400000000000` (required, number) - time in nanoseconds to throttle errors notification

## GET Notification Setting (PATCH Notification Setting)
+ organization_id: `1` (required, number) - id of organization

## Info (object)
+ name (optional, string)

## Address (object)
+ country (optional, string)
+ zip_code (optional, string)
+ state_province (optional, string)
+ city (optional, string)
+ addr_1 (optional, string)
+ addr_2 (optional, string)

## PolicyMode (object)
+ policy_mode (required, enum[string]) - The organization's policy application mode
    + at_discovery
    + continuous

# Group Override limitation API V2
An API that allow to configure override limitation and checking by this limits.

Only Super Admin from team or Team Lead with feature `override_limit` allowed to access this API.

##  Override limitation Endpoint by team [/v2/override-limit/team/#team_id#]

### GET

+ Request (application/json)

    + Headers
    
            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

    + Parameters
        + team_id: `1` (number, required) - unique Team ID

+ Response 200 (application/json)

    + Attributes(OverrideLimit)

+ Response 401 (application/json)

    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }

+ Response 404 (application/json) 
    
    + Body

            {
                "code": "NOT_FOUND",
                "detail_code": "",
                "message": "No limit set"
            }


### PUT

+ Request (application/json)

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

    + Attributes (OverrideLimit)

+ Response 200 (application/json)

    + Attributes (OverrideLimit)

+ Response 401 (application/json)

    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }


### DELETE

+ Request (application/json)

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 204 (application/json)

+ Response 401 (application/json)

    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }

+ Response 404 (application/json) 
    
    + Body

            {
                "code": "NOT_FOUND",
                "detail_code": "",
                "message": "Team not found"
            }


##  Override limitation Endpoint [/v2/override-limit/available?res_id=18&res_id=93&res_id=83]

### GET

+ Request (application/json)

    + Headers
    
            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 200 (application/json)

    + Attributes (OverrideAvailable)

+ Response 401 (application/json)

    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }

+ Response 404 (application/json) 
    
    + Body

            {
                "code": "UNAVAILABLE_RESOURCE",
                "detail_code": "",
                "message": "Resource 83 is unavailable for you"
            }

# Data Structures

## OverrideLimit

 + `limit_sec`: `7200` (number, required) - maximum duration of limit in seconds 

## OverrideAvailable

 + `available_sec`: `7200` (number, required) - available duration of override in seconds 

# Group Policies API V2

An API that provides operations for interacting with ParkMyCloud policies.

## About

A policy consists of a set of selection/filtration criteria and a set of actions
to be taken against any resource that matches the criteria. Each policy also has
a 0-based position within the list of all policies for an organization.

## Authentication

All requests to this API must be authenticated using an authorization token. The
authorization token must be provided using the `X-Auth-Token` request header.
For example:

```http
X-Auth-Token: cd57fa5140a0c7bf0e6f3bed9b109771
```

For details on how to obtain an authorization token, see the documentation for
the `/auth` API.

## Policies [/v2/policies]

### List Policies [GET /v2/policies{?criteria,page,pageSize}]

Fetches the list of all policies for the current user's organization.

+ Parameters

    + criteria: true (optional, boolean) - Whether to include the `criteria` field for each policy in the response.

        + Default: true
    + page: 1 (optional, number) - The 1-index page of results to fetch.

        + Default: 1
    + pageSize: 100 (optional, number) - The number of results per page. The maximum allowed value is 100.

        + Default: 100

+ Request With Criteria

    + Headers

            Accept: application/json
            X-Auth-Token: <Authorization Token>

+ Response 200 (application/json)

    + Attributes
        + data (ReadPolicyPayloadList)

+ Request Without Criteria

    + Headers

            Accept: application/json
            X-Auth-Token: <Authorization Token>

+ Response 200 (application/json)

    + Attributes
        + data (ReadPolicyPayloadNoCriteriaList)

### Get Policy [GET /v2/policies/policy/{id}]

Fetches a single policy, given its unique ID.

+ Parameters

    + id: abcd1234 (required, string) - The unique ID of the policy to retrieve

+ Request

    + Headers

            Accept: application/json
            X-Auth-Token: <Authorization Token>

+ Response 200 (application/json)

    + Attributes
        + data (ReadPolicyPayload)

+ Response 404 (application/json)

    + Body

            {
                "code": "NOT_FOUND",
                "detail_code": "",
                "message": "Policy not found"
            }

### Create Policy [POST /v2/policies]

Creates a new policy, given a payload of policy properties.

::: note
Only users with "Super Admin" permissions are allowed to create policies.
:::

+ Request

    + Headers

            Accept: application/json
            Content-Type: application/json
            X-Auth-Token: <Authorization Token>

    + Attributes (required, CreatePolicyPayload)

+ Response 201 (application/json)

    + Attributes
        + data (ReadPolicyPayload)

+ Response 400 (application/json)

    + Body

            {
                "code": "BAD_REQUEST",
                "detail_code": "",
                "message": "Invalid request data"
            }

+ Response 403 (application/json)

    + Body

            {
                "code": "FORBIDDEN",
                "detail_code": "",
                "message": "Insufficient permissions"
            }

### Update Policy [PUT /v2/policies/policy/{id}]

Updates a policy, given its unique ID and a payload of updated policy properties.

::: note
Only users with "Super Admin" permissions are allowed to update policies.
:::

::: warning
This call does not support partial updates. The entire definition of the policy
must be specified.
:::

+ Parameters

    + id: abcd1234 (required, string) - The unique ID of the policy to update

+ Request

    + Headers

            Accept: application/json
            Content-Type: application/json
            X-Auth-Token: <Authorization Token>

    + Attributes (required, CreatePolicyPayload)

+ Response 200 (application/json)

    + Attributes
        + data (ReadPolicyPayload)

+ Response 400 (application/json)

    + Body

            {
                "code": "BAD_REQUEST",
                "detail_code": "",
                "message": "Invalid request data"
            }

+ Response 403 (application/json)

    + Body

            {
                "code": "FORBIDDEN",
                "detail_code": "",
                "message": "Insufficient permissions"
            }

### Delete Policy [DELETE /v2/policies/policy/{id}]

Deletes a policy, given its unique ID.

::: note
Only users with "Super Admin" permissions are allowed to delete policies.
:::

+ Parameters

    + id: abcd1234 (required, string) - The unique ID of the policy to delete

+ Request

    + Headers

            Accept: application/json
            X-Auth-Token: <Authorization Token>

+ Response 204 (application/json)

+ Response 403 (application/json)

    + Body

            {
                "code": "FORBIDDEN",
                "detail_code": "",
                "message": "Insufficient permissions"
            }

## Reapply Policy Actions [PUT /v2/policies/reapply]

Reapplies the actions of all policies.

::: note
Only users with "Super Admin" permissions are allowed to reapply policy actions.
:::

+ Request

    + Headers

            Accept: application/json
            X-Auth-Token: <Authorization Token>

+ Response 200 (application/json)

+ Response 403 (application/json)

    + Body

            {
                "code": "FORBIDDEN",
                "detail_code": "",
                "message": "Insufficient permissions"
            }

## Reorder Policies [PUT /v2/policies/order]

Updates the order of all policies for the current user's organization.

::: note
Only users with "Super Admin" permissions are allowed to modify the order of policies.
:::

::: note
The ID for every policy must be provided, and all provided IDs must correspond
to policies that actually exist. If any policy IDs are omitted, an error will be
returned with a `detail_code` of `MISSING_ID`. If any policy IDs provided do not
correspond to a policy that exists, an error will be returned with a `detail_code`
of `INVALID_ID`.
:::

+ Request

    + Headers

            Accept: application/json
            X-Auth-Token: <Authorization Token>

    + Body

            ["abcd1234", "efgh5678"]

    + Attributes (required, PolicyOrder)

+ Response 200 (application/json)

+ Response 400 (application/json)

    + Body

            {
                "code": "INVALID_REQUEST",
                "detail_code": "MISSING_ID",
                "message": "Missing ID: abcd1234"
            }

+ Response 403 (application/json)

    + Body

            {
                "code": "FORBIDDEN",
                "detail_code": "",
                "message": "Insufficient permissions"
            }

## Test Policy Criteria [POST /v2/policies/test]

Returns a subset of resources that match the specified policy critiera.

::: note
Only users with "Super Admin" permissions are allowed to test policy critiera.
:::

+ Request

    + Headers

            Accept: application/json
            Content-Type: application/json
            X-Auth-Token: <Authorization Token>

    + Attributes (required, CreatePolicyPayload)

+ Response 200 (application/json)

    + Attributes
        + data (object)
            + resources (array[ResourceOutput], fixed-type) - A list of resources that match the specified policy's criteria
            + is_subset (boolean) - `true` if the list of resources is only a subset of the matching resources (otherwise, `false`)

+ Response 400 (application/json)

    + Body

            {
                "code": "BAD_REQUEST",
                "detail_code": "",
                "message": "Invalid request data"
            }

+ Response 403 (application/json)

    + Body

            {
                "code": "FORBIDDEN",
                "detail_code": "",
                "message": "Insufficient permissions"
            }

# Data Structures

## ReadPolicyPayload (object)

+ id: abcd1234 (required, string) - The unique ID of the policy
+ name: Policy 01 (required, string) - The name of the policy. Policy names must be unique within an organization. Max length is 64 characters.
+ position: 1 (required, number) - The policy's 0-based position within the list of all policies
+ criteria (required, PolicyCriteria) - The list of selection criteria
+ actions (required, ActionsOutput) - The set of actions to take for applicable resources

## ReadPolicyPayloadNoCriteria (object)

+ id: abcd1234 (required, string) - The unique ID of the policy
+ name: Policy 01 (required, string) - The name of the policy. Policy names must be unique within an organization. Max length is 64 characters.
+ position: 1 (required, number) - The policy's 0-based position within the list of all policies
+ actions (required, ActionsOutput) - The set of actions to take for applicable resources

## ReadPolicyPayloadList (array[ReadPolicyPayload], fixed-type)

## ReadPolicyPayloadNoCriteriaList (array[ReadPolicyPayloadNoCriteria], fixed-type)

## CreatePolicyPayload (object)

+ name: Policy 01 (required, string) - The name of the policy. Policy names must be unique within an organization. Max length is 64 characters.
+ criteria (required, PolicyCriteria) - The list of selection criteria
+ actions (required, ActionsInput) - The set of actions to take for applicable resources

## PolicyOrder (array[string], fixed-type)

### Sample

+ ["abcd1234", "efgh5678"]

## PolicyCriteria (object)

+ condition: OR (required, enum[string])
    + AND
    + OR
+ rules (required, array[PolicyRule, PolicyCriteriaNested], fixed-type)

## PolicyCriteriaNested (object)

+ condition: AND (required, enum[string])
    + AND
    + OR
+ rules (required, array[PolicyRule])

## PolicyRule (object)

+ id: resource_name (required, enum[string]) - The rule's unique identifier
    + any_tag_name
    + any_tag_value
    + any_tag_name_value
    + all_tag_names
    + all_tag_values
    + all_tag_names_values
    + credential_name
    + location
    + provider_id
    + purchase_option
    + resource_name
    + type
+ operator: equal (required, enum[string]) - The rule's logical operator
    + equal
    + not_equal
    + in
    + not_in
    + less
    + less_or_equal
    + greater
    + greater_or_equal
    + between
    + not_between
    + begins_with
    + not_begins_with
    + contains
    + not_contains
    + ends_with
    + not_ends_with
    + is_empty
    + is_not_empty
+ value: My Team (required, *)

## ActionsInput (object)

+ assign_team (optional, object) - The team to which applicable resources should be assigned
    + id: 10 (required, number) - The team's ID
+ assign_schedule (optional, object) - The schedule that should be applied to applicable resources
    + id: 200 (required, number) - The schedule's ID
+ detach_schedule(optional, boolean) - Whether to detach any assigned schedule from applicable resources
+ set_restriction (optional, enum[string]) - The type of restriction to apply to applicable resources
    + none - No restrictions
    + override_only - Schedules may be overridden, but not added or removed.
    + never_park - The resource may never be parked
+ set_asg_parking_method (optional, enum[string]) - The ASG parking method to apply to applicable resources
    + scale - Scale down the number of instances when parking
    + suspend - Suspend ASG processes and stop instances

## ActionsOutput (object)

+ assign_team (optional, object) - The team to which applicable resources should be assigned
    + id: 10 (required, number) - The team's ID
    + name: My Team (required, string) - The team's name
+ assign_schedule (optional, object) - The schedule that should be applied to applicable resources
    + id: 200 (required, number) - The schedule's ID
    + name: Schedule 01 (required, string) - The schedule's name
+ detach_schedule(optional, boolean) - Whether to detach any assigned schedule from applicable resources
+ set_restriction (optional, enum[string]) - The type of restriction to apply to applicable resources
    + none - No restrictions
    + override_only - Schedules may be overridden, but not added or removed.
    + never_park - The resource may never be parked
+ set_asg_parking_method (optional, enum[string]) - The ASG parking method to apply to applicable resources
    + scale - Scale down the number of instances when parking
    + suspend - Suspend ASG processes and stop instances

## ResourceOutput (object)

+ id: 1 (required, number) - The resource's unique ID
+ name: Some Resource (required, string) - The resource's name
+ resource_type: asg (required, enum[string]) - The resource's type
    + asg
    + compute
    + lg
    + rds
+ instance_size: m2.large (required, string) - The resource's instance size
+ purchase_option: pre (optional, string) - The resource's purchase option
+ location: westus (required, string) - The resource's location
+ provider: azure (required, enum[string]) - The resource's cloud service provider
    + alibaba
    + aws
    + azure
    + gcp
+ credential: `PMC-2` (required, string) - The resource's credential name
+ team: My First Team (required, string) - The resource's team name
+ tags (optional, TagList) - The resource's tags

## Policy Tag (object)

+ key: Foo (required, string) - The tag's key/name
+ value: Bar (required, string) - The tag's value

## TagList (array[Policy Tag], fixed-type)

### Sample

+ [{"key": "Foo", "value": "Bar"}]

# Group Providers API V2

## Providers [/v2/providers]

### List Providers [GET /v2/providers{?locations}]

Fetches the list of providers.

+ Parameters

    + locations: true (optional, boolean) - Whether to include the list of each provider's locations

        + Default: true

+ Request With Locations

    + Headers

            Accept: application/json
            X-Auth-Token: <Authorization Token>

+ Response 200 (application/json)

    + Attributes
        + data (array[Provider], fixed-type)

+ Request Without Locations

    + Headers

            Accept: application/json
            X-Auth-Token: <Authorization Token>

+ Response 200 (application/json)

    + Attributes
        + data (array[ProviderNoLocations], fixed-type)

# Data Structures

## Provider (object)

+ id: 1 (required, number) - The unique ID of the provider
+ name: AWS (required, string) - The name of the provider
+ locations (required, array[Location], fixed-type) - The provider's locations

## ProviderNoLocations (object)

+ id: 1 (required, number) - The unique ID of the provider
+ name: AWS (required, string) - The name of the provider

## Location (object)

+ code: us-east-1 (required, string) - The location's code
+ name: `US East (N. Virginia)` (required, string) - The location's name
# Group Rightsizing Recommendation Query API

Rightsizing Recommendation Query is a service that aggregates info about
all OPEN rightsizing recommendations. This API allows to list, filter
and sort those aggregated records.

## Rightsizing Query [/v2/rightsizing/query/?ids={ids}&resource_ids={resource_ids}&parent_ids={parent_ids}&team_ids={team_ids}&cred_ids={cred_ids}&providers={providers}&resource_name={resource_name}&resource_kind={resource_kind}&resource_location={resource_location}&parent_kind={parent_kind}&team_name={team_name}&cred_name={cred_name}&search={search}&updated_before={updated_before}&updated_after={updated_after}&offset={offset}&limit={limit}&order={order}]

+ Parameters
  + ids: `1,2,3` (string, optional) - recommendation ids (comma separated list of integers)
  + resource_ids: `3,5,7` (string, optional) - resource ids (comma separated list of integers)
  + parent_ids: `8,9` (string, optional) - parent resource ids (comma separated list of integers)
  + team_ids: `2,6` (string, optional) - team ids (comma separated list of integers)
  + cred_ids: `1,9,4` (string, optional) - team ids (comma separated list of integers)
  + providers: `aws,gcp` (string, optional) - cloud provider symbolic ids (comma separated list of strings).
      Possible values:
      - `aws`
      - `gcp`
      - `azure`
      - `alibaba`
  + resource_name (string, optional) - resource name (case insensitive partial matching)
  + resource_kind (enum[string], optional) - resource type.
      Possible values:
      - `compute`
      - `asg`
      - `lg`
      - `rds`
  + resource_location (string, optional) - resource location (case insensitive partial matching)
  + resource_size (string, optional) - current resource size (case insensitive partial matching)
  + target_size (string, optional) - target resource size (case insensitive partial matching)
  + parent_name (string, optional) - parent resource name (case insensitive partial matching)
  + parent_kind (enum[string], optional) - parent resource type.
      Possible values:
      - `compute`
      - `asg`
      - `lg`
      - `rds`
  + team_name (string, optional) - team name (case insensitive partial matching)
  + cred_name (string, optional) - credential name (case insensitive partial matching)
  + search (string, optional) - arbitrary string to look for in all text fields (case insensitive partial matching)
  + updated_after (string, optional) - updated after time (RFC3339 encoded)
  + updated_before (string, optional) - updated before time (RFC3339 encoded)
  + offset: 75 (number, optional) - offset in the whole result set to start returning records at
  + limit: 25 (number, optional) - number of records to return starting from the offset (-1 means no limit)
  + order (enum[string], optional) - order by.
      Possible values:
      - `resource_name`
      - `resource_kind`
      - `resource_location`
      - `resource_price`
      - `target_price`
      - `parent_kind`
      - `provider`
      - `projected_savings`
      - `team_name`
      - `cred_name`
      - `updated_at`
      - `-resource_name`
      - `-resource_kind`
      - `-resource_location`
      - `-resource_size`
      - `-resource_price`
      - `-target_size`
      - `-target_price`
      - `-parent_name`
      - `-parent_kind`
      - `-provider`
      - `-projected_savings`
      - `-team_name`
      - `-cred_name`
      - `-updated_at`

### GET

+ Request (application/json)

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 200 (application/json)

    + Attributes (RightsizingQueryListPage)


+ Response 403 (application/json)

    + Body

            {
                "code": "FORBIDDEN",
                "detail_code": "",
                "message": "Insufficient permissions"
            }

## Data dump CSV [/v2/rightsizing/query/dump/?format={format}]

+ Parameters
  + format: `json` (enum[string], optional) - output format.
      Possible values:
      - `csv`
      - `json`

### GET

+ Request (application/json)

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 200 (text/csv; charset=UTF-8)

    + Headers
     
            Content-decomposition: attachment; fileName=ParkMyCloud_Rightsize_Recommendations_2020_05_18.csv

+ Response 200 (application/json)

    + Attributes (RightsizingQueryDump)


+ Response 403 (application/json)

    + Body

            {
                "code": "FORBIDDEN",
                "detail_code": "",
                "message": "Insufficient permissions"
            }
# Data Structures

## RightsizingQueryListPage
 + total: 1000 (number, required) - total count of items
 + offset: 50 (number, required) - current offset
 + limit: 50 (number, required) - current limit
 + items(array[RightsizingQueryRecord])

## RightsizingQueryDump
 + items(array[RightsizingQueryRecord])

## RightsizingQueryRecord
 + id: 12 (number, required) - rightsizing recommendation id
 + `resource_id`: 33 (number, required) - resource id
 + `resource_kind` (enum[string], required) - resource type
   + Members
    + compute
    + asg
    + lg
    + rds
 + `resource_name`: `DevServer N1` (string, required) - resource name
 + `resource_location`: `us-west-2` (string, required) resource location
 + `resource_size`: `m5.xlarge` (string, required) - current resource size
 + `resource_price`: 0.019 (number, required) - resource houly price (scaled)
 + `target_size`: `r5a.large` (string, required) - target resource size
 + `target_price`: 0.0154 (number, required) - target houly price (scaled)
 + `projected_savings`: 34.75 (number, required) - projected monthly price difference
 + `parent_id`: 177 (number, optional) - parent resource id
 + `parent_name`: `LG-1` (string, required) - parent resource name
 + `parent_kind` (enum[string], optional) - parent resource type
   + Members
    + compute
    + asg
    + lg
    + rds
 + provider (enum[string], optional) - Cloud provider symbolic id
   + Members
    + `aws`
    + `gcp`
    + `azure`
    + `alibaba`
 + `cred_id`: 200 (number, required) - credential ID
 + `cred_name`: `AWS Cred` (string, required) - credential name
 + `team_id`: 250 (number, required) - team ID
 + `team_name`: `Dev Team` (string, required) - team name
 + `is_cluster`: false (boolean, required) - flag indicating the resource is a DB cluster
 + `has_schedule`: false (boolean, required) - flag indicating the resource has an attached schedule
 + `has_metrics`: true (boolean, required) - flag indicating the resource has some metrics available
 + `has_mem_metrics`: false (boolean, required) - flag indicating the resource has MEM metrics available
 + `parent_kind` (enum[string], optional) - parent resource type
 + `updated_at`: `2019-05-03T09:52:55.770725197Z` (string, required) - time of the last update (RFC3339 encoded)
 + `created_at`: `2019-05-03T09:52:55.770725197Z` (string, required) - time of the creation (RFC3339 encoded)

# Group Schedules API V2

***These endpoints are currently in private preview.***

Schedule resource composed of a collection of timespans per day.  Each timespan represents a period of time during which the specified state is requested.  

If no timespans are provided, or there is a gap between timespans, the system will default to an `ignore` state.

## Schedule [/v2/schedules/]

### List [GET /v2/schedules/{?offset,limit}]

+ Parameters
  + offset: 50 (number, optional) - offset in the whole result set to start returning records at
  + limit: 50 (number, optional) - number of records to return starting from the offset (-1 means no limit)
  + name (string, optional) - name of the schedule
  + description (string, optional) - explanation of purpose of schedule
  + type (enum[string], optional) - filter by schedule type
      Possible values:
      - `timespans`
      - `details`
  + order (enum[string], optional) - order by.
      Possible values:
      - `name`
      - `description`
      - `time_zone`
      - `savings`
      - `updated_at`
      - `assigned`
      - `type`
      - `-name`
      - `-description`
      - `-time_zone`
      - `-savings`
      - `-updated_at`
      - `-assigned`
      - `-type`

+ Request (application/json)
    
    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 200 (application/json)
  
    + Attributes (ScheduleV2ListPage)

+ Response 401 (application/json)   
  
    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }

### Create [POST]

+ Request (application/json)
    
    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8
      
    + Attributes (ScheduleV2 POST)

+ Response 201 (application/json)
  
    + Attributes (ScheduleV2 GET)

+ Response 401 (application/json)   
  
    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }

## Schedule By ID [/v2/schedules/{schedule\_id}]

### GET [GET]

+ Request (application/json)
    
    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 200 (application/json)
  
    + Attributes (ScheduleV2 GET)

+ Response 401 (application/json)   
  
    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }

### Delete [DELETE]

+ Request (application/json)
    
    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 204 (application/json)

+ Response 401 (application/json) 
  
    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }

### Update (Partial) [PATCH]

+ Request (application/json)
    
    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8
      
    + Attributes (ScheduleV2 PATCH)

+ Response 200 (application/json)
  
    + Attributes (ScheduleV2 GET)

+ Response 401 (application/json)   
  
    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }


# Data Structures

## ScheduleV2ListPage
 + total: 1000 (number, required) - total count of items
 + offset: 50 (number, required) - current offset
 + limit: 50 (number, required) - current limit
 + items(array[ScheduleV2ListItem])

## ScheduleV2ListItem(ScheduleV2)
 + id: `1` (required, number) - system generated ID for the schedule
 + type: `timespans` (string, required) - specifies one of two types for the schedule
 + url: `https://api.parkmycloud.com/v2/schedules/1` (string, required) - specifies url for GET endpoint to retrieve more information on the schedule
## ScheduleV2(object)
 + name: `always parked` (required, string) - the name of the schedule
 + description: `some description` (optional, string) - a description of the schedule
 + time_zone: `America/Chicago` (string, required) - time zone to used by the schedule in the format of Area/Location (zoneinfo)
 + smartpark: `false` (optional, boolean) - is this schedule generated by smartpark process. ParkMyCloud creates Smartparking schedules based on utilization data
 + savings_pct: `67.32` (optional, number) - calculated savings
 + updated_at: `2020-04-02T12:16:45Z` (optional, string) - last updated time 
 + assigned: `5` (optional, number) - count of resources assigned this schedule

## ScheduleV2 POST(ScheduleV2)
 + timespans (optional, WeeklyTimespansV2)

## ScheduleV2Optional(object)
 + name: `always parked` (optional, string) - the name of the schedule
 + description: `some description` (optional, string) - a description of the schedule
 + time_zone: `America/Chicago` (optional, string) - time zone to used by the schedule in the format of Area/Location (zoneinfo)
 
## ScheduleV2 PATCH(ScheduleV2Optional)
 + timespans (optional, WeeklyTimespansV2)

## ScheduleV2 GET(ScheduleV2 POST)
 + id: `1` (required, number) - system generated ID for the schedule

## ScheduleV2 List(ScheduleV2)
 + timespans (optional, WeeklyTimespansV2)

## WeeklyTimespansV2
 + monday (array[TimespanV2]) - collection of timespans for Monday
 + tuesday (array[TimespanV2]) - collection of timespans for Tuesday
 + wednesday (array[TimespanV2]) - collection of timespans for Wednesday
 + thursday (array[TimespanV2]) - collection of timespans for Thursday
 + friday (array[TimespanV2]) - collection of timespans for Friday
 + saturday (array[TimespanV2]) - collection of timespans for Saturday
 + sunday (array[TimespanV2]) - collection of timespans for Sunday

## TimespanV2
 + state: `on` (required, string) - the desired state
 + begins: `11:00:15` (required, string) - timespan start in 24h format
 + ends: `23:59:59` (required, string) - timespan ends in 24h format
# Group Resource Query API

Resource Query is a service that aggregates info about
resources with information about it credential, team and members. This API allows to list, filter
and sort those aggregated records.

## Query [/v2/resourcequery/?team_ids={team_ids}&cred_ids={cred_ids}&provider={provider}&name={name}&type={type}&location={location}&team_name={team_name}&cred_name={cred_name}&search={search}&state={state}&tags={tags}&info={info}&schedule_name={schedule_name}&has_heatmap_data={has_heatmap_data}&snnoze_until={snooze_until}&offset={offset}&limit={limit}&order={order}]

+ Parameters
  + team_ids: `2,6` (string, optional) - team ids (comma separated list of integers)
  + cred_ids: `1,9,4` (string, optional) - team ids (comma separated list of integers)
  + provider (enum[string], optional) - cloud provider symbolic ids (comma separated list of strings).
      Possible values:
      - `aws`
      - `gcp`
      - `azure`
      - `alibaba`
  + name (string, optional) - resource name (case insensitive partial matching)
  + state (enum[string], optional) - resource state (case insensitive partial matching)
      Possible values:
      - `starting`
      - `running`
      - `stopping`
      - `stopped`
      - `terminating`
      - `terminated`
      - `unknown`
      - `missing`
  + type (enum[string], optional) - resource type.
      Possible values:
      - `compute`
      - `containers`
      - `asg`
      - `lg`
      - `rds`
      - `rds_cluster`
  + tags (string, optional) - resource tags
  + location (string, optional) - resource location (case insensitive partial matching)
  + info (string, optional) - current resource size (case insensitive partial matching)
  + team_name (string, optional) - team name (case insensitive partial matching)
  + cred_name (string, optional) - credential name (case insensitive partial matching)
  + schedule_name (string, optional) - schedule name (case insensitive partial matching)
  + has_heatmap_data (boolean, optional) - show wether resource has heatmap data or not (case insensitive partial matching)
  + snooze_until (string, optional) - snoozed until time (RFC3339 encoded)
  + search (string, optional) - arbitrary string to look for in all text fields (case insensitive partial matching)
  + offset: 75 (number, optional) - offset in the whole result set to start returning records at
  + limit: 25 (number, optional) - number of records to return starting from the offset (-1 means no limit)
  + order (enum[string], optional) - order by.
      Possible values:
      - `name`
      - `type`
      - `provider`
      - `location`
      - `state`
      - `cost`
      - `info`
      - `has_heatmap_data`
      - `schedule_name`
      - `cred_name`
      - `team_name`
      - `recommended`
      - `-name`
      - `-type`
      - `-provider`
      - `-location`
      - `-state`
      - `-cost`
      - `-info`
      - `-has_heatmap_data`
      - `-schedule_name`
      - `-cred_name`
      - `-team_name`
      - `-recommended`

### GET

+ Request (application/json)

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 200 (application/json)

    + Attributes (ResourceQueryListPage)


+ Response 403 (application/json)

    + Body

            {
                "code": "FORBIDDEN",
                "detail_code": "",
                "message": "Insufficient permissions"
            }

## Send report Email [/v2/resourcequery/mail/]

+ Parameters
  + All params accepted by /v2/resourcequery and
  + format: `pdf` Mandatory : Possible values: `csv`, `pdf`
  + receiver: `example@parkmycloud.com` Mandatory : Comma Separated email addresses
### POST

+ Request (application/json)

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 202 (application/json)

    + blank response (Sends a mail)


+ Response 400 (application/json)

    + Body

            {
                "code": "FORBIDDEN",
                "detail_code": "",
                "message": "Bad Request"
            }


# Data Structures

## ResourceQueryListPage
 + total: 1000 (number, required) - total count of items
 + offset: 50 (number, required) - current offset
 + limit: 50 (number, required) - current limit
 + items(array[ResourceQueryRecord])

## ResourceQueryDump
 + items(array[ResourceQueryRecord])

## ResourceQueryRecord
 + id: 12 (number, required) - resource ID
 + `name`: `DevServer N1` (string, required) - resource name
 + `type` (enum[string], required) - resource type
   + Members
    + containers
    + compute
    + asg
    + lg
    + rds
    + rds_cluster
 + provider (enum[string], optional) - Cloud provider symbolic id
   + Members
    + `aws`
    + `gcp`
    + `azure`
    + `alibaba`
 + `location`: `us-west-2` (string, required) resource location
 + `state` (enum[string], required) - resource state
   + Members
    + `starting`
    + `running`
    + `stopping`
    + `stopped`
    + `terminating`
    + `terminated`
    + `unknown`
    + `missing`
 + `cost`: 0.019 (number, required) - resource monthly cost (scaled)
 + `info`: `m5.xlarge` (string, required) - current resource size
 + `has_heatmap_data`: true (boolean, required) - flag indicating the resource has some metrics available
 + `unparkable`: true (boolean, required) - flag indicating the resource parkable or not
 + `restriction` (enum[number], required) - restriction
   + Members
    + 0 - none
    + 1 - never park
    + 2 - override only
 + `schedule_id`: 1 (number, required) - schedule ID
 + `schedule_name`: `AWS` (string, required) - schedule name
 + `schedule_type`: `timespans` (string, optional) - specifies one of two types for the schedule (details/timespans)
 + `schedule_url`: `https://api.parkmycloud.com/v2/schedules/1` (string, optional) - specifies url for GET endpoint to retrieve more information on the schedule
 + `snooze_until`: `2019-05-03T09:52:55.770725197Z` (string, required) - snooze until time (RFC3339 encoded)

 + `cred_id`: 200 (number, required) - credential ID
 + `cred_name`: `AWS Cred` (string, required) - credential name

 + `team_id`: 250 (number, required) - team ID
 + `team_name`: `Dev Team` (string, required) - team name

 + `recommended`: true (boolean, required) - flag indicating the resource has recommendation

# Group Recommendation Query API

Recommendation Query is a service that aggregates info about
all OPEN recommendations. This API allows to list, filter
and sort those aggregated records.

## Query [/v2/recommendationquery/?has_schedule={has_schedule}&types={types}&recommendation_ids={recommendation_ids}&resource_ids={resource_ids}&parent_ids={parent_ids}&team_ids={team_ids}&cred_ids={cred_ids}&providers={providers}&resource_name={resource_name}&resource_kind={resource_kind}&resource_location={resource_location}&parent_kind={parent_kind}&team_name={team_name}&cred_name={cred_name}&search={search}&updated_before={updated_before}&updated_after={updated_after}&offset={offset}&limit={limit}&order={order}]

+ Parameters
  + types: `smartparking,rightsizing` (string, optional) - recommendation types (comma separated list of strings).
      Possible values:
      - `smartparking`
      - `rightsizing`
  + has_schedule (boolean, optional) - show whether resource has schedule or not
  + recommendation_ids: `1,2,3` (string, optional) - recommendation ids (comma separated list of integers)
  + resource_ids: `3,5,7` (string, optional) - resource ids (comma separated list of integers)
  + parent_ids: `8,9` (string, optional) - parent resource ids (comma separated list of integers)
  + team_ids: `2,6` (string, optional) - team ids (comma separated list of integers)
  + cred_ids: `1,9,4` (string, optional) - team ids (comma separated list of integers)
  + providers: `aws,gcp` (string, optional) - cloud provider symbolic ids (comma separated list of strings).
      Possible values:
      - `aws`
      - `gcp`
      - `azure`
      - `alibaba`
  + resource_name (string, optional) - resource name (case insensitive partial matching)
  + resource_kind (enum[string], optional) - resource type.
      Possible values:
      - `containers`
      - `compute`
      - `asg`
      - `lg`
      - `rds`
  + resource_location (string, optional) - resource location (case insensitive partial matching)
  + resource_size (string, optional) - current resource size (case insensitive partial matching)
  + target_size (string, optional) - target resource size (case insensitive partial matching)
  + parent_name (string, optional) - parent resource name (case insensitive partial matching)
  + parent_kind (enum[string], optional) - parent resource type.
      Possible values:
      - `compute`
      - `asg`
      - `lg`
      - `rds`
  + team_name (string, optional) - team name (case insensitive partial matching)
  + cred_name (string, optional) - credential name (case insensitive partial matching)
  + search (string, optional) - arbitrary string to look for in all text fields (case insensitive partial matching)
  + updated_after (string, optional) - updated after time (RFC3339 encoded)
  + updated_before (string, optional) - updated before time (RFC3339 encoded)
  + offset: 75 (number, optional) - offset in the whole result set to start returning records at
  + limit: 25 (number, optional) - number of records to return starting from the offset (-1 means no limit)
  + order (enum[string], optional) - order by.
      Possible values:
      - `quality`
      - `resource_name`
      - `resource_kind`
      - `resource_location`
      - `resource_cost`
      - `target_price`
      - `parent_kind`
      - `provider`
      - `projected_savings`
      - `projected_savings_percent`
      - `team_name`
      - `cred_name`
      - `updated_at`
      - `-quality`
      - `-resource_name`
      - `-resource_kind`
      - `-resource_location`
      - `-resource_size`
      - `-resource_cost`
      - `-target_size`
      - `-target_price`
      - `-parent_name`
      - `-parent_kind`
      - `-provider`
      - `-projected_savings`
      - `-projected_savings_percent`
      - `-team_name`
      - `-cred_name`
      - `-updated_at`

### GET

+ Request (application/json)

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 200 (application/json)

    + Attributes (RecommendationQueryListPage)


+ Response 403 (application/json)

    + Body

            {
                "code": "FORBIDDEN",
                "detail_code": "",
                "message": "Insufficient permissions"
            }

## Stat [/v2/recommendationquery/stat?has_schedule={has_schedule}&types={types}&recommendation_ids={recommendation_ids}&resource_ids={resource_ids}&parent_ids={parent_ids}&team_ids={team_ids}&cred_ids={cred_ids}&providers={providers}&resource_name={resource_name}&resource_kind={resource_kind}&resource_location={resource_location}&parent_kind={parent_kind}&team_name={team_name}&cred_name={cred_name}&search={search}&updated_before={updated_before}&updated_after={updated_after}]

+ Parameters
    + types: `smartparking,rightsizing` (string, optional) - recommendation types (comma separated list of strings).
      Possible values:
        - `smartparking`
        - `rightsizing`
    + has_schedule (boolean, optional) - show whether resource has schedule or not
    + recommendation_ids: `1,2,3` (string, optional) - recommendation ids (comma separated list of integers)
    + resource_ids: `3,5,7` (string, optional) - resource ids (comma separated list of integers)
    + parent_ids: `8,9` (string, optional) - parent resource ids (comma separated list of integers)
    + team_ids: `2,6` (string, optional) - team ids (comma separated list of integers)
    + cred_ids: `1,9,4` (string, optional) - team ids (comma separated list of integers)
    + providers: `aws,gcp` (string, optional) - cloud provider symbolic ids (comma separated list of strings).
      Possible values:
        - `aws`
        - `gcp`
        - `azure`
        - `alibaba`
    + resource_name (string, optional) - resource name (case insensitive partial matching)
    + resource_kind (enum[string], optional) - resource type.
      Possible values:
        - `containers`
        - `compute`
        - `asg`
        - `lg`
        - `rds`
    + resource_location (string, optional) - resource location (case insensitive partial matching)
    + resource_size (string, optional) - current resource size (case insensitive partial matching)
    + target_size (string, optional) - target resource size (case insensitive partial matching)
    + parent_name (string, optional) - parent resource name (case insensitive partial matching)
    + parent_kind (enum[string], optional) - parent resource type.
      Possible values:
        - `compute`
        - `asg`
        - `lg`
        - `rds`
    + team_name (string, optional) - team name (case insensitive partial matching)
    + cred_name (string, optional) - credential name (case insensitive partial matching)
    + search (string, optional) - arbitrary string to look for in all text fields (case insensitive partial matching)
    + updated_after (string, optional) - updated after time (RFC3339 encoded)
    + updated_before (string, optional) - updated before time (RFC3339 encoded)

### GET

+ Request (application/json)

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 200 (application/json)

    + Attributes (Stat)


+ Response 403 (application/json)

    + Body

            {
                "code": "FORBIDDEN",
                "detail_code": "",
                "message": "Insufficient permissions"
            }


## Data dump CSV [/v2/rightsizing/query/dump/?types={types}&format={format}]

+ Parameters
  + types: `smartparking,rightsizing` (string, optional) - recommendation types (comma separated list of strings).
      Possible values:
      - `smartparking`
      - `rightsizing`
  + format: `json` (enum[string], optional) - output format.
      Possible values:
      - `csv`
      - `json`

### GET

+ Request (application/json)

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 200 (text/csv; charset=UTF-8)

    + Headers
     
            Content-decomposition: attachment; fileName=ParkMyCloud_Rightsize_Recommendations_2020_05_18.csv

+ Response 200 (application/json)

    + Attributes (RecommendationQueryDump)


+ Response 403 (application/json)

    + Body

            {
                "code": "FORBIDDEN",
                "detail_code": "",
                "message": "Insufficient permissions"
            }
## Send report Email [/v2/recommendationquery/mail/]

+ Parameters
    + All params accepted by /v2/recommendationquery and
    + format: Mandatory : `pdf` Possible values: `csv`, `pdf`
    + receiver: `example@parkmycloud.com` Mandatory : Comma Separated email addresses
    
### POST

+ Request (application/json)

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 202 (application/json)

    + blank response (Sends a mail)


+ Response 400 (application/json)

    + Body

            {
                "code": "FORBIDDEN",
                "detail_code": "",
                "message": "Bad request"
            }


# Data Structures

## RecommendationQueryListPage
 + total: 1000 (number, required) - total count of items
 + offset: 50 (number, required) - current offset
 + limit: 50 (number, required) - current limit
 + items(array[RecommendationQueryRecord])

## RecommendationQueryDump
 + items(array[RecommendationQueryRecord])

## Stat
 + monthly_savings: 100.24 (number, required) - total monthly projected saving from recommendations
 + annual_savings: 1202.88 (number, required) - total annual projected savings from recommendations

## RecommendationQueryRecord
 + id: 12 (number, required) - rightsizing recommendation id
 + `resource_id`: 33 (number, required) - resource id
 + `resource_kind` (enum[string], required) - resource type
   + Members
    + compute
    + containers
    + asg
    + lg
    + rds
 + `resource_name`: `DevServer N1` (string, required) - resource name
 + `resource_location`: `us-west-2` (string, required) resource location
 + `resource_size`: `m5.xlarge` (string, required) - current resource size
 + `resource_cost`: 0.019 (number, required) - resource montly cost (scaled)
 + `target_size`: `r5a.large` (string, required) - target resource size
 + `target_price`: 0.0154 (number, required) - target houly price (scaled)
 + `projected_savings`: 34.75 (number, required) - projected monthly price difference
 + `parent_id`: 177 (number, optional) - parent resource id
 + `parent_name`: `LG-1` (string, required) - parent resource name
 + `parent_kind` (enum[string], optional) - parent resource type
   + Members
    + compute
    + asg
    + lg
    + rds
 + provider (enum[string], optional) - Cloud provider symbolic id
   + Members
    + `aws`
    + `gcp`
    + `azure`
    + `alibaba`
 + `cred_id`: 200 (number, required) - credential ID
 + `cred_name`: `AWS Cred` (string, required) - credential name
 + `team_id`: 250 (number, required) - team ID
 + `team_name`: `Dev Team` (string, required) - team name
 + `is_cluster`: false (boolean, required) - flag indicating the resource is a DB cluster
 + `has_schedule`: false (boolean, required) - flag indicating the resource has an attached schedule
 + `has_metrics`: true (boolean, required) - flag indicating the resource has some metrics available
 + `has_mem_metrics`: false (boolean, required) - flag indicating the resource has MEM metrics available
 + `parent_kind` (enum[string], optional) - parent resource type
 + `updated_at`: `2019-05-03T09:52:55.770725197Z` (string, required) - time of the last update (RFC3339 encoded)
 + `created_at`: `2019-05-03T09:52:55.770725197Z` (string, required) - time of the creation (RFC3339 encoded)

# Group Resizing Query API

## Resize query [/v2/resizequery/?status={status}&resource_type={resource_type}&resource_provider={resource_provider}&resource_name={resource_name}&team_name={team_name}&cred_name={cred_name}&resource_location={resource_location}&updated_at_before={updated_at_before}&updated_at_after={updated_at_after}&at_time_before={at_time_before}&at_time_after={at_time_after}&offset={offset}&limit={limit}&order={order}]

+ Parameters
  + resource_name (string, optional) - resource name
  + resource_provider (enum[string], optional) - Cloud provider symbolic id
    + Members
      + `aws`
      + `gcp`
      + `azure`
      + `alibaba`
  + resource_type (enum[string], optional) - resource type
    + Members
      + compute
      + asg
      + lg
      + rds
  + resource_location (string, optional) - resource location
  + team_name (string, optional) - team name
  + cred_name (string, optional) - credential name
  + `updated_at_after`(string, optional) - updated at after
  + `updated_at_before` (string, optional) - updated at before
  + `at_time_after` (string, optional) - at time at after
  + `at_time_before` (string, optional) - at time at before
  + status (string, optional) - resize task status
  + limit (number, optional) - indicates the maximum number of items to return
  + offset (number, optional) - indicates the starting position of the query
  + order (enum[string], optional) - order
    + Members
      + `resource_name`
      + `resource_provider`
      + `resource_type`
      + `resource_location`
      + `team_name`
      + `cred_name`
      + `updated_at`
      + `at_time`
      + `status`
      + `from`
      + `to`
      + `-resource_name`
      + `-resource_provider`
      + `-resource_type`
      + `-resource_location`
      + `-team_name`
      + `-cred_name`
      + `-updated_at`
      + `-at_time`
      + `-status`
      + `-from`
      + `-to`

### GET

+ Request (application/json)

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 200 (application/json)

    + Attributes (Page)

+ Response 403 (application/json)

    + Body

            {
                "code": "FORBIDDEN",
                "detail_code": "",
                "message": "Insufficient permissions"
            }

## Send report Email [/v2/resizequery/mail/]

+ Parameters
  + All params accepted by /v2/resizequery and
  + format: Mandatory : `pdf` Possible values: `csv`, `pdf`
  + receiver: `example@parkmycloud.com` Mandatory : Comma Separated email addresses
### POST

+ Request (application/json)

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 202 (application/json)

    + blank response (Sends a mail)


+ Response 400 (application/json)

    + Body

            {
                "code": "FORBIDDEN",
                "detail_code": "",
                "message": "Bad Request"
            }

# Data Structures

## Page
 + total: 1000 (number, required) - total count of items
 + offset: 50 (number, required) - current offset
 + limit: 50 (number, required) - current limit
 + items(array[ResizeQuery])

## ResizeQuery
 + `task_id`: 12 (number, required) - resize task id
 + from: `t2.micro` (string, required) - origin resource size
 + to: `t2.large` (string, required) - target resource size
 + status (enum[string], required) - current task status
   + Members
    + `waiting`
    + `pending`
    + `in-progress`
    + `cleanup`
    + `done`
    + `cancelled`
    + `failed`
 + when: `ready` (enum[string], required) - when to resize
  + Members
    + ready - when the resource is ready to be resized
    + now - right away
    + next-maintenance-window - on the next maintenance window
    + `2019-05-03T09:52:55Z` - at specific time
 + `updated_at`: `2019-05-03T09:52:55.770725197Z`
 + message (string, optional)

 + resource_id: 300 (number, required) - resource ID
 + resource_name: `production` (string, required) - resource name
 + resource_location: `us-west-2` (string, required) resource location
 + resource_provider (enum[string], optional) - Cloud provider symbolic id
   + Members
    + `aws`
    + `gcp`
    + `azure`
    + `alibaba`
 + resouce_type (enum[string], optional) - resource type
   + Members
    + compute
    + asg
    + lg
    + rds

 + cred_id: 200 (number, required) - credential ID
 + cred_name: `AWS Cred` (string, required) - credential name

 + team_id: 250 (number, required) - team ID
 + team_name: `main team` (string, required) - team name

# Group Reports API V2

## Recommendation [/v2/report/recommendation]

### GET


+ Request
    
    + Headers

            Accept: text/csv
            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 200 (text/csv)

    + Body

            account_id,instance_id,resource_type,has_schedule,recommendation_type,resource_name,team_name,provider_name,credential_name,location,info,cost,smartpark_min,smartpark_max,resize_min,resize_max,pmc_resource_id
            project_id,gcp-dev1,compute,false,smartpark,gcp-dev1,My First Team,gcp,gcp,us-east1-c,custom-1-8192-ext,55.77,28.22,55.77,0.00,0.00,26598


+ Request
    
    + Headers

            Accept: text/yaml
            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 200 (text/yaml)

    + Body

            - account_id: project_id
              instance_id: gcp-dev
              resource_type: compute
              has_schedule: false
              type:
              - resize
              - smartpark
              resource_name: gcp-dev
              team_name: My First Team
              provider_name: gcp
              cred_name: gcp
              location: us-central1-c
              info: f1-micro
              cost: 5.548
              resize:
                min: 1.58688
                max: 3.5568000000000004
              smartpark:
                min: 5.547999858856201
                max: 5.547999858856201
              resource_id: 1792

+ Request
    
    + Headers

            Accept: application/json
            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 200 (application/json)

    + Body

            [
                {
                    "account_id": "project_id",
                    "instance_id": "gcp-dev",
                    "resource_type": "compute",
                    "has_schedule": false,
                    "type": [
                        "resize",
                        "smartpark"
                    ],
                    "resource_name": "gcp-dev",
                    "team_name": "My First Team",
                    "provider_name": "gcp",
                    "cred_name": "gcp",
                    "location": "us-central1-c",
                    "info": "f1-micro",
                    "cost": 5.548,
                    "resize": {
                        "min": 1.58688,
                        "max": 3.5568000000000004
                    },
                    "smartpark": {
                        "min": 5.5149760246276855,
                        "max": 5.547999858856201
                    },
                    "resource_id": 1793
                },
            ]

## Filtered recommendations [/v2/report/recommendation/filtered{?credential,location,metrics,name,provider,recommended,schedule,search,state,status,tags,team,type,page,pageSize,sort}]

### GET

- Parameters

    - credential: MyCred (string, optional) - A portion of a resource's credential name. Used in a sub-string match to
      filter by credential name. May be prefixed with `-` to perform a "NOT" filter.
    - location: us-east (string, optional) - A portion of a resource's location. Used in a sub-string match to
      filter by location. May be prefixed with `-` to perform a "NOT" filter.
    - metrics: true (boolean, optional) - A value indicating whether to return resources that do or do not have
      usage metrics. Pass `true` to only return resources that do have usage metrics, or `false` to only
      return resources without usage metrics.
    - name: dev-serv (string, optional) - A portion of a resource's name. Used in a sub-string match to
      filter by name. May be prefixed with `-` to perform a "NOT" filter.
    - provider: aws (string, optional) - A portion of a resource's provider name. Used in a sub-string match to
      filter by provider name. May be prefixed with `-` to perform a "NOT" filter.
    - recommended: true (boolean, optional) - A boolean value indicating whether to only return resources that have
      some sort of schedule recommendation. Pass `true` to only return resources that have any type of
      recommendation. Passing `false` is not supported.
    - schedule: always (string, optional) - A portion of a resource's schedule name. Used in a sub-string match to
      filter by schedule name. May be prefixed with `-` to perform a "NOT" filter.
    - search: t2 (string, optional) - A search term that will be applied to numerous fields at once. The values
      for several fields are concatenated together with a space (` `) character and a sub-string match is
      performed using the specified search term. The fields used are "team name", "credential name",
      "provider name", "location", "name", "schedule name", "state", "info text", "CSP instance ID", and
      "tags". May be prefixed with `-` to perform a "NOT" filter.
    - state: parked (enum[string], optional) - A value indicating a resource's state. Only resources that are currently in
      the specified state will be returned.
          - running
          - starting
          - stopping
          - stopped
          - parking
          - parked
    - status: attached (enum[string], optional) - A value indicating a resource's schedule status.
          - attached
          - detached
          - snoozed
    - tags: abcd1234 (string, optional) - A search term that will be applied to a resource's tags. A sub-string match is
      performed against the resource's tag keys and values. May be prefixed with `-` to perform a "NOT" filter.
    - team: dev (string, optional) - A portion of a resource's team name. Used in a sub-string match to filter by team
      name. May be prefixed with `-` to perform a "NOT" filter.
    - type: asg,lg (array[enum[string]], optional) - A comma-separated list of resource types that should be returned.
          - compute
          - asg
          - lg
          - rds
    - page: 1 (integer, optional) - The page number of results to return. Pages are 1-indexed, meaning page 1 is the
      first page.

      Default: 1
    - pageSize: 200 (integer, optional) - The size of the page of results to return. The minimum page size is 1; the
      maximum page size is 500.

      Default: 200
    - sort: name (string, optional) - The field by which the results should be sorted. By default, results are sorted
      by their create time and then their primary key identifier. When a value is provided for the `sort` parameter,
      that field is used for the first-order sort, then the results are further sorted by create time and primary key
      identifier. May be prefixed with `-` to perform a "reverse" (or descending) sort.


+ Request
    
    + Headers

            Accept: text/csv
            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 200 (text/csv)

    + Body

            Resource Type,Has Schedule,Recommendation Type,Resource Name,Team Name,Provider Name,Credential Name,Location,Info,Cost ($),Smartpark Min Savings ($),Smartpark Max Savings ($),Resize Min Savings ($),Resize Max Savings ($)
            compute,false,smartpark,gcp-dev1,My First Team,gcp,gcp,us-east1-c,custom-1-8192-ext,55.77,28.22,55.77,0.00,0.00

This API support json/yaml/csv as output format, clients should include one of the headers:
* Accept: application/json
* Accept: text/yaml
* Accept: text/csv

## Aggregated Actual Savings [/v2/report/savings/all/{time_range}]

+ Parameters
  + time_range: `prev` (string, required) - report time window,
  one of:
      * current: calendar month to date
      * prev: previous full calendar month
      * 2018-05: specified month in YYYY-MM format.

### GET

Will aggregate actual savings for all resources visible to logged-in user. In this report
we don't count LG/ASG members

+ Request
    
    + Headers

            Accept: application/json
            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 200 (application/json)

    + Attributes (Aggregated)

## Each Actual Savings [/v2/report/savings/each/{time_range}]

+ Parameters
  + time_range: `prev` (string, required) - report time window,
  one of:
      * current: calendar month to date
      * prev: previous full calendar month
      * 2018-05: specified month in YYYY-MM format.

### GET

List resource identifiers and associated actual savings value, for each resource.

+ Request
    
    + Headers

            Accept: application/json
            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 200 (application/json)

    + Attributes (Savings)

## Resource Actual Savings [/v2/report/savings/{resource_id}/{time_range}]

+ Parameters
  + time_range: `prev` (string, required) - report time window,
  one of:
      * current: calendar month to date
      * prev: previous full calendar month
      * 2018-05: specified month in YYYY-MM format.
  + resource_id: `1` (number, required) - PMC internal resource ID

### GET

Actual savings value for a single specific resource

+ Request
    
    + Headers

            Accept: application/json
            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 200 (application/json)

    + Attributes (Saving)

# Data Structures

## ReportRange(object)
 + begin: `2018-05-01T00:00:00Z`  (string, required) - begin date
 + end: `2018-06-01T00:00:00Z`  (string, required) - end date

## Savings(ReportRange)
 + items (array[Item])

## Saving(Item)
 + begin: `2018-05-01T00:00:00Z`  (string, required) - begin date
 + end: `2018-06-01T00:00:00Z`  (string, required) - end date

## Aggregated (ReportRange)
 + `available_hours`: `730` (number, required) - total number of hours indicated instances existed during time window
 + `potential_cost`: `3.8512` (number, required) - resource cost per hour x total hours available
 + `parked_hours`: `50` (number, required) - total number of hours indicated instances were in “stopped” state
 + savings: `23` (number, required) - resource cost per hour x total hours parked

## Item(object)
 + provider_name (enum[string], required) - name of the CSP provider
  - gcp
  - aws
  - azure
 + `account_id`: `project_id` (string, required) - unique CSP provider ID(Accound ID for AWS, Subcription for Azure and ProjectID for GCP)
 + `resource_type`: `compute` (enum[string], required) - PMC resource type
  - compute
  - asg
  - lg
  - rds
  - composite
 + `instance_id`: `i-1234567890abcdef0` (string, optional) - CSP instance ID(can be empty for ASG and LG)
 + location: `us-central1-c` (string, required) - CSP location
 + `resource_name`: `gcp-dev` (string, required) - resource name
 + `resource_id`: `123` (number, required) - PMC internal resource ID
 + deleted: `false` (boolean, required) - wether resource already deleted
 + `available_hours`: `730` (number, required) - total number of hours indicated instances existed during time window
 + `potential_cost`: `3.8512` (number, required) - resource cost per hour x total hours available
 + `parked_hours`: `50` (number, required) - total number of hours indicated instances were in “stopped” state
 + savings: `23` (number, required) - resource cost per hour x total hours parked

# Group Resource API V2

An API that allows to set/reset instance cost, enable/disable smartpark recommendation
generation for the instance, set resource limits, manipulate schedule overrides and
retrieve resize related metadata.

## Resource [/v2/resource/{res\_id}]

### GET

Get a single resource without any nested objects

+ Parameters
  + res\_id (number, required) - resource id


+ Request (application/json)

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 200 (application/json)
    + Attributes (Resource)

## Set Cost [/v2/resource/{resource\_id}/set\_cost?cost={cost}]

### GET

Set instance cost. For ASG we set instance cost, not ASG cost as whole, so if
we have ASG with 4 instances with 5$ cost each, we can override this 5$ cost, not 20$.

+ Parameters
  + resource\_id (number, required) - resource id
  + cost (number, required) - instance cost

+ Request (application/json)

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 200 (application/json)
    + Attributes (Cost)

## Reset Cost [/v2/resource/{resource\_id}/reset\_cost]

Reset instance cost of resource.

### GET

+ Parameters
  + resource\_id (number, required) - resource id

+ Request (application/json)

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 200 (application/json)
    + Attributes (Cost)

## Resizing Compatible types [/v2/resource/{res\_id}/resize/compatible-types]

### GET

Returns a list of resize compatible types for the resource with potential cost and savings

+ Parameters

  + res\_id (number, required) - resource id

+ Request (application/json)

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 200 (application/json)

    + Attributes (array[InstanceTypeInfo])

    + Body

            [
                {
                    "provider":   "aws",
                    "type":       "m5.medium",
                    "features":   [
                        {"id":"type",    "name":"Instance Type",       "raw":"t2.large", "value":"t2.large"},
                        {"id":"vcpu",    "name":"vCPU",                "raw":2,          "value":"2"},
                        {"id":"mem",     "name":"Memory",              "raw":8192,       "value":"8 GB"},
                        {"id":"enh.net", "name":"Enhanced Networking", "raw":true,       "value":"Yes"},
                        {"id":"store",   "name":"Instance Store",      "raw":"ebs only", "value":"EBS only"},
                        {"id":"cost",    "name":"Monthly Cost",        "raw":32.53,      "value":"$32.53"},
                        {"id":"save",    "name":"Monthly Savings",     "raw":-10.03,     "value":"-$10.03"},
                    ],
                    "attributes": {
                        "ecu":                     "variable",
                        "vcpu":                    "2",
                        "memory":                  "8192",
                        "storage":                 "ebs only",
                        "clockspeed":              "Up to 3.0 GHz",
                        "servicecode":             "AmazonEC2",
                        "servicename":             "Amazon Elastic Compute Cloud",
                        "instancetype":            "t2.large",
                        "locationtype":            "aws region",
                        "instancefamily":          "general purpose",
                        "currentgeneration":       "yes",
                        "physicalprocessor":       "Intel Xeon Family",
                        "processorfeatures":       "Intel AVX; Intel Turbo",
                        "networkperformance":      "Low to Moderate",
                        "processorarchitecture":   "64-bit",
                        "normalizationsizefactor": "4"
                    }
                }
            ]

## Resizing Custom types [/v2/resource/{res\_id}/resize/custom-limits]

### GET

Returns limits for custom instance types in context of a resource {res\_id}.
It takes into account resource's location/region/zone, its current type (if necessary) plus
any attributes and provider specific rules that may affect the limits.
For example certain GCP zones cannot have custom machine types (`custom-N-M` and `db-custom-N-M`)
with higher than usual number of CPUs (96 vs 64).

+ Parameters

  + res\_id: 123  (number, required) - resource id

+ Request (application/json)

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 200 (application/json)

    + Attributes (InstanceTypeInfo)

    + Body

            {
                "provider": "gcp",
                "location": "europe-west6-c",
                "limits": [
                    {
                        "prefix": "custom",
                        "name":   "cores",
                        "min":    1,
                        "max":    64,
                        "ranges": [
                            {
                                "from":        1,
                                "to":          1,
                                "dependents":  [
                                    {name:"mem_mb", "min":1024, "max":6656, "step":256},
                                    {name:"mem_ext_mb", "min":1024, "max":638976, "step":256}
                                ]
                            },
                            ...
                            {
                                "from":        64,
                                "to":          64,
                                "dependents":  [
                                    {"name":"mem_mb", "min":59136, "max":425984, "step":256},
                                    {"name":"mem_ext_mb", "min":59136, "max":638976, "step":256}
                                ]
                            }
                        ]
                    },
                    {
                        "prefix": "n2-custom",
                        "name":   "cores",
                        "min":    2,
                        "max":    80,
                        "ranges": [
                            {
                                "from":        2,
                                "to":          2,
                                "dependents":  [
                                    {name:"mem_mb", "min":512, "max":16384, "step":256},
                                    {name:"mem_ext_mb", "min":512, "max":655360, "step":256}
                                ]
                            },
                            ...
                            {
                                "from":        80,
                                "to":          80,
                                "dependents":  [
                                    {"name":"mem_mb", "min":40960, "max":655360, "step":256},
                                    {"name":"mem_ext_mb", "min":40960, "max":655360, "step":256}
                                ]
                            }
                        ]
                    }
                ]
            }

+ Response 403 (application/json)

    + Body

            {
                "code": "FORBIDDEN",
                "detail_code": "",
                "message": "Insufficient permissions"
            }


## Resizing Instance-type info [/v2/resource/{res\_id}/resize/instance-type/{type}]

### GET

Validates an instance {type} in a context of a resource {res\_id}.
It takes into account resource's location/region/zone, its current type (if necessary) plus
any attributes that may affect the decision. Also it checks against provider specific rules
and limits. For example custom GCP machine types (`custom-N-M` and `db-custom-N-M`) have a
dependency between possible values of N and M (cores vs. memory).

If the type is valid returns an instance-type metadata in context of the current resource
(i.e. what the resource would look like if it was resized to this type). The info includes
potential monthly cost and savings.

If the type is invalid returns a BAD\_REQUEST error with the INVALID\_TYPE code and a text
message containing the reason.

+ Parameters

  + res\_id: 123          (number, required) - resource id
  + type:    `c5.xxlarge` (string, required) - target instance-type

+ Request (application/json)

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 200 (application/json)

    + Attributes (InstanceTypeInfo)

    + Body

            {
                "provider":   "aws",
                "type":       "m5.medium",
                "features":   [
                    {"id":"type",    "name":"Instance Type",       "raw":"t2.large", "value":"t2.large"},
                    {"id":"vcpu",    "name":"vCPU",                "raw":2,          "value":"2"},
                    {"id":"mem",     "name":"Memory",              "raw":8192,       "value":"8 GB"},
                    {"id":"enh.net", "name":"Enhanced Networking", "raw":true,       "value":"Yes"},
                    {"id":"store",   "name":"Instance Store",      "raw":"ebs only", "value":"EBS only"},
                    {"id":"cost",    "name":"Monthly Cost",        "raw":32.53,      "value":"$32.53"},
                    {"id":"save",    "name":"Monthly Savings",     "raw":-10.03,     "value":"-$10.03"},
                ],
                "attributes": {
                    "ecu":                     "variable",
                    "vcpu":                    "2",
                    "memory":                  "8192",
                    "storage":                 "ebs only",
                    "clockspeed":              "Up to 3.0 GHz",
                    "servicecode":             "AmazonEC2",
                    "servicename":             "Amazon Elastic Compute Cloud",
                    "instancetype":            "t2.large",
                    "locationtype":            "aws region",
                    "instancefamily":          "general purpose",
                    "currentgeneration":       "yes",
                    "physicalprocessor":       "Intel Xeon Family",
                    "processorfeatures":       "Intel AVX; Intel Turbo",
                    "networkperformance":      "Low to Moderate",
                    "processorarchitecture":   "64-bit",
                    "normalizationsizefactor": "4"
                }
            }

+ Response 400 (application/json)

    + Body

            {
                "code": "BAD_REQUEST",
                "detail_code": "INVALID_TYPE",
                "message": "Custom GCP Compute instances cannot have more than 96 CPU cores"
            }

+ Response 403 (application/json)

    + Body

            {
                "code": "FORBIDDEN",
                "detail_code": "",
                "message": "Insufficient permissions"
            }

## Parking restriction [/v2/resource/{res\_id}/restriction]

+ Parameters
    + `res_id` (number, required) - resource id

### GET

Get current parking restriction for a resource

+ Request

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 200 (application/json)

    + Attributes (Restriction)

### PUT

Set a parking restriction for a resource

+ Request (application/json)

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

    + Attributes (Restriction)

+ Response 200 (application/json)

    + Attributes (RestrictionOldNew)

## Resize Recommendation Flag [/v2/resource/{res\_id}/resize-recommendations]

### PUT 

Set the `resize_recommendation_enable` flag of the resource. False means there will be no resize recommendations
for this instance.

+ Parameters
    + `res_id` (number, required) - resource id

+ Request (application/json)


    + Headers

            Accept: application/json
            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

    + Attributes

        + enable (required, boolean) - value of the `resize_recommendation_enabled` flag


+ Response 200 (application/json)

    + Attributes
        + id: 1 (number, required) - id of the resource
        + name: dev_instance (string, required) - name of the resource
        + resize_recommendation_enabled: true (boolean, required) - flag value

+ Response 400 (application/json)

    + Body

            {
                "code": "BAD_REQUEST",
                "detail_code": "",
                "message": "Invalid request data"
            }

+ Response 403 (application/json)

    + Body

            {
                "code": "FORBIDDEN",
                "detail_code": "",
                "message": "Insufficient permissions"
            }

## Smartpark Recommendation Flag  [/v2/resource/{res\_id}/smartpark-recommendations]

### PUT 

Set the `spr_enable` flag of the resource. False means there will be no smartpark recommendations
for this instance.

+ Parameters
    + `res_id` (number, required) - resource id

+ Request (application/json)


    + Headers

            Accept: application/json
            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

    + Attributes

        + enable (required, boolean) - value of the `spr_enabled` flag


+ Response 200 (application/json)

    + Attributes
        + id: 1 (number, required) - id of the resource
        + name: dev_instance (string, required) - name of the resource
        + spr_enabled: true (boolean, required) - flag value

+ Response 400 (application/json)

    + Body

            {
                "code": "BAD_REQUEST",
                "detail_code": "",
                "message": "Invalid request data"
            }

+ Response 403 (application/json)

    + Body

            {
                "code": "FORBIDDEN",
                "detail_code": "",
                "message": "Insufficient permissions"
            }

## Attach schedule [/v2/resource/attach-schedule]

Attach schedule to the list of resources

### PUT

+ Request (application/json)

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

    + Attributes (Attach)

+ Response 200 (application/json)

## Detach schedule [/v2/resource/detach-schedule]

Detach schedule from the list of resources

### PUT

+ Request (application/json)

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

    + Attributes (Detach)

+ Response 200 (application/json)

## Override schedule [/v2/resource/override]

Override schedules of the given resources. Also works for Logical Group members.

### PUT

+ Request (application/json)

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

    + Attributes (Override)

+ Response 200 (application/json)

    + Attributes (OverrideResponse)

+ Response 403 (application/json)

    + Body

            {
                "code": "INVALID_PERMISSIONS",
                "detail_code": "OVERRIDE_EXCEEDED",
                "message": "Override is greater than available"
            }

## Cancel override schedule [/v2/resource/override/cancel]

Cancel schedule override of the given resources. Also works for Logical Group members.

### PUT

+ Request (application/json)

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

    + Attributes (Detach)

+ Response 200 (application/json)

## Parking Config [/v2/resource/{res\_id}/parking/config]

+ Parameters
    + `res_id` (number, required) - resource id

### GET

Get current parking config for a resource

+ Request

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 200 (application/json)

    + Attributes
        + id: 1 (number, required) - id of the resource
        + name: dev_instance (string, required) - name of the resource
        + params: [Config]

### PUT

Set parking config for a resource

+ Request (application/json)

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

    + Attributes

        + throttled_size (required, string) - desired size of DB on parking
        + throttled_storage (required, number) - desired storage in GB on parking

+ Response 200 (application/json)

    + Attributes
        + id: 1 (number, required) - id of the resource
        + name: dev_instance (string, required) - name of the resource
        + params: [Config]

## Parking Compatible types [/v2/resource/{res\_id}/parking/compatible-types]

### GET

Returns a list of parking compatible types for the resource with potential cost and savings

+ Parameters

  + res\_id (number, required) - resource id

+ Request (application/json)

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 200 (application/json)

    + Attributes (array[InstanceTypeInfo])

    + Body

            [
                {
                    "provider": "azure",
                    "type": "S0",
                    "features": [{"id": "type","name": "Instance Type","raw": "dtu","value": "dtu"},
                        {"id": "origincost","name": "Monthly Origin Cost","raw": 14.718625,"value": "$14.72"},
                        {"id": "cost","name": "Monthly Cost","raw": 14.718625,"value": "$14.72"},
                        {"id": "storage","name": "Storage","raw": 2,"value": "2 GB"},
                        {"id": "family","name": "Family","raw": "Standard","value": "Standard"},
                        {"id": "dtu","name": "DTUs","raw": 10,"value": "10"},
                        {"id": "save","name": "Monthly Savings","raw": 14.700375000000001,"value": "+$14.70"
                        }
                    ],
                    "attributes": {}
                }
            ]

## List Resource Groups [/v2/resource/azure/resourcegroups]

### GET

Returns a list of resource groups

+ Parameters

    + cred_ids (string, optional) - cred ids
    + team_ids (string, optional) - team ids

+ Request (application/json)

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 200 (application/json)

    + Body

            {
                "data": [
                    {
                        "resource_group": "pmc-west",
                        "cred_id": 1
                    }
                ]
            }
      
# Data Structures

## Detach
 + item\_ids (array[number], required) - list of resources IDs

## Attach
 + item\_ids (array[number], required) - list of resources IDs
 + schedule\_id: `1001` (number, required) - schedule ID to attach

## Cost
 + cost: `20` (number, required) - new resource cost
 + instance\_cost: `10` (number, required) - new instance cost
 
## InstanceTypeInfo (object)
+ provider (enum[string], required) - Cloud provider symbolic id
    + Members
        + `aws`
        + `gcp`
        + `azure`
        + `alibaba`
+ type: `c4.large` (string, required) - Instance type name
+ features (array[Feature], required) - Pre-processed instance features
+ attributes (object, required) - Raw cloud provider's attributes

## Feature (object)
+ id: `enh.net` (string, required)

    Identifier of the feature. Stays the same across different cloud providers and various instance types
    (if the feature is present in the list).

+ name: `Enhanced Networking` (string, required)

    Human readable name of the feature. The client may not use the provided name.

+ raw: true (required)

    Raw value of the feature.

+ value: `Yes` (string, required)

    Human-friendly formatted value of the feature.

## Resource
 + id: `1` (number, required) - resource id
 + parent\_id: `2` (number, optional) - parent id, if it exists
 + name: `gcp instance` (string, required) - resource name
 + origin\_price: `0.01` (number, required) - discovered resource price
 + price: `0.05` (number, required) - current active resource price
 + instance\_price: `0.05` (number, required) - price of one instance(only for ASG)
 + cost\_overridden: `true` (boolean, required) - wether cost overriden or not
 + restriction (RestrictionEnum) - a parking restriction applied to a resource
 + state (enum[string], optional) - A value indicating a resource's state. Only resources that are currently in the specified state will be returned.
    - running
    - starting
    - stopping
    - stopped
    - parking
    - parked
 + type: asg,lg (array[enum[string]], optional) - A comma-separated list of resource types that should be returned.
    - compute
    - asg
    - lg
    - rds

## RestrictionEnum (enum[number]) - `parking-restriction` code
     + Members
       + 0 - No Restrictions
       + 1 - Never park; all parking actions are disabled
       + 2 - Schedule can only be overridden

## Restriction
  + restriction (RestrictionEnum, required)

## RestrictionOldNew
  + `old` (RestrictionEnum, required)
  + `new` (RestrictionEnum, required)

## Override
 + `item_ids` (array[number], required) - list of resources IDs
 + `override_period`: `1` (number, optional) - overrider period in hours (can be fractional)
 + `override_until`: `2017-10-02T00:00:00Z` (string, optional) - override until date, timezone should be provided in separate field
 + `timezone`: `Europe/Minsk` (string, optional) - timezone for override\_until param

## OverrideResponse
 + `override_until`: `2017-10-02T00:00:00Z` (string, required) - override until date(in UTC)

## Config
 + `throttled`: [Edition]
 + `original`: [Edition]
 + `type`: `manual` (string, required) - config type either manual or default

## Edition
 + `size`: `GP_Gen5_2` (string, required) - size of the resource
 + `storage`: `10` (number, required) - storage of the resource
 + `capacity`: `2` (number, required) - number of DTU/vCore included in the edition
 + `tier`: `GeneralPurpose` (string, required) - Tier to which the resource edition belongs
 + `cost`: `391.79` (number, required) - Monthly cost(730 hours) of the edition

# Group Resizing API V2

## Resizing task [/v2/resize/]

### POST

Schedules a resizing of a resource `res_id` to a specified size/type (see JSON parameters).

JSON parameters basically consist of three mandatory fields: `to`, `from` and `when`.
However specific resource types may require additional parameters - for example
AWS RDS resources also accept an `immediately` _(bool)_ parameter, which instructs AWS
to act either right after the _API call_ or during the next scheduled _maintenance window_
at the AWS cloud.

Responses with the added resizing task (JSON).

+ Request (application/json)

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

    + Attributes(ResizeTask POST)

+ Response 201 (application/json)

    + Attributes (ResizeTask)

+ Response 400 (application/json)

    + Body

            {
                "code": "INVALID_REQUEST", 
                "detail_code": "",
                "message": "bad Param From (\"t2.micro\"): doesn't match current resource size t1.micro"
            }

+ Response 403 (application/json)

    + Body

            {
                "code": "FORBIDDEN",
                "detail_code": "",
                "message": "Insufficient permissions"
            }

## Resizing task List [/v2/resize/?resource_id={resource_id}]

+ Parameters
  + resource_id (number, optional) - resource id

### GET

Lists resizing tasks (active, cancelled, finished).

If successful responses with a list of resizing tasks (JSON).

+ Request (application/json)

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 200 (application/json)

    + Attributes (array[ResizeTask])

    + Body

            [
              {
                "id": 42,
                "resource_id": 300, 
                "status": "pending",
                "params": {
                    "to": "t2.small",
                    "from": "t1.micro",
                    "when": "now"
                },
                "message": "",
                "updated_at": "2019-05-03T09:52:55.770725197Z",
                "created_at": "2019-05-03T09:52:55Z"
              }
            ]

+ Response 404 (application/json)

    + Body

            {
                "code": "NOT_FOUND", 
                "detail_code": "",
                "message": "resource not found"
            }

+ Response 403 (application/json)

    + Body

            {
                "code": "FORBIDDEN",
                "detail_code": "",
                "message": "Insufficient permissions"
            }

## Resizing Task [/v2/resize/{task_id}]

+ Parameters
  + task_id (number, required) - task id

### GET

Get resizing task.

+ Request (application/json)

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 200 (application/json)

    + Attributes (ResizeTask)

+ Response 404 (application/json)

    + Body

            {
                "code": "NOT_FOUND", 
                "detail_code": "",
                "message": "resource not found"
            }

+ Response 403 (application/json)

    + Body

            {
                "code": "FORBIDDEN",
                "detail_code": "",
                "message": "Insufficient permissions"
            }


### DELETE

Cancels an active resizing task `task_id`. Notice cancellation of a resize task may not finish
right away – in that case the task switches to the **CLEANUP** status which in time may become
either **CANCELLED** or **FAILED** if something went wrong. 

If successful responses with an updated resize task.

+ Request (application/json)

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 200 (application/json)

    + Attributes (ResizeTask)

+ Response 404 (application/json)

    + Body

            {
                "code": "NOT_FOUND", 
                "detail_code": "",
                "message": "resize task not found"
            }

+ Response 403 (application/json)

    + Body

            {
                "code": "FORBIDDEN",
                "detail_code": "",
                "message": "Insufficient permissions"
            }

# Data Structures

## ResizeTask(ResizeTask POST)
 + id: 42 (number, required) - resize task ID
 + status (enum[string], required) - current task status
   + Members
     + `waiting`
     + `pending`
     + `in-progress`
     + `cleanup`
     + `done`
     + `cancelled`
     + `failed`
 + message (string, optional)
 + `updated_at`: `2019-05-03T09:52:55.770725197Z`
 + `created_at`: `2019-05-03T09:52:55Z`

## ResizeTask POST
 + `resource_id`: 300 (number, required) - resource ID
 + params (object, required)
   + to: `t2.small` (string, required) - target resource type
   + from: `t1.micro` (string, required) - current resource type
   + when: `ready` (enum[string], required) - when to resize
     + Members
       + ready - when the resource is ready to be resized
       + now - right away
       + `2019-05-03T09:52:55Z` - at specific time
   + immediately: `true` (boolean, optional) - AWS RDS specific parameter
# Group Rightsizing Recommendation
An API for Rightsizing Recommendation

## Settings [/v2/rightsizing/settings/{team_id}]

+ Parameters
  + team_id: `123` (number) - The unique ID of the team

### GET

+ Request (application/json)

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 200 (application/json)
    + Attributes (Setting)

+ Response 401 (application/json)

    
    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }

+ Response 403 (application/json)

    
    + Body

            {
                "code": "INVALID_PERMISSIONS",
                "detail_code": "",
                "message": "Not authorized to access this setting"
            }

### POST
This request will update current rightsizing team configuration

+ Request (application/json)

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8
    
    + Attributes (Setting)

+ Response 200 (application/json)
    + Attributes (Setting)

+ Response 401 (application/json)

    
    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }

+ Response 403 (application/json)

    
    + Body

            {
                "code": "INVALID_PERMISSIONS",
                "detail_code": "",
                "message": "Not authorized to access this setting"
            }

### DELETE
This request will reset rightsizing team configuration

+ Request (application/json)

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8
    
+ Response 201 (application/json)
    + Attributes (Setting)

+ Response 401 (application/json)

    
    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }

+ Response 403 (application/json)

    
    + Body

            {
                "code": "INVALID_PERMISSIONS",
                "detail_code": "",
                "message": "Not authorized to access this setting"
            }

## List ignore codes [/v2/rightsizing/ignore-codes]

### GET

+ Request (application/json)

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 200 (application/json)

    + Attributes (array[IgnoreCode])

+ Response 401 (application/json)

    
    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }

+ Response 403 (application/json)

    
    + Body

            {
                "code": "INVALID_PERMISSIONS",
                "detail_code": "",
                "message": "Not authorized to access this setting"
            }

## List rightsizing recommendations for resource [/v2/rightsizing/?resource_id={resource_id}&status={status}]

+ Parameters
  + resource_id (number, required) - resource id
  + status (string, optional) - filter by recommendations status

### GET

+ Request (application/json)

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 200 (application/json)
    + Attributes (array[RightsizingRecommendation])

+ Response 401 (application/json)

    
    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }

+ Response 404 (application/json) 
    
    + Body

            {
                "code": "NOT_FOUND",
                "detail_code": "",
                "message": "Resource not found"
            }

## Ignore rightsizing recommendations [/v2/rightsizing/{recommendation_id}/ignore]

+ Parameters
  + recommendation_id (number, required) - recommendation id

### POST

+ Request (application/json)

    + Attributes (IgnoreOptions)

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 200 (application/json)

+ Response 401 (application/json)

    
    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }

+ Response 404 (application/json) 
    
    + Body

            {
                "code": "NOT_FOUND",
                "detail_code": "",
                "message": "Recommendation not found"
            }

## Ignore rightsizing recommendation for resource [/v2/rightsizing/resource/{resource_id}/ignore]

+ Parameters
  + resource_id (number, required) - resource id

### POST

+ Request (application/json)

    + Attributes (IgnoreOptions)

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 200 (application/json)

+ Response 401 (application/json)

    
    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }

+ Response 404 (application/json) 
    
    + Body

            {
                "code": "NOT_FOUND",
                "detail_code": "",
                "message": "Recommendation not found"
            }

## Apply rightsizing recommendations [/v2/rightsizing/{recommendation_id}/apply]

+ Parameters
  + recommendation_id (number, required) - recommendation id

### POST

+ Request (application/json)

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 200 (application/json)

+ Response 401 (application/json)

    
    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }

+ Response 404 (application/json) 
    
    + Body

            {
                "code": "NOT_FOUND",
                "detail_code": "",
                "message": "Recommendation not found"
            }
            
## Get or set rightsizing organization settings [/v2/rightsizing/organization/settings]

### GET

+ Request (application/json)

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 200 (application/json)
    
    + Attributes (RightsizingSettings)
    
+ Response 401 (application/json)

    
    + Body
    
            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }

### POST

+ Request (application/json)
    
    + Attributes (RightsizingSettings)

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 200 (application/json)
    
    + Attributes (RightsizingSettings)
    
+ Response 401 (application/json)

    
    + Body
    
            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }


## Generate Updated Recommendations [/v2/rightsizing/recommendations/update]

### POST

+ Request (application/json)

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 200 (application/json)

+ Response 401 (application/json)

    
    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }

+ Response 403 (application/json)

    
    + Body

            {
                "code": "INVALID_PERMISSIONS",
                "detail_code": "",
                "message": "not authorized to access this route"
            }

# Data Structures

## Setting
 + enabled: `true` (boolean, required) - is rightsizing enabled for the team
 + `time_range_id` (number, required) - heatmap range ID

## IgnoreOptions
+ code_id: `1` (number, required) - ignore code ID related to existed codes
+ comment: `Some comment` (string) - user's comment

## IgnoreCode
 + id: `1` (number, required) - ignore code ID
 + name: `Operations` (string, required) - ignore code name
 + description: `We cannot make a change that will disrupt operations and/or the resource must remain the current size for functional reasons.` (string, optional) - ignore code description

## RightsizingSettings
 + type: `month` (enum[string], required) - type of settings
   + month
   + fiscal_quarter
   + fiscal_year
 + start_month: `12` (number, optional) - 1-12 selected start month for fiscal quarter and fiscal year
 + duration: `18` (number, optional) - 1-240 duration for month type

## RightsizingRecommendation
 + id: `1` (number, required) - recommendation ID
 + resource_id: `1` (number, required) - resource ID
 + action (enum[string], required) - action of the recommendation
   + modernize
   + resize
   + no_change
 + caveat (enum[string], optional) - caveat of the recommendation
   + no_metrics
   + not_enough_metrics
   + no_memory_metrics
   + only_modernizing
   + no_resize_target
   + no_change
   + not_enough_time
 + status (enum[string], required) - status of the recommendation
   + open
   + accepted
   + ignored
   + timeout
   + cancelled
 + created_at: `2017-10-02T00:00:00Z`  (string, required) - when recommendation created
 + updated_at: `2017-10-02T00:00:00Z`  (string, optional) - when recommendation updated
 + target_type: `m4.2xlarge` (string, optional)- The new recommended resource type.

## Group Resources API

## Get Resources [/eng/resources/{resource_id}]

### GET

+ Parameters
  + resource_id: `1` (number, required) - resource id

+ Request (application/json)

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 200 (application/json)
    + Attributes (ResourceData)

+ Response 404 (application/json) 
    
    + Body

            {
                "code": "NOT_FOUND",
                "detail_code": "",
                "message": "Item not found"
            }

## Resource Stats [/resources/stats{?credential,location,metrics,name,provider,recommended,recommendation,schedule,search,state,status,tags,team,type}]

### GET

- Parameters

    - credential: MyCred (string, optional) - A portion of a resource's credential name. Used in a sub-string match to
      filter by credential name. May be prefixed with `-` to perform a "NOT" filter.
    - location: us-east (string, optional) - A portion of a resource's location. Used in a sub-string match to
      filter by location. May be prefixed with `-` to perform a "NOT" filter.
    - metrics: true (boolean, optional) - A value indicating whether to return resources that do or do not have
      usage metrics. Pass `true` to only return resources that do have usage metrics, or `false` to only
      return resources without usage metrics.
    - name: dev-serv (string, optional) - A portion of a resource's name. Used in a sub-string match to
      filter by name. May be prefixed with `-` to perform a "NOT" filter.
    - provider: aws (string, optional) - A portion of a resource's provider name. Used in a sub-string match to
      filter by provider name. May be prefixed with `-` to perform a "NOT" filter.
    - recommended: true (boolean, optional) - A boolean value indicating whether to only return resources that have
      some sort of schedule recommendation. Pass `true` to only return resources that have any type of
      recommendation. Passing `false` is not supported.
    - recommendation: smartpark,resize (array[enum[string]], optional) - A comma-separated list of recommendation types that should be returned.
          - smartpark
          - resize
    - schedule: always (string, optional) - A portion of a resource's schedule name. Used in a sub-string match to
      filter by schedule name. May be prefixed with `-` to perform a "NOT" filter.
    - search: t2 (string, optional) - A search term that will be applied to numerous fields at once. The values
      for several fields are concatenated together with a space (` `) character and a sub-string match is
      performed using the specified search term. The fields used are "team name", "credential name",
      "provider name", "location", "name", "schedule name", "state", "info text", "CSP instance ID", and
      "tags". May be prefixed with `-` to perform a "NOT" filter.
    - state: parked (enum[string], optional) - A value indicating a resource's state. Only resources that are currently in
      the specified state will be returned.
          - running
          - starting
          - stopping
          - stopped
          - parking
          - parked
    - status: attached (enum[string], optional) - A value indicating a resource's schedule status.
          - attached
          - detached
          - snoozed
    - tags: abcd1234 (string, optional) - A search term that will be applied to a resource's tags. A sub-string match is
      performed against the resource's tag keys and values. May be prefixed with `-` to perform a "NOT" filter.
    - team: dev (string, optional) - A portion of a resource's team name. Used in a sub-string match to filter by team
      name. May be prefixed with `-` to perform a "NOT" filter.
    - type: asg,lg (array[enum[string]], optional) - A comma-separated list of resource types that should be returned.
          - compute
          - asg
          - lg
          - rds

- Request

    - Headers

            X-Auth-Token: <Authorization Token>

- Response 200 (application/json)

    - Attributes (ResourceStats)

- Response 400 (application/json)

    - Body

                {
                    "code": "INVALID_REQUEST",
                    "detail_code": "",
                    "message": "Invalid request"
                }

- Response 401 (application/json)

    - Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }



## List Resources [/resources/paged{?credential,location,metrics,name,provider,recommended,recommendation,schedule,search,state,status,tags,team,type,page,pageSize,sort}]

### GET

- Parameters

    - credential: MyCred (string, optional) - A portion of a resource's credential name. Used in a sub-string match to
      filter by credential name. May be prefixed with `-` to perform a "NOT" filter.
    - location: us-east (string, optional) - A portion of a resource's location. Used in a sub-string match to
      filter by location. May be prefixed with `-` to perform a "NOT" filter.
    - metrics: true (boolean, optional) - A value indicating whether to return resources that do or do not have
      usage metrics. Pass `true` to only return resources that do have usage metrics, or `false` to only
      return resources without usage metrics.
    - name: dev-serv (string, optional) - A portion of a resource's display name. Used in a sub-string match to
      filter by name. May be prefixed with `-` to perform a "NOT" filter.
    - provider: aws (string, optional) - A portion of a resource's provider name. Used in a sub-string match to
      filter by provider name. May be prefixed with `-` to perform a "NOT" filter.
    - recommended: true (boolean, optional) - A boolean value indicating whether to only return resources that have
      some sort of schedule recommendation. Pass `true` to only return resources that have any type of
      recommendation. Passing `false` is not supported.
    - recommendation: resize,smartpark (array[enum[string]], optional) - A comma-separated list of recommendation types that should be returned.
          - resize
          - smartpark
    - schedule: always (string, optional) - A portion of a resource's schedule name. Used in a sub-string match to
      filter by schedule name. May be prefixed with `-` to perform a "NOT" filter.
    - search: t2 (string, optional) - A search term that will be applied to numerous fields at once. The values
      for several fields are concatenated together with a space (` `) character and a sub-string match is
      performed using the specified search term. The fields used are "team name", "credential name",
      "provider name", "location", "name", "schedule name", "state", "info text", "CSP instance ID", and
      "tags". May be prefixed with `-` to perform a "NOT" filter.
    - state: parked (enum[string], optional) - A value indicating a resource's state. Only resources that are currently in
      the specified state will be returned.
          - running
          - starting
          - stopping
          - stopped
          - parking
          - parked
    - status: attached (enum[string], optional) - A value indicating a resource's schedule status.
          - attached
          - detached
          - snoozed
    - tags: abcd1234 (string, optional) - A search term that will be applied to a resource's tags. A sub-string match is
      performed against the resource's tag keys and values. May be prefixed with `-` to perform a "NOT" filter.
    - team: dev (string, optional) - A portion of a resource's team name. Used in a sub-string match to filter by team
      name. May be prefixed with `-` to perform a "NOT" filter.
    - type: asg,lg (array[enum[string]], optional) - A comma-separated list of resource types that should be returned.
          - compute
          - asg
          - lg
          - rds
    - page: 1 (integer, optional) - The page number of results to return. Pages are 1-indexed, meaning page 1 is the
      first page.

      Default: 1
    - pageSize: 200 (integer, optional) - The size of the page of results to return. The minimum page size is 1; the
      maximum page size is 500.

      Default: 200
    - sort: name (string, optional) - The field by which the results should be sorted. By default, results are sorted
      by their create time and then their primary key identifier. When a value is provided for the `sort` parameter,
      that field is used for the first-order sort, then the results are further sorted by create time and primary key
      identifier. May be prefixed with `-` to perform a "reverse" (or descending) sort.

- Request

    - Headers

            X-Auth-Token: <Authorization Token>

- Response 200 (application/json)

    - Attributes (ResourcesResponse)

- Response 400 (application/json)

    - Body

                {
                    "code": "INVALID_REQUEST",
                    "detail_code": "",
                    "message": "Invalid request"
                }

- Response 401 (application/json)

    - Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }



## Resource States [/resource-states]

### GET

+ Request

    + Headers

            X-Auth-Token: <Authorization Token>

+ Response 200 (application/json)

    + Body 

                {
                    "items": [
                        [
                            0,                                // Parent ID or zero
                            4,                                // ID
                            "running",                        // State, or empty string
                            0,                                // Recommendation
                            1006,                             // Schedule ID, or null 
                            1,                                // Snoozed 0 or 1 
                            "2016-08-31T16:53:06Z",           // Schedule snoozed until 
                            3,                                // Team ID
                            0                                 // restriction: null, 0, 1, or 2
                        ],
                        [
                            0,
                            5,
                            "stopped",
                            0,
                            null,
                            0,
                            null,
                            3,
                            null
                        ]
                    ]
                }

+ Response 401 (application/json)

    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }

## Toggle Resources [/resources/toggle]

Resources can be started or stopped by sending a list of IDs along with the action of `start` or `stop`.
If the user is not allowed access to the specified team, the service will return 403 with code 'INVALID_PERMISSIONS'.
Additionally it may change state of an overridden Logical Group member.

### PUT

+ Request

    + Headers

            X-Auth-Token: <Authorization Token>
    
    + Attributes (Put Toggle)

+ Response 202

    Starting/stopping process is initiated. It may take some time.

    + Body

+ Response 401 (application/json)

    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }

+ Response 403

    Starting/stopping process is initiated. It may take some time.

    + Attributes

        + `code`: `LIMITED_BY_PLAN` (string)

## Resources Change Team [/resources/change-team]

Changes the team associated with a resource

### PUT

+ Request

    + Headers

            X-Auth-Token: <Authorization Token>
    
    + Attributes (Put Change Team)

+ Response 200

    Resources have changed teams

    + Body

+ Response 400

    If any of the specified items are archived, or are members of a group, or are not
accessible by the user through group membership

    + Attributes

        + `code`: `INVALID_REQUEST` (string)

+ Response 401 (application/json)

    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }

+ Response 403

    The user is not allowed access to the specified team

    + Attributes

        + `code`: `INVALID_PERMISSIONS` (string)


## Resource details [/resources/detail/{id}]

Provides detailed information on the given resource.
If the resource is an overridden Logical Group member then `data.pmc_detail.parking_calendar` section contains parent LG's fields (`id`, `name`, ...)
while `snooze_until` holds an RFC3339 encoded timestamp associated with the LG member.

## GET

+ Request 

    + Headers

            X-Auth-Token: <Authorization Token>

+ Parameters
  + id: `1` (number, required) - resource id

+ Response 200 (application/json)
    AWS Response
    + Body
      {
        "data": {
          "ami_launch_index": 0,
          "architecture": "x86_64",
          "block_device_mapping": [
            {
              "device_name": "/dev/sda1",
              "ebs": {
                "attach_time": "2020-05-19T20:49:25Z",
                "delete_on_termination": true,
                "status": "attached",
                "volume_id": "vol-08e81e75806df40ff"
              }
            }
          ],
          "client_token": "API-v-PMCSe-G1UQGYEOYI6D",
          "display_name": "API-v8-3-0-2020-05-19--16-48",
          "dns_name": "",
          "ebs_optimized": false,
          "group_set": [
            {
              "group_id": "sg-0eedb05d89b23ccfd",
              "group_name": "Dev-test-eu-north-1"
            },
            {
              "group_id": "sg-04ba6153a2a0a602a",
              "group_name": "pmc-autotest-api-servers"
            }
          ],
          "hypervisor": "xen",
          "iam_instance_profile": {
            "arn": "arn:aws:iam::078013660993:instance-profile/pmc-instance-deploy",
            "id": "AIPAJBT4BHJ6CVR7VNGHA"
          },
          "image_id": "ami-017ad30b324faed9b",
          "instance_id": "i-01378e5c2cb035562",
          "instance_state": {
            "code": 80,
            "name": "stopped"
          },
          "instance_type": "t3.medium",
          "key_name": "pmc-dev-eu-north-1",
          "launch_time": "2020-05-19T20:49:24Z",
          "monitoring": {
            "state": "enabled"
          },
          "network_interface_set": [
            {
              "attachment": {
                "attach_time": "2020-05-19T20:49:24Z",
                "attachment_id": "eni-attach-02ff08a7b658a3223",
                "delete_on_termination": true,
                "device_index": 0,
                "status": "attached"
              },
              "description": "",
              "group_set": [
                {
                  "group_id": "sg-0eedb05d89b23ccfd",
                  "group_name": "Dev-test-eu-north-1"
                },
                {
                  "group_id": "sg-04ba6153a2a0a602a",
                  "group_name": "pmc-autotest-api-servers"
                }
              ],
              "mac_address": "0e:74:5f:ba:7b:ee",
              "network_interface_id": "eni-0ea222ad0a37da331",
              "owner_id": "078013660993",
              "private_dns_name": "ip-172-31-5-166.eu-north-1.compute.internal",
              "private_ip_address": "172.31.5.166",
              "private_ip_address_set": [
                {
                  "primary": true,
                  "private_dns_name": "ip-172-31-5-166.eu-north-1.compute.internal",
                  "private_ip_address": "172.31.5.166"
                }
              ],
              "source_dest_check": true,
              "status": "in-use",
              "subnet_id": "subnet-0706018807d9283df",
              "vpc_id": "vpc-00ab1f3d3d0b30a2e"
            }
          ],
          "placement": {
            "availability_zone": "eu-north-1c",
            "group_name": "",
            "tenancy": "default"
          },
          "pmc_detail": {
            "id": 26495,
            "parent_id": 0,
            "created_time": "1639560432",
            "type": "compute",
            "csp_instance_id": "i-01378e5c2cb035562",
            "state": "stopped",
            "location": "eu-north-1",
            "name": "API-v8-3-0-2020-05-19--16-48",
            "cost": 31.54,
            "has_heatmap_data": false,
            "purchasing_option": "on_demand",
            "info_text": "t3.medium",
            "restriction": 0,
            "stoppable": true,
            "spr_enabled": true,
            "parking_calendar": null,
            "recommendation": "",
            "tags": [
              {
                "key": "InstallStatus",
                "value": "SUCCESS"
              },
              {
                "key": "Name",
                "value": "API-v8-3-0-2020-05-19--16-48"
              },
              {
                "key": "Version",
                "value": "v8.3.0"
              },
              {
                "key": "VersionEng",
                "value": "v8.3.0"
              },
              {
                "key": "Create AMI",
                "value": "No"
              },
              {
                "key": "VersionClient",
                "value": "v8.3.0"
              },
              {
                "key": "InstallData",
                "value": "All OK"
              },
              {
                "key": "VersionServer",
                "value": "v8.3.0"
              },
              {
                "key": "Role",
                "value": "API"
              },
              {
                "key": "aws:cloudformation:stack-id",
                "value": "arn:aws:cloudformation:eu-north-1:078013660993:stack/API-v8-3-0-2020-05-19--16-48/31d7da60-9a12-11ea-8638-0e13c5678742"
              },
              {
                "key": "aws:cloudformation:logical-id",
                "value": "PMCServerInstance"
              },
              {
                "key": "aws:cloudformation:stack-name",
                "value": "API-v8-3-0-2020-05-19--16-48"
              }
            ],
            "credential": {
              "id": 34,
              "name": "aws"
            },
            "team": {
              "id": 95,
              "name": "My First Team"
            },
            "provider": {
              "id": 1,
              "name": "aws"
            },
            "origin_cost": 31.54,
            "instance_cost": 31.54,
            "cost_overridden": false,
            "recommendations": {},
            "is_rds_cluster": false,
            "resize_enabled": true,
            "os": "",
            "display_name": "API-v8-3-0-2020-05-19--16-48",
            "parent": null
          },
          "pmc_resource_type": "instance",
          "private_dns_name": "ip-172-31-5-166.eu-north-1.compute.internal",
          "private_ip_address": "172.31.5.166",
          "provider_status": "stopped",
          "root_device_name": "/dev/sda1",
          "root_device_type": "ebs",
          "snapshots": [],
          "source_dest_check": true,
          "state_reason": {
            "code": "Client.InstanceInitiatedShutdown",
            "message": "Client.InstanceInitiatedShutdown: Instance initiated shutdown"
          },
          "subnet_id": "subnet-0706018807d9283df",
          "tag_set": [
            {
              "key": "InstallStatus",
              "value": "SUCCESS"
            },
            {
              "key": "Name",
              "value": "API-v8-3-0-2020-05-19--16-48"
            },
            {
              "key": "Version",
              "value": "v8.3.0"
            },
            {
              "key": "VersionEng",
              "value": "v8.3.0"
            },
            {
              "key": "Create AMI",
              "value": "No"
            },
            {
              "key": "VersionClient",
              "value": "v8.3.0"
            },
            {
              "key": "InstallData",
              "value": "All OK"
            },
            {
              "key": "VersionServer",
              "value": "v8.3.0"
            },
            {
              "key": "Role",
              "value": "API"
            },
            {
              "key": "aws:cloudformation:stack-id",
              "value": "arn:aws:cloudformation:eu-north-1:078013660993:stack/API-v8-3-0-2020-05-19--16-48/31d7da60-9a12-11ea-8638-0e13c5678742"
            },
            {
              "key": "aws:cloudformation:logical-id",
              "value": "PMCServerInstance"
            },
            {
              "key": "aws:cloudformation:stack-name",
              "value": "API-v8-3-0-2020-05-19--16-48"
            }
          ],
          "type_info": {
            "provider": "aws",
            "type": "t3.medium",
            "features": [
              {
                "id": "type",
                "name": "Instance Type",
                "raw": "t3.medium",
                "value": "t3.medium"
              },
              {
                "id": "vcpu",
                "name": "vCPU",
                "raw": 2,
                "value": "2"
              },
              {
                "id": "mem",
                "name": "Memory",
                "raw": 4096,
                "value": "4 GB"
              },
              {
                "id": "enh.net",
                "name": "Enhanced Network",
                "raw": true,
                "value": "Yes"
              },
              {
                "id": "store",
                "name": "Instance Store",
                "raw": "ebs only",
                "value": "EBS only"
              },
              {
                "id": "spot",
                "name": "Spot Instance",
                "raw": false,
                "value": "—"
              },
              {
                "id": "cost",
                "name": "Monthly Cost",
                "raw": 31.536,
                "value": "$31.54"
              }
            ],
            "attributes": {
              "availabilityzone": "",
              "classicnetworkingsupport": "false",
              "clockspeed": "3.1 GHz",
              "currentgeneration": "yes",
              "dedicatedebsthroughput": "Up to 2085 Mbps",
              "ecu": "variable",
              "enasupport": "yes",
              "enhancednetworkingsupported": "yes",
              "instancefamily": "general purpose",
              "instancetype": "t3.medium",
              "intelavx2available": "yes",
              "intelavxavailable": "yes",
              "intelturboavailable": "yes",
              "locationtype": "aws region",
              "marketoption": "ondemand",
              "memory": "4096",
              "networkperformance": "Up to 5 Gigabit",
              "normalizationsizefactor": "2",
              "physicalprocessor": "Intel Skylake E5 2686 v5",
              "processorarchitecture": "64-bit",
              "processorfeatures": "AVX; AVX2; Intel AVX; Intel AVX2; Intel AVX512; Intel Turbo",
              "servicecode": "AmazonEC2",
              "servicename": "Amazon Elastic Compute Cloud",
              "storage": "ebs only",
              "vcpu": "2",
              "vpcnetworkingsupport": "true"
            }
          },
          "virtualization_type": "hvm",
          "volumes": [
            {
              "id": 16818,
              "location": "eu-north-1c",
              "availability_zone": "eu-north-1c",
              "cred_id": 7,
              "region": "eu-north-1",
              "instance_id": "i-01378e5c2cb035562",
              "create_time": "2020-05-19T20:49:25Z",
              "encrypted": false,
              "iops": 120,
              "kms_key_id": "",
              "size": 40,
              "snapshot_id": "snap-080f4321353a90b28",
              "volume_id": "vol-08e81e75806df40ff",
              "volume_type": "gp2",
              "state": "in-use",
              "attachment": {
                "attach_time": "2020-05-19T20:49:25Z",
                "delete_on_termination": true,
                "device": "/dev/sda1",
                "state": "attached"
              }
            },
            {
              "id": 75201,
              "location": "eu-north-1c",
              "availability_zone": "eu-north-1c",
              "cred_id": 34,
              "region": "eu-north-1",
              "instance_id": "i-01378e5c2cb035562",
              "create_time": "2020-05-19T20:49:25Z",
              "encrypted": false,
              "iops": 120,
              "kms_key_id": "",
              "size": 40,
              "snapshot_id": "snap-080f4321353a90b28",
              "volume_id": "vol-08e81e75806df40ff",
              "volume_type": "gp2",
              "state": "in-use",
              "attachment": {
                "attach_time": "2020-05-19T20:49:25Z",
                "delete_on_termination": true,
                "device": "/dev/sda1",
                "state": "attached"
              }
            }
          ],
          "vpc_id": "vpc-00ab1f3d3d0b30a2e"
        }
      }

+ Response 200 (application/json)
    Azure Response
    + Body
      {
        "data": {
          "azure_rg_name": "DefaultResourceGroup-CUS",
          "classic": false,
          "display_name": "DefaultResourceGroup-CUS/ubuntu18",
          "id": "/subscriptions/7a7a385d-4817-4511-b6f8-55b72498e0c9/resourceGroups/DefaultResourceGroup-CUS/providers/Microsoft.Compute/virtualMachines/ubuntu18",
          "image_reference": {
            "offer": "UbuntuServer",
            "publisher": "Canonical",
            "sku": "18.04-LTS",
            "version": "latest"
          },
          "location": "westus2",
          "name": "ubuntu18",
          "os_type": "Linux",
          "pmc_detail": {
            "id": 27010,
            "parent_id": 0,
            "created_time": "1639754299",
            "type": "compute",
            "csp_instance_id": "/subscriptions/7a7a385d-4817-4511-b6f8-55b72498e0c9/resourceGroups/DefaultResourceGroup-CUS/providers/Microsoft.Compute/virtualMachines/ubuntu18",
            "state": "stopped",
            "location": "westus2",
            "name": "ubuntu18",
            "cost": 30.37,
            "has_heatmap_data": true,
            "purchasing_option": "on_demand",
            "info_text": "Standard_B2s",
            "restriction": 0,
            "stoppable": true,
            "spr_enabled": true,
            "parking_calendar": null,
            "recommendation": "smartpark",
            "tags": [
              {
                "key": "vkim",
                "value": "testVM"
              }
            ],
            "credential": {
              "id": 35,
              "name": "az"
            },
            "team": {
              "id": 95,
              "name": "My First Team"
            },
            "provider": {
              "id": 3,
              "name": "azure"
            },
            "origin_cost": 30.37,
            "instance_cost": 30.37,
            "cost_overridden": false,
            "recommendations": {
              "smartpark": {
                "max_savings": 30.37,
                "min_savings": 30.01,
                "max_savings_percent": 100,
                "min_savings_percent": 98.81
              }
            },
            "is_rds_cluster": false,
            "resize_enabled": true,
            "os": "Linux",
            "display_name": "DefaultResourceGroup-CUS/ubuntu18",
            "parent": null
          },
          "power_state": "deallocated",
          "private_ips": [
            "172.16.1.4"
          ],
          "provisioning_state": "Succeeded",
          "public_ips": [],
          "snapshots": [
            {
              "id": 286,
              "cred_id": 35,
              "updated_at": "2022-01-11T13:32:34Z",
              "name": "fullsnapshot",
              "resource_group": "PMC-WEST",
              "subscription_id": "7a7a385d-4817-4511-b6f8-55b72498e0c9",
              "type": "Microsoft.Compute/snapshots",
              "location": "westus2",
              "sku_type": "Standard_ZRS",
              "sku_tier": "Standard",
              "tags": {},
              "properties": {
                "time_created": "2020-05-28T15:05:23Z",
                "os_type": "Linux",
                "hyper_v_gen": "V1",
                "disk_size_gb": 30,
                "disk_size_bytes": 32213303296,
                "unique_id": "bcc4bf10-10fb-4586-a126-e9e6189f9db5",
                "provisioning_state": "Succeeded",
                "enc_set_id": "",
                "enc_set_ver": "",
                "enc_type": "EncryptionAtRestWithPlatformKey",
                "enc_set_enabled": false,
                "incremental": false,
                "creation_data": {
                  "create_option": "Copy",
                  "storage_account_id": "",
                  "image_ref_id": "",
                  "image_ref_lun": 0,
                  "gallery_image_ref_id": "",
                  "gallery_image_ref_lun": 0,
                  "source_uri": "",
                  "source_resource_id": "/subscriptions/7a7a385d-4817-4511-b6f8-55b72498e0c9/resourceGroups/DEFAULTRESOURCEGROUP-CUS/providers/Microsoft.Compute/disks/ubuntu18_disk1_b3b121f37ec749efb91d6aea54d677e3",
                  "source_unique_id": "b3b121f3-7ec7-49ef-b91d-6aea54d677e3",
                  "upload_size_bytes": 0
                }
              }
            }
          ],
          "statuses": [
            {
              "code": "ProvisioningState/succeeded",
              "display_status": "Provisioning succeeded",
              "provider_status": "Provisioning succeeded"
            },
            {
              "code": "PowerState/deallocated",
              "display_status": "VM deallocated",
              "provider_status": "VM deallocated"
            }
          ],
          "type": "Microsoft.Compute/virtualMachines",
          "type_info": {
            "provider": "azure",
            "type": "Standard_B2s",
            "features": [
              {
                "id": "vcpu",
                "name": "vCPU",
                "raw": 2,
                "value": "2"
              },
              {
                "id": "mem",
                "name": "Memory",
                "raw": 4096,
                "value": "4 GB"
              },
              {
                "id": "mdd",
                "name": "Max Data Disk Count",
                "raw": 4,
                "value": "4"
              },
              {
                "id": "premio",
                "name": "Premium IO",
                "raw": true,
                "value": "true"
              },
              {
                "id": "premio",
                "name": "Premium IO",
                "raw": true,
                "value": "true"
              },
              {
                "id": "size",
                "name": "Machine Size",
                "raw": "B2s",
                "value": "B2s"
              },
              {
                "id": "version",
                "name": "Machine Version",
                "raw": 0,
                "value": "0"
              },
              {
                "id": "cost",
                "name": "Monthly Cost",
                "raw": 30.368,
                "value": "$30.37"
              }
            ],
            "attributes": {}
          },
          "uuid": "db46c5a4-c18c-489a-a873-7b2818547330",
          "vm_size": "Standard_B2s",
          "volumes": [
            {
              "id": 5166,
              "cred_id": 35,
              "updated_at": "2022-01-11T13:32:33Z",
              "native_id": "/subscriptions/7a7a385d-4817-4511-b6f8-55b72498e0c9/resourceGroups/DEFAULTRESOURCEGROUP-CUS/providers/Microsoft.Compute/disks/ubuntu18_disk1_b3b121f37ec749efb91d6aea54d677e3",
              "name": "ubuntu18_disk1_b3b121f37ec749efb91d6aea54d677e3",
              "resource_group": "DEFAULTRESOURCEGROUP-CUS",
              "subscription_id": "7a7a385d-4817-4511-b6f8-55b72498e0c9",
              "type": "Microsoft.Compute/disks",
              "location": "westus2",
              "managed_by": "/subscriptions/7a7a385d-4817-4511-b6f8-55b72498e0c9/resourceGroups/DefaultResourceGroup-CUS/providers/Microsoft.Compute/virtualMachines/ubuntu18",
              "managed_by_extra": [],
              "sku_type": "Premium_LRS",
              "sku_tier": "Premium",
              "zones": [],
              "tags": {},
              "properties": {
                "time_created": "2020-04-08T15:49:44Z",
                "os_type": "Linux",
                "hyper_v_gen": "V1",
                "disk_size_gb": 30,
                "disk_size_bytes": 32213303296,
                "unique_id": "b3b121f3-7ec7-49ef-b91d-6aea54d677e3",
                "provisioning_state": "Succeeded",
                "disk_iops_read_write": 120,
                "disk_mbps_read_write": 25,
                "disk_iops_read_only": 0,
                "disk_mbps_read_only": 0,
                "disk_state": "Reserved",
                "enc_set_id": "",
                "enc_set_ver": "",
                "enc_type": "EncryptionAtRestWithPlatformKey",
                "enc_set_enabled": false,
                "max_shares": 0,
                "share_info": [],
                "creation_data": {
                  "create_option": "FromImage",
                  "storage_account_id": "",
                  "image_ref_id": "/Subscriptions/45231f81-377d-441c-af2b-e409bd355507/Providers/Microsoft.Compute/Locations/westus2/Publishers/canonical/ArtifactTypes/VMImage/Offers/ubuntuserver/Skus/18.04-lts/Versions/18.04.202003250",
                  "image_ref_lun": 0,
                  "gallery_image_ref_id": "",
                  "gallery_image_ref_lun": 0,
                  "source_uri": "",
                  "source_resource_id": "",
                  "source_unique_id": "",
                  "upload_size_bytes": 0
                }
              }
            }
          ]
        }
      }

+ Response 200 (application/json)
    Alibaba Response
    + Body
            {
                "data": {
                    "display_name":"pmc-test",
                    "cpu": 1,
                    "create_time": "2018-06-04T10:49Z",
                    "description": "",
                    "hostname": "iZrj9a0z1wy5zy10mfen82Z",
                    "image_id": "ubuntu_16_0402_64_20G_alibase_20180409.vhd",
                    "instance_charge_type": "PostPaid",
                    "memory": 512,
                    "network_interface_set": [
                    {
                        "description": "",
                        "mac_address": "00:16:3e:00:19:8e",
                        "network_interface_id": "eni-rj9abw0e4r5uq4ofeg9g",
                        "network_interface_name": "",
                        "private_ip_address": "172.20.187.15"
                    }
                    ],
                    "os": "Ubuntu  16.04 64位",
                    "pmc_detail": {
                    "id": 1,
                    "created_time": "1528887513",
                    "type": "compute",
                    "csp_instance_id": "i-rj9a0z1wy5zy10mfen82",
                    "state": "stopped",
                    "location": "us-west-1",
                    "name": "pmc-test",
                    "cost": 5.11,
                    "has_heatmap_data": false,
                    "purchasing_option": "on_demand",
                    "info_text": "ecs.t5-lc2m1.nano",
                    "restriction": 0,
                    "stoppable": true,
                    "spr_enabled": true,
                    "parking_calendar": null,
                    "recommendation": "none",
                    "tags": [
                        {
                        "key": "test",
                        "value": "test"
                        }
                    ],
                    "credential": {
                        "id": 1,
                        "name": "alibaba"
                    },
                    "team": {
                        "id": 1,
                        "name": "My First Team"
                    },
                    "provider": {
                        "id": 4,
                        "name": "alibaba"
                    },
                    "parent": null
                    },
                    "serial_number": "67719316-65f4-4c3e-b711-d3efd20304b6",
                    "spot_strategy": "NoSpot",
                    "start_time": "2018-06-13T14:30Z",
                    "stopped_mode": "StopCharging",
                    "vlan_id": "",
                    "zone_id": "us-west-1b"
                }
            }

+ Response 401 (application/json)

    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }

+ Response 403

    The user is not allowed access to the specified team

    + Attributes

        + `code`: `CSP_ACCESS_DENIED` (string)
        + `message`: `CSP did not allow access to resource detail` (string)


# Data Structures

## ResourceData

- id: 1 (number) - The resource's primary key identifier
- created_time: 1520972819 (string) - The time at which the resource was created (Unix timestamp format)
- type (enum[string]) - The type of cloud computing resource
    - compute
    - asg
    - lg
    - rds
- csp_instance_id: `i-c78e891dbf13acb88` (string) - The resource's ID from its cloud service provider
- state (enum[string]) - The run state of the resource
    - running
    - starting
    - stopping
    - stopped
    - parking
    - parked
- location: `ap-southeast-1` (string) - The resource's location
- name: Dev Server 1 (string) - The resource's name
- cost: 85.26 (number) - The resource's estimated monthly cost. User can override this cost.
- origin_cost: 85.26 (number) - The resource's estimated monthly cost according to discovered price
- cost_overridden: false (boolean) - Whether user override the resource cost
- has_heatmap_data: true (boolean) - Whether the resource has metrics ("heatmap") data
- spr_enabled: true (boolean) - Whether smartpark recommendation generation is enabled for this resource
- `purchasing_option`: on_demand (string) - BAR
- info_text: t2.large (string) - Text describing the resource type
- restriction (enum[number]) - A parking restriction for the resource
    - 0 - No Restrictions
    - 1 - Never park; all parking actions are disabled
    - 2 - Schedule can only be overridden
- parking_calendar (object) - The resource's parking calendar (schedule)
    - id: 1 (number) - The parking calendar's primary key identifier. If the resource is an overridden member of a Logical Group then the parent calendar id is returned.
    - snooze_until: 1520972819 (string) - The time at which the schedule should be un-snoozed (Unix timestamp format). NULL if resource not snoozed
    - name: `Up M-F, 7 am - 7 pm` (string) - A name of a parking calendar. If the resource is an overridden member of a Logical Group then the parent calendar's name is returned.
- recommendation (enum[string]) - The type of recommendation for the resource
    - smartpark
    - resize
    - none
- recommendations (Recommendations) - resource recommendation
- tags (array) - Key/value pairs of resource metadata
    - (object)
        - key: `Name` (string) - The key name
        - value: `Dev Server 1` (string) - The key value
- credential (object) - The resource's cloud credential
    - id: 1 (number) - The credential's primary key identifier
    - name: `AWS Cred 01` (string) - The credential's name
- team (object) - The resource's team
    - id: 1 (number) - The team's primary key identifier
    - name: `My Team 01` (string) - The teams's name
- provider (object) - The resource's cloud service provider
    - id: 1 (number) - The provider's primary key identifier
    - name (enum[string]) - The provider's name
        - aws
        - gcp
        - azure
- display_name: Resource Group/Dev Server 1 (string) - In case of Azure provider, display_name is of format <resource_group>/<instance_name>, For other providers, it is same as resource's name.

## ResourcesResponse

- data (array[ResourceData])
- counts
    - all: 1 (number) - Total number of resources in result set
    - recommended: 0 (number) - Number of resources in result set with recommendations
    - running: 1 (number) - Number of resources in result set that are currently running 
    - scheduled: 0 (number) - Number of resources in result set that have a schedule attached
    - snoozed: 0 (number) - Number of resources in result set that are currently "snoozed"
- page_info
    - page: 1 (number) - Page number of results
    - page_size: 200 (number) - Maximum number of results per page
    - total_pages: 10 (number) - Total number of result pages

## Recommendations
- smartpark (SPRResourceSavings, optional) - smartpark savings
- resize (ResourceSavings, optional) - resize savings

## ResourceSavings
- max_savings: 10.5 (number, required) - max savings
- mim_savings: 1.5 (number, required) - min savings

## SPRResourceSavings(ResourceSavings)
- max_savings_percent: 94.64 (number, required) - max savings percent
- min_savings_percent: 84.33 (number, required) - min savings percent

## ResourceStats(object)
- monthly_savings: 12345.67 (number, required) - projected amount of dollar savings (month-worth)
- annualy_savings: 12345.67 (number, required) - projected amount of dollar savings (year-worth)
- total: 21500 (number, required) - total number of matching resources
- running: 1025 (number, required) - number of running resources
- scheduled: 5670 (number, required) - number of resources with a schedule
- snoozed: 17 (number, required) - number of resources with an overridden schedule
- recommended: 559 (number, required) - number of resources having some type of recommendation

## Put Toggle(object)
 + `action` (enum[string], optional) - the action to take
   + Members
     - `start` - start a resource
     - `stop` - stop a resource
 + `item_ids` (array[number], required) - list of resource ids
   - 1
   - 2  

## Put Change Team(object)
 + `team_id` (number, required) - team id
 + `item_ids` (array[number], required) - list of resource ids
   - 1
   - 2  

# Group Team API V2

An API that provides operations for interacting with ParkMyCloud teams, and their respective settings.

## About

https://parkmycloud.atlassian.net/wiki/spaces/PMCUG/pages/182321/Team+Management

## Authentication

All requests to this API must be authenticated using an authorization token. The
authorization token must be provided using the `X-Auth-Token` request header.
For example:

```http
X-Auth-Token: cd57fa5140a0c7bf0e6f3bed9b109771
```

For details on how to obtain an authorization token, see the documentation for
the `/auth` API.

## List Teams [/v2/teams{?associated_only}]
A resource representing all of the teams in the callers organization, and the respective team leads.

### GET

+ Request

    + Headers

            X-Auth-Token: <Authorization Token>

+ Parameters

    + associated_only (bool, optional) - Limit the returned teams to only those associated with the caller.
        + Default: `false`

+ Response 200 (application/json)

    + Attributes (List Teams)


+ Response 401 (application/json)

    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }

+ Response 403 (application/json)

    + Body
    
            {
                "code": "INVALID_PERMISSIONS",
                "detail_code": "",
                "message": "not authorized to access this route"
            }

## Create a Team [/v2/teams]

A resource to create a team with associated users

### POST

+ Request (application/json)

    + Headers

            X-Auth-Token: <Authorization Token>
    
    + Attributes (Upsert Team)

+ Response 201 (application/json)

    + Attributes (Upserted Team)

+ Response 400 (application/json)

    + Body
    
            {
                "code": "INVALID_REQUEST",
                "detail_code": "",
                "message": "Failed to validate users"
            }

+ Response 401 (application/json)

    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }

+ Response 403 (application/json)

    + Body
    
            {
                "code": "INVALID_PERMISSIONS",
                "detail_code": "",
                "message": "not authorized to access this route"
            }
##  Get/Update/Delete Team By ID [/v2/teams/{id}]
A resource representing a team in my organization, and the associated users.


+ Parameters
  + id: `1` (number, required) - team id

### GET

+ Request

    + Headers

            X-Auth-Token: <Authorization Token>

+ Response 200 (application/json)
     
    + Attributes (Get Team)
            

+ Response 401 (application/json)

    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }

+ Response 403 (application/json)

    + Body
    
            {
                "code": "INVALID_PERMISSIONS",
                "detail_code": "",
                "message": "not authorized to access this route"
            }

### PUT

+ Request (application/json)

    + Headers

            X-Auth-Token: <Authorization Token>

    + Attributes (Upsert Team)

+ Response 200 (application/json)

    + Attributes (Upserted Team)
            
+ Response 401 (application/json)

    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }

+ Response 403 (application/json)

    + Body
    
            {
                "code": "INVALID_PERMISSIONS",
                "detail_code": "",
                "message": "not authorized to access this route"
            }

### DELETE

+ Request

    + Headers

            X-Auth-Token: <Authorization Token>

+ Response 204 

+ Response 401 (application/json)

    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }

+ Response 403 (application/json)

    + Body
    
            {
                "code": "INVALID_PERMISSIONS",
                "detail_code": "",
                "message": "not authorized to access this route"
            }


##  Get/Update Settings [/v2/teams/settings]
A resource representing the settings affecting team functionality for the callers' organization.

### GET

+ Request

    + Headers

            X-Auth-Token: <Authorization Token>

+ Response 200 (application/json)
     
    + Attributes (Settings)
            

+ Response 401 (application/json)

    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }

+ Response 403 (application/json)

    + Body
    
            {
                "code": "INVALID_PERMISSIONS",
                "detail_code": "",
                "message": "not authorized to access this route"
            }

### PATCH

+ Request (application/json)

    + Headers

            X-Auth-Token: <Authorization Token>
    
    + Attributes (Settings)

+ Response 200 (application/json)
     
    + Attributes (Settings)
            

+ Response 401 (application/json)

    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }

+ Response 403 (application/json)

    + Body
    
            {
                "code": "INVALID_PERMISSIONS",
                "detail_code": "",
                "message": "not authorized to access this route"
            }

##  Get/Update Restrictions [/v2/teams/{team_id}/restriction]
A resource representing restriction settings for team.

+ Parameters
  + team_id: `1` (number, required) - team id

### GET

+ Request

    + Headers

            X-Auth-Token: <Authorization Token>

+ Response 200 (application/json)

    + Attributes (TeamRestrictionEnum)


+ Response 401 (application/json)

    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }

+ Response 403 (application/json)

    + Body

            {
                "code": "INVALID_PERMISSIONS",
                "detail_code": "",
                "message": "not authorized to access this route"
            }

### PATCH

+ Request (application/json)

    + Headers

            X-Auth-Token: <Authorization Token>

    + Attributes (TeamRestrictionEnum)

+ Response 200 (application/json)

    + Attributes (TeamRestrictionEnum)


+ Response 401 (application/json)

    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }

+ Response 403 (application/json)

    + Body

            {
                "code": "INVALID_PERMISSIONS",
                "detail_code": "",
                "message": "not authorized to access this route"
            }

# Data Structures

## Get Team(object)
 + `id`: `123` (number, required) - team id 
 + `name`: `DevOps` (string, required) - team name
 + `organization_id`: `1` (number, required) - organization id
 + `users` (array[UserList], optional) - list of team users

## List Teams(object)
 + `teams` (array[ListTeam], required) - list of teams in the requesters organization

## ListTeam(object)
 + `id`: `123` (number, required) - team id 
 + `name`: `DevOps` (string, required) - team name
 + `organization_id`: `1` (number, required) - organization id
 + `leads` (array[LeadsList], required) - list of team leads

## UserList
 + id: `1` (number, required) - user id
 + first_name: `Marty` (string, required) - first name
 + last_name: `McFly` (string, required) - last name
 + job_title: `manager` (string, required) - job title
 + role_id: 2 (enum[number], required) - role ID
   - 1 - Admin
   - 2 - Team Lead
   - 3 - Member
   - 4 - Purchasing

## LeadsList
 + id: `1` (number, required) - user id
 + first_name: `Marty` (string, required) - first name
 + last_name: `McFly` (string, required) - last name

## Upsert Team(object)
 + `name`: `DevOps` (string, required) - team name
 + `users` (array[number], required) - list of team user IDs
   - 1
   - 2    

## Upserted Team(object)
+ `id`: `123` (number, required) - team id 
+ `name`: `DevOps` (string, required) - team name
+ `organization_id`: `1` (number, required) - organization id
+ `users` (array[number], required) - list of team user IDs
  - 1
  - 2

## Settings(object)
+ `can_team_lead_create_team` (boolean, required) - gives a team lead user the ability to create a team 
  Default: false

## TeamRestrictionEnum(object)
+ `restriction`: `restrict-none` (enum[string], required) - enum that represents constant restriction for team
    + Members:
        - `restrict-none` - Show all details (Default mode)
        - `restrict-prices` - Hide resource prices and savings
        - `restrict-details` - Hide all prices,savings, and details

# Group User API V2

## Invite user [/users/invite/{id}]

+ Parameters
  + id: `1` (number, required) - user id

### POST

+ Request (application/json)

    + Headers

            X-Auth-Token: <Authorization Token>

+ Response 200 (application/json)

+ Response 403 (application/json)

    + Body

            {
                "code": "IVALID_PERMISSIONS",
                "detail_code": "",
                "message": "Permission denied"
            }

## Lost password [/users/lost-password]

### POST

+ Request (application/json)

+ Attributes
  - email_address: `user@company.com` (string, required) - user email

+ Response 200 (application/json)

+ Response 400 (application/json)

    + Body

            {
                "code": "EMAIL_ADDRESS_MUST_NOT_BE_EMPTY",
                "detail_code": "",
                "message": "",
            }

## User permissons [/users/permissions]

### GET

+ Request (application/json)

    + Headers

            X-Auth-Token: <Authorization Token>

+ Response 200 (application/json)

    + Attributes(array[Permission])

## Users Add/List [/users]

### Add new user [POST]

+ Request (application/json)

    + Headers

            X-Auth-Token: <Authorization Token>

    + Attributes (POST Python User)

+ Response 201 (application/json)

    + Attributes (GET Python User)

+ Response 403 (application/json)

    + Body

            {
                "code": "IVALID_PERMISSIONSN",
                "detail_code": "",
                "message": "Permission denied"
            }

+ Response 400 (application/json)

    + Body

            {
                "code": "VALIDATION_ERROR",
                "detail_code": "",
                "message": "SSO required for every user except admins",
            }

### List users [GET]

+ Request (application/json)

    + Headers

            X-Auth-Token: <Authorization Token>

+ Response 200 (application/json)

    + Attributes
      - users (array[GET Python User])

+ Response 403 (application/json)

    + Body

            {
                "code": "IVALID_PERMISSIONSN",
                "detail_code": "",
                "message": "Permission denied"
            }

+ Response 400 (application/json)

    + Body

            {
                "code": "VALIDATION_ERROR",
                "detail_code": "",
                "message": "error "
            }


##  Get/Update/Delete [/users/{id}]

+ Parameters
  + id: `1` (number, required) - user id

### Get user detail [GET]

+ Request (application/json)

    + Headers

            X-Auth-Token: <Authorization Token>


+ Response 200 (application/json)

    + Attributes(GET Python User)

+ Response 403 (application/json)

    + Body

            {
                "code": "IVALID_PERMISSIONSN",
                "detail_code": "",
                "message": "Permission denied"
            }

### Update user detail [PUT]

+ Request (application/json)

    + Headers

            X-Auth-Token: <Authorization Token>

    + Attributes(GET Python User)


+ Response 200 (application/json)

    + Attributes(GET Python User)

+ Response 400 (application/json)

    + Body

            {
                "code": "BAD_REQUEST",
                "detail_code": "",
                "message": "Invalid request data"
            }

+ Response 401 (application/json)

    
    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }

+ Response 403 (application/json)

    + Body

            {
                "code": "IVALID_PERMISSIONSN",
                "detail_code": "",
                "message": "Permission denied"
            }

### Delete detail [DELETE]

+ Request (application/json)

    + Headers

            X-Auth-Token: <Authorization Token>

+ Response 204 (application/json)

+ Response 403 (application/json)

    + Body

            {
                "code": "IVALID_PERMISSIONSN",
                "detail_code": "",
                "message": "Permission denied"
            }


## Password [/v2/users/{id}/password]

+ Parameters
    + id: `1` (number, required) - unique user id


### Change own password [PUT]

+ Request (application/json)

    + Headers

            X-Auth-Token: <Authorization Token>

    
    + Attributes
        + old: `old-secret` (string, required) - old password
        + new: `new-secret` (string, required) - new password

+ Response 200 (application/json)

    + Attributes (User)

+ Response 400 (application/json)

    + Body

            {
                "code": "BAD_REQUEST",
                "detail_code": "",
                "message": "Invalid request data"
            }

+ Response 403 (application/json)

    + Body

            {
                "code": "FORBIDDEN",
                "detail_code": "",
                "message": "Insufficient permissions"
            }


### Re-set user's password (for admins) [PATCH]


+ Request (application/json)

    + Headers

            X-Auth-Token: <Authorization Token>

    
    + Attributes
        + new: `new-secret` (string, required) - new password

+ Response 200 (application/json)

    + Attributes (User)

+ Response 400 (application/json)

    + Body

            {
                "code": "BAD_REQUEST",
                "detail_code": "",
                "message": "Invalid request data"
            }

+ Response 403 (application/json)

    + Body

            {
                "code": "FORBIDDEN",
                "detail_code": "",
                "message": "Insufficient permissions"
            }


# Data Structures

## User (object)
 + id: `123` (number, required) - unique user ID
 + name: `Name` (string, required) - user's name

## Python UserPref(object)
+ `user_pref`: `{}` (string, optional) - JSON data defined by console

## POST Python User(object)
 + first_name: `Test` (string, required) - first name
 + last_name: `Jonson` (string, required) - last name
 + email_address: `test@user.com` (string, required) - email
 + job_titile: `manager` (string, required) - job title
 + phone_number: `555 345 123 123` (string, required) - phone number
 + organization_id: 1 (number, required) - organization ID
 + role_id: 2 (enum[number], required) - role ID
   - 1 - Admin
   - 2 - Team Lead
   - 3 - Member
   - 4 - Purchasing
 + timezone: `Europe/Moscow` (string, required) - IANA timezone
 + `team_ids` (array[number], required) - list of user teams
 + `point_of_contact`: 0 (number, required) - whether this user is a point of contact
 + `permission_ids` (array, optional) - list of team lead permissions
   - (enum)
       - 1 (number) - Add/Edit parking schedules
       - 2 (number) - Add/Edit recommendation settings
       - 3 (number) - Edit override limit
 + `api_access`: 0 (number, required) - whether this user has access to API
 + `user_pref` (Python UserPref)

## GET Python User(POST Python User)
 + id: `1` (number, required) - user id
 + first_name: `Test` (string, required) - first name
 + last_name: `Jonson` (string, required) - last name
 + email_address: `test@user.com` (string, required) - email
 + job_titile: `manager` (string, required) - job title
 + phone_number: `555 345 123 123` (string, required) - phone number
 + organization_id: 1 (number, required) - organization ID
 + role_id: 2 (enum[number], required) - role ID
   - 1 - Admin
   - 2 - Team Lead
   - 3 - Member
   - 4 - Purchasing

## Permission(object)
 + name: `Add/Edit parking schedules` (string, required) - name of the permission
 + id: `1` (number, required) - id of the permission

# Group Schedules API

## Schedules Collection [/eng/schedules/]

### Create schedule [POST]

+ Request (application/json)

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8
    
    + Attributes (Schedule POST)

+ Response 201 (application/json)
    + Attributes (Schedule Get)

### List all schedules [GET]

+ Request (application/json)

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 200 (application/json)
    + Attributes (array[Schedule])

## Schedule Resource  [/eng/schedules/{id}]

+ Parameters
  + id: `123` (number) - The unique ID of the scheduled report

### Get Schedule with details [GET]

+ Request (application/json)

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 200 (application/json)
    + Attributes (Schedule Get)

### Update Schedule with details [PUT]

+ Request (application/json)

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8
    
    + Attributes (Schedule POST)

+ Response 201 (application/json)
    + Attributes (Schedule Get)

### Delete Schedule [DELETE]

+ Request (application/json)

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 204

## Schedule Timezone  [/eng/schedules/set-timezone/{id}]

+ Parameters
  + id: `123` (number) - The unique ID of the scheduled

### PUT

+ Request (application/json)

    + Headers 

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8
    
    + Attributes (Timezone)

+ Response 200 (application/json)
    + Attributes (Schedule Get)


# Data Structures

## Schedule
 - name: `always parked` (required, string) - the name of the schedule.
 - description: `some description` (optional, string) - a customer-assigned description of the schedule.
 - time_zone: `Europe/Minsk` (string, required) - time zone to use for the schedule offset from UTC.
 - smartpark: `false` (optional, boolean) - is this schedule generated by smartpark process. Smartparking schedules are created by ParkMyCloud based on utilization data.
 - savings_pct: `67.32` (optional, number) - saving percents calculated on server side. 
 - updated_at: `2020-04-02T12:16:45Z` (optional, string) - last updated time. 
 - assigned: `5` (optional, number) - count of assigned resources. 

## Timezone
 - timezone: `Europe/Minsk` (required, string) - new schedule timezone(this timezone just for representation, this won't change UTC time of schedule)

## Schedule POST(Schedule)
 - times (Times)

## Schedule Get(Schedule POST)
 - id: `1` (required, number) - ID number for the schedule

## Times
 - 0 (array[DayTimeEnd10, DayTimeStart12], optional) - scheduled to work 10-12:00
 - 1 (array[DayTimeEnd10, DayTimeStart12, DayTimeEnd14, DayTimeStart18], optional) - scheduled to work two times 10-12:00, 14-18:00 
 - 2 (array[DayTimeEnd10, DayTimeStart18], optional) - scheduled to work one time 10-18:00
 - 3 (array[DayTimeEnd10], optional)
 - 4 (array[DayTimeEnd14], optional) - scheduled for two days from friday 14:00
 - 5 (array[DayTimeStart18], optional) - to saturday 18:00 
 - 6 (array[DayTimeEnd14, DayTimeStart18], optional) - scheduled to work for 14-18:00

## DayTimeEnd10
 - `end`: `10:00:00` (string, optional) - time of start in 24h format

## DayTimeEnd14
 - `end`: `14:00:00` (string, optional) - time of start in 24h format

## DayTimeStart12
 - `start`: `12:00:00` (string, optional) - time of end in 24h format

## DayTimeStart18
 - `start`: `18:00:00` (string, optional) - time of end in 24h format
# Azure API V2

An API that allow to list the azure management services.

## Azure Subscription Endpoint [/v2/autocred/subscriptions]

### GET

+ Request (application/json)

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8
            X-Azure-Service-Auth-Token: eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIng1dCI6ImtnMkxZczJUMENUaklmajRydDZKSXluZW4zOCIsImtpZCI6ImtnMkxZczJUMENUaklmajRydDZKSXluZW4zOCJ9.eyJhdWQiOiJodHRwczovL21hbmFnZW1lbnQuYXp1cmUuY29tIiwiaXNzIjoiaHR0cHM6Ly9zdHMud2luZG93cy5uZXQvM2UyMGM5YjgtMTczNC00MTQxLTk1YjQtZWZkOWY0YzI0N2RlLyIsImlhdCI6MTYwNDU1OTI0OSwibmJmIjoxNjA0NTU5MjQ5LCJleHAiOjE2MDQ1NjMxNDksImFjciI6IjEiLCJhaW8iOiJBVVFBdS84UkFBQUErSS9BL0c5T2NYQmJVMGN0R3plQUJEWUhNQ2pWQzc5T29Va0F3THpEVWdIbVdCamVaODUyeHZQSm9mVTdlT3VHUzg2SWJUcWw2K0ZlSmtZb0J0WXBkZz09IiwiYWx0c2VjaWQiOiI1OjoxMDAzMjAwMEVGNTU4MDczIiwiYW1yIjpbInB3ZCJdLCJhcHBpZCI6ImRmZmQzMmFhLTcxNWQtNDY2MS05NTE2LTQ1MjUxZWIxNWE2MiIsImFwcGlkYWNyIjoiMCIsImVtYWlsIjoidmlrbmVzaC5tQGdvcGhlcnNsYWIuY29tIiwiZmFtaWx5X25hbWUiOiJNIiwiZ2l2ZW5fbmFtZSI6IlZpa25lc2giLCJpZHAiOiJodHRwczovL3N0cy53aW5kb3dzLm5ldC9kOGFlM2Y5My02NDRlLTQzOWYtOGFhOC03NGIyMDM3MDQ1MzEvIiwiaXBhZGRyIjoiMTU3LjQ2Ljc5LjIyMyIsIm5hbWUiOiJ2aWtuZXNoLm5tIiwib2lkIjoiZmRkZTNmNTYtZjI0MS00ZWYzLWEwYTItYTExMjM3NDE0YTg0IiwicHVpZCI6IjEwMDMyMDAwRUY4MUMwNDYiLCJyaCI6IjAuQUFBQXVNa2dQalFYUVVHVnRPX1o5TUpIM3FveV9kOWRjV0ZHbFJaRkpSNnhXbUpiQUk4LiIsInNjcCI6InVzZXJfaW1wZXJzb25hdGlvbiIsInN1YiI6ImRpZ2c2LWNFM1dhaHBKTUxzd0VoUHc2TDdCRHVIWGhhazFfTl9sQlNGZWsiLCJ0aWQiOiIzZTIwYzliOC0xNzM0LTQxNDEtOTViNC1lZmQ5ZjRjMjQ3ZGUiLCJ1bmlxdWVfbmFtZSI6InZpa25lc2gubUBnb3BoZXJzbGFiLmNvbSIsInV0aSI6ImR5MUloZjZtWUV5MVhlVFRoSndFQVEiLCJ2ZXIiOiIxLjAiLCJ4bXNfdGNkdCI6MTQzNTY5MDAzMH0.vvcJPeNK749pNda_WvxNhrCQt97gztymIXxnipwMzkJQ1FqUykr1PXyadgq5TNxC4cj6t8aqrKoYaXCbCu19SDTBR33KVofPLugAf71Rjy4FA55NPywRJaYf0NLc86SgD6UAz5gW4clwgSCOPTLvyitQWq4H6qFZLdmKK07yI0oFlhWyw1OvaMAlLSRpy_nAdqT_23NhxRIvAjbqmnXrn4wq1JUk6JNN6gT9KIKe3imDEWlU18JN9CiVXdviUphAZNMnqaLE4h8LoMosjBTH8xwp5zblwuQRulJY-8oF0-7pY9HCqRpX4sIdQ8EvFeLZ675CYqXW8PLMN1YqLDfs7g

+ Response 200 (application/json)
    + Body

            {
                "data": [
                    {
                        "id": "<subscription_id>",
                        "name": "Azure subscription 1",
                        "enabled": false,
                        "state": "Enabled",
                        "team": 1,
                        "provider": "azure",
                        "exists": true
                    },
                    {
                        "id": "<subscription_id>",
                        "name": "Azure subscription 2",
                        "enabled": false,
                        "state": "Enabled",
                        "team": 2,
                        "provider": "azure",
                        "exists": false
                    }
                ]
            }

+ Response 401 (application/json)


    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }

+ Response 400 (application/json) 

    + Body

            {
                "code": "INVALID_REQUEST",
                "detail_code": "",
                "message": "The access token expiry UTC time '11/5/2020 1:45:56 PM' is earlier than current UTC time '11/5/2020 1:53:14 PM'."
            }

## Azure Automated Target(Credential) Validation Endpoint [/v2/autocred]

### POST

+ Request (application/json)

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8
            
            X-Azure-Service-Auth-Token: eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIng1dCI6ImtnMkxZczJUMENUaklmajRydDZKSXluZW4zOCIsImtpZCI6ImtnMkxZczJUMENUaklmajRydDZKSXluZW4zOCJ9.eyJhdWQiOiJodHRwczovL21hbmFnZW1lbnQuYXp1cmUuY29tIiwiaXNzIjoiaHR0cHM6Ly9zdHMud2luZG93cy5uZXQvM2UyMGM5YjgtMTczNC00MTQxLTk1YjQtZWZkOWY0YzI0N2RlLyIsImlhdCI6MTYwNDU1OTI0OSwibmJmIjoxNjA0NTU5MjQ5LCJleHAiOjE2MDQ1NjMxNDksImFjciI6IjEiLCJhaW8iOiJBVVFBdS84UkFBQUErSS9BL0c5T2NYQmJVMGN0R3plQUJEWUhNQ2pWQzc5T29Va0F3THpEVWdIbVdCamVaODUyeHZQSm9mVTdlT3VHUzg2SWJUcWw2K0ZlSmtZb0J0WXBkZz09IiwiYWx0c2VjaWQiOiI1OjoxMDAzMjAwMEVGNTU4MDczIiwiYW1yIjpbInB3ZCJdLCJhcHBpZCI6ImRmZmQzMmFhLTcxNWQtNDY2MS05NTE2LTQ1MjUxZWIxNWE2MiIsImFwcGlkYWNyIjoiMCIsImVtYWlsIjoidmlrbmVzaC5tQGdvcGhlcnNsYWIuY29tIiwiZmFtaWx5X25hbWUiOiJNIiwiZ2l2ZW5fbmFtZSI6IlZpa25lc2giLCJpZHAiOiJodHRwczovL3N0cy53aW5kb3dzLm5ldC9kOGFlM2Y5My02NDRlLTQzOWYtOGFhOC03NGIyMDM3MDQ1MzEvIiwiaXBhZGRyIjoiMTU3LjQ2Ljc5LjIyMyIsIm5hbWUiOiJ2aWtuZXNoLm5tIiwib2lkIjoiZmRkZTNmNTYtZjI0MS00ZWYzLWEwYTItYTExMjM3NDE0YTg0IiwicHVpZCI6IjEwMDMyMDAwRUY4MUMwNDYiLCJyaCI6IjAuQUFBQXVNa2dQalFYUVVHVnRPX1o5TUpIM3FveV9kOWRjV0ZHbFJaRkpSNnhXbUpiQUk4LiIsInNjcCI6InVzZXJfaW1wZXJzb25hdGlvbiIsInN1YiI6ImRpZ2c2LWNFM1dhaHBKTUxzd0VoUHc2TDdCRHVIWGhhazFfTl9sQlNGZWsiLCJ0aWQiOiIzZTIwYzliOC0xNzM0LTQxNDEtOTViNC1lZmQ5ZjRjMjQ3ZGUiLCJ1bmlxdWVfbmFtZSI6InZpa25lc2gubUBnb3BoZXJzbGFiLmNvbSIsInV0aSI6ImR5MUloZjZtWUV5MVhlVFRoSndFQVEiLCJ2ZXIiOiIxLjAiLCJ4bXNfdGNkdCI6MTQzNTY5MDAzMH0.vvcJPeNK749pNda_WvxNhrCQt97gztymIXxnipwMzkJQ1FqUykr1PXyadgq5TNxC4cj6t8aqrKoYaXCbCu19SDTBR33KVofPLugAf71Rjy4FA55NPywRJaYf0NLc86SgD6UAz5gW4clwgSCOPTLvyitQWq4H6qFZLdmKK07yI0oFlhWyw1OvaMAlLSRpy_nAdqT_23NhxRIvAjbqmnXrn4wq1JUk6JNN6gT9KIKe3imDEWlU18JN9CiVXdviUphAZNMnqaLE4h8LoMosjBTH8xwp5zblwuQRulJY-8oF0-7pY9HCqRpX4sIdQ8EvFeLZ675CYqXW8PLMN1YqLDfs7g
            
            X-Azure-Graph-Auth-Token: eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIng1dCI6ImtnMkxZczJUMENUaklmajRydDZKSXluZW4zOCIsImtpZCI6ImtnMkxZczJUMENUaklmajRydDZKSXluZW4zOCJ9.eyJhdWQiOiJodHRwczovL21hbmFnZW1lbnQuYXp1cmUuY29tIiwiaXNzIjoiaHR0cHM6Ly9zdHMud2luZG93cy5uZXQvM2UyMGM5YjgtMTczNC00MTQxLTk1YjQtZWZkOWY0YzI0N2RlLyIsImlhdCI6MTYwNDU1OTI0OSwibmJmIjoxNjA0NTU5MjQ5LCJleHAiOjE2MDQ1NjMxNDksImFjciI6IjEiLCJhaW8iOiJBVVFBdS84UkFBQUErSS9BL0c5T2NYQmJVMGN0R3plQUJEWUhNQ2pWQzc5T29Va0F3THpEVWdIbVdCamVaODUyeHZQSm9mVTdlT3VHUzg2SWJUcWw2K0ZlSmtZb0J0WXBkZz09IiwiYWx0c2VjaWQiOiI1OjoxMDAzMjAwMEVGNTU4MDczIiwiYW1yIjpbInB3ZCJdLCJhcHBpZCI6ImRmZmQzMmFhLTcxNWQtNDY2MS05NTE2LTQ1MjUxZWIxNWE2MiIsImFwcGlkYWNyIjoiMCIsImVtYWlsIjoidmlrbmVzaC5tQGdvcGhlcnNsYWIuY29tIiwiZmFtaWx5X25hbWUiOiJNIiwiZ2l2ZW5fbmFtZSI6IlZpa25lc2giLCJpZHAiOiJodHRwczovL3N0cy53aW5kb3dzLm5ldC9kOGFlM2Y5My02NDRlLTQzOWYtOGFhOC03NGIyMDM3MDQ1MzEvIiwiaXBhZGRyIjoiMTU3LjQ2Ljc5LjIyMyIsIm5hbWUiOiJ2aWtuZXNoLm5tIiwib2lkIjoiZmRkZTNmNTYtZjI0MS00ZWYzLWEwYTItYTExMjM3NDE0YTg0IiwicHVpZCI6IjEwMDMyMDAwRUY4MUMwNDYiLCJyaCI6IjAuQUFBQXVNa2dQalFYUVVHVnRPX1o5TUpIM3FveV9kOWRjV0ZHbFJaRkpSNnhXbUpiQUk4LiIsInNjcCI6InVzZXJfaW1wZXJzb25hdGlvbiIsInN1YiI6ImRpZ2c2LWNFM1dhaHBKTUxzd0VoUHc2TDdCRHVIWGhhazFfTl9sQlNGZWsiLCJ0aWQiOiIzZTIwYzliOC0xNzM0LTQxNDEtOTViNC1lZmQ5ZjRjMjQ3ZGUiLCJ1bmlxdWVfbmFtZSI6InZpa25lc2gubUBnb3BoZXJzbGFiLmNvbSIsInV0aSI6ImR5MUloZjZtWUV5MVhlVFRoSndFQVEiLCJ2ZXIiOiIxLjAiLCJ4bXNfdGNkdCI6MTQzNTY5MDAzMH0.vvcJPeNK749pNda_WvxNhrCQt97gztymIXxnipwMzkJQ1FqUykr1PXyadgq5TNxC4cj6t8aqrKoYaXCbCu19SDTBR33KVofPLugAf71Rjy4FA55NPywRJaYf0NLc86SgD6UAz5gW4clwgSCOPTLvyitQWq4H6qFZLdmKK07yI0oFlhWyw1OvaMAlLSRpy_nAdqT_23NhxRIvAjbqmnXrn4wq1JUk6JNN6gT9KIKe3imDEWlU18JN9CiVXdviUphAZNMnqaLE4h8LoMosjBTH8xwp5zblwuQRulJY-8oF0-7pY9HCqRpX4sIdQ8EvFeLZ675CYqXW8PLMN1YqLDfs7g


    + Body

            [
                {
                    "team_id": 1,
                    "subscription_id": "subscription-1",
                    "name": "subscription-name"
                } 
            ]

    


+ Response 200 (application/json)

    + Body

            {
                "data": <auto_cred_id>
            }


+ Response 401 (application/json)


    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }

+ Response 400 (application/json) 

    + Body

            {
                "code": "INVALID_REQUEST",
                "detail_code": "",
                "message": "Invalid Azure Microsoft Graph token"
            }


## Azure Automated Target(Credential) Validated Endpoint [/v2/autocred/:id]


### GET

+ Request (application/json)

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8
            
+ Response 200 (application/json)
    + Body

        + Partial-Pass

                {
                    "data": [
                        {
                            "name": "",
                            "provider": "azure",
                            "account_number": "<subscription_id>",
                            "team_id": 1,
                            "state": "partial_pass",
                            "cred_id": 1,
                            "validation_error": {
                                "AZURE_VALIDATE_MANAGED_INSTANCES": "subscription <subscription_id> does not have Microsoft.Sql/managedInstances/*/read permission in its security policy",
                                "AZURE_VALIDATE_MANAGED_INSTANCES_WRITE": "subscription <subscription_id> does not have Microsoft.Sql/managedInstances/write permission in its security policy",
                                "AZURE_VALIDATE_MONITORING": "insufficient permissions for reading metrics",
                                "AZURE_VALIDATE_NODEGROUPS": "subscription <subscription_id> does not have Microsoft.ContainerService/managedClusters/agentPools/read permission in its security policy",
                                "AZURE_VALIDATE_SQL_POOL_WRITE": "subscription <subscription_id> does not have Microsoft.Sql/servers/elasticPools/write permission in its security policy"
                            },
                            "created_at": "2021-03-18T19:25:39Z",
                            "updated_at": "2021-03-18T19:25:57Z"
                        }
                    ]
                }

        + Pass

                {
                    "data": [
                        {
                            "name": "",
                            "provider": "azure",
                            "account_number": "<subscription_id>",
                            "team_id": 1,
                            "state": "pass",
                            "validation_error": null,
                            "cred_id": 1,
                            "created_at": "2021-03-18T19:25:39Z",
                            "updated_at": "2021-03-18T19:25:57Z"
                        }
                    ]
                }
    
        + Fail

                {
                    "data": [
                        {
                            "name": "",
                            "provider": "azure",
                            "account_number": "<subscription_id>",
                            "team_id": 1,
                            "state": "fail",
                            "validation_error": {
                                "AZURE_VALIDATE_MANAGED_INSTANCES": "subscription <subscription_id> does not have Microsoft.Sql/managedInstances/*/read permission in its security policy",
                                "AZURE_VALIDATE_MANAGED_INSTANCES_WRITE": "subscription <subscription_id> does not have Microsoft.Sql/managedInstances/write permission in its security policy",
                                "AZURE_VALIDATE_MONITORING": "insufficient permissions for reading metrics",
                                "AZURE_VALIDATE_NODEGROUPS": "subscription <subscription_id> does not have Microsoft.ContainerService/managedClusters/agentPools/read permission in its security policy",
                                "AZURE_VALIDATE_SQL_POOL_WRITE": "subscription <subscription_id> does not have Microsoft.Sql/servers/elasticPools/write permission in its security policy"
                            },
                            "created_at": "2021-03-18T19:25:39Z",
                            "updated_at": "2021-03-18T19:25:57Z"
                        }
                    ]
                }

+ Response 401 (application/json)


    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }

+ Response 404 (application/json)


    + Body

            {
                "code": "NOT_FOUND",
                "detail_code": "",
                "message": "id not found"
            }


+ Response 400 (application/json) 

    + Body

            {
                "code": "INVALID_REQUEST",
                "detail_code": "",
                "message": "The access token expiry UTC time '11/5/2020 1:45:56 PM' is earlier than current UTC time '11/5/2020 1:53:14 PM'."
            }



## Azure Automated Target(Credential) List Endpoint [/v2/autocred]


### GET

+ Request (application/json)

    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8
            
+ Response 200 (application/json)
    + Body

            {
                "data": [
                    {
                        "id": 1,
                        "state": "processing",
                        "name": "ParkMyCloud-Automated-Target-3e20c9b8-1734-4141-95b4-efd9f4c247de"
                    },
                    {
                        "id": 2,
                        "state": "processed",
                        "name": "ParkMyCloud-Automated-Target-3e20c9b8-1734-4141-95b4-efd9f4c247de"
                    }
                ]
            }

+ Response 401 (application/json)


    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }

+ Response 404 (application/json)


    + Body

            {
                "code": "NOT_FOUND",
                "detail_code": "",
                "message": "id not found"
            }


+ Response 400 (application/json) 

    + Body

            {
                "code": "INVALID_REQUEST",
                "detail_code": "",
                "message": "The access token expiry UTC time '11/5/2020 1:45:56 PM' is earlier than current UTC time '11/5/2020 1:53:14 PM'."
            }

# Legacy Reports

# Group Reports API

An API that provides operations for fetching ParkMyCloud reports.

## Authentication

All requests to this API must be authenticated using an authorization token. The
authorization token must be provided using the `X-Auth-Token` request header.
For example:

```http
X-Auth-Token: cd57fa5140a0c7bf0e6f3bed9b109771
```

For details on how to obtain an authorization token, see the documentation for
the `/auth` API.

## List Report groups [GET /report/report-types]

List all report groups types with configs of visibility, etc.

+ Request

    + Headers

            X-Auth-Token: <Authorization Token>

+ Response 200 (application/json)

    + Attributes (List ReportTypesGroups)


+ Response 401 (application/json)

    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }

+ Response 403 (application/json)

    + Body

            {
                "code": "INVALID_PERMISSIONS",
                "detail_code": "",
                "message": "not authorized to access this route"
            }

## List Report ranges [GET /report/report-ranges]

Provides possible ranges for reports

+ Request

    + Headers

            X-Auth-Token: <Authorization Token>

+ Response 200 (application/json)

    + Attributes (List RangeCodes)


+ Response 401 (application/json)

    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }

+ Response 403 (application/json)

    + Body

            {
                "code": "INVALID_PERMISSIONS",
                "detail_code": "",
                "message": "not authorized to access this route"
            }

## Fetch report [GET /report/fetch{?format}{?range_code}{?report_type}{?team_id}{?cred_id}]

Provide report based on inputted params

+ Parameters

    + format: `json` (enum[string], required) - format of reports
        + Members
            + `json`
            + `json_chart`
            + `csv`
            + `excel`

    + range_code (enum[string], required) - range code for report
        + Members
            + `month_to_date`
            + `quarter_to_date`
            + `year_to_date`
            + `last_month`
            + `last_quarter`
            + `last_year`
            + `trailing_30_days`
            + `trailing_6_months`
            + `trailing_12_months`
            + `trailing_24_months`

    + report_type (enum[ReportCode], required) - report type
        + Members
            + `daily_savings`
            + `costs_savings_summary_by_team`
            + `costs_savings_summary_by_cred`
            + `costs_savings_by_team`
            + `costs_savings_by_account`
            + `costs_savings_by_provider`
            + `daily_costs_by_credential`
            + `daily_savings_by_credential`
            + `all_org_recommendations_by_cred`
            + `all_org_recommendations_by_team`
            + `daily_costs_by_provider`
            + `daily_savings_by_provider`
            + `top_costs_by_credential`
            + `top_savings_by_credential`
            + `monthly_savings`
            + `costs_by_provider_by_team`
            + `savings_by_provider_by_team`
            + `top_costs_by_resource`
            + `top_savings_by_resource`
            + `resource_counts_by_provider_by_location`
            + `percent_up_down_by_team`
            + `daily_resource_hours`
            + `monthly_resource_hours`
            + `monthly_resource_status`
            + `cost_by_resource`
            + `cost_by_team`
            + `cost_by_credential`
            + `org_team_roster`

    + team_id: `1` (string, optional) - `team.id` filter
        - Can be:
            + `'1'` - for special id
            + `'1,2,3'` - for multiple ids
            + `'*'` - for all ids

    + cred_id: `1` (string, optional) - `cred.id` filter
        - Can be:
            + `'1'` - for special id
            + `'1,2,3'` - for multiple ids
            + `'*'` - for all ids

+ Request

    + Headers

            X-Auth-Token: <Authorization Token>

+ Response 200 (application/json)

    + Attributes (Report)


+ Response 401 (application/json)

    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }

+ Response 403 (application/json)

    + Body

            {
                "code": "INVALID_PERMISSIONS",
                "detail_code": "",
                "message": "not authorized to access this route"
            }

# Usage reports [/report/download]

Section desctribes creating and fetching usage reports

## Request usage report [POST]

+ Request

    + Attributes (UsageReportForm)

    + Headers

            X-Auth-Token: <Authorization Token>

+ Response 200 (application/json)

    + Attributes (UsageReport)


+ Response 401 (application/json)

    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }

+ Response 403 (application/json)

    + Body

            {
                "code": "INVALID_PERMISSIONS",
                "detail_code": "",
                "message": "not authorized to access this route"
            }


## Download usage report [GET /report/download/{report_id}]

+ Parameters
    + `report_id`: `FmeVXoSTa3tNoaeWvEBTnQ` (string) - id of report

+ Response 200 (application/vnd.ms-excel)

    ```
    Binary contnet of xls file
    ```

+ Response 401 (application/json)

    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }

+ Response 403 (application/json)

    + Body

            {
                "code": "INVALID_PERMISSIONS",
                "detail_code": "",
                "message": "not authorized to access this route"
            }


# Data Structures

## List ReportTypesGroups(object)
 + `groups` (array[ReportTypesGroup], required) - list of report type

## ReportTypesGroup(object)
 + `items` (array[ReportTypes], required) - list of reports in group
 + `visual`: `true` (boolean, required) - visibility of the group
 + `name`: `Resource` (string, required) - name of the reports group

## ReportTypes(object)
 + `code`: `daily_savings` (ReportCode, required) - code of report
 + `name`: `Daily Savings` (string, required) - report's name
 + `team_filter`: `true` (boolean, required) - mark that report provides teams filter
 + `cred_filter`: `true` (boolean, required) - mark that report provides creds filter
 + `bottom_text`: `some caveat or message` (string, required) - description text for the reports

## ReportCode(string)

## List RangeCodes(object)
 + `range_codes` (array[RangeCodes], required)

## RangeCodes(object)
 + `code`: `month_to_date` (string, required) - code of range
 + `name`: `Month-to-Date` (string, required) - name of range

## Report(object)
 + `series` (array[Series], optional) - series of data
 + `limited_for_chart`: `false` (boolean, optional) - 'json_chart' format may limit the number of rows returned, and if so will return as `true`
 + `columns` (array[Column], optional) - column of chart
 + `empty`: `false` (boolean, required) - if no data `true` will be returned

## Series(object)
 + `column`: `aws` (string) - name of column
 + `values` (array[enum[]]) - array of different type

## Column(object)
 + `name`: `aws` (string, required) - name of column
 + `label`: `aws` (string) - label of column for chart
 + `sub_columns` (array[Column], optional) - optional sub columns

## UsageReportForm(object)
 + `start`: `2019-09-30T21:00:00.000Z` (string, required) - start time-date for report
 + `end`: `2019-10-18T20:59:59.999Z` (string, required) - end time-date for report
 + `report_type`: `cost_by_resource` (enum[string], required) - type of report
    + Members
        + `cost_by_team`
        + `cost_by_credential`
 + team_id: `1` (string, optional) - `team.id` filter
 + cred_id: `1,2,3` (string, optional) - `cred.id` filter

## UsageReport(object)
 + `report_id`: `FmeVXoSTa3tNoaeWvEBTnQ` (string, required) - report id used for download


# Group Audit Log API

An API that provides operations for fetching ParkMyCloud users actions.
Additional information can be found in https://parkmycloud.atlassian.net/wiki/spaces/PMCUG/pages/22446383/User+Audit+Log

## Authentication

All requests to this API must be authenticated using an authorization token. The
authorization token must be provided using the `X-Auth-Token` request header.
For example:

```http
X-Auth-Token: cd57fa5140a0c7bf0e6f3bed9b109771
```

For details on how to obtain an authorization token, see the documentation for
the `/auth` API.

## List Users actions [GET /eng/user-actions{?start}{?end}{?dir}{?dir_id}{?per_page}{?search}]

List audit log based on input params.

+ Parameters
    + start: `20191003` (string, required) - begin date of report in YYYYMMDD format
    + end: `20191103` (string, required) - end date of report in YYYYMMDD format
    + dir: `next` (enum[string], required) - the direction we are paging
        + Members
            - `next`
            - `prev`
            - `first`
            - `last`
    + dir_id: `next` (enum[string], required) - the first or last ID in the direction we are paging
        + Members
            - `next`
            - `prev`
    + per_page: `15` (number, required) - the number of results to return per page
    + search: `resource.stop` (string, optional) - search for fields in `username`, `user_desc`, `code`, or `message`

+ Request

    + Headers

            X-Auth-Token: <Authorization Token>

+ Response 200 (application/json)

    + Attributes (List UserAction)

+ Response 401 (application/json)

    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }

+ Response 403 (application/json)

    + Body

            {
                "code": "INVALID_PERMISSIONS",
                "detail_code": "",
                "message": "not authorized to access this route"
            }

## Download Audit Log [GET /eng/user-actions/download{?start}{?end}]

Download audit log as csv file in date range.

+ Parameters
    + start: `20191003` (string, required) - begin date of report in YYYYMMDD format
    + end: `20191103` (string, required) - end date of report in YYYYMMDD format

+ Request

    + Headers

            X-Auth-Token: <Authorization Token>

+ Response 200 (text/csv)

    + Body
        ```
        Time (UTC),AppCode,Username,User Description,Code,Message
        2019-11-14 17:55:31,0,some@email.com,John Smith,team.update,ID: 3 | Name: B | OrgID: 1 | UserIDs: []
        2019-11-14 17:55:32,0,some@email.com,John Smith,rightsizing.enabled,rightsizing enabled for team B
        2019-11-14 17:55:49,0,some@email.com,John Smith,team.update,ID: 3 | Name: B | OrgID: 1 | UserIDs: []
        ```


+ Response 401 (application/json)

    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }

+ Response 403 (application/json)

    + Body

            {
                "code": "INVALID_PERMISSIONS",
                "detail_code": "",
                "message": "not authorized to access this route"
            }

# Data Structures

## List UserAction(object)
 + `first_id`: `123` (number, required) - unique id of first items element
 + `last_id`: `138` (number, required) - unique id of last items element
 + `has_next`: `false` (boolean, required) - true if has next pages
 + `has_prev`: `true` (boolean, required) - true if has previous pages
 + `items` (array[UserAction], required) - list of report type

## UserAction(object)
 + `ts`: `2016-11-27T22:51:56Z` (string, required) - list of report type
 + `app_code`: `0` (number, required) - code of application
 + `username`: `some@email.com` (string, required) - email of user
 + `user_desc`: `John Smith` (string, required) - first and last name of user
 + `code`: `lg.create` (enum[string], required) - system code of user action
  + Members
   - `lg.create` - Created a Logical Group
   - `lg.rename` - Renamed the Logical Group
   - `lg.update` - Updated the Logical Group
   - `lg.delete` - Deleted the Logical Group
   - `organization.create` - Created account
   - `organization.changed` - Organization name has been changed
   - `cred.create` - Created credential
   - `cred.delete` - Deleted credential
   - `cred.update` - Updated credential
   - `idash.login` - Login for organization
   - `user.create` - Created user
   - `user.invite` - Invited user
   - `user.update` - Updated user
   - `team.create` - Created team with team info
   - `team.update` - Updated team with team info
   - `team.settings` - Allow Team Leads to create Teams <enabled/disabled>
   - `team.restriction` - Restriction changed for team with data
   - `resource.toggle` - Resource toggled by user
   - `resource.start` - Resource started
   - `resource.stop` - Resource stopped
   - `resource.move.team` - Resource moved to team with data
   - `asg.update` - Updated ASG with data
   - `user.apikey.create` - Created apikey for user
   - `user.apikey.regenerated` - Regenerated apikey for user
   - `user.apikey.delete` - Deleted apikey for user
   - `apikey.login.failed` - Failed login with APIKEY
   - `apikey.login` - Login with APIKEY
   - `schedule.create` - Created schedule
   - `schedule.delete` - Deleted schedule
   - `schedule.update` - Updated schedule
   - `schedule.detach` - Detached schedule from resource
   - `schedule.attach` - Attached schedule from resource
   - `schedule.override` - Override schedule from resource is set
   - `schedule.override_cancel` - Override schedule from resource canceled
   - `policy.create` - Policy created
   - `policy.delete` - Policy deleted
   - `policy.update` - Policy updated
   - `policy.reorder` - Reordered policies for org
   - `policy.action.assign_team_id` - Team assign for resources is set
   - `policy.action.assign_schedule_id` - Schedule assign for resources is set
   - `policy.action.detach_schedule` - Schedule detach for resources is set
   - `policy.action.set_restriction` - Restriction for resources is set
   - `policy.action.set_application_mode` - Application mode for resources is set
   - `policy.action.apply_for_credential` - Policies have been applied for Credential
   - `policy.action.set_asg_parking_method` - ASG parking method for resource is set
   - `policy.action.accept_spr` - Accepted smart-park recommendation for resource
   - `sso.create` - Created SSO
   - `sso.update` - Updated SSO
   - `sso.delete` - Deleted SSO
   - `feature.selections.change` - Changed organization feature selections
   - `notifications.output.create` - Created notification output
   - `notifications.output.update` - Updated notification output
   - `notifications.output.delete` - Deleted notification output
   - `recommendation.update` - Added recommendation keywords
   - `recommendation.ignore` - Ignored recommendations
   - `licensing.changed` - Licensing setting changed to organization
   - `rightsizing.add` - Rightsizing task for the resource (with params) added
   - `rightsizing.run` - Rightsizing task for the resource (with params) started
   - `rightsizing.cancel` - Rightsizing task for the resource (with params) canceled
   - `rightsizing.accept` - Rightsizing recommendation for the resource (with params) accepted
   - `rightsizing.ignore` - Rightsizing recommendation for the resource (with params) ignored
   - `rightsizing.reset` - Rightsizing settings for team reset to default
   - `rightsizing.changed` - Timerange setting changed for team
   - `rightsizing.enabled` - Rightsizing enabled for team
   - `rightsizing.disabled` - Rightsizing disabled for team
   - `resource_cost.reset` - Resource (data) cost reset
   - `resource_cost.changed` - Resource (data) cost changed
   - `restriction.changed` - Resource (data) restriction changed
   - `systemlog.rightsizing.task` - Rightsizing task has new status for the resource (data)
   - `override.restriction.changed` - Schedule override restriction changed for team (data)
   - `override.restriction.disabled` - Disabled schedule override for team
   - `override.restriction.enabled` - Schedule override restriction set for team with data
   - `override.restriction.deleted` - Schedule override restriction removed for team
 + `message`: `Some message description` (string, required) - detailed description of user action
 + `is_idash_user`: `false` (boolean, required) - represents user's type console(false) or idash(true)
# Group Notifications API

## Organization Notifications [/eng/notifications/org-outputs]

Organization notifications provide API CRUD for notifications objects that allows to send notification based on system events filtered by team.
across multiple channels like `slack`, `hangouts`, `microsoft teams`, `webhooks`, `email`.

### List all notifications [GET]

+ Request (application/json)
    
    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 200 (application/json)
    + Attributes (Notification List)

+ Response 401 (application/json)

    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }

### Create new notification [POST]

+ Request (application/json)
    
    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 201 (application/json)
    + Attributes (Notification update)
    
    + Body
            {
                "id": 1
            }

+ Response 401 (application/json)

    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }


### Update notification [PUT /eng/notifications/org-outputs/{notification_id}]

+ Parameters
  + notification_id (number, required) - notification's id

+ Request (application/json)
    
    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 200 (application/json)
    + Attributes (Notification update)
    
    + Body
            {
            }

+ Response 401 (application/json)

    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }

### Delete notification [DELETE /eng/notifications/org-outputs/{notification_id}]

+ Parameters
  + notification_id (number, required) - notification's id

+ Request (application/json)
    
    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 204 (application/json)
   
    + Body
            {}

+ Response 401 (application/json)

    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }

## User's Notification [/eng/notifications/user-output]

User's notification provide API that allows to send notification based on system events filtered by teams, only by `email` channel.


### Get User notification [GET]

+ Request (application/json)
    
    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 200 (application/json)

    + Attributes (User notification)

+ Response 401 (application/json)

    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }

### Update User notification [PUT]

+ Request (application/json)
    
    + Headers

            X-Auth-Token: 7ca57767ae16bb878f62946b0a8bb0385c9607d8

+ Response 200 (application/json)
    + Attributes (User notification update)
    
    + Body
        
            {}

+ Response 401 (application/json)

    + Body

            {
                "code": "NOT_AUTHENTICATED",
                "detail_code": "",
                "message": "Unauthorized"
            }


# Data Structures

## Notification List(object)
+ `outputs`: array(Notification) - array of Notifications

## Notification(Notification update)
+ `id`: `1` (number, required) - notification's unique key

## Notification update(User notification)
+ `value`: `https://hooks.slack.com/services/acbABC1` (string, required) - notification data, type depends on notification `protocol`
+ `protocol`: `email` (enum[string], required) - notification's protocol channel
    + Members:
        + `slack` - slack channel
        + `hangouts` - hangouts channel
        + `msteams` - microsoft teams channel
        + `email` - user's email
        + `org-email` - using 
        + `webhook` - webhook channel 
+ `disable_tls_check`: `false` (boolean, required) - affects only `webhook` protocol
+ `metadata`: (Notification Metadata, optional) - affects only `webhook` protocol

## User notification(User notification update)
+ `name`: `Notification 1` (string, required) - notification's name

## User notification update(object)
+ `enabled`: `true` (boolean, required) - is notification enabled
+ `event_codes`: (array[number], required) - means type of events that will be sent to channel
    - `1` - System Errors. Parking, discovery errors
    - `2` - Parking Actions. Scheduled resource start/stop
    - `3` - User Actions. Toggle, schedule attach/detach, snooze and snooze cancel; schedule update; credential update.
    - `4` - Policy Actions. Automatic schedule attachment by a policy rule.
    - `5` - System Maintenance and Updates.
    - `6` - Resource Shutdown Warning
    - `7` - Credential Errors
+ `team_ids`: (array[number], required) - means list of team ids whose notifications are sent to this channel, empty means "all teams"
    - 1
    - 2
+ `specific_teams`: `true` (boolean, required) - true if `team_ids` is set or all assigned teams are deleted
+ `shutdown_warning_time`: 900 (number, optional) - optional arguments that holds `Resource Shutdown Warning` time in seconds

## Notification Metadata
+ `custom_headers`: (object, optional) - custom webhook headers key-value pair, max 5 headers accepted
  - `header_key`:`value`
