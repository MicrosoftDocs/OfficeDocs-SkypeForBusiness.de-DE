---
title: 'Lync Server 2013: Anzeigen einer Liste vertrauenswürdiger Anwendungen'
description: 'Lync Server 2013: zeigt eine Liste vertrauenswürdiger Anwendungen an.'
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
ms.openlocfilehash: 01d45c682550640c3fc7284e0b60ca6844896b5d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574791"
---
# <a name="view-a-list-of-trusted-applications-in-lync-server-2013"></a><span data-ttu-id="82bbb-103">Anzeigen einer Liste vertrauenswürdiger Anwendungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="82bbb-103">View a list of trusted applications in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82bbb-104">_**Letztes Änderungsstand des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="82bbb-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="82bbb-105">Sie können lync Server 2013 Systemsteuerung verwenden, um eine Liste der vertrauenswürdigen Anwendungen anzuzeigen, die Sie in ihrer lync Server 2013 Umgebung bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="82bbb-105">You can use Lync Server 2013 Control Panel to view a list of the trusted applications that you have deployed in your Lync Server 2013 environment.</span></span> <span data-ttu-id="82bbb-106">Eine vertrauenswürdige Anwendung ist eine Anwendung, die auf Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK basiert und von lync Server 2013 als vertrauenswürdig eingestuft wird.</span><span class="sxs-lookup"><span data-stu-id="82bbb-106">A trusted application is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Lync Server 2013.</span></span> <span data-ttu-id="82bbb-107">Die Eigenschaften dieser Vertrauensbeziehung werden in der folgenden Liste zusammengefasst:</span><span class="sxs-lookup"><span data-stu-id="82bbb-107">This trust relationship is summarized in the following list:</span></span>

  - <span data-ttu-id="82bbb-108">Vertrauenswürdige Anwendungen werden nicht für die Authentifizierung durch lync Server herausgefordert.</span><span class="sxs-lookup"><span data-stu-id="82bbb-108">Trusted applications are not challenged for authentication by Lync Server.</span></span>

  - <span data-ttu-id="82bbb-109">Vertrauenswürdige Anwendungen werden nicht durch lync Server für SIP-Transaktionen, Verbindungen oder ausgehende VoIP-Anrufe (Voice over Internet Protocol) gedrosselt.</span><span class="sxs-lookup"><span data-stu-id="82bbb-109">Trusted applications are not throttled by Lync Server for SIP transactions, connections or outgoing Voice over Internet Protocol (VoIP) calls.</span></span>

  - <span data-ttu-id="82bbb-110">Vertrauenswürdige Anwendungen können die Identität beliebiger Benutzer annehmen und Konferenzen beitreten, ohne in Konferenzlisten aufzutauchen.</span><span class="sxs-lookup"><span data-stu-id="82bbb-110">Trusted applications can impersonate any user and can join conferences without appearing in rosters.</span></span>

  - <span data-ttu-id="82bbb-111">Vertrauenswürdige Anwendungen sind hochverfügbar und ausfallsicher.</span><span class="sxs-lookup"><span data-stu-id="82bbb-111">Trusted applications are highly available and resilient.</span></span>

<span data-ttu-id="82bbb-112">In lync Server-Systemsteuerung können Sie den Namen der Anwendungen, den Pool, in dem Sie ausgeführt werden, und den Port anzeigen, den Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="82bbb-112">In Lync Server Control Panel, you can see the name of the applications, the pool where they run, and the port they use.</span></span>

<div>

## <a name="to-view-a-list-of-trusted-applications"></a><span data-ttu-id="82bbb-113">So zeigen Sie eine Liste der vertrauenswürdigen Anwendungen an</span><span class="sxs-lookup"><span data-stu-id="82bbb-113">To view a list of trusted applications</span></span>

1.  <span data-ttu-id="82bbb-114">Melden Sie sich über ein Benutzerkonto, das der CsServerAdministrator-, CsAdministrator-, "cshelpdesk"-oder CsViewOnlyAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="82bbb-114">From a user account that is assigned to the CsServerAdministrator, CsAdministrator, CsHelpDesk, or CsViewOnlyAdministrator role, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="82bbb-115">Ausführliche Informationen zu den in lync Server 2013 verfügbaren vordefinierten Administratorrollen finden Sie unter [Planning for Role-Based Access Control in lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span><span class="sxs-lookup"><span data-stu-id="82bbb-115">For details about the predefined administrative roles available in Lync Server 2013, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span></span>

2.  <span data-ttu-id="82bbb-116">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="82bbb-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="82bbb-117">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="82bbb-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="82bbb-118">Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Vertrauenswürdige Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="82bbb-118">In the left navigation bar, click **Topology** and the click **Trusted Application**.</span></span>

4.  <span data-ttu-id="82bbb-119">Klicken Sie auf der Seite **Vertrauenswürdige Anwendung** auf eine Spaltenüberschrift, um die Anwendungen bei Bedarf zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="82bbb-119">On the **Trusted Application** page, click a column heading to sort the applications, if needed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="82bbb-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="82bbb-120">See Also</span></span>


[<span data-ttu-id="82bbb-121">Verwalten der lync Server 2013 Topologie</span><span class="sxs-lookup"><span data-stu-id="82bbb-121">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

