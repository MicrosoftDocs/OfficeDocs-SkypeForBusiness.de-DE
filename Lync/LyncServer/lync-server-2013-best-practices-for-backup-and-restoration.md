---
title: 'Lync Server 2013: bewährte Methoden für Sicherung und Wiederherstellung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for backup and restoration
ms:assetid: abbce0e4-973a-4624-a0c1-e0f22e1d348b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202184(v=OCS.15)
ms:contentKeyID: 51541500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca14913d063a8691d0477af912e70e72b91143fa
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535202"
---
# <a name="best-practices-for-backup-and-restoration-for-lync-server-2013"></a><span data-ttu-id="be23a-102">Bewährte Methoden für die Sicherung und Wiederherstellung für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be23a-102">Best practices for backup and restoration for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="be23a-103">_**Letztes Änderungsstand des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="be23a-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="be23a-104">In diesem Abschnitt werden bewährte Methoden für zwei wichtige Bereiche beschrieben:</span><span class="sxs-lookup"><span data-stu-id="be23a-104">This section includes two types of best practices:</span></span>

  - <span data-ttu-id="be23a-105">Bewährte Methoden für Sicherung und Wiederherstellung.</span><span class="sxs-lookup"><span data-stu-id="be23a-105">Best practices for backup and restoration.</span></span>

  - <span data-ttu-id="be23a-106">Bewährte Methoden für die Minimierung der Auswirkungen eines Notfalls.</span><span class="sxs-lookup"><span data-stu-id="be23a-106">Best practices for minimizing the impact of a disaster.</span></span>

<div>

## <a name="best-practices-for-backup-and-restoration"></a><span data-ttu-id="be23a-107">Bewährte Methoden für die Sicherung und Wiederherstellung</span><span class="sxs-lookup"><span data-stu-id="be23a-107">Best Practices for Backup and Restoration</span></span>

<span data-ttu-id="be23a-108">Wenden Sie beim Sichern oder Wiederherstellen Ihrer Daten die folgenden bewährten Methoden an, um den Sicherungs-und Wiederherstellungsvorgang zu vereinfachen:</span><span class="sxs-lookup"><span data-stu-id="be23a-108">To facilitate your backup and restoration process, apply the following best practices when you back up or restore your data:</span></span>

  - <span data-ttu-id="be23a-109">Führen Sie regelmäßige Sicherungen in geeigneten Zeitabständen aus.</span><span class="sxs-lookup"><span data-stu-id="be23a-109">Perform regular backups at appropriate intervals.</span></span> <span data-ttu-id="be23a-110">Der einfachste und am häufigsten angewendete Sicherungstyp und -zeitplan ist eine vollständige nächtliche Sicherung der gesamten SQL Server-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="be23a-110">The simplest and most commonly used backup type and rotation schedule is a full, nightly backup of the entire SQL Server database.</span></span> <span data-ttu-id="be23a-111">Wenn die Wiederherstellung erforderlich ist, erfordert der Wiederherstellungsprozess dann nur eine Sicherung, und es sollten nicht mehr als die Daten eines Tages verloren gehen.</span><span class="sxs-lookup"><span data-stu-id="be23a-111">Then, if restoration is necessary, the restoration process requires only one backup, and no more than a day’s data should be lost.</span></span>

  - <span data-ttu-id="be23a-112">Wenn Sie mithilfe von Cmdlets oder der lync Server-Systemsteuerung Konfigurationsänderungen vornehmen, verwenden Sie das Cmdlet **Export-CsConfiguration** , um eine Snapshot-Sicherung der Topologie-Konfigurationsdatei (XDS. mdf) zu erstellen, damit Sie die Änderungen nicht verlieren, wenn Sie die Datenbanken wiederherstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="be23a-112">If you use cmdlets or the Lync Server Control Panel to make configuration changes, use the **Export-CsConfiguration** cmdlet to take a snapshot backup of the topology configuration file (Xds.mdf) after you make the changes, so that you won't lose the changes if you need to restore your databases.</span></span> <span data-ttu-id="be23a-113">Beachten Sie, dass diese Konfiguration im XML-Format gesichert und als ZIP-Datei komprimiert wird.</span><span class="sxs-lookup"><span data-stu-id="be23a-113">Note that this configuration is backed up in XML format and compressed as a ZIP file.</span></span>

  - <span data-ttu-id="be23a-114">Stellen Sie sicher, dass der freigegebene Ordner, den Sie für die Sicherung lync Server verwenden möchten, über ausreichend Speicherplatz verfügt, um alle gesicherten Daten zu speichern.</span><span class="sxs-lookup"><span data-stu-id="be23a-114">Make sure that the shared folder you plan to use for backing up Lync Server has sufficient disk space to hold all the backed up data.</span></span>

  - <span data-ttu-id="be23a-115">Planen Sie Sicherungen, wenn lync Server Nutzung normalerweise niedrig ist, um die Server Leistung und Benutzerfreundlichkeit zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="be23a-115">Schedule backups when Lync Server usage is typically low, to improve server performance and user experience.</span></span>

  - <span data-ttu-id="be23a-116">Stellen Sie sicher, dass der Speicherort, an dem Sie Daten sichern, gesichert ist (Wir empfehlen einen Remotestandort).</span><span class="sxs-lookup"><span data-stu-id="be23a-116">Make sure that the location where you back up data is secure (we recommend a remote location).</span></span>

  - <span data-ttu-id="be23a-117">Bewahren Sie die Sicherungsdateien auf, in denen Sie verfügbar sein werden, falls Sie die Daten wiederherstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="be23a-117">Keep the backup files where they will be available, in case you need to restore the data.</span></span>

  - <span data-ttu-id="be23a-118">Planen und planen Sie regelmäßige Tests der Wiederherstellungsprozesse, die von Ihrer Organisation unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="be23a-118">Plan for and schedule periodic testing of the restoration processes that are supported by your organization.</span></span>

  - <span data-ttu-id="be23a-119">Überprüfen Sie Ihre Sicherungs-und Wiederherstellungsprozesse im voraus, um sicherzustellen, dass Sie erwartungsgemäß funktionieren.</span><span class="sxs-lookup"><span data-stu-id="be23a-119">Validate your backup and restoration processes in advance to make sure that they work as expected.</span></span>

</div>

<div>

## <a name="best-practices-for-minimizing-the-impact-of-a-disaster"></a><span data-ttu-id="be23a-120">Bewährte Methoden für die Minimierung der Auswirkungen eines Notfalls</span><span class="sxs-lookup"><span data-stu-id="be23a-120">Best Practices for Minimizing the Impact of a Disaster</span></span>

<span data-ttu-id="be23a-121">Die beste Strategie für den Umgang mit katastrophalen Dienstunterbrechungen (verursacht durch nicht verwaltbare Ereignisse wie Stromausfälle oder plötzliche Hardwarefehler) besteht darin, davon ausgehen, dass Sie geschehen werden, und entsprechend zu planen.</span><span class="sxs-lookup"><span data-stu-id="be23a-121">The best strategy for dealing with disastrous service interruptions (caused by unmanageable events such as power outages or sudden hardware failures) is to assume they will happen, and to plan accordingly.</span></span>

<span data-ttu-id="be23a-122">Wenn lync Services mit einem Minimum an unterbrechungs-und Ausfallzeiten für Ihre Organisation geschäftskritisch sind, sollten Sie die Implementierung gekoppelter Pools von Front-End-Servern in Betracht gezogen, wie in [Planen für hohe Verfügbarkeit und Notfallwiederherstellung in lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="be23a-122">If Lync services, with a minimum of disruption and outage, are business-critical for your organization, you should consider implementing paired pools of Front End Servers, as described in [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="be23a-123">Wenn dann ein solcher Pool einen Notfall aufweist, kann ein Administrator die Benutzer dieses Pools mit einem Minimum an Ausfallzeiten umstellen, um vom anderen Pool bedient zu werden.</span><span class="sxs-lookup"><span data-stu-id="be23a-123">Then, if one of these pools has a disaster, an administrator can switch the users of that pool to be served by the other pool, with a minimum of downtime.</span></span>

<span data-ttu-id="be23a-124">Die Notfall Verwaltungspläne, die Sie im Rahmen der Sicherungs-und Wiederherstellungsstrategie entwickeln, sollten Folgendes umfassen:</span><span class="sxs-lookup"><span data-stu-id="be23a-124">The disaster management plans that you develop as part of your backup and restoration strategy should include the following:</span></span>

  - <span data-ttu-id="be23a-125">Das aufhalten ihrer Softwaremedien und ihrer Software-und Firmware-Updates ist leicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="be23a-125">Keeping your software media, and your software and firmware updates, readily available.</span></span>

  - <span data-ttu-id="be23a-126">Führen Sie Unterlagen über Ihre Hardware und Software.</span><span class="sxs-lookup"><span data-stu-id="be23a-126">Maintaining hardware and software records.</span></span>

  - <span data-ttu-id="be23a-127">Regelmäßiges Sichern Ihrer Daten und Überwachung der Integrität Ihrer Sicherungen</span><span class="sxs-lookup"><span data-stu-id="be23a-127">Backing up your data regularly and monitoring the integrity of your backups.</span></span>

  - <span data-ttu-id="be23a-128">Schulen Sie Ihre Mitarbeiter in den Bereichen Notfallwiederherstellung und Dokumentieren von Verfahren, und führen Sie Übungen mit Simulationen der Notfallwiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="be23a-128">Training your staff in disaster recovery, documenting procedures, and implementing disaster recovery simulation drills.</span></span>

  - <span data-ttu-id="be23a-129">Wenn Sie Ersatzhardware zur Verfügung stellen oder wenn Sie über eine Vereinbarung zum Service Level (SLA) verfügen, beauftragen Sie die Hardwareanbieter und Lieferanten für eine sofortige Ersetzung.</span><span class="sxs-lookup"><span data-stu-id="be23a-129">Keeping spare hardware available, or, if you have a service level agreement (SLA), contracting with hardware vendors and suppliers for prompt replacements.</span></span>

  - <span data-ttu-id="be23a-130">Speichern Sie die Transaktionsprotokolldateien (LDF-Dateien) getrennt von den Datenbankdateien (MDF-Dateien).</span><span class="sxs-lookup"><span data-stu-id="be23a-130">Separating the location of your transaction log files (.ldf files) and database files (.mdf files).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

