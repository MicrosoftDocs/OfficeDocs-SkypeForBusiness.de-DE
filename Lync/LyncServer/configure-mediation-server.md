---
title: Konfigurieren von Vermittlungsserver
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configure Mediation Server
ms:assetid: 583236fd-33cd-4045-81df-baa58ed07779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204913(v=OCS.15)
ms:contentKeyID: 48184207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72b5742d264efb8c84518511d40195a109594e2a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503372"
---
# <a name="configure-mediation-server"></a><span data-ttu-id="a11ec-102">Konfigurieren von Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="a11ec-102">Configure Mediation Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a11ec-103">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="a11ec-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="a11ec-104">In diesem Verfahren werden die Schritte zum Konfigurieren des lync Server 2013 Pools für die Verwendung der lync Server 2013 Vermittlungsserver anstelle des Legacy-Office Communications Server 2007 R2 Vermittlungsservers erläutert.</span><span class="sxs-lookup"><span data-stu-id="a11ec-104">This procedure details the steps to configure the Lync Server 2013 pool to use the Lync Server 2013 Mediation Server, instead of the legacy Office Communications Server 2007 R2 Mediation Server.</span></span>

<span data-ttu-id="a11ec-p101">Für eine erfolgreiche Veröffentlichung, Aktivierung oder Deaktivierung einer Topologie beim Hinzufügen oder Entfernen einer Serverrolle müssen Sie als Mitglied der Gruppen "RTCUniversalServerAdmins" und "Domänen-Admins" angemeldet sein. Es ist auch möglich, die geeigneten Administratorrechte und -berechtigungen für das Hinzufügen von Serverrollen zu delegieren. Ausführliche Informationen finden Sie unter Delegieren von Setupberechtigungen in der Bereitstellungsdokumentation für Standard Edition-Server oder Enterprise Edition-Server. Für andere Konfigurationsänderungen müssen Sie lediglich Mitglied der Gruppe "RTCUniversalServerAdmins" sein.</span><span class="sxs-lookup"><span data-stu-id="a11ec-p101">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups. It is also possible to delegate the proper administrator rights and permissions for adding server roles. For details, see Delegate Setup Permissions in the Standard Edition server or Enterprise Edition server Deployment documentation. For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a11ec-109">Aktuelle Informationen zur Suche nach qualifizierten PSTN-Gateways, IP-Nebenstellenanlagen und SIP-Trunking-Diensten, die mit lync Server 2013 zusammenarbeiten, finden Sie unter "Microsoft Unified Communications Open Interoperability Program" unter <A href="https://go.microsoft.com/fwlink/p/?linkid=206015">https://go.microsoft.com/fwlink/p/?linkId=206015</A> .</span><span class="sxs-lookup"><span data-stu-id="a11ec-109">For the latest information on finding qualified PSTN gateways, IP-PBXs, and SIP trunking services that work with Lync Server 2013, see "Microsoft Unified Communications Open Interoperability Program" at <A href="https://go.microsoft.com/fwlink/p/?linkid=206015">https://go.microsoft.com/fwlink/p/?linkId=206015</A>.</span></span>



</div>

<div>

## <a name="to-configure-mediation-server-using-topology-builder"></a><span data-ttu-id="a11ec-110">So konfigurieren Sie den Vermittlungsserver mithilfe des Topologie-Generators</span><span class="sxs-lookup"><span data-stu-id="a11ec-110">To configure Mediation Server Using Topology Builder</span></span>

1.  <span data-ttu-id="a11ec-111">Öffnen Sie eine bestehende Topologie im Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="a11ec-111">Open an existing topology from Topology Builder.</span></span>

2.  <span data-ttu-id="a11ec-112">Navigieren Sie im linken Bereich zu **PSTN-Gateways**.</span><span class="sxs-lookup"><span data-stu-id="a11ec-112">In the left pane, navigate to **PSTN gateways**.</span></span>

3.  <span data-ttu-id="a11ec-113">Klicken Sie mit der rechten Maustaste auf **PSTN-Gateways**, und klicken Sie auf **Neues IP/PSTN-Gateway**.</span><span class="sxs-lookup"><span data-stu-id="a11ec-113">Right-click **PSTN gateways**, and then click **New IP/PSTN Gateway**.</span></span>

4.  <span data-ttu-id="a11ec-114">Geben Sie auf der Seite **Neues IP/PSTN-Gateway definieren** die folgenden Informationen ein:</span><span class="sxs-lookup"><span data-stu-id="a11ec-114">Complete the **Define New IP/PSTN Gateway** page with the following information:</span></span>
    
      - <span data-ttu-id="a11ec-p102">Geben Sie einen vollqualifizierten Domänennamen oder eine IP-Adresse für das Gateway ein. Der FQDN des Gateways ist notwendig, wenn das Gateway das TLS-Protokoll verwendet.</span><span class="sxs-lookup"><span data-stu-id="a11ec-p102">Enter the gateway FQDN or IP address. The FQDN of the gateway is required if the gateway uses the TLS protocol.</span></span>
    
      - <span data-ttu-id="a11ec-117">Übernehmen Sie den Standardwert von **Überwachungsport für das IP/PSTN-Gateway**, oder geben Sie den neuen Überwachungsport ein, falls er geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="a11ec-117">Accept the default value of the **Listening port for IP/PSTN gateway** or enter the new listening port if it was modified.</span></span>
    
      - <span data-ttu-id="a11ec-118">Legen Sie das **SIP-Transportprotokoll** fest.</span><span class="sxs-lookup"><span data-stu-id="a11ec-118">Set the **Sip Transport Protocol**.</span></span>

5.  <span data-ttu-id="a11ec-119">Navigieren Sie im linken Bereich zum **Front-End-Pool der Enterprise Edition** oder zum **Standard Edition-Server**.</span><span class="sxs-lookup"><span data-stu-id="a11ec-119">In the left pane, navigate to the **Enterprise Edition Front End pool** or the **Standard Edition Server**.</span></span>

6.  <span data-ttu-id="a11ec-120">Klicken Sie mit der rechten Maustaste auf den Pool, und klicken Sie auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="a11ec-120">Right-click the pool, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="a11ec-121">Legen Sie unter **Vermittlungsserver** die **Überwachungsports** fest.</span><span class="sxs-lookup"><span data-stu-id="a11ec-121">Under **Mediation Server**, set the **Listening ports**.</span></span>

8.  <span data-ttu-id="a11ec-122">Ordnen Sie dann das neu erstellte PSTN-Gateway zu, indem Sie es markieren und auf **Hinzufügen** klicken.</span><span class="sxs-lookup"><span data-stu-id="a11ec-122">Next, associate the newly created PSTN gateway by selecting it and clicking **Add**.</span></span>

9.  <span data-ttu-id="a11ec-123">Wählen Sie im **Topologie-Generator** den obersten Knoten **Lync Server** aus.</span><span class="sxs-lookup"><span data-stu-id="a11ec-123">In **Topology Builder**, select the top-most node **Lync Server**.</span></span>

10. <span data-ttu-id="a11ec-124">Wählen Sie im Menü **Aktion** den Eintrag **Topologie veröffentlichen** aus, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a11ec-124">From the **Action** menu, select **Publish Topology** and then click **Next**.</span></span>

11. <span data-ttu-id="a11ec-125">Klicken Sie nach dem Abschließen des **Veröffentlichungs-Assistenten** auf **Fertig stellen**, um den Assistenten zu schließen.</span><span class="sxs-lookup"><span data-stu-id="a11ec-125">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a11ec-126">Es ist wichtig, dass Sie das nächste Thema durchführen, indem Sie <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">VoIP-Routen so ändern, dass die neue lync Server 2013 Vermittlungsserver verwendet</A> wird, um sicherzustellen, dass die VoIP-Routen auf den richtigen Vermittlungsserver hinweisen.</span><span class="sxs-lookup"><span data-stu-id="a11ec-126">It is important that you complete the next topic, <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">Change voice routes to use the new Lync Server 2013 Mediation Server</A> to ensure that the voice routes are pointing to the correct Mediation Server.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

