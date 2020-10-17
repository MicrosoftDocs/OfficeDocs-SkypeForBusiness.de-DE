---
title: Konfigurieren eines Watcher-Knotens für die Teilnahme an der System Center-Ermittlung
description: Konfigurieren eines Watcher-Knotens für die Teilnahme an der System Center-Ermittlung
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
ms.openlocfilehash: d6a42ae77e0c8bde8b8e4de4461180ad00380a5d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564361"
---
# <a name="configuring-a-watcher-node-in-lync-server-2013-to-participate-in-system-center-discovery"></a><span data-ttu-id="b22df-103">Konfigurieren eines Watcher-Knotens in lync Server 2013 zur Teilnahme an der System Center-Ermittlung</span><span class="sxs-lookup"><span data-stu-id="b22df-103">Configuring a watcher node in Lync Server 2013 to participate in System Center discovery</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b22df-104">_**Letztes Änderungsstand des Themas:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="b22df-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="b22df-105">Um sicherzustellen, dass der Watcher-Knoten am Ermittlungsprozess für System Center Operations Manager teilnimmt, müssen Sie das folgende Verfahren auf einem Computer ausführen, auf dem die System Center Operations Manager-Konsole installiert wurde:</span><span class="sxs-lookup"><span data-stu-id="b22df-105">To make sure that your watcher node participates in the discovery process for System Center Operations Manager, you must complete the following procedure on a computer where the System Center Operations Manager console has been installed:</span></span>

1.  <span data-ttu-id="b22df-106">Klicken Sie auf die Registerkarte **Verwaltung** auf **Mit Agents verwaltet**.</span><span class="sxs-lookup"><span data-stu-id="b22df-106">On the **Administration** tab, click **Agent Managed**.</span></span>

2.  <span data-ttu-id="b22df-p101">Klicken Sie mit der rechten Maustaste auf den Namen des Watcher-Knoten-Computers, und klicken Sie dann auf **Eigenschaften**. Wählen Sie im Dialogfeld **Eigenschaften** auf der Registerkarte **Sicherheit** die Option **Dieser Agent soll als Proxyagent fungieren und verwaltete Objekte auf anderen Computern erkennen** aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b22df-p101">Right-click the name of the watcher node computer, and then click **Properties**. In the **Properties** dialog box, on the **Security** tab, select **Allow this agent to act as a proxy and discover managed objects on other computers**, and then click **OK**.</span></span>

<span data-ttu-id="b22df-109">Starten Sie den Watcher-Knoten-Computer neu, nachdem Sie Watcher-Knoten so konfiguriert haben, dass er als Proxy fungiert.</span><span class="sxs-lookup"><span data-stu-id="b22df-109">After configuring the watcher node to act as a proxy, reboot the watcher node computer.</span></span> <span data-ttu-id="b22df-110">Vergewissern Sie sich nach dem Neustart des Computers, dass im Ereignisprotokoll von Operations Manager auf diesem Computer keine Fehlerereignisse aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="b22df-110">After the computer has rebooted, verify that no error events are being recorded in the Operations Manager event log on that computer.</span></span> <span data-ttu-id="b22df-111">Nachdem der Computer 15 Minuten lang ausgeführt wurde, verwenden Sie die Operations Manager-Konsole, um zu überprüfen, ob Ihre lync Server Computer unter der Kategorie **lync** aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="b22df-111">After the computer has been running for 15 minutes or so, use the Operations Manager console to verify that your Lync Server computers are listed under the **Lync** category.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

