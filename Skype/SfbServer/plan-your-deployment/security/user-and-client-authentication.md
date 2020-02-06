---
title: Benutzer-und Clientauthentifizierung für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
description: Ein vertrauenswürdiger Benutzer ist derjenige, dessen Anmeldeinformationen von einem vertrauenswürdigen Server in Skype for Business Server authentifiziert wurden. Dieser Server ist in der Regel ein Standard Edition-Server, Enterprise Edition-Front-End-Server oder Director. Skype for Business Server basiert auf Active Directory-Domänendiensten als einzelnes, vertrauenswürdiges Back-End-Repository für Benutzeranmeldeinformationen.
ms.openlocfilehash: 2ffabce6546bf8b542503f8c80fe5cb2b952c568
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815583"
---
# <a name="user-and-client-authentication-for-skype-for-business-server"></a>Benutzer-und Clientauthentifizierung für Skype for Business Server
 
Ein vertrauenswürdiger Benutzer ist derjenige, dessen Anmeldeinformationen von einem vertrauenswürdigen Server in Skype for Business Server authentifiziert wurden. Dieser Server ist in der Regel ein Standard Edition-Server, Enterprise Edition-Front-End-Server oder Director. Skype for Business Server basiert auf Active Directory-Domänendiensten als einzelnes, vertrauenswürdiges Back-End-Repository für Benutzeranmeldeinformationen.
  
Authentifizierung bedeutet die Bereitstellung von Benutzeranmeldeinformationen für einen vertrauenswürdigen Server. Skype for Business Server verwendet die folgenden Authentifizierungsprotokolle, abhängig vom Status und Standort des Benutzers.
  
- Mit **Kerberos Version 5-Sicherheitsprotokoll** für interne Benutzer mit Active Directory-Anmeldeinformationen Für Kerberos ist eine Clientverbindung mit Active Directory-Domänendiensten erforderlich, weshalb Sie nicht für die Authentifizierung von Clients außerhalb der Unternehmensfirewall verwendet werden kann.
    
- **NTLM-Protokoll** für Benutzer mit Active Directory-Anmeldeinformationen, die von einem Endpunkt außerhalb der Unternehmensfirewall eine Verbindung herstellen. Der Access-Edgedienst übergibt Anmeldeanforderungen an einen Director, falls vorhanden, oder einen Front-End-Server zur Authentifizierung. Der Access-Edgedienst selbst führt keine Authentifizierung durch.
    
    > [!NOTE]
    > Da der Angriffsschutz des NTLM-Protokolls schwächer ist als der von Kerberos, minimieren einige Organisationen die Nutzung von NTLM. Daher kann der Zugriff auf Skype for Business Server auf interne oder über eine VPN-oder DirectAccess-Verbindung angeschlossene Clients beschränkt sein. 
  
- Das **Digestprotokoll** für sogenannte anonyme Benutzer. Anonyme Benutzer sind externe Benutzer, die nicht über anerkannte Active Directory-Anmeldeinformationen verfügen, aber zu einer lokalen Konferenz eingeladen wurden und einen gültigen Konferenzschlüssel besitzen. Die Digestauthentifizierung wird nicht für andere Clientinteraktionen verwendet.
    
Die Skype for Business Server-Authentifizierung besteht aus zwei Phasen:
  
1. Zwischen dem Client und dem Server wird eine Sicherheitszuordnung eingerichtet.
    
2. Client und Server verwenden die vorhandene Sicherheitszuordnung, um Nachrichten, die sie senden, zu signieren, und Nachrichten, die sie empfangen, zu überprüfen. Nicht authentifizierte Nachrichten von einem Client werden nicht akzeptiert, wenn die Authentifizierung auf dem Server aktiviert ist.
    
Die Benutzervertrauenswürdigkeit ist mit jeder Nachricht verbunden, die von einem Benutzer stammt, nicht mit der Benutzeridentität selbst. Der Server überprüft jede Nachricht auf gültige Benutzeranmeldeinformationen. Wenn die Benutzeranmeldeinformationen gültig sind, wird die Nachricht weder vom ersten Server, der sie empfängt, noch von allen anderen Servern in der vertrauenswürdigen Servercloud herausgefordert.
  
Benutzer mit gültigen Anmeldeinformationen, die von einem Verbundpartner ausgegeben wurden, sind vertrauenswürdig, erhalten aber optional aufgrund zusätzlicher Einschränkungen nicht sämtliche Berechtigungen, die internen Benutzern erteilt werden.
  
Die Protokolle ICE und TURN verwenden ebenfalls die Digestherausforderung, wie im IETF TURN RFC beschrieben.
  
Client Zertifikate bieten eine alternative Möglichkeit für Benutzer, von Skype for Business Server authentifiziert zu werden. Anstelle der Angabe eines Benutzernamens und eines Kennworts haben die Benutzer ein Zertifikat und den privaten Schlüssel, der dem Zertifikat entspricht, das zum Auflösen einer kryptografischen Aufforderung benötigt wird. (Dieses Zertifikat muss über einen Antragstellernamen oder einen alternativen Antragstellernamen verfügen, der den Benutzer identifiziert und von einer Stammzertifizierungsstelle ausgestellt werden muss, die von Servern mit Skype for Business Server vertraut ist, innerhalb des Gültigkeitszeitraums des Zertifikats liegt und nicht widerrufen wurde.) Damit die Benutzer authentifiziert werden können, müssen Sie nur eine persönliche Identifikationsnummer (PIN) eingeben. Zertifikate sind besonders nützlich für Telefone, Handys und andere Geräte, bei denen es schwierig ist, einen Benutzernamen und ein Kennwort einzugeben.
  
### <a name="cryptographic-requirements-due-to-asp-net-45"></a>Kryptografische Anforderungen aufgrund von ASP .NET 4,5 

Ab Skype for Business Server 2015 CU5 wird AES für ASP.NET 4,6 nicht unterstützt, was dazu führen kann, dass die APP für Skype-Besprechungen nicht gestartet wird. Wenn ein Client AES als Computerschlüssel-Überprüfungs Wert verwendet, müssen Sie den Wert des Computerschlüssels auf SHA-1 oder einen anderen unterstützten Algorithmus auf der Websiteebene der Skype-Besprechungs-App auf IIS zurücksetzen. Falls erforderlich, finden Sie Anweisungen unter [IIS 8,0 ASP.net Configuration Management](https://docs.microsoft.com/iis/get-started/whats-new-in-iis-8/iis-80-aspnet-configuration-management) .
  
Weitere unterstützte Werte:
  
- HMACSHA256
    
- HMACSHA384
    
- HMACSHA512
    
  Die Werte AES, 3DES und MD5 sind nicht mehr zulässig, während sie in ASP.NET 4 noch zulässig waren. Die [kryptografischen Verbesserungen in ASP.NET 4,5, PT. 2,](https://blogs.msdn.microsoft.com/webdev/2012/10/23/cryptographic-improvements-in-asp-net-4-5-pt-2/) haben weitere Details.
  
