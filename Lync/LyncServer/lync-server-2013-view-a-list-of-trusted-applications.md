---
title: 'Lync Server 2013: Anzeigen einer Liste vertrauenswürdiger Anwendungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View a list of trusted applications
ms:assetid: f09300b3-67cf-4e70-a51a-23d62479b913
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182604(v=OCS.15)
ms:contentKeyID: 48185844
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d5f9d112e045e753147f7fcffa875177a6feb0d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757499"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-a-list-of-trusted-applications-in-lync-server-2013"></a><span data-ttu-id="609d7-102">Anzeigen einer Liste vertrauenswürdiger Anwendungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="609d7-102">View a list of trusted applications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="609d7-103">_**Letztes Änderungsdatum des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="609d7-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="609d7-104">Sie können die lync Server 2013-Systemsteuerung verwenden, um eine Liste der vertrauenswürdigen Anwendungen anzuzeigen, die Sie in ihrer lync Server 2013-Umgebung bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="609d7-104">You can use Lync Server 2013 Control Panel to view a list of the trusted applications that you have deployed in your Lync Server 2013 environment.</span></span> <span data-ttu-id="609d7-105">Bei einer vertrauenswürdigen Anwendung handelt es sich um eine Anwendung, die auf dem Microsoft Unified Communications Managed API (UCMA) 3,0 Core SDK basiert, das von lync Server 2013 als vertrauenswürdig eingestuft wird.</span><span class="sxs-lookup"><span data-stu-id="609d7-105">A trusted application is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Lync Server 2013.</span></span> <span data-ttu-id="609d7-106">Diese Vertrauensstellung wird in der folgenden Liste zusammengefasst:</span><span class="sxs-lookup"><span data-stu-id="609d7-106">This trust relationship is summarized in the following list:</span></span>

  - <span data-ttu-id="609d7-107">Vertrauenswürdige Anwendungen werden für die Authentifizierung durch lync Server nicht in Frage gestellt.</span><span class="sxs-lookup"><span data-stu-id="609d7-107">Trusted applications are not challenged for authentication by Lync Server.</span></span>

  - <span data-ttu-id="609d7-108">Vertrauenswürdige Anwendungen werden nicht von lync Server für SIP-Transaktionen, Verbindungen oder ausgehende VoIP-Anrufe (Voice over Internet Protocol) gedrosselt.</span><span class="sxs-lookup"><span data-stu-id="609d7-108">Trusted applications are not throttled by Lync Server for SIP transactions, connections or outgoing Voice over Internet Protocol (VoIP) calls.</span></span>

  - <span data-ttu-id="609d7-109">Vertrauenswürdige Anwendungen können sich als alle Benutzer erweisen und können an Konferenzen teilnehmen, ohne dass Sie in Dienstplänen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="609d7-109">Trusted applications can impersonate any user and can join conferences without appearing in rosters.</span></span>

  - <span data-ttu-id="609d7-110">Vertrauenswürdige Anwendungen sind hochgradig verfügbar und widerstandsfähig.</span><span class="sxs-lookup"><span data-stu-id="609d7-110">Trusted applications are highly available and resilient.</span></span>

<span data-ttu-id="609d7-111">In der lync Server-Systemsteuerung können Sie den Namen der Anwendungen, den Pool, in dem Sie ausgeführt werden, und den von Ihnen verwendeten Port sehen.</span><span class="sxs-lookup"><span data-stu-id="609d7-111">In Lync Server Control Panel, you can see the name of the applications, the pool where they run, and the port they use.</span></span>

<div>

## <a name="to-view-a-list-of-trusted-applications"></a><span data-ttu-id="609d7-112">So zeigen Sie eine Liste vertrauenswürdiger Anwendungen an</span><span class="sxs-lookup"><span data-stu-id="609d7-112">To view a list of trusted applications</span></span>

1.  <span data-ttu-id="609d7-113">Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsServerAdministrator“, „CsAdministrator“, „CsHelpDesk“ oder „CsViewOnlyAdministrator“ zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="609d7-113">From a user account that is assigned to the CsServerAdministrator, CsAdministrator, CsHelpDesk, or CsViewOnlyAdministrator role, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="609d7-114">Details zu den vordefinierten Administratorrollen, die in lync Server 2013 zur Verfügung stehen, finden Sie unter [Planen der rollenbasierten Zugriffssteuerung in lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span><span class="sxs-lookup"><span data-stu-id="609d7-114">For details about the predefined administrative roles available in Lync Server 2013, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span></span>

2.  <span data-ttu-id="609d7-115">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="609d7-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="609d7-116">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="609d7-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="609d7-117">Klicken Sie in der linken Navigationsleiste auf **Topologie** , und klicken Sie auf **vertrauenswürdige Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="609d7-117">In the left navigation bar, click **Topology** and the click **Trusted Application**.</span></span>

4.  <span data-ttu-id="609d7-118">Klicken Sie auf der Seite **vertrauenswürdige Anwendung** auf eine Spaltenüberschrift, um die Anwendungen bei Bedarf zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="609d7-118">On the **Trusted Application** page, click a column heading to sort the applications, if needed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="609d7-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="609d7-119">See Also</span></span>


[<span data-ttu-id="609d7-120">Verwalten der Lync Server 2013-Topologie</span><span class="sxs-lookup"><span data-stu-id="609d7-120">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

