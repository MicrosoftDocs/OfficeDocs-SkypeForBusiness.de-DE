---
title: 'Lync Server 2013: Anzeigen von Details zu einem Dienst'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View details about a service
ms:assetid: bc8e8202-cd68-47e4-95b2-bb36e51cc124
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182578(v=OCS.15)
ms:contentKeyID: 48185253
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65fd84ad7290f3b82130f04d8b81955f6ffb4921
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847257"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-details-about-a-service-in-lync-server-2013"></a><span data-ttu-id="721d2-102">Anzeigen von Details zu einem Dienst in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="721d2-102">View details about a service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="721d2-103">_**Letztes Änderungsdatum des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="721d2-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="721d2-104">Sie können die lync Server-Systemsteuerung verwenden, um Details zu jedem Dienst anzuzeigen, der auf einem bestimmten Computer in Ihrer Topologie ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="721d2-104">You can use Lync Server Control Panel to view details about each service that is running on a specific computer in your topology.</span></span> <span data-ttu-id="721d2-105">Sie können den Status jedes Diensts und Details wie die zugehörigen Datenbanken, Ports und abhängigen Dienste anzeigen.</span><span class="sxs-lookup"><span data-stu-id="721d2-105">You can view the status of each service and details such as the associated databases, ports, and dependent services.</span></span>

<div>

## <a name="to-view-details-for-a-service"></a><span data-ttu-id="721d2-106">So zeigen Sie Details zu einem Dienst an</span><span class="sxs-lookup"><span data-stu-id="721d2-106">To view details for a service</span></span>

1.  <span data-ttu-id="721d2-107">Melden Sie sich bei einem Benutzerkonto, das einer der vordefinierten Administratorrollen für lync Server 2013 zugewiesen ist, bei jedem Computer in ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="721d2-107">From a user account that is assigned to any of the predefined administrative roles for Lync Server 2013, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="721d2-108">Details zu den vordefinierten Administratorrollen, die in lync Server 2013 zur Verfügung stehen, finden Sie unter [Planen der rollenbasierten Zugriffssteuerung in lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span><span class="sxs-lookup"><span data-stu-id="721d2-108">For details about the predefined administrative roles available in Lync Server 2013, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span></span>

2.  <span data-ttu-id="721d2-109">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="721d2-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="721d2-110">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="721d2-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="721d2-111">Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Status**.</span><span class="sxs-lookup"><span data-stu-id="721d2-111">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="721d2-112">Sortieren oder Durchsuchen Sie auf der **Status** Seite die Liste, und klicken Sie dann auf den Computer, den Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="721d2-112">In the **Status** page, sort or search through the list and then click the computer that you want to view.</span></span>

5.  <span data-ttu-id="721d2-113">Klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="721d2-113">Click **Properties**.</span></span>

6.  <span data-ttu-id="721d2-114">Sortieren Sie im Fenster **Computer Detail anzeigen** die Liste der Dienste, falls erforderlich, und klicken Sie auf den Dienst, den Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="721d2-114">In the **View Computer Detail** window, sort the list of services, if necessary, and click the service you want to view.</span></span>

7.  <span data-ttu-id="721d2-115">Führen Sie bei Bedarf eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="721d2-115">Do any of the following as needed:</span></span>
    
      - <span data-ttu-id="721d2-116">Wenn Sie den aktuellen Status dieses bestimmten Diensts anzeigen möchten, klicken Sie auf **Dienststatus abrufen**.</span><span class="sxs-lookup"><span data-stu-id="721d2-116">To see the latest status of that specific service, click **Get service status**.</span></span>
    
      - <span data-ttu-id="721d2-117">Wenn Sie die Details für diesen bestimmten Dienst anzeigen möchten, klicken Sie auf **Eigenschaften** , und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="721d2-117">To see the details for that specific service, click **Properties** and then click **Close**.</span></span>
    
      - <span data-ttu-id="721d2-118">Klicken Sie auf **Schließen**, um zur Liste aller Computer in Ihrer Topologie zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="721d2-118">To return to the list of all computers in your topology, click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="721d2-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="721d2-119">See Also</span></span>


[<span data-ttu-id="721d2-120">Verwalten der Lync Server 2013-Topologie</span><span class="sxs-lookup"><span data-stu-id="721d2-120">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

