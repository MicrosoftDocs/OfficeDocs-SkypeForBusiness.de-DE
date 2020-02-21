---
title: Bereitstellen eines Survivable Branch Appliance-oder Server Zweig-Standort Tasks
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy a Survivable Branch Appliance or Server - branch site task
ms:assetid: 7989ba29-0419-46dd-892c-4ad3238afd56
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398599(v=OCS.15)
ms:contentKeyID: 48184586
ms.date: 10/29/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d17cc327578ff812fb01d61a64348bc0776762bd
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179762"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-a-survivable-branch-appliance-or-server-with-lync-server-2013---branch-site-task"></a><span data-ttu-id="0f142-102">Bereitstelleneiner Survivable Branch Appliance oder eines Servers mit lync Server 2013-Branch-Standort Aufgabe</span><span class="sxs-lookup"><span data-stu-id="0f142-102">Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f142-103">_**Letztes Änderungsstand des Themas:** 2014-10-28_</span><span class="sxs-lookup"><span data-stu-id="0f142-103">_**Topic Last Modified:** 2014-10-28_</span></span>

<span data-ttu-id="0f142-104">Führen Sie eines der beiden in diesem Thema am Zweigstellenstandort beschriebenen Verfahren aus, nachdem Sie die Aufgaben bei der [Bereitstellungeines Survivable Branch Appliance oder Servers mit lync Server 2013-zentralen Websiteaufgaben](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)erfolgreich abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="0f142-104">Perform one of the two procedures described in this topic at the branch site, after successfully completing the tasks in [Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md).</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="0f142-105">Zum Ausführen dieser Vorgehensweise müssen Sie Mitglied der Gruppe "RTCUniversalSBATechnicians" sein.</span><span class="sxs-lookup"><span data-stu-id="0f142-105">To perform this procedure, you must be a member of the RTCUniversalSBATechnicians group.</span></span>



</div>

<div>

## <a name="to-deploy-the-survivable-branch-appliance"></a><span data-ttu-id="0f142-106">So stellen Sie die Survivable Branch Appliance bereit</span><span class="sxs-lookup"><span data-stu-id="0f142-106">To deploy the Survivable Branch Appliance</span></span>

  - <span data-ttu-id="0f142-107">Survivable Branch Appliance-Bereitstellung wird vom Survivable Branch Appliance Anbieter über eine Webbenutzeroberfläche (User Interface, UI) aktiviert.</span><span class="sxs-lookup"><span data-stu-id="0f142-107">Survivable Branch Appliance deployment is enabled by the Survivable Branch Appliance vendor through a web user interface (UI).</span></span> <span data-ttu-id="0f142-108">Informationen zum Bereitstellen des Survivable Branch Appliance finden Sie in der Dokumentation Ihres Survivable Branch Appliance-Anbieters.</span><span class="sxs-lookup"><span data-stu-id="0f142-108">For information about deploying the Survivable Branch Appliance, see your Survivable Branch Appliance vendor documentation.</span></span>

</div>

<div>

## <a name="to-deploy-the-survivable-branch-server"></a><span data-ttu-id="0f142-109">So stellen Sie den Survivable Branch Server bereit</span><span class="sxs-lookup"><span data-stu-id="0f142-109">To deploy the Survivable Branch Server</span></span>

  - <span data-ttu-id="0f142-110">Installieren Sie lync Server 2013 auf einem Computer, auf dem Windows Server 2008 R2, Windows Server 2012 oder Windows Server 2012 R2 installiert ist, genauso wie jede andere lync Server 2013 Server Rolle.</span><span class="sxs-lookup"><span data-stu-id="0f142-110">Install Lync Server 2013 on a computer running Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2, just as you would install any other Lync Server 2013 server role.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="0f142-111">Informationen zum Installieren von lync Server finden Sie unter <A href="lync-server-2013-deploying-lync-server.md">Deploying lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="0f142-111">For information about installing Lync Server, see <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

<span data-ttu-id="0f142-112">**Nächster Schritt**: [Konfigurieren von Benutzern für Ausfallsicherheit für Zweigstellenstandorte in lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span><span class="sxs-lookup"><span data-stu-id="0f142-112">**Next step**: [Configuring users for branch site resiliency in Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0f142-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0f142-113">See Also</span></span>


[<span data-ttu-id="0f142-114">Anhang a: Verwenden von Cmdlets zum Bereitstellen eines Survivable Branch Appliance in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f142-114">Appendix A: Using cmdlets to deploy a Survivable Branch Appliance in Lync Server 2013</span></span>](lync-server-2013-appendix-a-using-cmdlets-to-deploy-a-survivable-branch-appliance.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

