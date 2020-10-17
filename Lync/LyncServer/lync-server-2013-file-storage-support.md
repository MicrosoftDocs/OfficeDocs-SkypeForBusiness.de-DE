---
title: Unterstützung von lync Server 2013 Dateispeicher
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: File storage support
ms:assetid: ed66430d-3c19-4267-938c-956a51005073
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399073(v=OCS.15)
ms:contentKeyID: 48185743
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c424693b71f516b1fcb27523fbcb27b3a514176
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507279"
---
# <a name="file-storage-support-in-lync-server-2013"></a><span data-ttu-id="bf16e-102">Unterstützung von Dateispeicher in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bf16e-102">File storage support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf16e-103">_**Letztes Änderungsstand des Themas:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="bf16e-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="bf16e-104">Lync Server 2013 verwendet denselben Dateispeicher für alle Dateispeicher.</span><span class="sxs-lookup"><span data-stu-id="bf16e-104">Lync Server 2013 uses the same file store for all file storage.</span></span> <span data-ttu-id="bf16e-105">Die Dateispeicherunterstützung umfasst Folgendes:</span><span class="sxs-lookup"><span data-stu-id="bf16e-105">File storage support includes the following:</span></span>

  - <span data-ttu-id="bf16e-106">Eine Dateifreigabe auf einer DAS-Lösung (Direct Attached Storage) oder auf einer SAN-Lösung (Storage Area Network), einschließlich DFS (Distributed File System), sowie auf einem RAID (Redundant Array of Independent Disks) für Dateispeicher.</span><span class="sxs-lookup"><span data-stu-id="bf16e-106">A file share on either direct attached storage (DAS) or a storage area network (SAN), including Distributed File System (DFS), and on a redundant array of independent disks (RAID) for file stores.</span></span> <span data-ttu-id="bf16e-107">Ausführliche Informationen zu den Speicheranforderungen finden Sie unter [Technische Anforderungen für Front-End-Server, Instant Messaging und Anwesenheit in lync Server 2013](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md) sowie [Hardware-und Softwareanforderungen für den Director in lync Server 2013](lync-server-2013-hardware-and-software-requirements-for-the-director.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="bf16e-107">For details about storage requirements, see [Technical requirements for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md) and [Hardware and software requirements for the Director in Lync Server 2013](lync-server-2013-hardware-and-software-requirements-for-the-director.md) in the Planning documentation.</span></span> <span data-ttu-id="bf16e-108">Ausführliche Informationen zu DFS für Windows Server 2008 Betriebssystem finden Sie in der schrittweisen Anleitung zu DFS für Windows Server 2008 unter [https://go.microsoft.com/fwlink/p/?linkId=202835](https://go.microsoft.com/fwlink/p/?linkid=202835) .</span><span class="sxs-lookup"><span data-stu-id="bf16e-108">For details about DFS for Windows Server 2008 operating system, see the DFS Step-by-Step Guide for Windows Server 2008 at [https://go.microsoft.com/fwlink/p/?linkId=202835](https://go.microsoft.com/fwlink/p/?linkid=202835).</span></span>

  - <span data-ttu-id="bf16e-109">Einen freigegebenen Cluster für die Dateifreigabe.</span><span class="sxs-lookup"><span data-stu-id="bf16e-109">A shared cluster for the file share.</span></span> <span data-ttu-id="bf16e-110">Wenn Sie einen freigegebenen Cluster verwenden, sollten Sie Clusterserver mit Windows Server 2008 oder Windows Server 2008 R2 verwenden.</span><span class="sxs-lookup"><span data-stu-id="bf16e-110">If you use a shared cluster, you should use cluster servers running Windows Server 2008 or Windows Server 2008 R2.</span></span> <span data-ttu-id="bf16e-111">Das Verwenden von Clusterservern mit einer älteren Version von Windows kann zu Berechtigungsproblemen führen, die verhindern, dass einige Features verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="bf16e-111">Using cluster servers running an older version of Windows may result in permission issues that prevent some features from being available.</span></span> <span data-ttu-id="bf16e-112">Verwenden Sie die Clusterverwaltung, um die Dateifreigaben zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="bf16e-112">Use the Cluster Administrator to create the file shares.</span></span> <span data-ttu-id="bf16e-113">Ausführliche Informationen zur Verwendung der Cluster Verwaltung finden Sie im Microsoft Knowledge Base-Artikel 284838, "Erstellen einer Server Cluster-Dateifreigabe mit Cluster.exe" unter [https://go.microsoft.com/fwlink/p/?linkId=140899](https://go.microsoft.com/fwlink/p/?linkid=140899) .</span><span class="sxs-lookup"><span data-stu-id="bf16e-113">For details about using the Cluster Administrator, see Microsoft Knowledge Base article 284838, "How to Create a Server Cluster File Share with Cluster.exe" at [https://go.microsoft.com/fwlink/p/?linkId=140899](https://go.microsoft.com/fwlink/p/?linkid=140899).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

