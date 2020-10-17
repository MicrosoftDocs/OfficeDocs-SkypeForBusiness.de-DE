---
title: 'Lync Server 2013: Fehler bei der Edgepool, die für lync Server Partnerverbund verwendet wird'
description: 'Lync Server 2013: Fehler bei der Edgepool, die für lync Server Partnerverbund verwendet wird.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over the Edge pool used for Lync Server federation
ms:assetid: 5c9da0f2-7429-40bb-bb3c-5cc4ecb5a13d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688071(v=OCS.15)
ms:contentKeyID: 49733665
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1e7e13ccd35a653d38174f55ace9dc6637ded04
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554911"
---
# <a name="failing-over-the-edge-pool-used-for-lync-server-federation-in-lync-server-2013"></a><span data-ttu-id="1f87a-103">Failover der Edgepool, die für lync Server Partnerverbund in lync Server 2013 verwendet wurden</span><span class="sxs-lookup"><span data-stu-id="1f87a-103">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f87a-104">_**Letztes Änderungsstand des Themas:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="1f87a-104">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="1f87a-105">Wenn der Edge-Pool ausfällt, in dem der Lync Server-Partnerverbund konfiguriert wurde, müssen Sie den Verbund ändern und einen anderen Edgepool für den Partnerverbund angeben.</span><span class="sxs-lookup"><span data-stu-id="1f87a-105">If the Edge pool where you have Lync Server federation configured goes down, you must change federation to use a different Edge pool for federation to work.</span></span>

<div>

## <a name="failing-over-the-edge-pool-used-for-lync-server-federation"></a><span data-ttu-id="1f87a-106">Failover des Edgepools für den Lync Server-Verbund</span><span class="sxs-lookup"><span data-stu-id="1f87a-106">Failing Over the Edge Pool Used for Lync Server Federation</span></span>

1.  <span data-ttu-id="1f87a-p101">Öffnen Sie den Topologie-Generator auf einem Front-End-Server. Erweitern Sie **Edge-Pools**, und klicken Sie mit der rechten Maustaste auf den Edgeserver oder auf den Edgeserverpool, der zurzeit für den Verbund konfiguriert ist. Wählen Sie **Eigenschaften bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="1f87a-p101">On a Front End server, open Topology Builder. Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation. Select **Edit properties**.</span></span>

2.  <span data-ttu-id="1f87a-p102">Klicken Sie unter **Eigenschaften bearbeiten** und **Allgemein** auf **Partnerverbund für diesen Edgepool aktivieren (Port 5061)**. Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="1f87a-p102">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>

3.  <span data-ttu-id="1f87a-p103">Erweitern Sie **Edge-Pools**, und klicken Sie mit der rechten Maustaste auf den Edgeserver oder Edgeserverpool, der jetzt für den Partnerverbund verwendet werden soll. Wählen Sie **Eigenschaften bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="1f87a-p103">Expand **Edge pools**, then right click the Edge server or Edge server pool that you now want to use for Federation. Select **Edit properties**.</span></span>

4.  <span data-ttu-id="1f87a-p104">Klicken Sie unter **Eigenschaften bearbeiten** und **Allgemein** auf **Partnerverbund für diesen Edge-Pool aktivieren (Port 5061)**. Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="1f87a-p104">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>

5.  <span data-ttu-id="1f87a-p105">Klicken Sie auf **Aktion**, wählen Sie **Topologie** und dann **Veröffentlichen** aus. Klicken Sie auf der Seite **Topologie veröffentlichen** nach Aufforderung auf **Weiter**. Klicken Sie nach Abschluss der Veröffentlichung auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="1f87a-p105">Click **Action**, select **Topology**, select **Publish**. When prompted on **Publish the topology**, click **Next**. When the Publish is finished, click **Finish**.</span></span>

6.  <span data-ttu-id="1f87a-p106">Öffnen Sie den Assistenten für die Lync Server-Bereitstellung auf dem Edgeserver. Klicken Sie auf **Lync Server-System installieren oder aktualisieren** und dann auf **Lync Server-Komponenten einrichten oder entfernen**. Klicken Sie auf **Erneut ausführen**.</span><span class="sxs-lookup"><span data-stu-id="1f87a-p106">On the Edge server, open the Lync Server Deployment wizard. Click **Install or Update Lync Server System**, then click **Setup or Remove Lync Server Components**. Click **Run Again**.</span></span>

7.  <span data-ttu-id="1f87a-p107">Klicken Sie unter "Lync Server-Komponenten einrichten" auf **Weiter**. Auf dem Zusammenfassungsbildschirm werden die Aktionen angezeigt, die gerade ausgeführt werden. Klicken Sie nach Abschluss der Bereitstellung auf **Protokoll anzeigen**, um die verfügbaren Protokolldateien anzuzeigen. Klicken Sie auf **Fertig stellen**, um die Bereitstellung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="1f87a-p107">At Setup Lync Server components, click **Next**. The summary screen will show actions as they are executed. Once the deployment is done, click **View Log** to view available log files. Click **Finish** to complete the deployment.</span></span>
    
    <span data-ttu-id="1f87a-126">Wenn der Standort mit dem ausgefallenen Edgepool Front-End-Server enthält, die noch ausgeführt werden, müssen Sie den Webkonferenzdienst und den A/V-Konferenzdienst in diesen Front-End-Pools aktualisieren und für einen Edgepool an einem Remotestandort konfigurieren, der weiterhin ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1f87a-126">If the site containing the failed Edge pool contains Front End Servers that are still running, you must update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to use an Edge pool in a remote site that is still running.</span></span> <span data-ttu-id="1f87a-127">Weitere Informationen finden Sie unter [Ändern der Edgepool, die einem Front-End-Pool in lync Server 2013 zugeordnet sind](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span><span class="sxs-lookup"><span data-stu-id="1f87a-127">For more information, see [Changing the Edge pool associated with a Front End pool in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1f87a-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1f87a-128">See Also</span></span>


[<span data-ttu-id="1f87a-129">Failover der Edgepool, die für den XMPP-Verbund in lync Server 2013 verwendet wurden</span><span class="sxs-lookup"><span data-stu-id="1f87a-129">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  
[<span data-ttu-id="1f87a-130">Zurückgeben der Edgepool, die für lync Server Partnerverbund oder XMPP-Verbund in lync Server 2013 verwendet wurden</span><span class="sxs-lookup"><span data-stu-id="1f87a-130">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)  


[<span data-ttu-id="1f87a-131">Edgeserver Notfallwiederherstellung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f87a-131">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

