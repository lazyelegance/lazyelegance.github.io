---
title: JWT Creation and Verification
category: iam
date: 2024-10-19
layout: post
---

JWTs can be used in various ways:

- **Authentication**: When a user successfully logs in using their credentials, an [ID token](https://auth0.com/docs/security/tokens/id-tokens) is returned. According to the [OpenID Connect (OIDC) specs](https://openid.net/specs/openid-connect-core-1_0.html#IDToken), an ID token is always a JWT.

- **Authorization**: Once a user is successfully logged in, an application may request to access routes, services, or resources (e.g., APIs) on behalf of that user. To do so, in every request, it must pass an Access Token, which may be in the form of a JWT. Single Sign-on (SSO) widely uses JWT because of the small overhead of the format, and its ability to easily be used across different domains.

- **Information Exchange**: JWTs are a good way of securely transmitting information between parties because they can be signed, which means you can be sure that the senders are who they say they are. Additionally, the structure of a JWT allows you to verify that the content hasn't been tampered with.

[Producing and Consuming JWSs](https://datatracker.ietf.org/doc/html/rfc7515#section-5){: target="_blank"}

## Structure

JWT tokens consist of three parts:

- Header: Contains the token type (typ) and hash algorithm (alg), such as HMAC SHA256 or RSA. [ℹ]({% link _notes/hmac-vs-rsa.md %})
- Payload: Includes seven predefined claims (not mandatory but recommended), public claims, and private claims.
- Signature: Created using the encoded header, encoded payload, and a secret.

![JWT Structure]({{site.baseurl}}/assets/images/jwt-structure.png){:.ioda}

## JWT Creation

![JWT Creation]({{site.baseurl}}/assets/images/jwt-creation.png){:.ioda}

## JWT Verification

![JWT Verification]({{site.baseurl}}/assets/images/jwt-verification.png){:.ioda}
