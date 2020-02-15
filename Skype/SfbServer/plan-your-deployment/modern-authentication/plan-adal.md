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
description: In diesem Artikel wird erläutert, welche moderne Authentifizierung (basierend auf der Active Directory-Authentifizierungsbibliothek (Adal) und OAuth 2,0).
ms.openlocfilehash: 5a51b0712f33cbafc64f87f56b4d12649bfad97e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046288"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>Vorgehensweise verwenden der modernen Authentifizierung (Adal) mit Skype for Business
 
Dieser Artikel enthält eine Einführung in die moderne Authentifizierung (basierend auf der Active Directory-Authentifizierungsbibliothek (Adal) und OAuth 2,0), die im kumulativen März 2016-Update für Skype for Business für Skype for Business Server 2015 oder von der ersten Seite gefunden werden kann. Release für Skype for Business Server 2019.
  
## <a name="what-is-adal"></a>Was ist Adal?

Adal ist die Abkürzung für "Active Directory Authentication Library" und stellt zusammen mit OAuth 2,0 eine Untermauerung der modernen Authentifizierung dar. Diese Codebibliothek dient zum Bereitstellen gesicherter Ressourcen in Ihrem Verzeichnis für Clientanwendungen (wie Skype for Business) über Sicherheitstoken. Adal arbeitet mit OAuth 2,0 zusammen, um mehr Authentifizierungs-und Autorisierungs Szenarien wie mehrstufige Authentifizierung (Multi-Factor Authentication, MFA) und weitere Formen der SAML-Authentifizierung zu ermöglichen.
  
Eine Vielzahl von apps, die als Clients fungieren, können moderne Authentifizierung nutzen, um Hilfe bei der Bereitstellung sicherer Ressourcen zu erhalten. In Skype for Business Server wird diese Technologie zwischen lokalen Clients und lokalen Servern verwendet, um Benutzern eine ordnungsgemäße Autorisierung für Ressourcen zu ermöglichen.
  
Moderne Authentifizierungs Unterhaltungen (die auf Adal und OAuth 2,0 basieren) haben einige Elemente gemeinsam.
  
- Es gibt einen Client, der eine Anforderung für eine Ressource macht, in diesem Fall ist der Client Skype for Business.
    
- Es gibt eine Ressource, für die der Client eine bestimmte Zugriffsebene benötigt, und diese Ressource wird durch einen Verzeichnisdienst gesichert, in diesem Fall ist die Ressource Skype for Business Server.
    
- Es gibt eine OAuth-Verbindung, also eine Verbindung, die der *Autorisierung* eines Benutzers für den Zugriff auf eine Ressource gewidmet ist. (OAuth ist auch unter dem aussagekräftigeren Namen "Server-zu-Server-Authentifizierung" bekannt und wird häufig als S2S abgekürzt.)
    
In Skype for Business Server Unterhaltungen mit moderner Authentifizierung (Adal) kommuniziert Skype for Business Server über ADFS (ADFS 3,0 in Windows Server 2012 R2). Die Authentifizierung kann mit einem anderen Identitätsanbieter (IDP) erfolgen, aber Skype for Business Server muss für die direkte Kommunikation mit ADFS konfiguriert sein. Wenn Sie ADFS nicht für die Verwendung mit Skype for Business Server konfiguriert haben, schließen Sie die [ADFS-Installation](https://technet.microsoft.com/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx)ab.
  
Adal ist im kumulativen Update 2016 für Skype for Business Server 2015 enthalten, und das kumulative Update vom März 2016 für Skype for Business **muss** installiert sein und für eine erfolgreiche Konfiguration erforderlich sein. Für Skype for Business Server 2019 ist es ab der ersten Version des Produkts verfügbar.
  
> [!NOTE]
> Während der ersten Version wird die moderne Authentifizierung in einer lokalen Umgebung nur unterstützt, wenn keine gemischte Skype-Topologie beteiligt ist. Beispiel: Wenn die Umgebung rein Skype for Business Server ist. Diese Anweisung kann Änderungen unterworfen werden. 
  
Ein PowerShell-Paket einschließlich der PS1-Dateien mit den von Adal verwendeten Befehlen muss für eine erfolgreiche Konfiguration heruntergeladen werden.

Informationen zum Implementieren der modernen Authentifizierung in Skype for Business finden Sie unter: [How to use modern Authentication (Adal) with Skype for Business](../../manage/authentication/use-adal.md)
