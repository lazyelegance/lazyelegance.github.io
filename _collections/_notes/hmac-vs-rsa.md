---
title: HMAC vs RSA
category: iam
date: 2024-10-19
layout: post
---


A *signing* algorithm that, given a message and a private key, produces a signature.

A *signature verifying* algorithm that, given the message, public key and signature, either accepts or rejects the message's claim to authenticity.

### Symmetric Signing

![Symmetric Signing]({{site.baseurl}}/assets/images/symmetric-signing.png){:.ioda}

### Asymmetric Signing

![Asymmetric Signing]({{site.baseurl}}/assets/images/asymmetric-signing.png){:.ioda}

### HMAC

Symmetric

HMAC is used to **prevent manipulation** by someone who does not have access to the secret. Typically this means preventing manipulation by the client if the secret is only known to the server or to prevent manipulation in transit if the secret is known to client and server.

### RSA

Asymmetric

An RSA based signature is used to prevent manipulation and also to **allow others to verify the integrity and source of the data** without being able to manipulate the data. This can be done because the private key is only known to the provider and signer of the data while the public key is known to everybody who likes to verify the integrity.
