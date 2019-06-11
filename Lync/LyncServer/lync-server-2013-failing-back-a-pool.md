---
title: 'Lync Server 2013: Ausführen eines Failbacks für einen Pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing back a pool
ms:assetid: 6232b644-ef57-4c9c-abec-14ff8ffc9fe7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204945(v=OCS.15)
ms:contentKeyID: 48184289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cade83015f57e86e08978ac3bfd9fb848dae9563
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832178"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-back-a-pool-in-lync-server-2013"></a>Ausführen eines Failbacks für einen Pool in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Nachdem der Pool, der das Desaster erlebt hat, wieder online ist (also pool1 in diesem Beispiel), führen Sie die folgenden Schritte aus, um die Bereitstellung auf normalen Arbeitsstatus wiederherzustellen.

Beachten Sie, dass der Failback-Vorgang mehrere Minuten in Anspruch nimmt.Zur Orientierung: Erwartungsgemäß dauert dies bei einem Pool mit 20.000 Benutzern bis zu 60 Minuten.

1.  Führen Sie einen Failback für die Benutzer durch, die sich ursprünglich in pool1 begeben haben, und Sie haben ein Failover auf Pool2 durchgeführt, indem Sie das folgende Cmdlet eingegeben haben:
    
        Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

Es sind keine weiteren Schritte erforderlich. Wenn Sie einen Fehler über den zentralen Verwaltungs Server ausgeführt haben, können Sie ihn in Pool2 belassen.

</div>

<span> </span>

</div>

</div>

</div>

