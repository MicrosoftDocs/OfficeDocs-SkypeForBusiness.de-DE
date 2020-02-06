---
title: Konfigurieren von Zugriffsrichtlinien und Zertifikaten für XMPP-Gateways
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Die XMPP-Föderation definiert eine externe Bereitstellung, die auf dem Extensible Messaging and Presence Protocol (XMPP) basiert. Eine XMPP-Konfiguration ermöglicht Benutzern den Zugriff auf XMPP-Domänenbenutzer durch:'
ms.openlocfilehash: 8182153bf3633b2392969f5870a7d5b96471d4fb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813763"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a>Konfigurieren von Zugriffsrichtlinien und Zertifikaten für XMPP-Gateways

Die XMPP-Föderation definiert eine externe Bereitstellung, die auf dem Extensible Messaging and Presence Protocol (XMPP) basiert. Eine XMPP-Konfiguration ermöglicht Benutzern den Zugriff auf XMPP-Domänenbenutzer durch:
  
- Chat und Anwesenheit – nur für Personen
    
- Erstellen von XMPP-verbundkontakten im Skype for Business-Client
    
Wenn Sie Richtlinien für die Unterstützung von XMPP-Verbundpartnern konfigurieren, gelten die Richtlinien für Benutzer von XMPP-Verbunddomänen, nicht aber für Benutzer von SIP-Chat Diensten (Session Initiation Protocol) oder SIP-Verbunddomänen. Sie konfigurieren einen XMPP-Verbundpartner für jede XMPP-Verbunddomäne, die es Ihren Benutzern ermöglichen soll, Kontakte hinzuzufügen und mit Ihnen zu kommunizieren. Sobald die Richtlinien vorhanden sind, müssen Sie die XMPP-Gateway-Zertifikate konfigurieren. 
  
> [!NOTE]
> Die XMPP-Funktionalität ist in Skype for Business Server 2019 veraltet, kann aber auf einem Legacy Server in Koexistenz mit Skype for Business Server 2019 fortgesetzt werden. Stellen Sie sicher, dass Sie bereits den Legacy Server (Skype for Business Server 2015/lync Server 2013) XMPP-Gateway bereitgestellt haben und die Zugriffsrichtlinien so konfiguriert haben, dass Benutzer für Legacy-XMPP-Gateways aktiviert werden. Ausführliche Informationen finden Sie unter [Migrieren von XMPP-Föderationen](migrating-xmpp-federation.md). 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a>Konfigurieren einer Richtlinie für den externen Zugriff zum Aktivieren von Benutzern für Legacy-XMPP-Gateways

1. Öffnen Sie das Legacy-Control Panel für Skype for Business Server.
    
2. Klicken Sie in der linken Navigationsleiste auf **Föderation und externer Zugriff**, und klicken Sie dann auf **Richtlinie für den externen Zugriff**.
    
3. Klicken Sie auf **Neu** und anschließend auf **Benutzerrichtlinie**.
    
4. Geben Sie einen Namen für die Benutzerrichtlinie für den externen Zugriff ein.
    
5. Geben Sie eine Beschreibung für die Benutzerrichtlinie für den externen Zugriff an.
    
6. Wählen Sie **Kommunikation mit Verbundbenutzern aktivieren**aus.
    
7. Wählen Sie **Kommunikation mit XMPP-Verbundbenutzern aktivieren**aus.
    
8. Klicken Sie auf **Commit** , um Ihre Änderungen an der Website-oder Benutzerrichtlinie zu speichern. 
    

