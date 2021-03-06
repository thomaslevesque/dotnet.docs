---
title: "How to: Specify Client Credentials for a Data Service Request (WCF Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "WCF Data Services, customizing requests"
ms.assetid: 1632f9af-e45f-4363-9222-03823daa8e28
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
---
# How to: Specify Client Credentials for a Data Service Request (WCF Data Services)
By default, the client library does not supply credentials when sending a request to an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] service. However, you can specify that credentials be sent to authenticate requests to the data service by supplying a <xref:System.Net.NetworkCredential> for the <xref:System.Data.Services.Client.DataServiceContext.Credentials%2A> property of the <xref:System.Data.Services.Client.DataServiceContext>. For more information, see [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md). The example in this topic shows how to explicitly provide credentials that are used by the [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] client when requesting data from the data service.  
  
 The example in this topic uses the Northwind sample data service and autogenerated client data service classes. This service and the client data classes are created when you complete the [WCF Data Services quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md). You can also use the [Northwind sample data service](http://go.microsoft.com/fwlink/?LinkId=187426) that is published on the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] Web site; this sample data service is read-only and attempting to save changes returns an error. The sample data services on the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] Web site allow anonymous authentication.  
  
## Example  
 The following example is from the code-behind page for an Extensible Application Markup Language (XAML) file that is the main page of the Windows Presentation Framework application. This example displays a `LoginWindow` instance to collect authentication credentials from the user, and then uses these credentials when making a request to the data service.  
  
<!-- TODO: review snippet reference  [!CODE [Astoria NorthwindClient#ClientCredentials](Astoria NorthwindClient#ClientCredentials)]  -->  
  
## Example  
 The following XAML defines the main page of the WPF application.  
  
<!-- TODO: review snippet reference  [!CODE [Astoria NorthwindClient#ClientCredentialsXaml](Astoria NorthwindClient#ClientCredentialsXaml)]  -->  
  
## Example  
 The following example is from the code-behind page for the window that is used to collect the authentication credentials from the user before making a request to the data service.  
  
<!-- TODO: review snippet reference  [!CODE [Astoria NorthwindClient#ClientCredentialsLogin](Astoria NorthwindClient#ClientCredentialsLogin)]  -->  
  
## Example  
 The following XAML defines the login of the WPF application.  
  
<!-- TODO: review snippet reference  [!CODE [Astoria NorthwindClient#ClientCredentialsLoginXaml](Astoria NorthwindClient#ClientCredentialsLoginXaml)]  -->  
  
## .NET Framework Security  
 The following security considerations apply to the example in this topic:  
  
-   To verify that the credentials supplied in this sample work, the Northwind data service must use an authentication scheme other than anonymous access. Otherwise, the Web site hosting the data service will not request credentials.  
  
-   User credentials should only be requested during execution and should not be cached. Credentials must always be stored securely.  
  
-   Data sent with Basic and Digest Authentication is not encrypted, so the data can be seen by an adversary. Additionally, basic authentication credentials (user name and password) are sent in cleartext and can be intercepted.  
  
 For more information, see [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md).  
  
## See Also  
 [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)   
 [WCF Data Services Client Library](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)