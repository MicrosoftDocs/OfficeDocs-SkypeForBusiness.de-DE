---
title: 'Lync Server 2013: Einrichten einer Sicherungs-und Wiederherstellungsstrategie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Establishing a backup and restoration strategy
ms:assetid: f545a75f-bbc4-4968-b510-8f6f3920112b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202195(v=OCS.15)
ms:contentKeyID: 51541532
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d378c66ae820ef0be7b7b3b0492b023863e977ea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832194"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="establishing-a-backup-and-restoration-strategy-for-lync-server-2013"></a><span data-ttu-id="779c2-102">Einrichten einer Sicherungs-und Wiederherstellungsstrategie für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="779c2-102">Establishing a backup and restoration strategy for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="779c2-103">_**Letztes Änderungsdatum des Themas:** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="779c2-103">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="779c2-104">Bevor Sie einen Sicherungs-und Wiederherstellungsplan für lync Server entwickeln können, müssen Sie eine Strategie entwickeln, die den Zielen Ihrer Organisation entspricht.</span><span class="sxs-lookup"><span data-stu-id="779c2-104">Before you can develop a backup and restoration plan for Lync Server, you need to develop a strategy that fits with your organization's goals.</span></span> <span data-ttu-id="779c2-105">Zur Entwicklung einer effektiven Sicherungs-und Wiederherstellungsstrategie müssen Sie Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="779c2-105">To develop an effective backup and restoration strategy, you will need to:</span></span>

  - <span data-ttu-id="779c2-106">Unternehmensprioritäten festlegen</span><span class="sxs-lookup"><span data-stu-id="779c2-106">Establish business priorities.</span></span>

  - <span data-ttu-id="779c2-107">Ermitteln von Sicherungs-und Wiederherstellungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="779c2-107">Identify backup and restoration requirements.</span></span>

<div>

## <a name="establishing-business-priorities"></a><span data-ttu-id="779c2-108">Einrichten von Unternehmensprioritäten</span><span class="sxs-lookup"><span data-stu-id="779c2-108">Establishing Business Priorities</span></span>

<span data-ttu-id="779c2-109">Bewerten Sie die geschäftlichen Prioritäten Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="779c2-109">Evaluate the business priorities of your organization.</span></span> <span data-ttu-id="779c2-110">In der Regel sind die primären Unternehmensprioritäten, die sich auf Ihre Sicherungs-und Wiederherstellungsstrategie auswirken, wie folgt:</span><span class="sxs-lookup"><span data-stu-id="779c2-110">Typically, the primary business priorities that affect your backup and restoration strategy are the following:</span></span>

  - <span data-ttu-id="779c2-111">Business Continuity-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="779c2-111">Business continuity requirements</span></span>

  - <span data-ttu-id="779c2-112">Datenvollständigkeit</span><span class="sxs-lookup"><span data-stu-id="779c2-112">Data completeness</span></span>

  - <span data-ttu-id="779c2-113">Daten kritisch</span><span class="sxs-lookup"><span data-stu-id="779c2-113">Data criticality</span></span>

  - <span data-ttu-id="779c2-114">Portabilitäts Anforderungen</span><span class="sxs-lookup"><span data-stu-id="779c2-114">Portability requirements</span></span>

  - <span data-ttu-id="779c2-115">Kosteneinschränkungen</span><span class="sxs-lookup"><span data-stu-id="779c2-115">Cost constraints</span></span>

<span data-ttu-id="779c2-116">Geschäftliche Anforderungen wie diese helfen bei der Bestimmung der Service Level Agreements (SLAs), die Sie mit ihren Kunden entwickeln.</span><span class="sxs-lookup"><span data-stu-id="779c2-116">Business needs such as these help to determine the service level agreements (SLAs) that you develop with your customers.</span></span> <span data-ttu-id="779c2-117">Service Level Agreements beeinflussen Ihre Sicherungs-und Wiederherstellungsstrategie erheblich.</span><span class="sxs-lookup"><span data-stu-id="779c2-117">Service level agreements greatly influence your backup and recovery strategy.</span></span>

</div>

<div>

## <a name="identifying-backup-and-restoration-requirements"></a><span data-ttu-id="779c2-118">Identifizieren von Sicherungs-und Wiederherstellungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="779c2-118">Identifying Backup and Restoration Requirements</span></span>

<span data-ttu-id="779c2-119">Ihre Geschäftsprioritäten und Service Level Agreements dienen dazu, die Anforderungen Ihrer Organisationen für das Sichern und Wiederherstellen von lync Server zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="779c2-119">Your business priorities and service level agreements act in determining your organizations' requirements for backing up and restoring Lync Server.</span></span> <span data-ttu-id="779c2-120">Ermitteln und dokumentieren Sie Ihre Anforderungen für Folgendes:</span><span class="sxs-lookup"><span data-stu-id="779c2-120">Identify and document your requirements for the following:</span></span>

  - <span data-ttu-id="779c2-121">**Häufigkeit von Sicherungen**   Informationen zu den bewährten Methoden für die Sicherungshäufigkeit finden Sie unter [bewährte Methoden für die Sicherung und Wiederherstellung für lync Server 2013](lync-server-2013-best-practices-for-backup-and-restoration.md).</span><span class="sxs-lookup"><span data-stu-id="779c2-121">**Frequency of backups**   For details about best practices for backup frequency, see [Best practices for backup and restoration for Lync Server 2013](lync-server-2013-best-practices-for-backup-and-restoration.md).</span></span>

  - <span data-ttu-id="779c2-122">**Zu den Sicherungs-und Wiederherstellungstools**   gehören die Personen, die die Tools verwenden sollen, und auf welchen Computern.</span><span class="sxs-lookup"><span data-stu-id="779c2-122">**Backup and restoration tools**   Include who is to use the tools, and on which computers.</span></span> <span data-ttu-id="779c2-123">Details zu den in diesem Thema und den erforderlichen Berechtigungen besprochenen Tools finden Sie unter [Sicherungs-und Wiederherstellungsanforderungen in lync Server 2013: Tools und Berechtigungen](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="779c2-123">For details about the tools discussed in this topic and necessary permissions, see [Backup and restoration requirements in Lync Server 2013: tools and permissions](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span></span>

  - <span data-ttu-id="779c2-124">**Sicherungsspeicherort**   ermitteln Sie, ob die Sicherungen lokal oder Remote aufbewahrt werden, wobei Sicherheit und Barrierefreiheit berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="779c2-124">**Backup location**   Identify whether the backups are kept locally or remotely, taking security and accessibility into consideration.</span></span> <span data-ttu-id="779c2-125">Geben Sie das für die Sicherungen zu verwendende Medium an.</span><span class="sxs-lookup"><span data-stu-id="779c2-125">Specify the media to be used for the backups.</span></span>

  - <span data-ttu-id="779c2-126">**Hardware-und Softwareanforderungen**   identifizieren und dokumentieren ihre spezifischen Hardware-und Softwareanforderungen, einschließlich Hardware für den Backup-Speicher und die Wiederherstellung bestimmter Komponenten sowie Software-und Netzwerkkonnektivität, die erforderlich ist, um unterstützen Sie die Sicherung und Wiederherstellung.</span><span class="sxs-lookup"><span data-stu-id="779c2-126">**Hardware and software requirements**   Identify and document your specific hardware and software requirements, including the hardware for backup storage and restoration of specific components and any software and network connectivity required to support backup and restoration.</span></span> <span data-ttu-id="779c2-127">Berücksichtigen Sie bei der Entwicklung Ihrer Hardware-und Softwareanforderungen die verschiedenen Wiederherstellungsszenarien, die Folgen.</span><span class="sxs-lookup"><span data-stu-id="779c2-127">As you develop your hardware and software requirements, keep in mind the various restoration scenarios that follow.</span></span>

  - <span data-ttu-id="779c2-128">**Wiederherstellungsszenarien**   hier sind die Wiederherstellungsprozesse für die folgenden Szenarien:</span><span class="sxs-lookup"><span data-stu-id="779c2-128">**Restoration scenarios**   Here are the restoration processes for the following scenarios:</span></span>
    
      - <span data-ttu-id="779c2-129">Ein lync Server-Pool schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="779c2-129">A Lync Server pool fails.</span></span> <span data-ttu-id="779c2-130">Für dieses Szenario muss jeder Server im Pool neu erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="779c2-130">This scenario requires rebuilding each server in the pool.</span></span>
    
      - <span data-ttu-id="779c2-131">Ein Standard Edition-Server schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="779c2-131">A Standard Edition server fails.</span></span> <span data-ttu-id="779c2-132">Für dieses Szenario muss der Server auf einem neuen oder sauberen Computer neu erstellt und Datenbanken wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="779c2-132">This scenario requires rebuilding the server on a new or clean computer and restoring databases.</span></span>
    
      - <span data-ttu-id="779c2-133">Verlust des zentralen Verwaltungsspeichers.</span><span class="sxs-lookup"><span data-stu-id="779c2-133">Loss of the Central Management store.</span></span> <span data-ttu-id="779c2-134">Dieses Szenario erfordert mindestens das Wiederherstellen und Veröffentlichen des zentralen Verwaltungsspeichers.</span><span class="sxs-lookup"><span data-stu-id="779c2-134">At a minimum, this scenario requires restoring and publishing the Central Management store.</span></span>
    
      - <span data-ttu-id="779c2-135">Verlust eines Back-End-Servers, wenn der zentrale Verwaltungsspeicher weiterhin normal funktioniert.</span><span class="sxs-lookup"><span data-stu-id="779c2-135">Loss of a Back End Server when the Central Management store is still functioning normally.</span></span> <span data-ttu-id="779c2-136">Für dieses Szenario muss der Server auf einem neuen oder sauberen Computer neu erstellt und Datenbanken wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="779c2-136">This scenario requires rebuilding the server on a new or clean computer and restoring databases.</span></span>
    
      - <span data-ttu-id="779c2-137">Ein Server, der Mitglied eines lync Server-Pools ist, schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="779c2-137">A server that is a member of a Lync Server pool fails.</span></span> <span data-ttu-id="779c2-138">Für dieses Szenario muss der Server auf einem neuen oder sauberen Computer neu erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="779c2-138">This scenario requires rebuilding the server on a new or clean computer.</span></span>
    
      - <span data-ttu-id="779c2-139">Ein Dateispeicher schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="779c2-139">A File Store fails.</span></span> <span data-ttu-id="779c2-140">Für dieses Szenario muss der Dateiserver oder der Dateicluster wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="779c2-140">This scenario requires restoring the file server or file cluster.</span></span>
    
      - <span data-ttu-id="779c2-141">Eine Datenbank zum Archivieren, überwachen oder beständigen Chat schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="779c2-141">An Archiving, Monitoring, or Persistent Chat database fails.</span></span> <span data-ttu-id="779c2-142">Für dieses Szenario müssen die Datenbanken neu erstellt werden, und wenn die Daten für Ihre Organisation wichtig sind, müssen Sie die Daten wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="779c2-142">This scenario requires recreating the databases, and, if the data is critical to your organization, restoring the data.</span></span> <span data-ttu-id="779c2-143">Archivierungs-, Überwachungs-und beständige Chat Daten sind nicht erforderlich, um lync Server wieder in Betrieb zu nehmen.</span><span class="sxs-lookup"><span data-stu-id="779c2-143">Archiving, Monitoring, and Persistent Chat data is not required to get Lync Server back up and running.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

