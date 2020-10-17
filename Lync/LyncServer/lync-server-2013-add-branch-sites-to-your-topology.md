---
title: 'Lync Server 2013: Hinzufügen von Zweigstellenstandorten zur Topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add branch sites to your topology
ms:assetid: b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412905(v=OCS.15)
ms:contentKeyID: 48185216
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fec919491872df8dc2ab0f843be84d4d0de1c280
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521572"
---
# <a name="add-branch-sites-to-your-topology-in-lync-server-2013"></a><span data-ttu-id="a5507-102">Hinzufügen von Zweigstellenstandorten zu Ihrer Topologie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5507-102">Add branch sites to your topology in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5507-103">_**Letztes Änderungsstand des Themas:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="a5507-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="a5507-p101">Zweigstellenstandorte repräsentieren physische Zweigstellenbüros, die über einen WAN-Link mit Ihren Hauptbüros verbunden sind. Führen Sie dieses Verfahren am zentralen Standort aus, um einen Zweigstellenstandort zu Ihrer Lync-Topologie hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="a5507-p101">Branch sites represent physical branch offices that are connected to your main offices over a WAN link. To add a branch site to your Lync topology, perform this procedure at the central site.</span></span>

<div>

## <a name="to-add-branch-sites-to-your-topology"></a><span data-ttu-id="a5507-106">So fügen Sie Zweigstellenstandorte zu einer Topologie hinzu</span><span class="sxs-lookup"><span data-stu-id="a5507-106">To add branch sites to your topology</span></span>

1.  <span data-ttu-id="a5507-107">Klicken Sie auf **Start**, **Alle Programme**, **Microsoft Lync Server** und anschließend auf **Lync Server-Topologie-Generator**.</span><span class="sxs-lookup"><span data-stu-id="a5507-107">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="a5507-108">Erweitern Sie den zentralen Standort in der Konsolenstruktur, klicken Sie mit der rechten Maustaste auf **Zweigstellenstandorte**, und klicken Sie dann auf **Neuer Zweigstellenstandort**.</span><span class="sxs-lookup"><span data-stu-id="a5507-108">In the console tree, expand the central site, right-click **Branch Sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="a5507-109">Klicken Sie im Dialogfeld **Neuen Zweigstellenstandort definieren** auf **Name**, und geben Sie den Namen für den Zweigstellenstandort ein.</span><span class="sxs-lookup"><span data-stu-id="a5507-109">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>

4.  <span data-ttu-id="a5507-110">(Optional) Klicken Sie auf **Beschreibung**, und geben Sie eine aussagekräftige Beschreibung für den Zweigstellenstandort ein.</span><span class="sxs-lookup"><span data-stu-id="a5507-110">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="a5507-111">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a5507-111">Click **Next**.</span></span>

6.  <span data-ttu-id="a5507-112">(Optional) Führen Sie im nächsten Dialogfeld **Neuen Zweigstellenstandort definieren** einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="a5507-112">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
      - <span data-ttu-id="a5507-113">Klicken Sie auf **Ort**, und geben Sie den Namen der Stadt ein, in der sich der Zweigstellenstandort befindet.</span><span class="sxs-lookup"><span data-stu-id="a5507-113">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
      - <span data-ttu-id="a5507-114">Klicken Sie auf **Bundesland/Kanton**, und geben Sie den Namen des Bundeslands bzw. Kantons ein, in dem sich der Zweigstellenstandort befindet.</span><span class="sxs-lookup"><span data-stu-id="a5507-114">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
      - <span data-ttu-id="a5507-115">Klicken Sie auf **Ländercode**, und geben Sie den zweistelligen Ländercode für das Land ein, in dem sich der Zweigstellenstandort befindet.</span><span class="sxs-lookup"><span data-stu-id="a5507-115">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="a5507-116">Klicken Sie auf **Weiter**, und führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="a5507-116">Click **Next**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="a5507-117">Wenn Sie an dieser Stelle eine Survivable Branch Appliance oder einen Server verwenden, müssen Sie sicherstellen, dass das Kontrollkästchen neuen übermäßigen **Assistenten öffnen, wenn dieser Assistent geschlossen** wird aktiviert ist, klicken Sie auf **Fertig stellen**, und folgen Sie dann den Anweisungen im Assistenten, der geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="a5507-117">If you are using a Survivable Branch Appliance or Server at this site, be sure that the **Open the New Survivable Wizard when this wizard closes** check box is selected, click **Finish**, and then follow the directions in the wizard that opens.</span></span> <span data-ttu-id="a5507-118">Informationen zu Assistenten Elementen finden Sie unter [define a Survivable Branch Appliance or Server in lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span><span class="sxs-lookup"><span data-stu-id="a5507-118">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>
    
      - <span data-ttu-id="a5507-119">Wenn Sie an diesem Standort keinen Survivable Branch Appliance oder Server verwenden, deaktivieren Sie das Kontrollkästchen **neuen überlebten Assistenten öffnen, wenn dieser Assistent geschlossen** wird, und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="a5507-119">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>

8.  <span data-ttu-id="a5507-120">Wiederholen Sie die oben beschriebenen Schritte für jeden Zweigstellenstandort, der zur Topologie hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a5507-120">Repeat the previous steps for each branch site that you want to add to the topology.</span></span>

<span data-ttu-id="a5507-121">**Nächster Schritt:**</span><span class="sxs-lookup"><span data-stu-id="a5507-121">**Next step:**</span></span>

<span data-ttu-id="a5507-122">Bei Survivable Branch Appliances oder Servern: [Definieren einer Survivable Branch Appliance oder eines Servers in lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)</span><span class="sxs-lookup"><span data-stu-id="a5507-122">For Survivable Branch Appliances or Servers: [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)</span></span>

<span data-ttu-id="a5507-123">Für nicht belastbare PSTN-Konnektivität: [definieren Sie ein PSTN-Gateway für einen Zweigstellenstandort in lync Server 2013](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md), [Konfigurieren Sie einen trunk mit medienumgehung in lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md), oder [Konfigurieren Sie einen trunk ohne medienumgehung in lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="a5507-123">For non-resilient PSTN connectivity: [Define a PSTN gateway for a branch site in Lync Server 2013](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md), [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md), or [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

