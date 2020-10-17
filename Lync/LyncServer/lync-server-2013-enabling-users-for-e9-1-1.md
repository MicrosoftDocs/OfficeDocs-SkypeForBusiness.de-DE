---
title: 'Lync Server 2013: Aktivieren von Benutzern für E9-1-1'
description: 'Lync Server 2013: Aktivieren von Benutzern für E9-1-1.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling users for E9-1-1
ms:assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425892(v=OCS.15)
ms:contentKeyID: 48183884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ba29406dc0d7a1140c83a1a9d271afca5d6b0c7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546441"
---
# <a name="enabling-users-for-e9-1-1-in-lync-server-2013"></a>Aktivieren von Benutzern für E9-1-1 in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-06-06_

Während der Clientregistrierung verwendet lync Server eine ortungsrichtlinie, um die E9-1-1-Eigenschaften für Enterprise-VoIP-aktivierte Benutzer zu konfigurieren. Diese Richtlinie enthält die Einstellungen, die definieren, wie E9-1-1 implementiert wird. Die ortungsrichtlinie enthält beispielsweise Informationen wie die Notrufnummern Zeichenfolge und gibt an, ob ein Benutzer einen Speicherort manuell eingeben muss, wenn der Standortinformationsdienst nicht automatisch einen Ort bereitstellt. Eine vollständige Definition einer ortungsrichtlinie finden Sie unter [Definieren der ortungsrichtlinie für lync Server 2013](lync-server-2013-defining-the-location-policy.md).

Lync Server können Clients basierend auf dem Subnetz oder Benutzern basierend auf einer globalen, Standort-oder benutzerbezogenen Richtlinie eine ortungsrichtlinie zuweisen. Beantworten Sie zunächst die folgenden Fragen, bevor Sie sich für eine Methode zum Aktivieren der Benutzer für E9-1-1 entscheiden.

  - **Planen Sie die Aktivierung für alle Benutzer, oder soll die Unterstützung auf spezifische geografische Bereiche innerhalb des Unternehmens beschränkt werden?**  
    Sie können allen Benutzern in Ihrem Unternehmen einen Standort zuweisen, indem Sie eine globale Ortungsrichtlinie verwenden. Durch das Zuweisen einer ortungsrichtlinie zu einem lync Server Netzwerkstandort und das anschließende Hinzufügen von Subnetzen zum Standort können Sie die E9-1 -1-Unterstützung jedoch auf ausgewählte Standorte innerhalb des Unternehmens beschränken und das Routingverhalten für E9-1-1 pro Standort angeben.

<!-- end list -->

  - **Planen Sie die Aktivierung einzelner Benutzer über eine Benutzerrichtlinie?**  
    Sie können bestimmten Benutzern oder Kontaktobjekten von Telefonen in öffentlichen Bereichen direkt Ortungsrichtlinien zuweisen, wenn Sie die E9-1-1-Unterstützung anpassen möchten.

<!-- end list -->

  - **Sollen Clients auch dann für E9-1-1 aktiviert werden, wenn sie sich außerhalb des Netzwerks bewegen oder sich von einem undefinierten Subnetz aus verbinden?**  
    Wenn Benutzern eine globale Standort-, Standort-oder benutzerspezifische ortungsrichtlinie zugewiesen ist, kann Sie zur manuellen Eingabe eines Standorts in den Client verpflichtet werden, wenn sich der Client nicht in einem definierten Subnetz befindet oder wenn der Standortinformationsdienst keinen Ort gefunden hat. Ausführliche Informationen finden Sie unter [Definieren der Benutzeroberfläche für den manuellen Erwerb eines Standorts in lync Server 2013](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md).

</div>

<span> </span>

</div>

</div>

</div>

