---
title: 'Lync Server 2013: Erforderliche Ressourcen für den Server für beständigen Chat'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Required resources
ms:assetid: bce50b95-f3c8-407e-963a-d8896ee77fbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205211(v=OCS.15)
ms:contentKeyID: 48185255
ms.date: 02/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac51432de0a6ca261e42f77d64ef1aa1a615cb6d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823252"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="required-resources-for-persistent-chat-server-in-lync-server-2013"></a>Erforderliche Ressourcen für den Server für beständigen Chat in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2016-02-05_

Hochverfügbarkeit und Disaster Recovery für beständigen Chat Server erfordern zusätzliche Ressourcen, die über das hinausgehen, was in der Regel für den vollständigen Betrieb benötigt wird. Bevor Sie den beständigen Chat Server für Hochverfügbarkeit und Disaster Recovery konfigurieren, stellen Sie sicher, dass Sie über die folgenden Ressourcen verfügen, die für den standardmäßigen Serverbetrieb des beständigen Chats erforderlich sind. Weitere Konfigurationsinformationen finden Sie unter [Konfigurieren des beständigen Chat Servers in lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md).

  - Eine dedizierte Datenbankinstanz, die sich im gleichen physikalischen Rechenzentrum befindet, in dem sich das Home-Front-End des Server Diensts für beständigen Chat befindet. Diese Datenbank dient als SQL Server-Spiegelung für die primäre Datenbank für beständigen Chat. Optional können Sie einen zusätzlichen SQL-Server als Spiegelungs Zeuge festlegen, wenn Sie ein automatisches Failover zur Spiegeldatenbank durch stellen möchten.

  - Eine dedizierte Datenbankinstanz in dem anderen physischen Rechenzentrum. Diese Datenbank dient als SQL Server-Protokollversand-sekundäre Datenbank für die Datenbank im primären Rechenzentrum.

  - Eine dedizierte Datenbankinstanz, die als SQL Server-Spiegelung für die sekundäre Datenbank fungieren soll. Optional können Sie einen zusätzlichen SQL Server als Spiegelungs Zeuge auf dem Server angeben. Beide Instanzen müssen sich im selben physischen Rechenzentrum wie die sekundäre Datenbank befinden.

  - Wenn die Kompatibilität des beständigen Chat Servers aktiviert ist, sind zusätzliche drei dedizierte Datenbankinstanzen erforderlich. Ihre Verteilung ist mit denen identisch, die zuvor für die persistente Chat-Datenbank beschrieben wurden. Es ist zwar möglich, dass die Compliance-Datenbank dieselbe SQL Server-Instanz wie die persistente Chat-Datenbank hat, wir empfehlen jedoch eigenständige Instanzen für eine höhere Verfügbarkeit und Disaster Recovery.

  - Es muss eine Dateifreigabe erstellt und für die Transaktionsprotokolle des SQL Server-Protokollversands festgelegt werden. Alle SQL-Server in beiden Rechenzentren, in denen persistente Chat Datenbanken ausgeführt werden, müssen über Lese-/Schreibzugriff auf diese Dateifreigabe verfügen. Diese Freigabe wird nicht als Teil einer FileStore-Rolle definiert.

  - Eine Dateifreigabe auf dem sekundären Datenbankserver, die als Zielordner für die SQL Server-Transaktionsprotokolle fungieren soll, die aus der Dateifreigabe des primären Servers kopiert werden.

<div>


> [!NOTE]  
> Aktive beständige Chat Server in einem beständigen Chat Serverpool müssen sich in derselben Zeitzone befinden wie der lync-Pool für den nächsten Hop, der in der Topologie definiert ist.



</div>

Die folgenden Abbildungen enthalten Beispiele dafür, wie der gesamte Server Pool für beständigen Chat in den beiden unterschiedlichen gedehnten Pool Topologien konfiguriert werden kann:

  - Gedehnter beständiger Chat Server Pool, wenn Rechenzentren mit hoher Bandbreite/geringer Latenz geographisch lokalisiert sind.

  - Gedehnter beständiger Chat Server Pool, wenn Rechenzentren mit niedriger Bandbreite/hoher Latenz geografischer Standort sind.

Die folgende Abbildung zeigt eine gedehnte Server Pooltopologie mit beständigem Chat, in der Rechenzentren mit hoher Bandbreite/geringer Latenz geographisch lokalisiert sind.

**Gedehnter beständiger Chat Server Pool, wenn Rechenzentren mit hoher Bandbreite/geringer Latenz geographisch lokalisiert sind.**

![Beständiger Chat Server Pool HBW-Konfigurationsprüfung] (images/JJ205211.55d10910-c824-41e6-bed2-08d13a2abd65(OCS.15).jpg "Beständiger Chat Server Pool HBW-Konfigurationsprüfung")

Die folgende Abbildung zeigt eine gedehnte Server Pooltopologie mit beständigem Chat, in der Rechenzentren mit niedriger Bandbreite/hoher Latenz geografisch lokalisiert sind.

**Gedehnter beständiger Chat Server Pool, wenn Rechenzentren mit niedriger Bandbreite/hoher Latenz geografischer Standort sind.**

![Beständiger Chat Server Pool LBW-Konfigurationsprüfung] (images/JJ205211.586b0a3a-3767-4991-944f-ee54389512aa(OCS.15).jpg "Beständiger Chat Server Pool LBW-Konfigurationsprüfung")

</div>

<span> </span>

</div>

</div>

</div>

