---
title: Zurückgeben der Edgepool, die für lync Server Partnerverbund oder XMPP-Partnerverbund verwendet werden
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing back the Edge pool used for Lync Server federation or XMPP federation
ms:assetid: d40097a1-1bed-44dc-aeb6-0871927ab2b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721897(v=OCS.15)
ms:contentKeyID: 49733831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1adafdb90b9ea42d3694410b2103ef0e46aa70b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045948"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="3fb79-102">Zurückgeben der Edgepool, die für lync Server Partnerverbund oder XMPP-Verbund in lync Server 2013 verwendet wurden</span><span class="sxs-lookup"><span data-stu-id="3fb79-102">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3fb79-103">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="3fb79-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="3fb79-104">Nachdem ein ausgefallener Edgepool, von dem der Partnerverbund gehostet wurde, wieder online geschaltet wurde, führen Sie mit diesem Verfahren ein Failback für die Lync Server-Partnerverbundroute und/oder die XMPP-Partnerverbundroute aus, um den wiederhergestellten Edgepool wiederzuverwenden.</span><span class="sxs-lookup"><span data-stu-id="3fb79-104">After a failed Edge pool that used to host federation has been brought back online, use this procedure to fail back the Lync Server federation route and/or the XMPP federation route to again use this restored Edge pool.</span></span>

<div>

## <a name="failing-back-federation-to-a-restored-edge-pool"></a><span data-ttu-id="3fb79-105">Ausführen eines Failbacks für den Partnerverbund für einen wiederhergestellten Edgepool</span><span class="sxs-lookup"><span data-stu-id="3fb79-105">Failing Back Federation to a Restored Edge Pool</span></span>

1.  <span data-ttu-id="3fb79-106">Starten Sie auf dem Edgepool, der nun wieder verfügbar ist, die Edgedienste.</span><span class="sxs-lookup"><span data-stu-id="3fb79-106">On the Edge pool that is now available again, start the Edge Services.</span></span>

2.  <span data-ttu-id="3fb79-107">Führen Sie die folgenden Aktionen aus, wenn Sie ein Failback für die Lync Server-Partnerverbundroute ausführen möchten, um den wiederhergestellten Edgeserver zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="3fb79-107">If you want to fail back the Lync Server federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="3fb79-p101">Öffnen Sie auf einem Front-End-Server den Topologie-Generator. Erweitern Sie **Edgepools**, und klicken Sie dann mit der rechten Maustaste auf den Edgeserver oder Edgeserver-Pool, der aktuell für den Partnerverbund konfiguriert ist. Wählen Sie **Eigenschaften bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="3fb79-p101">On a Front End server, open Topology Builder. Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation. Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="3fb79-p102">Deaktivieren Sie in **Eigenschaften bearbeiten** unter **Allgemein** das Kontrollkästchen **Partnerverbund für diesen Edgepool aktivieren (Port 5061)**. Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3fb79-p102">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>
    
      - <span data-ttu-id="3fb79-p103">Erweitern Sie **Edgepools**, und klicken Sie dann mit der rechten Maustaste auf den ursprünglichen Edgeserver oder Edgeserver-Pool, den Sie wieder für den Partnerverbund verwenden möchten. Wählen Sie **Eigenschaften bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="3fb79-p103">Expand **Edge pools**, then right click the original Edge server or Edge server pool that you again want to use for Federation. Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="3fb79-p104">Aktivieren Sie in **Eigenschaften bearbeiten** unter **Allgemein** das Kontrollkästchen **Partnerverbund für diesen Edgepool aktivieren (Port 5061)**. Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3fb79-p104">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>
    
      - <span data-ttu-id="3fb79-p105">Klicken Sie auf **Aktion**, wählen Sie **Topologie** und dann **Veröffentlichen** aus. Klicken Sie auf der Seite **Topologie veröffentlichen** nach Aufforderung auf **Weiter**. Klicken Sie nach Abschluss der Veröffentlichung auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="3fb79-p105">Click **Action**, select **Topology**, select **Publish**. When prompted on **Publish the topology**, click **Next**. When the Publish is finished, click **Finish**.</span></span>
    
      - <span data-ttu-id="3fb79-p106">Öffnen Sie den Assistenten für die Lync Server-Bereitstellung auf dem Edgeserver. Klicken Sie auf **Lync Server-System installieren oder aktualisieren** und dann auf **Lync Server-Komponenten einrichten oder entfernen**. Klicken Sie auf **Erneut ausführen**.</span><span class="sxs-lookup"><span data-stu-id="3fb79-p106">On the Edge server, open the Lync Server Deployment wizard. Click **Install or Update Lync Server System**, then click **Setup or Remove Lync Server Components**. Click **Run Again**.</span></span>
    
      - <span data-ttu-id="3fb79-p107">Klicken Sie unter "Lync Server-Komponenten einrichten" auf **Weiter**. Auf dem Zusammenfassungsbildschirm werden die Aktionen angezeigt, die gerade ausgeführt werden. Klicken Sie nach Abschluss der Bereitstellung auf **Protokoll anzeigen**, um die verfügbaren Protokolldateien anzuzeigen. Klicken Sie auf **Fertig stellen**, um die Bereitstellung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="3fb79-p107">At Setup Lync Server components, click **Next**. The summary screen will show actions as they are executed. Once the deployment is done, click **View Log** to view available log files. Click **Finish** to complete the deployment.</span></span>

3.  <span data-ttu-id="3fb79-127">Führen Sie die folgenden Aktionen aus, wenn Sie ein Failback für die XMPP-Partnerverbundroute ausführen möchten, um den wiederhergestellten Edgeserver zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="3fb79-127">If you want to fail back the XMPP federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="3fb79-128">Führen Sie das folgende Cmdlet aus, um die XMPP-Partnerverbundroute erneut auf den Edgepool zu verweisen, von dem nun der XMPP-Partnerverbund gehostet wird (in diesem Beispiel EdgeServer1):</span><span class="sxs-lookup"><span data-stu-id="3fb79-128">Run the following cmdlet to repoint the XMPP federation route to the Edge pool which will now host XMPP federation (in this example, EdgeServer1):</span></span>
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        <span data-ttu-id="3fb79-129">In diesem Beispiel ist Site1 der Standort, der den Edgepool enthält, von dem nun die XMPP-Partnerverbundroute gehostet wird. EdgeServer1.contoso.com ist der vollqualifizierte Domänenname (FQDN) eines Edgeservers in diesem Pool.</span><span class="sxs-lookup"><span data-stu-id="3fb79-129">In this example, Site1 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer1.contoso.com is the FQDN of an Edge Server in that pool.</span></span>
    
      - <span data-ttu-id="3fb79-p108">Falls Sie noch keinen DNS-SRV-Eintrag für den XMPP-Partnerverbund haben, der in den Edgepool aufgelöst wird, von dem nun der XMPP-Partnerverbund gehostet wird, müssen Sie ihn wie im folgenden Beispiel dargestellt hinzufügen. Für diesen SRV-Eintrag ist der Portwert 5269 erforderlich.</span><span class="sxs-lookup"><span data-stu-id="3fb79-p108">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example. This SRV record must have a port value of 5269.</span></span>
        
            _xmpp-server._tcp.contoso.com
    
      - <span data-ttu-id="3fb79-132">Ändern Sie auf dem externen DNS-Server den DNS-A-Eintrag für den XMPP-Partnerverbund, sodass er auf EdgeServer2.contoso.com verweist.</span><span class="sxs-lookup"><span data-stu-id="3fb79-132">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>
    
      - <span data-ttu-id="3fb79-133">Überprüfen Sie, ob für den Edgepool, von dem nun der XMPP-Partnerverbund gehostet wird, der Port 5269 extern geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="3fb79-133">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

4.  <span data-ttu-id="3fb79-134">Falls die Front-End-Pools weiter an dem Standort ausgeführt werden, der den ausgefallenen und inzwischen wiederhergestellten Edgepool enthält, sollten Sie den Webkonferenzdienst und den A/V-Konferenzdienst auf diesen Front-End-Pools aktualisieren, sodass wieder die Edgepools am lokalen Standort verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3fb79-134">If the Front End pools remained running in the site containing the Edge pool that failed and has been restored, you should update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to again use the Edge pools at their local site.</span></span> <span data-ttu-id="3fb79-135">Weitere Informationen finden Sie unter [Ändern der Edgepool, die einem Front-End-Pool in lync Server 2013 zugeordnet sind](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span><span class="sxs-lookup"><span data-stu-id="3fb79-135">For more information, see [Changing the Edge pool associated with a Front End pool in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span></span>

5.  <span data-ttu-id="3fb79-136">Falls der Front-End-Pool am selben Standort wie der ausgefallene Edgepool ebenfalls ausgefallen ist, können Sie nun mit Invoke–CsPoolFailback ein Failback auf den Front-End-Pool ausführen.</span><span class="sxs-lookup"><span data-stu-id="3fb79-136">If the Front End pool at the same site as the failed Edge pool also failed, you can now use Invoke–CsPoolFailback to fail back the Front End pool.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3fb79-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3fb79-137">See Also</span></span>


[<span data-ttu-id="3fb79-138">Failover der Edgepool, die für lync Server Partnerverbund in lync Server 2013 verwendet wurden</span><span class="sxs-lookup"><span data-stu-id="3fb79-138">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)  
[<span data-ttu-id="3fb79-139">Failover der Edgepool, die für den XMPP-Verbund in lync Server 2013 verwendet wurden</span><span class="sxs-lookup"><span data-stu-id="3fb79-139">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  


[<span data-ttu-id="3fb79-140">Edgeserver Notfallwiederherstellung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3fb79-140">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

