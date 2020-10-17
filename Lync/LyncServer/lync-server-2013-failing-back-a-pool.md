---
title: 'Lync Server 2013: zurückschlagen eines Pools'
description: 'Lync Server 2013: Fehler beim Zurückgeben eines Pools.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing back a pool
ms:assetid: 6232b644-ef57-4c9c-abec-14ff8ffc9fe7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204945(v=OCS.15)
ms:contentKeyID: 48184289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c1fc0ea4514d2f951dd936521590d47b809db38
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567741"
---
# <a name="failing-back-a-pool-in-lync-server-2013"></a>Zurückschlagen eines Pools in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

Nachdem der ausgefallene Pool (d. h. Pool1 im vorliegenden Beispiel) wieder online ist, müssen Sie die folgenden Schritte ausführen, um Ihre Bereitstellung wieder in den normalen Betriebszustand zurückzuversetzen.

Beachten Sie, dass der Failback-Prozess einige Zeit in Anspruch nehmen kann. So würde zum Beispiel ein Pool mit 20.000 Benutzern bis zu 60 Minuten benötigen.

1.  Führen Sie für die Benutzer, die ursprünglich in Pool1 untergebracht waren und auf Pool2 verlegt wurden, ein Failback mit dem folgenden Cmdlet durch:
    
        Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

Weitere Schritte sind nicht erforderlich. Wenn Sie den zentralen Verwaltungs Server nicht erfolgreich ausgeführt haben, können Sie ihn in Pool2 belassen.

</div>

<span> </span>

</div>

</div>

</div>

