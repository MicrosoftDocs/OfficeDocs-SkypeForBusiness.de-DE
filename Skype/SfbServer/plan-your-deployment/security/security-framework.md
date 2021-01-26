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
description: Dieser Abschnitt bietet eine Übersicht über die grundlegenden Elemente, die das Sicherheitsframework für Skype for Business Server bilden. Das Verständnis, wie diese Elemente zusammenarbeiten, ist wichtig, um fundierte Entscheidungen zur Sicherung Ihrer bestimmten Skype for Business Server-Bereitstellung zu treffen.
ms.openlocfilehash: 94d2ffac30e029ab6631557a69d6da3ec108657f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832095"
---
# <a name="security-framework-for-skype-for-business-server"></a>Sicherheitsframework für Skype for Business Server
 
Dieser Abschnitt bietet eine Übersicht über die grundlegenden Elemente, die das Sicherheitsframework für Skype for Business Server bilden. Das Verständnis, wie diese Elemente zusammenarbeiten, ist wichtig, um fundierte Entscheidungen zur Sicherung Ihrer bestimmten Skype for Business Server-Bereitstellung zu treffen.
  
Folgende Komponenten sind beteiligt:
  
- Die Active Directory-Domänendienste (AD DS) bieten ein zentrales vertrauenswürdiges Back-End-Repository für Benutzerkonten und Netzwerkressourcen.
    
- Role-Based Zugriffssteuerung (RBAC) ermöglicht ihnen das Delegieren von Verwaltungsaufgaben bei gleichzeitiger Aufrechterhaltung hoher Sicherheitsstandards.
    
- Public Key Infrastructure (PKI) verwendet Zertifikate, die von vertrauenswürdigen Zertifizierungsstellen ausgestellt wurden, um Server zu authentifizieren und die Datenintegrität sicherzustellen.
    
- TLS (Transport Layer Security), HTTPS über SSL (HTTPS) und MTLS (Mutual TLS) ermöglichen die Authentifizierung von Endgeräten und die Sofortnachrichtenverschlüsselung. Point-to-Point-Audio-, Video- und Anwendungsfreigabe-Datenströme werden mit dem Secure Real-Time Transport Protocol (SRTP) verschlüsselt.
    
- Standardprotokolle zur Authentifizierung von Benutzern, sofern möglich.
    
- Windows PowerShell-Sicherheitsfeatures, die standardmäßig aktiviert sind, sodass die Benutzer nicht auf einfache Weise oder unwissentlich Skripts ausführen können.
    
Diese grundlegenden Sicherheitselemente arbeiten zusammen, um vertrauenswürdige Benutzer, Server, Verbindungen und Vorgänge zu definieren, um eine sichere Grundlage für Skype for Business Server zu gewährleisten.
  
## <a name="in-this-section"></a>Inhalt dieses Abschnitts

In den Themen in diesem Abschnitt wird beschrieben, wie jedes dieser grundlegenden Elemente funktioniert, um die Sicherheit Ihrer Skype for Business Server-Infrastruktur zu verbessern.
  
- [Active Directory Domain Services for Skype for Business Server](active-directory-domain-services.md)
    
- [Rollenbasierte Zugriffssteuerung (RBAC) für Skype for Business Server](role-based-access-control-rbac.md)
    
- [Public Key Infrastructure for Skype for Business Server](public-key-infrastructure-for-skype.md)
    
- [TLS und MTLS für Skype for Business Server](tls-and-mtls.md)
    
- [Verschlüsselung für Skype for Business Server](encryption.md)
    
- [Benutzer- und Clientauthentifizierung für Skype for Business Server](user-and-client-authentication.md)
    
- [Windows PowerShell und Skype for Business Server-Verwaltungstools](management-tools.md)
    

