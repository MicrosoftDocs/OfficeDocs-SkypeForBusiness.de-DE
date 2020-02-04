---
title: Überprüfen der Koexistenz der Pilotinstallation mit Pools der Vorversion
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
ms.openlocfilehash: fe3b3e04940c90cba4e46fc165c2494f77105667
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730895"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>Überprüfen der Koexistenz der Pilotinstallation mit Pools der Vorversion

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-29_

Nachdem Sie den Pilot Pool bereitgestellt haben, müssen Sie die Koexistenz der beiden Pools überprüfen, indem Sie die Verwaltungstools verwenden, um die Poolinformationen anzuzeigen. Für die lync Server 2013-Pools und Legacy Pools müssen Sie die lync Server 2013-Systemsteuerung und die Tools für die Topologie-Builder verwenden.

<div>

## <a name="verify-that-lync-server-2013-services-have-started"></a>Überprüfen, ob die lync Server 2013-Dienste gestartet wurden

1.  Navigieren Sie vom lync Server 2013-Front-End-Server zum Applet\\Dienste für administrative Tools.

2.  Überprüfen Sie, ob die folgenden Dienste auf dem Front-End-Server ausgeführt werden:

**Lync Server 2013-Dienste**

![Liste der gestarteten lync Server-Dienste](images/JJ205420.cfff9385-6bf6-461c-982c-e727c9f20b70(OCS.15).png "Liste der gestarteten lync Server-Dienste")

</div>

<div>

## <a name="open-the-lync-server-2013-control-panel"></a>Öffnen der lync Server 2013-Systemsteuerung

Öffnen Sie auf dem Front-End-Server in ihrer lync Server 2013-Bereitstellung die lync Server 2013-Systemsteuerung, und wählen Sie den lync Server 2010-Pool aus. Wiederholen Sie den Vorgang, um den lync Server 2013-Pool zu öffnen.

**Öffnen der lync Server 2013-Systemsteuerung**

![Dialogfeld ' URL auswählen '](images/JJ205420.b1f8e650-9c3c-4563-a403-5069f198342f(OCS.15).png "Dialogfeld ' URL auswählen '")

<div>


> [!IMPORTANT]  
> Bei lync Server 2013 müssen Sie Silverlight vor der Verwendung der lync Server-Systemsteuerung auf Silverlight, Version 5, aktualisieren.



</div>

Diese Topologie umfasst jetzt lync Server 2010 und lync Server 2013-Serverrollen.

**Lync Server 2013-Seite "Systemsteuerung"**

![Lync Server Control Panel – Seite "Topologie"](images/JJ205420.4ed1cc7a-cb3e-42f6-82e2-6d4d71d19352(OCS.15).jpg "Lync Server Control Panel – Seite "Topologie"")

</div>

<div>

## <a name="dont-attempt-to-open-the-topology-in-lync-server-2010-topology-builder"></a>Versuchen Sie nicht, die Topologie im lync Server 2010-Topologie-Generator zu öffnen.

Wenn Sie versuchen, die Topologie mit lync Server 2010 Topology Builder zu öffnen, wird der folgende Fehler angezeigt. Die Topologie kann nur mit dem lync Server 2013-Topologie-Generator angezeigt werden. Der lync Server 2013-Topologie-Generator muss zum Erstellen von Pools für lync Server 2013 und lync Server 2010 verwendet werden.

**Fehlermeldung zum lync Server 2010-Topologie-Generator**

![MMC-Snap-Fehler in lync Server Topology Builder](images/JJ205420.f6666343-c348-4d81-ae0e-6ba5a44e16c4(OCS.15).png "MMC-Snap-Fehler in lync Server Topology Builder")

</div>

</div>

<span> </span>

</div>

</div>

</div>

