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
description: In diesem Artikel wird erläutert, was die moderne Authentifizierung (die auf der Active Directory Authentication Library (ADAL) und OAuth 2.0 basiert) ist.
ms.openlocfilehash: bd5d172fe4589cbd28c5b22507ad8603695ed62f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816225"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>Verwenden der modernen Authentifizierung (ADAL) mit Skype for Business
 
In diesem Artikel wird die moderne Authentifizierung (basierend auf der Active Directory Authentication Library (ADAL) und OAuth 2.0) erläutert, die im kumulativen März 2016-Update für Skype for Business für Skype for Business Server 2015 oder in der ersten Version für Skype for Business Server 2019 zu finden ist.
  
## <a name="what-is-adal"></a>Was ist ADAL?

ADAL ist das Akronym für die "Active Directory-Authentifizierungsbibliothek" und ist zusammen mit OAuth 2.0 eine Grundlage für die moderne Authentifizierung. Diese Codebibliothek wurde entwickelt, um gesicherte Ressourcen in Ihrem Verzeichnis clientanwendungen (wie Skype for Business) über Sicherheitstoken zur Verfügung zu stellen. ADAL arbeitet mit OAuth 2.0 zusammen, um weitere Authentifizierungs- und Autorisierungsszenarien wie die mehrstufige Authentifizierung (Multi-Factor Authentication, MFA) und mehr Formen der SAML-Authentifizierung zu ermöglichen.
  
Eine Vielzahl von Apps, die als Clients fungieren, können die moderne Authentifizierung nutzen, um zu sicheren Ressourcen zu wechseln. In Skype for Business Server wird diese Technologie zwischen lokalen Clients und lokalen Servern verwendet, um Benutzern eine angemessene Autorisierungsstufe für Ressourcen zu ermöglichen.
  
Unterhaltungen mit moderner Authentifizierung (die auf ADAL und OAuth 2.0 basieren) haben einige Elemente gemeinsam.
  
- Es gibt einen Client, der eine Anforderung für eine Ressource macht, in diesem Fall ist der Client Skype for Business.
    
- Es gibt eine Ressource, für die der Client eine bestimmte Zugriffsebene benötigt, und diese Ressource wird durch einen Verzeichnisdienst gesichert, in diesem Fall ist die Ressource Skype for Business Server.
    
- Es gibt eine OAuth-Verbindung, mit anderen Worten, eine Verbindung, die der Autorisierung eines Benutzers für den Zugriff auf eine Ressource zugeordnet ist.  (OAuth wird auch unter dem aussagekräftigen Namen "Server-zu-Server"-Authentifizierung bezeichnet und häufig als S2S abgekürzt.)
    
In Skype for Business Server Modern Authentication (ADAL)-Unterhaltungen kommuniziert Skype for Business Server über ADFS (ADFS 3.0 in Windows Server 2012 R2). Die Authentifizierung kann mit einem anderen Identitätsanbieter (IdP) ausgeführt werden, skype for Business server muss jedoch für die direkte Kommunikation mit ADFS konfiguriert werden. Wenn Sie ADFS nicht für die Zusammenarbeit mit Skype for Business Server konfiguriert haben, schließen Sie die [ADFS-Installation ab.](https://technet.microsoft.com/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx)
  
ADAL ist im kumulativen März 2016-Update für Skype for Business Server 2015 enthalten, und das kumulative März 2016-Update für Skype for **Business** muss installiert sein und ist für eine erfolgreiche Konfiguration erforderlich. Für Skype for Business Server 2019 ist es ab der ersten Produktversion verfügbar.
  
> [!NOTE]
> Während der ersten Version wird die moderne Authentifizierung in einer lokalen Umgebung nur unterstützt, wenn keine gemischte Skype-Topologie beteiligt ist. Beispiel: Die Umgebung ist rein skype for Business Server. Diese Anweisung kann geändert werden. 
  
Für eine erfolgreiche Konfiguration muss ein PowerShell-Paket mit PS1-Dateien mit den von ADAL verwendeten Befehlen heruntergeladen werden.

Informationen zum Implementieren der modernen Authentifizierung in Skype for Business finden Sie unter: Verwenden der modernen [Authentifizierung (ADAL) mit Skype for Business](../../manage/authentication/use-adal.md)
