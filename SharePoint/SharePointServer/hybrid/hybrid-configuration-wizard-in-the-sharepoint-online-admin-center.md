---
title: Hybrid Configuration Wizard in the SharePoint admin center
ms.reviewer: 
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2023
audience: ITPro
f1.keywords:
- CSH
ms.topic: conceptual
ms.service: sharepoint-server-itpro
ms.localizationpriority: medium
ms.collection:
- Ent_O365_Hybrid
- IT_Sharepoint_Server
- IT_SharePoint_Hybrid_Top
- Strat_SP_gtc
- M365-collaboration
- SPO_Content
ms.custom: 
ms.assetid: dcac4cbf-7840-470a-9712-3b968c4f06d0
description: Learn how to use the Hybrid Configuration Wizard in the SharePoint admin center.

---

# Hybrid Configuration Wizard in the SharePoint admin center

[!INCLUDE[appliesto-2013-2016-2019-SUB-SPO-md](../includes/appliesto-2013-2016-2019-SUB-SPO-md.md)]

## What is the Hybrid Configuration Wizard?

Hybrid Configuration Wizard is a wizard that can be downloaded to your SharePoint Server from Microsoft 365. The wizard helps automate certain configuration steps needed to connect your on-premises SharePoint Server environment with SharePoint in Microsoft 365. The Hybrid Configuration Wizard is your assistant, designed to do some of the work for you.

Use the Hybrid Configuration Wizard to redirect OneDrive to Microsoft 365, leverage hybrid site features or app launcher, and add some extra integration between on-premises SharePoint Server and an extranet site made in Microsoft 365. Hybrid Configuration Wizard also creates a Server-to-Server (S2S)/OAuth connection for your [SharePoint Hybrid features](sharepoint-hybrid-sites-and-search.md).

## Using the Hybrid Configuration Wizard

First, you need to ensure you meet the prerequisites in your SharePoint Server on-premises farm, then you can run the Hybrid Configuration Wizard.

 **Prerequisites to run the Hybrid Configuration Wizard**

The Hybrid Configuration Wizard requires the [.NET Framework 4.6.2](https://dotnet.microsoft.com/download/dotnet-framework/net462) in order to run. 

To run the Hybrid Configuration Wizard, you must be:

- A member of the Farm Administrators group.

- A service application administrator (Full Control) for the User Profile Service.

- A Microsoft 365 Global Admin, either with or without multi-factor authentication (MFA) enabled for the account.

- Signed in to Microsoft 365 and SharePoint Server from a server in your SharePoint Server farm.

- Able to launch the Hybrid Configuration Wizard as a Farm Admin with elevated permissions.

> [!IMPORTANT]
> The Hybrid Configuration Wizard must be launched from an on-premises server with SharePoint Server 2013, SharePoint Server 2016, SharePoint Server 2019, or SharePoint Server Subscription Edition installed. Launch it in the environment you want to use for your SharePoint hybrid.
>
> Microsoft recommends that you use roles with the fewest permissions. Using lower permissioned accounts helps improve security for your organization. Global Administrator is a highly privileged role that should be limited to emergency scenarios when you can't use an existing role.


## SharePoint Hybrid features offered in the Hybrid Configuration Wizard

Use the Hybrid Configuration Wizard to configure, or assist with the configuration of, hybrids that connect Microsoft 365 and your on-premises SharePoint environment.

The Hybrid Configuration Wizard helps with or completes the setup of these hybrid features:

- **[Hybrid OneDrive](plan-hybrid-onedrive-for-business.md)** - Choosing this option will redirect on-premises My Sites/OneDrive sites to SharePoint in Microsoft 365 and OneDrive. After the wizard completes, any click of the OneDrive link from on-premises redirects to OneDrive in the cloud. Once your redirection is complete, the users can begin to migrate any files to their online OneDrive. This option also sets up hybrid user profiles. When users click to view a profile, they'll be redirected to the profile in Microsoft 365.

- **[Hybrid Sites Features](sharepoint-hybrid-sites-and-search.md)** - Choosing this option sets up hybrid sites features, a suite of site integration features, and OneDrive redirection. Selecting this option configures hybrid OneDrive and hybrid user profiles, hybrid site following, and the hybrid app launcher.

- **[Hybrid App Launcher](the-extensible-hybrid-app-launcher.md)** - This hybrid feature further integrates Microsoft 365 with your on-premises SharePoint Server farm by placing tiles like Office 365 Delve and Video (and custom Microsoft 365 tiles you may have) on the on-premises SharePoint Server App Launcher. This option also sets up hybrid OneDrive with user profile redirection, and sites features.

- **[Business-to-business (B2B) extranet sites](../../SharePointOnline/create-b2b-extranet.md)** - Choosing this option installs extra features you can integrate with an extranet site you create in Microsoft 365. With Microsoft 365 extranet, partners can connect directly to a members-only site in Microsoft 365 without access to the corporate on-premises environment or any other Microsoft 365 site. Choosing this option sets up OneDrive and user profile redirection, sites features, and hybrid app launcher. 

- **[Hybrid Taxonomy](plan-hybrid-sharepoint-taxonomy-and-hybrid-content-types.md)** - This feature allows a centralized taxonomy that's readable and writable in the Microsoft 365 Cloud, to be used as a read-only copy within the premises. This feature includes Hybrid Content type (June 2017 PU required) which replicates the published content types in Microsoft 365 to on-premises. Choosing this option sets up OneDrive and user profile redirection, sites features, and hybrid app launcher.

- **[Hybrid self-service site creation](hybrid-self-service-site-creation.md)** - This feature redirects the default self-service site creation page in SharePoint Server 2013, SharePoint Server 2016, or SharePoint Server 2019 (/_layouts/15/scsignup.aspx) to the SharePoint in Microsoft 365 Group Creation page. This setting can be configured independently for each web application in your farm. It helps your users create their sites in SharePoint in Microsoft 365 instead of SharePoint Server.

- **[Cloud hybrid search](./learn-about-cloud-hybrid-search-for-sharepoint.md)** - Choosing this option creates a cloud Search service application in SharePoint Server and connects it to your Microsoft 365 organization. Implementing this option means you've performed one of the steps needed to set up cloud hybrid search; you must do the rest of the steps yourself (see the [roadmap](configure-cloud-hybrid-searchroadmap.md)). This option doesn't include setting up of other hybrid features.

> [!TIP]
> If the Hybrid Configuration Wizard is run a second time with an enabled feature unchecked, this setting won't cause the feature to be uninstalled. Any additional selections will be installed and previously installed features will remain.

For all options, the Hybrid Configuration Wizard configures a server-to-server trust between your SharePoint Server farm and Microsoft 365.

The Hybrid Configuration Wizard doesn't uninstall features. If you run the Hybrid Configuration Wizard and deselect a feature that you previously installed, it remains installed.

To get started configuring hybrid features for your environment, choose from:

- [Configure hybrid OneDrive - roadmap](configure-hybrid-onedrive-for-businessroadmap.md)

- [Configure hybrid sites features - roadmap](configure-hybrid-sites-featuresroadmap.md)

- [Configure cloud hybrid search - roadmap](configure-cloud-hybrid-searchroadmap.md)

- [Configure hybrid SharePoint taxonomy and hybrid content types](configure-hybrid-sharepoint-taxonomy-and-hybrid-content-types.md)

## Hybrid Configuration Wizard Prerequisite Checking

While running the Hybrid Configuration Wizard, the basic SharePoint farm settings are checked which would otherwise block the setup of essential hybrid building-blocks (such as OAuth/S2S Trust). The importance of settings' check is why you should launch the Hybrid Configuration Wizard from a server that will be part of your SharePoint hybrid. Some of the settings that are detected and checked while the configuration is run, include whether the:

- SharePoint Server farm exists

- Account is a farm administrator

- SharePoint farm is a version that can function in a hybrid configuration

- AppMangementServiceInstance is online

- AppMangementServiceApplication is online

- AppMangementServiceApplicationProxy is online

- UserProfileApplicationProxy is online

- The SPO365LinkSettings cmdlet (used to set MySiteHostURL) is accessible on the server 

The results of this testing can be viewed as a report if any prerequisite isn't met. If all prerequisites are met, you'll see green check-marks beside all the prerequisites and can continue your hybrid configuration.

## Authentication realm update

As part of hybrid configuration, the Hybrid Configuration Wizard updates the on-premises farm's authentication realm to match the Microsoft 365 organization context ID. After the authentication realm is changed, existing SharePoint in Microsoft 365 add-ins fail to authenticate. The Hybrid Configuration Wizard attempts to fix this issue automatically. If the Hybrid Configuration Wizard isn't able to fix this issue or if you choose to fix it manually, follow the steps in [Fix the HTTP 401 error with provider-hosted add-ins and issues with workflow and cross farm trust scenarios in SharePoint in Microsoft 365](https://support.microsoft.com/help/4010011).

## See also

#### Other Resources

[You receive the error "Value cannot be null. Parameter name: My site URL or team site URL from Discovery Service is null or empty" when you use the SharePoint Hybrid Configuration Wizard](https://support.microsoft.com/kb/3204761)
