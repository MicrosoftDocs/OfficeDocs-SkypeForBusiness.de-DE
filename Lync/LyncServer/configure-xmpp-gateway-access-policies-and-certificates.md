---
title: Konfigurieren von Zugriffsrichtlinien und Zertifikaten für XMPP-Gateways
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
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
ms.openlocfilehash: d7353d6bfdd4c045d9d592ababf92f2aaaec2365
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754473"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a>Konfigurieren von Zugriffsrichtlinien und Zertifikaten für XMPP-Gateways

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-15_

XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP). An XMPP configuration allows Lync users access to XMPP domain users by:

  - Chat und Anwesenheit – nur zwischen Benutzern

  - Erstellung von XMPP-Verbundkontakten im Lync-Client

When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains. You configure an XMPP Federated Partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with. Once the policies are in place, you need to configure the XMPP Gateway certificates.

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

