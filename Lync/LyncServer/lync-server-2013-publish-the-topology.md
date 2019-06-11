---
title: 'Lync Server 2013: Veröffentlichen der Topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Publish the topology
ms:assetid: 3b5a744b-b3a8-4538-a55e-e2e4f72dff47
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425880(v=OCS.15)
ms:contentKeyID: 48183866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fee3b14776c6cdf6ddd52ada724d3d4a6d6a245a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823966"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-topology-in-lync-server-2013"></a><span data-ttu-id="4b243-102">Veröffentlichen der Topologie in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b243-102">Publish the topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b243-103">_**Letztes Änderungsdatum des Themas:** 2013-10-01_</span><span class="sxs-lookup"><span data-stu-id="4b243-103">_**Topic Last Modified:** 2013-10-01_</span></span>

<span data-ttu-id="4b243-104">Um eine Topologie beim Hinzufügen oder Entfernen einer Serverrolle erfolgreich zu veröffentlichen, zu aktivieren oder zu deaktivieren, sollten Sie als Benutzer angemeldet sein, der Mitglied der Gruppen RTCUniversalServerAdmins und Domänenadministratoren ist.</span><span class="sxs-lookup"><span data-stu-id="4b243-104">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="4b243-105">Es ist auch möglich, die richtigen Administratorrechte und-Berechtigungen zu delegieren.</span><span class="sxs-lookup"><span data-stu-id="4b243-105">It is also possible to delegate the proper administrator rights and permissions.</span></span> <span data-ttu-id="4b243-106">Ausführliche Informationen finden Sie unter Delegieren von [Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="4b243-106">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span> <span data-ttu-id="4b243-107">Bei anderen Konfigurationsänderungen ist nur die Mitgliedschaft in der RTCUniversalServerAdmins-Gruppe erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4b243-107">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<span data-ttu-id="4b243-108">Nachdem Sie Ihre Topologie im Topologie-Generator definiert haben, müssen Sie die Topologie im zentralen Verwaltungsspeicher veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="4b243-108">After you define your topology in Topology Builder, you must publish the topology to the Central Management store.</span></span> <span data-ttu-id="4b243-109">Der zentrale Verwaltungsspeicher bietet eine robuste, schematisierten Speicherung der Daten, die zum definieren, einrichten, verwalten, verwalten, beschreiben und betreiben einer lync Server 2013-Bereitstellung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="4b243-109">The Central Management store provides a robust, schematized storage of the data needed to define, set up, maintain, administer, describe, and operate a Lync Server 2013 deployment.</span></span> <span data-ttu-id="4b243-110">Außerdem werden die Daten überprüft, um die Konsistenz der Konfiguration zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="4b243-110">It also validates the data to help ensure configuration consistency.</span></span> <span data-ttu-id="4b243-111">Alle Änderungen an diesen Konfigurationsdaten erfolgen im zentralen Verwaltungsspeicher, wodurch Synchronisierungsprobleme beseitigt werden.</span><span class="sxs-lookup"><span data-stu-id="4b243-111">All changes to this configuration data happen at the Central Management store, eliminating “out-of-sync” issues.</span></span> <span data-ttu-id="4b243-112">Schreibgeschützte Kopien der Daten werden auf alle Server in der Topologie repliziert, einschließlich Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="4b243-112">Read-only copies of the data are replicated to all servers in the topology, including Edge Servers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4b243-113">SQL Server benötigt eine Mindestmenge von 20 GB freien Speicherplatz, um die ursprüngliche Topologie erfolgreich zu veröffentlichen und den zentralen Verwaltungs Server zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4b243-113">SQL Server needs a minimum of 20 GB of free disk space to successfully publish the initial topology and create the Central Management Server.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="4b243-114">Nur für Enterprise Edition: um die Topologie zu veröffentlichen, muss der auf SQL Server basierende Back-End-Server online sein und über Firewall-Ausnahmen zugänglich sein.</span><span class="sxs-lookup"><span data-stu-id="4b243-114">For Enterprise Edition only: In order to publish the topology, the SQL Server-based Back End Server must be online and accessible with firewall exceptions in place.</span></span> <span data-ttu-id="4b243-115">Details zum Angeben von Firewall-Ausnahmen finden Sie unter <A href="lync-server-2013-understanding-firewall-requirements-for-sql-server.md">Grundlegendes zu Firewall-Anforderungen für SQL Server mit lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="4b243-115">For details about specifying firewall exceptions, see <A href="lync-server-2013-understanding-firewall-requirements-for-sql-server.md">Understanding firewall requirements for SQL Server with Lync Server 2013</A>.</span></span> <span data-ttu-id="4b243-116">Details zum Konfigurieren von SQL Server finden Sie unter <A href="lync-server-2013-configure-sql-server-for-lync-server.md">Konfigurieren von SQL Server für lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="4b243-116">For details about configuring SQL Server, see <A href="lync-server-2013-configure-sql-server-for-lync-server.md">Configure SQL Server for Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-publish-a-topology"></a><span data-ttu-id="4b243-117">So veröffentlichen Sie eine Topologie</span><span class="sxs-lookup"><span data-stu-id="4b243-117">To publish a topology</span></span>

1.  <span data-ttu-id="4b243-118">Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="4b243-118">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="4b243-119">Wählen Sie aus, um die Topologie aus einer lokalen Datei zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="4b243-119">Select to open the topology from a local file.</span></span> <span data-ttu-id="4b243-120">Wenn Sie sich auf dem Computer befinden, auf dem Sie die Topologie definiert haben, befindet sich diese an dem Speicherort, an dem Sie Sie in früheren Schritten gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="4b243-120">If you are on the computer where you defined the topology, this will be in the location where you saved it in earlier steps.</span></span> <span data-ttu-id="4b243-121">In der Regel handelt es sich hierbei um den Ordner "Dokumente" des Benutzers, der die Topologie konfiguriert hat.</span><span class="sxs-lookup"><span data-stu-id="4b243-121">Typically, this will be the Documents folder of the user who configured the topology.</span></span>

3.  <span data-ttu-id="4b243-122">Klicken Sie mit der rechten Maustaste auf den **lync Server 2013** -Knoten, und klicken Sie dann auf **Topologie veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="4b243-122">Right-click the **Lync Server 2013** node, and then click **Publish Topology**.</span></span>

4.  <span data-ttu-id="4b243-123">Klicken Sie auf der Seite **Topologie veröffentlichen** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4b243-123">On the **Publish the topology** page, click **Next**.</span></span>

5.  <span data-ttu-id="4b243-124">Wählen Sie auf der Seite **Create** Databases die Datenbanken aus, die Sie veröffentlichen möchten.</span><span class="sxs-lookup"><span data-stu-id="4b243-124">On the **Create databases** page, select the databases you want to publish.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4b243-125">Wenn Sie nicht über die erforderlichen Rechte zum Erstellen der Datenbanken verfügen, können Sie die Kontrollkästchen neben diesen Datenbanken deaktivieren, und ein Benutzer mit den entsprechenden Rechten kann später die Datenbankenerstellen.</span><span class="sxs-lookup"><span data-stu-id="4b243-125">If you don’t have the appropriate rights to create the databases, you can clear the check boxes next to those databases, and someone with appropriate rights can later create the databases.</span></span> <span data-ttu-id="4b243-126">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Bereitstellungsberechtigungen für SQL Server in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="4b243-126">For details, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A>.</span></span>

    
    </div>

6.  <span data-ttu-id="4b243-127">Klicken Sie optional auf **Erweitert**.</span><span class="sxs-lookup"><span data-stu-id="4b243-127">Optionally click **Advanced**.</span></span> <span data-ttu-id="4b243-128">Mit den erweiterten Optionen für SQL Server-Datendatei Platzierungen können Sie zwischen den folgenden Optionen auswählen:</span><span class="sxs-lookup"><span data-stu-id="4b243-128">The Advanced SQL Server data file placement options let you select between the following options:</span></span>
    
      - <span data-ttu-id="4b243-129">**Speicherort für Datenbankdateien automatisch ermitteln** – mit dieser Option wird die optimale Betriebsleistung basierend auf der Datenträgerkonfiguration auf dem SQL Server-basierten Server ermittelt, indem die Protokoll-und Datendateien an den besten Speicherort verteilt werden.</span><span class="sxs-lookup"><span data-stu-id="4b243-129">**Automatically determine database file location** – This option will determine the best operational performance based on the disk configuration on your SQL Server-based server by distributing the log and data files to the best location.</span></span>
    
      - <span data-ttu-id="4b243-p107">**Standardpfade der SQL Server-Instanz verwenden**: Bei Auswahl dieser Option werden die Protokoll- und Datendateien gemäß den Instanzeneinstellungen auf dem SQL Server-basierten Server platziert. Diese Option macht keinen Gebrauch von der Funktion des SQL Server-basierten Servers zum Ermitteln der optimalen Speicherorte für Protokolle und Daten. Der SQL Server-Administrator verschiebt die Protokoll- und Datendateien in der Regel an Speicherorte, die für den SQL Server-basierten Server geeignet sind und den Verwaltungsverfahren für die Organisation entsprechen.</span><span class="sxs-lookup"><span data-stu-id="4b243-p107">**Use SQL Server instance defaults** – This option puts log and data files onto the SQL Server-based server by using the instance settings. This option does not use the operational functionality of the SQL Server-based server to determine optimal locations for logs and data. The SQL Server administrator would typically move the log and data files to locations that are appropriate for the SQL Server-based server and organization management procedures.</span></span>
    
    <span data-ttu-id="4b243-133">Klicken Sie auf **OK** und dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4b243-133">Click **OK**, and then click **Next**.</span></span>

7.  <span data-ttu-id="4b243-134">Wählen Sie auf der Seite **Central Management Server auswählen** einen Front-End-Pool aus.</span><span class="sxs-lookup"><span data-stu-id="4b243-134">On the **Select Central Management Server** page, select a Front End pool.</span></span>

8.  <span data-ttu-id="4b243-135">Klicken Sie optional auf **Erweitert**.</span><span class="sxs-lookup"><span data-stu-id="4b243-135">Optionally click **Advanced**.</span></span> <span data-ttu-id="4b243-136">Mit den erweiterten Optionen für die SQL Server-Datendatei Platzierung können Sie zwischen den folgenden Optionen auswählen:</span><span class="sxs-lookup"><span data-stu-id="4b243-136">The Advanced SQL Server data file placement options enables you to select between the following options:</span></span>
    
      - <span data-ttu-id="4b243-137">**Speicherort für Datenbankdateien automatisch ermitteln** – mit dieser Option wird die optimale Betriebsleistung basierend auf der Datenträgerkonfiguration auf dem SQL Server-basierten Server ermittelt, indem die Protokoll-und Datendateien an den besten Speicherort verteilt werden.</span><span class="sxs-lookup"><span data-stu-id="4b243-137">**Automatically determine database file location** – This option will determine the best operational performance based on the disk configuration on your SQL Server-based server by distributing the log and data files to the best location.</span></span>
    
      - <span data-ttu-id="4b243-p109">**Standardpfade der SQL Server-Instanz verwenden**: Bei Auswahl dieser Option werden die Protokoll- und Datendateien gemäß den Instanzeneinstellungen auf dem SQL Server-basierten Server platziert. Diese Option macht keinen Gebrauch von der Funktion des SQL Server-basierten Servers zum Ermitteln der optimalen Speicherorte für Protokolle und Daten. Der SQL Server-Administrator verschiebt die Protokoll- und Datendateien in der Regel an Speicherorte, die für den SQL Server-basierten Server geeignet sind und den Verwaltungsverfahren für die Organisation entsprechen.</span><span class="sxs-lookup"><span data-stu-id="4b243-p109">**Use SQL Server instance defaults** – This option puts log and data files onto the SQL Server-based server by using the instance settings. This option does not use the operational functionality of the SQL Server-based server to determine optimal locations for logs and data. The SQL Server administrator would typically move the log and data files to locations that are appropriate for the SQL Server-based server and organization management procedures.</span></span>
    
    <span data-ttu-id="4b243-141">Klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="4b243-141">Click **OK**.</span></span>

9.  <span data-ttu-id="4b243-142">Klicken Sie auf **Weiter**, um die Veröffentlichung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="4b243-142">Click **Next** to complete the publishing process.</span></span>

10. <span data-ttu-id="4b243-143">Wenn der Veröffentlichungsprozess abgeschlossen ist, klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="4b243-143">When the publish process has completed, click **Finish**.</span></span>
    
    <span data-ttu-id="4b243-144">Wenn die Topologie erfolgreich veröffentlicht wurde, können Sie mit der Installation eines lokalen Replikats des zentralen Verwaltungsspeichers auf jedem Server mit lync Server 2013 in Ihrer Topologie beginnen.</span><span class="sxs-lookup"><span data-stu-id="4b243-144">When the topology has been published successfully, you can begin installing a local replica of the Central Management store on each server running Lync Server 2013 in your topology.</span></span> <span data-ttu-id="4b243-145">Es wird empfohlen, mit dem ersten Front-End-Pool zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="4b243-145">We recommend that you begin with the first Front End pool.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4b243-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4b243-146">See Also</span></span>


[<span data-ttu-id="4b243-147">Einrichten von Front-End-Servern und Front-End-Pools für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b243-147">Setting up Front End Servers and Front End pools for Lync Server 2013</span></span>](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

