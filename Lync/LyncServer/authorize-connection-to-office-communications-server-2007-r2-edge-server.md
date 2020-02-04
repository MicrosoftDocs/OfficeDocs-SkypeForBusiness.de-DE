---
title: Autorisieren der Verbindung zu Office Communications Server 2007 R2 Edge Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Authorize connection to Office Communications Server 2007 R2 Edge Server
ms:assetid: 14f6798a-28d6-4b3d-8734-942192e1bbf5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204702(v=OCS.15)
ms:contentKeyID: 48183493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8dbce32a12f05dff768d23a2bdccfe1b84a567cb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724215"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="authorize-connection-to-office-communications-server-2007-r2-edge-server"></a><span data-ttu-id="db38d-102">Autorisieren der Verbindung zu Office Communications Server 2007 R2 Edge Server</span><span class="sxs-lookup"><span data-stu-id="db38d-102">Authorize connection to Office Communications Server 2007 R2 Edge Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db38d-103">_**Letztes Änderungsdatum des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="db38d-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="db38d-104">Für jeden lync Server 2013-Front-End-Server oder Standard Edition-Server in Ihrem Pilot Pool müssen Sie die Liste der internen Server aktualisieren, die zum Herstellen einer Verbindung mit dem Office Communications Server 2007 R2 Edge-Server autorisiert sind.</span><span class="sxs-lookup"><span data-stu-id="db38d-104">For each Lync Server 2013 Front End Server or Standard Edition server in your pilot pool, you must update the list of internal servers that are authorized to connect to the Office Communications Server 2007 R2 Edge Server.</span></span> <span data-ttu-id="db38d-105">Ohne diese Updates funktionieren externe Audio/visuelle (A/V)-Konferenzen für Benutzer, die mit dem Legacy-Edgeserver verbunden sind, nicht.</span><span class="sxs-lookup"><span data-stu-id="db38d-105">Without these updates, external audio/visual (A/V) conferencing for users joining by using the legacy Edge Server will not work.</span></span>

<div>

## <a name="to-authorize-connection-to-office-communications-server-2007-r2-edge-server"></a><span data-ttu-id="db38d-106">So autorisieren Sie die Verbindung zu Office Communications Server 2007 R2 Edge Server</span><span class="sxs-lookup"><span data-stu-id="db38d-106">To Authorize Connection to Office Communications Server 2007 R2 Edge Server</span></span>

1.  <span data-ttu-id="db38d-107">Öffnen Sie auf dem Office Communications Server 2007 R2-Edgeserver in der Gruppe **Administrative Tools** das Snap-in **Computer Verwaltung** .</span><span class="sxs-lookup"><span data-stu-id="db38d-107">From the Office Communications Server 2007 R2 Edge Server, from the **Administrative Tools** group, open the **Computer Management** snap-in.</span></span>

2.  <span data-ttu-id="db38d-108">Erweitern Sie in der Konsolenstruktur **Dienste und Anwendungen**.</span><span class="sxs-lookup"><span data-stu-id="db38d-108">In the console tree, expand **Services and Applications**.</span></span>

3.  <span data-ttu-id="db38d-109">Klicken Sie mit der rechten Maustaste auf **Office Communications Server 2007 R2**, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="db38d-109">Right-click **Office Communications Server 2007 R2**, and then click **Properties**.</span></span>

4.  <span data-ttu-id="db38d-110">Klicken Sie auf die Registerkarte **intern** .</span><span class="sxs-lookup"><span data-stu-id="db38d-110">Click the **Internal** tab.</span></span>

5.  <span data-ttu-id="db38d-111">Klicken Sie unter **Server hinzufügen**auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="db38d-111">Under **Add Server**, click **Add**.</span></span>

6.  <span data-ttu-id="db38d-112">Geben Sie im Dialogfeld **Office Communications Server hinzufügen** die entsprechenden Informationen ein:</span><span class="sxs-lookup"><span data-stu-id="db38d-112">In the **Add Office Communications Server** dialog box, enter the appropriate information:</span></span>
    
      - <span data-ttu-id="db38d-113">Geben Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) jedes lync Server 2013-Front-End-Servers oder Standard Edition-Servers und lync Server 2013-Pools an.</span><span class="sxs-lookup"><span data-stu-id="db38d-113">Specify the fully qualified domain name (FQDN) of each Lync Server 2013 Front End Server or Standard Edition server, and Lync Server 2013 pool.</span></span>
    
      - <span data-ttu-id="db38d-114">Geben Sie den FQDN des lync Server 2013-Directors an, wenn Sie eine statische Route im Pool konfiguriert haben, die den Computer für den nächsten Hop nach dem FQDN angibt.</span><span class="sxs-lookup"><span data-stu-id="db38d-114">Specify the FQDN of the Lync Server 2013 Director if you configured a static route on the pool that specifies the next hop computer by its FQDN.</span></span>

7.  <span data-ttu-id="db38d-115">Nachdem Sie einen Eintrag für jeden lync Server 2013, Front-End-Server, Standard Edition-Server,-Pool und-Director hinzugefügt haben, klicken Sie auf über **nehmen** , und klicken Sie dann auf **OK** , um die Seite Eigenschaften zu schließen.</span><span class="sxs-lookup"><span data-stu-id="db38d-115">After you have added an entry for each Lync Server 2013, Front End Server, Standard Edition server, pool, and Director, click **Apply** and then click **OK** to close the Properties page.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

