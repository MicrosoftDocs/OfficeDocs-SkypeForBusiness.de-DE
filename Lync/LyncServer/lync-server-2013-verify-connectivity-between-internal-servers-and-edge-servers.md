---
title: Überprüfen der Konnektivität zwischen internen Servern und Edge-Servern
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify connectivity between internal servers and Edge Servers
ms:assetid: 219f706e-2b8a-46c5-b394-c384240eef50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398292(v=OCS.15)
ms:contentKeyID: 48183602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a170ac21c89bd405ad0406830c00feabbde5434
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518652"
---
# <a name="verify-connectivity-between-internal-servers-and-edge-servers-in-lync-server-2013"></a>Überprüfen der Konnektivität zwischen internen Servern und Edge-Servern in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-08_

In lync Server 2013 war ein separater Validierungs Assistent verfügbar, der die Überprüfung der Konnektivität zwischen Edge-Servern und internen Servern unterstützt. In lync Server 2013 wird die Überprüfung der Konnektivität bei der Installation Ihrer Edgeserver automatisch durchgeführt.

Sie können die Replikation von Konfigurationsinformationen auf den Edge überprüfen, indem Sie das Cmdlet Windows PowerShell **Get-CsManagementStoreReplicationStatus** auf dem internen Computer ausführen, auf dem sich der zentrale Verwaltungsspeicher befindet (oder auf einem beliebigen Computer in der Domäne, auf dem lync Server 2013 Core Components (OcsCore.msi) installiert ist. Anfängliche Ergebnisse geben möglicherweise den Status "false" anstelle von "true" für die Replikation an. Wenn dies der Fall ist, führen Sie das **Invoke-CsManagementStoreReplication-** Cmdlet aus, und lassen Sie die Replikation vor dem erneuten Ausführen des **Get-CsManagementStoreReplicationStatus** Zeit in Anspruch nehmen.

Sie können die Konnektivität für externe Benutzer separat überprüfen, einschließlich Verwendung der Remoteverbindungsanalyse von Office Communications Server zum Überprüfen der Remotebenutzerkonnektivität. Ausführliche Informationen finden Sie unter [Überprüfen der Konnektivität für externe Benutzer in lync Server 2013](lync-server-2013-verify-connectivity-for-external-users.md).

</div>

<span> </span>

</div>

</div>

</div>

