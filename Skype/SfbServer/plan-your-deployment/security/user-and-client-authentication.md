---
title: Benutzer- und Clientauthentifizierung für Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
description: Ein vertrauenswürdiger Benutzer ist ein Benutzer, dessen Anmeldeinformationen von einem vertrauenswürdigen Server in Skype for Business Server authentifiziert wurden. Dieser Server ist in der Regel ein Standard Edition Server, Enterprise Edition Front-End-Server oder Director. Skype for Business Server nutzt Active Directory Domain Services als einziges, vertrauenswürdiges Back-End-Repository von Benutzeranmeldeinformationen.
ms.openlocfilehash: d256efdf69afce16a06b3b055a9446b29deb7cb0
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60737641"
---
# <a name="user-and-client-authentication-for-skype-for-business-server"></a>Benutzer- und Clientauthentifizierung für Skype for Business Server
 
Ein vertrauenswürdiger Benutzer ist ein Benutzer, dessen Anmeldeinformationen von einem vertrauenswürdigen Server in Skype for Business Server authentifiziert wurden. Dieser Server ist in der Regel ein Standard Edition Server, Enterprise Edition Front-End-Server oder Director. Skype for Business Server nutzt Active Directory Domain Services als einziges, vertrauenswürdiges Back-End-Repository von Benutzeranmeldeinformationen.
  
Die Authentifizierung ist die Bereitstellung von Benutzerinformationen für einen vertrauenswürdigen Server. Skype for Business Server verwendet je nach Status und Speicherort des Benutzers die folgenden Authentifizierungsprotokolle.
  
- **Sicherheitsprotokoll MIT Kerberos Version 5** für interne Benutzer mit Active Directory-Anmeldeinformationen. Kerberos erfordert eine Clientverbindung zu den Active Directory-Domänendiensten. Aus diesem Grund kann es nicht zur Authentifizierung von Clients außerhalb der Unternehmensfirewall verwendet werden.
    
- **NTLM-Protokoll** für Benutzer mit Active Directory-Anmeldeinformationen, die eine Verbindung über ein Endgerät von außerhalb der Unternehmensfirewall herstellen. Der Zugriffs-Edgedienst gibt Anmeldeanforderungen zur Authentifizierung an einen Director (falls vorhanden) oder an einen Front-End-Server weiter. Der Zugriffs-Edgedienst selbst führt keine Authentifizierung durch.
    
    > [!NOTE]
    > NTLM-Protokoll bietet weniger Schutz vor Angriffen als Kerberos, daher reduzieren einige Organisationen die Verwendung von NTLM. Daher kann der Zugriff auf Skype for Business Server auf interne oder über eine VPN- oder DirectAccess-Verbindung verbundene Clients beschränkt sein. 
  
- **Digestprotokoll** für sogenannte anonyme Benutzer. Anonyme Benutzer sind Benutzer von außerhalb, die über keine anerkannten Active Directory-Anmeldeinformationen verfügen, jedoch zu einer Konferenz im Unternehmen eingeladen wurden und im Besitz eines gültigen Konferenzschlüssels sind. Die Digestauthentifizierung wird für keine weiteren Clientinteraktionen verwendet.
    
Skype for Business Server Authentifizierung besteht aus zwei Phasen:
  
1. Zwischen Client und Server wird eine Sicherheitszuordnung erstellt.
    
2. Client und Server verwenden die vorhandene Sicherheitszuordnung, um Nachrichten zu signieren und um empfangene Nachrichten zu prüfen. Wenn die Authentifizierung auf dem Server aktiviert ist, werden nicht authentifizierte Nachrichten eines Clients nicht akzeptiert.
    
Jede Nachricht von einem Benutzer (nicht die Benutzeridentität selbst) wird mit Vertrauensinformationen ("Benutzervertrauensstellung") versehen. Der Server überprüft die einzelnen Nachrichten auf gültige Benutzeranmeldeinformationen. Wenn die Benutzerinformationen gültig sind, wird die Nachricht nicht nur vom ersten Server, der die Nachricht empfängt, akzeptiert, sondern auch von allen anderen Servern der vertrauenswürdigen Serverwolke wird keine Authentifizierung angefordert.
  
Benutzer mit gültigen Anmeldeinformationen, die von einem Verbundpartner ausgestellt wurden, werden als vertrauenswürdig eingestuft. Möglicherweise gelten für sie jedoch zusätzliche Einschränkungen, sodass sie nicht über dieselben Berechtigungen wie die internen Benutzer verfügen.
  
Die ICE- und TURN-Protokolle verwenden ebenfalls Digestabfrage wie in IETF TURN RFC beschrieben.
  
Clientzertifikate bieten eine alternative Möglichkeit für Benutzer, von Skype for Business Server authentifiziert zu werden. Anstatt einen Benutzernamen und ein Kennwort anzugeben, verfügen Benutzer über ein Zertifikat und den privaten Schlüssel, der dem Zertifikat entspricht, das zum Beheben einer kryptografischen Herausforderung erforderlich ist. (Dieses Zertifikat muss einen Antragstellernamen oder einen alternativen Antragstellernamen aufweisen, der den Benutzer identifiziert und von einer Stammzertifizierungsstelle ausgestellt werden muss, die von Servern mit Skype for Business Server als vertrauenswürdig eingestuft wird, sich innerhalb des Gültigkeitszeitraums des Zertifikats befindet und nicht widerrufen wurde.) Um authentifiziert zu werden, müssen Benutzer nur eine persönliche Identifikationsnummer (PIN) eingeben. Zertifikate sind besonders nützlich für Telefone, Mobiltelefone und andere Geräte, auf denen es schwierig ist, einen Benutzernamen und ein Kennwort einzugeben.
  
### <a name="cryptographic-requirements-due-to-asp-net-45"></a>Kryptografische Anforderungen aufgrund von ASP .NET 4.5 

Ab Skype for Business Server 2015 CU5 wird AES für ASP.NET 4.6 nicht unterstützt, was dazu führen kann, dass Skype Besprechungs-App nicht gestartet werden kann. Wenn ein Client AES als Computerschlüsselüberprüfungswert verwendet, müssen Sie den Computerschlüsselwert auf SHA-1 oder einen anderen unterstützten Algorithmus auf der Websiteebene Skype Besprechungs-App auf IIS zurücksetzen. Anweisungen finden Sie bei Bedarf unter [IIS 8.0 ASP.NET Configuration Management.](/iis/get-started/whats-new-in-iis-8/iis-80-aspnet-configuration-management)
  
Weitere unterstützte Werte sind:
  
- HMACSHA256
    
- HMACSHA384
    
- HMACSHA512
    
  Die Werte AES, 3DES und MD5 sind nicht mehr zulässig, da sie sich einmal in ASP.NET 4 befanden. [Kryptografieverbesserungen in ASP.NET 4.5, Pt. 2,](https://blogs.msdn.microsoft.com/webdev/2012/10/23/cryptographic-improvements-in-asp-net-4-5-pt-2/) enthält weitere Details.
