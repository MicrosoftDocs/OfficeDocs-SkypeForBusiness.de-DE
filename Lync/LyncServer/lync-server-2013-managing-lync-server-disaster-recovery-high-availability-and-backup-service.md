---
title: Verwalten von lync Server Notfallwiederherstellung, hoher Verfügbarkeit und Sicherungsdienst
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
ms.openlocfilehash: b7ee9bd75ce0f9326c06ffda28a48193749a950c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150286"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-lync-server-2013-disaster-recovery-high-availability-and-backup-service"></a>Verwalten von lync Server 2013 Notfallwiederherstellung, hoher Verfügbarkeit und Sicherungsdienst

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-12_

Dieser Abschnitt enthält Verfahren für Notfall Wiederherstellungsvorgänge sowie für die Verwaltung des Sicherungsdiensts, der die Daten in paarweise gepaarten Front-End-Pools synchronisiert.

Notfallwiederherstellungsverfahren, sowohl Failover als auch Failback, sind manuell. Wenn ein Notfall vorliegt, muss der Administrator die Failover-Verfahren manuell aufrufen. Gleiches gilt für das Failback, nachdem der Pool repariert wurde.

Für die Notfallwiederherstellungsverfahren im Rest dieses Abschnitts wird Folgendes vorausgesetzt:

  - Sie verfügen über eine Bereitstellung mit paarweise gepaarten Front-End-Pools, die sich an unterschiedlichen Standorten befinden, wie unter [Planung für hohe Verfügbarkeit und Notfallwiederherstellung in lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)beschrieben. Der Sicherungsdienst wurde für diese gepaarten Pools ausgeführt, damit Sie synchronisiert bleiben.

  - Wenn der zentrale Verwaltungsspeicher in einem der Pools gehostet wird, wird er auf beiden Pools installiert und ausgeführt, wobei einer der Pools, die den aktiven Master hosten, und der andere Pool, der den Standby hostet.

<div>


> [!IMPORTANT]
> In den folgenden Verfahren bezieht sich der Parameter <EM>poolfqdn "</EM> auf den FQDN des Pools, der vom Notfall betroffen ist, und nicht auf den Pool, von dem betroffene Benutzer umgeleitet werden. Für dieselbe Gruppe betroffener Benutzer bezieht sich dieser auf denselben Pool sowohl in Failover-als auch in Failback-Cmdlets (also im Pool, der zuerst die Benutzer vor dem Failover verwaltet hat).<BR>Nehmen wir beispielsweise an, dass alle Benutzer, die in einem Pool P1 verwaltet werden, ein Failover auf den Sicherungspool P2 durchlaufen haben. Wenn der Administrator alle Benutzer, die derzeit von P2 gewartet werden, von P1 migrieren möchte, muss der Administrator die folgenden Schritte ausführen: 
> <OL>
> <LI>
> <P>Zurücksetzen aller Benutzer, die ursprünglich unter P1 von P2 auf P1 verwaltet wurden, mithilfe des Failback-Cmdlets. In diesem Fall ist die <EM>poolfqdn "</EM> P1's FQDN.</P>
> <LI>
> <P>Führen Sie einen Failover für alle Benutzer aus, die ursprünglich mit dem Cmdlet Failover auf P2 auf P1 verwaltet wurden. In diesem Fall ist die <EM>poolfqdn "</EM> P2 FQDN.</P>
> <LI>
> <P>Wenn der Administrator später diese P2-Benutzer wieder auf P2 zurückführen möchte, ist die <EM>poolfqdn "</EM> P2 FQDN.</P></LI></OL>Beachten Sie, dass Schritt 1 vor Schritt 2 ausgeführt werden muss, um die Integrität des Pools beizubehalten. Wenn Sie Schritt 2 vor Schritt 1 versuchen, tritt beim Schritt 2-Cmdlet ein Fehler auf.



</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Konfigurieren und Überwachen des Sicherungsdiensts in lync Server 2013](lync-server-2013-configuring-and-monitoring-the-backup-service.md)

  - [Failover eines Pools in lync Server 2013](lync-server-2013-failing-over-a-pool.md)

  - [Zurückschlagen eines Pools in lync Server 2013](lync-server-2013-failing-back-a-pool.md)

  - [Failover einer gespiegelten Datenbank in lync Server 2013](lync-server-2013-failing-over-a-mirrored-database.md)

  - [Failover der Edgepool, die für lync Server Partnerverbund in lync Server 2013 verwendet wurden](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

  - [Failover der Edgepool, die für den XMPP-Verbund in lync Server 2013 verwendet wurden](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)

  - [Zurückgeben der Edgepool, die für lync Server Partnerverbund oder XMPP-Verbund in lync Server 2013 verwendet wurden](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)

  - [Ändern des Edgepool, das einem Front-End-Pool in lync Server 2013 zugeordnet ist](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)

  - [Wiederherstellen von Konferenz Inhalten mithilfe des Sicherungsdiensts in lync Server 2013](lync-server-2013-restoring-conference-contents-using-the-backup-service.md)

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Planen der hohen Verfügbarkeit und der Notfallwiederherstellung in lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

