---
title: AWS Cognito
layout: default
---
# AWS COGNITO
- AWS Service that offers Authentication and Authorization features.
- User registration, sign in and access control
- protocols OAuth,OIDC, SAML
- Keep directory of users, MFA
- Securing APIs
- Provide Temp access to AWS resource

## Core Concepts
| User Pools | Identity Pools |
| :---------- | :-------------- |
| use cognito or social as identity provider | Short term access ,get credential as IAM |
| User directories | dynamic select IAM using token attributes |
| Oauth 2.0 flow/auth flow|

**User Pool Hosted UI**<br>
user sign in => redirect to cognito UI => Sign up => add to user pool => redirect back to web app

##  Triggers
Allow to run code in response to cognito event

## Additional Topics
**SINGLE SIGN ON SSO**
1. OAUTH 2.0
2. federated identity -> SAML and OIDC
3. SAML workflow  
> <img src="./assests/Screenshot 2025-04-10 120451.png" width="500" height="500">

## Attaching Google with cognito
1. Create a new project in developer console
2. Create an Oauth consent page
3. Create an oauth client
    - under jS origin > user pool domain
    - redirect url > userpool domain+/oauth2/idpresponse
4. Back to aws console
5. authentication > social and external providers
    - add google 
    - paste client id and client password
    - map attributes as required
    - map openid email profile
    - save changes
6. In login page > edit and add google as idp
7. login page is ready
