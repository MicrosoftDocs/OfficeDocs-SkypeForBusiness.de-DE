---
title: 'Lync Server 2013: Einrichten einer Sicherungs-und Wiederherstellungsstrategie'
description: 'Lync Server 2013: Einrichten einer Sicherungs-und Wiederherstellungsstrategie.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Establishing a backup and restoration strategy
ms:assetid: f545a75f-bbc4-4968-b510-8f6f3920112b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202195(v=OCS.15)
ms:contentKeyID: 51541532
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4fdefed873d1fd69d82f8ecebceeb92f06f65f7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555041"
---
# <a name="establishing-a-backup-and-restoration-strategy-for-lync-server-2013"></a><span data-ttu-id="88039-103">Einrichten einer Sicherungs-und Wiederherstellungsstrategie für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88039-103">Establishing a backup and restoration strategy for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88039-104">_**Letztes Änderungsstand des Themas:** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="88039-104">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="88039-105">Bevor Sie einen Sicherungs-und Wiederherstellungsplan für lync Server entwickeln können, müssen Sie eine Strategie entwickeln, die in die Ziele Ihrer Organisation passt.</span><span class="sxs-lookup"><span data-stu-id="88039-105">Before you can develop a backup and restoration plan for Lync Server, you need to develop a strategy that fits with your organization's goals.</span></span> <span data-ttu-id="88039-106">Um eine effektive Sicherungs-und Wiederherstellungsstrategie zu entwickeln, müssen Sie Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="88039-106">To develop an effective backup and restoration strategy, you will need to:</span></span>

  - <span data-ttu-id="88039-107">Festlegen von Geschäftsprioritäten</span><span class="sxs-lookup"><span data-stu-id="88039-107">Establish business priorities.</span></span>

  - <span data-ttu-id="88039-108">Ermitteln der Sicherungs-und Wiederherstellungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="88039-108">Identify backup and restoration requirements.</span></span>

<div>

## <a name="establishing-business-priorities"></a><span data-ttu-id="88039-109">Einrichten von Geschäftsprioritäten</span><span class="sxs-lookup"><span data-stu-id="88039-109">Establishing Business Priorities</span></span>

<span data-ttu-id="88039-110">Bewerten Sie die geschäftlichen Prioritäten Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="88039-110">Evaluate the business priorities of your organization.</span></span> <span data-ttu-id="88039-111">Normalerweise sind die folgenden primären Geschäftsprioritäten für Ihre Sicherungs-und Wiederherstellungsstrategie relevant:</span><span class="sxs-lookup"><span data-stu-id="88039-111">Typically, the primary business priorities that affect your backup and restoration strategy are the following:</span></span>

  - <span data-ttu-id="88039-112">Anforderungen an die Geschäftskontinuität</span><span class="sxs-lookup"><span data-stu-id="88039-112">Business continuity requirements</span></span>

  - <span data-ttu-id="88039-113">Datenvollständigkeit</span><span class="sxs-lookup"><span data-stu-id="88039-113">Data completeness</span></span>

  - <span data-ttu-id="88039-114">Datenkritikalität</span><span class="sxs-lookup"><span data-stu-id="88039-114">Data criticality</span></span>

  - <span data-ttu-id="88039-115">Portabilitäts Anforderungen</span><span class="sxs-lookup"><span data-stu-id="88039-115">Portability requirements</span></span>

  - <span data-ttu-id="88039-116">Kosteneinschränkungen</span><span class="sxs-lookup"><span data-stu-id="88039-116">Cost constraints</span></span>

<span data-ttu-id="88039-117">Geschäftliche Anforderungen wie diese helfen bei der Bestimmung der Vereinbarungen zum Service Level (Service Level Agreements, SLAs), die Sie mit ihren Kunden entwickeln.</span><span class="sxs-lookup"><span data-stu-id="88039-117">Business needs such as these help to determine the service level agreements (SLAs) that you develop with your customers.</span></span> <span data-ttu-id="88039-118">Vereinbarungen zum Service Level beeinflussen die Sicherungs-und Wiederherstellungsstrategie stark.</span><span class="sxs-lookup"><span data-stu-id="88039-118">Service level agreements greatly influence your backup and recovery strategy.</span></span>

</div>

<div>

## <a name="identifying-backup-and-restoration-requirements"></a><span data-ttu-id="88039-119">Identifizieren der Sicherungs-und Wiederherstellungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="88039-119">Identifying Backup and Restoration Requirements</span></span>

<span data-ttu-id="88039-120">Ihre geschäftlichen Prioritäten und Vereinbarungen zum Service Level dienen der Bestimmung der Anforderungen Ihrer Organisation zum Sichern und Wiederherstellen von lync Server.</span><span class="sxs-lookup"><span data-stu-id="88039-120">Your business priorities and service level agreements act in determining your organizations' requirements for backing up and restoring Lync Server.</span></span> <span data-ttu-id="88039-121">Identifizieren und dokumentieren Sie Ihre Anforderungen für Folgendes:</span><span class="sxs-lookup"><span data-stu-id="88039-121">Identify and document your requirements for the following:</span></span>

  - <span data-ttu-id="88039-122">**Häufigkeit von Sicherungen**     Ausführliche Informationen zu bewährten Methoden für die Sicherungshäufigkeit finden Sie unter [bewährte Methoden für die Sicherung und Wiederherstellung für lync Server 2013](lync-server-2013-best-practices-for-backup-and-restoration.md).</span><span class="sxs-lookup"><span data-stu-id="88039-122">**Frequency of backups**   For details about best practices for backup frequency, see [Best practices for backup and restoration for Lync Server 2013](lync-server-2013-best-practices-for-backup-and-restoration.md).</span></span>

  - <span data-ttu-id="88039-123">**Sicherungs-und Wiederherstellungstools**     Geben Sie an, welche Benutzer die Tools verwenden sollen und auf welchen Computern.</span><span class="sxs-lookup"><span data-stu-id="88039-123">**Backup and restoration tools**   Include who is to use the tools, and on which computers.</span></span> <span data-ttu-id="88039-124">Ausführliche Informationen zu den in diesem Thema und den erforderlichen Berechtigungen beschriebenen Tools finden Sie unter [Sicherungs-und Wiederherstellungsanforderungen in lync Server 2013: Tools and Permissions](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="88039-124">For details about the tools discussed in this topic and necessary permissions, see [Backup and restoration requirements in Lync Server 2013: tools and permissions](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span></span>

  - <span data-ttu-id="88039-125">**Sicherungsspeicherort**     Ermitteln, ob die Sicherungen lokal oder Remote aufbewahrt werden, wobei Sicherheit und Barrierefreiheit berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="88039-125">**Backup location**   Identify whether the backups are kept locally or remotely, taking security and accessibility into consideration.</span></span> <span data-ttu-id="88039-126">Geben Sie die Medien an, die für die Sicherungen verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="88039-126">Specify the media to be used for the backups.</span></span>

  - <span data-ttu-id="88039-127">**Hardware-und Softwareanforderungen**     Identifizieren und dokumentieren Sie Ihre spezifischen Hardware-und Softwareanforderungen, einschließlich der Hardware für den Sicherungsspeicher und der Wiederherstellung bestimmter Komponenten sowie aller Software-und Netzwerkkonnektivität, die zur Unterstützung von Sicherung und Wiederherstellung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="88039-127">**Hardware and software requirements**   Identify and document your specific hardware and software requirements, including the hardware for backup storage and restoration of specific components and any software and network connectivity required to support backup and restoration.</span></span> <span data-ttu-id="88039-128">Beachten Sie bei der Entwicklung Ihrer Hardware-und Softwareanforderungen die verschiedenen Wiederherstellungsszenarien, die befolgt werden.</span><span class="sxs-lookup"><span data-stu-id="88039-128">As you develop your hardware and software requirements, keep in mind the various restoration scenarios that follow.</span></span>

  - <span data-ttu-id="88039-129">**Wiederherstellungsszenarien**     Hier sind die Wiederherstellungsprozesse für die folgenden Szenarien:</span><span class="sxs-lookup"><span data-stu-id="88039-129">**Restoration scenarios**   Here are the restoration processes for the following scenarios:</span></span>
    
      - <span data-ttu-id="88039-130">Ein lync Server Pool schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="88039-130">A Lync Server pool fails.</span></span> <span data-ttu-id="88039-131">In diesem Szenario ist es erforderlich, jeden Server im Pool neu zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="88039-131">This scenario requires rebuilding each server in the pool.</span></span>
    
      - <span data-ttu-id="88039-132">Ein Standard Edition-Server schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="88039-132">A Standard Edition server fails.</span></span> <span data-ttu-id="88039-133">In diesem Szenario ist es erforderlich, den Server auf einem neuen oder sauberen Computer neu zu erstellen und Datenbanken wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="88039-133">This scenario requires rebuilding the server on a new or clean computer and restoring databases.</span></span>
    
      - <span data-ttu-id="88039-134">Verlust des zentralen Verwaltungsspeichers.</span><span class="sxs-lookup"><span data-stu-id="88039-134">Loss of the Central Management store.</span></span> <span data-ttu-id="88039-135">Dieses Szenario erfordert mindestens die Wiederherstellung und Veröffentlichung des zentralen Verwaltungsspeichers.</span><span class="sxs-lookup"><span data-stu-id="88039-135">At a minimum, this scenario requires restoring and publishing the Central Management store.</span></span>
    
      - <span data-ttu-id="88039-136">Verlust eines Back-End-Servers, wenn der zentrale Verwaltungsspeicher noch normal funktioniert.</span><span class="sxs-lookup"><span data-stu-id="88039-136">Loss of a Back End Server when the Central Management store is still functioning normally.</span></span> <span data-ttu-id="88039-137">In diesem Szenario ist es erforderlich, den Server auf einem neuen oder sauberen Computer neu zu erstellen und Datenbanken wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="88039-137">This scenario requires rebuilding the server on a new or clean computer and restoring databases.</span></span>
    
      - <span data-ttu-id="88039-138">Ein Server, der Mitglied eines lync Server Pools ist, schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="88039-138">A server that is a member of a Lync Server pool fails.</span></span> <span data-ttu-id="88039-139">In diesem Szenario ist es erforderlich, den Server auf einem neuen oder sauberen Computer neu zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="88039-139">This scenario requires rebuilding the server on a new or clean computer.</span></span>
    
      - <span data-ttu-id="88039-140">Ein Dateispeicher schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="88039-140">A File Store fails.</span></span> <span data-ttu-id="88039-141">In diesem Szenario muss der Dateiserver oder der Dateicluster wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="88039-141">This scenario requires restoring the file server or file cluster.</span></span>
    
      - <span data-ttu-id="88039-142">Eine Datenbank für Archivierung, Überwachung oder beständigen Chat schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="88039-142">An Archiving, Monitoring, or Persistent Chat database fails.</span></span> <span data-ttu-id="88039-143">Dieses Szenario erfordert das Neuerstellen der Datenbanken und, wenn die Daten für Ihre Organisation wichtig sind, die Wiederherstellung der Daten.</span><span class="sxs-lookup"><span data-stu-id="88039-143">This scenario requires recreating the databases, and, if the data is critical to your organization, restoring the data.</span></span> <span data-ttu-id="88039-144">Das Archivieren, überwachen und beständigen Chat Daten ist nicht erforderlich, um lync Server Sicherung und Ausführung zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="88039-144">Archiving, Monitoring, and Persistent Chat data is not required to get Lync Server back up and running.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

