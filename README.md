---
title: F5 - Azure AD Integration
description: 
author: RZomerman
ms.date: 05/5/2020
layout: LandingPage
ms.topic: landing-page
ms.service: 
ms.subservice:
---

# Introduction

In this tutorial, you'll learn how to integrate F5 with Azure Active Directory (Azure AD)

When you integrate F5 with Azure AD, you can:

- Control in Azure AD who has access to the F5 published website or VPN.
- Enable your users to be automatically signed-in to F5 with their Azure AD accounts (SSO).
- Manage your accounts in one central location - the Azure portal.

To learn more about SaaS app integration with single sign-on in Azure AD, see Single sign-on to applications in Azure Active Directory.

This chapter describes the initial SAML configuration between F5 and Azure AD. In the next chapters, this configuration will be used in an Access Profile. Note that for each application you wish to publish through F5 with Azure AD sign-in support, you will have to create a new IdP and SP in F5.

## Prerequisites

To get started, you need the following items:

- An Azure AD subscription. If you don't have a subscription, you can get a free account.

Deploying the joint solution requires the following license:

- F5 BIG-IP® Best bundle (or)
- F5 BIG-IP Access Policy Manager™ (APM) standalone license
- F5 BIG-IP Access Policy Manager™ (APM) add-on license on an existing BIG-IP F5 BIG-IP® Local Traffic Manager™ (LTM).

In addition to the above license, the F5 system may also be licensed with:

- A URL Filtering subscription to use the URL category database
- An F5 IP Intelligence subscription to detect and block known attackers and malicious traffic
- A network hardware security module (HSM) to safeguard and manage digital keys for strong authentication

> [!NOTE]
> This walkthrough uses sample names and values from a company called Contoso. Replace these with your own. For example:
>
> - Domain name - **Contoso**
> - Application Name - **Header App**
> - Application URL - **https://header.contoso.com**

## Next steps

The configuration of your F5-APM with AAD integration can be based the Guided Configuration wizard, or through manual steps if desired. The chapter describes the basic creation of an application in Azure AD based on the F5 object available in the Marketplace.

- [F5 - Azure AD Integration - Create an Enterprise Application in AAD](f5-aad.md)

### Other items in this tutorial
 Guided:

> - [F5 - Azure AD Integration - Guided Configuration for HTTP Headers](f5-header-guided.md)
> - [F5 - Azure AD Integration - Guided Configuration for Kerberos](f5-kerberos-guided.md)

Manual deployments:

> - [Manual Configuration of AAD as SAML provider](f5--aad-saml-manual.md)
> - [Manual creation of an Access Profile with SAML](f5-accessprofile.md)
> - [Publishing Kerberos based applications with AAD & F5](f5-kerberos.md)
> - [Publishing Header based applications with AAD & F5](f5-header-based.md)
> - [Publishing Advanced Header based applications with AAD & F5](f5-advanced-header.md) - an advanced scenario where an external LDAP store is used to inject HTTP HEADERS to the backend webserver.
