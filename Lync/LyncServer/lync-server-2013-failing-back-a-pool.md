---
title: 'Lync Server 2013: zurückschlagen eines Pools'
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
ms.openlocfilehash: c5929ed5fc3d29c0a42c223403a78f83154c5bef
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048028"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-back-a-pool-in-lync-server-2013"></a>Zurückschlagen eines Pools in lync Server 2013

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

