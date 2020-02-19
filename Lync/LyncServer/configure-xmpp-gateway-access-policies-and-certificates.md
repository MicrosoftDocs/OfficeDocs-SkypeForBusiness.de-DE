---
title: Konfigurieren von Zugriffsrichtlinien und Zertifikaten für XMPP-Gateways
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure XMPP gateway access policies and certificates
ms:assetid: fac02f4e-d14d-4be3-b53c-74c82436fd93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721945(v=OCS.15)
ms:contentKeyID: 49733882
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b6f1e9ef32d9d679542de35b8a2bd8dc3e855b86
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136012"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a>Konfigurieren von Zugriffsrichtlinien und Zertifikaten für XMPP-Gateways

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-15_

Der XMPP-Partnerverbund definiert eine externe Bereitstellung basierend auf dem XMPP-Protokoll (eXtensible Messaging and Presence Protocol). Die XMPP-Konfiguration erlaubt Lync-Benutzern wie folgt den Zugriff auf XMPP-Domänenbenutzer:

  - Chat und Anwesenheit – nur zwischen Benutzern

  - Erstellung von XMPP-Verbundkontakten im Lync-Client

Beim Konfigurieren von Richtlinien für die Unterstützung von XMPP-Verbundpartnern (extensible Messaging and Presence Protocol) gelten die Richtlinien für Benutzer von XMPP-Partnerverbunddomänen, aber nicht für Benutzer von SIP (Session Initiation Protocol)-Chatdienstanbietern (z. B. Windows Live) oder von SIP-Partnerverbunddomänen. Sie konfigurieren einen XMPP-Verbundpartner für jede XMPP-Partnerverbunddomäne, der Ihre Benutzer Kontakte hinzufügen und mit der sie kommunizieren sollen können. Wenn die Richtlinien vorhanden sind, müssen Sie die XMPP-Gatewayzertifikate konfigurieren.

<div>


> [!NOTE]  
> Um mit der XMPP-Gateway-Migration zu beginnen, müssen Sie das lync Server 2013 XMPP-Gateway bereitstellen und Zugriffsrichtlinien konfigurieren, um Benutzer für lync Server 2013 XMPP-Gateway zu aktivieren. Alle Benutzer müssen in die lync Server 2013-Bereitstellung verschoben werden, bevor Sie diese Schritte ausführen. Ausführliche Informationen finden Sie unter <A href="configure-xmpp-gateway-on-lync-server-2013.md">configure XMPP Gateway on lync Server 2013</A>.



</div>

<div>

## <a name="configure-an-external-access-policy-to-enable-users-for-lync-server-2013-xmpp-gateway"></a>Konfigurieren einer externen Zugriffsrichtlinie, um Benutzer für Lync Server 2013 XMPP Gateway zu aktivieren

1.  Öffnen Sie die Lync Server-Systemsteuerung.

2.  Klicken Sie in der linken Navigationsleiste auf **Partnerverbund und externer Zugriff**, und klicken Sie dann auf **Externe Zugriffsrichtlinie**.

3.  Klicken Sie auf **Neu** und anschließend auf **Benutzerrichtlinie**.

4.  Geben Sie einen Namen für die externe Benutzerzugriffsrichtlinie ein.

5.  Geben Sie eine Beschreibung für die externe Benutzerzugriffsrichtlinie ein.

6.  Wählen Sie **Kommunikation mit Partnerbenutzern aktivieren** aus.

7.  Wählen Sie **Kommunikation mit XMPP-Partnerverbundbenutzern aktivieren** aus.

8.  Klicken Sie auf **Commit ausführen**, um Ihre Änderungen am Standort oder an der Benutzerrichtlinie zu speichern.

</div>

</div>

<span> </span>

</div>

</div>

</div>

