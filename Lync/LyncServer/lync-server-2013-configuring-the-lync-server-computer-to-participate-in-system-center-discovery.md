---
title: Konfigurieren des lync Server-Computers für die Teilnahme an der System Center Discovery
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring the Lync Server computer to participate in System Center discovery
ms:assetid: 2f9c9cb0-3120-4571-9cd2-657c2123fe21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204776(v=OCS.15)
ms:contentKeyID: 48183731
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e4b50fad3e0d197259847db9a94bf9e64618d7e2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839171"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-lync-server-2013-computer-to-participate-in-system-center-discovery"></a><span data-ttu-id="af84d-102">Konfigurieren des lync Server 2013-Computers zur Teilnahme an der System Center Discovery</span><span class="sxs-lookup"><span data-stu-id="af84d-102">Configuring the Lync Server 2013 computer to participate in System Center discovery</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af84d-103">_**Letztes Änderungsdatum des Themas:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="af84d-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="af84d-104">Wenn Sie sicherstellen möchten, dass Ihr neuer lync Server-Agent am Ermittlungsprozess für System Center Operations Manager teilnimmt, müssen Sie auf jedem Computer, auf dem die System Center Operations Manager-Konsole installiert wurde, das folgende Verfahren ausführen:</span><span class="sxs-lookup"><span data-stu-id="af84d-104">To make sure that your new Lync Server agent participates in discovery process for System Center Operations Manager, you must complete the following procedure on each computer where the System Center Operations Manager console has been installed:</span></span>

1.  <span data-ttu-id="af84d-105">Klicken Sie auf der Registerkarte **Verwaltung** auf **Agent verwaltet**.</span><span class="sxs-lookup"><span data-stu-id="af84d-105">On the **Administration** tab, click **Agent Managed**.</span></span>

2.  <span data-ttu-id="af84d-106">Klicken Sie mit der rechten Maustaste auf den Namen des Computers und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="af84d-106">Right-click the name of the computer, and then click **Properties**.</span></span> <span data-ttu-id="af84d-107">Wählen Sie im Dialogfeld **Eigenschaften** auf der Registerkarte **Sicherheit** die Option **dieser Agent soll als Proxy fungieren und verwaltete Objekte auf anderen Computern erkennen**aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="af84d-107">In the **Properties** dialog box, on the **Security** tab, select **Allow this agent to act as a proxy and discover managed objects on other computers**, and then click **OK**.</span></span>

<span data-ttu-id="af84d-108">Nachdem Sie Schritt 2 abgeschlossen haben, starten Sie den Integritäts-Agent-Dienst neu.</span><span class="sxs-lookup"><span data-stu-id="af84d-108">After completing step 2, reboot the Health Agent service.</span></span> <span data-ttu-id="af84d-109">(Durch einen Neustart des Diensts wird die Erkennung des neuen Computers erzwungen.</span><span class="sxs-lookup"><span data-stu-id="af84d-109">(Rebooting the service will “force” discovery of the new machine.</span></span> <span data-ttu-id="af84d-110">Wenn Sie den Dienst nicht neu starten, kann es bis zu 4 Stunden dauern, bis der neue Computer von System Center Operations Manager erkannt wird.)</span><span class="sxs-lookup"><span data-stu-id="af84d-110">If you do not reboot the service, it could take as long as 4 hours before the new machine is discovered by System Center Operations Manager.).</span></span> <span data-ttu-id="af84d-111">Vergewissern Sie sich nach dem Neustart des Diensts, dass im Ereignisprotokoll des Operations-Managers auf diesem Computer keine Fehlerereignisse aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="af84d-111">After the service has rebooted, verify that no error events are being recorded in the Operations Manager event log on that computer.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

