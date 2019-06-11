---
title: 'Lync Server 2013: bewährte Methoden für Sicherung und Wiederherstellung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Best practices for backup and restoration
ms:assetid: abbce0e4-973a-4624-a0c1-e0f22e1d348b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202184(v=OCS.15)
ms:contentKeyID: 51541500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fc7a926bd8fd5c61f87d5e8252c30f40e5a6a69
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839725"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-backup-and-restoration-for-lync-server-2013"></a><span data-ttu-id="d5b32-102">Bewährte Methoden für die Sicherung und Wiederherstellung für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5b32-102">Best practices for backup and restoration for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5b32-103">_**Letztes Änderungsdatum des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="d5b32-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="d5b32-104">Dieser Abschnitt enthält zwei Arten von bewährten Methoden:</span><span class="sxs-lookup"><span data-stu-id="d5b32-104">This section includes two types of best practices:</span></span>

  - <span data-ttu-id="d5b32-105">Bewährte Methoden für Sicherung und Wiederherstellung</span><span class="sxs-lookup"><span data-stu-id="d5b32-105">Best practices for backup and restoration.</span></span>

  - <span data-ttu-id="d5b32-106">Bewährte Methoden zum Minimieren der Auswirkungen eines Notfalls</span><span class="sxs-lookup"><span data-stu-id="d5b32-106">Best practices for minimizing the impact of a disaster.</span></span>

<div>

## <a name="best-practices-for-backup-and-restoration"></a><span data-ttu-id="d5b32-107">Bewährte Methoden für Sicherung und Wiederherstellung</span><span class="sxs-lookup"><span data-stu-id="d5b32-107">Best Practices for Backup and Restoration</span></span>

<span data-ttu-id="d5b32-108">Wenden Sie beim Sichern oder Wiederherstellen Ihrer Daten die folgenden bewährten Methoden an, um den Sicherungs-und Wiederherstellungsprozess zu vereinfachen:</span><span class="sxs-lookup"><span data-stu-id="d5b32-108">To facilitate your backup and restoration process, apply the following best practices when you back up or restore your data:</span></span>

  - <span data-ttu-id="d5b32-109">Führen Sie regelmäßige Sicherungen in angemessenen Abständen aus.</span><span class="sxs-lookup"><span data-stu-id="d5b32-109">Perform regular backups at appropriate intervals.</span></span> <span data-ttu-id="d5b32-110">Der einfachste und am häufigsten verwendete Backup-Typ und-Rotations Zeitplan ist eine vollständige, nächtliche Sicherung der gesamten SQL Server-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="d5b32-110">The simplest and most commonly used backup type and rotation schedule is a full, nightly backup of the entire SQL Server database.</span></span> <span data-ttu-id="d5b32-111">Wenn die Wiederherstellung erforderlich ist, erfordert der Wiederherstellungsprozess nur eine Sicherung, und es sollten nicht mehr als die Daten eines Tages verloren gehen.</span><span class="sxs-lookup"><span data-stu-id="d5b32-111">Then, if restoration is necessary, the restoration process requires only one backup, and no more than a day’s data should be lost.</span></span>

  - <span data-ttu-id="d5b32-112">Wenn Sie mithilfe von Cmdlets oder der lync Server-Systemsteuerung Konfigurationsänderungen vornehmen, verwenden Sie das Cmdlet **Export-CsConfiguration** , um eine Snapshot-Sicherung der Topologie-Konfigurationsdatei (XDS. mdf) zu erstellen, nachdem Sie die Änderungen vorgenommen haben, damit die Änderungen nicht verloren gehen, wenn Sie müssen Ihre Datenbanken wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="d5b32-112">If you use cmdlets or the Lync Server Control Panel to make configuration changes, use the **Export-CsConfiguration** cmdlet to take a snapshot backup of the topology configuration file (Xds.mdf) after you make the changes, so that you won't lose the changes if you need to restore your databases.</span></span> <span data-ttu-id="d5b32-113">Beachten Sie, dass diese Konfiguration im XML-Format gesichert und als ZIP-Datei komprimiert wird.</span><span class="sxs-lookup"><span data-stu-id="d5b32-113">Note that this configuration is backed up in XML format and compressed as a ZIP file.</span></span>

  - <span data-ttu-id="d5b32-114">Stellen Sie sicher, dass der freigegebene Ordner, den Sie zum Sichern von lync Server verwenden möchten, über genügend Speicherplatz verfügt, um alle gesicherten Daten zu speichern.</span><span class="sxs-lookup"><span data-stu-id="d5b32-114">Make sure that the shared folder you plan to use for backing up Lync Server has sufficient disk space to hold all the backed up data.</span></span>

  - <span data-ttu-id="d5b32-115">Planen Sie Sicherungen, wenn die lync Server-Auslastung in der Regel gering ist, um die Serverleistung und die Benutzerfreundlichkeit zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="d5b32-115">Schedule backups when Lync Server usage is typically low, to improve server performance and user experience.</span></span>

  - <span data-ttu-id="d5b32-116">Stellen Sie sicher, dass der Speicherort, an dem Sie Daten sichern, sicher ist (Wir empfehlen einen Remotestandort).</span><span class="sxs-lookup"><span data-stu-id="d5b32-116">Make sure that the location where you back up data is secure (we recommend a remote location).</span></span>

  - <span data-ttu-id="d5b32-117">Bewahren Sie die Sicherungsdateien auf, wo Sie verfügbar sein werden, falls Sie die Daten wiederherstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="d5b32-117">Keep the backup files where they will be available, in case you need to restore the data.</span></span>

  - <span data-ttu-id="d5b32-118">Planen und planen Sie regelmäßige Tests der Wiederherstellungsprozesse, die von Ihrer Organisation unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="d5b32-118">Plan for and schedule periodic testing of the restoration processes that are supported by your organization.</span></span>

  - <span data-ttu-id="d5b32-119">Überprüfen Sie Ihre Sicherungs-und Wiederherstellungsprozesse im voraus, um sicherzustellen, dass Sie wie erwartet funktionieren.</span><span class="sxs-lookup"><span data-stu-id="d5b32-119">Validate your backup and restoration processes in advance to make sure that they work as expected.</span></span>

</div>

<div>

## <a name="best-practices-for-minimizing-the-impact-of-a-disaster"></a><span data-ttu-id="d5b32-120">Bewährte Methoden zum Minimieren der Auswirkungen eines Notfalls</span><span class="sxs-lookup"><span data-stu-id="d5b32-120">Best Practices for Minimizing the Impact of a Disaster</span></span>

<span data-ttu-id="d5b32-121">Die beste Strategie für den Umgang mit katastrophalen Dienstunterbrechungen (verursacht durch nicht verwaltbare Ereignisse wie Stromausfälle oder plötzliche Hardwareausfälle) besteht darin, davon auszugehen, dass dies geschieht, und entsprechend zu planen.</span><span class="sxs-lookup"><span data-stu-id="d5b32-121">The best strategy for dealing with disastrous service interruptions (caused by unmanageable events such as power outages or sudden hardware failures) is to assume they will happen, and to plan accordingly.</span></span>

<span data-ttu-id="d5b32-122">Wenn die lync-Dienste mit einem mindestunterbrechungs-und Ausfallrisiko für Ihre Organisation unternehmenskritisch sind, sollten Sie in der Lage sein, gekoppelte Pools von Front-End-Servern zu implementieren, wie unter [Planen von hoher Verfügbarkeit und Disaster Recovery in lync Server beschrieben. 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="d5b32-122">If Lync services, with a minimum of disruption and outage, are business-critical for your organization, you should consider implementing paired pools of Front End Servers, as described in [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="d5b32-123">Wenn eines dieser Pools einen Notfall hat, kann ein Administrator die Benutzer des Pools so umschalten, dass Sie mit einem mindestausfall von einem anderen Pool bedient werden.</span><span class="sxs-lookup"><span data-stu-id="d5b32-123">Then, if one of these pools has a disaster, an administrator can switch the users of that pool to be served by the other pool, with a minimum of downtime.</span></span>

<span data-ttu-id="d5b32-124">Die Notfall Verwaltungspläne, die Sie im Rahmen ihrer Sicherungs-und Wiederherstellungsstrategie entwickeln, sollten Folgendes umfassen:</span><span class="sxs-lookup"><span data-stu-id="d5b32-124">The disaster management plans that you develop as part of your backup and restoration strategy should include the following:</span></span>

  - <span data-ttu-id="d5b32-125">Sie können Ihr Software-Medium sowie Ihre Software-und Firmware-Updates bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="d5b32-125">Keeping your software media, and your software and firmware updates, readily available.</span></span>

  - <span data-ttu-id="d5b32-126">Verwalten von Hardware-und Software Datensätzen</span><span class="sxs-lookup"><span data-stu-id="d5b32-126">Maintaining hardware and software records.</span></span>

  - <span data-ttu-id="d5b32-127">Regelmäßiges Sichern Ihrer Daten und Überwachen der Integrität Ihrer Sicherungen</span><span class="sxs-lookup"><span data-stu-id="d5b32-127">Backing up your data regularly and monitoring the integrity of your backups.</span></span>

  - <span data-ttu-id="d5b32-128">Schulung Ihrer Mitarbeiter in Disaster Recovery, Dokumentation von Verfahren und Implementierung von Disaster Recovery-Simulationsübungen.</span><span class="sxs-lookup"><span data-stu-id="d5b32-128">Training your staff in disaster recovery, documenting procedures, and implementing disaster recovery simulation drills.</span></span>

  - <span data-ttu-id="d5b32-129">Wenn Sie Ersatzhardware zur Verfügung haben oder wenn Sie über einen Service Level Agreement (SLA) verfügen, können Sie sich mit Hardwareanbietern und Lieferanten für den sofortigen Austausch beauftragen.</span><span class="sxs-lookup"><span data-stu-id="d5b32-129">Keeping spare hardware available, or, if you have a service level agreement (SLA), contracting with hardware vendors and suppliers for prompt replacements.</span></span>

  - <span data-ttu-id="d5b32-130">Trennen des Speicherorts ihrer Transaktionsprotokolldateien (LDF-Dateien) und Datenbankdateien (MDF-Dateien)</span><span class="sxs-lookup"><span data-stu-id="d5b32-130">Separating the location of your transaction log files (.ldf files) and database files (.mdf files).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

