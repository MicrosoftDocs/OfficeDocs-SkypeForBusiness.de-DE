---
title: 'Lync Server 2013: Übersicht über das Parken von Anrufen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Call Park
ms:assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205124(v=OCS.15)
ms:contentKeyID: 48184939
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: acb507ddf7fc47714781e83da0fa77d093f193c0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153265"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-call-park-in-lync-server-2013"></a><span data-ttu-id="e76ce-102">Übersicht über das Parken von Anrufen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e76ce-102">Overview of Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e76ce-103">_**Letztes Änderungsstand des Themas:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="e76ce-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="e76ce-104">Im lync Server 2013 Anwendung zum Parken von anrufen können Enterprise-VoIP-Benutzer eine der folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="e76ce-104">The Lync Server 2013 Call Park application lets Enterprise Voice users do any of the following:</span></span>

  - <span data-ttu-id="e76ce-105">Halten Sie einen Anruf gedrückt, und rufen Sie dann den Anruf vom gleichen Telefon oder von einem anderen Telefon ab.</span><span class="sxs-lookup"><span data-stu-id="e76ce-105">Put a call on hold and then retrieve the call from the same phone or another phone.</span></span>

  - <span data-ttu-id="e76ce-106">Halten Sie einen Anruf an, um ihn an eine Abteilung oder einen allgemeinen Bereich zu übertragen (beispielsweise an eine Vertriebsabteilung oder an ein Warehouse, in dem ein Telefon für gemeinsame Bereiche vorhanden ist).</span><span class="sxs-lookup"><span data-stu-id="e76ce-106">Put a call on hold to transfer it to a department or general area (for example, to a sales department or a warehouse where there is a common area phone).</span></span>

  - <span data-ttu-id="e76ce-107">Halten Sie einen Anruf gedrückt, und halten Sie das ursprüngliche Anrufbeantworter für andere Anrufe frei.</span><span class="sxs-lookup"><span data-stu-id="e76ce-107">Put a call on hold and keep the original answering phone free for other calls.</span></span>

<span data-ttu-id="e76ce-108">Wenn ein Benutzer einen Anruf parkt, übergibt lync Server den Anruf an eine temporäre Nummer, die als *Orbit*bezeichnet wird, wobei der Anruf angehalten wird, bis er abgerufen wird oder ein Timeout auftritt. Lync Server sendet den Orbit an den Benutzer, der den Anruf geparkt hat.</span><span class="sxs-lookup"><span data-stu-id="e76ce-108">When a user parks a call, Lync Server transfers the call to a temporary number, called an *orbit*, where the call is held until it is retrieved or it times out. Lync Server sends the orbit to the user who parked the call.</span></span> <span data-ttu-id="e76ce-109">Zum Abrufen des geparkten Anrufs kann der Benutzer die Umlaufbahn Nummer wählen oder im Unterhaltungsfenster auf den Orbit-Link oder die Orbit-Schaltfläche klicken.</span><span class="sxs-lookup"><span data-stu-id="e76ce-109">To retrieve the parked call, the user can dial the orbit number or click the orbit link or button in the Conversation window.</span></span>

<span data-ttu-id="e76ce-110">Der Benutzer, der einen Anruf geparkt hat, kann eine Person Benachrichtigen, um den Anruf mithilfe eines externen Mechanismus, beispielsweise Instant Messaging (Sofortnachrichten) oder eines Auslagerungs Systems, abzurufen, um die orbitnummer an eine andere Person zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="e76ce-110">The user who parked a call can notify someone to retrieve the call by using an external mechanism, such as instant messaging (IM) or a paging system, to communicate the orbit number to someone else.</span></span> <span data-ttu-id="e76ce-111">Der Benutzer, der den Anruf geparkt hat, kann das Unterhaltungsfenster geöffnet lassen, um eine Benachrichtigung zu erhalten, wenn der Anruf abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="e76ce-111">The user who parked the call can leave the Conversation window open to receive notification when the call is retrieved.</span></span>

<span data-ttu-id="e76ce-112">Da Umlaufbahn Bereiche global eindeutig sind, können Anrufe von beliebigen lync Server Standort-oder PBX-Telefonen abgerufen werden, wenn das Routing entsprechend konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="e76ce-112">Because orbit ranges are globally unique, it is possible to retrieve calls from any Lync Server site or PBX phone if routing is configured appropriately.</span></span> <span data-ttu-id="e76ce-113">Wenn der Anruf nicht innerhalb einer konfigurierbaren Zeitspanne abgerufen wird, klingelt der Anruf an die Person zurück, die ihn geparkt hat.</span><span class="sxs-lookup"><span data-stu-id="e76ce-113">If no one retrieves the call within a configurable amount of time, the call rings back to the person who parked it.</span></span> <span data-ttu-id="e76ce-114">Wenn diese Person den Rückruf nicht beantwortet, wird der Anruf an ein Fallback-Ziel, beispielsweise an einen Operator, übertragen, falls dies konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="e76ce-114">If that person does not answer the ringback, the call is transferred to a fallback destination, such as to an operator, if so configured.</span></span> <span data-ttu-id="e76ce-115">Sie können konfigurieren, wie oft der Anruf klingelt, bevor er von ein bis zehn Mal übertragen wird.</span><span class="sxs-lookup"><span data-stu-id="e76ce-115">You can configure the number of times the call rings back before being transferred from one to ten times.</span></span> <span data-ttu-id="e76ce-116">Wenn niemand einen übertragenen Anruf beantwortet, wird der Anruf getrennt.</span><span class="sxs-lookup"><span data-stu-id="e76ce-116">If no one answers a transferred call, the call is disconnected.</span></span> <span data-ttu-id="e76ce-117">Die Umlaufbahn wird freigegeben, wenn der Anruf abgerufen oder getrennt wird.</span><span class="sxs-lookup"><span data-stu-id="e76ce-117">The orbit is freed when the call is retrieved or disconnected.</span></span>

<span data-ttu-id="e76ce-118">Wenn Sie das Parken von Anrufen bereitstellen, müssen Sie Bereiche für Durchwahlnummern für das Parken von Anrufen reservieren.</span><span class="sxs-lookup"><span data-stu-id="e76ce-118">When you deploy Call Park, you need to reserve ranges of extension numbers for parking calls.</span></span> <span data-ttu-id="e76ce-119">Diese Erweiterungen müssen virtuelle Erweiterungen sein: Erweiterungen, denen kein Benutzer oder Telefon zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="e76ce-119">These extensions need to be virtual extensions: extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="e76ce-120">Anschließend konfigurieren Sie die Orbit-Tabelle für das Parken von Anrufen mit den Bereichen der Durchwahlnummern und geben an, welche Anwendungsdienst die Anwendung zum Parken von Anrufen hostet, die die einzelnen Bereiche behandelt.</span><span class="sxs-lookup"><span data-stu-id="e76ce-120">You then configure the call park orbit table with the ranges of extension numbers and specify which Application service hosts the Call Park application that handles each range.</span></span> <span data-ttu-id="e76ce-121">Jeder Front-End-Pool verfügt auf dem entsprechenden Back-End-Server über eine Parken-Tabelle, die zum Verwalten von Anrufen verwendet wird, die im Pool geparkt sind.</span><span class="sxs-lookup"><span data-stu-id="e76ce-121">Each Front End pool has a Call Park table on the corresponding Back End Server that is used to manage calls that are parked on the pool.</span></span> <span data-ttu-id="e76ce-122">Die Liste der orbitbereiche wird im zentralen Verwaltungsspeicher gespeichert und zum Weiterleiten von Umlaufbahnen zum Ziel Pool verwendet.</span><span class="sxs-lookup"><span data-stu-id="e76ce-122">The list of orbit ranges is stored in Central Management store and is used to route orbits to the destination pool.</span></span> <span data-ttu-id="e76ce-123">Jeder lync Server Pool, in dem die Anwendung zum Parken von Anrufen bereitgestellt und konfiguriert ist, kann einen oder mehrere Umlaufbahn Bereiche aufweisen.</span><span class="sxs-lookup"><span data-stu-id="e76ce-123">Each Lync Server pool where the Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="e76ce-124">Umlaufbahn Bereiche müssen in der lync Server-Bereitstellung global eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="e76ce-124">Orbit ranges must be globally unique across the Lync Server deployment.</span></span>

<span data-ttu-id="e76ce-125">Sie können auch andere Einstellungen für das Parken von anrufen konfigurieren, beispielsweise, wo Anrufe umgeleitet werden, wenn ein Timeout auftritt und ob die Person auf dem Telefon Musik hört, während Sie geparkt hat.</span><span class="sxs-lookup"><span data-stu-id="e76ce-125">You also configure other Call Park settings, such as where calls are redirected if they time out and whether the person on the phone hears music while parked.</span></span> <span data-ttu-id="e76ce-126">Sie können auch die Musikdatei angeben, die wiedergegeben werden soll, während der Anruf gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="e76ce-126">You can also specify the music file to play while the call is on hold.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e76ce-127">Benutzerdefinierte Musik-on-Hold-Dateien für das Parken von Anrufen werden nicht als Teil des lync Server 2013 Notfall Wiederherstellungsprozesses gesichert und gehen verloren, wenn die in den Pool hochgeladenen Dateien beschädigt, beschädigt oder gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="e76ce-127">Customized music-on-hold files for Call Park are not backed up as part of the Lync Server 2013 disaster recovery process and will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="e76ce-128">Bewahren Sie immer eine separate Sicherungskopie der angepassten Musikdateien auf, die Sie für das Parken von Anrufen hochgeladen haben.</span><span class="sxs-lookup"><span data-stu-id="e76ce-128">Always keep a separate backup copy of the customized music-on-hold files that you have uploaded for Call Park.</span></span>



</div>

<span data-ttu-id="e76ce-129">Die Anwendung zum Parken von anrufen ist eine Komponente von Enterprise-VoIP.</span><span class="sxs-lookup"><span data-stu-id="e76ce-129">The Call Park application is a component of Enterprise Voice.</span></span> <span data-ttu-id="e76ce-130">Wenn Sie Enterprise-VoIP bereitstellen, wird das Anwendung zum Parken von Anrufen automatisch installiert und aktiviert.</span><span class="sxs-lookup"><span data-stu-id="e76ce-130">When you deploy Enterprise Voice, the Call Park application is installed and activated automatically.</span></span> <span data-ttu-id="e76ce-131">Bevor Sie das Parken von Anrufen verwenden können, muss der Enterprise-VoIP-Administrator es jedoch konfigurieren und für Benutzer über VoIP-Richtlinie aktivieren.</span><span class="sxs-lookup"><span data-stu-id="e76ce-131">Before you can use Call Park, however, the Enterprise Voice administrator must configure it and enable it for users through voice policy.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

