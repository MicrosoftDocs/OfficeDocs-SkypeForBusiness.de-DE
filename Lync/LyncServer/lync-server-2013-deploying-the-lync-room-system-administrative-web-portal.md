---
title: 'Lync Server 2013: Bereitstellen des administrativen Portals für das lync Room-System'
description: 'Lync Server 2013: Bereitstellen des administrativen Portals für das lync Room-System.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying the Lync Room System Administrative Web Portal
ms:assetid: ecba5b36-632e-40b9-9c2e-ab825baf7a46
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436324(v=OCS.15)
ms:contentKeyID: 56737621
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e67723b3ddf3f452c53411e560420bb0b043128e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565981"
---
# <a name="deploying-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a><span data-ttu-id="81856-103">Bereitstellen des Administrator Portals für das lync Room-System in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81856-103">Deploying the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81856-104">_**Letztes Änderungsstand des Themas:** 2015-05-04_</span><span class="sxs-lookup"><span data-stu-id="81856-104">_**Topic Last Modified:** 2015-05-04_</span></span>

<span data-ttu-id="81856-105">Das Verwaltungsportal für das Microsoft lync Server 2013 lync-Raumsystem (LRS) ist ein Webportal, mit dem Organisationen ihre lync Room System-Konferenzräume verwalten können.</span><span class="sxs-lookup"><span data-stu-id="81856-105">The Microsoft Lync Server 2013 Lync Room System (LRS) Administrative Web Portal is a web portal that organizations can use to maintain their Lync Room System conference rooms.</span></span> <span data-ttu-id="81856-106">Administratoren können das LRS-Verwaltungs Webportal zum Überwachen von LRS-Integrität verwenden, beispielsweisedurch Überwachung von miteinander verbundenen Audiogeräten/Videogeräten.</span><span class="sxs-lookup"><span data-stu-id="81856-106">Administrators can use the LRS Administrative Web Portal to monitor LRS health, for example by monitoring audio/video devices that are connected.</span></span> <span data-ttu-id="81856-107">Mit diesem Portal können Administratoren Remote Diagnoseinformationen sammeln, um die Integrität des Konferenzraums zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="81856-107">With this portal, administrators can remotely collect diagnostic information to monitor conference room health.</span></span>

<span data-ttu-id="81856-108">Das Verwaltungsportal LRS wird auf jeder lync-Front-End-Server bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="81856-108">The LRS Administrative Web Portal is deployed on every Lync Front End Server.</span></span> <span data-ttu-id="81856-109">Dieses Handbuch enthält Anweisungen für Administratoren zur Installation und Konfiguration des LRS-Verwaltungsportals.</span><span class="sxs-lookup"><span data-stu-id="81856-109">This guide provides instructions for administrators about how to install and configure the LRS Administrative Web Portal.</span></span> <span data-ttu-id="81856-110">Sie richtet sich an Administratoren, die über Kenntnisse in lync Server Verwaltung verfügen und über Administratorrechte verfügen, um die lync Server Topologie zu ändern.</span><span class="sxs-lookup"><span data-stu-id="81856-110">It is intended for administrators who have knowledge of Lync Server administration, and who have administrator user rights to modify the Lync Server topology.</span></span>

<span data-ttu-id="81856-111">Nachdem das LRS-Verwaltungsportal auf dem Server bereitgestellt wurde, können Administratoren den Status aller LRS-Räume überprüfen, indem Sie sich über ihre eigenen Computer oder Laptops an der Website anmelden.</span><span class="sxs-lookup"><span data-stu-id="81856-111">After LRS Administrative Web Portal is deployed on the server, administrators can check the status of all LRS rooms by logging on to the site from their own computers or laptops.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="81856-112">Wenn Sie das LRS-Verwaltungs Webportal in einer Microsoft lync Server 2013-Bereitstellung installieren, sollten Sie das <A href="https://go.microsoft.com/fwlink/p/?linkid=544806">Microsoft lync Room System-Verwaltungs Webportal für lync Server 2013</A>verwenden.</span><span class="sxs-lookup"><span data-stu-id="81856-112">When you install the LRS Administrative Web Portal in a Microsoft Lync Server 2013 deployment, you should use the <A href="https://go.microsoft.com/fwlink/p/?linkid=544806">Microsoft Lync Room System Administrative Web Portal for Lync Server 2013</A>.</span></span><BR><span data-ttu-id="81856-113">Es steht eine neue Version des LRS-Verwaltungsportals für Skype for Business Server 2015 zur Verfügung, Sie sollten diese Version jedoch erst installieren, wenn Sie Skype for Business Server 2015 bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="81856-113">A new version of the LRS Administrative Web Portal is available for Skype for Business Server 2015, but you should not install that version unless you have deployed Skype for Business Server 2015.</span></span> <span data-ttu-id="81856-114">Laden Sie das <A href="https://go.microsoft.com/fwlink/?linkid=544807">Microsoft lync Room System administrative Webportal für Skype for Business Server 2015</A>herunter.</span><span class="sxs-lookup"><span data-stu-id="81856-114">Download the <A href="https://go.microsoft.com/fwlink/?linkid=544807">Microsoft Lync Room System Administrative Web Portal for Skype for Business Server 2015</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="81856-115">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="81856-115">In This Section</span></span>

[<span data-ttu-id="81856-116">Konfigurieren der lync Server 2013 Umgebung für das Administrator-Webportal von lync Room System</span><span class="sxs-lookup"><span data-stu-id="81856-116">Configuring your Lync Server 2013 environment for the Lync Room System Administrative Web Portal</span></span>](lync-server-2013-configuring-your-environment-for-the-lync-room-system-administrative-web-portal.md)

[<span data-ttu-id="81856-117">Installieren des Administrator-Webportals für das lync Room-System in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81856-117">Installing the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>](lync-server-2013-installing-the-lync-room-system-administrative-web-portal.md)

[<span data-ttu-id="81856-118">Verwenden des Administrator-Webportals von lync Room System in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81856-118">Using the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>](lync-server-2013-using-the-lync-room-system-administrative-web-portal.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="81856-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="81856-119">See Also</span></span>


[<span data-ttu-id="81856-120">Bereitstellen von Konferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81856-120">Deploying conferencing in Lync Server 2013</span></span>](lync-server-2013-deploying-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

