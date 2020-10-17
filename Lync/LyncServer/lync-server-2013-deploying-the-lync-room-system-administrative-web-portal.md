---
title: 'Lync Server 2013: Bereitstellen des administrativen Portals für das lync Room-System'
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
ms.openlocfilehash: a7a7f3589f809fa9dfcbfa872653fb4cb8161ea8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522912"
---
# <a name="deploying-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a><span data-ttu-id="aadd9-102">Bereitstellen des Administrator Portals für das lync Room-System in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aadd9-102">Deploying the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aadd9-103">_**Letztes Änderungsstand des Themas:** 2015-05-04_</span><span class="sxs-lookup"><span data-stu-id="aadd9-103">_**Topic Last Modified:** 2015-05-04_</span></span>

<span data-ttu-id="aadd9-104">Das Verwaltungsportal für das Microsoft lync Server 2013 lync-Raumsystem (LRS) ist ein Webportal, mit dem Organisationen ihre lync Room System-Konferenzräume verwalten können.</span><span class="sxs-lookup"><span data-stu-id="aadd9-104">The Microsoft Lync Server 2013 Lync Room System (LRS) Administrative Web Portal is a web portal that organizations can use to maintain their Lync Room System conference rooms.</span></span> <span data-ttu-id="aadd9-105">Administratoren können das LRS-Verwaltungs Webportal zum Überwachen von LRS-Integrität verwenden, beispielsweisedurch Überwachung von miteinander verbundenen Audiogeräten/Videogeräten.</span><span class="sxs-lookup"><span data-stu-id="aadd9-105">Administrators can use the LRS Administrative Web Portal to monitor LRS health, for example by monitoring audio/video devices that are connected.</span></span> <span data-ttu-id="aadd9-106">Mit diesem Portal können Administratoren Remote Diagnoseinformationen sammeln, um die Integrität des Konferenzraums zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="aadd9-106">With this portal, administrators can remotely collect diagnostic information to monitor conference room health.</span></span>

<span data-ttu-id="aadd9-107">Das Verwaltungsportal LRS wird auf jeder lync-Front-End-Server bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="aadd9-107">The LRS Administrative Web Portal is deployed on every Lync Front End Server.</span></span> <span data-ttu-id="aadd9-108">Dieses Handbuch enthält Anweisungen für Administratoren zur Installation und Konfiguration des LRS-Verwaltungsportals.</span><span class="sxs-lookup"><span data-stu-id="aadd9-108">This guide provides instructions for administrators about how to install and configure the LRS Administrative Web Portal.</span></span> <span data-ttu-id="aadd9-109">Sie richtet sich an Administratoren, die über Kenntnisse in lync Server Verwaltung verfügen und über Administratorrechte verfügen, um die lync Server Topologie zu ändern.</span><span class="sxs-lookup"><span data-stu-id="aadd9-109">It is intended for administrators who have knowledge of Lync Server administration, and who have administrator user rights to modify the Lync Server topology.</span></span>

<span data-ttu-id="aadd9-110">Nachdem das LRS-Verwaltungsportal auf dem Server bereitgestellt wurde, können Administratoren den Status aller LRS-Räume überprüfen, indem Sie sich über ihre eigenen Computer oder Laptops an der Website anmelden.</span><span class="sxs-lookup"><span data-stu-id="aadd9-110">After LRS Administrative Web Portal is deployed on the server, administrators can check the status of all LRS rooms by logging on to the site from their own computers or laptops.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="aadd9-111">Wenn Sie das LRS-Verwaltungs Webportal in einer Microsoft lync Server 2013-Bereitstellung installieren, sollten Sie das <A href="https://go.microsoft.com/fwlink/p/?linkid=544806">Microsoft lync Room System-Verwaltungs Webportal für lync Server 2013</A>verwenden.</span><span class="sxs-lookup"><span data-stu-id="aadd9-111">When you install the LRS Administrative Web Portal in a Microsoft Lync Server 2013 deployment, you should use the <A href="https://go.microsoft.com/fwlink/p/?linkid=544806">Microsoft Lync Room System Administrative Web Portal for Lync Server 2013</A>.</span></span><BR><span data-ttu-id="aadd9-112">Es steht eine neue Version des LRS-Verwaltungsportals für Skype for Business Server 2015 zur Verfügung, Sie sollten diese Version jedoch erst installieren, wenn Sie Skype for Business Server 2015 bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="aadd9-112">A new version of the LRS Administrative Web Portal is available for Skype for Business Server 2015, but you should not install that version unless you have deployed Skype for Business Server 2015.</span></span> <span data-ttu-id="aadd9-113">Laden Sie das <A href="https://go.microsoft.com/fwlink/?linkid=544807">Microsoft lync Room System administrative Webportal für Skype for Business Server 2015</A>herunter.</span><span class="sxs-lookup"><span data-stu-id="aadd9-113">Download the <A href="https://go.microsoft.com/fwlink/?linkid=544807">Microsoft Lync Room System Administrative Web Portal for Skype for Business Server 2015</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="aadd9-114">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="aadd9-114">In This Section</span></span>

[<span data-ttu-id="aadd9-115">Konfigurieren der lync Server 2013 Umgebung für das Administrator-Webportal von lync Room System</span><span class="sxs-lookup"><span data-stu-id="aadd9-115">Configuring your Lync Server 2013 environment for the Lync Room System Administrative Web Portal</span></span>](lync-server-2013-configuring-your-environment-for-the-lync-room-system-administrative-web-portal.md)

[<span data-ttu-id="aadd9-116">Installieren des Administrator-Webportals für das lync Room-System in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aadd9-116">Installing the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>](lync-server-2013-installing-the-lync-room-system-administrative-web-portal.md)

[<span data-ttu-id="aadd9-117">Verwenden des Administrator-Webportals von lync Room System in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aadd9-117">Using the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>](lync-server-2013-using-the-lync-room-system-administrative-web-portal.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="aadd9-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aadd9-118">See Also</span></span>


[<span data-ttu-id="aadd9-119">Bereitstellen von Konferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aadd9-119">Deploying conferencing in Lync Server 2013</span></span>](lync-server-2013-deploying-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

