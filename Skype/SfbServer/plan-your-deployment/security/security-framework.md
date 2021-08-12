---
title: Sicherheitsframework für Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 01131e28-b38e-40d9-8524-06725b9c6608
description: Dieser Abschnitt bietet eine Übersicht über die grundlegenden Elemente, die das Sicherheitsframework für Skype for Business Server bilden. Das Verständnis, wie diese Elemente zusammenarbeiten, ist wichtig, um fundierte Entscheidungen zum Sichern Ihrer bestimmten Skype for Business Server Bereitstellung zu treffen.
ms.openlocfilehash: a0f6513f86d7416f546c6a744fc1b40df7c7137a18dae5d76fcf18166a4f2eb1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54337713"
---
# <a name="security-framework-for-skype-for-business-server"></a>Sicherheitsframework für Skype for Business Server
 
Dieser Abschnitt bietet eine Übersicht über die grundlegenden Elemente, die das Sicherheitsframework für Skype for Business Server bilden. Das Verständnis, wie diese Elemente zusammenarbeiten, ist wichtig, um fundierte Entscheidungen zum Sichern Ihrer bestimmten Skype for Business Server Bereitstellung zu treffen.
  
Folgende Komponenten sind beteiligt:
  
- Die Active Directory-Domänendienste (AD DS) bieten ein zentrales vertrauenswürdiges Back-End-Repository für Benutzerkonten und Netzwerkressourcen.
    
- Role-Based Zugriffssteuerung (Access Control, RBAC) können Sie administrative Aufgaben delegieren und gleichzeitig hohe Sicherheitsstandards beibehalten.
    
- Public Key Infrastructure (PKI) verwendet Zertifikate, die von vertrauenswürdigen Zertifizierungsstellen (CAs) ausgestellt wurden, um Server zu authentifizieren und die Datenintegrität sicherzustellen.
    
- TLS (Transport Layer Security), HTTPS über SSL (HTTPS) und MTLS (Mutual TLS) ermöglichen die Authentifizierung von Endgeräten und die Sofortnachrichtenverschlüsselung. Point-to-Point-Audio-, Video- und Anwendungsfreigabe-Datenströme werden mit dem Secure Real-Time Transport Protocol (SRTP) verschlüsselt.
    
- Standardprotokolle zur Authentifizierung von Benutzern, sofern möglich.
    
- Windows PowerShell-Sicherheitsfeatures, die standardmäßig aktiviert sind, sodass die Benutzer nicht auf einfache Weise oder unwissentlich Skripts ausführen können.
    
Diese grundlegenden Sicherheitselemente arbeiten zusammen, um vertrauenswürdige Benutzer, Server, Verbindungen und Vorgänge zu definieren, um eine sichere Grundlage für Skype for Business Server zu gewährleisten.
  
## <a name="in-this-section"></a>Inhalt dieses Abschnitts

In den Themen in diesem Abschnitt wird beschrieben, wie jedes dieser grundlegenden Elemente funktioniert, um die Sicherheit Ihrer Skype for Business Server-Infrastruktur zu verbessern.
  
- [Active Directory-Domänendienste für Skype for Business Server](active-directory-domain-services.md)
    
- [Rollenbasierte Zugriffssteuerung (RBAC) für Skype for Business Server](role-based-access-control-rbac.md)
    
- [Public Key-Infrastruktur für Skype for Business Server](public-key-infrastructure-for-skype.md)
    
- [TLS und MTLS für Skype for Business Server](tls-and-mtls.md)
    
- [Verschlüsselung für Skype for Business Server](encryption.md)
    
- [Benutzer- und Clientauthentifizierung für Skype for Business Server](user-and-client-authentication.md)
    
- [Verwaltungstools für Windows PowerShell und Skype for Business Server](management-tools.md)
    

