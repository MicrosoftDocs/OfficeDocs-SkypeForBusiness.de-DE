---
title: Planen der modernen Authentifizierung (ADAL) mit Skype für Unternehmen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: In diesem Artikel wird erklärt, was modernen Authentifizierung (die auf dem Active Directory-Authentifizierung Library (ADAL) und OAuth 2.0 basiert) ist.
ms.openlocfilehash: 666808134e2ed178a85058a6e3cd3019bf982a35
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907192"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>Wie Sie moderne Authentifizierung (ADAL) mit Skype for Business verwenden
 
In diesem Artikel wird die modernen Authentifizierung (die auf dem Active Directory-Authentifizierung Library (ADAL) und OAuth 2.0 basiert), die in der März 2016 nachlesen können kumulative Update für Skype für Unternehmen für Skype für Business Server 2015 oder aus Initial die Version für Skype für Business Server 2019.
  
## <a name="what-is-adal"></a>Was ist ADAL?

ADAL ist das Akronym für „Active Directory Authentication Library“ und bildet gemeinsam mit OAuth 2.0 die Grundlage für die moderne Authentifizierung. In dieser Codebibliothek dient zum gesicherte Ressourcen in Ihrem Verzeichnis Clientanwendungen (wie Skype für Unternehmen) über Sicherheitstoken zur Verfügung zu stellen. ADAL arbeitet mit OAuth 2.0 zusammen, um mehr Szenarien für Authentifizierung und Autorisierung wie mehrstufige Authentifizierung (Multi-Factor Authentication, MFA) und weitere Formen der SAML-Authentifizierung zu ermöglichen.
  
Viele Apps, die als Clients fungieren, können moderne Authentifizierung zur Unterstützung des Zugriffs auf gesicherte Ressourcen nutzen. In Skype für Business Server wird diese Technologie zwischen lokalen Clients und Servern verwendet, um Benutzern eine ordnungsgemäße Ebene der Autorisierung auf Ressourcen bieten.
  
Unterhaltungen mit moderner Authentifizierung (die auf ADAL und OAuth 2.0 gründen), haben einige Gemeinsamkeiten.
  
- Ein Client, eine Anforderung für eine Ressource vorhanden ist, der Client ist in diesem Fall Skype für Unternehmen.
    
- Es ist eine Ressource, zu der der Client eine bestimmte Zugriffsebene, benötigt, und diese Ressource wird durch einen Verzeichnisdienst gesichert, die Ressource ist in diesem Fall Skype für Business Server.
    
- Besteht eine OAuth-Verbindung mit anderen Worten, eine Verbindung, die einen Benutzer Zugriff auf eine Ressource für das *Autorisieren* dediziert. (OAuth ist auch unter dem aussagekräftigeren Namen „Server-to-Server“ bekannt und wird deshalb häufig als S2S abgekürzt.)
    
Skype für Business Server modernen Authentifizierung (ADAL) Unterhaltungen kommuniziert Skype für Business Server über AD FS (AD FS 3.0 in Windows Server 2012 R2). Die Authentifizierung kann über einen beliebigen anderen Identitätsanbieter (Identity Provider, IdP) erfolgen, aber Skype for Business Server muss für die direkte Kommunikation mit AD FS konfiguriert sein. Wenn Sie ADFS zur Arbeit mit Skype für Business Server konfiguriert haben füllen Sie die [AD FS-Installation](https://technet.microsoft.com/en-us/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx).
  
ADAL ist in der März 2016 enthalten kumulative Update für Skype für Business Server 2015 und die März 2016 kumulative Update für Skype für Business **muss** installiert werden und für die erfolgreiche Konfiguration erforderlich ist. Skype für Business Server 2019 ist es von der ersten Version des Produkts zur Verfügung.
  
> [!NOTE]
> Während der Erstveröffentlichung ist moderne Authentifizierung in einer lokalen Umgebung nur unterstützt, wenn es keine gemischter Skype-Topologie ist. Wenn beispielsweise die Umgebung rein Skype für Business Server befindet. Mit dieser Anweisung möglicherweise kann geändert werden. 
  
Ein PowerShell-Paket einschließlich .ps1-Dateien mit den von ADAL verwendeten Befehlen muss für eine erfolgreiche Konfiguration heruntergeladen werden.

Informationen zum Implementieren modernen Authentifizierung in Skype für Unternehmen, verweisen Sie auf: [wie Sie modernen Authentifizierung (ADAL) mit Skype für Unternehmen](../../manage/authentication/use-adal.md)
