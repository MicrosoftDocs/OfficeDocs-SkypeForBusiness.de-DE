---
title: 'Lync Server 2013: Starten oder Beenden von lync Server-Diensten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Start or stop Lync Server 2013 services
ms:assetid: 1c70b4ec-9de5-4f7a-a3c9-c0eb76710505
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520958(v=OCS.15)
ms:contentKeyID: 48183554
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a44e0725aa622b061acc936606bdf2941050952
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847711"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="start-or-stop-lync-server-2013-services"></a><span data-ttu-id="7347c-102">Starten oder Beenden von lync Server 2013-Diensten</span><span class="sxs-lookup"><span data-stu-id="7347c-102">Start or stop Lync Server 2013 services</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7347c-103">_**Letztes Änderungsdatum des Themas:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="7347c-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="7347c-104">Sie können die lync Server-Systemsteuerung verwenden, um alle lync Server 2013-Dienste zu starten oder zu beenden, die auf einem bestimmten Computer ausgeführt werden, oder um einen bestimmten Dienst zu starten oder zu beenden.</span><span class="sxs-lookup"><span data-stu-id="7347c-104">You can use Lync Server Control Panel to start or stop all the Lync Server 2013 services running on a specific computer or to start or stop a specific service.</span></span>

<div>

## <a name="to-start-or-stop-all-lync-server-services-on-a-computer"></a><span data-ttu-id="7347c-105">So starten oder beenden Sie alle lync Server-Dienste auf einem Computer</span><span class="sxs-lookup"><span data-stu-id="7347c-105">To start or stop all Lync Server services on a computer</span></span>

1.  <span data-ttu-id="7347c-106">Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder über entsprechende Benutzerrechte verfügt) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, bei jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie lync Server 2013 bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="7347c-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span> <span data-ttu-id="7347c-107">Sie können feststellen, ob Ihnen die CsServerAdministrator-oder CsAdministrator-RBAC-Rolle zugewiesen wurde, indem Sie einen Befehl wie den folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="7347c-107">You can determine whether you have been assigned the CsServerAdministrator or the CsAdministrator RBAC role by running a command similar to the following:</span></span>
    
        Get-CsAdminRoleAssignment -Identity "kenmyer"

2.  <span data-ttu-id="7347c-108">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="7347c-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7347c-109">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7347c-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7347c-110">Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Status**.</span><span class="sxs-lookup"><span data-stu-id="7347c-110">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="7347c-111">Sortieren oder Durchsuchen Sie auf der **Status** Seite die Liste nach Bedarf, um den Computer zu finden, auf dem die Dienste ausgeführt werden, die Sie starten oder beenden möchten, und klicken Sie darauf.</span><span class="sxs-lookup"><span data-stu-id="7347c-111">On the **Status** page, sort or search through the list as needed to find the computer that is running the services you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="7347c-112">Klicken Sie auf **Aktion**.</span><span class="sxs-lookup"><span data-stu-id="7347c-112">Click **Action**.</span></span>

6.  <span data-ttu-id="7347c-113">Klicken Sie auf **alle Dienste starten** oder **alle Dienste beenden**.</span><span class="sxs-lookup"><span data-stu-id="7347c-113">Click **Start All services** or **Stop All services**.</span></span>

</div>

<div>

## <a name="to-start-or-stop-a-specific-service"></a><span data-ttu-id="7347c-114">So starten oder beenden Sie einen bestimmten Dienst</span><span class="sxs-lookup"><span data-stu-id="7347c-114">To start or stop a specific service</span></span>

1.  <span data-ttu-id="7347c-115">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="7347c-115">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7347c-116">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="7347c-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7347c-117">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7347c-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7347c-118">Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Status**.</span><span class="sxs-lookup"><span data-stu-id="7347c-118">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="7347c-119">Sortieren oder Durchsuchen Sie auf der **Status** Seite die Liste nach Bedarf, um den Computer zu finden, auf dem der Dienst ausgeführt wird, den Sie starten oder beenden möchten, und klicken Sie darauf.</span><span class="sxs-lookup"><span data-stu-id="7347c-119">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="7347c-120">Klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="7347c-120">Click **Properties**.</span></span>

6.  <span data-ttu-id="7347c-121">Sortieren Sie die Liste der Dienste, falls erforderlich, und klicken Sie auf den Dienst, den Sie starten oder beenden möchten.</span><span class="sxs-lookup"><span data-stu-id="7347c-121">Sort the list of services, if necessary, and click the service you want to start or stop.</span></span>

7.  <span data-ttu-id="7347c-122">Klicken Sie auf **Aktion**.</span><span class="sxs-lookup"><span data-stu-id="7347c-122">Click **Action**.</span></span>

8.  <span data-ttu-id="7347c-123">Klicken Sie auf **Dienst starten** oder **Dienst beenden**.</span><span class="sxs-lookup"><span data-stu-id="7347c-123">Click **Start service** or **Stop service**.</span></span>

9.  <span data-ttu-id="7347c-124">Klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="7347c-124">Click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7347c-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7347c-125">See Also</span></span>


[<span data-ttu-id="7347c-126">Verhindern von Sitzungen für Dienste in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7347c-126">Prevent sessions for services in Lync Server 2013</span></span>](lync-server-2013-prevent-sessions-for-services.md)  


[<span data-ttu-id="7347c-127">Verwalten der Lync Server 2013-Topologie</span><span class="sxs-lookup"><span data-stu-id="7347c-127">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

