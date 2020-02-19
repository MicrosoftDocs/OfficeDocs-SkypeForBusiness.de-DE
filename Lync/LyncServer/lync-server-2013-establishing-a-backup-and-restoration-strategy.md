---
title: 'Lync Server 2013: Einrichten einer Sicherungs-und Wiederherstellungsstrategie'
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
ms.openlocfilehash: dcdfbb6b51a966149451e8f396b345b0383947e3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42131788"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="establishing-a-backup-and-restoration-strategy-for-lync-server-2013"></a><span data-ttu-id="da200-102">Einrichten einer Sicherungs-und Wiederherstellungsstrategie für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da200-102">Establishing a backup and restoration strategy for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da200-103">_**Letztes Änderungsstand des Themas:** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="da200-103">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="da200-104">Bevor Sie einen Sicherungs-und Wiederherstellungsplan für lync Server entwickeln können, müssen Sie eine Strategie entwickeln, die in die Ziele Ihrer Organisation passt.</span><span class="sxs-lookup"><span data-stu-id="da200-104">Before you can develop a backup and restoration plan for Lync Server, you need to develop a strategy that fits with your organization's goals.</span></span> <span data-ttu-id="da200-105">Um eine effektive Sicherungs-und Wiederherstellungsstrategie zu entwickeln, müssen Sie Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="da200-105">To develop an effective backup and restoration strategy, you will need to:</span></span>

  - <span data-ttu-id="da200-106">Festlegen von Geschäftsprioritäten</span><span class="sxs-lookup"><span data-stu-id="da200-106">Establish business priorities.</span></span>

  - <span data-ttu-id="da200-107">Ermitteln der Sicherungs-und Wiederherstellungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="da200-107">Identify backup and restoration requirements.</span></span>

<div>

## <a name="establishing-business-priorities"></a><span data-ttu-id="da200-108">Einrichten von Geschäftsprioritäten</span><span class="sxs-lookup"><span data-stu-id="da200-108">Establishing Business Priorities</span></span>

<span data-ttu-id="da200-109">Bewerten Sie die geschäftlichen Prioritäten Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="da200-109">Evaluate the business priorities of your organization.</span></span> <span data-ttu-id="da200-110">Normalerweise sind die folgenden primären Geschäftsprioritäten für Ihre Sicherungs-und Wiederherstellungsstrategie relevant:</span><span class="sxs-lookup"><span data-stu-id="da200-110">Typically, the primary business priorities that affect your backup and restoration strategy are the following:</span></span>

  - <span data-ttu-id="da200-111">Anforderungen an die Geschäftskontinuität</span><span class="sxs-lookup"><span data-stu-id="da200-111">Business continuity requirements</span></span>

  - <span data-ttu-id="da200-112">Datenvollständigkeit</span><span class="sxs-lookup"><span data-stu-id="da200-112">Data completeness</span></span>

  - <span data-ttu-id="da200-113">Daten kritisch</span><span class="sxs-lookup"><span data-stu-id="da200-113">Data criticality</span></span>

  - <span data-ttu-id="da200-114">Portabilitäts Anforderungen</span><span class="sxs-lookup"><span data-stu-id="da200-114">Portability requirements</span></span>

  - <span data-ttu-id="da200-115">Kosteneinschränkungen</span><span class="sxs-lookup"><span data-stu-id="da200-115">Cost constraints</span></span>

<span data-ttu-id="da200-116">Geschäftliche Anforderungen wie diese helfen bei der Bestimmung der Vereinbarungen zum Service Level (Service Level Agreements, SLAs), die Sie mit ihren Kunden entwickeln.</span><span class="sxs-lookup"><span data-stu-id="da200-116">Business needs such as these help to determine the service level agreements (SLAs) that you develop with your customers.</span></span> <span data-ttu-id="da200-117">Vereinbarungen zum Service Level beeinflussen die Sicherungs-und Wiederherstellungsstrategie stark.</span><span class="sxs-lookup"><span data-stu-id="da200-117">Service level agreements greatly influence your backup and recovery strategy.</span></span>

</div>

<div>

## <a name="identifying-backup-and-restoration-requirements"></a><span data-ttu-id="da200-118">Identifizieren der Sicherungs-und Wiederherstellungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="da200-118">Identifying Backup and Restoration Requirements</span></span>

<span data-ttu-id="da200-119">Ihre geschäftlichen Prioritäten und Vereinbarungen zum Service Level dienen der Bestimmung der Anforderungen Ihrer Organisation zum Sichern und Wiederherstellen von lync Server.</span><span class="sxs-lookup"><span data-stu-id="da200-119">Your business priorities and service level agreements act in determining your organizations' requirements for backing up and restoring Lync Server.</span></span> <span data-ttu-id="da200-120">Identifizieren und dokumentieren Sie Ihre Anforderungen für Folgendes:</span><span class="sxs-lookup"><span data-stu-id="da200-120">Identify and document your requirements for the following:</span></span>

  - <span data-ttu-id="da200-121">**Häufigkeit von Sicherungen**   ausführliche Informationen zu bewährten Methoden für die Sicherungshäufigkeit finden Sie unter [bewährte Methoden für die Sicherung und Wiederherstellung für lync Server 2013](lync-server-2013-best-practices-for-backup-and-restoration.md).</span><span class="sxs-lookup"><span data-stu-id="da200-121">**Frequency of backups**   For details about best practices for backup frequency, see [Best practices for backup and restoration for Lync Server 2013](lync-server-2013-best-practices-for-backup-and-restoration.md).</span></span>

  - <span data-ttu-id="da200-122">**Zu den Sicherungs-und Wiederherstellungstools**   gehören die Benutzer, die die Tools verwenden sollen, und auf welchen Computern.</span><span class="sxs-lookup"><span data-stu-id="da200-122">**Backup and restoration tools**   Include who is to use the tools, and on which computers.</span></span> <span data-ttu-id="da200-123">Ausführliche Informationen zu den in diesem Thema und den erforderlichen Berechtigungen beschriebenen Tools finden Sie unter [Sicherungs-und Wiederherstellungsanforderungen in lync Server 2013: Tools and Permissions](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="da200-123">For details about the tools discussed in this topic and necessary permissions, see [Backup and restoration requirements in Lync Server 2013: tools and permissions](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span></span>

  - <span data-ttu-id="da200-124">**Sicherungsspeicherort**   ermitteln Sie, ob die Sicherungen lokal oder Remote aufbewahrt werden, wobei Sicherheit und Barrierefreiheit berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="da200-124">**Backup location**   Identify whether the backups are kept locally or remotely, taking security and accessibility into consideration.</span></span> <span data-ttu-id="da200-125">Geben Sie die Medien an, die für die Sicherungen verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="da200-125">Specify the media to be used for the backups.</span></span>

  - <span data-ttu-id="da200-126">**Hardware-und Softwareanforderungen**   identifizieren und dokumentieren ihre spezifischen Hardware-und Softwareanforderungen, einschließlich der Hardware für den Sicherungsspeicher und der Wiederherstellung bestimmter Komponenten sowie der erforderlichen Software-und Netzwerkkonnektivität zur Unterstützung von Sicherung und Wiederherstellung.</span><span class="sxs-lookup"><span data-stu-id="da200-126">**Hardware and software requirements**   Identify and document your specific hardware and software requirements, including the hardware for backup storage and restoration of specific components and any software and network connectivity required to support backup and restoration.</span></span> <span data-ttu-id="da200-127">Beachten Sie bei der Entwicklung Ihrer Hardware-und Softwareanforderungen die verschiedenen Wiederherstellungsszenarien, die befolgt werden.</span><span class="sxs-lookup"><span data-stu-id="da200-127">As you develop your hardware and software requirements, keep in mind the various restoration scenarios that follow.</span></span>

  - <span data-ttu-id="da200-128">**Wiederherstellungsszenarien**   sind hier die Wiederherstellungsprozesse für die folgenden Szenarien:</span><span class="sxs-lookup"><span data-stu-id="da200-128">**Restoration scenarios**   Here are the restoration processes for the following scenarios:</span></span>
    
      - <span data-ttu-id="da200-129">Ein lync Server Pool schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="da200-129">A Lync Server pool fails.</span></span> <span data-ttu-id="da200-130">In diesem Szenario ist es erforderlich, jeden Server im Pool neu zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="da200-130">This scenario requires rebuilding each server in the pool.</span></span>
    
      - <span data-ttu-id="da200-131">Ein Standard Edition-Server schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="da200-131">A Standard Edition server fails.</span></span> <span data-ttu-id="da200-132">In diesem Szenario ist es erforderlich, den Server auf einem neuen oder sauberen Computer neu zu erstellen und Datenbanken wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="da200-132">This scenario requires rebuilding the server on a new or clean computer and restoring databases.</span></span>
    
      - <span data-ttu-id="da200-133">Verlust des zentralen Verwaltungsspeichers.</span><span class="sxs-lookup"><span data-stu-id="da200-133">Loss of the Central Management store.</span></span> <span data-ttu-id="da200-134">Dieses Szenario erfordert mindestens die Wiederherstellung und Veröffentlichung des zentralen Verwaltungsspeichers.</span><span class="sxs-lookup"><span data-stu-id="da200-134">At a minimum, this scenario requires restoring and publishing the Central Management store.</span></span>
    
      - <span data-ttu-id="da200-135">Verlust eines Back-End-Servers, wenn der zentrale Verwaltungsspeicher noch normal funktioniert.</span><span class="sxs-lookup"><span data-stu-id="da200-135">Loss of a Back End Server when the Central Management store is still functioning normally.</span></span> <span data-ttu-id="da200-136">In diesem Szenario ist es erforderlich, den Server auf einem neuen oder sauberen Computer neu zu erstellen und Datenbanken wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="da200-136">This scenario requires rebuilding the server on a new or clean computer and restoring databases.</span></span>
    
      - <span data-ttu-id="da200-137">Ein Server, der Mitglied eines lync Server Pools ist, schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="da200-137">A server that is a member of a Lync Server pool fails.</span></span> <span data-ttu-id="da200-138">In diesem Szenario ist es erforderlich, den Server auf einem neuen oder sauberen Computer neu zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="da200-138">This scenario requires rebuilding the server on a new or clean computer.</span></span>
    
      - <span data-ttu-id="da200-139">Ein Dateispeicher schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="da200-139">A File Store fails.</span></span> <span data-ttu-id="da200-140">In diesem Szenario muss der Dateiserver oder der Dateicluster wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="da200-140">This scenario requires restoring the file server or file cluster.</span></span>
    
      - <span data-ttu-id="da200-141">Eine Datenbank für Archivierung, Überwachung oder beständigen Chat schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="da200-141">An Archiving, Monitoring, or Persistent Chat database fails.</span></span> <span data-ttu-id="da200-142">Dieses Szenario erfordert das Neuerstellen der Datenbanken und, wenn die Daten für Ihre Organisation wichtig sind, die Wiederherstellung der Daten.</span><span class="sxs-lookup"><span data-stu-id="da200-142">This scenario requires recreating the databases, and, if the data is critical to your organization, restoring the data.</span></span> <span data-ttu-id="da200-143">Das Archivieren, überwachen und beständigen Chat Daten ist nicht erforderlich, um lync Server Sicherung und Ausführung zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="da200-143">Archiving, Monitoring, and Persistent Chat data is not required to get Lync Server back up and running.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

