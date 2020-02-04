---
title: 'Lync Server 2013: Ausführen eines Failovers für den Edgepool, der für den XMPP-Partnerverbund verwendet wird'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over the Edge pool used for XMPP federation
ms:assetid: 587e7829-a26b-46f8-8aad-b78a7b325b55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688065(v=OCS.15)
ms:contentKeyID: 49733659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d1c76dc37ce1abb2d34c474d4144b0894d93a0f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765183"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-the-edge-pool-used-for-xmpp-federation-in-lync-server-2013"></a>Ausführen eines Failovers für den Edgepool in Lync Server 2013, der für den XMPP-Partnerverbund verwendet wird

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-19_

In Ihrer Organisation gibt es einen Edge-Pool, der als Pool für XMPP-Föderationen verwendet wird. Wenn dieser Pool ausfällt, müssen Sie die XMPP-Föderation nicht verwenden, um einen anderen Edge-Pool zu verwenden, bevor die XMPP-Föderation wieder funktionieren kann.

Wenn Sie Edge-Pools zum ersten Mal installieren und die XMPP-Föderation aktivieren, können Sie den Disaster Recovery-Prozess vereinfachen, indem Sie externe DNS-SRV-Einträge für alle Ihre Edge-Pools für XMPP Federation einrichten, und nicht nur eine. Jeder dieser SRV-Einträge muss einen anderen Prioritäts Satz aufweisen. Der gesamte XMPP-Verbunddatenverkehr durchläuft den Pool mit dem SRV-Eintrag mit der höchsten Priorität. Weitere Informationen zum Aktivieren und Einrichten von XMPP Federation finden Sie unter [Einrichten von XMPP Federation in lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md).

In der folgenden Vorgehensweise ist EdgePool1 der Pool, in dem die XMPP-Föderation ursprünglich gehostet wurde, und EdgePool2 ist der Pool, der nun XMPP-Föderation hostet.

<div>

## <a name="failing-over-the-edge-pool-used-for-xmpp-federation"></a>Failover des für die XMPP-Föderation verwendeten Edge-Pools

1.  Wenn Sie noch keinen anderen Edge-Pool bereitgestellt haben (außer dem, der zurzeit nicht vorhanden ist), stellen Sie diesen Pool bereit. Ausführliche Informationen finden Sie unter [Bereitstellen des Zugriffs auf externe Benutzer in lync Server 2013](lync-server-2013-deploying-external-user-access.md).

2.  Führen Sie auf jedem Edgeserver des neuen Edge-Pools, in dem nun XMPP Federation (EdgePool2) gehostet wird, das folgende Cmdlet aus:
    
        Stop-CsWindowsService

3.  Führen Sie das folgende Cmdlet aus, um die XMPP-Föderations Route auf EdgePool2 zu verweisen:
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    In diesem Beispiel ist site2 die Website, die den Edge-Pool enthält, auf dem nun die XMPP-Föderations Route gehostet wird, und EdgeServer2.contoso.com ist der FQDN eines Edgeserver in diesem Pool.

4.  Ändern Sie auf dem externen DNS-Server den DNS-A-Eintrag für XMPP-Föderation, um auf EdgeServer2.contoso.com zu verweisen.

5.  Wenn Sie noch keinen DNS-SRV-Eintrag für die XMPP-Föderation haben, der in den Edge-Pool aufgelöst wird, der nun XMPP-Föderation hostet, müssen Sie ihn wie im folgenden Beispiel hinzufügen. Dieser SRV-Eintrag muss einen Portwert von 5269 aufweisen.
    
        _xmpp-server._tcp.contoso.com

6.  Überprüfen Sie, ob der Edge-Pool, auf dem nun der XMPP-Verbund gehostet wird, Port 5269 extern geöffnet hat.

7.  Starten Sie die Dienste auf allen Edgeserver im Edge-Pool, die nun die XMPP-Föderation hosten:
    
        Start-CsWindowsService

</div>

</div>

<span> </span>

</div>

</div>

</div>

