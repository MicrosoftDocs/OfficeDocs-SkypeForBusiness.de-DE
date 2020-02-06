---
title: Planen der modernen Authentifizierung (Adal) mit Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: In diesem Artikel wird erläutert, welche moderne Authentifizierung (die auf der Active Directory Authentication Library (Adal) und OAuth 2,0) basiert.
ms.openlocfilehash: 239dd6a49ecbec043a661e622a66eb5cb4665e96
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815833"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>Wie Sie moderne Authentifizierung (ADAL) mit Skype for Business verwenden
 
Dieser Artikel enthält eine Einführung in die moderne Authentifizierung (basierend auf der Active Directory Authentication Library (Adal) und OAuth 2,0), die im kumulativen Update vom März 2016 für Skype for Business für Skype for Business Server 2015 oder von Initial gefunden werden kann. Release für Skype for Business Server 2019.
  
## <a name="what-is-adal"></a>Was ist ADAL?

ADAL ist das Akronym für „Active Directory Authentication Library“ und bildet gemeinsam mit OAuth 2.0 die Grundlage für die moderne Authentifizierung. Diese Codebibliothek dient dazu, sichere Ressourcen in Ihrem Verzeichnis für Clientanwendungen (wie Skype for Business) über Sicherheitstoken zur Verfügung zu stellen. ADAL arbeitet mit OAuth 2.0 zusammen, um mehr Szenarien für Authentifizierung und Autorisierung wie mehrstufige Authentifizierung (Multi-Factor Authentication, MFA) und weitere Formen der SAML-Authentifizierung zu ermöglichen.
  
Viele Apps, die als Clients fungieren, können moderne Authentifizierung zur Unterstützung des Zugriffs auf gesicherte Ressourcen nutzen. In Skype for Business Server wird diese Technologie zwischen lokalen Clients und lokalen Servern verwendet, um Benutzern eine geeignete Berechtigungsstufe für Ressourcen zu ermöglichen.
  
Unterhaltungen mit moderner Authentifizierung (die auf ADAL und OAuth 2.0 gründen), haben einige Gemeinsamkeiten.
  
- Es gibt einen Client, der eine Anfrage für eine Ressource macht, in diesem Fall ist der Client Skype for Business.
    
- Es gibt eine Ressource, für die der Client eine bestimmte Zugriffsebene benötigt, und diese Ressource wird durch einen Verzeichnisdienst gesichert, in diesem Fall die Ressource ist Skype for Business Server.
    
- Es gibt eine OAuth-Verbindung, also eine Verbindung, die für das *autorisieren* eines Benutzers für den Zugriff auf eine Ressource vorgesehen ist. (OAuth ist auch unter dem aussagekräftigeren Namen „Server-to-Server“ bekannt und wird deshalb häufig als S2S abgekürzt.)
    
In Adal-Unterhaltungen (Skype for Business Server modern Authentication) kommuniziert Skype for Business Server über ADFS (ADFS 3,0 in Windows Server 2012 R2). Die Authentifizierung kann über einen beliebigen anderen Identitätsanbieter (Identity Provider, IdP) erfolgen, aber Skype for Business Server muss für die direkte Kommunikation mit AD FS konfiguriert sein. Wenn Sie ADFS nicht für die Verwendung von Skype for Business Server konfiguriert haben, führen Sie die [ADFS-Installation](https://technet.microsoft.com/en-us/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx)aus.
  
Adal ist im kumulativen Update vom März 2016 für Skype for Business Server 2015 enthalten, und das kumulative Update vom März 2016 für Skype for Business **muss** installiert sein und für eine erfolgreiche Konfiguration benötigt werden. Für Skype for Business Server 2019 steht es ab der ersten Version des Produkts zur Verfügung.
  
> [!NOTE]
> Während der ersten Version wird die moderne Authentifizierung in einer lokalen Umgebung nur unterstützt, wenn keine gemischte Skype-Topologie involviert ist. Wenn es sich beispielsweise um eine reine Skype for Business Server-Umgebung handelt. Diese Erklärung kann Änderungen unterworfen sein. 
  
Ein PowerShell-Paket einschließlich .ps1-Dateien mit den von ADAL verwendeten Befehlen muss für eine erfolgreiche Konfiguration heruntergeladen werden.

Informationen zum Implementieren der modernen Authentifizierung in Skype for Business finden Sie unter: [Verwenden der modernen Authentifizierung (Adal) mit Skype for Business](../../manage/authentication/use-adal.md)
