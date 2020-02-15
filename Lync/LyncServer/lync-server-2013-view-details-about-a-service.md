---
title: 'Lync Server 2013: Anzeigen von Details zu einem Dienst'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View details about a service
ms:assetid: bc8e8202-cd68-47e4-95b2-bb36e51cc124
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182578(v=OCS.15)
ms:contentKeyID: 48185253
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8268720754f0f34fa24a5a5c7beef9ac21b5d3e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048259"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-details-about-a-service-in-lync-server-2013"></a><span data-ttu-id="4851a-102">Anzeigen von Details zu einem Dienst in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4851a-102">View details about a service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4851a-103">_**Letztes Änderungsstand des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="4851a-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="4851a-104">Sie können lync Server-Systemsteuerung verwenden, um Details zu jedem Dienst anzuzeigen, der auf einem bestimmten Computer in Ihrer Topologie läuft.</span><span class="sxs-lookup"><span data-stu-id="4851a-104">You can use Lync Server Control Panel to view details about each service that is running on a specific computer in your topology.</span></span> <span data-ttu-id="4851a-105">Sie können den Status der einzelnen Dienste und Details wie die zugeordneten Datenbanken, Ports und abhängigen Dienste anzeigen.</span><span class="sxs-lookup"><span data-stu-id="4851a-105">You can view the status of each service and details such as the associated databases, ports, and dependent services.</span></span>

<div>

## <a name="to-view-details-for-a-service"></a><span data-ttu-id="4851a-106">So zeigen Sie Details für einen Dienst an</span><span class="sxs-lookup"><span data-stu-id="4851a-106">To view details for a service</span></span>

1.  <span data-ttu-id="4851a-107">Melden Sie sich bei einem Benutzerkonto, das einer der vordefinierten Administratorrollen für lync Server 2013 zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="4851a-107">From a user account that is assigned to any of the predefined administrative roles for Lync Server 2013, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="4851a-108">Ausführliche Informationen zu den in lync Server 2013 verfügbaren vordefinierten Administratorrollen finden Sie unter [Planning for Role-Based Access Control in lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span><span class="sxs-lookup"><span data-stu-id="4851a-108">For details about the predefined administrative roles available in Lync Server 2013, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span></span>

2.  <span data-ttu-id="4851a-109">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="4851a-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4851a-110">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4851a-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4851a-111">Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Status**.</span><span class="sxs-lookup"><span data-stu-id="4851a-111">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="4851a-112">Sortieren oder Durchsuchen Sie die Liste auf der Seite **Status** , und klicken Sie dann auf den Computer, den Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="4851a-112">In the **Status** page, sort or search through the list and then click the computer that you want to view.</span></span>

5.  <span data-ttu-id="4851a-113">Klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="4851a-113">Click **Properties**.</span></span>

6.  <span data-ttu-id="4851a-114">Sortieren Sie im Fenster **Computer Details anzeigen** bei Bedarf die Liste der Dienste, und klicken Sie auf den Dienst, den Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="4851a-114">In the **View Computer Detail** window, sort the list of services, if necessary, and click the service you want to view.</span></span>

7.  <span data-ttu-id="4851a-115">Führen Sie bei Bedarf einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="4851a-115">Do any of the following as needed:</span></span>
    
      - <span data-ttu-id="4851a-116">Klicken Sie auf **Dienststatus abrufen**, um den aktuellen Status des betreffenden Diensts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4851a-116">To see the latest status of that specific service, click **Get service status**.</span></span>
    
      - <span data-ttu-id="4851a-117">Klicken Sie auf **Eigenschaften** , und klicken Sie dann auf **Schließen**, um die Details für diesen bestimmten Dienst anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4851a-117">To see the details for that specific service, click **Properties** and then click **Close**.</span></span>
    
      - <span data-ttu-id="4851a-118">Klicken Sie auf **Schließen**, um zur Liste aller Computer in Ihrer Topologie zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="4851a-118">To return to the list of all computers in your topology, click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4851a-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4851a-119">See Also</span></span>


[<span data-ttu-id="4851a-120">Verwalten der lync Server 2013 Topologie</span><span class="sxs-lookup"><span data-stu-id="4851a-120">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

