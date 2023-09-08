# Naming and Spacing Standards

## Database

### Database table names should not be plural

    * Good
        * user
        * user_data
    * Bad
        * users
        * users_data

### Column names should be snake case

    * Good
        * first_name
        * access_token
    * Bad
        * FirstName
        * accessToken

### Primary keys should not be named id

    * Good
        * user_id
    * Bad
        * id

## JavaScript / TypeScript

### Variable names should be camel case unless it is a constant

    * Good
        * accessToken
        * userId
    * Bad
        * UserID
        * user_id

### Constants should be upper case snake case

    * Good
        * USER_ROLES
        * AZURE_AUTH_TOKEN
    * Bad
        * user_roles
        * userRoles
        * azureAuthToken

### Indenting

    * 2 spaces (no tabs)

## Python

### Variable names should be lower case snake case

    * Good
        * user_id
        * token_serializer
    * Bad
        * userId
        * User

### Indenting

    * 4 spaces (no tabs)
