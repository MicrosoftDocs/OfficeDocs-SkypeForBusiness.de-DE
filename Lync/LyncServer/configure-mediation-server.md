---
title: Konfigurieren des Vermittlungsservers
TOCTitle: Configure Mediation Server
ms:assetid: 583236fd-33cd-4045-81df-baa58ed07779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204913(v=OCS.15)
ms:contentKeyID: 48184207
ms.date: 07/23/2014
mtps_version: v=OCS.15
ms.openlocfilehash: 143d98cebc151473b790246bc78d75e6e2f4185a
ms.sourcegitcommit: a599bdd5057c4fc38e14b4f14961e1a6bf08ee8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/05/2018
ms.locfileid: "27128168"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-mediation-server"></a><span data-ttu-id="04f9f-102">Konfigurieren des Vermittlungsservers</span><span class="sxs-lookup"><span data-stu-id="04f9f-102">Configure Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="04f9f-103">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="04f9f-103"></span></span>

<span data-ttu-id="04f9f-104">_**Letztes Änderungsdatum des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="04f9f-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="04f9f-105">In diesem Verfahren werden die Schritte zum Konfigurieren des Lync Server 2013 Pools für die Verwendung des Lync Server 2013 Vermittlungsservers anstelle der Vorversion Office Communications Server 2007 R2 Mediation Server verwenden.</span><span class="sxs-lookup"><span data-stu-id="04f9f-105">This procedure details the steps to configure the Lync Server 2013 pool to use the Lync Server 2013 Mediation Server, instead of the legacy Office Communications Server 2007 R2 Mediation Server.</span></span>

<span data-ttu-id="04f9f-106">Erfolgreich veröffentlichen, aktivieren oder Deaktivieren einer Topologie, die beim Hinzufügen oder Entfernen einer Serverrolle, Sie sollte als ein Benutzer ein Mitglied der Gruppen RTCUniversalServerAdmins und Domänen-Admins angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="04f9f-106">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="04f9f-107">Es ist auch möglich, die richtigen Administratorrechte und Berechtigungen für das Hinzufügen von Serverrollen zu delegieren.</span><span class="sxs-lookup"><span data-stu-id="04f9f-107">It is also possible to delegate the proper administrator rights and permissions for adding server roles.</span></span> <span data-ttu-id="04f9f-108">Weitere Informationen hierzu finden Sie unter Delegate Setup Permissions in der Standard Edition-Server oder Enterprise Edition-Server-Dokumentation zur Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="04f9f-108">For details, see Delegate Setup Permissions in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="04f9f-109">Für weitere konfigurationsänderungen ist nur die Mitgliedschaft in der Gruppe RTCUniversalServerAdmins ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="04f9f-109">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="04f9f-110">Aktuelle Informationen über das Auffinden von qualifizierten PSTN-Gateways, IP-PBXs und SIP-Trunking-Diensten, die mit Lync Server 2013 arbeiten, finden Sie unter "Microsoft Unified Communications Open Interoperability Program" unter <A href="http://go.microsoft.com/fwlink/p/?linkid=206015">http://go.microsoft.com/fwlink/p/?linkId=206015</A>.</span><span class="sxs-lookup"><span data-stu-id="04f9f-110">For the latest information on finding qualified PSTN gateways, IP-PBXs, and SIP trunking services that work with Lync Server 2013, see "Microsoft Unified Communications Open Interoperability Program" at <A href="http://go.microsoft.com/fwlink/p/?linkid=206015">http://go.microsoft.com/fwlink/p/?linkId=206015</A>.</span></span>



</div>

<div>

## <a name="to-configure-mediation-server-using-topology-builder"></a><span data-ttu-id="04f9f-111">So konfigurieren Sie Mediation Server Using Topologie-Generator</span><span class="sxs-lookup"><span data-stu-id="04f9f-111">To configure Mediation Server Using Topology Builder</span></span>

1.  <span data-ttu-id="04f9f-112">Öffnen Sie eine vorhandene Topologie Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="04f9f-112">Open an existing topology from Topology Builder.</span></span>

2.  <span data-ttu-id="04f9f-113">Navigieren Sie im linken Bereich zu **PSTN-Gateways**.</span><span class="sxs-lookup"><span data-stu-id="04f9f-113">In the left pane, navigate to **PSTN gateways**.</span></span>

3.  <span data-ttu-id="04f9f-114">Mit der rechten Maustaste **PSTN-Gateways**, und klicken Sie dann auf **Neues IP/PSTN-Gateway**.</span><span class="sxs-lookup"><span data-stu-id="04f9f-114">Right-click **PSTN gateways**, and then click **New IP/PSTN Gateway**.</span></span>

4.  <span data-ttu-id="04f9f-115">Führen Sie die Seite **Neues IP/PSTN-Gateway definieren** die folgenden Informationen ein:</span><span class="sxs-lookup"><span data-stu-id="04f9f-115">Complete the **Define New IP/PSTN Gateway** page with the following information:</span></span>
    
      - <span data-ttu-id="04f9f-116">Geben Sie das Gateway-FQDN oder die IP-Adresse ein.</span><span class="sxs-lookup"><span data-stu-id="04f9f-116">Enter the gateway FQDN or IP address.</span></span> <span data-ttu-id="04f9f-117">Der FQDN des Gateways ist erforderlich, wenn das Gateway TLS-Protokoll verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="04f9f-117">The FQDN of the gateway is required if the gateway uses the TLS protocol.</span></span>
    
      - <span data-ttu-id="04f9f-118">Akzeptieren Sie den Standardwert des **Überwachungsport für IP/PSTN-Gateway** , oder geben Sie den neuen Überwachungsport ein, falls er geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="04f9f-118">Accept the default value of the **Listening port for IP/PSTN gateway** or enter the new listening port if it was modified.</span></span>
    
      - <span data-ttu-id="04f9f-119">Legen Sie die **Sip-Transportprotokoll fest**.</span><span class="sxs-lookup"><span data-stu-id="04f9f-119">Set the **Sip Transport Protocol**.</span></span>

5.  <span data-ttu-id="04f9f-120">Navigieren Sie im linken Bereich der **Enterprise Edition-Front-End-Pool** oder **Standard Edition-Server**.</span><span class="sxs-lookup"><span data-stu-id="04f9f-120">In the left pane, navigate to the **Enterprise Edition Front End pool** or the **Standard Edition Server**.</span></span>

6.  <span data-ttu-id="04f9f-121">Mit der rechten Maustaste in des Pools, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="04f9f-121">Right-click the pool, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="04f9f-122">Klicken Sie unter **Vermittlungsserver**die **Überwachungsports**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="04f9f-122">Under **Mediation Server**, set the **Listening ports**.</span></span>

8.  <span data-ttu-id="04f9f-123">Ordnen Sie im nächsten Schritt das neu erstellte PSTN-Gateway, indem Sie es markieren und auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="04f9f-123">Next, associate the newly created PSTN gateway by selecting it and clicking **Add**.</span></span>

9.  <span data-ttu-id="04f9f-124">Wählen Sie im **Topologie-Generator**den obersten Knoten **Lync Server**aus.</span><span class="sxs-lookup"><span data-stu-id="04f9f-124">In **Topology Builder**, select the top-most node **Lync Server**.</span></span>

10. <span data-ttu-id="04f9f-125">Klicken Sie im Menü **Aktion** wählen Sie **Topologie veröffentlichen** aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="04f9f-125">From the **Action** menu, select **Publish Topology** and then click **Next**.</span></span>

11. <span data-ttu-id="04f9f-126">Wenn der **Veröffentlichen-Assistent** abgeschlossen ist, klicken Sie auf **Fertig stellen** , um den Assistenten zu schließen.</span><span class="sxs-lookup"><span data-stu-id="04f9f-126">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="04f9f-127">Es ist wichtig, schließen Sie das nächste Thema <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">Ändern VoIP-Routen für die neue Lync Server 2013-Vermittlungsservers verwenden</A> , um sicherzustellen, dass die VoIP-Routen auf den richtigen Vermittlungsserver zeigen.</span><span class="sxs-lookup"><span data-stu-id="04f9f-127">It is important that you complete the next topic, <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">Change voice routes to use the new Lync Server 2013 Mediation Server</A> to ensure that the voice routes are pointing to the correct Mediation Server.</span></span>



<span data-ttu-id="04f9f-128"></div>

</div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="04f9f-128"></span></span></div>

