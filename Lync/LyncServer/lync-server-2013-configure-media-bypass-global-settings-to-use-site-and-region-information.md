---
title: Konfigurieren der globalen Einstellungen für die Medienumgehung zur Verwendung von Standort- und Regionsinformationen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure media bypass global settings to use site and region information
ms:assetid: 0a21cdf1-f350-49da-b346-70806f256bea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398150(v=OCS.15)
ms:contentKeyID: 48183360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd070e6380a896548b851ac7d3472cd86eeba75b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839359"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-global-settings-in-lync-server-2013-to-use-site-and-region-information"></a>Configure media bypass global settings in Lync Server 2013 to use site and region information

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

<div>


> [!NOTE]
> In diesem Thema wird davon ausgegangen, dass Sie die medienumgehung für alle trunk Verbindungen vom Vermittlungs Server zu einem Peer (einem PSTN-Gateway (Public Switched Telephone Network), einer IP-Telefonanlage oder einem Session Border Controller (SBC) bei einem Internet-Telefoniedienst bereits konfiguriert haben. Anbieter (ITSP) für eine bestimmte Website oder einen bestimmten Dienst, für die Medien den Vermittlungs Server umgehen sollen.<BR>In diesem Thema wird auch davon ausgegangen, dass Sie alle zentralen Websites und Verzweigungs Websites im Topologie-Generator auf eine Weise definiert haben, die dem Netzwerkbereich, der Netzwerk Website und der Subnet-Konfiguration entspricht, die Sie gemäß den Schritten unter <A href="lync-server-2013-create-or-modify-a-network-region.md">erstellen oder Ändern eines Netzwerkbereichs in Lync Server 2013</A>, <A href="lync-server-2013-create-or-modify-a-network-site.md">erstellen oder Ändern einer Netzwerk Website in lync Server 2013</A>und Zuordnen eines Subnetzes <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">zu einer Netzwerk Website in lync Server 2013</A>. Wenn Sie nicht übereinstimmen, ist die medienumgehung nicht erfolgreich.



</div>

Zusätzlich zum Aktivieren der medienumgehung für einzelne trunk-Verbindungen, die einem Peer zugeordnet sind, müssen Sie auch die globalen Einstellungen konfigurieren. Wenn Sie die Schritte in diesem Thema zum Konfigurieren globaler Einstellungen für die medienumgehung verwenden, wird davon ausgegangen, dass eine oder beide der folgenden Situationen Ihre Konfiguration beeinflussen:

  - Sie verfügen *nicht* über eine gute Verbindung zwischen lync Server-Endpunkten und allen Peers, für die Sie die medienumgehung für die trunk-Verbindung konfiguriert haben.

  - Die Anrufannahme Steuerung (CAC) für die Bandbreitenverwaltung ist aktiviert.
    
    <div>
    

    > [!NOTE]
    > Details zu den Überlegungen für die Anrufsteuerung und die medienumgehung finden Sie im Abschnitt "Anrufsteuerung für PSTN-Verbindungen" im Abschnitt " <A href="lync-server-2013-media-bypass-and-mediation-server.md">medienumgehung und Vermittlungsserver" in lync Server 2013</A> in der Planungsdokumentation.

    
    </div>

Die Informationen zu Netzwerkregionen und Netzwerkstandorten werden sowohl für die Anrufsteuerung als auch für die Medienumgehung verwendet, wenn beide der erweiterten Enterprise-VoIP-Funktionen aktiviert sind. Wenn Sie daher die Anrufsteuerung bereits konfiguriert haben, müssen Sie das folgende Verfahren zum Bearbeiten von Standort- und Regioneninformationen nicht speziell für die Medienumgehung ausführen. Führen Sie die Schritte des folgenden Verfahrens aus, wenn Sie noch keine Netzwerkregionen und Standorte für die Anrufsteuerung konfiguriert haben und die Einstellungen für die Medienumgehung ändern möchten.

Oder führen Sie die folgenden Schritte aus, wenn Sie Website-und Regionsinformationen verwenden möchten, um die Umgehungs Entscheidung zu treffen, aber nicht die Möglichkeit haben, die Anrufsteuerung zu aktivieren. In diesem Fall müssen die Links zur Bandbreitenbeschränkung weiterhin über Netzwerk-standortübergreifende Richtlinien dargestellt werden, wie unter Erstellen von Netzwerk-standortübergreifenden [Richtlinien in lync Server 2013](lync-server-2013-create-network-intersite-policies.md)beschrieben. In diesem Fall sind die tatsächlichen Bandbreiteneinschränkungen nicht so wichtig, da die Anrufsteuerung nicht aktiviert wurde. Stattdessen werden diese Links zum Partitionieren von Subnetzen verwendet, um diejenigen anzugeben, die keine Bandbreitenbeschränkungen aufweisen und daher die medienumgehung verwenden können. Beachten Sie, dass dies auch der Fall ist, wenn die Anrufsteuerung und die medienumgehung aktiviert sind.

Damit die Umgehungsfunktion ordnungsgemäß funktioniert, muss die Konsistenz zwischen einer Website, wie Sie im Topologie-Generator definiert ist, und der Definition beim Konfigurieren von netzwerkregionen und Netzwerk Websites bestehen. Wenn Sie beispielsweise über eine Verzweigungs Website verfügen, die Sie im Topologie-Generator definiert haben, als ob nur ein PSTN-Gateway bereitgestellt wurde, muss diese Verzweigungs Website mit einer Enterprise-VoIP-Richtlinie konfiguriert werden, die es den Benutzern der Zweigstelle ermöglicht, ihre PSTN-Anrufe über das PSTN weiterzuleiten. Gateway an der Verzweigungs Website.

<div>

## <a name="to-configure-site-and-region-information-for-media-bypass"></a>So konfigurieren Sie Informationen zu Standorten und Regionen für die Medienumgehung

1.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.

3.  Doppelklicken Sie in der Tabelle auf die Konfiguration **Global**.

4.  Aktivieren Sie auf der Seite **Globale Einstellungen bearbeiten** das Kontrollkästchen **Medienumgehung aktivieren**.

5.  Klicken Sie auf **Standort- und Regionskonfiguration verwenden**.

6.  Falls erforderlich, aktivieren Sie das Kontrollkästchen **Umgehung für nicht zugeordnete Standorte aktivieren**.
    
    <div>
    

    > [!NOTE]
    > Aktivieren Sie dieses Kontrollkästchen nur, wenn Sie über einen oder mehrere große Standorte ohne Bandbreiteneinschränkungen verfügen (z. B. ein großer Hauptstandort), die einer bestimmten Region zugeordnet sind, und Sie außerdem über einige Zweigniederlassungen mit Bandbreiteneinschränkungen verfügen, die derselben Region zugeordnet sind. Wenn Sie die Umgehung für nicht zugeordnete Standorte aktivieren, wird die Konfiguration optimiert, da Sie nur die den Zweigniederlassungen zugeordneten Subnetze angeben, statt sämtliche, allen Standorten zugeordnete Subnetze angeben zu müssen. Es wird empfohlen, dieses Kontrollkästchen nicht zu aktivieren, wenn die Anrufsteuerung aktiviert wurde.

    
    </div>

7.  Klicken Sie auf **Commit ausführen**.

Fügen Sie als nächstes Subnetze zur Netzwerk Website hinzu, wie in Zuordnen von Subnetzen [mit Netzwerk Websites für die medienumgehung in lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md)beschrieben. (Die eigentlichen Verfahren zum Verknüpfen von Subnetzen mit Netzwerkstandorten werden unter [Zuordnen eines Subnetzes zu einer Netzwerk Website in lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md)beschrieben.) Nachdem Sie alle Subnetze mit Netzwerk Websites verknüpft haben, ist die Medien Umgehungs Bereitstellung abgeschlossen.

<div>


> [!IMPORTANT]
> Wenn Sie noch keine Netzwerkregionen und Netzwerkstandorte erstellt haben, müssen Sie dies nachholen, bevor Sie mit der Bereitstellung der Medienumgehung fortfahren können. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-create-or-modify-a-network-region.md">erstellen oder Ändern eines Netzwerkbereichs in lync Server 2013</A> und <A href="lync-server-2013-create-or-modify-a-network-site.md">erstellen oder Ändern einer Netzwerk Website in lync Server 2013</A>.



</div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Zuordnen von Subnetzen zu Netzwerk Websites zur medienumgehung in lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

