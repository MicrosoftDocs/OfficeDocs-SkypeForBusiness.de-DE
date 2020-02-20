---
title: 'Lync Server 2013: Failover des für XMPP-Verbund verwendeten Edgepools'
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
ms.openlocfilehash: 182bc427c7b4faf3bd937bd58af8ca1d4d9c7d77
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145824"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failing-over-the-edge-pool-used-for-xmpp-federation-in-lync-server-2013"></a>Failover der Edgepool, die für den XMPP-Verbund in lync Server 2013 verwendet wurden

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-19_

Ein Edgepool in Ihrer Organisation wurde als Pool für den XMPP-Verbund festgelegt. Wenn dieser Pool ausfällt, müssen Sie einen Failover des XMPP-Verbunds zu einem anderen Edgepool ausführen, um den XMPP-Verbund wieder verwenden zu können.

Wenn Sie Edgepools zum ersten Mal installieren und den XMPP-Verbund aktivieren, können Sie den Notfallwiederherstellungsprozess vereinfachen, indem Sie externe DNS-SRV-Einträge für alle Edgepools des XMPP-Verbunds anstatt nur einen einzigen einrichten. Jeder SRV-Eintrag muss über eine eigene Priorität verfügen. Der gesamte XMPP-Verbunddatenverkehr wird über den Pool mit dem SRV-Eintrag abgewickelt, der über die höchste Priorität verfügt. Weitere Informationen zum Aktivieren und Einrichten von XMPP-Verbund finden Sie unter [Einrichten von XMPP-Verbund in lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md).

Im folgenden Verfahren stellt EdgePool1 den Pool dar, in dem der XMPP-Verbund ursprünglich gehostet wurde; EdgePool2 ist der Pool, in dem der XMPP-Verbund jetzt gehostet werden soll.

<div>

## <a name="failing-over-the-edge-pool-used-for-xmpp-federation"></a>Failover des Edgepools für den XMPP-Verbund

1.  Wenn Sie (neben dem ausgefallenen) noch keinen weiteren Edgepool bereitgestellt haben, stellen Sie den Pool jetzt bereit. Ausführliche Informationen finden Sie unter [Deploying External User Access in lync Server 2013](lync-server-2013-deploying-external-user-access.md).

2.  Führen Sie auf jedem Edgeserver im neuen Edgepool, in dem jetzt der XMPP-Verbund gehostet wird (EdgePool2), das folgende Cmdlet aus:
    
        Stop-CsWindowsService

3.  Führen Sie das folgende Cmdlet aus, damit die XMPP-Verbundroute wieder auf EdgePool2 zeigt:
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    In diesem Beispiel stellt Site2 den Standort mit dem Edgepool dar, in dem jetzt die XMPP-Verbundroute gehostet wird, und EdgeServer2.contoso.com ist der FQDN eines Edgeservers in diesem Pool.

4.  Ändern Sie auf dem externen DNS-Server den DNS-A-Eintrag für den XMPP-Verbund, sodass dieser auf EdgeServer2.contoso.com verweist.

5.  Wenn Sie noch nicht über einen DNS-SRV-Eintrag für den XMPP-Verbund verfügen, der in den Edgepool aufgelöst wird, in dem jetzt der XMPP-Verbund gehostet wird, müssen Sie diesen hinzufügen, wie im folgenden Beispiel veranschaulicht. Dieser SRV-Eintrag muss den Portwert 5269 aufweisen.
    
        _xmpp-server._tcp.contoso.com

6.  Vergewissern Sie sich, dass in dem Edgepool, in dem der XMPP-Verbund jetzt gehostet wird, der Port 5269 für die externe Kommunikation geöffnet ist.

7.  Starten Sie die Dienste auf allen Edgeservern in dem Edgepool, in dem der XMPP-Verbund jetzt gehostet wird:
    
        Start-CsWindowsService

</div>

</div>

<span> </span>

</div>

</div>

</div>

