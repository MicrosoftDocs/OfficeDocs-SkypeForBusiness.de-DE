---
title: Überprüfen der Koexistenz von pilotpools mit einem Legacy Pool
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify pilot pool coexistence with legacy pool
ms:assetid: fe7e14bb-c7eb-4719-b154-009e99360520
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205420(v=OCS.15)
ms:contentKeyID: 48185964
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c30f15b7a4e40b5c814ed5f21d07e213b69cf10
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188888"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>Überprüfen der Koexistenz von pilotpools mit einem Legacy Pool

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-29_

Nachdem Sie den Pilot-Pool bereitgestellt haben, müssen Sie die Koexistenz der beiden Pools überprüfen, indem Sie die Verwaltungstools verwenden, um die Poolinformationen anzuzeigen. Für lync Server 2013 Pools und Legacy Pools müssen Sie die lync Server 2013-Systemsteuerung und die Topologie-Generator-Tools verwenden.

<div>

## <a name="verify-that-lync-server-2013-services-have-started"></a>Überprüfen, ob lync Server 2013 Dienste gestartet wurden

1.  Navigieren Sie im lync Server 2013 Front-End-Server zum Applet Dienste für administrative\\Tools.

2.  Überprüfen Sie, ob die folgenden Dienste auf dem Front-End-Server ausgeführt werden:

**Lync Server 2013 Dienste**

![Liste der gestarteten lync Server Dienste](images/JJ205420.cfff9385-6bf6-461c-982c-e727c9f20b70(OCS.15).png "Liste der gestarteten lync Server Dienste")

</div>

<div>

## <a name="open-the-lync-server-2013-control-panel"></a>Öffnen der lync Server 2013-Systemsteuerung

Öffnen Sie in der Front-End-Server in ihrer lync Server 2013-Bereitstellung die lync Server 2013-Systemsteuerung, und wählen Sie den lync Server 2010 Pool aus. Wiederholen Sie den Vorgang, um den lync Server 2013-Pool zu öffnen.

**Öffnen lync Server 2013 Systemsteuerung**

![Dialogfeld ' URL auswählen '](images/JJ205420.b1f8e650-9c3c-4563-a403-5069f198342f(OCS.15).png "Dialogfeld ' URL auswählen '")

<div>


> [!IMPORTANT]  
> In lync Server 2013 müssen Sie Silverlight vor der Verwendung des lync Server-Systemsteuerung auf Silverlight, Version 5, aktualisieren.



</div>

Diese Topologie umfasst nun lync Server 2010-und lync Server 2013-Server Rollen.

**Lync Server 2013-topologieseite "Systemsteuerung"**

![Lync Server-Systemsteuerung-Topologie-Seite](images/JJ205420.4ed1cc7a-cb3e-42f6-82e2-6d4d71d19352(OCS.15).jpg "Lync Server-Systemsteuerung-Topologie-Seite")

</div>

<div>

## <a name="dont-attempt-to-open-the-topology-in-lync-server-2010-topology-builder"></a>Versuchen Sie nicht, die Topologie in lync Server 2010-Topologie-Generator zu öffnen.

Wenn Sie versuchen, die Topologie mit lync Server 2010-Topologie-Generator zu öffnen, tritt der folgende Fehler auf. Die Topologie kann nur mit lync Server 2013 Topologie-Generator angezeigt werden. Der lync Server 2013 Topologie-Generator muss verwendet werden, um Pools für lync Server 2013 und lync Server 2010 zu erstellen.

**Lync Server 2010-Topologie-Generator Fehlermeldung**

![Lync Server-Topologie-Generator-MMC-Snap-Fehler](images/JJ205420.f6666343-c348-4d81-ae0e-6ba5a44e16c4(OCS.15).png "Lync Server-Topologie-Generator-MMC-Snap-Fehler")

</div>

</div>

<span> </span>

</div>

</div>

</div>

