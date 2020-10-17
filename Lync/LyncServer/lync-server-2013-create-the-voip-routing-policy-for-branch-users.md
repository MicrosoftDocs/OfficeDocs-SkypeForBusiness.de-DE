---
title: 'Lync Server 2013: Erstellen der VoIP-Routing Richtlinie für Zweigstellenbenutzer'
description: 'Lync Server 2013: Erstellen Sie die VoIP-Routing Richtlinie für Zweigstellenbenutzer.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create the VoIP routing policy for branch users
ms:assetid: 10deca9f-f870-4a42-b25d-e4fc53108658
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398196(v=OCS.15)
ms:contentKeyID: 48183435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c39cff86d9ede957fa99e7955d8a87172380f963
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551081"
---
# <a name="create-the-voip-routing-policy-for-branch-users-in-lync-server-2013"></a>Erstellen der VoIP-Routing Richtlinie für Zweigstellenbenutzer in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-23_

Es wird empfohlen, eine separate VoIP-Richtlinie (Voice over IP) für Benutzer an Zweigstellen zu erstellen. Diese Richtlinie sollte Routen zum Ausstieg aus dem Survivable Branch Appliance Gateway oder dem Survivable Branch Server externen Gateway sowie Sicherungs Routen zum Ausstieg von einem Gateway am zentralen Standort enthalten. Unabhängig davon, wo der Benutzer registriert ist, entweder auf der Registrierungsstelle im Survivable Branch Appliance oder Survivable Branch Server oder auf dem Sicherungs Registrierungs Cluster am zentralen Standort ist die VoIP-Richtlinie des Benutzers immer gültig.

<div>

## <a name="to-configure-the-voip-routing-policy-for-branch-users"></a>So konfigurieren Sie die VoIP-Routing Richtlinie für Zweigstellenbenutzer

1.  Erstellen Sie einen Wählplan auf Benutzerebene, und weisen Sie ihn Zweigstellenbenutzern zu. (Weitere Informationen finden Sie unter [Create a Dial Plan in lync Server 2013](lync-server-2013-create-a-dial-plan.md) in der Betriebsdokumentation.)

2.  Zuweisen von Normalisierungsregeln entsprechend den Wählgewohnheiten von Benutzern an diesem Standort. Wenn der Survivable Branch Appliance-oder Survivable Branch Server-Benutzer einen Failover zum sicherungsregistrierungspool am zentralen Standort vorschlägt, wird derselbe Wählplan wirksam. (Weitere Informationen finden Sie unter [Create a Dial Plan in lync Server 2013](lync-server-2013-create-a-dial-plan.md) in der Betriebsdokumentation.)

3.  Konfigurieren Sie eine VoIP-Route, die vom Survivable Branch Appliance Gateway oder dem Survivable Branch Server externen Gateway das. (Weitere Informationen finden Sie unter [Create a Voice Route in lync Server 2013](lync-server-2013-create-a-voice-route.md) in der Betriebsdokumentation.)

4.  Legen Sie eine Sicherungs Anrufroute auf dem Survivable Branch Appliance oder Survivable Branch Server Gateway so fest, dass Sie auf den sicherungsregistrierungspool (zusammen mit Vermittlungsserver) am zentralen Standort zeigt. (Weitere Informationen finden Sie in ihrer Survivable Branch Appliance-oder Survivable Branch Server Lieferantendokumentation.)
    
    <div>
    

    > [!NOTE]  
    > Durch diese Konfiguration für die Sicherung der Anrufweiterleitung wird sichergestellt, dass eingehende Anrufe an den Zweigstellenbenutzer funktionieren, wenn der Survivable Branch Appliance oder Survivable Branch Server nicht verfügbar ist (beispielsweise wenn er für die Wartung nicht zur Verfügung steht). Wenn die Registrierungsstelle und die Vermittlungsserver im Survivable Branch Appliance oder Survivable Branch Server nicht verfügbar sind und der Benutzer beim sicherungsregistrierungspool am zentralen Standort registriert ist, können eingehende Anrufe weiterhin an den Benutzer weitergeleitet werden.

    
    </div>

**Nächster Schritt**: [Konfigurieren von Einstellungen für die Umleitung von Voicemail in lync Server 2013](lync-server-2013-configure-voice-mail-rerouting-settings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

