---
title: 'Lync Server 2013: Starten oder Beenden von lync Server Diensten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Start or stop Lync Server 2013 services
ms:assetid: 1c70b4ec-9de5-4f7a-a3c9-c0eb76710505
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520958(v=OCS.15)
ms:contentKeyID: 48183554
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4396a6110337cfb9d3abdbd8136c78246b12bced
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007714"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="start-or-stop-lync-server-2013-services"></a><span data-ttu-id="51ac4-102">Starten oder Beenden von lync Server 2013 Diensten</span><span class="sxs-lookup"><span data-stu-id="51ac4-102">Start or stop Lync Server 2013 services</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51ac4-103">_**Letztes Änderungsstand des Themas:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="51ac4-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="51ac4-104">Sie können lync Server-Systemsteuerung verwenden, um alle lync Server 2013-Dienste zu starten oder zu beenden, die auf einem bestimmten Computer laufen, oder um einen bestimmten Dienst zu starten oder zu beenden.</span><span class="sxs-lookup"><span data-stu-id="51ac4-104">You can use Lync Server Control Panel to start or stop all the Lync Server 2013 services running on a specific computer or to start or stop a specific service.</span></span>

<div>

## <a name="to-start-or-stop-all-lync-server-services-on-a-computer"></a><span data-ttu-id="51ac4-105">So starten oder beenden Sie alle Lync Server-Dienste auf einem Computer</span><span class="sxs-lookup"><span data-stu-id="51ac4-105">To start or stop all Lync Server services on a computer</span></span>

1.  <span data-ttu-id="51ac4-106">Melden Sie sich von einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe (oder gleichwertigen Benutzerrechten) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, an jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie lync Server 2013 bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="51ac4-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span> <span data-ttu-id="51ac4-107">Sie können bestimmen, ob Ihnen die CsServerAdministrator-oder die CsAdministrator-RBAC-Rolle zugewiesen wurde, indem Sie einen Befehl wie den folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="51ac4-107">You can determine whether you have been assigned the CsServerAdministrator or the CsAdministrator RBAC role by running a command similar to the following:</span></span>
    
        Get-CsAdminRoleAssignment -Identity "kenmyer"

2.  <span data-ttu-id="51ac4-108">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="51ac4-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="51ac4-109">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="51ac4-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="51ac4-110">Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Status**.</span><span class="sxs-lookup"><span data-stu-id="51ac4-110">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="51ac4-111">Sortieren oder durchsuchen Sie die Liste auf der Seite **Status**, und ermitteln Sie so den Computer, auf dem die Dienste ausgeführt werden, die Sie starten oder beenden möchten. Klicken Sie anschließend auf den Computer.</span><span class="sxs-lookup"><span data-stu-id="51ac4-111">On the **Status** page, sort or search through the list as needed to find the computer that is running the services you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="51ac4-112">Klicken Sie auf **Aktion**.</span><span class="sxs-lookup"><span data-stu-id="51ac4-112">Click **Action**.</span></span>

6.  <span data-ttu-id="51ac4-113">Klicken Sie auf **Alle Dienste starten** bzw. auf **Alle Dienste beenden**.</span><span class="sxs-lookup"><span data-stu-id="51ac4-113">Click **Start All services** or **Stop All services**.</span></span>

</div>

<div>

## <a name="to-start-or-stop-a-specific-service"></a><span data-ttu-id="51ac4-114">So starten oder beenden Sie einen bestimmten Dienst</span><span class="sxs-lookup"><span data-stu-id="51ac4-114">To start or stop a specific service</span></span>

1.  <span data-ttu-id="51ac4-115">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="51ac4-115">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="51ac4-116">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="51ac4-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="51ac4-117">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="51ac4-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="51ac4-118">Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Status**.</span><span class="sxs-lookup"><span data-stu-id="51ac4-118">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="51ac4-119">Sortieren oder durchsuchen Sie die Liste auf der Seite **Status**, um den Computer zu ermitteln, auf dem der Dienst ausgeführt wird, den Sie starten oder beenden möchten. Klicken Sie anschließend auf den Computer.</span><span class="sxs-lookup"><span data-stu-id="51ac4-119">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="51ac4-120">Klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="51ac4-120">Click **Properties**.</span></span>

6.  <span data-ttu-id="51ac4-121">Sortieren Sie ggf. die Liste der Dienste, und klicken Sie auf den Dienst, den Sie starten oder beenden möchten.</span><span class="sxs-lookup"><span data-stu-id="51ac4-121">Sort the list of services, if necessary, and click the service you want to start or stop.</span></span>

7.  <span data-ttu-id="51ac4-122">Klicken Sie auf **Aktion**.</span><span class="sxs-lookup"><span data-stu-id="51ac4-122">Click **Action**.</span></span>

8.  <span data-ttu-id="51ac4-123">Klicken Sie auf **Dienst starten** bzw. auf **Dienst beenden**.</span><span class="sxs-lookup"><span data-stu-id="51ac4-123">Click **Start service** or **Stop service**.</span></span>

9.  <span data-ttu-id="51ac4-124">Klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="51ac4-124">Click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="51ac4-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="51ac4-125">See Also</span></span>


[<span data-ttu-id="51ac4-126">Verhindern von Sitzungen für Dienste in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51ac4-126">Prevent sessions for services in Lync Server 2013</span></span>](lync-server-2013-prevent-sessions-for-services.md)  


[<span data-ttu-id="51ac4-127">Verwalten der lync Server 2013 Topologie</span><span class="sxs-lookup"><span data-stu-id="51ac4-127">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

