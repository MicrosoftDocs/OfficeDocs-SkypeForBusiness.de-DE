---
title: Benutzer- und Client für die Authentifizierung Skype Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
description: Ein vertrauenswürdiger ist Benutzer ein, dessen Anmeldeinformationen von einem vertrauenswürdigen Server in Skype für Business Server authentifiziert wurden. Dieser Server ist in der Regel ein Standard Edition-Server, Enterprise Edition-Front-End-Server und Director. Skype für Business Server nutzt Active Directory Domain Services als einzelnen, vertrauenswürdigen Back-End-Repository von Benutzeranmeldeinformationen.
ms.openlocfilehash: 9616774bf721863503c2ebd9145c6860f7068ef3
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2018
ms.locfileid: "26294340"
---
# <a name="user-and-client-authentication-for-skype-for-business-server"></a>Benutzer- und Client für die Authentifizierung Skype Business Server
 
Ein vertrauenswürdiger ist Benutzer ein, dessen Anmeldeinformationen von einem vertrauenswürdigen Server in Skype für Business Server authentifiziert wurden. Dieser Server ist in der Regel ein Standard Edition-Server, Enterprise Edition-Front-End-Server und Director. Skype für Business Server nutzt Active Directory Domain Services als einzelnen, vertrauenswürdigen Back-End-Repository von Benutzeranmeldeinformationen.
  
Authentifizierung bedeutet die Bereitstellung von Benutzeranmeldeinformationen für einen vertrauenswürdigen Server. Skype für Business Server verwendet die folgenden Authentifizierungsprotokolle – abhängig vom Status und Standort des Benutzers.
  
- **MIT Kerberos Version 5 Security-Protokoll** für interne Benutzer mit Active Directory-Anmeldeinformationen. Kerberos erfordert Clients eine Verbindung mit Active Directory-Domänendienste, weshalb sie verwendet werden, für die Authentifizierung von Clients außerhalb der Unternehmensfirewall befindet.
    
- **NTLM-Protokoll** für Benutzer mit Active Directory-Anmeldeinformationen, die über ein Endgerät von außerhalb der Unternehmensfirewall eine Verbindung herstellen. Der Zugriffs-edgedienst übergibt Anfragen zur Anmeldung an einen Director, falls vorhanden, oder ein Front-End-Server für die Authentifizierung. Der Zugriffs-edgedienst selbst führt keine Authentifizierung.
    
    > [!NOTE]
    > Da der Angriffsschutz des NTLM-Protokolls schwächer ist als der von Kerberos, minimieren einige Organisationen die Nutzung von NTLM. Daher Zugriff auf Skype für Business Server unter Umständen zu internen eingeschränkt oder Clients über eine VPN- oder DirectAccess Verbindung verbunden. 
  
- Das **Digestprotokoll** für sogenannte anonyme Benutzer. Anonyme Benutzer sind externe Benutzer, die nicht über anerkannte Active Directory-Anmeldeinformationen verfügen, aber zu einer lokalen Konferenz eingeladen wurden und einen gültigen Konferenzschlüssel besitzen. Die Digestauthentifizierung wird nicht für andere Clientinteraktionen verwendet.
    
Skype für Business Server-Authentifizierung besteht aus zwei Phasen:
  
1. Zwischen dem Client und dem Server wird eine Sicherheitszuordnung eingerichtet.
    
2. Client und Server verwenden die vorhandene Sicherheitszuordnung, um Nachrichten, die sie senden, zu signieren, und Nachrichten, die sie empfangen, zu überprüfen. Nicht authentifizierte Nachrichten von einem Client werden nicht akzeptiert, wenn die Authentifizierung auf dem Server aktiviert ist.
    
Die Benutzervertrauenswürdigkeit ist mit jeder Nachricht verbunden, die von einem Benutzer stammt, nicht mit der Benutzeridentität selbst. Der Server überprüft jede Nachricht auf gültige Benutzeranmeldeinformationen. Wenn die Benutzeranmeldeinformationen gültig sind, wird die Nachricht weder vom ersten Server, der sie empfängt, noch von allen anderen Servern in der vertrauenswürdigen Servercloud herausgefordert.
  
Benutzer mit gültigen Anmeldeinformationen, die von einem Verbundpartner ausgegeben wurden, sind vertrauenswürdig, erhalten aber optional aufgrund zusätzlicher Einschränkungen nicht sämtliche Berechtigungen, die internen Benutzern erteilt werden.
  
Die Protokolle ICE und TURN verwenden ebenfalls die Digestherausforderung, wie im IETF TURN RFC beschrieben.
  
Clientzertifikate stellen eine Alternative für Benutzer von Skype für Business Server authentifiziert werden. Anstelle der Angabe eines Benutzernamens und eines Kennworts haben die Benutzer ein Zertifikat und den privaten Schlüssel, der dem Zertifikat entspricht, das zum Auflösen einer kryptografischen Aufforderung benötigt wird. (Dieses Zertifikat benötigen eine Antragstellername oder alternativer Antragstellername, der identifiziert den Benutzer und muss einer Stammzertifizierungsstelle, die Servern mit Skype für Business Server als vertrauenswürdig einstufen, die innerhalb der Gültigkeitsdauer werden und nicht gesperrt.) Um authentifiziert werden, müssen Benutzer nur eine persönliche Identifikationsnummer (PIN) eingeben. Zertifikate sind besonders für Telefone, Mobiltelefone und andere Geräte, auf dem ist es schwierig, einen Benutzernamen und ein Kennwort einzugeben.
  
### <a name="cryptographic-requirements-due-to-asp-net-45"></a>Kryptografische Anforderungen aufgrund von ASP .NET 4.5 

Ab Skype für Business Server 2015 CU5 AES für ASP.NET 4.6 nicht unterstützt wird, und dadurch kann Skype Besprechungen App zu einem Fehler beim Starten. Wenn ein Client AES als Wert Schlüssel-Überprüfung Computer verwendet wird, Sie den Schlüsselwert Computer auf SHA-1 oder eine andere unterstützte Algorithmus auf Standortebene Skype Besprechungen App auf IIS zurückzusetzen müssen. Falls erforderlich, finden Sie unter [IIS 8.0 ASP.NET Configuration Management](https://docs.microsoft.com/en-us/iis/get-started/whats-new-in-iis-8/iis-80-aspnet-configuration-management) Anweisungen.
  
Weitere unterstützte Werte:
  
- HMACSHA256
    
- HMACSHA384
    
- HMACSHA512
    
  Die Werte AES, 3DES und MD5 sind nicht mehr zulässig, während sie in ASP.NET 4 noch zulässig waren. [
                Weitere Details finden Sie unter Cryptographic Improvements in ASP.NET 4.5, pt. 2](https://blogs.msdn.microsoft.com/webdev/2012/10/23/cryptographic-improvements-in-asp-net-4-5-pt-2/).
  
