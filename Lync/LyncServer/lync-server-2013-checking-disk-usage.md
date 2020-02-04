---
title: 'Lync Server 2013: Überprüfen der Datenträgerverwendung'
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
ms.openlocfilehash: 554b493ba7ca837a8ea5c80f6751ddb91061c374
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726695"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="checking-disk-usage-in-lync-server-2013"></a><span data-ttu-id="b82db-102">Überprüfen der Datenträgerverwendung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b82db-102">Checking disk usage in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b82db-103">_**Letztes Änderungsdatum des Themas:** 2014-04-30_</span><span class="sxs-lookup"><span data-stu-id="b82db-103">_**Topic Last Modified:** 2014-04-30_</span></span>

<span data-ttu-id="b82db-104">Festplatten-Laufwerke sind eine wichtige Komponente der lync Server 2013-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="b82db-104">Hard disks drives are an important component of the Lync Server 2013 deployment.</span></span> <span data-ttu-id="b82db-105">Ohne ausreichend freien Festplattenspeicher können weder das Betriebssystem noch die lync Server 2013-Datenbanken ordnungsgemäß funktionieren.</span><span class="sxs-lookup"><span data-stu-id="b82db-105">Without sufficient free disk volume, neither the operating system nor the Lync Server 2013 databases can function correctly.</span></span> <span data-ttu-id="b82db-106">Sie müssen die lync Server 2013-Datenbankstatistik für die Back-End-Datenbank täglich überwachen, um sicherzustellen, dass auf den Servern nicht genügend Speicherplatz vorhanden ist, und um sich vorzubereiten, wie erforderlich Speicherressourcen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b82db-106">You must monitor the Lync Server 2013 back-end database statistics daily to help to make sure that servers do not run out of disk space, and to prepare to add storage resources as required.</span></span>

<span data-ttu-id="b82db-107">Neben der Überprüfung des Speicherplatzes auf Festplatten, die das Betriebssystem, die Programmdateien, die Datenbank und die Transaktionsprotokolle (lync Server 2013-Back-End) hosten, sollten Sie auch die Verwendung des Dateisystems überwachen, das Speicherplatz für Dateifreigaben enthält, die die folgenden wichtigen Daten enthalten: Daten</span><span class="sxs-lookup"><span data-stu-id="b82db-107">Apart from checking space on disks hosting the operating system, program files, database, and transaction logs (Lync Server 2013 Back End), you should also monitor usage of the file system that includes disk space for file shares that contain the following important data:</span></span>

  - <span data-ttu-id="b82db-108">Besprechungsinhalte</span><span class="sxs-lookup"><span data-stu-id="b82db-108">Meeting content</span></span>

  - <span data-ttu-id="b82db-109">Metadaten für Besprechungsinhalte</span><span class="sxs-lookup"><span data-stu-id="b82db-109">Meeting content metadata</span></span>

  - <span data-ttu-id="b82db-110">Kompatibilitäts Protokolle für Besprechungen</span><span class="sxs-lookup"><span data-stu-id="b82db-110">Meeting compliance logs</span></span>

  - <span data-ttu-id="b82db-111">Anwendungsdaten Dateien (intern von der Anwendungsserverkomponente verwendet)</span><span class="sxs-lookup"><span data-stu-id="b82db-111">Application data files (used internally by the application server component)</span></span>

  - <span data-ttu-id="b82db-112">Web Service-und Compliance-Ordner für Gruppen-Chat Server (zum Speichern von Dateien, die in den Gruppen-Chat-Webdienst hochgeladen wurden)</span><span class="sxs-lookup"><span data-stu-id="b82db-112">Group Chat Server web service and compliance folders (to store files uploaded to the Group Chat web service)</span></span>

  - <span data-ttu-id="b82db-113">XML-Dateien für Gruppen-Chat-Compliance (mit Gruppen-Chat-Konformitäts Einträgen)</span><span class="sxs-lookup"><span data-stu-id="b82db-113">Group Chat compliance XML files (that contain Group Chat compliance records)</span></span>

  - <span data-ttu-id="b82db-114">Aktualisieren von Dateien (für den Geräteaktualisierungsdienst)</span><span class="sxs-lookup"><span data-stu-id="b82db-114">Update files (for Device Update Service)</span></span>

  - <span data-ttu-id="b82db-115">Adressbuchdateien</span><span class="sxs-lookup"><span data-stu-id="b82db-115">Address Book files</span></span>

<span data-ttu-id="b82db-116">Lync Server 2013 benötigt Festplattenspeicher, um die Datenbanken und Transaktionsprotokolle zusätzlich zu den zuvor aufgelisteten Dateien auf Dateifreigaben zu speichern.</span><span class="sxs-lookup"><span data-stu-id="b82db-116">Lync Server 2013 needs hard disk space to store its databases and transaction logs in addition to files on file shares previously listed.</span></span>

<span data-ttu-id="b82db-117">Sie sollten den Speicherplatz regelmäßig überwachen, um sicherzustellen, dass die lync Server 2013-Bereitstellung aufgrund unzureichender Speicherressourcen nicht beeinträchtigt wird.</span><span class="sxs-lookup"><span data-stu-id="b82db-117">You should monitor the disk space regularly to help to make sure that the Lync Server 2013 deployment is not adversely affected because of insufficient storage resources.</span></span>

<span data-ttu-id="b82db-118">Vergleichen und verwalten Sie statistische Informationen zu dem verfügbaren Speicherplatz auf den einzelnen lync Server 2013-Volumes und dem erwarteten Wachstum der Datenbanken und Transaktionsprotokolldateien.</span><span class="sxs-lookup"><span data-stu-id="b82db-118">Compare and maintain statistical information about available disk space on each Lync Server 2013 volume and expected growth of the databases and transaction log files.</span></span> <span data-ttu-id="b82db-119">Dies hilft bei der Kapazitätsplanung und beim Hinzufügen von Speicher, wenn die Speicherressourcen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="b82db-119">This helps with capacity planning and adding storage when the storage resources are required.</span></span>

<span data-ttu-id="b82db-120">Zur Unterstützung von Problemen bei der Problembehandlung und Notfallwiederherstellung empfiehlt es sich, den verfügbaren freien Speicherplatz gleich oder größer als 110 Prozent der Datenbankgröße zu haben.</span><span class="sxs-lookup"><span data-stu-id="b82db-120">To accommodate troubleshooting and disaster recovery situations, we recommend that available free volume space be equal or greater than 110 percent of the size of database.</span></span>

<span data-ttu-id="b82db-121">Sie können den freien Speicherplatz überprüfen, indem Sie die folgenden Methoden verwenden:</span><span class="sxs-lookup"><span data-stu-id="b82db-121">You can check free disk space by using the following methods:</span></span>

1.  <span data-ttu-id="b82db-122">**System Center Operations Manager**   System Center Operations Manager kann verwendet werden, um Administratoren zu warnen, wenn der Speicherplatz für Volumes begrenzt ist.</span><span class="sxs-lookup"><span data-stu-id="b82db-122">**System Center Operations Manager**   System Center Operations Manager can be used to warn administrators when volume space is constrained.</span></span>

2.  <span data-ttu-id="b82db-123">**Beim Ausführen eines Skripts**   wird der Speicherplatz durch Ausführen eines Skripts überwacht, das Ihnen eine Nachricht sendet, wenn der verfügbare Festplattenspeicherplatz unter 20 Prozent fällt.</span><span class="sxs-lookup"><span data-stu-id="b82db-123">**Running a script**   Monitor disk space by running a script that sends you a message if the available hard disk space falls below 20 percent.</span></span> <span data-ttu-id="b82db-124">Sie können ein Beispielskript im Microsoft Script Center auf TechNet finden, indem Sie Folgendes untersuchen:[http://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard%20disk%20alert\&f%5B0%5D.Value=hard%20disk%20alert\&f%5B0%5D.Type=SearchText\&ac=5](http://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard+disk+alert%26f%5b0%5d.value=hard+disk+alert%26f%5b0%5d.type=searchtext%26ac=5)</span><span class="sxs-lookup"><span data-stu-id="b82db-124">You can find a sample script on Microsoft Script Center on TechNet, examine: [http://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard%20disk%20alert\&f%5B0%5D.Value=hard%20disk%20alert\&f%5B0%5D.Type=SearchText\&ac=5](http://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard+disk+alert%26f%5b0%5d.value=hard+disk+alert%26f%5b0%5d.type=searchtext%26ac=5)</span></span>

3.  <span data-ttu-id="b82db-125">**Windows**   -Explorer verwenden Sie den Windows-Explorer, um den Speicherplatz auf Volumes zu überprüfen, die lync Server 2013-Protokolle und-Datenbanken speichern.</span><span class="sxs-lookup"><span data-stu-id="b82db-125">**Windows Explorer**   Use Windows Explorer to check for disk space on volumes that store Lync Server 2013 logs and databases.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

