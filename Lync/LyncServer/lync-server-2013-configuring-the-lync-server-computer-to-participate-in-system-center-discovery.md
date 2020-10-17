---
title: Konfigurieren des lync Server Computers für die Teilnahme an der System Center-Ermittlung
description: Konfigurieren des lync Server Computers für die Teilnahme an der System Center-Ermittlung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the Lync Server computer to participate in System Center discovery
ms:assetid: 2f9c9cb0-3120-4571-9cd2-657c2123fe21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204776(v=OCS.15)
ms:contentKeyID: 48183731
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44d25ba3de673084b2e64e17790a2776cbe57f07
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556851"
---
# <a name="configuring-the-lync-server-2013-computer-to-participate-in-system-center-discovery"></a>Konfigurieren des lync Server 2013 Computers für die Teilnahme an der System Center-Ermittlung

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-20_

Um sicherzustellen, dass Ihr neuer lync Server-Agent am Ermittlungsprozess für System Center Operations Manager teilnimmt, müssen Sie auf jedem Computer, auf dem die System Center Operations Manager-Konsole installiert ist, das folgende Verfahren ausführen:

1.  Klicken Sie auf die Registerkarte **Verwaltung** auf **Mit Agents verwaltet**.

2.  Klicken Sie mit der rechten Maustaste auf den Namen des Computers, und klicken Sie dann auf **Eigenschaften**. Wählen Sie im Dialogfeld **Eigenschaften** auf der Registerkarte **Sicherheit** die Option **Dieser Agent soll als Proxyagent fungieren und verwaltete Objekte auf anderen Computern erkennen** aus, und klicken Sie dann auf **OK**.

Starten Sie den Systemintegritäts-Agent-Dienst neu, nachdem Sie Schritt 2 abgeschlossen haben. (Durch den Neustart des Diensts wird die Erkennung des neuen Computers "erzwungen". Wenn Sie den Dienst nicht neu starten, kann es bis zu 4 Stunden dauern, bis der neue Computer vom System Center Operations Manager erkannt wird.). Stellen Sie nach dem Neustart des Diensts sicher, dass im System Center Operations Manager-Ereignisprotokoll keine Fehlerereignisse aufgezeichnet werden.

</div>

<span> </span>

</div>

</div>

</div>

