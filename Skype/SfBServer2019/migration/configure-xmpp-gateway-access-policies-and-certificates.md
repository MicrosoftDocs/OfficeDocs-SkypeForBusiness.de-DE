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
ms.localizationpriority: medium
description: 'Der XMPP-Partnerverbund definiert eine externe Bereitstellung basierend auf dem XMPP-Protokoll (eXtensible Messaging and Presence Protocol). Eine XMPP-Konfiguration ermöglicht Benutzern den Zugriff auf XMPP-Domänenbenutzer durch:'
ms.openlocfilehash: c442d0c4f5b5443e378be5afc031f7489860e42a
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58594305"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a>Konfigurieren von Zugriffsrichtlinien und Zertifikaten für XMPP-Gateways

Der XMPP-Partnerverbund definiert eine externe Bereitstellung basierend auf dem XMPP-Protokoll (eXtensible Messaging and Presence Protocol). Eine XMPP-Konfiguration ermöglicht Benutzern den Zugriff auf XMPP-Domänenbenutzer durch:
  
- Chat und Anwesenheit – nur Von Person zu Person
    
- Erstellen von XMPP-Verbundkontakten im Skype for Business-Client
    
Wenn Sie Richtlinien für die Unterstützung von XMPP-Verbundpartnern konfigurieren, gelten die Richtlinien für Benutzer von XMPP-Verbunddomänen, aber nicht für Benutzer von SIP-Dienstanbietern (Session Initiation Protocol) oder SIP-Partnerverbunddomänen. Sie konfigurieren einen XMPP-Verbundpartner für jede XMPP-Verbunddomäne, mit der Sie Ihren Benutzern das Hinzufügen von Kontakten und die Kommunikation ermöglichen möchten. Wenn die Richtlinien vorhanden sind, müssen Sie die XMPP-Gatewayzertifikate konfigurieren. 
  
> [!NOTE]
> XMPP-Funktionen sind in Skype for Business Server 2019 veraltet, können aber auf einem Legacyserver in Koexistenz mit Skype for Business Server 2019 fortgesetzt werden. Stellen Sie sicher, dass Sie das Legacyserver-XMPP-Gateway (Skype for Business Server 2015/Lync Server 2013) bereits bereitgestellt und die Zugriffsrichtlinien so konfiguriert haben, dass Benutzer für ältere XMPP-Gateways aktiviert sind. Ausführliche Informationen finden Sie unter [Migrieren des XMPP-Partnerverbunds.](migrating-xmpp-federation.md) 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a>Konfigurieren einer Richtlinie für den externen Zugriff zum Aktivieren von Benutzern für ältere XMPP-Gateways

1. Öffnen Sie die Legacy-Skype for Business Server Systemsteuerung.
    
2. Klicken Sie in der linken Navigationsleiste auf **Partnerverbund und externer Zugriff**, und klicken Sie dann auf **Externe Zugriffsrichtlinie**.
    
3. Klicken Sie auf **Neu** und anschließend auf **Benutzerrichtlinie**.
    
4. Geben Sie einen Namen für die externe Benutzerzugriffsrichtlinie ein.
    
5. Geben Sie eine Beschreibung für die externe Benutzerzugriffsrichtlinie ein.
    
6. Wählen Sie **Kommunikation mit Partnerbenutzern aktivieren** aus.
    
7. Wählen Sie **Kommunikation mit XMPP-Partnerverbundbenutzern aktivieren** aus.
    
8. Klicken Sie auf **Commit ausführen**, um Ihre Änderungen am Standort oder an der Benutzerrichtlinie zu speichern. 
    

