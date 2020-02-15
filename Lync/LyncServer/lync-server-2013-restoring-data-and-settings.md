---
title: 'Lync Server 2013: Wiederherstellen von Daten und Einstellungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring data and settings
ms:assetid: b07f5dd7-7bed-4819-8cb5-617f5acd478e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202185(v=OCS.15)
ms:contentKeyID: 51541503
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e5b8575ee1362b240df0bfc0a1a1a6b27afde268
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050427"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-data-and-settings-in-lync-server-2013"></a><span data-ttu-id="9e240-102">Wiederherstellen von Daten und Einstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e240-102">Restoring data and settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e240-103">_**Letztes Änderungsstand des Themas:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="9e240-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="9e240-104">Wenn Sie eine Notfall Wiederherstellungs Topologie mit gepaarten Pools implementiert haben und einer dieser Front-End-Pools ausgefallen ist und Sie den Dienst für Ihre Benutzer schnell wiederherstellen müssen, finden Sie unter [failing over a Pool in lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span><span class="sxs-lookup"><span data-stu-id="9e240-104">If you have implemented a disaster recovery topology with paired pools, and one of those Front End pools has gone down and you need to quickly restore service to your users, see [Failing over a pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span></span> <span data-ttu-id="9e240-105">Verwenden Sie andernfalls die Informationen in den folgenden Themen zusammen mit den Arbeitsblättern in [Sicherungs-und Wiederherstellungs Arbeitsblättern für lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md), um lync Server nach einem Ausfall oder Ausfall wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="9e240-105">Otherwise, use the information in the following topics, along with the worksheets in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md), to restore Lync Server after a failure or outage.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9e240-106">Um Ausfallzeiten und potenzielle Datenverluste zu verringern, führen Sie die in diesem Dokument beschriebenen Wiederherstellungsverfahren nur aus, wenn die Problembehandlung bei der Identifizierung und Behebung des Problems nicht wirksam ist.</span><span class="sxs-lookup"><span data-stu-id="9e240-106">To reduce downtime and potential data loss, perform the restoration procedures described in this document only if troubleshooting procedures are not effective in identifying and correcting the problem.</span></span> <span data-ttu-id="9e240-107">Versuchen Sie während der Problembehandlung, die Auswirkungen auf andere Server und Komponenten zu minimieren, wenn Sie die Server herunterfahren und neu starten.</span><span class="sxs-lookup"><span data-stu-id="9e240-107">During troubleshooting, try to minimize the impact on other servers and components as you shut down and restart servers.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9e240-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="9e240-108">In This Section</span></span>

  - [<span data-ttu-id="9e240-109">Vorbereiten der Wiederherstellung lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e240-109">Preparing to restore Lync Server 2013</span></span>](lync-server-2013-preparing-to-restore-lync-server.md)

  - [<span data-ttu-id="9e240-110">Wiederherstellen eines Standard Edition-Servers in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e240-110">Restoring a Standard Edition server in Lync Server 2013</span></span>](lync-server-2013-restoring-a-standard-edition-server.md)

  - [<span data-ttu-id="9e240-111">Wiederherstellen des Servers, der den zentralen Verwaltungsspeicher in lync Server 2013 hostet</span><span class="sxs-lookup"><span data-stu-id="9e240-111">Restoring the server hosting the Central Management store in Lync Server 2013</span></span>](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)

  - [<span data-ttu-id="9e240-112">Wiederherstellen eines Enterprise Edition-Back-End-Servers in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e240-112">Restoring an Enterprise Edition Back End Server in Lync Server 2013</span></span>](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md)

  - [<span data-ttu-id="9e240-113">Wiederherstellen eines Enterprise Edition-Mitgliedsservers in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e240-113">Restoring an Enterprise Edition member server in Lync Server 2013</span></span>](lync-server-2013-restoring-an-enterprise-edition-member-server.md)

  - [<span data-ttu-id="9e240-114">Wiederherstellen eines lync Server Pools in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e240-114">Restoring a Lync Server pool in Lync Server 2013</span></span>](lync-server-2013-restoring-a-lync-server-pool.md)

  - [<span data-ttu-id="9e240-115">Ausführen eines ABC-Front-End-Pool-Failovers in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e240-115">Performing an ABC Front End pool failover in Lync Server 2013</span></span>](lync-server-2013-performing-an-abc-front-end-pool-failover.md)

  - [<span data-ttu-id="9e240-116">Wiederherstellen eines Dateispeichers in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e240-116">Restoring a file store in Lync Server 2013</span></span>](lync-server-2013-restoring-a-file-store.md)

  - [<span data-ttu-id="9e240-117">Wiederherstellen von Überwachungs-oder Archivierungsdaten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e240-117">Restoring monitoring or archiving data in Lync Server 2013</span></span>](lync-server-2013-restoring-monitoring-or-archiving-data.md)

  - [<span data-ttu-id="9e240-118">Wiederherstellen von Daten für beständigen Chat in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e240-118">Restoring Persistent Chat data in Lync Server 2013</span></span>](lync-server-2013-restoring-persistent-chat-data.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

