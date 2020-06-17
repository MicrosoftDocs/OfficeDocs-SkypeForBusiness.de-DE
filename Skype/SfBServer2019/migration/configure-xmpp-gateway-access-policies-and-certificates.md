---
title: Konfigurieren von Zugriffsrichtlinien und Zertifikaten für XMPP-Gateways
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Der XMPP-Partnerverbund definiert eine externe Bereitstellung basierend auf dem XMPP-Protokoll (eXtensible Messaging and Presence Protocol). Eine XMPP-Konfiguration ermöglicht Benutzern den Zugriff auf XMPP-Domänenbenutzer durch:'
ms.openlocfilehash: f94cd3bc0a769165f6ffe8ecabea8b7f48a1ff07
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753935"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a>Konfigurieren von Zugriffsrichtlinien und Zertifikaten für XMPP-Gateways

Der XMPP-Partnerverbund definiert eine externe Bereitstellung basierend auf dem XMPP-Protokoll (eXtensible Messaging and Presence Protocol). Eine XMPP-Konfiguration ermöglicht Benutzern den Zugriff auf XMPP-Domänenbenutzer durch:
  
- Chat und Anwesenheit – nur Person zu Person
    
- Erstellen von XMPP-verbundkontakten im Skype for Business-Client
    
Wenn Sie Richtlinien für die Unterstützung von XMPP-Verbundpartnern konfigurieren, gelten die Richtlinien für Benutzer von XMPP-Verbunddomänen, jedoch nicht für Benutzer von SIP-Chat (Session Initiation Protocol)-Dienstanbietern oder SIP-Verbunddomänen. Sie konfigurieren einen XMPP-Verbundpartner für jede XMPP-Verbunddomäne, die Sie Ihren Benutzern erlauben möchten, Kontakte hinzuzufügen und mit Ihnen zu kommunizieren. Wenn die Richtlinien vorhanden sind, müssen Sie die XMPP-Gatewayzertifikate konfigurieren. 
  
> [!NOTE]
> Die XMPP-Funktionalität ist in Skype for Business Server 2019 veraltet, kann aber in einem Legacy Server in Koexistenz mit Skype for Business Server 2019 fortgesetzt werden. Stellen Sie sicher, dass Sie das XMPP-Gateway für Legacy Server (Skype for Business Server 2015/lync Server 2013) bereits bereitgestellt haben, und konfigurieren Sie die Zugriffsrichtlinien, um Benutzer für das Vorgänger-XMPP-Gateway zu aktivieren. Ausführliche Informationen finden Sie unter [Migrating XMPP Federation](migrating-xmpp-federation.md). 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a>Konfigurieren einer Richtlinie für den externen Zugriff zur Aktivierung von Benutzern für das Vorgänger-XMPP-Gateway

1. Öffnen Sie die Legacy Skype for Business Server Systemsteuerung.
    
2. Klicken Sie in der linken Navigationsleiste auf **Partnerverbund und externer Zugriff**, und klicken Sie dann auf **Externe Zugriffsrichtlinie**.
    
3. Klicken Sie auf **Neu** und anschließend auf **Benutzerrichtlinie**.
    
4. Geben Sie einen Namen für die externe Benutzerzugriffsrichtlinie ein.
    
5. Geben Sie eine Beschreibung für die externe Benutzerzugriffsrichtlinie ein.
    
6. Wählen Sie **Kommunikation mit Partnerbenutzern aktivieren** aus.
    
7. Wählen Sie **Kommunikation mit XMPP-Partnerverbundbenutzern aktivieren** aus.
    
8. Klicken Sie auf **Commit ausführen**, um Ihre Änderungen am Standort oder an der Benutzerrichtlinie zu speichern. 
    

