---
title: Sicherheitsframework für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 01131e28-b38e-40d9-8524-06725b9c6608
description: Dieser Abschnitt enthält eine Übersicht über die grundlegenden Elemente, die das Sicherheitsframework für Skype for Business Server bilden. Wenn Sie wissen möchten, wie diese Elemente zusammenarbeiten, ist es wichtig, fundierte Entscheidungen über die Sicherung ihrer speziellen Skype for Business Server-Bereitstellung zu treffen.
ms.openlocfilehash: 8b82b09a8220139abe62ac4503ad8a7eddc28e99
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296875"
---
# <a name="security-framework-for-skype-for-business-server"></a>Sicherheitsframework für Skype for Business Server
 
Dieser Abschnitt enthält eine Übersicht über die grundlegenden Elemente, die das Sicherheitsframework für Skype for Business Server bilden. Wenn Sie wissen möchten, wie diese Elemente zusammenarbeiten, ist es wichtig, fundierte Entscheidungen über die Sicherung ihrer speziellen Skype for Business Server-Bereitstellung zu treffen.
  
Es handelt sich um die folgenden Elemente:
  
- Active Directory-Domänendienste (AD DS) bietet ein einzelnes vertrauenswürdiges Back-End-Repository für Benutzerkonten und Netzwerkressourcen.
    
- Die rollenbasierte Zugriffskontrolle (RBAC) ermöglicht die Delegation administrativer Aufgaben bei gleichzeitiger Aufrechterhaltung von hohen Sicherheitsstandards.
    
- Die Public Key-Infrastruktur (PKI) verwendet von vertrauenswürdigen Zertifizierungsstellen ausgestellte Zertifikate, um Server zu authentifizieren und die Datenintegrität zu sichern.
    
- Transport Layer Security (TLS), HTTPS über SSL (HTTPS) und Mutual TLS (MTLS) ermöglichen die Endpunktauthentifizierung und IM-Verschlüsselung. Punkt-zu-Punkt-Audio-, Video- und Anwendungsfreigabestreams werden über SRTP (Secure Real-Time Transport Protocol) verschlüsselt.
    
- Branchenstandardprotokolle für die Benutzerauthentifizierung, falls möglich.
    
- Windows PowerShell bietet Sicherheitsfeatures, die standardmäßig aktiviert sind, sodass Benutzer keine einfachen oder unwissentlichen Skripts ausführen können.
    
Diese grundlegenden Sicherheitselemente arbeiten zusammen, um vertrauenswürdige Benutzer, Server, Verbindungen und Vorgänge zu definieren, um sicherzustellen, dass ein sicheres Fundament für Skype for Business Server besteht.
  
## <a name="in-this-section"></a>Inhalt dieses Abschnitts

In den Themen in diesem Abschnitt wird beschrieben, wie jedes dieser grundlegenden Elemente funktioniert, um die Sicherheit Ihrer Skype for Business Server-Infrastruktur zu verbessern.
  
- [Active Directory-Domänendienste für Skype for Business Server](active-directory-domain-services.md)
    
- [Rollenbasierte Zugriffssteuerung (RBAC) für Skype for Business Server](role-based-access-control-rbac.md)
    
- [Infrastruktur öffentlicher Schlüssel für Skype for Business Server](public-key-infrastructure-for-skype.md)
    
- [TLS und MTLS für Skype for Business Server](tls-and-mtls.md)
    
- [Verschlüsselung für Skype for Business Server](encryption.md)
    
- [Benutzer-und Clientauthentifizierung für Skype for Business Server](user-and-client-authentication.md)
    
- [Windows PowerShell und Skype for Business Server-Verwaltungstools](management-tools.md)
    

