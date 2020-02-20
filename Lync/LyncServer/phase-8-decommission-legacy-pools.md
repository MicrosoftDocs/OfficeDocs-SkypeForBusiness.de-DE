---
title: 'Phase 8: Außerbetriebnahme von Legacy Pools'
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: 'Phase 8: Decommission legacy pools'
ms:assetid: 1c68e5d8-fb5f-45e6-b6e3-27f5e830c966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204724(v=OCS.15)
ms:contentKeyID: 48183557
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58ec7d07725ee75e5f20897894f465ac9fb269a4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148424"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="phase-8-decommission-legacy-pools"></a><span data-ttu-id="d5d86-102">Phase 8: Außerbetriebnahme von Legacy Pools</span><span class="sxs-lookup"><span data-stu-id="d5d86-102">Phase 8: Decommission legacy pools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5d86-103">_**Letztes Änderungsstand des Themas:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="d5d86-103">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="d5d86-104">Das folgende Thema bietet Anleitungen zum Aktualisieren von DNS-Einträgen, zum Verschieben des Inhalts Verwaltungsservers, zur Außerbetriebnahme von Pools und zum Deaktivieren und Entfernen von Servern und Pools aus einer Legacy Bereitstellung von lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="d5d86-104">The following topic provides guidance in updating DNS entries, moving the Content Management Server, decommissioning pools, and deactivating and removing servers and pools from a legacy deployment of Lync Server 2010.</span></span> <span data-ttu-id="d5d86-105">Es sind nicht alle der in diesem Abschnitt aufgeführten Verfahren notwendig.</span><span class="sxs-lookup"><span data-stu-id="d5d86-105">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="d5d86-106">Lesen Sie die Dokumentation, um das Verfahren zu ermitteln, das Sie für die Außerbetriebsetzung ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="d5d86-106">Read the documentation and determine which decommissioning procedure to use.</span></span>

<span data-ttu-id="d5d86-107">Ausführliche Informationen zum Entfernen lync Server 2010 Server und Serverrollen sowie eine schrittweise Anleitung zur Außerbetriebnahme einer lync Server 2010-Bereitstellung finden Sie unter "Deinstallieren von Microsoft lync Server 2010 und Entfernen von Serverrollen", die unter [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227)heruntergeladen werden können.</span><span class="sxs-lookup"><span data-stu-id="d5d86-107">For exhaustive coverage of removing Lync Server 2010 servers and server roles, and a step-by-step guide to decommissioning a Lync Server 2010 deployment, see "Uninstalling Microsoft Lync Server 2010 and Removing Server Roles," which can be downloaded at [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d5d86-108">Informationen zum Migrieren und aktualisieren verwaltete API von Microsoft Unified Communications (UCMA) Anwendungen vor dem Stillsetzen ihrer Vorgänger Umgebung finden Sie unter<A href="https://go.microsoft.com/fwlink/p/?linkid=269555">https://go.microsoft.com/fwlink/p/?LinkId=269555</A></span><span class="sxs-lookup"><span data-stu-id="d5d86-108">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, prior to decommissioning your legacy environment, see <A href="https://go.microsoft.com/fwlink/p/?linkid=269555">https://go.microsoft.com/fwlink/p/?LinkId=269555</A></span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d5d86-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="d5d86-109">In This Section</span></span>

  - <span></span>  
    [<span data-ttu-id="d5d86-110">Aktualisieren von DNS-SRV-Einträgen</span><span class="sxs-lookup"><span data-stu-id="d5d86-110">Update DNS SRV records</span></span>](update-dns-srv-records.md)

  - <span></span>  
    [<span data-ttu-id="d5d86-111">Legen Sie den lync Server 2010 zentralen Verwaltungs Server auf lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5d86-111">Move the Lync Server 2010 Central Management Server to Lync Server 2013</span></span>](move-the-lync-server-2010-central-management-server-to-lync-server-2013.md)

  - <span></span>  
    [<span data-ttu-id="d5d86-112">Verschieben von Konferenzverzeichnissen</span><span class="sxs-lookup"><span data-stu-id="d5d86-112">Move Conference Directories</span></span>](move-lync-server-2010-conference-directories-to-lync-server-2013.md)

  - <span></span>  
    [<span data-ttu-id="d5d86-113">Entfernen der Zuordnung des Archivierungsservers</span><span class="sxs-lookup"><span data-stu-id="d5d86-113">Remove the Archiving server association</span></span>](remove-the-archiving-server-association.md)

  - <span></span>  
    [<span data-ttu-id="d5d86-114">Entfernen der Monitoring Server-Zuordnung</span><span class="sxs-lookup"><span data-stu-id="d5d86-114">Remove the Monitoring server association</span></span>](remove-the-monitoring-server-association.md)

  - <span></span>  
    [<span data-ttu-id="d5d86-115">Entfernen der Enterprise Edition-Front-End-Server oder Standard Edition Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="d5d86-115">Remove the Enterprise Edition Front End Server or Standard Edition Front End Server</span></span>](remove-the-enterprise-edition-front-end-server-or-standard-edition-front-end-server.md)

  - <span></span>  
    [<span data-ttu-id="d5d86-116">Entfernen SQL Server Instanzen und Datenbanken auf dem Back-End-Server</span><span class="sxs-lookup"><span data-stu-id="d5d86-116">Remove SQL Server instances and databases on the Back End Server</span></span>](remove-sql-server-instances-and-databases-on-the-back-end-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

