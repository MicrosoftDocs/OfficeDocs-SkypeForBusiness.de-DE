---
title: 'Lync Server 2013: Aktivieren von Benutzern für E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling users for E9-1-1
ms:assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425892(v=OCS.15)
ms:contentKeyID: 48183884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d62d811d78695cbc04fa8def76da1843beddb586
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832223"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-users-for-e9-1-1-in-lync-server-2013"></a>Aktivieren von Benutzern für E9-1-1 in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-06-06_

Während der Clientregistrierung verwendet lync Server eine ortungsrichtlinie, um die E9-1-1-Eigenschaften für Enterprise-VoIP-Benutzer zu konfigurieren. Diese Richtlinie enthält die Einstellungen, die definieren, wie E9-1-1 implementiert wird. Beispielsweise enthält die Standortrichtlinie Informationen wie die Notrufnummern Zeichenfolge und ob ein Benutzer manuell einen Standort eingeben muss, wenn der standortinformationsdienst nicht automatisch einen Speicherort bereitstellt. Eine vollständige Definition einer Standortrichtlinie finden Sie unter [Definieren der Standortrichtlinie für lync Server 2013](lync-server-2013-defining-the-location-policy.md).

Lync Server kann Clients, die auf einem Subnetz basieren, oder Benutzern, die auf einer globalen, pro-Site-oder pro-Benutzer-Richtlinie basieren, eine ortungsrichtlinie zuweisen. Damit Sie entscheiden können, wie Sie die Benutzer aktivieren können, sollten Sie zunächst die folgenden Fragen beantworten.

  - **Beabsichtigen Sie, alle Benutzer zu aktivieren oder die Unterstützung auf bestimmte geografische Bereiche des Unternehmens zu begrenzen?**  
    Sie können allen Benutzern in Ihrem Unternehmen einen Standort zuweisen, indem Sie eine globale Standortrichtlinie verwenden. Wenn Sie jedoch eine Standortrichtlinie einer lync Server-Netzwerk Website zuweisen und dann Subnetze zur Website hinzufügen, können Sie die E9-1-1-Unterstützung auf ausgewählte Standorte innerhalb des Unternehmens begrenzen und das Routingverhalten von E9-1-1 pro Website angeben.

<!-- end list -->

  - **Beabsichtigen Sie, einzelne Benutzer über eine Benutzerrichtlinie zu aktivieren?**  
    Sie können Standortrichtlinien bestimmten Benutzern oder öffentlichen Telefon Kontaktobjekten direkt zuweisen, wenn Sie Ihre E9-1-1-Unterstützung anpassen möchten.

<!-- end list -->

  - **Wenn Clients außerhalb des Netzwerks oder mit einem nicht definierten Subnetz verbunden sind, sollten die Clients weiterhin für E9-1-1 aktiviert sein?**  
    Wenn Benutzern eine Global-, Site-oder pro-User-ortungsrichtlinie zugewiesen ist, kann es erforderlich sein, einen Standort manuell in den Client einzugeben, wenn sich der Client nicht in einem definierten Subnetz befindet oder vom standortinformationsdienst kein Standort gefunden wurde. Ausführliche Informationen finden Sie unter [Definieren der Benutzeroberfläche für den manuellen Erwerb eines Speicherorts in lync Server 2013](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md).

</div>

<span> </span>

</div>

</div>

</div>

