---
title: Benutzer- und Clientauthentifizierung für Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/14/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
description: Ein vertrauenswürdiger ist Benutzer ein, dessen Anmeldeinformationen von einem vertrauenswürdigen Server in Skype für Business Server 2015 authentifiziert wurden. Dieser Server ist in der Regel ein Standard Edition-Server, Enterprise Edition-Front-End-Server und Director. Skype für Business Server nutzt Active Directory Domain Services als einzelnen, vertrauenswürdigen Back-End-Repository von Benutzeranmeldeinformationen.
ms.openlocfilehash: d8fa9265a4c27432dd4c2dba6e15c07e39f348b8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="user-and-client-authentication-for-skype-for-business-server-2015"></a>Benutzer- und Clientauthentifizierung für Skype for Business Server 2015
 
Ein vertrauenswürdiger ist Benutzer ein, dessen Anmeldeinformationen von einem vertrauenswürdigen Server in Skype für Business Server 2015 authentifiziert wurden. Dieser Server ist in der Regel ein Standard Edition-Server, Enterprise Edition-Front-End-Server und Director. Skype für Business Server nutzt Active Directory Domain Services als einzelnen, vertrauenswürdigen Back-End-Repository von Benutzeranmeldeinformationen.
  
Authentifizierung bedeutet die Bereitstellung von Benutzeranmeldeinformationen für einen vertrauenswürdigen Server. Skype für Business Server verwendet die folgenden Authentifizierungsprotokolle – abhängig vom Status und Standort des Benutzers.
  
- **MIT Kerberos Version 5 Security-Protokoll** für interne Benutzer mit Active Directory-Anmeldeinformationen. Kerberos erfordert Clients eine Verbindung mit Active Directory-Domänendienste, weshalb sie verwendet werden, für die Authentifizierung von Clients außerhalb der Unternehmensfirewall befindet.
    
- **NTLM-Protokoll** für Benutzer mit Active Directory-Anmeldeinformationen, die über ein Endgerät von außerhalb der Unternehmensfirewall eine Verbindung herstellen. Der Zugriffs-edgedienst übergibt Anfragen zur Anmeldung an einen Director, falls vorhanden, oder ein Front-End-Server für die Authentifizierung. Der Zugriffs-edgedienst selbst führt keine Authentifizierung.
    
    > [!NOTE]
    > Da der Angriffsschutz des NTLM-Protokolls schwächer ist als der von Kerberos, minimieren einige Organisationen die Nutzung von NTLM. Daher unter Umständen zu internen Zugriff auf Skype für Business Server 2015 eingeschränkt oder Clients über eine VPN- oder DirectAccess Verbindung verbunden. 
  
- 
            Das **Digestprotokoll** für sogenannte anonyme Benutzer. Anonyme Benutzer sind externe Benutzer, die nicht über anerkannte Active Directory-Anmeldeinformationen verfügen, aber zu einer lokalen Konferenz eingeladen wurden und einen gültigen Konferenzschlüssel besitzen. Die Digestauthentifizierung wird nicht für andere Clientinteraktionen verwendet.
    
Skype für Business Server 2015 Authentifizierung besteht aus zwei Phasen:
  
1. Zwischen dem Client und dem Server wird eine Sicherheitszuordnung eingerichtet.
    
2. Client und Server verwenden die vorhandene Sicherheitszuordnung, um Nachrichten, die sie senden, zu signieren, und Nachrichten, die sie empfangen, zu überprüfen. Nicht authentifizierte Nachrichten von einem Client werden nicht akzeptiert, wenn die Authentifizierung auf dem Server aktiviert ist.
    
Die Benutzervertrauenswürdigkeit ist mit jeder Nachricht verbunden, die von einem Benutzer stammt, nicht mit der Benutzeridentität selbst. Der Server überprüft jede Nachricht auf gültige Benutzeranmeldeinformationen. Wenn die Benutzeranmeldeinformationen gültig sind, wird die Nachricht weder vom ersten Server, der sie empfängt, noch von allen anderen Servern in der vertrauenswürdigen Servercloud herausgefordert.
  
Benutzer mit gültigen Anmeldeinformationen, die von einem Verbundpartner ausgegeben wurden, sind vertrauenswürdig, erhalten aber optional aufgrund zusätzlicher Einschränkungen nicht sämtliche Berechtigungen, die internen Benutzern erteilt werden.
  
Die Protokolle ICE und TURN verwenden ebenfalls die Digestherausforderung, wie im IETF TURN RFC beschrieben.
  
Clientzertifikate stellen eine Alternative für Benutzer von Skype für Business Server 2015 authentifiziert werden. Benutzer haben statt einen Benutzernamen und ein Kennwort ein Zertifikat und den privaten Schlüssel für das Zertifikat, das eine Herausforderung kryptografische aufzulösende erforderlich ist. (Dieses Zertifikat benötigen eine Antragstellername oder alternativer Antragstellername identifiziert den Benutzer und muss von einer Stammzertifizierungsstelle, der von Servern mit Skype für Business Server 2015 vertraut ausgestellt werden, die innerhalb der Gültigkeitsdauer und nicht gesperrt.) Um authentifiziert werden, müssen Benutzer nur eine persönliche Identifikationsnummer (PIN) eingeben. Zertifikate sind besonders für Telefone, Mobiltelefone und andere Geräte, auf dem ist es schwierig, einen Benutzernamen und ein Kennwort einzugeben.
  

