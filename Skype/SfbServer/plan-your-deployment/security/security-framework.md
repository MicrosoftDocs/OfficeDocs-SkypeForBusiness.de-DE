---
title: Sicherheitsframework für Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 01131e28-b38e-40d9-8524-06725b9c6608
description: Dieser Abschnitt enthält eine Übersicht über die grundlegenden Elemente, die das Sicherheitsframework für Skype für Business Server 2015 bilden. Grundlegendes zur Funktionsweise dieser Elemente zusammen ist vornehmen, fundierte Entscheidungen zum Sichern Ihrer bestimmten Skype für Business Server 2015 Bereitstellung entscheidend.
ms.openlocfilehash: c29941a3e903b6318db2de0453589b5017e6f51b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="security-framework-for-skype-for-business-server-2015"></a>Sicherheitsframework für Skype for Business Server 2015
 
Dieser Abschnitt enthält eine Übersicht über die grundlegenden Elemente, die das Sicherheitsframework für Skype für Business Server 2015 bilden. Grundlegendes zur Funktionsweise dieser Elemente zusammen ist vornehmen, fundierte Entscheidungen zum Sichern Ihrer bestimmten Skype für Business Server 2015 Bereitstellung entscheidend.
  
Es handelt sich um die folgenden Elemente:
  
- Active Directory-Domänendienste (AD DS) stellt ein einzelnes vertrauenswürdiges Back-End-Repository für Benutzerkonten und Netzwerkressourcen.
    
- Die rollenbasierte Zugriffskontrolle (RBAC) ermöglicht die Delegation administrativer Aufgaben bei gleichzeitiger Aufrechterhaltung von hohen Sicherheitsstandards.
    
- Die Public Key-Infrastruktur (PKI) verwendet von vertrauenswürdigen Zertifizierungsstellen ausgestellte Zertifikate, um Server zu authentifizieren und die Datenintegrität zu sichern.
    
- Transport Layer Security (TLS), HTTPS über SSL (HTTPS) und Mutual TLS (MTLS) ermöglichen die Endpunktauthentifizierung und IM-Verschlüsselung. Punkt-zu-Punkt-Audio-, Video- und Anwendungsfreigabestreams werden über SRTP (Secure Real-Time Transport Protocol) verschlüsselt.
    
- Branchenstandardprotokolle für die Benutzerauthentifizierung, falls möglich.
    
- Windows PowerShell-Sicherheitsfeatures, die standardmäßig aktiviert sind, sodass Benutzer auf einfache Weise oder unwissentlich Skripts ausführen können.
    
Diese grundlegenden Sicherheitskomponenten arbeiten zusammen, um vertrauenswürdige Benutzer, Server, Verbindungen und Vorgänge, um ein sicheres Fundament für Skype für Business Server 2015 sicherzustellen definieren.
  
## <a name="in-this-section"></a>Inhalt dieses Abschnitts

In den Themen in diesem Abschnitt wird beschrieben, wie der einzelnen Grundkomponenten zur Verbesserung der Sicherheit von Ihrer Skype für Business Server-Infrastruktur funktioniert.
  
- [Active Directory-Domänendienste für Skype für Business Server 2015](active-directory-domain-services.md)
    
- [Rollenbasierte Zugriffssteuerung (RBAC) für Skype für Business Server 2015](role-based-access-control-rbac.md)
    
- [Public Key-Infrastruktur für Skype für Business Server 2015](public-key-infrastructure-for-skype.md)
    
- [TLS und MTLS für Skype für Business Server 2015](tls-and-mtls.md)
    
- [Verschlüsselung für Skype für Business Server 2015](encryption.md)
    
- [Benutzer- und Client für die Authentifizierung Skype Business Server 2015](user-and-client-authentication.md)
    
- [Windows PowerShell und Skype für Business Server 2015-Verwaltungstools](management-tools.md)
    

