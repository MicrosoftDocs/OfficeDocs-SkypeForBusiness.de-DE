---
title: 'Lync Server 2013: Veröffentlichen der Topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish the topology
ms:assetid: 3b5a744b-b3a8-4538-a55e-e2e4f72dff47
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425880(v=OCS.15)
ms:contentKeyID: 48183866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1aa216ba3db48f03dbcdd69f4deea029e7a366df
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042402"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-topology-in-lync-server-2013"></a><span data-ttu-id="73644-102">Veröffentlichen der Topologie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73644-102">Publish the topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73644-103">_**Letztes Änderungsstand des Themas:** 2013-10-01_</span><span class="sxs-lookup"><span data-stu-id="73644-103">_**Topic Last Modified:** 2013-10-01_</span></span>

<span data-ttu-id="73644-104">Für eine erfolgreiche Veröffentlichung, Aktivierung oder Deaktivierung einer Topologie beim Hinzufügen oder Entfernen einer Serverrolle müssen Sie als Mitglied der Gruppen "RTCUniversalServerAdmins" und "Domänen-Admins" angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="73644-104">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="73644-105">Es ist auch möglich, die geeigneten Administratorrechte und -berechtigungen zu delegieren.</span><span class="sxs-lookup"><span data-stu-id="73644-105">It is also possible to delegate the proper administrator rights and permissions.</span></span> <span data-ttu-id="73644-106">Ausführliche Informationen finden Sie unter [Delegate Setup Permissions in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="73644-106">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span> <span data-ttu-id="73644-107">Für andere Konfigurationsänderungen müssen Sie lediglich Mitglied der Gruppe "RTCUniversalServerAdmins" sein.</span><span class="sxs-lookup"><span data-stu-id="73644-107">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<span data-ttu-id="73644-108">Nachdem Sie Ihre Topologie im Topologie-Generator definiert haben, müssen Sie die Topologie im zentralen Verwaltungsspeicher veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="73644-108">After you define your topology in Topology Builder, you must publish the topology to the Central Management store.</span></span> <span data-ttu-id="73644-109">Der zentrale Verwaltungsspeicher bietet eine robuste, schematisierten Speicherung der Daten, die für die Definition, Einrichtung, Verwaltung, Verwaltung, Beschreibung und den Betrieb einer lync Server 2013-Bereitstellung benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="73644-109">The Central Management store provides a robust, schematized storage of the data needed to define, set up, maintain, administer, describe, and operate a Lync Server 2013 deployment.</span></span> <span data-ttu-id="73644-110">Außerdem werden die Daten überprüft, um die Konsistenz der Konfiguration zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="73644-110">It also validates the data to help ensure configuration consistency.</span></span> <span data-ttu-id="73644-111">Alle Änderungen an diesen Konfigurationsdaten erfolgen im zentralen Verwaltungsspeicher, wodurch nicht mehr synchrone Probleme auftreten.</span><span class="sxs-lookup"><span data-stu-id="73644-111">All changes to this configuration data happen at the Central Management store, eliminating “out-of-sync” issues.</span></span> <span data-ttu-id="73644-112">Schreibgeschützte Kopien der Daten werden auf alle Server in der Topologie repliziert, Edgeserver eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="73644-112">Read-only copies of the data are replicated to all servers in the topology, including Edge Servers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="73644-113">SQL Server benötigt mindestens 20 GB freien Speicherplatz, um die anfängliche Topologie erfolgreich zu veröffentlichen und den zentralen Verwaltungs Server zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="73644-113">SQL Server needs a minimum of 20 GB of free disk space to successfully publish the initial topology and create the Central Management Server.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="73644-114">Nur Enterprise Edition: Zum Veröffentlichen der Topologie muss der SQL Server-basierte Back-End-Server online und über die eingerichteten Firewallausnahmen erreichbar sein.</span><span class="sxs-lookup"><span data-stu-id="73644-114">For Enterprise Edition only: In order to publish the topology, the SQL Server-based Back End Server must be online and accessible with firewall exceptions in place.</span></span> <span data-ttu-id="73644-115">Ausführliche Informationen zum Angeben von Firewall-Ausnahmen finden Sie unter <A href="lync-server-2013-understanding-firewall-requirements-for-sql-server.md">Understanding Firewall Requirements for SQL Server with lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="73644-115">For details about specifying firewall exceptions, see <A href="lync-server-2013-understanding-firewall-requirements-for-sql-server.md">Understanding firewall requirements for SQL Server with Lync Server 2013</A>.</span></span> <span data-ttu-id="73644-116">Ausführliche Informationen zum Konfigurieren von SQL Server finden Sie unter <A href="lync-server-2013-configure-sql-server-for-lync-server.md">configure SQL Server for lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="73644-116">For details about configuring SQL Server, see <A href="lync-server-2013-configure-sql-server-for-lync-server.md">Configure SQL Server for Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-publish-a-topology"></a><span data-ttu-id="73644-117">So veröffentlichen Sie eine Topologie</span><span class="sxs-lookup"><span data-stu-id="73644-117">To publish a topology</span></span>

1.  <span data-ttu-id="73644-118">Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.</span><span class="sxs-lookup"><span data-stu-id="73644-118">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="73644-p104">Öffnen Sie die Topologie aus einer lokalen Datei. Wenn Sie an dem Computer arbeiten, an dem Sie die Topologie definiert haben, ist dies der Speicherort, an dem Sie die Datei zuvor gespeichert haben. In der Regel ist dies der Ordner "Dokumente" des Benutzers, der die Topologie konfiguriert hat.</span><span class="sxs-lookup"><span data-stu-id="73644-p104">Select to open the topology from a local file. If you are on the computer where you defined the topology, this will be in the location where you saved it in earlier steps. Typically, this will be the Documents folder of the user who configured the topology.</span></span>

3.  <span data-ttu-id="73644-122">Klicken Sie mit der rechten Maustaste auf den Knoten **lync Server 2013** , und klicken Sie dann auf **Topologie veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="73644-122">Right-click the **Lync Server 2013** node, and then click **Publish Topology**.</span></span>

4.  <span data-ttu-id="73644-123">Klicken Sie auf der Seite **Topologie veröffentlichen** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="73644-123">On the **Publish the topology** page, click **Next**.</span></span>

5.  <span data-ttu-id="73644-124">Wählen Sie auf der Seite **Datenbanken erstellen** die Datenbanken, die Sie veröffentlichen möchten.</span><span class="sxs-lookup"><span data-stu-id="73644-124">On the **Create databases** page, select the databases you want to publish.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="73644-125">Wenn Sie nicht über die erforderlichen Rechte zum Erstellen der Datenbanken verfügen, können Sie die Kontrollkästchen neben diesen Datenbanken deaktivieren, und ein Benutzer mit den entsprechenden Berechtigungen kann später die Datenbankenerstellen.</span><span class="sxs-lookup"><span data-stu-id="73644-125">If you don’t have the appropriate rights to create the databases, you can clear the check boxes next to those databases, and someone with appropriate rights can later create the databases.</span></span> <span data-ttu-id="73644-126">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment Permissions for SQL Server in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="73644-126">For details, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A>.</span></span>

    
    </div>

6.  <span data-ttu-id="73644-127">Klicken Sie optional auf **Erweitert**.</span><span class="sxs-lookup"><span data-stu-id="73644-127">Optionally click **Advanced**.</span></span> <span data-ttu-id="73644-128">Mit den Optionen für erweiterte SQL Server-Platzierung von Datendateien können Sie zwischen den folgenden Optionen auswählen:</span><span class="sxs-lookup"><span data-stu-id="73644-128">The Advanced SQL Server data file placement options let you select between the following options:</span></span>
    
      - <span data-ttu-id="73644-129">**Speicherort für Datenbankdateien automatisch bestimmen** – Bei Auswahl dieser Option wird optimale Leistung basierend auf der Festplattenkonfiguration für Ihren SQL Server-basierten Server gewährleistet, indem die Protokoll- und Datendateien verteilt platziert werden.</span><span class="sxs-lookup"><span data-stu-id="73644-129">**Automatically determine database file location** – This option will determine the best operational performance based on the disk configuration on your SQL Server-based server by distributing the log and data files to the best location.</span></span>
    
      - <span data-ttu-id="73644-p107">**Standardpfade der SQL Server-Instanz verwenden** – Bei Auswahl dieser Option werden die Protokoll- und Datendateien gemäß den Instanzeneinstellungen auf dem SQL Server-basierten Server platziert. Diese Option macht keinen Gebrauch von der Funktion des SQL Server-basierten Servers zum Ermitteln der optimalen Speicherorte für Protokolle und Daten. Der SQL Server-Administrator verschiebt die Protokoll- und Datendateien in der Regel an Speicherorte, die für den SQL Server-basierten Server geeignet sind und den Verwaltungsverfahren für die Organisation entsprechen.</span><span class="sxs-lookup"><span data-stu-id="73644-p107">**Use SQL Server instance defaults** – This option puts log and data files onto the SQL Server-based server by using the instance settings. This option does not use the operational functionality of the SQL Server-based server to determine optimal locations for logs and data. The SQL Server administrator would typically move the log and data files to locations that are appropriate for the SQL Server-based server and organization management procedures.</span></span>
    
    <span data-ttu-id="73644-133">Klicken Sie auf **OK** und dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="73644-133">Click **OK**, and then click **Next**.</span></span>

7.  <span data-ttu-id="73644-134">Wählen Sie auf der Seite **zentralen Verwaltungs Server auswählen** eine Front-End-Pool aus.</span><span class="sxs-lookup"><span data-stu-id="73644-134">On the **Select Central Management Server** page, select a Front End pool.</span></span>

8.  <span data-ttu-id="73644-135">Klicken Sie optional auf **Erweitert**.</span><span class="sxs-lookup"><span data-stu-id="73644-135">Optionally click **Advanced**.</span></span> <span data-ttu-id="73644-136">Mit den Optionen für erweiterte SQL Server-Platzierung von Datendateien können Sie zwischen den folgenden Optionen auswählen:</span><span class="sxs-lookup"><span data-stu-id="73644-136">The Advanced SQL Server data file placement options enables you to select between the following options:</span></span>
    
      - <span data-ttu-id="73644-137">**Speicherort für Datenbankdateien automatisch bestimmen** – Bei Auswahl dieser Option wird optimale Leistung basierend auf der Festplattenkonfiguration für Ihren SQL Server-basierten Server gewährleistet, indem die Protokoll- und Datendateien verteilt platziert werden.</span><span class="sxs-lookup"><span data-stu-id="73644-137">**Automatically determine database file location** – This option will determine the best operational performance based on the disk configuration on your SQL Server-based server by distributing the log and data files to the best location.</span></span>
    
      - <span data-ttu-id="73644-p109">**Standardpfade der SQL Server-Instanz verwenden** – Bei Auswahl dieser Option werden die Protokoll- und Datendateien gemäß den Instanzeneinstellungen auf dem SQL Server-basierten Server platziert. Diese Option macht keinen Gebrauch von der Funktion des SQL Server-basierten Servers zum Ermitteln der optimalen Speicherorte für Protokolle und Daten. Der SQL Server-Administrator verschiebt die Protokoll- und Datendateien in der Regel an Speicherorte, die für den SQL Server-basierten Server geeignet sind und den Verwaltungsverfahren für die Organisation entsprechen.</span><span class="sxs-lookup"><span data-stu-id="73644-p109">**Use SQL Server instance defaults** – This option puts log and data files onto the SQL Server-based server by using the instance settings. This option does not use the operational functionality of the SQL Server-based server to determine optimal locations for logs and data. The SQL Server administrator would typically move the log and data files to locations that are appropriate for the SQL Server-based server and organization management procedures.</span></span>
    
    <span data-ttu-id="73644-141">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="73644-141">Click **OK**.</span></span>

9.  <span data-ttu-id="73644-142">Klicken Sie auf **Weiter**, um die Veröffentlichung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="73644-142">Click **Next** to complete the publishing process.</span></span>

10. <span data-ttu-id="73644-143">Klicken Sie nach Abschluss der Veröffentlichung auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="73644-143">When the publish process has completed, click **Finish**.</span></span>
    
    <span data-ttu-id="73644-144">Wenn die Topologie erfolgreich veröffentlicht wurde, können Sie mit der Installation eines lokalen Replikats des zentralen Verwaltungsspeichers auf jedem Server beginnen, auf dem lync Server 2013 in Ihrer Topologie ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="73644-144">When the topology has been published successfully, you can begin installing a local replica of the Central Management store on each server running Lync Server 2013 in your topology.</span></span> <span data-ttu-id="73644-145">Es wird empfohlen, mit dem ersten Front-End-Pool zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="73644-145">We recommend that you begin with the first Front End pool.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="73644-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="73644-146">See Also</span></span>


[<span data-ttu-id="73644-147">Einrichten von Front-End-Servern und Front-End-Pools für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73644-147">Setting up Front End Servers and Front End pools for Lync Server 2013</span></span>](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

