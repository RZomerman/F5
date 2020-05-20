---
title: F5 - Azure AD Integration - Manual creation of SAML provider
description: 
author: RZomerman
ms.date: 05/5/2020
layout: LandingPage
ms.topic: landing-page
ms.service: 
ms.subservice:
---

# Introduction

The configuration of your F5 with AAD integration can be based the Guided Configuration wizard, or through manual steps if desired. This chapter describes the basic creation of a SAML Service Provider with external IdP and is not required if you are following the Guided Configuration tutorials.

## Prerequisites

To get started, you need the following items:
    - an application in Azure AD according to: [F5 - Creating an Enterprise Application in Azure AD](f5-aad.md)

## Creating an IDP and SP in F5

This chapter will create an IDP linked to the created Azure AD application.

1. In F5 select **Access : Federation : SAML Service Provider : External IdP Connectors**
1. Click the down arrow under **Create** and select **From metadata**
1. Browse for the AAD downloaded `<Federation Metadata XML>` file, give the provider a name such as `<AAD - header.contoso.com>` and click **OK**
1. Go to **Access : Federation : SAML Service Provider : Local SP Services** and click **Create**
1. Give a **Name** (such as `<AAD - header.contoso.com>`) an **Entity ID** (such as `<https://header.contoso.com>`) and **Host** (such as `<https://header.contoso.com>`) and click **OK**
1. Select the newly created Service Provider entry and click **Bind/Unbind IdP Connectors**
1. in the pop-up, select **Add New Row**. Select the created IdP provider (`<AAD - header.contoso.com>`) in the dropdown under **SAML IdP Connectors** and click **Update** and click **OK** to close
1. Select the newly created Service Provider entry and click **Export Metadata**

A file will be downloaded from the F5 device. This file will have to be uploaded into the application in Azure under the SAML configuration. 

1. Open Azure Active Directory in Azure and select **Enterprise Applications**
1. search for your created application (`<Header App>`) and open the properties of the application
1. Once the application details are open, select **Single sign-on** and select **SAML**
1. on the top bar, select **Upload metadata file** and upload the exported F5 XML file.
1. click **Save**



## Next steps

This concludes the configuration of the SP, IdP and Azure AD configuration which is required for almost all F5 scenario's such as Kerberos, Header based and advanced Header injection scenarios.

> - [Publishing Kerberos based applications with AAD & F5](f5-kerberos.md)
> - [Publishing Header based applications with AAD & F5](f5-header.md)
> - [Publishing Advanced Header based applications with AAD & F5](f5-advanced-header.md) - an advanced scenario where an external LDAP store is used to inject HTTP HEADERS to the backend webserver.
