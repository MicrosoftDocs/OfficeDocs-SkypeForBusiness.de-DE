---
title: Hinzufügen von lync Server 2013 Survivable Branch Appliance Zweigstellen Standorts zur Topologie
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add Lync Server 2013 Survivable Branch Appliance branch site to your topology
ms:assetid: d3142a37-4606-456d-8ea9-6cc0e51e55f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721896(v=OCS.15)
ms:contentKeyID: 49733830
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b43272cc5ca054f913d51ec157802dc8f847461
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179962"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology"></a><span data-ttu-id="77497-102">Hinzufügen von lync Server 2013 Survivable Branch Appliance Zweigstellen Standorts zur Topologie</span><span class="sxs-lookup"><span data-stu-id="77497-102">Add Lync Server 2013 Survivable Branch Appliance branch site to your topology</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77497-103">_**Letztes Änderungsstand des Themas:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="77497-103">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="77497-104">Microsoft lync Server 2013 Survivable Branch Appliances (SBA) können keinem Microsoft lync Server 2010 Front-End-Pool als Sicherungs Registrierungsstelle zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="77497-104">Microsoft Lync Server 2013 Survivable Branch Appliances (SBA) cannot be associated to a Microsoft Lync Server 2010 Front End pool as a backup Registrar.</span></span> <span data-ttu-id="77497-105">Das SBA muss einem Microsoft lync Server 2013 Front-End-Pool zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="77497-105">The SBA must be associated with a Microsoft Lync Server 2013 Front End pool.</span></span> <span data-ttu-id="77497-106">Bei diesen Schritten wird ein Microsoft lync Server 2013 SBA angenommen.</span><span class="sxs-lookup"><span data-stu-id="77497-106">These steps assume a Microsoft Lync Server 2013 SBA.</span></span> <span data-ttu-id="77497-107">Führen Sie dieses Verfahren am zentralen Standort aus.</span><span class="sxs-lookup"><span data-stu-id="77497-107">Perform this procedure at the central site.</span></span>

<div>

## <a name="to-add-branch-sites-with-microsoft-lync-server-2013-sba-to-your-topology"></a><span data-ttu-id="77497-108">So fügen Sie einer Topologie Zweigstellen mit Microsoft lync Server 2013 SBA hinzu</span><span class="sxs-lookup"><span data-stu-id="77497-108">To add branch sites with Microsoft Lync Server 2013 SBA to your topology</span></span>

1.  <span data-ttu-id="77497-109">Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.</span><span class="sxs-lookup"><span data-stu-id="77497-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="77497-110">Erweitern Sie den zentralen Standort in der Konsolenstruktur, erweitern Sie **Zweigniederlassungen**, und klicken Sie dann auf **Neue Zweigniederlassung**.</span><span class="sxs-lookup"><span data-stu-id="77497-110">In the console tree, expand the central site, expand **Branch Sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="77497-111">Klicken Sie im Dialogfeld **Neue Zweigniederlassung definieren** auf **Name**, und geben Sie einen Namen für die neue Zweigniederlassung ein.</span><span class="sxs-lookup"><span data-stu-id="77497-111">In the **Define New Branch Site** dialog box, click **Name**, and then type a name for the new branch site.</span></span>

4.  <span data-ttu-id="77497-112">(Optional) Klicken Sie auf **Beschreibung**, und geben Sie eine aussagekräftige Beschreibung für die Zweigniederlassung ein.</span><span class="sxs-lookup"><span data-stu-id="77497-112">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="77497-113">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="77497-113">Click **Next**.</span></span>

6.  <span data-ttu-id="77497-114">(Optional) Führen Sie im nächsten Dialogfeld **Neuen Zweigstellenstandort definieren** einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="77497-114">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
      - <span data-ttu-id="77497-115">Klicken Sie auf **Ort**, und geben Sie den Namen der Stadt ein, in der sich der Zweigstellenstandort befindet.</span><span class="sxs-lookup"><span data-stu-id="77497-115">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
      - <span data-ttu-id="77497-116">Klicken Sie auf **Bundesland/Kanton**, und geben Sie den Namen des Bundeslands bzw. Kantons ein, in dem sich der Zweigstellenstandort befindet.</span><span class="sxs-lookup"><span data-stu-id="77497-116">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
      - <span data-ttu-id="77497-117">Klicken Sie auf **Ländercode**, und geben Sie den zweistelligen Ländercode für das Land ein, in dem sich der Zweigstellenstandort befindet.</span><span class="sxs-lookup"><span data-stu-id="77497-117">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="77497-118">Klicken Sie auf **Weiter**, und führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="77497-118">Click **Next**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="77497-119">Wenn Sie eine Survivable Branch Appliance oder Survivable Branch Server an dieser Stelle verwenden, müssen Sie sicherstellen, dass das Kontrollkästchen **neuen überlebten Assistenten öffnen, wenn dieser Assistent geschlossen** wird aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="77497-119">If you are using a Survivable Branch Appliance or Survivable Branch Server at this site, be sure that the **Open the New Survivable Wizard when this wizard closes** check box is selected.</span></span>
    
      - <span data-ttu-id="77497-120">Wenn Sie auf dieser Website keine Survivable Branch Appliance oder Survivable Branch Server verwenden, deaktivieren Sie das Kontrollkästchen **neuen überlebten Assistenten öffnen, wenn dieser Assistent geschlossen** wird.</span><span class="sxs-lookup"><span data-stu-id="77497-120">If you are not using a Survivable Branch Appliance or Survivable Branch Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box.</span></span>
    
      - <span data-ttu-id="77497-121">Klicken Sie auf **Fertig stellen**, und befolgen Sie die Anweisungen im Assistenten, der geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="77497-121">Click **Finish**, and then follow the directions in the wizard that opens.</span></span> <span data-ttu-id="77497-122">Informationen zu Assistenten Elementen finden Sie unter [define a Survivable Branch Appliance or Server in lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span><span class="sxs-lookup"><span data-stu-id="77497-122">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>

8.  <span data-ttu-id="77497-123">Wiederholen Sie die oben beschriebenen Schritte für jeden Zweigstellenstandort, der zur Topologie hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="77497-123">Repeat the previous steps for each branch site that you want to add to the topology.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="77497-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="77497-124">See Also</span></span>


[<span data-ttu-id="77497-125">Definieren einer Survivable Branch Appliance oder eines Servers in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77497-125">Define a Survivable Branch Appliance or Server in Lync Server 2013</span></span>](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)  
[<span data-ttu-id="77497-126">Definieren eines PSTN-Gateways für einen Zweigstellenstandort in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77497-126">Define a PSTN gateway for a branch site in Lync Server 2013</span></span>](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)  
[<span data-ttu-id="77497-127">Konfigurieren eines Trunks mit medienumgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77497-127">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="77497-128">Konfigurieren eines Trunks ohne medienumgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77497-128">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

