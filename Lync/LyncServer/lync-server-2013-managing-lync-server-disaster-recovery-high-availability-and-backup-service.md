---
title: Verwalten von lync Server Disaster Recovery, Hochverfügbarkeits-und Sicherungsdienst
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Lync Server disaster recovery, high availability, and Backup Service
ms:assetid: f4cd36fb-ffd6-48fa-b761-e11b3bcff91a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721939(v=OCS.15)
ms:contentKeyID: 49733876
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7adc4086ac8ac6b8e5ad33c2e4c1dc131d357e0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762073"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-lync-server-2013-disaster-recovery-high-availability-and-backup-service"></a>Verwalten der Notfallwiederherstellung, der hohen Verfügbarkeit und des Sicherungsdiensts in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-12_

Dieser Abschnitt enthält Verfahren für Wiederherstellungsvorgänge in Notfällen sowie für die Verwaltung des Sicherungsdiensts, der die Daten in gekoppelten Front-End-Pools synchronisiert.

Disaster Recovery-Verfahren, sowohl Failover als auch Failback, sind manuell. Wenn ein Notfall vorliegt, muss der Administrator die Failoververfahren manuell aufrufen. Das gleiche gilt für das Failback, nachdem der Pool repariert wurde.

Bei den Disaster Recovery-Verfahren im restlichen Abschnitt wird Folgendes vorausgesetzt:

  - Sie verfügen über eine Bereitstellung mit gekoppelten Front-End-Pools, die sich an verschiedenen Standorten befinden, wie unter [Planen der Hochverfügbarkeits-und Disaster Recovery in lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)beschrieben. Der Sicherungsdienst wurde in diesen gekoppelten Pools ausgeführt, um sie synchron zu halten.

  - Wenn der zentrale Verwaltungsspeicher in einem der Pools gehostet wird, wird er in beiden Pools installiert und ausgeführt, wobei einer dieser Pools den aktiven Master und den anderen Pool hostet, in dem sich der Standby-Modus befindet.

<div>


> [!IMPORTANT]
> In den folgenden Verfahren bezieht sich der <EM>PoolFQDN</EM> -Parameter auf den FQDN des Pools, der von einem Notfall betroffen ist, nicht auf den Pool, von dem betroffene Benutzer umgeleitet werden. Für denselben Satz betroffener Benutzer verweist er sowohl in Failover-als auch in Failback-Cmdlets auf denselben Pool (also auf den Pool, der zuerst die Benutzer vor dem Failover verwaltet hat).<BR>Angenommen, ein Fall, in dem alle Benutzer, die sich in einem Pool P1 befanden, auf den Sicherungspool P2 umgestellt wurden. Wenn der Administrator alle Benutzer verschieben möchte, die von P2 aktuell gewartet werden, um von P1 gewartet zu werden, muss der Administrator die folgenden Schritte ausführen: 
> <OL>
> <LI>
> <P>Führen Sie mithilfe des Failback-Cmdlets alle Benutzer, die sich ursprünglich auf P1 benetzten, von P2 zu P1 zurück. In diesem Fall ist der <EM>PoolFQDN</EM> P1's-FQDN.</P>
> <LI>
> <P>Über das Failover-Cmdlet können alle Benutzer, die sich ursprünglich auf P2 mit P1 befanden, einen Failover durchführen. In diesem Fall ist der <EM>PoolFQDN</EM> P2-FQDN.</P>
> <LI>
> <P>Wenn der Administrator später diese P2-Benutzer wieder in P2 zurücksetzen möchte, ist der <EM>PoolFQDN</EM> P2-FQDN.</P></LI></OL>Beachten Sie, dass Schritt 1 oben vor Schritt 2 ausgeführt werden muss, um die Pool Integrität beizubehalten. Wenn Sie Schritt 2 vor Schritt 1 versuchen, tritt das Cmdlet "Schritt 2" nicht auf.



</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Konfigurieren und Überwachen des Sicherungsdiensts in Lync Server 2013](lync-server-2013-configuring-and-monitoring-the-backup-service.md)

  - [Ausführen eines Failovers für einen Pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md)

  - [Ausführen eines Failbacks für einen Pool in Lync Server 2013](lync-server-2013-failing-back-a-pool.md)

  - [Ausführen eines Failovers für eine gespiegelte Datenbank in Lync Server 2013](lync-server-2013-failing-over-a-mirrored-database.md)

  - [Ausführen eines Failovers für den Edgepool in Lync Server 2013, der für den Lync Server-Partnerverbund verwendet wird](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

  - [Ausführen eines Failovers für den Edgepool in Lync Server 2013, der für den XMPP-Partnerverbund verwendet wird](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)

  - [Ausführen eines Failbacks für den Edgepool in Lync Server 2013, der für den Lync Server-Partnerverbund verwendet wird](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)

  - [Ändern des einem Front-End-Pool zugeordneten Edgepools in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)

  - [Wiederherstellen von Konferenzinhalten mithilfe des Sicherungsdiensts in Lync Server 2013](lync-server-2013-restoring-conference-contents-using-the-backup-service.md)

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Planen der hohen Verfügbarkeit und der Notfallwiederherstellung in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

