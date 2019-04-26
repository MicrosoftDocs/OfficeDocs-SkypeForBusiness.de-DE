---
title: Konfigurieren von Zugriffsrichtlinien und Zertifikaten für XMPP-Gateways
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'XMPP-Verbund definiert eine externe Bereitstellung auf Grundlage von eXtensible Messaging and Presence Protocol (XMPP). XMPP-Konfiguration ermöglicht Benutzern den Zugriff auf XMPP-Domänenbenutzern anhand folgender Kriterien:'
ms.openlocfilehash: 65ef8904660eaa75ddd10238a6561ea91b9f7278
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32238661"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a>Konfigurieren von Zugriffsrichtlinien und Zertifikaten für XMPP-Gateways

XMPP-Verbund definiert eine externe Bereitstellung auf Grundlage von eXtensible Messaging and Presence Protocol (XMPP). XMPP-Konfiguration ermöglicht Benutzern den Zugriff auf XMPP-Domänenbenutzern anhand folgender Kriterien:
  
- Sofortnachrichten und Anwesenheit – nur zwischen Personen
    
- Erstellung von XMPP-Verbundkontakten auf die Skype für Business-client
    
Beim Konfigurieren von Richtlinien für die Unterstützung von XMPP-Verbundpartner, die Richtlinien gelten für Benutzer von XMPP federated Domänen, aber nicht für Benutzer von Session Initiation-Protokoll (SIP) instant messaging (IM) Service Provider oder SIP verbunddomänen. Konfigurieren Sie eine XMPP-Verbundpartner für jede federated XMPP-Domäne, die Sie Ihre Benutzer die Kontakte hinzufügen und die Kommunikation mit zulassen möchten. Nachdem die Richtlinien vorhanden sind, müssen Sie die Zertifikate XMPP-Gateway zu konfigurieren. 
  
> [!NOTE]
> XMPP-Funktionen ist in Skype für Business Server 2019 veraltet, sondern in einen Legacyserver zusammen mit Skype für Business Server 2019 fortgeführt werden kann. Stellen Sie sicher, dass den Server der Vorversionen bereits bereitgestellt haben (Skype für Business Server 2015 / Lync Server 2013) XMPP-Gateway und Richtlinien für den Zugriff zum Aktivieren von Benutzern für legacy XMPP-Gateway konfiguriert. Weitere Informationen hierzu finden Sie unter [Migrieren von XMPP-Verbund](migrating-xmpp-federation.md). 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a>Konfigurieren einer Richtlinie für externen Zugriff zum Aktivieren von Benutzern für legacy-XMPP-Gateway

1. Öffnen Sie die Vorversion Skype Business Server-Systemsteuerung.
    
2. Klicken Sie in der linken Navigationsleiste auf **Partnerverbund und externer Zugriff**und klicken Sie dann auf **Richtlinie für den externen Zugriff**.
    
3. Klicken Sie auf **Neu** und anschließend auf **Benutzerrichtlinie**.
    
4. Geben Sie einen Namen für die externe benutzerzugriffsrichtlinie ein.
    
5. Geben Sie eine Beschreibung für die externe benutzerzugriffsrichtlinie ein.
    
6. Wählen Sie **Kommunikation mit Partnerbenutzern aktivieren**.
    
7. Wählen Sie **Kommunikation mit XMPP partnerverbundbenutzern aktivieren**aus.
    
8. Klicken Sie auf **Commit** , um Ihre Änderungen an der Standort- oder Benutzerrichtlinie zu speichern. 
    

