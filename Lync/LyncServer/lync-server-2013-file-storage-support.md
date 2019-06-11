---
title: 'Lync Server 2013: Dateispeicherunterstützung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: File storage support
ms:assetid: ed66430d-3c19-4267-938c-956a51005073
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399073(v=OCS.15)
ms:contentKeyID: 48185743
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3025534aecb45f230e986016e839af07fe1406cf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832152"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="file-storage-support-in-lync-server-2013"></a><span data-ttu-id="0758e-102">Dateispeicherunterstützung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0758e-102">File storage support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0758e-103">_**Letztes Änderungsdatum des Themas:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="0758e-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="0758e-104">Lync Server 2013 verwendet denselben Dateispeicher für alle Dateispeicher.</span><span class="sxs-lookup"><span data-stu-id="0758e-104">Lync Server 2013 uses the same file store for all file storage.</span></span> <span data-ttu-id="0758e-105">Die Unterstützung für Dateispeicher umfasst Folgendes:</span><span class="sxs-lookup"><span data-stu-id="0758e-105">File storage support includes the following:</span></span>

  - <span data-ttu-id="0758e-106">Eine Dateifreigabe entweder in Direct Attached Storage (das) oder in einem SAN (Storage Area Network), einschließlich DFS (Distributed File System), und auf einem redundanten Array von unabhängigen Datenträgern (RAID) für Dateispeicher.</span><span class="sxs-lookup"><span data-stu-id="0758e-106">A file share on either direct attached storage (DAS) or a storage area network (SAN), including Distributed File System (DFS), and on a redundant array of independent disks (RAID) for file stores.</span></span> <span data-ttu-id="0758e-107">Details zu den Speicheranforderungen finden Sie unter [Technische Voraussetzungen für Front-End-Server, Instant Messaging und Anwesenheitsinformationen in lync Server 2013](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md) sowie [Hardware-und Softwareanforderungen für den Director in lync Server 2013](lync-server-2013-hardware-and-software-requirements-for-the-director.md) in der Planung. Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="0758e-107">For details about storage requirements, see [Technical requirements for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md) and [Hardware and software requirements for the Director in Lync Server 2013](lync-server-2013-hardware-and-software-requirements-for-the-director.md) in the Planning documentation.</span></span> <span data-ttu-id="0758e-108">Ausführliche Informationen zum Betriebssystem DFS für Windows Server 2008 finden Sie in [http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835)der schrittweisen Anleitung zu DFS für Windows Server 2008 unter.</span><span class="sxs-lookup"><span data-stu-id="0758e-108">For details about DFS for Windows Server 2008 operating system, see the DFS Step-by-Step Guide for Windows Server 2008 at [http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835).</span></span>

  - <span data-ttu-id="0758e-109">Ein freigegebener Cluster für die Dateifreigabe.</span><span class="sxs-lookup"><span data-stu-id="0758e-109">A shared cluster for the file share.</span></span> <span data-ttu-id="0758e-110">Wenn Sie einen freigegebenen Cluster verwenden, sollten Sie Cluster Server mit Windows Server 2008 oder Windows Server 2008 R2 verwenden.</span><span class="sxs-lookup"><span data-stu-id="0758e-110">If you use a shared cluster, you should use cluster servers running Windows Server 2008 or Windows Server 2008 R2.</span></span> <span data-ttu-id="0758e-111">Die Verwendung von Clusterservern, auf denen eine ältere Version von Windows ausgeführt wird, kann zu Berechtigungsproblemen führen, die verhindern, dass einige Features verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="0758e-111">Using cluster servers running an older version of Windows may result in permission issues that prevent some features from being available.</span></span> <span data-ttu-id="0758e-112">Verwenden Sie die Cluster Verwaltung, um die Dateifreigaben zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0758e-112">Use the Cluster Administrator to create the file shares.</span></span> <span data-ttu-id="0758e-113">Details zur Verwendung des Cluster Administrators finden Sie im [http://go.microsoft.com/fwlink/p/?linkId=140899](http://go.microsoft.com/fwlink/p/?linkid=140899)Microsoft Knowledge Base-Artikel 284838, "Erstellen einer Server Cluster-Dateifreigabe mit Cluster. exe".</span><span class="sxs-lookup"><span data-stu-id="0758e-113">For details about using the Cluster Administrator, see Microsoft Knowledge Base article 284838, "How to Create a Server Cluster File Share with Cluster.exe" at [http://go.microsoft.com/fwlink/p/?linkId=140899](http://go.microsoft.com/fwlink/p/?linkid=140899).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

