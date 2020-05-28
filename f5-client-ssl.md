---
title: F5 - Import a PFX and create a client profile
description: 
author: RZomerman
ms.date: 05/5/2020
layout: LandingPage
ms.topic: landing-page
ms.service: 
ms.subservice:
---

# Introduction

The configuration of your F5 with AAD integration can be based the Guided Configuration wizard, or through manual steps if desired. This chapter describes the basic creation of an application in Azure AD based on the F5 object available in the Marketplace.

## Prerequisites

To get started, you need the following items:

- An Azure AD subscription. If you don't have a subscription, you can get a free account.

## F5 Configuration - SSL Certificates

Because we are publishing an SSL based website, we need to load an SSL certificate into the F5 system. This certificate will be used to host our website and should match the URL used (`<portal.contoso.com / *.contoso.com>`).

1. Go to, **System >> Certificate Management >> Traffic Certificate Management : SSL Certificate List : Import**

2. If you have a pfx file, set the Import Type to PKCS 12 (IIS), give the imported certificate a name, choose the pfx file and provide the `<PFX password>` prior to clicking **Import**

![F5 Import PFX](./images/)

Next, the certificate needs to be added to a client SSL profile, create a new profile using:

3. Go to **Local Traffic >> Profiles : SSL : Client** and click **+**
4. Give the profile a name (for example `<.contoso.com>`)
5. Leave the parent to **client**
6. Under **basic** select the **Custom** checkbox
7. Click **Add** under the **Certificate Key Chain** and add your previously imported certificate
8. Click **Finish**
