---
title: 'Lync Server 2013: Bereitstellen des administrativen lync Room System-Webportals'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying the Lync Room System Administrative Web Portal
ms:assetid: ecba5b36-632e-40b9-9c2e-ab825baf7a46
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436324(v=OCS.15)
ms:contentKeyID: 56737621
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16fc5e7d0f136481ddce5d34de41268cb224822e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832522"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a><span data-ttu-id="a11e5-102">Deploying the Lync Room System Administrative Web Portal in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a11e5-102">Deploying the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a11e5-103">_**Letztes Änderungsdatum des Themas:** 2015-05-04_</span><span class="sxs-lookup"><span data-stu-id="a11e5-103">_**Topic Last Modified:** 2015-05-04_</span></span>

<span data-ttu-id="a11e5-104">Das Microsoft lync Server 2013 lync-Verwaltungsportal ist ein Webportal, das Organisationen zum Verwalten Ihrer lync Room-Konferenzräume verwenden können.</span><span class="sxs-lookup"><span data-stu-id="a11e5-104">The Microsoft Lync Server 2013 Lync Room System (LRS) Administrative Web Portal is a web portal that organizations can use to maintain their Lync Room System conference rooms.</span></span> <span data-ttu-id="a11e5-105">Administratoren können das LRS-Verwaltungs Webportal verwenden, um die LRS-Integrität zu überwachen, beispielsweise indem Sie angeschlossene Audio/Videogeräte überwachen.</span><span class="sxs-lookup"><span data-stu-id="a11e5-105">Administrators can use the LRS Administrative Web Portal to monitor LRS health, for example by monitoring audio/video devices that are connected.</span></span> <span data-ttu-id="a11e5-106">Mit diesem Portal können Administratoren über Remoteverbindungen Diagnoseinformationen sammeln, um die Konferenzraumintegrität zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="a11e5-106">With this portal, administrators can remotely collect diagnostic information to monitor conference room health.</span></span>

<span data-ttu-id="a11e5-107">Das administrative LRS-Webportal wird auf jedem lync-Front-End-Server bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="a11e5-107">The LRS Administrative Web Portal is deployed on every Lync Front End Server.</span></span> <span data-ttu-id="a11e5-108">Dieses Handbuch enthält Anweisungen für Administratoren zum Installieren und Konfigurieren des LRS-Verwaltungsportals.</span><span class="sxs-lookup"><span data-stu-id="a11e5-108">This guide provides instructions for administrators about how to install and configure the LRS Administrative Web Portal.</span></span> <span data-ttu-id="a11e5-109">Sie ist für Administratoren vorgesehen, die über Kenntnisse der lync Server-Verwaltung verfügen und über Administratorrechte verfügen, um die lync Server-Topologie zu ändern.</span><span class="sxs-lookup"><span data-stu-id="a11e5-109">It is intended for administrators who have knowledge of Lync Server administration, and who have administrator user rights to modify the Lync Server topology.</span></span>

<span data-ttu-id="a11e5-110">Nachdem das LRS Administrative Web Portal auf dem Server bereitgestellt wurde, können Administratoren den Status aller LRS-Räume überprüfen, indem Sie sich auf Ihren eigenen Computern oder Laptops bei der Website anmelden.</span><span class="sxs-lookup"><span data-stu-id="a11e5-110">After LRS Administrative Web Portal is deployed on the server, administrators can check the status of all LRS rooms by logging on to the site from their own computers or laptops.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a11e5-111">Wenn Sie das administrative LRS-Webportal in einer Microsoft lync Server 2013-Bereitstellung installieren, sollten Sie das administrative Webportal des <A href="http://go.microsoft.com/fwlink/p/?linkid=544806">Microsoft lync Room-Systems für lync Server 2013</A>verwenden.</span><span class="sxs-lookup"><span data-stu-id="a11e5-111">When you install the LRS Administrative Web Portal in a Microsoft Lync Server 2013 deployment, you should use the <A href="http://go.microsoft.com/fwlink/p/?linkid=544806">Microsoft Lync Room System Administrative Web Portal for Lync Server 2013</A>.</span></span><BR><span data-ttu-id="a11e5-112">Eine neue Version des LRS-Administrator-Webportal steht für Skype for Business Server 2015 zur Verfügung, Sie sollten diese Version aber nur installieren, wenn Sie Skype for Business Server 2015 bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="a11e5-112">A new version of the LRS Administrative Web Portal is available for Skype for Business Server 2015, but you should not install that version unless you have deployed Skype for Business Server 2015.</span></span> <span data-ttu-id="a11e5-113">Laden Sie das <A href="http://go.microsoft.com/fwlink/?linkid=544807">Administrative Webportal des Microsoft lync Room-Systems für Skype for Business Server 2015</A>herunter.</span><span class="sxs-lookup"><span data-stu-id="a11e5-113">Download the <A href="http://go.microsoft.com/fwlink/?linkid=544807">Microsoft Lync Room System Administrative Web Portal for Skype for Business Server 2015</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a11e5-114">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a11e5-114">In This Section</span></span>

[<span data-ttu-id="a11e5-115">Configuring your Lync Server 2013 environment for the Lync Room System Administrative Web Portal</span><span class="sxs-lookup"><span data-stu-id="a11e5-115">Configuring your Lync Server 2013 environment for the Lync Room System Administrative Web Portal</span></span>](lync-server-2013-configuring-your-environment-for-the-lync-room-system-administrative-web-portal.md)

[<span data-ttu-id="a11e5-116">Installing the Lync Room System Administrative Web Portal in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a11e5-116">Installing the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>](lync-server-2013-installing-the-lync-room-system-administrative-web-portal.md)

[<span data-ttu-id="a11e5-117">Using the Lync Room System Administrative Web Portal in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a11e5-117">Using the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>](lync-server-2013-using-the-lync-room-system-administrative-web-portal.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a11e5-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a11e5-118">See Also</span></span>


[<span data-ttu-id="a11e5-119">Bereitstellen von Konferenzen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a11e5-119">Deploying conferencing in Lync Server 2013</span></span>](lync-server-2013-deploying-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

