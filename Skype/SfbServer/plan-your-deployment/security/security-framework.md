---
title: Sicherheitsframework für Skype für Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 01131e28-b38e-40d9-8524-06725b9c6608
description: Dieser Abschnitt enthält eine Übersicht über die grundlegenden Elemente, die das Sicherheitsframework für Skype für Business Server bilden. Grundlegendes zur Funktionsweise dieser Elemente zusammen ist entscheidend, um fundierte Entscheidungen zum Sichern Ihrer bestimmten Skype für Business Server-Bereitstellung.
ms.openlocfilehash: 487b3ea7f57c1a008327be2b9b31664a160e8425
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20983616"
---
# <a name="security-framework-for-skype-for-business-server"></a>Sicherheitsframework für Skype für Business Server
 
Dieser Abschnitt enthält eine Übersicht über die grundlegenden Elemente, die das Sicherheitsframework für Skype für Business Server bilden. Grundlegendes zur Funktionsweise dieser Elemente zusammen ist entscheidend, um fundierte Entscheidungen zum Sichern Ihrer bestimmten Skype für Business Server-Bereitstellung.
  
Es handelt sich um die folgenden Elemente:
  
- Active Directory-Domänendienste (AD DS) stellt ein einzelnes vertrauenswürdiges Back-End-Repository für Benutzerkonten und Netzwerkressourcen.
    
- Die rollenbasierte Zugriffskontrolle (RBAC) ermöglicht die Delegation administrativer Aufgaben bei gleichzeitiger Aufrechterhaltung von hohen Sicherheitsstandards.
    
- Die Public Key-Infrastruktur (PKI) verwendet von vertrauenswürdigen Zertifizierungsstellen ausgestellte Zertifikate, um Server zu authentifizieren und die Datenintegrität zu sichern.
    
- Transport Layer Security (TLS), HTTPS über SSL (HTTPS) und Mutual TLS (MTLS) ermöglichen die Endpunktauthentifizierung und IM-Verschlüsselung. Punkt-zu-Punkt-Audio-, Video- und Anwendungsfreigabestreams werden über SRTP (Secure Real-Time Transport Protocol) verschlüsselt.
    
- Branchenstandardprotokolle für die Benutzerauthentifizierung, falls möglich.
    
- Windows PowerShell-Sicherheitsfeatures, die standardmäßig aktiviert sind, sodass Benutzer auf einfache Weise oder unwissentlich Skripts ausführen können.
    
Diese grundlegenden Sicherheitskomponenten arbeiten zusammen, um vertrauenswürdige Benutzer, Server, Verbindungen und Vorgänge, um ein sicheres Fundament für Skype für Business Server sicherzustellen definieren.
  
## <a name="in-this-section"></a>Inhalt dieses Abschnitts

In den Themen in diesem Abschnitt wird beschrieben, wie der einzelnen Grundkomponenten zur Verbesserung der Sicherheit von Ihrer Skype für Business Server-Infrastruktur funktioniert.
  
- [Active Directory-Domänendienste für Skype für Business Server](active-directory-domain-services.md)
    
- [Rollenbasierte Zugriffssteuerung (RBAC) für Skype für Business Server](role-based-access-control-rbac.md)
    
- [Public Key-Infrastruktur für Skype für Business Server](public-key-infrastructure-for-skype.md)
    
- [TLS und MTLS für Skype für Business Server](tls-and-mtls.md)
    
- [Verschlüsselung für Skype für Business Server](encryption.md)
    
- [Benutzer- und Client für die Authentifizierung Skype Business Server](user-and-client-authentication.md)
    
- [Windows PowerShell und Skype für Business Server-Verwaltungstools](management-tools.md)
    

