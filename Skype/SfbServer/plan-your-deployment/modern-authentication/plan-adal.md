---
title: Planen der modernen Authentifizierung (ADAL) mit Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: In diesem Artikel wird erläutert, was die moderne Authentifizierung (basierend auf der Active Directory Authentication Library (ADAL) und OAuth 2.0 ist.
ms.openlocfilehash: 1df07491881b90efc16c97e7cd5cec0953cfb346
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096611"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>Verwenden der modernen Authentifizierung (ADAL) mit Skype for Business
 
In diesem Artikel wird die moderne Authentifizierung (basierend auf der Active Directory Authentication Library (ADAL) und OAuth 2.0) erläutert, die im kumulativen Update für Skype for Business für Skype for Business Server 2015 vom März 2016 oder in der ersten Version für Skype for Business Server 2019 zu finden ist.
  
## <a name="what-is-adal"></a>Was ist ADAL?

ADAL ist das Akronym für die Active Directory-Authentifizierungsbibliothek und ist zusammen mit OAuth 2.0 eine Grundlage der modernen Authentifizierung. Diese Codebibliothek dient dazu, gesicherte Ressourcen in Ihrem Verzeichnis clientanwendungen (z. B. Skype for Business) über Sicherheitstoken zur Verfügung zu stellen. ADAL arbeitet mit OAuth 2.0 zusammen, um mehr Authentifizierungs- und Autorisierungsszenarien wie mehrstufige Authentifizierung (Multi-Factor Authentication, MFA) und weitere Formen von SAML Auth zu ermöglichen.
  
Eine Vielzahl von Apps, die als Clients fungieren, können die moderne Authentifizierung nutzen, um hilfe beim Abrufen gesicherter Ressourcen zu helfen. In Skype for Business Server wird diese Technologie zwischen lokalen Clients und lokalen Servern verwendet, um Benutzern eine ordnungsgemäße Autorisierungsebene für Ressourcen zu ermöglichen.
  
Moderne Authentifizierungsunterhaltungen (die auf ADAL und OAuth 2.0 basieren) haben einige Elemente gemeinsam.
  
- Es gibt einen Client, der eine Anforderung für eine Ressource einreicht, in diesem Fall ist der Client Skype for Business.
    
- Es gibt eine Ressource, für die der Client eine bestimmte Zugriffsebene benötigt, und diese Ressource wird durch einen Verzeichnisdienst gesichert, in diesem Fall ist die Ressource Skype for Business Server.
    
- Es gibt eine OAuth-Verbindung, d. h.  eine Verbindung, die dem Autorisieren eines Benutzers für den Zugriff auf eine Ressource gewidmet ist. (OAuth wird auch durch den aussagekräftigen Namen "Server-zu-Server"-Authentifizierung bezeichnet und wird häufig als S2S abgekürzt.)
    
In Skype for Business Server Modern Authentication (ADAL)-Unterhaltungen kommuniziert Skype for Business Server über ADFS (ADFS 3.0 in Windows Server 2012 R2). Die Authentifizierung kann mit einem anderen Identitätsanbieter (IdP) ausgeführt werden, aber der Skype for Business-Server muss für die direkte Kommunikation mit ADFS konfiguriert werden. Wenn Sie ADFS nicht für die Arbeit mit Skype for Business Server konfiguriert haben, schließen Sie die [ADFS-Installation ab.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd727938(v=ws.10))
  
ADAL ist im kumulativen Update für Skype for Business Server 2015 vom März 2016 enthalten, und das kumulative Update für Skype for **Business** vom März 2016 muss installiert sein und ist für eine erfolgreiche Konfiguration erforderlich. Für Skype for Business Server 2019 ist es ab der ersten Version des Produkts verfügbar.
  
> [!NOTE]
> Während der ersten Version wird die moderne Authentifizierung in einer lokalen Umgebung nur unterstützt, wenn keine gemischte Skype-Topologie beteiligt ist. Wenn die Umgebung z. B. rein skype for Business Server ist. Diese Anweisung kann geändert werden. 
  
Ein PowerShell-Paket mit PS1-Dateien mit den von ADAL verwendeten Befehlen muss für eine erfolgreiche Konfiguration heruntergeladen werden.

Informationen zum Implementieren der modernen Authentifizierung in Skype for Business finden Sie unter: Verwenden der modernen Authentifizierung [(ADAL) mit Skype for Business](/microsoft-365/enterprise/hybrid-modern-auth-overview)