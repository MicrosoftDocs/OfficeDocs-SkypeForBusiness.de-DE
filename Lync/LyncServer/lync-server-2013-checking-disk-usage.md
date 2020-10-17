---
title: 'Lync Server 2013: Überprüfen der Datenträgerverwendung'
description: 'Lync Server 2013: Überprüfen der Datenträgerverwendung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Checking disk usage
ms:assetid: 0f0cb9bf-3f11-43ff-be10-5c8e1b5c4f08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720908(v=OCS.15)
ms:contentKeyID: 63969578
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7eddde772d156f0a416dab381efe1ab33ee202f9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571001"
---
# <a name="checking-disk-usage-in-lync-server-2013"></a><span data-ttu-id="61895-103">Überprüfen der Datenträgerverwendung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61895-103">Checking disk usage in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61895-104">_**Letztes Änderungsstand des Themas:** 2014-04-30_</span><span class="sxs-lookup"><span data-stu-id="61895-104">_**Topic Last Modified:** 2014-04-30_</span></span>

<span data-ttu-id="61895-105">Festplatten sind ein wichtiger Bestandteil der lync Server 2013-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="61895-105">Hard disks drives are an important component of the Lync Server 2013 deployment.</span></span> <span data-ttu-id="61895-106">Ohne ausreichend freies Festplattenvolume kann weder das Betriebssystem noch die lync Server 2013 Datenbanken ordnungsgemäß funktionieren.</span><span class="sxs-lookup"><span data-stu-id="61895-106">Without sufficient free disk volume, neither the operating system nor the Lync Server 2013 databases can function correctly.</span></span> <span data-ttu-id="61895-107">Sie müssen die Statistiken für lync Server 2013 Back-End-Datenbanken täglich überwachen, um sicherzustellen, dass auf den Servern nicht genügend Speicherplatz zur Verfügung steht und dass Sie nach Bedarf Speicherressourcen hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="61895-107">You must monitor the Lync Server 2013 back-end database statistics daily to help to make sure that servers do not run out of disk space, and to prepare to add storage resources as required.</span></span>

<span data-ttu-id="61895-108">Neben der Überprüfung des Speicherplatzes auf Datenträgern, die das Betriebssystem, die Programmdateien, die Datenbank und die Transaktionsprotokolle (lync Server 2013 Back-End) hosten, sollten Sie auch die Verwendung des Dateisystems überwachen, das Speicherplatz für Dateifreigaben enthält, die die folgenden wichtigen Daten enthalten:</span><span class="sxs-lookup"><span data-stu-id="61895-108">Apart from checking space on disks hosting the operating system, program files, database, and transaction logs (Lync Server 2013 Back End), you should also monitor usage of the file system that includes disk space for file shares that contain the following important data:</span></span>

  - <span data-ttu-id="61895-109">Besprechungsinhalte</span><span class="sxs-lookup"><span data-stu-id="61895-109">Meeting content</span></span>

  - <span data-ttu-id="61895-110">Metadaten für Besprechungsinhalte</span><span class="sxs-lookup"><span data-stu-id="61895-110">Meeting content metadata</span></span>

  - <span data-ttu-id="61895-111">Erfüllen von Kompatibilitäts Protokollen</span><span class="sxs-lookup"><span data-stu-id="61895-111">Meeting compliance logs</span></span>

  - <span data-ttu-id="61895-112">Anwendungsdatendatei (intern von der Anwendungsserverkomponente verwendet)</span><span class="sxs-lookup"><span data-stu-id="61895-112">Application data files (used internally by the application server component)</span></span>

  - <span data-ttu-id="61895-113">Group Chat Server-Webdienst und Compliance-Ordner (zum Speichern von Dateien, die in den Gruppenchat-Webdienst hochgeladen wurden)</span><span class="sxs-lookup"><span data-stu-id="61895-113">Group Chat Server web service and compliance folders (to store files uploaded to the Group Chat web service)</span></span>

  - <span data-ttu-id="61895-114">XML-Dateien für Gruppenchat-Konformität (mit Gruppenchat-Kompatibilitäts Einträgen)</span><span class="sxs-lookup"><span data-stu-id="61895-114">Group Chat compliance XML files (that contain Group Chat compliance records)</span></span>

  - <span data-ttu-id="61895-115">Aktualisieren von Dateien (für den Geräteaktualisierungsdienst)</span><span class="sxs-lookup"><span data-stu-id="61895-115">Update files (for Device Update Service)</span></span>

  - <span data-ttu-id="61895-116">Adressbuchdateien</span><span class="sxs-lookup"><span data-stu-id="61895-116">Address Book files</span></span>

<span data-ttu-id="61895-117">Lync Server 2013 benötigt auf der Festplatte Speicherplatz zum Speichern der Datenbanken und Transaktionsprotokolle sowie der zuvor aufgeführten Dateien auf Dateifreigaben.</span><span class="sxs-lookup"><span data-stu-id="61895-117">Lync Server 2013 needs hard disk space to store its databases and transaction logs in addition to files on file shares previously listed.</span></span>

<span data-ttu-id="61895-118">Sie sollten den Speicherplatz regelmäßig überwachen, um sicherzustellen, dass die lync Server 2013-Bereitstellung aufgrund unzureichender Speicherressourcen nicht beeinträchtigt wird.</span><span class="sxs-lookup"><span data-stu-id="61895-118">You should monitor the disk space regularly to help to make sure that the Lync Server 2013 deployment is not adversely affected because of insufficient storage resources.</span></span>

<span data-ttu-id="61895-119">Vergleichen und verwalten Sie statistische Informationen über den verfügbaren Speicherplatz auf jedem lync Server 2013 Volume und das erwartete Wachstum der Datenbanken und Transaktionsprotokolldateien.</span><span class="sxs-lookup"><span data-stu-id="61895-119">Compare and maintain statistical information about available disk space on each Lync Server 2013 volume and expected growth of the databases and transaction log files.</span></span> <span data-ttu-id="61895-120">Dies hilft bei der Kapazitätsplanung und beim Hinzufügen von Speicher, wenn die Speicherressourcen benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="61895-120">This helps with capacity planning and adding storage when the storage resources are required.</span></span>

<span data-ttu-id="61895-121">Zur Unterstützung der Problembehandlung und Notfall Wiederherstellungssituationen wird empfohlen, dass verfügbarer freier Speicherplatz mindestens 110% der Größe der Datenbank entspricht oder größer ist.</span><span class="sxs-lookup"><span data-stu-id="61895-121">To accommodate troubleshooting and disaster recovery situations, we recommend that available free volume space be equal or greater than 110 percent of the size of database.</span></span>

<span data-ttu-id="61895-122">Sie können den freien Speicherplatz auf der Festplatte mithilfe der folgenden Methoden überprüfen:</span><span class="sxs-lookup"><span data-stu-id="61895-122">You can check free disk space by using the following methods:</span></span>

1.  <span data-ttu-id="61895-123">**System Center Operations Manager**     System Center Operations Manager kann verwendet werden, um Administratoren zu warnen, wenn der Speicherplatz auf dem Volume eingeschränkt ist.</span><span class="sxs-lookup"><span data-stu-id="61895-123">**System Center Operations Manager**   System Center Operations Manager can be used to warn administrators when volume space is constrained.</span></span>

2.  <span data-ttu-id="61895-124">**Ausführen eines Skripts**     Überwachen Sie den Speicherplatz, indem Sie ein Skript ausführen, das Ihnen eine Nachricht sendet, wenn der verfügbare Festplattenspeicherplatz unter 20 Prozent liegt.</span><span class="sxs-lookup"><span data-stu-id="61895-124">**Running a script**   Monitor disk space by running a script that sends you a message if the available hard disk space falls below 20 percent.</span></span> <span data-ttu-id="61895-125">Ein Beispielskript im Microsoft Script Center auf TechNet finden Sie unter: [https://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard%20disk%20alert\&f%5B0%5D.Value=hard%20disk%20alert\&f%5B0%5D.Type=SearchText\&ac=5](https://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard+disk+alert%26f%5b0%5d.value=hard+disk+alert%26f%5b0%5d.type=searchtext%26ac=5)</span><span class="sxs-lookup"><span data-stu-id="61895-125">You can find a sample script on Microsoft Script Center on TechNet, examine: [https://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard%20disk%20alert\&f%5B0%5D.Value=hard%20disk%20alert\&f%5B0%5D.Type=SearchText\&ac=5](https://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard+disk+alert%26f%5b0%5d.value=hard+disk+alert%26f%5b0%5d.type=searchtext%26ac=5)</span></span>

3.  <span data-ttu-id="61895-126">**Windows-Explorer**     Überprüfen Sie mithilfe von Windows-Explorer den Speicherplatz auf Volumes, in denen lync Server 2013 Protokolle und Datenbanken gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="61895-126">**Windows Explorer**   Use Windows Explorer to check for disk space on volumes that store Lync Server 2013 logs and databases.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

