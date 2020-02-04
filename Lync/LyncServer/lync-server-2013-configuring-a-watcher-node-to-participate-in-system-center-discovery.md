---
title: Konfigurieren eines Watcher-Knotens zur Teilnahme an der System Center Discovery
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to participate in System Center discovery
ms:assetid: 15c5dcfd-603b-47ea-af1b-8714c2ec08af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204704(v=OCS.15)
ms:contentKeyID: 48183500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ca3724f9b5bc8200e2ca006d9fa7445d7368ab7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763489"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-in-lync-server-2013-to-participate-in-system-center-discovery"></a>Konfigurieren eines Watcher-Knotens in lync Server 2013 für die Teilnahme an der System Center Discovery

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-22_

Wenn Sie sicherstellen möchten, dass Ihr Watcher-Knoten am Ermittlungsprozess für System Center Operations Manager teilnimmt, müssen Sie das folgende Verfahren auf einem Computer ausführen, auf dem die System Center Operations Manager-Konsole installiert wurde:

1.  Klicken Sie auf der Registerkarte **Verwaltung** auf **Agent verwaltet**.

2.  Klicken Sie mit der rechten Maustaste auf den Namen des Watcher-Knoten Computers, und klicken Sie dann auf **Eigenschaften**. Wählen Sie im Dialogfeld **Eigenschaften** auf der Registerkarte **Sicherheit** die Option **dieser Agent soll als Proxy fungieren und verwaltete Objekte auf anderen Computern erkennen**aus, und klicken Sie dann auf **OK**.

Nachdem Sie den Watcher-Knoten so konfiguriert haben, dass er als Proxy fungiert, starten Sie den Watcher-Knoten Computer neu. Vergewissern Sie sich nach dem Neustart des Computers, dass im Ereignisprotokoll des Operations-Managers auf diesem Computer keine Fehlerereignisse aufgezeichnet werden. Nachdem der Computer 15 Minuten lang ausgeführt wurde, verwenden Sie die Operations Manager-Konsole, um zu überprüfen, ob Ihre lync Server-Computer unter der **lync** -Kategorie aufgelistet sind.

</div>

<span> </span>

</div>

</div>

</div>

