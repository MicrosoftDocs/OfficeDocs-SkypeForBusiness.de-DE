---
title: Autorisieren der Verbindung mit Office Communications Server 2007 R2 Edgeserver
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
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
ms.openlocfilehash: f66f53b5c1aa25324dbd316ad2d72e7d04c42e0f
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755137"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="authorize-connection-to-office-communications-server-2007-r2-edge-server"></a><span data-ttu-id="b0519-102">Autorisieren der Verbindung mit Office Communications Server 2007 R2 Edgeserver</span><span class="sxs-lookup"><span data-stu-id="b0519-102">Authorize connection to Office Communications Server 2007 R2 Edge Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0519-103">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="b0519-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="b0519-104">Für jeden lync Server 2013 Front-End-Server oder Standard Edition-Server im Pilot Pool müssen Sie die Liste der internen Server aktualisieren, die zum Herstellen einer Verbindung mit dem Office Communications Server 2007 R2 Edgeserver autorisiert sind.</span><span class="sxs-lookup"><span data-stu-id="b0519-104">For each Lync Server 2013 Front End Server or Standard Edition server in your pilot pool, you must update the list of internal servers that are authorized to connect to the Office Communications Server 2007 R2 Edge Server.</span></span> <span data-ttu-id="b0519-105">Ohne diese Aktualisierungen sind keine Audio/Video (A/V)-Konferenzen für Benutzer möglich, die den Edgeserver der Vorversion verwenden.</span><span class="sxs-lookup"><span data-stu-id="b0519-105">Without these updates, external audio/visual (A/V) conferencing for users joining by using the legacy Edge Server will not work.</span></span>

<div>

## <a name="to-authorize-connection-to-office-communications-server-2007-r2-edge-server"></a><span data-ttu-id="b0519-106">So autorisieren Sie die Verbindung mit Office Communications Server 2007 R2 Edgeserver</span><span class="sxs-lookup"><span data-stu-id="b0519-106">To Authorize Connection to Office Communications Server 2007 R2 Edge Server</span></span>

1.  <span data-ttu-id="b0519-107">Öffnen Sie in der Office Communications Server 2007 R2 Edgeserver in der Gruppe **Verwaltungs Tools** das Snap-in **Computer Verwaltung** .</span><span class="sxs-lookup"><span data-stu-id="b0519-107">From the Office Communications Server 2007 R2 Edge Server, from the **Administrative Tools** group, open the **Computer Management** snap-in.</span></span>

2.  <span data-ttu-id="b0519-108">Erweitern Sie in der Konsolenstruktur die Option **Dienste und Anwendungen**.</span><span class="sxs-lookup"><span data-stu-id="b0519-108">In the console tree, expand **Services and Applications**.</span></span>

3.  <span data-ttu-id="b0519-109">Klicken Sie mit der rechten Maustaste auf **Office Communications Server 2007 R2** und anschließend auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="b0519-109">Right-click **Office Communications Server 2007 R2**, and then click **Properties**.</span></span>

4.  <span data-ttu-id="b0519-110">Klicken Sie auf die Registerkarte **Intern**.</span><span class="sxs-lookup"><span data-stu-id="b0519-110">Click the **Internal** tab.</span></span>

5.  <span data-ttu-id="b0519-111">Klicken Sie unter **Server hinzufügen** auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="b0519-111">Under **Add Server**, click **Add**.</span></span>

6.  <span data-ttu-id="b0519-112">Geben Sie im Dialogfeld **Office Communications Server hinzufügen** die entsprechenden Informationen ein:</span><span class="sxs-lookup"><span data-stu-id="b0519-112">In the **Add Office Communications Server** dialog box, enter the appropriate information:</span></span>
    
      - <span data-ttu-id="b0519-113">Geben Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) der einzelnen lync Server 2013 Front-End-Server oder Standard Edition-Server und lync Server 2013 Pool an.</span><span class="sxs-lookup"><span data-stu-id="b0519-113">Specify the fully qualified domain name (FQDN) of each Lync Server 2013 Front End Server or Standard Edition server, and Lync Server 2013 pool.</span></span>
    
      - <span data-ttu-id="b0519-114">Geben Sie den FQDN des lync Server 2013 Directors an, wenn Sie eine statische Route im Pool konfiguriert haben, die den Computer für den nächsten Hop nach dem FQDN angibt.</span><span class="sxs-lookup"><span data-stu-id="b0519-114">Specify the FQDN of the Lync Server 2013 Director if you configured a static route on the pool that specifies the next hop computer by its FQDN.</span></span>

7.  <span data-ttu-id="b0519-115">Nachdem Sie einen Eintrag für jeden lync Server 2013, Front-End-Server, Standard Edition-Server, Pool und Director hinzugefügt haben, klicken Sie auf über **nehmen** und dann auf **OK** , um die Eigenschaftenseite zu schließen.</span><span class="sxs-lookup"><span data-stu-id="b0519-115">After you have added an entry for each Lync Server 2013, Front End Server, Standard Edition server, pool, and Director, click **Apply** and then click **OK** to close the Properties page.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

