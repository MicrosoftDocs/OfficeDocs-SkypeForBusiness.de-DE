---
title: 'Lync Server 2013: Erstellen einer VoIP-Routingrichtlinie für Zweigstellenbenutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create the VoIP routing policy for branch users
ms:assetid: 10deca9f-f870-4a42-b25d-e4fc53108658
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398196(v=OCS.15)
ms:contentKeyID: 48183435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f53e69069bc1f39f84c057f1e90882d5ae0d65d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832763"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-the-voip-routing-policy-for-branch-users-in-lync-server-2013"></a>Erstellen einer VoIP-Routingrichtlinie für Zweigstellenbenutzer in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-23_

Es wird empfohlen, eine separate VoIP-Richtlinie für Benutzer an Zweigstellen zu erstellen. Diese Richtlinie sollte Routen zu Ausgängen vom Survivable Branch Appliance-Gateway oder dem überlebensfähigen externen Branch Server-Gateway sowie Backup-Routen zum Ausstieg von einem Gateway am zentralen Standort enthalten. Unabhängig davon, wo der Benutzer registriert ist, entweder auf der Registrierungsstelle auf der Survivable Branch-Appliance oder auf dem Überlebenden Branch-Server oder auf dem Backup-Registrar-Cluster am zentralen Standort, ist die VoIP-Richtlinie des Benutzers immer gültig.

<div>

## <a name="to-configure-the-voip-routing-policy-for-branch-users"></a>So konfigurieren Sie die VoIP-Routing Richtlinie für Verzweigungs Benutzer

1.  Erstellen Sie einen Wählplan auf Benutzerebene, und weisen Sie ihn Verzweigungs Benutzern zu. (Weitere Informationen finden Sie unter [Erstellen eines Wählplans in lync Server 2013](lync-server-2013-create-a-dial-plan.md) in der Betriebsdokumentation.)

2.  Weisen Sie Normalisierungsregeln zu, die den Wählgewohnheiten der Benutzer auf dieser Website entsprechen. Wenn der überlebensfähige Branch Appliance-oder Survivable Branch Server-Benutzer an den sicherungsregistrierungspool am zentralen Standort scheitert, ist derselbe Wählplan in Kraft. (Weitere Informationen finden Sie unter [Erstellen eines Wählplans in lync Server 2013](lync-server-2013-create-a-dial-plan.md) in der Betriebsdokumentation.)

3.  Konfigurieren Sie eine VoIP-Route, die vom Survivable Branch Appliance-Gateway oder dem egresses-externen Gateway überlebensfähig ist. (Weitere Informationen finden Sie unter [Erstellen einer VoIP-Route in lync Server 2013](lync-server-2013-create-a-voice-route.md) in der Betriebsdokumentation.)

4.  Legen Sie eine Backup-Anrufroute auf der Survivable Branch-Appliance oder einem Überlebenden Branch Server-Gateway fest, um auf den sicherungsregistrierungspool (zusammen mit dem Mediation Server) am zentralen Standort zu verweisen. (Weitere Informationen finden Sie in der Dokumentation zu ihrer Survivable Branch-Appliance oder der Survivable Branch Server-Anbieter.)
    
    <div>
    

    > [!NOTE]  
    > Mit dieser Konfiguration für eine Backup-Anrufroute können Sie sicherstellen, dass eingehende Anrufe an den Verzweigungs Benutzer funktionieren, wenn die Survivable Branch-Appliance oder der Survivable Branch-Server nicht zur Verfügung steht (beispielsweise, wenn Sie nicht gewartet werden kann). Wenn die Registrierungsstelle und der Vermittlungsserver auf der Survivable Branch-Appliance oder dem Survivable Branch-Server nicht verfügbar sind und der Benutzer beim sicherungsregistrierungspool am zentralen Standort registriert ist, können eingehende Anrufe weiterhin an den Benutzer weitergeleitet werden.

    
    </div>

**Nächster Schritt**: [Konfigurieren der Einstellungen für die Umleitung von Voicemail in lync Server 2013](lync-server-2013-configure-voice-mail-rerouting-settings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

