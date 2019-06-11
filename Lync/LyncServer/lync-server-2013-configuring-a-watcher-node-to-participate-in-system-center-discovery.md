---
title: Konfigurieren eines Watcher-Knotens zur Teilnahme an der System Center Discovery
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a watcher node to participate in System Center discovery
ms:assetid: 15c5dcfd-603b-47ea-af1b-8714c2ec08af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204704(v=OCS.15)
ms:contentKeyID: 48183500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66be6bd0336471626f2ca4e41a89c3a45b073f05
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839296"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-in-lync-server-2013-to-participate-in-system-center-discovery"></a><span data-ttu-id="9cbbe-102">Konfigurieren eines Watcher-Knotens in lync Server 2013 für die Teilnahme an der System Center Discovery</span><span class="sxs-lookup"><span data-stu-id="9cbbe-102">Configuring a watcher node in Lync Server 2013 to participate in System Center discovery</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9cbbe-103">_**Letztes Änderungsdatum des Themas:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="9cbbe-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="9cbbe-104">Wenn Sie sicherstellen möchten, dass Ihr Watcher-Knoten am Ermittlungsprozess für System Center Operations Manager teilnimmt, müssen Sie das folgende Verfahren auf einem Computer ausführen, auf dem die System Center Operations Manager-Konsole installiert wurde:</span><span class="sxs-lookup"><span data-stu-id="9cbbe-104">To make sure that your watcher node participates in the discovery process for System Center Operations Manager, you must complete the following procedure on a computer where the System Center Operations Manager console has been installed:</span></span>

1.  <span data-ttu-id="9cbbe-105">Klicken Sie auf der Registerkarte **Verwaltung** auf **Agent verwaltet**.</span><span class="sxs-lookup"><span data-stu-id="9cbbe-105">On the **Administration** tab, click **Agent Managed**.</span></span>

2.  <span data-ttu-id="9cbbe-106">Klicken Sie mit der rechten Maustaste auf den Namen des Watcher-Knoten Computers, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="9cbbe-106">Right-click the name of the watcher node computer, and then click **Properties**.</span></span> <span data-ttu-id="9cbbe-107">Wählen Sie im Dialogfeld **Eigenschaften** auf der Registerkarte **Sicherheit** die Option **dieser Agent soll als Proxy fungieren und verwaltete Objekte auf anderen Computern erkennen**aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="9cbbe-107">In the **Properties** dialog box, on the **Security** tab, select **Allow this agent to act as a proxy and discover managed objects on other computers**, and then click **OK**.</span></span>

<span data-ttu-id="9cbbe-108">Nachdem Sie den Watcher-Knoten so konfiguriert haben, dass er als Proxy fungiert, starten Sie den Watcher-Knoten Computer neu.</span><span class="sxs-lookup"><span data-stu-id="9cbbe-108">After configuring the watcher node to act as a proxy, reboot the watcher node computer.</span></span> <span data-ttu-id="9cbbe-109">Vergewissern Sie sich nach dem Neustart des Computers, dass im Ereignisprotokoll des Operations-Managers auf diesem Computer keine Fehlerereignisse aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="9cbbe-109">After the computer has rebooted, verify that no error events are being recorded in the Operations Manager event log on that computer.</span></span> <span data-ttu-id="9cbbe-110">Nachdem der Computer 15 Minuten lang ausgeführt wurde, verwenden Sie die Operations Manager-Konsole, um zu überprüfen, ob Ihre lync Server-Computer unter der **lync** -Kategorie aufgelistet sind.</span><span class="sxs-lookup"><span data-stu-id="9cbbe-110">After the computer has been running for 15 minutes or so, use the Operations Manager console to verify that your Lync Server computers are listed under the **Lync** category.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

