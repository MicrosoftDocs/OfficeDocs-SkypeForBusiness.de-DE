---
title: 'Lync Server 2013: Notfall Wiederherstellungstest'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disaster recovery test
ms:assetid: 04f5e747-d837-4350-9fc0-8605dbf025a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747887(v=OCS.15)
ms:contentKeyID: 63969571
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35b9aa12f7b3ae9b0c160147ad473976c92ab32e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145904"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="disaster-recovery-test-in-lync-server-2013"></a><span data-ttu-id="35ebb-102">Notfall Wiederherstellungstest in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35ebb-102">Disaster recovery test in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35ebb-103">_**Letztes Änderungsstand des Themas:** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="35ebb-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="35ebb-104">Führen Sie eine Systemwiederherstellung für einen lync Server 2013 Pool Server aus, um Ihren dokumentierten Notfall Wiederherstellungsprozess zu testen.</span><span class="sxs-lookup"><span data-stu-id="35ebb-104">Perform a system recovery for a Lync Server 2013 pool server to test your documented disaster recovery process.</span></span> <span data-ttu-id="35ebb-105">Bei diesem Test wird ein vollständiger Hardwarefehler für einen Server simuliert, und es wird sichergestellt, dass die Ressourcen, Pläne und Daten für die Wiederherstellung zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="35ebb-105">This test will simulate a complete hardware failure for one server, and will help guarantee that the resources, plans, and data is available for recovery.</span></span> <span data-ttu-id="35ebb-106">Versuchen Sie, den Fokus des Tests jeden Monat zu drehen, damit Ihre Organisation jedes Mal den Fehler eines anderen Servers oder eines anderen Geräts testet.</span><span class="sxs-lookup"><span data-stu-id="35ebb-106">Try to rotate the focus of the test each month so that your organization tests the failure of a different server or other piece of equipment every time.</span></span>

<span data-ttu-id="35ebb-107">Beachten Sie, dass der Zeitplan, nach dem Organisationen Notfall Wiederherstellungstests durchführen, unterschiedlich ist.</span><span class="sxs-lookup"><span data-stu-id="35ebb-107">Note that the schedule by which organizations perform Disaster Recovery testing will vary.</span></span> <span data-ttu-id="35ebb-108">Es ist sehr wichtig, dass Tests zur Notfallwiederherstellung nicht ignoriert oder vernachlässigt werden.</span><span class="sxs-lookup"><span data-stu-id="35ebb-108">It is very important that disaster recovery testing is not ignored or neglected.</span></span>

<div>


<span data-ttu-id="35ebb-109">Exportieren Sie die lync Server 2013 Topologie, Richtlinien und Konfigurationseinstellungen in eine Datei.</span><span class="sxs-lookup"><span data-stu-id="35ebb-109">Export your Lync Server 2013 topology, policies, and configuration settings to a file.</span></span> <span data-ttu-id="35ebb-110">Diese Datei kann unter anderem dann verwendet werden, um diese Informationen im zentralen Verwaltungsspeicher wiederherzustellen, nachdem ein Upgrade, ein Hardwarefehler oder ein anderes Problem zu Datenverlust geführt hat.</span><span class="sxs-lookup"><span data-stu-id="35ebb-110">Among other things, this file can then be used to restore this information to the Central Management store after an upgrade, a hardware failure, or some other issue has resulted in data loss.</span></span>

<span data-ttu-id="35ebb-111">Importieren Sie die lync Server 2013 Topologie, Richtlinien und Konfigurationseinstellungen in den zentralen Verwaltungsspeicher oder auf den lokalen Computer, wie in den folgenden Befehlen dargestellt:</span><span class="sxs-lookup"><span data-stu-id="35ebb-111">Import your Lync Server 2013 topology, policies, and configuration settings to either the Central Management store or to the local computer as shown in the following commands:</span></span>

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

<span data-ttu-id="35ebb-112">So sichern Sie Produktions lync Server 2013 Daten:</span><span class="sxs-lookup"><span data-stu-id="35ebb-112">To back up production Lync Server 2013 data:</span></span>

  - <span data-ttu-id="35ebb-113">Sichern Sie die RTC-und LCSLog-Datenbanken, indem Sie den Standard SQL Server Sicherungsvorgang verwenden, um die Datenbank auf ein Datei-oder Bandsicherungsgerät zu kippen.</span><span class="sxs-lookup"><span data-stu-id="35ebb-113">Back up the RTC and LCSLog databases by using the standard SQL Server backup process to dump the database to a file or tape dump device.</span></span>

  - <span data-ttu-id="35ebb-114">Verwenden Sie die Sicherungsanwendung eines Drittanbieters, um die Daten in Datei oder auf Band zu sichern.</span><span class="sxs-lookup"><span data-stu-id="35ebb-114">Use third-party backup application to back up the data to file or to tape.</span></span>

  - <span data-ttu-id="35ebb-115">Verwenden Sie das Cmdlet Export-csuserdata ", um einen XML-Export der gesamten RTC-Datenbank zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="35ebb-115">Use the Export-CsUserData cmdlet to create an XML export of the whole RTC database.</span></span>

  - <span data-ttu-id="35ebb-116">Verwenden Sie die Dateisystemsicherung oder Drittanbieter, um Besprechungsinhalte und Kompatibilitäts Protokolle zu sichern.</span><span class="sxs-lookup"><span data-stu-id="35ebb-116">Use the file system backup or third-party to back up meeting content and compliance logs.</span></span>

  - <span data-ttu-id="35ebb-117">Verwenden Sie das Befehlszeilentool Export-CsConfiguration, um lync Server 2013 Einstellungen zu sichern.</span><span class="sxs-lookup"><span data-stu-id="35ebb-117">Use the Export-CsConfiguration command-line tool to back up Lync Server 2013 settings.</span></span>

<span data-ttu-id="35ebb-118">Der erste Schritt beim Failover-Verfahren umfasst die erzwungene Verlagerung von Benutzern aus dem Produktionspool in den Notfall Wiederherstellungs Pool.</span><span class="sxs-lookup"><span data-stu-id="35ebb-118">The first step in the failover procedure includes a forced move of users from the production pool to the Disaster Recovery pool.</span></span>

<span data-ttu-id="35ebb-119">Dies ist eine erzwungene Verschiebung, da der Produktionspool nicht verfügbar ist, um die Benutzer Verlagerung zu akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="35ebb-119">This will be a forced move because the production pool won't be available to accept the user relocation.</span></span>

<span data-ttu-id="35ebb-120">Der lync Server 2013 Prozess "Benutzer verlegen" ist eine Änderung an einem Attribut für das Benutzerkontoobjekt zusätzlich zu einer Datensatzaktualisierung in der RTC SQL-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="35ebb-120">The Lync Server 2013 move user process is effectively a change to an attribute on the user account object in addition to a record update on the RTC SQL database.</span></span>

<span data-ttu-id="35ebb-121">Diese Daten können über die folgenden beiden Prozesse wiederhergestellt werden:</span><span class="sxs-lookup"><span data-stu-id="35ebb-121">This data can be restored through the following two processes:</span></span>

  - <span data-ttu-id="35ebb-122">Die RTC-Datenbank kann vom ursprünglichen Sicherungsspeicher Gerät aus dem Produktions SQL Server mithilfe des standardmäßigen SQL Server Wiederherstellungsprozesses oder mithilfe eines Sicherungs-/Wiederherstellungstools eines Drittanbieters wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="35ebb-122">RTC database can be restored from the original backup dump device from the production SQL Server using the standard SQL Server restore process, or using a third-party backup/restore utility.</span></span>

  - <span data-ttu-id="35ebb-123">Benutzer Kontaktdaten können mit dem Dienstprogramm DBIMPEXP. exe mithilfe der XML-Datei, die aus dem Export der Produktions SQL Server erstellt wurde, wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="35ebb-123">User contact data can be restored with the DBIMPEXP.exe utility using the XML file that was created from the production SQL Server export.</span></span>

<span data-ttu-id="35ebb-124">Nachdem diese Daten wiederhergestellt wurden, können Benutzer effektiv eine Verbindung mit dem Notfall Wiederherstellungs lync Server 2013-Pool herstellen und wie gewohnt arbeiten.</span><span class="sxs-lookup"><span data-stu-id="35ebb-124">After this data is restored, users can effectively connect to the Disaster Recovery Lync Server 2013 pool, and operate as usual.</span></span>

<span data-ttu-id="35ebb-125">Damit Benutzer eine Verbindung mit dem Notfall Wiederherstellungs lync Server 2013-Pool herstellen können, ist eine Änderung des DNS-Eintrags erforderlich.</span><span class="sxs-lookup"><span data-stu-id="35ebb-125">To enable users to connect to the Disaster Recovery Lync Server 2013 pool, a DNS record change will be required.</span></span>

<span data-ttu-id="35ebb-126">Auf den Produktions lync Server 2013 Pool wird von Clients verwiesen, die die Auto-Konfiguration und DNS-SRV-Einträge von verwenden:</span><span class="sxs-lookup"><span data-stu-id="35ebb-126">The production Lync Server 2013 pool will be referenced by clients using the auto-configuration and DNS SRV records of:</span></span>

  - <span data-ttu-id="35ebb-127">SRV: \_SIP. \_TLS. \<Domäne\> /CNAME: SIP. \<Domäne\></span><span class="sxs-lookup"><span data-stu-id="35ebb-127">SRV: \_sip.\_tls.\<domain\> /CNAME: SIP.\<domain\></span></span>

  - <span data-ttu-id="35ebb-128">CNAME: SIP. \<Domänen\> /CVC-Pool-1. \<Domäne\></span><span class="sxs-lookup"><span data-stu-id="35ebb-128">CNAME: SIP.\<domain\> /cvc-pool-1.\<domain\></span></span>

<span data-ttu-id="35ebb-129">Zur Vereinfachung des Failovers muss dieser CNAME-Eintrag so aktualisiert werden, dass er auf den FQDN des DROCSPool verweist:</span><span class="sxs-lookup"><span data-stu-id="35ebb-129">To facilitate the failover, this CNAME record must be updated to reference the DROCSPool FQDN:</span></span>

  - <span data-ttu-id="35ebb-130">CNAME: SIP. \<Domänen\> /DROCSPool. \<Domäne\></span><span class="sxs-lookup"><span data-stu-id="35ebb-130">CNAME: SIP.\<domain\> /DROCSPool.\<domain\></span></span>

  - <span data-ttu-id="35ebb-131">SIP. \<Domäne\></span><span class="sxs-lookup"><span data-stu-id="35ebb-131">Sip.\<domain\></span></span>

  - <span data-ttu-id="35ebb-132">AV.\<Domäne\></span><span class="sxs-lookup"><span data-stu-id="35ebb-132">AV.\<domain\></span></span>

  - <span data-ttu-id="35ebb-133">webconf. \<Domäne\></span><span class="sxs-lookup"><span data-stu-id="35ebb-133">webconf.\<domain\></span></span>

  - <span data-ttu-id="35ebb-134">OCSServices. \<Domäne\></span><span class="sxs-lookup"><span data-stu-id="35ebb-134">OCSServices.\<domain\></span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="35ebb-135">Ausführliche Verwaltungs-und Verwaltungsverfahren finden Sie unter <A href="lync-server-2013-backing-up-and-restoring-lync-server.md">Sichern und Wiederherstellen von lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="35ebb-135">For detailed administration and management procedures, see <A href="lync-server-2013-backing-up-and-restoring-lync-server.md">Backing up and restoring Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="35ebb-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="35ebb-136">See Also</span></span>


[<span data-ttu-id="35ebb-137">Planen der hohen Verfügbarkeit und der Notfallwiederherstellung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35ebb-137">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
[<span data-ttu-id="35ebb-138">Cmdlets für Sicherung und hohe Verfügbarkeit in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35ebb-138">Backup and high availability cmdlets in Lync Server 2013</span></span>](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)  


[<span data-ttu-id="35ebb-139">Import-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="35ebb-139">Import-CsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[<span data-ttu-id="35ebb-140">Sichern und Wiederherstellen lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35ebb-140">Backing up and restoring Lync Server 2013</span></span>](lync-server-2013-backing-up-and-restoring-lync-server.md)  
[<span data-ttu-id="35ebb-141">Verwalten von lync Server 2013 Notfallwiederherstellung, hoher Verfügbarkeit und Sicherungsdienst</span><span class="sxs-lookup"><span data-stu-id="35ebb-141">Managing Lync Server 2013 disaster recovery, high availability, and Backup Service</span></span>](lync-server-2013-managing-lync-server-disaster-recovery-high-availability-and-backup-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

