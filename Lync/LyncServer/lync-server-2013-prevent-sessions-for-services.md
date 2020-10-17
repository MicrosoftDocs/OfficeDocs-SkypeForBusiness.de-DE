---
title: 'Lync Server 2013: verhindern von Sitzungen für Dienste'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prevent sessions for services
ms:assetid: 977dcc5c-2aac-48ef-86a1-a8d47b4d9e74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182553(v=OCS.15)
ms:contentKeyID: 48184866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6bfb2316de9ea09db49ac22e0cf0addd0a699739
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513242"
---
# <a name="prevent-sessions-for-services-in-lync-server-2013"></a><span data-ttu-id="97f8a-102">Verhindern von Sitzungen für Dienste in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97f8a-102">Prevent sessions for services in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97f8a-103">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="97f8a-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="97f8a-104">Sie können lync Server-Systemsteuerung verwenden, um neue Sitzungen für alle lync Server 2013-Dienste zu verhindern, die auf einem bestimmten Computer auszuführen sind, oder um neue Sitzungen für einen bestimmten lync Server 2013 Dienst zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="97f8a-104">You can use Lync Server Control Panel to prevent new sessions for all the Lync Server 2013 services running on a specific computer or to prevent new sessions for a specific Lync Server 2013 service.</span></span>

<div>

## <a name="to-prevent-new-sessions-for-all-lync-server-services-on-a-computer"></a><span data-ttu-id="97f8a-105">So verhindern Sie neue Sitzungen für alle Lync Server-Dienste auf einem Computer</span><span class="sxs-lookup"><span data-stu-id="97f8a-105">To prevent new sessions for all Lync Server services on a computer</span></span>

1.  <span data-ttu-id="97f8a-106">Melden Sie sich von einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe (oder gleichwertigen Benutzerrechten) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, an jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie lync Server 2013 bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="97f8a-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="97f8a-107">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="97f8a-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="97f8a-108">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="97f8a-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="97f8a-109">Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Status**.</span><span class="sxs-lookup"><span data-stu-id="97f8a-109">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="97f8a-110">Sortieren oder durchsuchen Sie auf der Seite **Status** die Liste, um den Computer zu ermitteln, auf dem die Dienste ausgeführt werden, für die Sie neue Sitzungen verhindern möchten. Klicken Sie anschließend auf den Computer.</span><span class="sxs-lookup"><span data-stu-id="97f8a-110">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span>

5.  <span data-ttu-id="97f8a-111">Klicken Sie auf **Aktion**.</span><span class="sxs-lookup"><span data-stu-id="97f8a-111">Click **Action**.</span></span>

6.  <span data-ttu-id="97f8a-112">Klicken Sie auf **Neue Sitzungen für alle Dienste verhindern**.</span><span class="sxs-lookup"><span data-stu-id="97f8a-112">Click **Prevent new sessions for all services**.</span></span>

</div>

<div>

## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="97f8a-113">So verhindern Sie neue Sitzungen für einen bestimmten Dienst</span><span class="sxs-lookup"><span data-stu-id="97f8a-113">To prevent new sessions for a specific service</span></span>

1.  <span data-ttu-id="97f8a-114">Melden Sie sich von einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe (oder gleichwertigen Benutzerrechten) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, an jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie lync Server 2013 bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="97f8a-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="97f8a-115">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="97f8a-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="97f8a-116">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="97f8a-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="97f8a-117">Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Status**.</span><span class="sxs-lookup"><span data-stu-id="97f8a-117">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="97f8a-118">Sortieren oder durchsuchen Sie die Liste auf der Seite **Status**, um den Computer zu ermitteln, auf dem der Dienst ausgeführt wird, den Sie starten oder beenden möchten. Klicken Sie anschließend auf den Computer.</span><span class="sxs-lookup"><span data-stu-id="97f8a-118">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="97f8a-119">Klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="97f8a-119">Click **Properties**.</span></span>

6.  <span data-ttu-id="97f8a-120">Sortieren Sie ggf. die Liste der Dienste, und klicken Sie auf den Dienst, für den Sie neue Sitzungen verhindern möchten.</span><span class="sxs-lookup"><span data-stu-id="97f8a-120">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>

7.  <span data-ttu-id="97f8a-121">Klicken Sie auf **Aktion**.</span><span class="sxs-lookup"><span data-stu-id="97f8a-121">Click **Action**.</span></span>

8.  <span data-ttu-id="97f8a-122">Klicken Sie auf **Neue Sitzungen für Dienst verhindern**.</span><span class="sxs-lookup"><span data-stu-id="97f8a-122">Click **Prevent new sessions for service**.</span></span>

9.  <span data-ttu-id="97f8a-123">Klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="97f8a-123">Click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="97f8a-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="97f8a-124">See Also</span></span>


[<span data-ttu-id="97f8a-125">Verwalten der lync Server 2013 Topologie</span><span class="sxs-lookup"><span data-stu-id="97f8a-125">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

