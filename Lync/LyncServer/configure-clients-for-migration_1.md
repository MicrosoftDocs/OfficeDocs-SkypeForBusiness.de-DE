---
title: Konfigurieren der Clients für die Migration
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure clients for migration
ms:assetid: 8f17862b-d9d1-47f6-b248-51f4710f5030
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688130(v=OCS.15)
ms:contentKeyID: 49733729
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b63ad4dfd4b69966a6d206ab19330d7088aff434
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180978"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-clients-for-migration"></a><span data-ttu-id="21f0d-102">Konfigurieren der Clients für die Migration</span><span class="sxs-lookup"><span data-stu-id="21f0d-102">Configure clients for migration</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21f0d-103">_**Letztes Änderungsstand des Themas:** 2013-11-21_</span><span class="sxs-lookup"><span data-stu-id="21f0d-103">_**Topic Last Modified:** 2013-11-21_</span></span>

<span data-ttu-id="21f0d-104">Dieses Thema enthält die empfohlenen Schritte zur Clientbereitstellung, die Sie vor der Migration zu lync Server 2013 durchführen sollten.</span><span class="sxs-lookup"><span data-stu-id="21f0d-104">This topic contains the recommended client deployment steps you should take prior to migrating to Lync Server 2013.</span></span> <span data-ttu-id="21f0d-105">Diese Konfigurationsänderungen sollten in Office Communications Server 2007 R2 vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="21f0d-105">These configuration changes should be made on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="21f0d-106">Es ist sehr wichtig, dass diese Schritte vor der Migration durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="21f0d-106">It is very important that you perform these steps prior to migrating.</span></span> <span data-ttu-id="21f0d-107">Ausführliche Informationen finden Sie unter [Planning for Clients and Devices in lync Server 2013](lync-server-2013-planning-for-clients-and-devices.md).</span><span class="sxs-lookup"><span data-stu-id="21f0d-107">For details, see [Planning for clients and devices in Lync Server 2013](lync-server-2013-planning-for-clients-and-devices.md).</span></span>

<div>

## <a name="to-configure-clients-prior-to-migration"></a><span data-ttu-id="21f0d-108">So konfigurieren Sie Clients vor der Migration</span><span class="sxs-lookup"><span data-stu-id="21f0d-108">To configure clients prior to migration</span></span>

1.  <span data-ttu-id="21f0d-109">Bereitstellen der neuesten Office Communications Server 2007 R2 Server-, Client-und Geräte Updates (Hotfixes):</span><span class="sxs-lookup"><span data-stu-id="21f0d-109">Deploy the most recent Office Communications Server 2007 R2 server, client, and device updates (hotfixes):</span></span>
    
      - [<span data-ttu-id="21f0d-110">Anwenden von Office Communications Server 2007 R2 Updates</span><span class="sxs-lookup"><span data-stu-id="21f0d-110">Apply Office Communications Server 2007 R2 updates</span></span>](apply-office-communications-server-2007-r2-updates.md)
    
      - [<span data-ttu-id="21f0d-111">Beschreibung des kumulativen Updatepakets für Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="21f0d-111">Description of the cumulative update package for Communicator 2007 R2</span></span>](https://go.microsoft.com/fwlink/p/?linkid=335808)
    
      - [<span data-ttu-id="21f0d-112">Abrufen von Softwareupdates für Geräte</span><span class="sxs-lookup"><span data-stu-id="21f0d-112">Obtaining Software Updates for Devices</span></span>](https://go.microsoft.com/fwlink/?linkid=335809)

2.  <span data-ttu-id="21f0d-113">Verwenden Sie auf Office Communications Server 2007 R2 die Client Versions Filterung, damit nur Office Communications Server 2007 R2 Clients mit den neuesten installierten Updates angemeldet werden können.</span><span class="sxs-lookup"><span data-stu-id="21f0d-113">On Office Communications Server 2007 R2, use Client Version Filtering to allow only Office Communications Server 2007 R2 clients with the most current updates installed to sign in.</span></span>

3.  <span data-ttu-id="21f0d-114">Verwenden Sie auf Office Communications Server 2007 R2 die Client Versions Filterung, um zu verhindern, dass lync Server 2013-Clients sich anmelden.</span><span class="sxs-lookup"><span data-stu-id="21f0d-114">On Office Communications Server 2007 R2, use Client Version Filtering to block Lync Server 2013 clients from signing in.</span></span> <span data-ttu-id="21f0d-115">Führen Sie die unter **Konfigurieren der Client Versions Filterung** unter [https://go.microsoft.com/fwlink/p/?linkId=202488](https://go.microsoft.com/fwlink/p/?linkid=202488) beschriebenen Schritte aus, um die in der folgenden Tabelle aufgeführten Versionsfilter hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="21f0d-115">Follow the steps described in **Configuring Client Version Filtering** at [https://go.microsoft.com/fwlink/p/?linkId=202488](https://go.microsoft.com/fwlink/p/?linkid=202488) to add the version filters listed in the following table.</span></span> <span data-ttu-id="21f0d-116">Weisen Sie für jeden Versionsfilter die Aktion **Blockieren** zu.</span><span class="sxs-lookup"><span data-stu-id="21f0d-116">For each version filter, assign the action **Block**.</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="21f0d-117">Client</span><span class="sxs-lookup"><span data-stu-id="21f0d-117">Client</span></span></th>
    <th><span data-ttu-id="21f0d-118">Benutzer-Agent-Header</span><span class="sxs-lookup"><span data-stu-id="21f0d-118">User agent header</span></span></th>
    <th><span data-ttu-id="21f0d-119">Version</span><span class="sxs-lookup"><span data-stu-id="21f0d-119">Version</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="21f0d-120">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="21f0d-120">Lync 2013</span></span></p></td>
    <td><p><span data-ttu-id="21f0d-121">OC</span><span class="sxs-lookup"><span data-stu-id="21f0d-121">OC</span></span></p></td>
    <td><p><span data-ttu-id="21f0d-122">15.*..* \*</span><span class="sxs-lookup"><span data-stu-id="21f0d-122">15.*.*.\*</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="21f0d-123">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="21f0d-123">Lync Web App</span></span></p></td>
    <td><p><span data-ttu-id="21f0d-124">CWA</span><span class="sxs-lookup"><span data-stu-id="21f0d-124">CWA</span></span></p></td>
    <td><p><span data-ttu-id="21f0d-125">5.*..* \*</span><span class="sxs-lookup"><span data-stu-id="21f0d-125">5.*.*.\*</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="21f0d-126">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="21f0d-126">Lync Phone Edition</span></span></p></td>
    <td><p><span data-ttu-id="21f0d-127">OCPhone</span><span class="sxs-lookup"><span data-stu-id="21f0d-127">OCPhone</span></span></p></td>
    <td><p><span data-ttu-id="21f0d-128">4.*..* \*</span><span class="sxs-lookup"><span data-stu-id="21f0d-128">4.*.*.\*</span></span></p></td>
    </tr>
    </tbody>
    </table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

