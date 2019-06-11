---
title: 'Lync Server 2013: Bereitstellungscheckliste für die Anruf Zulassungs Steuerung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call admission control deployment checklist
ms:assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398928(v=OCS.15)
ms:contentKeyID: 48185525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cdda2e5231beb9f8303684ff29075c6322654945
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839716"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-deployment-checklist-for-lync-server-2013"></a>Checkliste für die Bereitstellung der Anrufsteuerung für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-22_

Verwenden Sie die folgende Checkliste, um sicherzustellen, dass Sie alle erforderlichen Konfigurationsaufgaben zum Bereitstellen der Anrufannahme Steuerung (CAC) abgeschlossen haben.

  - Wenn ein oder mehrere Edgeserver bereitgestellt werden, muss jede externe Schnittstellen-IP-Adresse der Subnetliste in den Netzwerkkonfigurationseinstellungen mit einer Bitmaske von 32 hinzugefügt werden. Sie sollten dieses Subnetz (IP-Adresse) außerdem der Netzwerkstandort-ID für den geografischen Standort zuordnen, an dem der A/V-Edgedienst bereitgestellt wurde.
    
    <div>
    

    > [!NOTE]  
    > Edgeserver müssen keine CAC-Implementierung implementieren.

    
    </div>

  - Stellen Sie sicher, dass CAC aktiviert ist, entweder über die lync Server-Systemsteuerung oder durch Ausführen des Cmdlets gemäß den Angaben unter [Aktivieren der Anrufsteuerung in lync Server 2013](lync-server-2013-enable-call-admission-control.md).

  - Stellen Sie sicher, dass die Anrufsteuerung an allen zentralen Standorten aktiviert ist. Dies kann über den Topologie-Generator erfolgen. Wenn beim Veröffentlichen eine Warnung generiert wird, ignorieren Sie diese *nicht*.

  - Stellen Sie sicher, dass alle im Unternehmensnetzwerk verwalteten Subnetze in den Netzwerkkonfigurationseinstellungen konfiguriert sind. Darüber hinaus ist es wichtig, dass jedes Subnetz einer Netzwerk Website zugeordnet ist, wie unter Zuordnen eines Subnetzes zu [einer Netzwerk Website in lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md)erläutert wird.

  - Stellen Sie sicher, dass die Subnetz- oder IP-Adressen aller Front-End-Server, Survivable Branch Appliances (SBAs), A/V-Konferenzserver (sofern in einem separaten Pool bereitgestellt) und Vermittlungsserver in den Netzwerkkonfigurationseinstellungen konfiguriert sind.

</div>

<span> </span>

</div>

</div>

</div>

