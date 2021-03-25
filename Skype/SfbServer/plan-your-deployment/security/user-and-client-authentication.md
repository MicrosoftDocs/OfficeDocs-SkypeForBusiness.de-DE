---
title: Benutzer- und Clientauthentifizierung für Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
description: Ein vertrauenswürdiger Benutzer ist einer, dessen Anmeldeinformationen von einem vertrauenswürdigen Server in Skype for Business Server authentifiziert wurden. Bei diesem Server handelt es sich in der Regel um einen Standard Edition-Server, einen Enterprise Edition-Front-End-Server oder einen Director. Skype for Business Server basiert auf Active Directory-Domänendiensten als einzelnes, vertrauenswürdiges Back-End-Repository mit Benutzeranmeldeinformationen.
ms.openlocfilehash: 544b661523bea73d65d64946d7bb88d4c6ecaa51
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120887"
---
# <a name="user-and-client-authentication-for-skype-for-business-server"></a>Benutzer- und Clientauthentifizierung für Skype for Business Server
 
Ein vertrauenswürdiger Benutzer ist einer, dessen Anmeldeinformationen von einem vertrauenswürdigen Server in Skype for Business Server authentifiziert wurden. Bei diesem Server handelt es sich in der Regel um einen Standard Edition-Server, einen Enterprise Edition-Front-End-Server oder einen Director. Skype for Business Server basiert auf Active Directory-Domänendiensten als einzelnes, vertrauenswürdiges Back-End-Repository mit Benutzeranmeldeinformationen.
  
Die Authentifizierung ist die Bereitstellung von Benutzerinformationen für einen vertrauenswürdigen Server. Skype for Business Server verwendet die folgenden Authentifizierungsprotokolle, je nach Status und Standort des Benutzers.
  
- **Sicherheitsprotokoll MIT Kerberos Version 5** für interne Benutzer mit Active Directory-Anmeldeinformationen. Kerberos erfordert eine Clientverbindung zu den Active Directory-Domänendiensten. Aus diesem Grund kann es nicht zur Authentifizierung von Clients außerhalb der Unternehmensfirewall verwendet werden.
    
- **NTLM-Protokoll** für Benutzer mit Active Directory-Anmeldeinformationen, die eine Verbindung über ein Endgerät von außerhalb der Unternehmensfirewall herstellen. Der Zugriffs-Edgedienst gibt Anmeldeanforderungen zur Authentifizierung an einen Director (falls vorhanden) oder an einen Front-End-Server weiter. Der Zugriffs-Edgedienst selbst führt keine Authentifizierung durch.
    
    > [!NOTE]
    > NTLM-Protokoll bietet weniger Schutz vor Angriffen als Kerberos, daher reduzieren einige Organisationen die Verwendung von NTLM. Aus diesem Grund kann der Zugriff auf Skype for Business Server auf interne Oder Clients beschränkt werden, die über eine VPN- oder DirectAccess-Verbindung verbunden sind. 
  
- **Digestprotokoll** für sogenannte anonyme Benutzer. Anonyme Benutzer sind Benutzer von außerhalb, die über keine anerkannten Active Directory-Anmeldeinformationen verfügen, jedoch zu einer Konferenz im Unternehmen eingeladen wurden und im Besitz eines gültigen Konferenzschlüssels sind. Die Digestauthentifizierung wird für keine weiteren Clientinteraktionen verwendet.
    
Die Skype for Business Server-Authentifizierung besteht aus zwei Phasen:
  
1. Zwischen Client und Server wird eine Sicherheitszuordnung erstellt.
    
2. Client und Server verwenden die vorhandene Sicherheitszuordnung, um Nachrichten zu signieren und um empfangene Nachrichten zu prüfen. Wenn die Authentifizierung auf dem Server aktiviert ist, werden nicht authentifizierte Nachrichten eines Clients nicht akzeptiert.
    
Jede Nachricht von einem Benutzer (nicht die Benutzeridentität selbst) wird mit Vertrauensinformationen ("Benutzervertrauensstellung") versehen. Der Server überprüft die einzelnen Nachrichten auf gültige Benutzeranmeldeinformationen. Wenn die Benutzerinformationen gültig sind, wird die Nachricht nicht nur vom ersten Server, der die Nachricht empfängt, akzeptiert, sondern auch von allen anderen Servern der vertrauenswürdigen Serverwolke wird keine Authentifizierung angefordert.
  
Benutzer mit gültigen Anmeldeinformationen, die von einem Verbundpartner ausgestellt wurden, werden als vertrauenswürdig eingestuft. Möglicherweise gelten für sie jedoch zusätzliche Einschränkungen, sodass sie nicht über dieselben Berechtigungen wie die internen Benutzer verfügen.
  
Die ICE- und TURN-Protokolle verwenden ebenfalls Digestabfrage wie in IETF TURN RFC beschrieben.
  
Clientzertifikate bieten eine alternative Möglichkeit für Benutzer, von Skype for Business Server authentifiziert zu werden. Anstatt einen Benutzernamen und ein Kennwort zur Verfügung zu stellen, verfügen die Benutzer über ein Zertifikat und den privaten Schlüssel, der dem Zertifikat entspricht, das zum Lösen einer kryptografischen Herausforderung erforderlich ist. (Dieses Zertifikat muss einen Betreffnamen oder einen alternativen Betreffnamen haben, der den Benutzer identifiziert und von einer Stammzertifizierungsstelle ausgestellt werden muss, die von Servern mit Skype for Business Server als vertrauenswürdig eingestuft wird, innerhalb des Gültigkeitszeitraums des Zertifikats liegt und nicht widerrufen wurde.) Um authentifiziert zu werden, müssen Benutzer nur eine persönliche Identifikationsnummer (PIN) eingeben. Zertifikate sind besonders nützlich für Telefone, Mobiltelefone und andere Geräte, auf denen es schwierig ist, einen Benutzernamen und ein Kennwort einzugeben.
  
### <a name="cryptographic-requirements-due-to-asp-net-45"></a>Kryptografieanforderungen aufgrund von ASP.NET 4.5 

Ab Skype for Business Server 2015 KU5 wird AES für ASP.NET 4.6 nicht unterstützt, und dies kann dazu führen, dass die Skype Meetings App nicht gestartet wird. Wenn ein Client AES als Überprüfungswert für den Computerschlüssel verwendet, müssen Sie den Computerschlüsselwert auf SHA-1 oder einen anderen unterstützten Algorithmus auf der Websiteebene von Skype Meetings App auf IIS zurücksetzen. Anweisungen finden Sie bei Bedarf unter [IIS 8.0 ASP.NET Configuration Management.](/iis/get-started/whats-new-in-iis-8/iis-80-aspnet-configuration-management)
  
Weitere unterstützte Werte sind:
  
- HMACSHA256
    
- HMACSHA384
    
- HMACSHA512
    
  Die Werte AES, 3DES und MD5 sind nicht mehr zulässig, wie sie einmal in ASP.NET 4 waren. [Kryptografische Verbesserungen in ASP.NET 4.5, Pt. 2](https://blogs.msdn.microsoft.com/webdev/2012/10/23/cryptographic-improvements-in-asp-net-4-5-pt-2/) enthält weitere Details.
