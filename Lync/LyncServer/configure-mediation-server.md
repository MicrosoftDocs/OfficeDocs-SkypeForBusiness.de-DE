---
title: Konfigurieren des Vermittlungsservers
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configure Mediation Server
ms:assetid: 583236fd-33cd-4045-81df-baa58ed07779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204913(v=OCS.15)
ms:contentKeyID: 48184207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60bacd308249536aee49101cbcab739a0876343e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839826"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-mediation-server"></a><span data-ttu-id="f96d4-102">Konfigurieren des Vermittlungsservers</span><span class="sxs-lookup"><span data-stu-id="f96d4-102">Configure Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f96d4-103">_**Letztes Änderungsdatum des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="f96d4-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="f96d4-104">In diesem Verfahren werden die Schritte zum Konfigurieren des lync Server 2013-Pools für die Verwendung des lync Server 2013-Vermittlungsservers und nicht des Legacy Office Communications Server 2007 R2-Vermittlungsservers erläutert.</span><span class="sxs-lookup"><span data-stu-id="f96d4-104">This procedure details the steps to configure the Lync Server 2013 pool to use the Lync Server 2013 Mediation Server, instead of the legacy Office Communications Server 2007 R2 Mediation Server.</span></span>

<span data-ttu-id="f96d4-105">Um eine Topologie beim Hinzufügen oder Entfernen einer Serverrolle erfolgreich zu veröffentlichen, zu aktivieren oder zu deaktivieren, sollten Sie als Benutzer angemeldet sein, der Mitglied der Gruppen RTCUniversalServerAdmins und Domänenadministratoren ist.</span><span class="sxs-lookup"><span data-stu-id="f96d4-105">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="f96d4-106">Es ist auch möglich, die richtigen Administratorrechte und-Berechtigungen für das Hinzufügen von Serverrollen zu delegieren.</span><span class="sxs-lookup"><span data-stu-id="f96d4-106">It is also possible to delegate the proper administrator rights and permissions for adding server roles.</span></span> <span data-ttu-id="f96d4-107">Ausführliche Informationen finden Sie unter Delegieren von Setup Berechtigungen in der Standard Edition-Server-oder Enterprise Edition-Server Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="f96d4-107">For details, see Delegate Setup Permissions in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="f96d4-108">Bei anderen Konfigurationsänderungen ist nur die Mitgliedschaft in der RTCUniversalServerAdmins-Gruppe erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f96d4-108">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f96d4-109">Aktuelle Informationen zum Auffinden qualifizierter PSTN-Gateways, IP-PBX-Dienste und SIP-Trunking-Diensten, die mit lync Server 2013 funktionieren, finden Sie unter "Microsoft Unified Communications <A href="http://go.microsoft.com/fwlink/p/?linkid=206015">http://go.microsoft.com/fwlink/p/?linkId=206015</A>Open Interoperability Program" unter.</span><span class="sxs-lookup"><span data-stu-id="f96d4-109">For the latest information on finding qualified PSTN gateways, IP-PBXs, and SIP trunking services that work with Lync Server 2013, see "Microsoft Unified Communications Open Interoperability Program" at <A href="http://go.microsoft.com/fwlink/p/?linkid=206015">http://go.microsoft.com/fwlink/p/?linkId=206015</A>.</span></span>



</div>

<div>

## <a name="to-configure-mediation-server-using-topology-builder"></a><span data-ttu-id="f96d4-110">So konfigurieren Sie den Vermittlungs Server mithilfe des Topologie-Generators</span><span class="sxs-lookup"><span data-stu-id="f96d4-110">To configure Mediation Server Using Topology Builder</span></span>

1.  <span data-ttu-id="f96d4-111">Öffnen Sie eine vorhandene Topologie aus dem Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="f96d4-111">Open an existing topology from Topology Builder.</span></span>

2.  <span data-ttu-id="f96d4-112">Navigieren Sie im linken Bereich zu **PSTN-Gateways**.</span><span class="sxs-lookup"><span data-stu-id="f96d4-112">In the left pane, navigate to **PSTN gateways**.</span></span>

3.  <span data-ttu-id="f96d4-113">Klicken Sie mit der rechten Maustaste auf **PSTN-Gateways**, und klicken Sie dann auf **neues IP/PSTN-Gateway**.</span><span class="sxs-lookup"><span data-stu-id="f96d4-113">Right-click **PSTN gateways**, and then click **New IP/PSTN Gateway**.</span></span>

4.  <span data-ttu-id="f96d4-114">Füllen Sie die Seite **neues IP/PSTN-Gateway definieren** mit den folgenden Informationen aus:</span><span class="sxs-lookup"><span data-stu-id="f96d4-114">Complete the **Define New IP/PSTN Gateway** page with the following information:</span></span>
    
      - <span data-ttu-id="f96d4-115">Geben Sie den FQDN oder die IP-Adresse des Gateways ein.</span><span class="sxs-lookup"><span data-stu-id="f96d4-115">Enter the gateway FQDN or IP address.</span></span> <span data-ttu-id="f96d4-116">Der FQDN des Gateways ist erforderlich, wenn das Gateway das TLS-Protokoll verwendet.</span><span class="sxs-lookup"><span data-stu-id="f96d4-116">The FQDN of the gateway is required if the gateway uses the TLS protocol.</span></span>
    
      - <span data-ttu-id="f96d4-117">Übernehmen Sie den Standardwert des **Überwachungs-Ports für IP/PSTN-Gateway** , oder geben Sie den neuen Abhör-Port ein, wenn er geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="f96d4-117">Accept the default value of the **Listening port for IP/PSTN gateway** or enter the new listening port if it was modified.</span></span>
    
      - <span data-ttu-id="f96d4-118">Setzen Sie das **SIP-Transport Protokoll**.</span><span class="sxs-lookup"><span data-stu-id="f96d4-118">Set the **Sip Transport Protocol**.</span></span>

5.  <span data-ttu-id="f96d4-119">Navigieren Sie im linken Bereich zum **Enterprise Edition-Front-End-Pool** oder zum **Standard Edition-Server**.</span><span class="sxs-lookup"><span data-stu-id="f96d4-119">In the left pane, navigate to the **Enterprise Edition Front End pool** or the **Standard Edition Server**.</span></span>

6.  <span data-ttu-id="f96d4-120">Klicken Sie mit der rechten Maustaste auf den Pool, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="f96d4-120">Right-click the pool, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="f96d4-121">Stellen Sie unter **Mediation Server**die **Abhör Anschlüsse**ein.</span><span class="sxs-lookup"><span data-stu-id="f96d4-121">Under **Mediation Server**, set the **Listening ports**.</span></span>

8.  <span data-ttu-id="f96d4-122">Ordnen Sie anschließend das neu erstellte PSTN-Gateway zu, indem Sie es auswählen und auf **Hinzufügen**klicken.</span><span class="sxs-lookup"><span data-stu-id="f96d4-122">Next, associate the newly created PSTN gateway by selecting it and clicking **Add**.</span></span>

9.  <span data-ttu-id="f96d4-123">Wählen Sie im **Topologie-Generator**den **lync-Server**mit dem höchsten Knoten aus.</span><span class="sxs-lookup"><span data-stu-id="f96d4-123">In **Topology Builder**, select the top-most node **Lync Server**.</span></span>

10. <span data-ttu-id="f96d4-124">Wählen Sie im Menü **Aktion** die Option **Topologie veröffentlichen** aus, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="f96d4-124">From the **Action** menu, select **Publish Topology** and then click **Next**.</span></span>

11. <span data-ttu-id="f96d4-125">Klicken Sie nach Abschluss des Veröffentlichungs- **Assistenten** auf **Fertig stellen** , um den Assistenten zu schließen.</span><span class="sxs-lookup"><span data-stu-id="f96d4-125">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f96d4-126">Es ist wichtig, dass Sie das nächste Thema durchführen, die <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">VoIP-Routen ändern, um den neuen lync Server 2013-Vermittlungsserver zu verwenden</A> , um sicherzustellen, dass die VoIP-Routen auf den richtigen Vermittlungsserver verweisen.</span><span class="sxs-lookup"><span data-stu-id="f96d4-126">It is important that you complete the next topic, <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">Change voice routes to use the new Lync Server 2013 Mediation Server</A> to ensure that the voice routes are pointing to the correct Mediation Server.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

