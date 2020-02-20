---
title: Anmerkungen zur lync Server 2013-Version
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Release notes
ms:assetid: 9f9e864c-3365-4800-803c-5289bd8fd363
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205120(v=OCS.15)
ms:contentKeyID: 48184930
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8cf95a95c02ad37abdbf88f235cff2f0d5b0459a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152167"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="release-notes-for-lync-server-2013"></a><span data-ttu-id="f20d5-102">Anmerkungen zur Version für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f20d5-102">Release notes for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f20d5-103">_**Letztes Änderungsstand des Themas:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="f20d5-103">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="f20d5-104">Willkommen bei den Anmerkungen zur lync Server 2013-Version.</span><span class="sxs-lookup"><span data-stu-id="f20d5-104">Welcome to the Lync Server 2013 Release Notes.</span></span> <span data-ttu-id="f20d5-105">In dieser Datei erhalten Sie Informationen zu bekannten Problemen mit lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f20d5-105">Refer to this file for information regarding known issues about Lync Server 2013.</span></span>

<div>

## <a name="about-this-document"></a><span data-ttu-id="f20d5-106">Über dieses Dokument</span><span class="sxs-lookup"><span data-stu-id="f20d5-106">About this document</span></span>

<span data-ttu-id="f20d5-107">Dieses Dokument enthält wichtige Informationen, die Sie kennen sollten, bevor Sie lync Server 2013 bereitstellen und verwenden.</span><span class="sxs-lookup"><span data-stu-id="f20d5-107">This document contains important information that you should know before you deploy and use Lync Server 2013.</span></span> <span data-ttu-id="f20d5-108">Ausführliche Informationen zu lync Server 2013 finden Sie in der [Microsoft lync Server 2013](microsoft-lync-server-2013.md) -Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="f20d5-108">For details about Lync Server 2013, refer to the [Microsoft Lync Server 2013](microsoft-lync-server-2013.md) documentation.</span></span>

<span data-ttu-id="f20d5-109">Dieses Dokument enthält die folgenden Abschnitte:</span><span class="sxs-lookup"><span data-stu-id="f20d5-109">This document contains the following sections:</span></span>

  - <span data-ttu-id="f20d5-110">Lync 2013-Client</span><span class="sxs-lookup"><span data-stu-id="f20d5-110">Lync 2013 client</span></span>

  - <span data-ttu-id="f20d5-111">Lync Server</span><span class="sxs-lookup"><span data-stu-id="f20d5-111">Lync Server</span></span>

  - <span data-ttu-id="f20d5-112">Installation</span><span class="sxs-lookup"><span data-stu-id="f20d5-112">Installation</span></span>

  - <span data-ttu-id="f20d5-113">Mobilität</span><span class="sxs-lookup"><span data-stu-id="f20d5-113">Mobility</span></span>

  - <span data-ttu-id="f20d5-114">Konferenzen</span><span class="sxs-lookup"><span data-stu-id="f20d5-114">Conferencing</span></span>

  - <span data-ttu-id="f20d5-115">Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="f20d5-115">Enterprise Voice</span></span>

  - <span data-ttu-id="f20d5-116">Anwesenheit</span><span class="sxs-lookup"><span data-stu-id="f20d5-116">Presence</span></span>

  - <span data-ttu-id="f20d5-117">Reaktionsgruppenanwendung und Anrufparkanwendung</span><span class="sxs-lookup"><span data-stu-id="f20d5-117">Response Group Application and Call Park Application</span></span>

  - <span data-ttu-id="f20d5-118">Systemsteuerung, Topologie-Generator und Planungstool von Lync Server</span><span class="sxs-lookup"><span data-stu-id="f20d5-118">Lync Server Control Panel, Topology Builder, and Planning Tool</span></span>

  - <span data-ttu-id="f20d5-119">Lokalisierung</span><span class="sxs-lookup"><span data-stu-id="f20d5-119">Localization</span></span>

  - <span data-ttu-id="f20d5-120">Copyright</span><span class="sxs-lookup"><span data-stu-id="f20d5-120">Copyright</span></span>

</div>

<span id="LyncClient"></span>

<div>

## <a name="lync-2013-client"></a><span data-ttu-id="f20d5-121">Lync 2013-Client</span><span class="sxs-lookup"><span data-stu-id="f20d5-121">Lync 2013 client</span></span>

<div>

## <a name="transferring-a-file-in-an-instant-message-fails-if-the-file-is-open-in-another-application"></a><span data-ttu-id="f20d5-122">Das übertragen einer Datei in einer Sofortnachricht schlägt fehl, wenn die Datei in einer anderen Anwendung geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="f20d5-122">Transferring a file in an instant message fails if the file is open in another application</span></span>

<span data-ttu-id="f20d5-123">**Problem**</span><span class="sxs-lookup"><span data-stu-id="f20d5-123">**Issue:**</span></span>

<span data-ttu-id="f20d5-124">Wenn Sie versuchen, eine Datei (beispielsweise ein Word-Dokument) zu übertragen, indem Sie Sie in eine Sofortnachricht an einen anderen lync-Benutzer einbinden, wird die Übertragung erfolgreich ausgeführt, die Datei kann jedoch tatsächlich nicht übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="f20d5-124">If you attempt to transfer a file, such as a Word document, by including it in an instant message to another Lync user, the transfer will appear to succeed but may actually fail to transfer the file.</span></span> <span data-ttu-id="f20d5-125">Ein Symbol für den Dateityp wird im lync-Client angezeigt, die Datei kann jedoch nicht vom vorgesehenen Empfänger geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="f20d5-125">An icon for the file type will be displayed in the Lync client, but the file cannot be opened by the intended receiver.</span></span> <span data-ttu-id="f20d5-126">Es wird keine Fehlermeldung angezeigt, die Sie darüber informiert, dass die Übertragung nicht erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="f20d5-126">No error message is displayed to inform you that the transfer was not successfull.</span></span>

<span data-ttu-id="f20d5-127">**Problemumgehung**</span><span class="sxs-lookup"><span data-stu-id="f20d5-127">**Workaround:**</span></span>

<span data-ttu-id="f20d5-128">Um dieses Problem zu umgehen, schließen Sie die geöffnete Datei oder Anwendung, die Sie geöffnet hat, bevor Sie versuchen, die Datei in einer Sofortnachricht zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="f20d5-128">To work around this issue, close the open file or application that has it open before attempting to transfer the file in an instant message.</span></span>

</div>

</div>

<span id="LyncServer"></span>

<div>

## <a name="lync-server"></a><span data-ttu-id="f20d5-129">Lync Server</span><span class="sxs-lookup"><span data-stu-id="f20d5-129">Lync Server</span></span>

<div>

## <a name="if-lync-server-storage-service-data-replication-fails-administrators-will-need-to-check-performance-counters-for-stale-storage-service-queue-items"></a><span data-ttu-id="f20d5-130">Wenn lync Server Datenreplikation für den Speicherdienst fehlschlägt, müssen Administratoren die Leistungsindikatoren für Warteschlangenelemente für veraltete Speicherdienste überprüfen.</span><span class="sxs-lookup"><span data-stu-id="f20d5-130">If Lync Server Storage Service data replication fails, administrators will need to check performance counters for stale Storage Service queue items</span></span>

<span data-ttu-id="f20d5-131">**Problem**</span><span class="sxs-lookup"><span data-stu-id="f20d5-131">**Issue:**</span></span>

<span data-ttu-id="f20d5-132">Der lync Server Speicherdienst verwendet Windows Fabric für die Replikation.</span><span class="sxs-lookup"><span data-stu-id="f20d5-132">The Lync Server Storage Service uses Windows Fabric for replication.</span></span> <span data-ttu-id="f20d5-133">Wenn Daten auf einem primären Front-End-Server gelöscht werden, aber der Löschvorgang für einen sekundären Front-End-Server fehlschlägt (beispielsweise wenn ein unerwartetes Herunterfahren oder ein Fehler auf dem Front-End-Server vorliegt), können Daten zurückgelassen und "verwaiste" werden.</span><span class="sxs-lookup"><span data-stu-id="f20d5-133">If data is deleted on a primary Front End Server, but the deletion on a secondary Front End Server fails—for example, if there is an unexpected shutdown or error on the Front End Server—data can be left behind and "orphaned."</span></span> <span data-ttu-id="f20d5-134">Die verwaisten Daten können zu Leistungsbeeinträchtigungen und Speicherplatzverschwendung führen.</span><span class="sxs-lookup"><span data-stu-id="f20d5-134">The orphaned data can cause performance to degrade and waste drive space.</span></span>

<span data-ttu-id="f20d5-135">**Problemumgehung**</span><span class="sxs-lookup"><span data-stu-id="f20d5-135">**Workaround:**</span></span>

<span data-ttu-id="f20d5-136">Um dieses Problem zu umgehen, sollten Administratoren den Leistungs\_Indikator\_auf\_dem\_Front-End-Server unter **ls: Lyss-Storage Service API** mit\_dem\_Namen **Lyss-Current number of Storage Service veraltete Warteschlangenelemente**überprüfen, wenn die Ereignisse Lyss DB Space used Error (ID = 32058) und Lyss\_DB\_Space Critical (ID = 32059) im Ereignisprotokoll generiert wird.</span><span class="sxs-lookup"><span data-stu-id="f20d5-136">To work around this issue, if the events LYSS\_DB\_SPACE\_USED\_ERROR (Id=32058) and LYSS\_DB\_SPACE\_USED\_CRITICAL (Id=32059) are generated in the event log, administrators should check the performance counter on the Front End Server under **LS:LYSS - Storage Service API** with a name of **LYSS - Current number of Storage Service stale queue items**.</span></span> <span data-ttu-id="f20d5-137">Wenn dieser Leistungsindikator einen hohen Wert aufweist (beispielsweise größer als 50000), sollte der Administrator das Tool CleanuUpStorageServiceData. exe im lync Server 2013 Resource Kit ausführen, mit dem alle verwaisten Daten aus dem Pool gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="f20d5-137">If this performance counter has a high value—for example, greater than 50,000—then the administrator should run the CleanuUpStorageServiceData.exe tool in the Lync Server 2013 Resource Kit, which will delete all orphaned data from the pool.</span></span> <span data-ttu-id="f20d5-138">Ausführliche Informationen zum Tool finden Sie in der Dokumentation zum lync Server 2013 Resource Kit.</span><span class="sxs-lookup"><span data-stu-id="f20d5-138">For details about the tool, see the Lync Server 2013 Resource Kit documentation.</span></span>

</div>

<div>

## <a name="whenever-the-ip-address-configuration-is-changed-for-a-server-or-pool-lync-server-services-need-to-be-restarted"></a><span data-ttu-id="f20d5-139">Wenn die IP-Adresskonfiguration für einen Server oder Pool geändert wird, müssen lync Server Dienste neu gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="f20d5-139">Whenever the IP Address configuration is changed for a server or pool, Lync Server services need to be restarted</span></span>

<span data-ttu-id="f20d5-140">**Problem**</span><span class="sxs-lookup"><span data-stu-id="f20d5-140">**Issue:**</span></span>

<span data-ttu-id="f20d5-141">Wenn die IP-Adresskonfiguration für eine lync Server 2013-Bereitstellung geändert wird, beispielsweise von IPv4 in Dual Stack oder von Dual-Stack zu IPv6, greifen nicht alle Server Komponenten die Konfigurationsänderung an, bis die Dienste neu gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="f20d5-141">When the IP Address configuration is changed for a Lync Server 2013 deployment, such as changing from IPv4 to Dual Stack, or from Dual Stack to Ipv6, not all server components pick up the configuration change until the services are restarted.</span></span>

<span data-ttu-id="f20d5-142">**Problemumgehung**</span><span class="sxs-lookup"><span data-stu-id="f20d5-142">**Workaround:**</span></span>

<span data-ttu-id="f20d5-143">Um dieses Problem zu umgehen, starten Sie lync Server Dienste neu, nachdem Sie die IP-Adresskonfiguration für die Bereitstellung geändert haben.</span><span class="sxs-lookup"><span data-stu-id="f20d5-143">To work around this issue, restart Lync Server services after changing the IP Address configuration for the deployment.</span></span> <span data-ttu-id="f20d5-144">Führen Sie dazu die folgenden Cmdlets im lync Server-Verwaltungsshell aus:</span><span class="sxs-lookup"><span data-stu-id="f20d5-144">To do so, run the following cmdlets in the Lync Server Management Shell:</span></span>

   ```PowerShell
    Stop-CsWindowsService -graceful
   ```

   ```PowerShell
    Start-CsWindowsService
   ```

</div>

<div>

## <a name="the-dial-in-conferencing-synthetic-transaction-cmdlet-is-no-longer-available-in-the-lync-server-2013-management-pack"></a><span data-ttu-id="f20d5-145">Das Cmdlet "synthetische Transaktion für Einwahlkonferenzen" steht im lync Server 2013 Management Pack nicht mehr zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="f20d5-145">The dial-in conferencing synthetic transaction cmdlet is no longer available in the Lync Server 2013 Management Pack</span></span>

<span data-ttu-id="f20d5-146">**Problem**</span><span class="sxs-lookup"><span data-stu-id="f20d5-146">**Issue:**</span></span>

<span data-ttu-id="f20d5-147">Das Cmdlet **Test-CsDialInConferencing** für die Einwahlkonferenz synthetische Transaktionen steht im lync Server 2013 Management Pack nicht mehr zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="f20d5-147">The dial-in conferencing synthetic transaction cmdlet **Test-CsDialInConferencing** is no longer available in the Lync Server 2013 Management Pack.</span></span>

<span data-ttu-id="f20d5-148">**Problemumgehung**</span><span class="sxs-lookup"><span data-stu-id="f20d5-148">**Workaround:**</span></span>

<span data-ttu-id="f20d5-149">Die Verwendung des Cmdlets **Test-CsDialInConferencing** für die synthetische Transaktion der Einwahlkonferenz wird nur intern für Unternehmen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f20d5-149">Use of the Dial-In Conferencing Synthetic Transaction cmdlet **Test-CsDialInConferencing** is supported only internally to an enterprise.</span></span>

<span data-ttu-id="f20d5-150">Administratoren können das Cmdlet in lync Server-Verwaltungsshell zu Problembehandlungszwecken weiterhin verwenden.</span><span class="sxs-lookup"><span data-stu-id="f20d5-150">Administrators may continue to use the cmdlet in Lync Server Management Shell for troubleshooting purposes.</span></span> <span data-ttu-id="f20d5-151">Bei Bedarf kann ein Unternehmen auch ein privates Management Pack zur internenen Ausführung des Cmdlets entwickeln.</span><span class="sxs-lookup"><span data-stu-id="f20d5-151">If required, an enterprise can also develop a private management pack to run the cmdlet internally.</span></span>

</div>

<div>

## <a name="the-centralized-logging-service-stops-if-network-traffic-is-disrupted-when-log-files-are-being-copied-to-network-share"></a><span data-ttu-id="f20d5-152">Der zentralisierte Protokollierungsdienst wird angehalten, wenn der Netzwerkdatenverkehr unterbrochen wird, wenn Protokolldateien in die Netzwerkfreigabe kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="f20d5-152">The Centralized Logging Service stops if network traffic is disrupted when log files are being copied to network share</span></span>

<span data-ttu-id="f20d5-153">**Problem**</span><span class="sxs-lookup"><span data-stu-id="f20d5-153">**Issue:**</span></span>

<span data-ttu-id="f20d5-154">Wenn der zentralisierte Protokollierungsdienst für die Verwendung eines Netzwerkpfads (der Wert des Parameters "CacheFileNetworkFolder" des **Get-CsClsConfiguration**-Cmdlets ist ein gültiger UNC-Pfad) konfiguriert ist, werden zwischengespeicherte Protokolldateien auf das Netzlaufwerk kopiert.</span><span class="sxs-lookup"><span data-stu-id="f20d5-154">When the Centralized Logging Service is configured to use a network path (the value of the CacheFileNetworkFolder parameter of the **Get-CsClsConfiguration** cmdlet is a valid UNC path), cached log files are copied to the network share.</span></span> <span data-ttu-id="f20d5-155">Wenn beim Kopieren der Dateien eine Störung im Netzwerkdatenverkehr auftritt, wird eine Ausnahme ausgelöst, durch die der zentralisierte Protokollierungsdienst angehalten wird.</span><span class="sxs-lookup"><span data-stu-id="f20d5-155">If there is a disruption in network traffic while the files are being copied, an exception will occur that will cause the centralized logging service to stop.</span></span>

<span data-ttu-id="f20d5-156">Der Dienst ist für bis zu drei automatische Neustarts konfiguriert, sodass er ausgehend von den ersten drei Ausnahmen neu gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="f20d5-156">The service is configured to automatically restart up to three times, so the service will recover from the first three exceptions.</span></span>

<span data-ttu-id="f20d5-157">**Problemumgehung**</span><span class="sxs-lookup"><span data-stu-id="f20d5-157">**Workaround:**</span></span>

<span data-ttu-id="f20d5-158">Das Problem kann nicht umgangen werden.</span><span class="sxs-lookup"><span data-stu-id="f20d5-158">There is no workaround for this issue.</span></span> <span data-ttu-id="f20d5-159">Um das Problem zu identifizieren, überwachen Sie das Ereignisprotokoll für die Ereignis-ID 7031 aus dem Dienststeuerungs-Manager, der protokolliert, wenn der Dienst Agent für lync Server zentralisierten Protokollierungsdienst unerwartet beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="f20d5-159">To identify the issue, monitor the event log for Event ID 7031 from the "Service Control Manager" that logs when the "Lync Server Centralized Logging Service Agent" service has terminated unexpectedly.</span></span> <span data-ttu-id="f20d5-160">Wenn dies mehr als dreimal geschieht, starten Sie den Dienst manuell mit dem Cmdlet " **Start-CsWindowService** " neu.</span><span class="sxs-lookup"><span data-stu-id="f20d5-160">If this happens more than three times, manually restart the service by using the **Start-CsWindowService** cmdlet.</span></span>

</div>

<div>

## <a name="storage-service-queue-items-need-to-be-imported-manually"></a><span data-ttu-id="f20d5-161">Speicherdienst-Warteschlangenelemente müssen manuell importiert werden</span><span class="sxs-lookup"><span data-stu-id="f20d5-161">Storage Service Queue Items need to be imported manually</span></span>

<span data-ttu-id="f20d5-162">**Problem**</span><span class="sxs-lookup"><span data-stu-id="f20d5-162">**Issue:**</span></span>

<span data-ttu-id="f20d5-163">In lync Server 2013 werden Daten zu Konferenzen und Chatnachrichten (beispielsweise archivierte Nachrichten und Aufzeichnung von Kommunikationsdatensätzen) in einer Datenbank auf jeder Front-End-Server gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f20d5-163">Lync Server 2013 stores data about conferencing and instant messaging, such as archived messages and call detail recording (CDR), on a database on each Front End Server.</span></span> <span data-ttu-id="f20d5-164">Die Daten werden während der Verarbeitung in der Datenbank gespeichert, bevor Sie an das vorgesehene Ziel übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="f20d5-164">The data is stored in the database while it is being processed before being delivered to the intended destination.</span></span> <span data-ttu-id="f20d5-165">Um die Leistung zu verbessern, exportiert lync Server 2013 die Warteschlangenelemente regelmäßig aus der lokalen Datenbank, die für einen längeren Zeitraum nicht verarbeitet werden, und speichert Sie im Dateispeicher.</span><span class="sxs-lookup"><span data-stu-id="f20d5-165">To improve performance, Lync Server 2013 periodically exports the queue items from the local database that are not processed for an extended period of time, and saves them on the file store.</span></span> <span data-ttu-id="f20d5-166">Wenn der Dateispeicher nicht verfügbar ist, werden die Elemente auf jeder Front-End-Server gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f20d5-166">If the file store is unavailable, the items are stored on each Front End Server.</span></span> <span data-ttu-id="f20d5-167">Derselbe Vorgang wird zum Verhindern von Datenverlusten bei Failovervorgängen für Pools verwendet.</span><span class="sxs-lookup"><span data-stu-id="f20d5-167">The same operation occurs to prevent data loss during pool failover.</span></span>

<span data-ttu-id="f20d5-168">Während des Exportvorgangs zeichnet der lync Server Speicherdienst jede Stufe im Ereignisprotokoll mit den Ereignis-IDs 32075 (vollständiger Löschvorgang wird gestartet), 32076 (vollständiger Flush ist abgeschlossen), 32082 (Wartungsebene wird gestartet), 32083 (Wartungsebene bündig ist abgeschlossen), 32089 (Flush erfolgte aufgrund des Füllens der Datenbank).</span><span class="sxs-lookup"><span data-stu-id="f20d5-168">During the export operation, the Lync Server Storage Service records every stage in the event log with event IDs of 32075 (full flush operation is started), 32076 (full flush is completed), 32082 (maintenance level flush is started), 32083 (maintenance level flush is completed), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="f20d5-169">Diese Daten werden nicht automatisch zurück in das System importiert, damit Sie verarbeitet und an ihr endgültiges Ziel (SQL Server oder Exchange Server) übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="f20d5-169">This data will not automatically be imported back to the system to be processed and delivered to its final destination (SQL Server or Exchange Server).</span></span>

<span data-ttu-id="f20d5-170">**Problemumgehung**</span><span class="sxs-lookup"><span data-stu-id="f20d5-170">**Workaround:**</span></span>

<span data-ttu-id="f20d5-171">Um die Daten in das System zu importieren, müssen Administratoren das ImportStorageServiceData-Tool im lync Server Resource Kit verwenden, mit dem die Daten wieder in das System eingefügt werden, damit Sie verarbeitet und an ihr endgültiges Ziel übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="f20d5-171">To import the data to the system, administrators will need to use the ImportStorageServiceData tool in the Lync Server Resource Kit, which will add the data back into the system to be processed and delivered to its final destination.</span></span>

</div>

<div>

## <a name="address-book-web-query-searches-will-fail-if-the-default-value-for-usenormalizationrules-is-changed-to-false"></a><span data-ttu-id="f20d5-172">Bei der Suche nach Adressbuch-Webabfragen tritt ein Fehler auf, wenn der Standardwert für UseNormalizationRules in false geändert wird.</span><span class="sxs-lookup"><span data-stu-id="f20d5-172">Address Book Web Query searches will fail if the default value for UseNormalizationRules is changed to False</span></span>

<span data-ttu-id="f20d5-173">**Problem**</span><span class="sxs-lookup"><span data-stu-id="f20d5-173">**Issue:**</span></span>

<span data-ttu-id="f20d5-p112">Wenn der Standardwert für UseNormalizationRules in "False" geändert wird, schlagen Adressbuch-Webabfragen fehl. Nach dem Ändern des Standardwerts können Lync Client-Benutzer die Lync-Adressbuch-Webabfrage nicht zum Suchen nach Benutzern verwenden.</span><span class="sxs-lookup"><span data-stu-id="f20d5-p112">If the default value for UseNormalizationRules is changed to False, Address Book Web Query searches will fail. After the default value is changed, Lync Client users will not be able to use Lync Address Book web query to search for users.</span></span>

<span data-ttu-id="f20d5-176">**Problemumgehung**</span><span class="sxs-lookup"><span data-stu-id="f20d5-176">**Workaround:**</span></span>

<span data-ttu-id="f20d5-177">Wenn der Standardwert für UseNormalizationRules auf false festgelegt ist, damit Benutzer Telefonnummern wie in Active Directory-Domänendienste definiert verwenden können, ohne Normalisierungsregeln lync Server 2013 anzuwenden, umgehen Sie dieses Problem, indem Sie folgende Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="f20d5-177">If the default value for UseNormalizationRules is set to False so that users can use phone numbers as defined in Active Directory Domain Services without Lync Server 2013 applying normalization rules, work around this issue by doing the following:</span></span>

1.  <span data-ttu-id="f20d5-178">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="f20d5-178">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="f20d5-179">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="f20d5-179">Do one of the following:</span></span>
    
      - <span data-ttu-id="f20d5-180">Wenn Ihre Bereitstellung nur lync Server 2013 Server enthält, führen Sie das folgende Cmdlet auf globaler Ebene aus, um die Werte für UseNormalizationRules und IgnoreGenericRules in true zu ändern:</span><span class="sxs-lookup"><span data-stu-id="f20d5-180">If your deployment includes only Lync Server 2013 servers, run the following cmdlet at the global level to change the values for UseNormalizationRules and IgnoreGenericRules to True:</span></span>
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - <span data-ttu-id="f20d5-181">Wenn Ihre Bereitstellung eine Kombination aus lync Server 2013 und lync Server 2010 oder Office Communications Server 2007 R2 enthält, führen Sie das folgende Cmdlet aus, und weisen Sie es jedem lync Server 2013 Pool in der Topologie zu:</span><span class="sxs-lookup"><span data-stu-id="f20d5-181">If your deployment includes a combination of Lync Server 2013 and Lync Server 2010 or Office Communications Server 2007 R2, run the following cmdlet and assign it to each Lync Server 2013 pool in the topology:</span></span>
        
            new-csAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  <span data-ttu-id="f20d5-182">Warten Sie, bis die CMS-Replikation für alle Pools erfolgt ist.</span><span class="sxs-lookup"><span data-stu-id="f20d5-182">Wait for CMS replication to occur on all pools.</span></span>

4.  <span data-ttu-id="f20d5-183">Ändern Sie die Datei mit den Telefonnormalisierungsregeln für Ihre Bereitstellung, sodass die Inhalte gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="f20d5-183">Modify the phone normalization rules file for your deployment to clear the content.</span></span> <span data-ttu-id="f20d5-184">Die Datei befindet sich in der Dateifreigabe der einzelnen lync Server 2013 Pools.</span><span class="sxs-lookup"><span data-stu-id="f20d5-184">The file is on the file share of each Lync Server 2013 pool.</span></span> <span data-ttu-id="f20d5-185">Wenn die Datei nicht vorhanden ist, erstellen Sie eine leere Datei mit dem Namen\_"\_Normalisierung\_\_Rules. txt" für Firmen Telefonnummern.</span><span class="sxs-lookup"><span data-stu-id="f20d5-185">If the file is not present, then create an empty file named "Company\_Phone\_Number\_Normalization\_Rules.txt."</span></span>

5.  <span data-ttu-id="f20d5-186">Warten Sie einige Minuten, bis alle Front-End-Pools die neuen Dateien gelesen haben.</span><span class="sxs-lookup"><span data-stu-id="f20d5-186">Wait several minutes for all Front End pools to read the new files.</span></span>

6.  <span data-ttu-id="f20d5-187">Führen Sie das folgende Cmdlet für jeden lync Server 2013 Pool in der Bereitstellung aus.</span><span class="sxs-lookup"><span data-stu-id="f20d5-187">Run the following cmdlet on each Lync Server 2013 pool in your deployment.</span></span>
    
        Update-csAddressBook

</div>

<div>

## <a name="address-book-server-error-event-21054-is-generated-once-daily-for-each-lync-2013-pool"></a><span data-ttu-id="f20d5-188">Das Adressbuch Server-Fehlerereignis 21054 wird einmal täglich für jeden lync 2013 Pool generiert.</span><span class="sxs-lookup"><span data-stu-id="f20d5-188">Address Book Server error event 21054 is generated once daily for each Lync 2013 pool</span></span>

<span data-ttu-id="f20d5-189">**Problem**</span><span class="sxs-lookup"><span data-stu-id="f20d5-189">**Issue:**</span></span>

<span data-ttu-id="f20d5-190">Lync Server 2013 Adressbuch Server generiert ein Fehlerereignis 21054 einmal täglich, wenn die tägliche Wartung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f20d5-190">Lync Server 2013 Address Book Server will generate error event 21054 once every day when performing daily maintenance.</span></span> <span data-ttu-id="f20d5-191">Der Fehler wird auch jedes Mal generiert, wenn ein Administrator das Cmdlet **Update-csAddressBook** ausführt, auch wenn das Update erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f20d5-191">The error is also generated every time an administrator runs the **Update-csAddressBook** cmdlet, even when the update is successful.</span></span> <span data-ttu-id="f20d5-192">Bei einer erfolgreichen Aktualisierung kann dieses Fehlerereignis jedoch bedenkenlos ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="f20d5-192">However, this error event can safely be ignored when the update is successful.</span></span>

<span data-ttu-id="f20d5-193">**Problemumgehung**</span><span class="sxs-lookup"><span data-stu-id="f20d5-193">**Workaround:**</span></span>

<span data-ttu-id="f20d5-194">Wenn dieses Fehlerereignis eintritt, führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="f20d5-194">When you encounter this error event, run the following cmdlet:</span></span>

    Debug-csAddressBookReplication -Poolfqdn <Pool FQDN for which the event was generated>

<span data-ttu-id="f20d5-195">Wenn das Cmdlet meldet, dass keine nicht indizierten oder verlassenen Objekte vorhanden sind, kann das Error-Ereignis 21054 sicher ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="f20d5-195">If the cmdlet reports that there are no unindexed or abandoned objects, the error event 21054 can be safely ignored.</span></span>

<span data-ttu-id="f20d5-196">Zudem sollte der Key Health Indicator (KHI) "Adressbuchbenutzer ordnungsgemäß indiziert" im System Center Operations Manager deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="f20d5-196">Additionally, the Key Health Indicator (KHI) "Address Book Users Correctly Indexed" should be turned off in System Center Operations Manager.</span></span>

</div>

<div>

## <a name="requests-may-fail-when-ipv6-is-configured-on-an-edge-pool"></a><span data-ttu-id="f20d5-197">Für Anforderungen kann ein Fehler auftreten, wenn IPv6 auf einem Edgepool konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="f20d5-197">Requests may fail when IPv6 is configured on an Edge pool</span></span>

<span data-ttu-id="f20d5-198">**Problem**</span><span class="sxs-lookup"><span data-stu-id="f20d5-198">**Issue:**</span></span>

<span data-ttu-id="f20d5-199">Wenn IPv6 auf einem Edgepool konfiguriert ist, schlagen möglicherwesie einige Anforderungen an den Edgepool fehl.</span><span class="sxs-lookup"><span data-stu-id="f20d5-199">When IPv6 is configured on an Edge pool, some requests to the Edge pool may fail.</span></span>

<span data-ttu-id="f20d5-200">**Problemumgehung**</span><span class="sxs-lookup"><span data-stu-id="f20d5-200">**Workaround:**</span></span>

<span data-ttu-id="f20d5-201">Konfigurieren Sie zur Umgehung dieses Problems Edgepools nicht mit IPv6.</span><span class="sxs-lookup"><span data-stu-id="f20d5-201">To work around this issue, do not configure an Edge pool with IPv6.</span></span>

</div>

<div>

## <a name="the-invoke-cspoolfailback-cmdlet-may-fail-during-pool-failback"></a><span data-ttu-id="f20d5-202">Das Invoke-csPoolFailback-Cmdlet schlägt möglicherweise beim Failback des Pools fehl</span><span class="sxs-lookup"><span data-stu-id="f20d5-202">The invoke-csPoolFailback cmdlet may fail during pool failback</span></span>

<span data-ttu-id="f20d5-203">**Problem**</span><span class="sxs-lookup"><span data-stu-id="f20d5-203">**Issue:**</span></span>

<span data-ttu-id="f20d5-204">Beim Versuch, einen Failback-Vorgang für einen Pool auszuführen, gibt das Cmdlet **invoke-csPoolFailback** möglicherweise den Fehler "Abschluss des Hydrationsprozesses nach mehreren Versuchen fehlgeschlagen" zurück.</span><span class="sxs-lookup"><span data-stu-id="f20d5-204">When attempting to fail back a pool, the **invoke-csPoolFailback** cmdlet may fail with the error, "Failed to complete hydration process after repeated attempts."</span></span>

<span data-ttu-id="f20d5-205">**Problemumgehung**</span><span class="sxs-lookup"><span data-stu-id="f20d5-205">**Workaround:**</span></span>

<span data-ttu-id="f20d5-p115">Wenn Sie dieses Problem umgehen möchten, führen Sie das Cmdlet erneut aus, und warten Sie, bis das Cmdlet erfolgreich abgeschlossen wurde. Beachten Sie, dass der Failback-Vorgang mehrere Minuten in Anspruchen nehmen kann. Für einen Pool mit 20.000 Benutzern kann dies bis zu 60 Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="f20d5-p115">To work around this issue, run the cmdlet again, and wait until the cmdlet succeeds. Note that the failback process can take several minutes to complete. It may take up to 60 minutes for a pool with 20,000 users.</span></span>

</div>

<div>

## <a name="data-loss-may-occur-when-you-add-a-front-end-server-to-an-already-established-pool--hybrid-skype-for-business-online"></a><span data-ttu-id="f20d5-209">Datenverlust kann auftreten, wenn Sie eine Front-End-Server zu einem bereits vorhandenen Pool hinzufügen – Hybrid, Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="f20d5-209">Data loss may occur when you add a Front End Server to an already established pool – Hybrid, Skype for Business Online</span></span>

<span data-ttu-id="f20d5-210">**Problem**</span><span class="sxs-lookup"><span data-stu-id="f20d5-210">**Issue:**</span></span>

<span data-ttu-id="f20d5-211">Dieses Problem kann in einer Umgebung auftreten, in der ein Pool über mehr als eine Front-End-Server verfügt, und Sie können entweder einen der Front-End-Server neu starten oder einen neuen Front-End-Server hinzufügen, der zuvor nicht Teil des Pools war.</span><span class="sxs-lookup"><span data-stu-id="f20d5-211">You may encounter this issue in an environment where a pool has more than one Front End Server, and you either restart one of the Front End Servers, or add a new Front End Server that was not previously part of the pool.</span></span>

<span data-ttu-id="f20d5-p116">Bei Benutzern, deren Daten archiviert werden, kommt es möglicherweise zu Datenverlusten, bis eine stabile Verteilung der Datenarchivierung für den Pool hergestellt wurde. Dieser Zeitraum mit potenziellem Datenverlust ist für Konversationen zwischen Personen auf 15 Minuten und für Konferenzen auf 30 Minuten begrenzt.</span><span class="sxs-lookup"><span data-stu-id="f20d5-p116">Users whose data is being archived may experience data loss until a stable distribution of data archiving is established for the pool. This period of potential data loss is limited to 15 minutes for person-to-person conversations, and 30 minutes for conferences.</span></span>

<span data-ttu-id="f20d5-214">**Problemumgehung**</span><span class="sxs-lookup"><span data-stu-id="f20d5-214">**Workaround:**</span></span>

<span data-ttu-id="f20d5-215">Wenn Sie die Wartung durchführen, statt Front-End-Server einzeln im Pool zu starten, sollten Sie einen Failover des Pools zu einem anderen Pool durchführen und dann Wartungsaufgaben auf den Servern ausführen.</span><span class="sxs-lookup"><span data-stu-id="f20d5-215">When you perform maintenance, instead of starting Front End Servers in the pool one by one, you should fail over the pool to another pool, and then perform maintenance tasks on the servers.</span></span> <span data-ttu-id="f20d5-216">Sie können die Verfügbarkeit des Diensts vor dem Ausführen von Wartungsaufgaben auch aufheben und die Verfügbarkeit dann nach Abschluss der Wartung wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="f20d5-216">You can also make the service unavailable before performing maintenance tasks, and then restore availability when maintenance is complete.</span></span>

</div>

<div>

## <a name="administrators-cannot-get-licensee-count-by-using-the-get-csclientaccesslicense-cmdlet"></a><span data-ttu-id="f20d5-217">Administratoren können die Anzahl der Lizenznehmer nicht mithilfe des Get-csclientaccesslicense abrufen-Cmdlets abrufen.</span><span class="sxs-lookup"><span data-stu-id="f20d5-217">Administrators cannot get licensee count by using the Get-CsClientAccessLicense cmdlet</span></span>

<span data-ttu-id="f20d5-218">**Problem**</span><span class="sxs-lookup"><span data-stu-id="f20d5-218">**Issue:**</span></span>

<span data-ttu-id="f20d5-219">Administratoren können die genaue Clientlizenzverwendung nicht mithilfe des Cmdlets **Get-CsClientAccessLicense** abrufen.</span><span class="sxs-lookup"><span data-stu-id="f20d5-219">Administrators cannot get accurate client license usage by using the **Get-CsClientAccessLicense** cmdlet.</span></span>

<span data-ttu-id="f20d5-220">**Problemumgehung**</span><span class="sxs-lookup"><span data-stu-id="f20d5-220">**Workaround:**</span></span>

<span data-ttu-id="f20d5-221">Wenn Sie den Serverlizenztyp überprüfen möchten, können Sie das Cmdlet **Get-CsService** ausführen, um die vollqualifizierten Domänennamen (Fully Qualified Domain Names, FDQNs) aller Datenbanken abzurufen.</span><span class="sxs-lookup"><span data-stu-id="f20d5-221">To check the server license type, you can run the **Get-CsService** cmdlet to retrieve the fully qualified domain names (FDQNs) of all databases.</span></span> <span data-ttu-id="f20d5-222">Wenn der FQDN des Front-End-Server mit dem FQDN der Back-End-Datenbank identisch ist, handelt es sich bei der Lizenz um eine Standard Edition-Lizenz.</span><span class="sxs-lookup"><span data-stu-id="f20d5-222">If the FQDN of the Front End Server is the same as the FQDN of the back-end database, the license is a Standard edition license.</span></span> <span data-ttu-id="f20d5-223">Andernfalls ist die Lizenz eine Enterprise Edition-Lizenz.</span><span class="sxs-lookup"><span data-stu-id="f20d5-223">Otherwise, the license is an Enterprise edition license.</span></span>

</div>

<div>

## <a name="client-licensee-count-is-not-accurately-reported"></a><span data-ttu-id="f20d5-224">Anzahl der Client Lizenzen wird nicht genau gemeldet</span><span class="sxs-lookup"><span data-stu-id="f20d5-224">Client licensee count is not accurately reported</span></span>

<span data-ttu-id="f20d5-225">**Problem**</span><span class="sxs-lookup"><span data-stu-id="f20d5-225">**Issue:**</span></span>

<span data-ttu-id="f20d5-226">Beim Ermitteln der Clienzlizenzanzahl liegen möglicherweise die folgenden Zustände vor:</span><span class="sxs-lookup"><span data-stu-id="f20d5-226">When determining client license counts, you may experience the following conditions:</span></span>

1.  <span data-ttu-id="f20d5-227">**Ungenaue Lizenzanzahl für mobile Benutzer**</span><span class="sxs-lookup"><span data-stu-id="f20d5-227">**Inaccurate license count for mobile users**</span></span>
    
    <span data-ttu-id="f20d5-p119">Die Lizenzanzahl basiert auf der Anzahl eindeutiger IP-Adressen für gerätebasierte Benutzer. Die Lizenzanzahl wird wie folgt begrenzt:</span><span class="sxs-lookup"><span data-stu-id="f20d5-p119">The license count is based on the number of unique IP addresses for device-based users. The license count will be limited in the following ways:</span></span>
    
      - <span data-ttu-id="f20d5-230">Es werden zu viele Lizenzen gezählt, wenn sich die IP-Adresse für den Benutzer in Lync-Sitzungen ändert.</span><span class="sxs-lookup"><span data-stu-id="f20d5-230">Licenses will be overcounted if the IP address for the user changes during Lync sessions.</span></span> <span data-ttu-id="f20d5-231">Dies kann auftreten, wenn ein Benutzer mit einem Desktop Client eine Verbindung mit lync Server von mehr als einem Standort herstellt.</span><span class="sxs-lookup"><span data-stu-id="f20d5-231">This can occur when a user connects to Lync Server from more than one location with a desktop client.</span></span>
    
      - <span data-ttu-id="f20d5-232">Es werden zu wenig Lizenzen gezählt, wenn ein Benutzer eine Verbindung mit einem mobilen Client herstellt, weil die IP-Adresse für das Gerät nicht bestimmt werden kann.</span><span class="sxs-lookup"><span data-stu-id="f20d5-232">Licenses will be undercounted if a user connects with a mobile client, because the IP address for the device cannot be determined.</span></span>

2.  <span data-ttu-id="f20d5-233">**Für Lync-Client-Anrufe über das Festnetz (Public Switched Telephone Network, PSTN), Lync-Client-Anrufe an PSTN-Leitungen und Lync-Anrufweiterleitungen an PSTN-Leitungen werden die Lizenzen doppelt gezählt**</span><span class="sxs-lookup"><span data-stu-id="f20d5-233">**Licenses are counted twice for public switched telephone network (PSTN) calls to Lync client, Lync client calls to PSTN lines, and Lync calls forwarded to PSTN lines**</span></span>
    
    <span data-ttu-id="f20d5-p121">In den folgenden Szenarien werden anstatt einer zwei zusätzliche Lizenzen gezählt, da zum Ermitteln der Anzahl verwendeter Lizenzen sowohl die Telefonnummer als auch der Lync-Benutzer gezählt wird. Wenn Sie die richtigen Lizenzierungsdaten abrufen möchten, entfernen Sie die von einer Telefonnummer generierten Lizenzen manuell.</span><span class="sxs-lookup"><span data-stu-id="f20d5-p121">In the following scenarios, two additional licenses will be counted instead of one because both the phone number and the Lync user are counted to determine the number of licenses used. To obtain accurate licensing data, manually remove the licenses generated by a phone number.</span></span>
    
      - <span data-ttu-id="f20d5-236">Ein PSTN-Telefonanruf an Lync</span><span class="sxs-lookup"><span data-stu-id="f20d5-236">A PSTN phone call to Lync</span></span>
    
      - <span data-ttu-id="f20d5-237">Ein Lync-Anruf an eine PSTN-Leitung</span><span class="sxs-lookup"><span data-stu-id="f20d5-237">A Lync call to a PSTN line</span></span>
    
      - <span data-ttu-id="f20d5-p122">Ein PSTN-Anruf an Lync und anschließende Anrufweiterleitung durch Lync an eine PSTN-Leitung. Eine der PSTN-Leitungen wird gezählt.</span><span class="sxs-lookup"><span data-stu-id="f20d5-p122">A PSTN call to Lync, and then Lync forwards the call to a PSTN line. One of the PSTN lines will be counted.</span></span>

3.  <span data-ttu-id="f20d5-240">**Für ein angemeldetes Lync-Telefon wird keine Lizenz gezählt**</span><span class="sxs-lookup"><span data-stu-id="f20d5-240">**A license will not be counted for a logged-on Lync phone**</span></span>
    
    <span data-ttu-id="f20d5-241">Wenn ein Benutzer ein Lync-zertifiziertes Telefon verwendet, das Telefon angemeldet wird und verbunden bleibt und der Anmeldestatus beibehalten wird, wird das Telefon nicht für die Verwendung einer Lizenz gezählt, sofern die Abfrage nach Lizenzen nach der Anmeldung des Telefons erfolgt.</span><span class="sxs-lookup"><span data-stu-id="f20d5-241">When a user uses a Lync-certified phone, if the phone logs in and stays connected, which retains its logon status, the phone will not be counted as using a license if the query for licenses occurs after the phone logged in.</span></span>

4.  <span data-ttu-id="f20d5-242">**Gezählte Lizenzen für PSTN-Telefone, die Konferenzen beitreten**</span><span class="sxs-lookup"><span data-stu-id="f20d5-242">**Licenses counted for PSTN phones joining conferences**</span></span>
    
    <span data-ttu-id="f20d5-p123">Wenn ein Benutzer mit einem PSTN-Telefon einer Konferenz beitritt, wird fälschlicherweise eine Lizenz für den Beitritt zu der Konferenz gezählt. Für den Beitritt zu einer Konferenz mit einem PSTN-Telefon wird keine Lizenz benötigt.</span><span class="sxs-lookup"><span data-stu-id="f20d5-p123">When a user joins a conference with a PSTN phone, a license will inaccurately be counted for joining the conference. However, no license is needed to join a conference with a PSTN phone.</span></span>

<span data-ttu-id="f20d5-245">**Problemumgehung**</span><span class="sxs-lookup"><span data-stu-id="f20d5-245">**Workaround:**</span></span>

1.  <span data-ttu-id="f20d5-246">**Ungenaue Lizenzanzahl für mobile Benutzer**</span><span class="sxs-lookup"><span data-stu-id="f20d5-246">**Inaccurate license count for mobile users**</span></span>
    
      - <span data-ttu-id="f20d5-247">Sie können die IP-Adressen, die zu ein und demselben Gerät gehören, manuell identifizieren und dann eine der Adressen aus der Lizenzanzahl entfernen.</span><span class="sxs-lookup"><span data-stu-id="f20d5-247">You can manually identify the IP addresses that belong to the same device and then remove one of them in the license count.</span></span>
    
      - <span data-ttu-id="f20d5-248">Beim Verbinden mobiler Geräte mit dem Lync-Client kann dieses Problem nicht umgangen werden.</span><span class="sxs-lookup"><span data-stu-id="f20d5-248">There is no workaround for this issue with mobile devices connecting with Lync client.</span></span>

2.  <span data-ttu-id="f20d5-249">**Für PSTN-Anrufe des Lync-Clients, Lync-Client-Anrufe an PSTN-Leitungen und Lync-Anfrufweiterleitungen an PSTN-Leitungen werden Lizenzen doppelt gezählt**</span><span class="sxs-lookup"><span data-stu-id="f20d5-249">**Licenses are counted twice for PSTN calls to Lync client, Lync client calls to PSTN lines, and Lync calls forwarded to PSTN lines**</span></span>
    
    <span data-ttu-id="f20d5-250">Sie müssen die PSTN-Telefonnummer manuell identifizieren und die für sie generierte Lizenzanzahl entfernen.</span><span class="sxs-lookup"><span data-stu-id="f20d5-250">You will need to manually identify the PSTN phone number and remove the license count generated for it.</span></span>

3.  <span data-ttu-id="f20d5-251">**Für angemeldete Lync-Telefone werden keine Lizenzen gezählt**</span><span class="sxs-lookup"><span data-stu-id="f20d5-251">**A license will not be counted for a logged-in Lync phone**</span></span>
    
    <span data-ttu-id="f20d5-252">Sie können das Lync-Telefon so konfigurieren, dass es in einem regelmäßigen Intervall (beispielsweise alle drei Monate) abgemeldet und dann wieder angemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="f20d5-252">You can configure the Lync phone to log off, and then log on again, at a regular interval, such as every 3 months.</span></span>

4.  <span data-ttu-id="f20d5-253">**Gezählte Lizenzen für PSTN-Telefone, die Konferenzen beitreten**</span><span class="sxs-lookup"><span data-stu-id="f20d5-253">**Licenses counted for PSTN phones joining conferences**</span></span>
    
    <span data-ttu-id="f20d5-254">Sie können die PSTN-Telefonnummer, die für den Konferenzbeitritt verwendet wird, manuell identifizieren und die von der Telefonnummer generierte Lizenz entfernen.</span><span class="sxs-lookup"><span data-stu-id="f20d5-254">You can manually identify the PSTN phone number that is used to join the conference and remove the license generated by the phone number.</span></span>

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-upgrading-to-silverlight-5"></a><span data-ttu-id="f20d5-255">Das lync Server-Systemsteuerung in einer VMware-Umgebung nach dem Upgrade auf Silverlight 5 nicht mehr funktioniert</span><span class="sxs-lookup"><span data-stu-id="f20d5-255">The Lync Server Control Panel stops working in a VMware environment after upgrading to Silverlight 5</span></span>

<span data-ttu-id="f20d5-256">**Problem**</span><span class="sxs-lookup"><span data-stu-id="f20d5-256">**Issue:**</span></span>

<span data-ttu-id="f20d5-257">Wenn Sie das lync Server-Systemsteuerung in einer VMware-Umgebung verwenden, funktioniert das lync Server-Systemsteuerung nach dem Upgrade Microsoft Silverlight auf Version 5 möglicherweise nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="f20d5-257">If you use the Lync Server Control Panel in a VMware environment, the Lync Server Control Panel may stop working after you upgrade Microsoft Silverlight to version 5.</span></span>

<span data-ttu-id="f20d5-258">**Problemumgehung**</span><span class="sxs-lookup"><span data-stu-id="f20d5-258">**Workaround:**</span></span>

<span data-ttu-id="f20d5-259">Führen Sie einen der folgenden Schritte aus, um das Problem zu umgehen:</span><span class="sxs-lookup"><span data-stu-id="f20d5-259">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="f20d5-260">Deinstallieren Sie Silverlight 5, und installieren Sie Silverlight [https://go.microsoft.com/fwlink/p/?LinkID=149156](https://go.microsoft.com/fwlink/p/?linkid=149156)4 aus.</span><span class="sxs-lookup"><span data-stu-id="f20d5-260">Uninstall Silverlight 5, and install Silverlight 4 from [https://go.microsoft.com/fwlink/p/?LinkID=149156](https://go.microsoft.com/fwlink/p/?linkid=149156).</span></span>

  - <span data-ttu-id="f20d5-261">Greifen Sie auf den lync Server-Systemsteuerung von einem Computer aus, auf dem es sich nicht um einen virtuellen VMware-Computer handelt.</span><span class="sxs-lookup"><span data-stu-id="f20d5-261">Access the Lync Server Control Panel from a computer that is not a VMware virtual computer.</span></span>
    
    <span data-ttu-id="f20d5-262">Dazu können Sie die lync Server-Systemsteuerung im Windows- **Startmenü** auf dem Server starten, wenn die lync Server Verwaltungstools auf dem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="f20d5-262">To do so, you can start the Lync Server Control Panel from the Windows **Start** menu on the server, if the Lync Server Administration tools are installed on the computer.</span></span>
    
    <span data-ttu-id="f20d5-263">Sie können auch über einen Webbrowser auf die lync Server-Systemsteuerung zugreifen.</span><span class="sxs-lookup"><span data-stu-id="f20d5-263">You can also access the Lync Server Control Panel by using a web browser.</span></span> <span data-ttu-id="f20d5-264">\<Die URL ähnelt dem FQDN\_\_\>des https://-Front-End-Pools/CSCP.</span><span class="sxs-lookup"><span data-stu-id="f20d5-264">The URL will be similar to https://\<frontend\_pool\_fqdn\>/cscp.</span></span>

</div>

<div>

## <a name="user-information-in-the-address-book-service-is-not-updated-after-the-distinguished-name-for-the-user-is-modified-in-active-directory"></a><span data-ttu-id="f20d5-265">Benutzerinformationen im Adressbuchdienst werden nicht aktualisiert, nachdem der Distinguished Name für den Benutzer in Active Directory geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="f20d5-265">User information in the Address Book Service is not updated after the distinguished name for the user is modified in Active Directory</span></span>

<span data-ttu-id="f20d5-266">**Problem**</span><span class="sxs-lookup"><span data-stu-id="f20d5-266">**Issue:**</span></span>

<span data-ttu-id="f20d5-267">Wenn die Distinguished Name (auch als DN bekannt) eines Benutzers in Active Directory-Domänendienste geändert wird, werden alle weiteren Änderungen nicht im Adressbuchdienst (ABS) aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="f20d5-267">If a user’s distinguished name (also known as DN) is changed in Active Directory Domain Services, any additional changes will not be updated in the Address Book Service (ABS).</span></span> <span data-ttu-id="f20d5-268">Dies wirkt sich nicht auf die Anmeldung oder Anwesenheit des Benutzers aus, verhindert jedoch die Kommunikation des Benutzers, wenn die SIP-Adresse ebenfalls geändert wird, da durch Suchvorgänge eine veraltete SIP-Adresse zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="f20d5-268">This does not affect sign-in or presence for the user, but it will prevent communication for the user if the SIP address is also changed, because searches will return an outdated SIP address.</span></span>

<span data-ttu-id="f20d5-269">**Problemumgehung**</span><span class="sxs-lookup"><span data-stu-id="f20d5-269">**Workaround:**</span></span>

<span data-ttu-id="f20d5-p126">Wenn Sie dieses Problem umgehen möchten, ändern Sie den DN eines Benutzers nicht. Wenn Sie den DN für den Benutzer auf den vorherigen Wert zurücksetzen, spiegeln sich Aktualisierungen im Adressbuchdienst wider.</span><span class="sxs-lookup"><span data-stu-id="f20d5-p126">To work around this issue, do not change a user’s DN. If you revert the DN for the user to the previous value, updates will be reflected in the Address Book Service.</span></span>

</div>

</div>

<span id="Installation"></span>

<div>

## <a name="installation"></a><span data-ttu-id="f20d5-272">Installation</span><span class="sxs-lookup"><span data-stu-id="f20d5-272">Installation</span></span>

<div>

## <a name="using-non-ascii-characters-may-result-in-lync-server-failing-to-start"></a><span data-ttu-id="f20d5-273">Das Verwenden von nicht-ASCII-Zeichen kann dazu führen, dass lync Server nicht gestartet wird</span><span class="sxs-lookup"><span data-stu-id="f20d5-273">Using non-ASCII characters may result in Lync server failing to start</span></span>

<span data-ttu-id="f20d5-274">**Problem**</span><span class="sxs-lookup"><span data-stu-id="f20d5-274">**Issue:**</span></span>

<span data-ttu-id="f20d5-275">Das Setup schlägt fehl, wenn der Name des Zielordners nicht-ASCII-Zeichen enthält (einschließlich Unicode, Doppelbyte-Zeichensatz (DBCS), UTF-8 und UTF-16).</span><span class="sxs-lookup"><span data-stu-id="f20d5-275">Setup will fail if the destination folder name includes non-ASCII characters (including UNICODE, double-byte character set (DBCS), UTF-8, and UTF-16).</span></span> <span data-ttu-id="f20d5-276">Darüber hinaus kann Setup erfolgreich ausgeführt werden, aber der Server wird nicht gestartet, wenn in einem der folgenden nicht-ASCII-Zeichen enthalten sind:</span><span class="sxs-lookup"><span data-stu-id="f20d5-276">In addition, Setup may succeed but the server will not start if non-ASCII characters are contained in any of the following:</span></span>

  - <span data-ttu-id="f20d5-277">Name des Computers</span><span class="sxs-lookup"><span data-stu-id="f20d5-277">Computer name</span></span>

  - <span data-ttu-id="f20d5-278">Domänenname</span><span class="sxs-lookup"><span data-stu-id="f20d5-278">Domain name</span></span>

  - <span data-ttu-id="f20d5-279">Benutzername</span><span class="sxs-lookup"><span data-stu-id="f20d5-279">User name</span></span>

  - <span data-ttu-id="f20d5-280">SIP-URI des Benutzers</span><span class="sxs-lookup"><span data-stu-id="f20d5-280">User SIP URI</span></span>

  - <span data-ttu-id="f20d5-281">Dienstkontoname</span><span class="sxs-lookup"><span data-stu-id="f20d5-281">Service account name</span></span>

<span data-ttu-id="f20d5-282">**Problemumgehung**</span><span class="sxs-lookup"><span data-stu-id="f20d5-282">**Workaround:**</span></span>

<span data-ttu-id="f20d5-283">Verwenden Sie nur ASCII-Zeichen im Namen des Zielordners, des Computernamens, des Domänennamens, des Benutzernamens, des SIP-URI des Benutzers und der Dienstkontonamen.</span><span class="sxs-lookup"><span data-stu-id="f20d5-283">Use only ASCII characters in the destination folder name, computer name, domain name, user name, user SIP URI, and service account names.</span></span>

</div>

<div>

## <a name="the-hotfix-for-heap-corruption-occurs-when-a-module-calls-the-insertentitybody-method-in-iis-75-must-be-installed-prior-to-installing-lync-server-2013"></a><span data-ttu-id="f20d5-284">Der Hotfix für "Heap Beschädigung tritt auf, wenn ein Modul ruft die InsertEntityBody-Methode in IIS 7,5" muss vor der Installation von lync Server 2013 installiert werden</span><span class="sxs-lookup"><span data-stu-id="f20d5-284">The hotfix for "Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5" must be installed prior to installing Lync Server 2013</span></span>

<span data-ttu-id="f20d5-285">**Problem**</span><span class="sxs-lookup"><span data-stu-id="f20d5-285">**Issue:**</span></span>

<span data-ttu-id="f20d5-286">Der Hotfix für "Heap Beschädigung tritt auf, wenn ein Modul die InsertEntityBody-Methode in IIS 7,5[https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)" () aufruft, die im Microsoft Knowledge[https://go.microsoft.com/fwlink/p/?LinkId=268603](https://go.microsoft.com/fwlink/p/?linkid=268603)Base-Artikel 264886 () beschrieben wird, muss vor der Installation von lync Server 2013 installiert werden.</span><span class="sxs-lookup"><span data-stu-id="f20d5-286">The hotfix for "Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5" ([https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)), described in Microsoft Knowledge Base article 264886 ([https://go.microsoft.com/fwlink/p/?LinkId=268603](https://go.microsoft.com/fwlink/p/?linkid=268603)), must be installed prior to installing Lync Server 2013.</span></span>

<span data-ttu-id="f20d5-287">**Problemumgehung**</span><span class="sxs-lookup"><span data-stu-id="f20d5-287">**Workaround:**</span></span>

<span data-ttu-id="f20d5-288">Laden Sie das Hotfix aus dem Microsoft Download Center unter [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)herunter, und installieren Sie es.</span><span class="sxs-lookup"><span data-stu-id="f20d5-288">Download and install the hotfix from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602).</span></span>

</div>

<div>

## <a name="lync-server-2013-fails-to-install-on-ita-windows-server-2012-os-rtm-version"></a><span data-ttu-id="f20d5-289">Lync Server 2013 kann nicht auf ITA-Windows Server 2012 OS RTM-Version installiert werden</span><span class="sxs-lookup"><span data-stu-id="f20d5-289">Lync Server 2013 fails to install on ITA Windows Server 2012 OS RTM version</span></span>

<span data-ttu-id="f20d5-290">**Problem**</span><span class="sxs-lookup"><span data-stu-id="f20d5-290">**Issue:**</span></span>

<span data-ttu-id="f20d5-291">Lync Server 2013 Installation schlägt auf ITA-Windows Server 2012 fehl, da Windows Fabric-Installation fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="f20d5-291">Lync Server 2013 installation fails on ITA Windows Server 2012 due to Windows Fabric installation failing.</span></span>

<span data-ttu-id="f20d5-p128">Die Windows Fabric-Installation ist fehlerhaft, weil Fabric-Ablaufverfolgunge im Zeitformat "HH:MM:SS" erstellt werden. Das Zeitformat in ITA Windows Server lautet jedoch "HH.MM.SS".</span><span class="sxs-lookup"><span data-stu-id="f20d5-p128">Windows Fabric installation fails because fabric traces are created with the time format of HH:MM:SS. However, in ITA Windows Server, the time format is HH.MM.SS.</span></span>

<span data-ttu-id="f20d5-294">**Problemumgehung**</span><span class="sxs-lookup"><span data-stu-id="f20d5-294">**Workaround:**</span></span>

<span data-ttu-id="f20d5-295">Um dieses Problem zu umgehen, aktualisieren Sie die Systemregistrierung, bevor Sie lync Server 2013 installieren.</span><span class="sxs-lookup"><span data-stu-id="f20d5-295">To work around this issue, update the system registry before installing Lync Server 2013.</span></span> <span data-ttu-id="f20d5-296">Der Registrierungsschlüssel, der aktualisiert werden muss, lautet:\_HKEY\\-Benutzer. Standard\\mäßige\\System\\Steuerung internationale sTimeFormat.</span><span class="sxs-lookup"><span data-stu-id="f20d5-296">The registry key that needs to be updated is: HKEY\_USERS\\.DEFAULT\\Control Panel\\International\\sTimeFormat.</span></span> <span data-ttu-id="f20d5-297">Ändern Sie den Wert von sTimeFormat in hh: mm: SS, indem Sie die Befehlszeilenschnittstelle Windows PowerShell wie folgt verwenden:</span><span class="sxs-lookup"><span data-stu-id="f20d5-297">Change the value of sTimeFormat to HH:mm:ss by using the Windows PowerShell command-line interface as follows:</span></span>

1.  <span data-ttu-id="f20d5-298">Starten Sie Windows PowerShell, und führen Sie die folgenden Cmdlets aus:</span><span class="sxs-lookup"><span data-stu-id="f20d5-298">Start Windows PowerShell and run the following cmdlets:</span></span>
    
       ```PowerShell
        New-PSDrive -Name HKU -PSProvider Registry -Root HKEY_USERS
       ```
    
       ```PowerShell
        $a="HKU:\.Default\Control Panel\International"
       ```

2.  <span data-ttu-id="f20d5-299">Führen Sie zum Anzeigen des aktuellen Werts das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="f20d5-299">To view the current value, run the following cmdlet:</span></span>
    
        Get-itemproperty $a -Name sTimeFormat
    
    <span data-ttu-id="f20d5-300">Notieren Sie den aktuellen Wert für "sTimeFormat", sodass er nach Abschluss der Installation wiederhergestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="f20d5-300">Make note of the current value for sTimeFormat so it can be restored after the installation is complete.</span></span>

3.  <span data-ttu-id="f20d5-301">Führen Sie zum Festlegen auf den neuen Wert das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="f20d5-301">To set to new value, run the following cmdlet:</span></span>
    
        Set-ItemProperty $a -Name sTimeFormat -Value "HH:mm:ss"

4.  <span data-ttu-id="f20d5-302">Nachdem lync Server 2013 erfolgreich installiert wurde, stellen Sie den ursprünglichen Wert für das sTimeFormat-Objekt wieder her, indem Sie das folgende Cmdlet ausführen:</span><span class="sxs-lookup"><span data-stu-id="f20d5-302">After Lync Server 2013 has been successfully installed, restore the original value for the sTimeFormat by running the following cmdlet:</span></span>
    
        - <span data-ttu-id="f20d5-303">Festlegen-ItemProperty $a-Name sTimeFormat-Wert "<Wert, der in Schritt 3 notiert wurde.</span><span class="sxs-lookup"><span data-stu-id="f20d5-303">Set-ItemProperty $a -Name sTimeFormat -Value "<Value noted down in Step 3.</span></span> <span data-ttu-id="f20d5-304">oberhalb> "</span><span class="sxs-lookup"><span data-stu-id="f20d5-304">above>"</span></span>

</div>

</div>

<span id="Mobility"></span>

<div>

## <a name="mobility"></a><span data-ttu-id="f20d5-305">Mobilität</span><span class="sxs-lookup"><span data-stu-id="f20d5-305">Mobility</span></span>

<div>

## <a name="issues-for-mobile-clients-during-the-server-failover-process"></a><span data-ttu-id="f20d5-306">Probleme für mobile Clients während des Server Failover-Prozesses</span><span class="sxs-lookup"><span data-stu-id="f20d5-306">Issues for mobile clients during the server failover process</span></span>

<span data-ttu-id="f20d5-307">**Problem**</span><span class="sxs-lookup"><span data-stu-id="f20d5-307">**Issue:**</span></span>

<span data-ttu-id="f20d5-308">Wenn ein lync Server fehlschlägt und der Failoverprozess beginnt, können sich die folgenden Probleme auf Mobile Client-Benutzer auswirken:</span><span class="sxs-lookup"><span data-stu-id="f20d5-308">When a Lync Server fails and the failover process begins, the following issues may affect mobile client users:</span></span>

  - <span data-ttu-id="f20d5-309">Kein eingehender lync-Anruf oder Signal für bis zu 10 Minuten nach dem Start des Failovers.</span><span class="sxs-lookup"><span data-stu-id="f20d5-309">No incoming Lync call or signal for up to 10 minutes after failover begins.</span></span>

  - <span data-ttu-id="f20d5-310">Eingehende Chat Anforderungen können nicht akzeptiert werden</span><span class="sxs-lookup"><span data-stu-id="f20d5-310">Cannot accept incoming Chat requests</span></span>

  - <span data-ttu-id="f20d5-311">Kann nicht an Besprechungen teilnehmen, wenn der fehlerhafte Server der Stammserver für den Benutzer ist</span><span class="sxs-lookup"><span data-stu-id="f20d5-311">Cannot join meetings if the failed server is the home server for the user</span></span>

<span data-ttu-id="f20d5-312">**Problemumgehung**</span><span class="sxs-lookup"><span data-stu-id="f20d5-312">**Workaround:**</span></span>

<span data-ttu-id="f20d5-313">Das Problem kann nicht umgangen werden.</span><span class="sxs-lookup"><span data-stu-id="f20d5-313">There is no workaround for this issue.</span></span> <span data-ttu-id="f20d5-314">Die normale Funktionalität wird nach Abschluss des Failover-Prozesses wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="f20d5-314">Normal functionality will be restored once the failover process is complete.</span></span>

</div>

<div>

## <a name="if-a-mobile-user-declines-an-incoming-call-from-another-lync-endpoint-the-call-is-displayed-as-a-missed-conversion-on-lync-mobile-clients"></a><span data-ttu-id="f20d5-315">Wenn ein mobiler Benutzer einen eingehenden Anruf von einem anderen lync-Endpunkt ablehnt, wird der Anruf als verpasste Konvertierung für lync Mobile-Clients angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f20d5-315">If a mobile user declines an incoming call from another Lync endpoint, the call is displayed as a missed conversion on Lync Mobile clients</span></span>

<span data-ttu-id="f20d5-316">**Problem**</span><span class="sxs-lookup"><span data-stu-id="f20d5-316">**Issue:**</span></span>

<span data-ttu-id="f20d5-317">Wenn ein mobiler Benutzer einen eingehenden Anruf ablehnt und der Anruf von einem anderen lync-Endpunkt stammt, wird der Anruf im lync Mobile-Client anstelle eines Anrufs in der Geräte Anrufliste als verpasste Unterhaltung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f20d5-317">If a mobile user declines an incoming call, and the call originated from another Lync endpoint, the call is displayed as a missed conversation in the Lync Mobile client instead of a call in the device call list.</span></span>

<span data-ttu-id="f20d5-318">**Problemumgehung**</span><span class="sxs-lookup"><span data-stu-id="f20d5-318">**Workaround:**</span></span>

<span data-ttu-id="f20d5-319">Das Problem kann nicht umgangen werden.</span><span class="sxs-lookup"><span data-stu-id="f20d5-319">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="the-mobile-client-may-not-display-a-federated-contacts-display-name-when-searching-for-contacts"></a><span data-ttu-id="f20d5-320">Der Anzeigename eines verbundenen Kontakts wird beim Suchen nach Kontakten vom mobilen Client möglicherweise nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f20d5-320">The mobile client may not display a federated contact’s display name when searching for contacts</span></span>

<span data-ttu-id="f20d5-321">**Problem**</span><span class="sxs-lookup"><span data-stu-id="f20d5-321">**Issue:**</span></span>

<span data-ttu-id="f20d5-322">Der Anzeigename für Partnerverbund Kontakte wird in einigen Szenarien möglicherweise nicht angezeigt, beispielsweise bei der Suche nach einem Verbundkontakt in der Kontaktliste.</span><span class="sxs-lookup"><span data-stu-id="f20d5-322">The display name for federated contacts may not be displayed in some scenarios, such as when searching for a federated contact in the contact list.</span></span> <span data-ttu-id="f20d5-323">Dies kann auftreten, wenn das aktive Anwesenheits Abonnement für den Kontakt vom mobilen lync-Client nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="f20d5-323">This can occur when the there is no active presence subscription for the contact from the Lync mobile client.</span></span>

<span data-ttu-id="f20d5-324">**Problemumgehung**</span><span class="sxs-lookup"><span data-stu-id="f20d5-324">**Workaround:**</span></span>

<span data-ttu-id="f20d5-325">Das Problem kann nicht umgangen werden.</span><span class="sxs-lookup"><span data-stu-id="f20d5-325">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="in-the-mobile-client-invitee-and-timestamp-information-are-missing-from-a-missed-conversation-that-is-an-invitation-to-a-conference"></a><span data-ttu-id="f20d5-326">Im mobilen Client fehlen die Informationen zum einladen und zum Zeitstempel bei einer verpassten Unterhaltung, die eine Einladung zu einer Konferenz darstellt.</span><span class="sxs-lookup"><span data-stu-id="f20d5-326">In the mobile client, invitee and timestamp information are missing from a missed conversation that is an invitation to a conference</span></span>

<span data-ttu-id="f20d5-327">**Problem**</span><span class="sxs-lookup"><span data-stu-id="f20d5-327">**Issue:**</span></span>

<span data-ttu-id="f20d5-328">Wenn im mobilen Client eine verpasste Unterhaltung eine Einladung zu einer Konferenz ist, fehlen die Informationen zum einladen und zum Zeitstempel in der Nachricht verpasste Unterhaltung.</span><span class="sxs-lookup"><span data-stu-id="f20d5-328">In the mobile client, when a missed conversation is an invitation to a conference, the invitee and timestamp information is missing from the missed conversation message.</span></span>

<span data-ttu-id="f20d5-329">**Problemumgehung**</span><span class="sxs-lookup"><span data-stu-id="f20d5-329">**Workaround:**</span></span>

<span data-ttu-id="f20d5-330">Das Problem kann nicht umgangen werden.</span><span class="sxs-lookup"><span data-stu-id="f20d5-330">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="mobile-client-users-making-calls-using-voip-are-not-be-able-to-leave-voice-mail-for-users-whose-voice-mail-is-configured-in-exchange-2010-or-earlier-versions"></a><span data-ttu-id="f20d5-331">Benutzer von Mobiltelefonen, die VoIP-Anrufe tätigen, können Voicemail für Benutzer, deren Voicemail in Exchange 2010 oder früheren Versionen konfiguriert ist, nicht mehr hinterlassen.</span><span class="sxs-lookup"><span data-stu-id="f20d5-331">Mobile client users making calls using VoIP are not be able to leave voice mail for users whose voice mail is configured in Exchange 2010 or earlier versions</span></span>

<span data-ttu-id="f20d5-332">**Problem**</span><span class="sxs-lookup"><span data-stu-id="f20d5-332">**Issue:**</span></span>

<span data-ttu-id="f20d5-333">Wenn ein mobiler Client-Benutzer VoIP zum Platzieren von Anrufen verwendet, kann der Benutzer keine Voicemail-Nachrichten für Benutzer, die für die Verwendung von Voicemail in Microsoft Exchange Server 2007 oder Microsoft Exchange Server 2010 konfiguriert sind, hinterlassen.</span><span class="sxs-lookup"><span data-stu-id="f20d5-333">If a mobile client user is using VoIP to place calls, the user will not be able to leave voice mail messages for users configured to use voice mail in Microsoft Exchange Server 2007 or Microsoft Exchange Server 2010.</span></span>

<span data-ttu-id="f20d5-334">**Problemumgehung**</span><span class="sxs-lookup"><span data-stu-id="f20d5-334">**Workaround:**</span></span>

<span data-ttu-id="f20d5-335">Um dieses Problem zu umgehen, verwenden Sie Exchange 2010 mit SP1 oder einer höheren Version von Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="f20d5-335">To work around this issue, use Exchange 2010 with SP1 or later version of Microsoft Exchange Server.</span></span>

</div>

<div>

## <a name="when-using-block-with-url-for-client-version-configuration-on-mobile-clients-an-incorrect-error-message-may-be-displayed"></a><span data-ttu-id="f20d5-336">Bei Verwendung von Block mit URL für die Client Versions Konfiguration auf mobilen Clients wird möglicherweise eine falsche Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f20d5-336">When using Block with URL for Client Version Configuration on mobile clients, an incorrect error message may be displayed</span></span>

<span data-ttu-id="f20d5-337">**Problem**</span><span class="sxs-lookup"><span data-stu-id="f20d5-337">**Issue:**</span></span>

<span data-ttu-id="f20d5-338">Bei Verwendung von **Block mit URL** für die Client Versions Konfiguration auf mobilen Clients wird möglicherweise eine falsche Fehlermeldung angezeigt, wenn die Client Version nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="f20d5-338">When using **Block with URL** for Client Version Configuration on mobile clients, an incorrect error message may be displayed when the client version is not supported.</span></span>

<span data-ttu-id="f20d5-339">**Problemumgehung**</span><span class="sxs-lookup"><span data-stu-id="f20d5-339">**Workaround:**</span></span>

<span data-ttu-id="f20d5-340">Um dieses Problem zu umgehen, konfigurieren Sie die Client Versions Konfiguration so, dass **Block** anstelle von **Block mit URL**verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f20d5-340">To work around this issue, configure Client Version Configuration to use **Block** instead of **Block with URL**.</span></span>

</div>

</div>

<span id="Conferencing"></span>

<div>

## <a name="conferencing"></a><span data-ttu-id="f20d5-341">Konferenzen</span><span class="sxs-lookup"><span data-stu-id="f20d5-341">Conferencing</span></span>

<div>

## <a name="antivirus-software-running-on-lync-server-2013front-end-servers-can-cause-application-domain-recycling-which-temporarily-interrupts-service-for-lync-web-app-2013-lync-mobile-2010-and-lync-mobile-2013-clients"></a><span data-ttu-id="f20d5-342">Antivirensoftware, die auf lync Server 2013-Front-End-Servern läuft, kann eine Wiederverwendung der Anwendungsdomäne verursachen, wodurch der Dienst für lync Web App 2013-, lync Mobile 2010-und lync Mobile 2013-Clients vorübergehend unterbrochen wird.</span><span class="sxs-lookup"><span data-stu-id="f20d5-342">Antivirus software running on Lync Server 2013 Front End Servers can cause Application Domain recycling, which temporarily interrupts service for Lync Web App 2013, Lync Mobile 2010, and Lync Mobile 2013 clients</span></span>

<span data-ttu-id="f20d5-343">**Problem**</span><span class="sxs-lookup"><span data-stu-id="f20d5-343">**Issue:**</span></span>

<span data-ttu-id="f20d5-344">Antivirensoftware kann Anwendungsdomänen Neustarts auslösen, was dazu führen kann, dass lync Mobility Service 2013 und Unified Communications (UC)-WebAPI-Clientanwendungen (lync Web App 2013, lync Mobile 2010 und lync Mobile 2013) ihren Status verlieren.</span><span class="sxs-lookup"><span data-stu-id="f20d5-344">Antivirus software can trigger application domain restarts, which can result in Lync Mobility Service 2013 and unified communications (UC) Web API client applications (Lync Web App 2013, Lync Mobile 2010, and Lync Mobile 2013) to lose their state.</span></span>

<span data-ttu-id="f20d5-345">**Problemumgehung**</span><span class="sxs-lookup"><span data-stu-id="f20d5-345">**Workaround:**</span></span>

<span data-ttu-id="f20d5-346">Wenn Sie dieses Problem umgehen möchten, schließen Sie die Ordner mit Webkomponenten und .NET Framework aus dem Virenschutzprogramm aus.</span><span class="sxs-lookup"><span data-stu-id="f20d5-346">To work around this issue, exclude the folders containing Web components and .NET framework from antivirus scanning.</span></span> <span data-ttu-id="f20d5-347">Ausführliche Informationen finden Sie im Microsoft Knowledge Base-Artikel 312592, "PRB: zufällige Anwendungsneustarts mit" Anwendung ist ein Neustart "Error in ASP.net" unter [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=312592](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=312592).</span><span class="sxs-lookup"><span data-stu-id="f20d5-347">For details, see Microsoft Knowledge Base article 312592, "PRB: Random application restarts with 'Application is restarting' error in ASP.NET," at [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=312592](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=312592).</span></span>

<span data-ttu-id="f20d5-348">Die folgenden Ordner sollten ausgeschlossen werden:</span><span class="sxs-lookup"><span data-stu-id="f20d5-348">The following folders should be excluded:</span></span>

  - <span data-ttu-id="f20d5-349">% Programme%\\Microsoft lync Server 2013\\-\\Webkomponenten\\MCX ext</span><span class="sxs-lookup"><span data-stu-id="f20d5-349">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Mcx\\Ext</span></span>

  - <span data-ttu-id="f20d5-350">% Programme%\\Microsoft lync Server 2013\\-\\Webkomponenten\\MCX int</span><span class="sxs-lookup"><span data-stu-id="f20d5-350">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Mcx\\Int</span></span>

  - <span data-ttu-id="f20d5-351">% Programme%\\Microsoft lync Server 2013\\-\\Webkomponenten\\Ucwa int</span><span class="sxs-lookup"><span data-stu-id="f20d5-351">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Ucwa\\Int</span></span>

  - <span data-ttu-id="f20d5-352">% Programme%\\Microsoft lync Server 2013\\-\\Webkomponenten\\Ucwa ext</span><span class="sxs-lookup"><span data-stu-id="f20d5-352">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Ucwa\\Ext</span></span>

  - <span data-ttu-id="f20d5-353">% Windir%\\Microsoft.net\\Framework64\\v 4.0.30319\\config</span><span class="sxs-lookup"><span data-stu-id="f20d5-353">%Windir%\\Microsoft.NET\\Framework64\\v4.0.30319\\Config</span></span>

</div>

<div>

## <a name="activex-controls-or-native-xmlhttp-support-must-be-enabled-in-windows-internet-explorer-to-successfully-join-conferences"></a><span data-ttu-id="f20d5-354">ActiveX-Steuerelemente oder systemeigene XMLHTTP-Unterstützung müssen in Windows Internet Explorer aktiviert werden, um Konferenzen erfolgreich beizutreten.</span><span class="sxs-lookup"><span data-stu-id="f20d5-354">ActiveX Controls or native XMLHTTP support must be enabled in Windows Internet Explorer to successfully join conferences</span></span>

<span data-ttu-id="f20d5-355">**Problem**</span><span class="sxs-lookup"><span data-stu-id="f20d5-355">**Issue:**</span></span>

<span data-ttu-id="f20d5-356">Wenn ein Benutzer ActiveX-Steuerelemente und die systemeigene XMLHTTP-Unterstützung in den Internetbrowsereinstellungen von Windows Internet Explorer deaktiviert hat, kann der Benutzer keiner Besprechung beitreten, falls Internet Explorer als Standardbrowser ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="f20d5-356">If a user has disabled both ActiveX Controls and native XMLHTTP support in Windows Internet Explorer Internet browser settings, the user will not be able to join a meeting if Internet Explorer is selected as the default browser.</span></span>

<span data-ttu-id="f20d5-357">**Problemumgehung**</span><span class="sxs-lookup"><span data-stu-id="f20d5-357">**Workaround:**</span></span>

<span data-ttu-id="f20d5-358">Aktivieren Sie in Internet Explorer ActiveX-Steuerelemente oder die "systemeigene XMLHTTP-Unterstützung".</span><span class="sxs-lookup"><span data-stu-id="f20d5-358">Enable either ActiveX Controls or "native XMLHTTP support" in Internet Explorer.</span></span>

</div>

<div>

## <a name="lync-server-web-conferencing-service-cannot-recover-from-critical-mode"></a><span data-ttu-id="f20d5-359">Lync Server Webkonferenzdienst kann nicht im kritischen Modus wiederhergestellt werden</span><span class="sxs-lookup"><span data-stu-id="f20d5-359">Lync Server Web Conferencing service cannot recover from critical mode</span></span>

<span data-ttu-id="f20d5-360">**Problem**</span><span class="sxs-lookup"><span data-stu-id="f20d5-360">**Issue:**</span></span>

<span data-ttu-id="f20d5-p134">Wenn der kritische Modus zur Archivierung aktiviert ist, startet der kritische Modus im Falle eines Systemausfalls, und die Konferenz ist für die Teilnehmer nicht mehr zugänglich. Nachdem der Administrator die Systemausfälle behoben hat (beispielsweise ein Datenbankproblem), wird der Datenkonferenzdienst nicht automatisch wiederhergestellt, und der Administrator muss den Konferenzdienst zum Fortsetzen der Konferenz manuell neu starten.</span><span class="sxs-lookup"><span data-stu-id="f20d5-p134">If critical mode is turned for archiving, in case of system failures, critical mode will start and the conferences will no longer work for the participants. After the administrator fixes the system failures (such as fixing a database issue), the data conferencing service doesn't automatically recover, and the administrator must manually restart the conferencing service for conferencing to resume.</span></span>

<span data-ttu-id="f20d5-363">**Problemumgehung**</span><span class="sxs-lookup"><span data-stu-id="f20d5-363">**Workaround:**</span></span>

<span data-ttu-id="f20d5-364">Ein Administrator muss den Konferenzdienst manuell neu starten, nachem der Systemausfall behoben wurde.</span><span class="sxs-lookup"><span data-stu-id="f20d5-364">An administrator needs to manually restart the conferencing service after the system failure is fixed.</span></span>

</div>

<div>

## <a name="web-conferencing-service-ignores-the-http-proxy-for-external-office-web-app-servers"></a><span data-ttu-id="f20d5-365">Webkonferenzdienst ignoriert den HTTP-Proxy für externe Office-Webanwendungsserver</span><span class="sxs-lookup"><span data-stu-id="f20d5-365">Web Conferencing service ignores the HTTP proxy for external Office Web App Servers</span></span>

<span data-ttu-id="f20d5-366">**Problem**</span><span class="sxs-lookup"><span data-stu-id="f20d5-366">**Issue:**</span></span>

<span data-ttu-id="f20d5-367">Wenn Sie einen Office Web Apps-Server außerhalb des Webkonferenzdienst bereitgestellt haben (also ein Server, der sich nicht im internen Unternehmensnetzwerk befindet) im Internet, Umkreisnetzwerk und der Webkonferenzdienst ein HTTP-Proxy erfordert, um eine Verbindung mit diesem herzustellen, wird der Die Office-webapps-Server Ermittlung schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="f20d5-367">If you have deployed an Office Web Apps Server external to the Web Conferencing service (that is, a server that is not in the internal corporate network) in the Internet, perimeter network, and the Web Conferencing service requires an HTTP proxy to connect to this, the Office Web Apps Server discovery will fail.</span></span> <span data-ttu-id="f20d5-368">Im Webkonferenzdienst wird die http-Proxyeinstellung ignoriert, wie im Topologie-Generator für Office-webapps-Server Setup definiert.</span><span class="sxs-lookup"><span data-stu-id="f20d5-368">The Web Conferencing service ignores the HTTP proxy setting, as defined in Topology Builder for Office Web Apps Server setup.</span></span> <span data-ttu-id="f20d5-369">Daher kann der lync-Client Microsoft PowerPoint 2010 Freigabe für andere Teilnehmer an der Konferenz nicht durchführen.</span><span class="sxs-lookup"><span data-stu-id="f20d5-369">As a result, the Lync client will not be able to do Microsoft PowerPoint 2010 sharing with other participants in the conference.</span></span> <span data-ttu-id="f20d5-370">Wenn Sie lync Server lokal installieren und außerdem Office-webapps Server lokal im internen Netzwerk konfigurieren, ist keine Proxykonfiguration erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f20d5-370">If you are installing Lync Server on-premises and also configure Office Web Apps Server on-premises in the internal network, a proxy configuration is not required.</span></span>

<span data-ttu-id="f20d5-371">**Problemumgehung**</span><span class="sxs-lookup"><span data-stu-id="f20d5-371">**Workaround:**</span></span>

<span data-ttu-id="f20d5-372">Die einzige Problemumgehung besteht darin, dass keine Bereitstellungskonfiguration vorliegt, bei der die Verwendung des HTTP-Proxys für die Kommunikation mit einem externen Office-webapps-Server erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="f20d5-372">The only workaround is to not have a deployment configuration that requires the use of HTTP proxy to communicate with an external Office Web Apps Server.</span></span>

</div>

<div>

## <a name="adding-video-to-an-audio-conferencing-provider-conference-is-not-supported"></a><span data-ttu-id="f20d5-373">Das Hinzufügen von Video zu einer Konferenz für einen Audiokonferenz-Anbieter wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="f20d5-373">Adding video to an audio conferencing provider conference is not supported</span></span>

<span data-ttu-id="f20d5-374">**Problem**</span><span class="sxs-lookup"><span data-stu-id="f20d5-374">**Issue:**</span></span>

<span data-ttu-id="f20d5-375">Das Hinzufügen eines Videos wird nicht unterstützt, wenn der Benutzer einer Audiokonferenz eines Audiokonferenzanbieters beitritt.</span><span class="sxs-lookup"><span data-stu-id="f20d5-375">Adding a video is not supported if the user is joined to an audio conferencing provider conference for audio.</span></span>

<span data-ttu-id="f20d5-376">**Problemumgehung**</span><span class="sxs-lookup"><span data-stu-id="f20d5-376">**Workaround:**</span></span>

<span data-ttu-id="f20d5-377">Das Problem kann nicht umgangen werden.</span><span class="sxs-lookup"><span data-stu-id="f20d5-377">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="topologies-with-ipv6-enabled-force-the-lync-web-app-silverlight-plug-in-auto-update-to-ensure-screen-sharing-functionality-can-work-from-lync-web-app"></a><span data-ttu-id="f20d5-378">Topologien mit aktivierter IPv6 erzwingen, dass die lync Web App Silverlight-Plug-in automatisch aktualisiert wird, um sicherzustellen, dass die Bildschirmfreigabe Funktion in lync Web App funktioniert.</span><span class="sxs-lookup"><span data-stu-id="f20d5-378">Topologies with IPv6 enabled force the Lync Web App Silverlight plug-in auto-update to ensure screen sharing functionality can work from Lync Web App</span></span>

<span data-ttu-id="f20d5-379">**Problem**</span><span class="sxs-lookup"><span data-stu-id="f20d5-379">**Issue:**</span></span>

<span data-ttu-id="f20d5-380">Wenn eine Topologie mit aktiviertem IPv6 konfiguriert ist, können Benutzer Ihren Bildschirm nicht über den lync Web App-Client freigeben, wenn bereits eine frühere Version des Plug-Ins für die Bildschirmfreigabe installiert ist.</span><span class="sxs-lookup"><span data-stu-id="f20d5-380">When a topology is configured with IPv6 enabled, users cannot share their screen from the Lync Web App client if an earlier version of the screen-sharing plug-in is already installed.</span></span>

<span data-ttu-id="f20d5-381">**Problemumgehung**</span><span class="sxs-lookup"><span data-stu-id="f20d5-381">**Workaround:**</span></span>

<span data-ttu-id="f20d5-382">Wenn Sie eine Aktualisierung der neuesten Version des Plug-Ins für die Bildschirmfreigabe beim Beitritt zur Besprechung über lync Web App erzwingen möchten, ändern Sie den Wert von **MinSupportedBuildVersion** von "4.0.7457.0" in "4.0.7577.380" in den beiden folgenden Dateien:</span><span class="sxs-lookup"><span data-stu-id="f20d5-382">To force an update to the most recent version of the screen-sharing plug-in when joining meeting via Lync Web App, modify the value of **MinSupportedBuildVersion** from "4.0.7457.0" to "4.0.7577.380" in both of the following files:</span></span>

  - <span data-ttu-id="f20d5-383">% Programme%\\Microsoft lync Server 15\\-\\Webkomponenten\\erreichen\\int\\-\\Client-Plugins ReachAppShPluginProperties. XML</span><span class="sxs-lookup"><span data-stu-id="f20d5-383">%ProgramFiles%\\Microsoft Lync Server 15\\Web Components\\Reach\\Int\\Client\\Plugins\\ReachAppShPluginProperties.xml</span></span>

  - <span data-ttu-id="f20d5-384">% Programme%\\Microsoft lync Server 15\\-\\Webkomponenten\\erreichen\\Ext\\-\\Client-Plugins ReachAppShPluginProperties. XML</span><span class="sxs-lookup"><span data-stu-id="f20d5-384">%ProgramFiles%\\Microsoft Lync Server 15\\Web Components\\Reach\\Ext\\Client\\Plugins\\ReachAppShPluginProperties.xml</span></span>

</div>

</div>

<span id="EnterpriseVoice"></span>

<div>

## <a name="enterprise-voice"></a><span data-ttu-id="f20d5-385">Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="f20d5-385">Enterprise Voice</span></span>

<div>

## <a name="in-some-cases-a-lync-client-running-on-a-computer-configured-to-use-ipv4-and-ipv6-dual-stack-might-not-support-capabilities-that-rely-in-the-ip-subnet-of-the-computer-such-as-e911-media-bypass-call-admission-control-and-location-based-routing"></a><span data-ttu-id="f20d5-386">In einigen Fällen unterstützt ein lync-Client auf einem Computer, der für die Verwendung von IPv4-und IPv6-dualen Stapeln konfiguriert ist, möglicherweise keine Funktionen, die im IP-Subnetz des Computers wie E911, medienumgehung, Anrufsteuerung und Standort basiertem Routing basieren.</span><span class="sxs-lookup"><span data-stu-id="f20d5-386">In some cases, a Lync client running on a computer configured to use IPv4 and IPv6 dual stack might not support capabilities that rely in the IP subnet of the computer such as E911, Media Bypass, Call Admission Control and Location Based Routing</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="f20d5-387">Die Informationen in diesem Abschnitt beziehen sich auf kumulative Updates für lync Server 2013: Februar 2013.</span><span class="sxs-lookup"><span data-stu-id="f20d5-387">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="f20d5-388">**Problem**</span><span class="sxs-lookup"><span data-stu-id="f20d5-388">**Issue:**</span></span>

<span data-ttu-id="f20d5-389">Wenn ein lync-Client auf einem Computer läuft, der für IPv4 und IPv6 Dual Stack aktiviert ist, und basierend auf der DNS-Auflösung des Proxyservers, kann der Client die IPv6-Adresse des Computers zur Anmeldung verwenden.</span><span class="sxs-lookup"><span data-stu-id="f20d5-389">When a Lync client is running on a computer that is enabled for IPv4 and IPv6 dual stack and based on the DNS resolution of the proxy server, the client may use the IPv6 address of the computer to sign in.</span></span> <span data-ttu-id="f20d5-390">Anschließend unterstützt der lync-Client nur die für IPv6 unterstützten Funktionen, die E911, medienumgehung, Anrufsteuerung und standortbasiertes Routing ausschließen.</span><span class="sxs-lookup"><span data-stu-id="f20d5-390">After doing so, the Lync Client will support only the capabilities supported for IPv6, which excludes E911, Media Bypass, Call Admission Control and Location Based Routing.</span></span>

<span data-ttu-id="f20d5-391">**Problemumgehung**</span><span class="sxs-lookup"><span data-stu-id="f20d5-391">**Workaround:**</span></span>

<span data-ttu-id="f20d5-392">Um dieses Problem zu umgehen, deaktivieren Sie die IPv6-Unterstützung auf dem Clientcomputer.</span><span class="sxs-lookup"><span data-stu-id="f20d5-392">To work around this issue, disable IPv6 support on the client computer.</span></span>

</div>

<div>

## <a name="if-enterprise-voice-is-not-configured-for-a-user-the-user-will-need-to-use-e164-format-to-dial-out-from-a-conference"></a><span data-ttu-id="f20d5-393">Wenn Enterprise-VoIP nicht für einen Benutzer konfiguriert ist, muss der Benutzer das E164-Format verwenden, um sich aus einer Konferenz abzuwählen.</span><span class="sxs-lookup"><span data-stu-id="f20d5-393">If Enterprise Voice is not configured for a user, the user will need to use E164 format to dial out from a conference</span></span>

<span data-ttu-id="f20d5-394">**Problem**</span><span class="sxs-lookup"><span data-stu-id="f20d5-394">**Issue:**</span></span>

<span data-ttu-id="f20d5-395">Wenn Enterprise-VoIP nicht für einen Benutzer konfiguriert ist, muss dieser Benutzer das E164-Format verwenden, um sich erfolgreich aus einer Konferenz auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="f20d5-395">If Enterprise Voice is not configured for a user, that user will need to use the E164 format to successfully dial out from a conference.</span></span> <span data-ttu-id="f20d5-396">Wird das E164-Format nicht verwendet, kann sich der Benutzer nicht aus der Konferenz auswählen.</span><span class="sxs-lookup"><span data-stu-id="f20d5-396">If the E164 format is not used, the user will not be able to dial out from the conference.</span></span>

<span data-ttu-id="f20d5-397">**Problemumgehung**</span><span class="sxs-lookup"><span data-stu-id="f20d5-397">**Workaround:**</span></span>

<span data-ttu-id="f20d5-398">Um dieses Problem zu umgehen, sollten Benutzer, die nicht für Enterprise-VoIP aktiviert sind, aus einer Konferenz wählen, indem Sie zahlen im E164-Format verwenden.</span><span class="sxs-lookup"><span data-stu-id="f20d5-398">To work around this issue, users who are not enabled for Enterprise Voice should dial out from a conference by using numbers in the E164 format.</span></span>

</div>

</div>

<span id="Presence"></span>

<div>

## <a name="presence"></a><span data-ttu-id="f20d5-399">Anwesenheit</span><span class="sxs-lookup"><span data-stu-id="f20d5-399">Presence</span></span>

<div>

## <a name="if-a-user-has-selected-block-all-invites-and-communications-while-the-unified-contact-store-is-turned-on-for-the-user-presence-status-is-not-rejected-when-it-should-be"></a><span data-ttu-id="f20d5-400">Wenn ein Benutzer die Option "alle Einladungen und Kommunikationen blockieren" ausgewählt hat, während der einheitliche Kontaktspeicher für den Benutzer aktiviert ist, wird der Anwesenheitsstatus nicht zurückgewiesen, wenn er</span><span class="sxs-lookup"><span data-stu-id="f20d5-400">If a user has selected "Block all invites and communications" while the unified contact store is turned on for the user, Presence status is not rejected when it should be</span></span>

<span data-ttu-id="f20d5-401">**Problem**</span><span class="sxs-lookup"><span data-stu-id="f20d5-401">**Issue:**</span></span>

<span data-ttu-id="f20d5-402">Wenn ein Benutzer die Option "Alle Einladungen und gesamte Kommunikaktion blockieren" ausgewählt hat, während der einheitliche Kontaktspeicher für den Benutzer aktiviert ist, wird der Anwesenheitsstatus nicht zurückgewiesen, wenn dies der Fall sein sollte.</span><span class="sxs-lookup"><span data-stu-id="f20d5-402">If a user has selected "Block all invites and communications" while the unified contact store is turned on for the user, Presence status is not rejected when it should be.</span></span>

<span data-ttu-id="f20d5-403">**Problemumgehung**</span><span class="sxs-lookup"><span data-stu-id="f20d5-403">**Workaround:**</span></span>

<span data-ttu-id="f20d5-p138">Zur Umgehung dieses Problems können Sie den einheitlichen Kontaktspeicher für den Benutzer deaktivieren. Führen Sie dazu die folgenden Cmdlets aus:</span><span class="sxs-lookup"><span data-stu-id="f20d5-p138">To work around this issue, you can turn off the unified contact store for the user. To do so, run the following cmdlets:</span></span>

    Set-CsUserServicesPolicy -Identity "<user display name>" -UcsAllowed $False

<span data-ttu-id="f20d5-406">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f20d5-406">For example:</span></span>

    Set-CsUserServicesPolicy -Identity "Ken Myer" -UcsAllowed $False

</div>

<div>

## <a name="office-communications-server-2007-r2-users-homed-on-premises-are-not-able-to-see-the-presence-status-of-skype-for-business-online-users-in-hybrid-deployments---hybrid"></a><span data-ttu-id="f20d5-407">Office Communications Server 2007 R2 Benutzer, die lokal verwaltet werden, können den Anwesenheitsstatus von Skype for Business Online Benutzern in hybridbereitstellungen nicht anzeigen – Hybrid</span><span class="sxs-lookup"><span data-stu-id="f20d5-407">Office Communications Server 2007 R2 users homed on-premises are not able to see the Presence status of Skype for Business Online users in hybrid deployments - Hybrid</span></span>

<span data-ttu-id="f20d5-408">**Problem**</span><span class="sxs-lookup"><span data-stu-id="f20d5-408">**Issue:**</span></span>

<span data-ttu-id="f20d5-409">Das Problem kann in einer hybridbereitstellung auftreten, wenn Sie einen lync Server 2013 Director verwenden.</span><span class="sxs-lookup"><span data-stu-id="f20d5-409">The issue may occur in a hybrid deployment when you are using a Lync Server 2013 Director.</span></span>

<span data-ttu-id="f20d5-410">Der Anwesenheitsstatus für Benutzer, die Skype for Business Online verwaltet werden, wird als Anwesenheit unbekannt für lokale Benutzer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f20d5-410">Presence status for users homed to Skype for Business Online is displayed as Presence Unknown for on-premises users.</span></span> <span data-ttu-id="f20d5-411">Außerdem können Benutzer, die Skype for Business Online verwaltet werden, den Anwesenheitsstatus für lokale Benutzer von Office Communications Server R2 nicht sehen.</span><span class="sxs-lookup"><span data-stu-id="f20d5-411">Also, users homed to Skype for Business Online are not able to see presence status for Office Communications Server R2 on-premises users.</span></span>

<span data-ttu-id="f20d5-412">**Problemumgehung**</span><span class="sxs-lookup"><span data-stu-id="f20d5-412">**Workaround:**</span></span>

<span data-ttu-id="f20d5-413">Um dieses Problem teilweise zu umgehen, ändern Sie den Stamm Server (msRTCSIP-presencehomeserver) der Skype for Business Online Benutzer so, dass er auf einen lync Server 2013 lokalen Pool anstatt auf den lync Server 2013 Director zeigt.</span><span class="sxs-lookup"><span data-stu-id="f20d5-413">To partially work around this issue, change the Home Server (msrtcsip-presencehomeserver) of the Skype for Business Online users to point to a Lync Server 2013 on-premises pool instead of the Lync Server 2013 Director.</span></span> <span data-ttu-id="f20d5-414">Sie können diese Einstellung für das lokale Front-End-Server ändern.</span><span class="sxs-lookup"><span data-stu-id="f20d5-414">You can modify this setting on the on-premises Front End Server.</span></span>

<span data-ttu-id="f20d5-415">Diese Problemumgehung zeigt ordnungsgemäß den Anwesenheitsstatus von Benutzern an, die Office Communications Server 2007 R2 für Skype for Business Online Benutzer verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="f20d5-415">This workaround will correctly display the Presence status of users homed to Office Communications Server 2007 R2 to Skype for Business Online users.</span></span>

</div>

</div>

<span id="ResponseGroup"></span>

<div>

## <a name="response-group-application-call-park-application-and-group-call-pickup"></a><span data-ttu-id="f20d5-416">Reaktionsgruppenanwendung, Anwendung zum Parken von Anrufen und gruppenanrufannahme</span><span class="sxs-lookup"><span data-stu-id="f20d5-416">Response Group application, Call Park application, and Group Call Pickup</span></span>

<div>

## <a name="a-caller-might-hear-one-second-of-music-on-hold-during-the-establishment-of-a-call-with-the-retrieving-party"></a><span data-ttu-id="f20d5-417">Ein Anrufer hört möglicherweise eine Sekunde der Wartemusik während der Erstellung eines Anrufs mit dem abrufenden Teilnehmer.</span><span class="sxs-lookup"><span data-stu-id="f20d5-417">A caller might hear one second of music-on-hold during the establishment of a call with the retrieving party</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="f20d5-418">Die Informationen in diesem Abschnitt beziehen sich auf kumulative Updates für lync Server 2013: Februar 2013.</span><span class="sxs-lookup"><span data-stu-id="f20d5-418">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="f20d5-419">**Problem**</span><span class="sxs-lookup"><span data-stu-id="f20d5-419">**Issue:**</span></span>

<span data-ttu-id="f20d5-420">Wenn ein Anruf über die gruppenanrufannahme abgerufen wird, hört der Anrufer möglicherweise eine Sekunde der Wartemusik während der Einrichtung des Anrufs mit dem Retriever-Teilnehmer.</span><span class="sxs-lookup"><span data-stu-id="f20d5-420">When a call is retrieved via Group Call Pickup, the caller might hear one second of music-on-hold during the establishment of the call with the retriever party.</span></span>

<span data-ttu-id="f20d5-421">**Problemumgehung**</span><span class="sxs-lookup"><span data-stu-id="f20d5-421">**Workaround:**</span></span>

<span data-ttu-id="f20d5-422">Das Problem kann nicht umgangen werden.</span><span class="sxs-lookup"><span data-stu-id="f20d5-422">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="a-response-group-agent-can-sign-in-and-sign-out-through-a-lync-server-2010-agent-console-to-lync-server-2010-formal-agent-groups-only"></a><span data-ttu-id="f20d5-423">Ein Reaktionsgruppen-Agent kann sich über eine lync Server 2010-Agent-Konsole anmelden und abmelden, um nur lync Server 2010 formellen Agentgruppen</span><span class="sxs-lookup"><span data-stu-id="f20d5-423">A Response Group agent can sign in and sign out through a Lync Server 2010 Agent Console to Lync Server 2010 formal Agent Groups only</span></span>

<span data-ttu-id="f20d5-424">**Problem**</span><span class="sxs-lookup"><span data-stu-id="f20d5-424">**Issue:**</span></span>

<span data-ttu-id="f20d5-425">Ein lync Server 2013 Reaktionsgruppen-Agent kann sich über eine lync Server 2010 Agent-Konsole anmelden und nur lync Server 2010 formellen Agentgruppen abmelden.</span><span class="sxs-lookup"><span data-stu-id="f20d5-425">A Lync Server 2013 Response Group agent can sign in and sign out through a Lync Server 2010 Agent Console to Lync Server 2010 formal Agent Groups only.</span></span> <span data-ttu-id="f20d5-426">In der lync Server 2010-Agent-Konsole können Benutzer nur die lync Server 2010 Reaktionsgruppe sehen, der Sie angehören.</span><span class="sxs-lookup"><span data-stu-id="f20d5-426">In the Lync Server 2010 Agent Console, users can see only the Lync Server 2010 Response Group that they belong to.</span></span> <span data-ttu-id="f20d5-427">Sie können keine der lync Server 2013 Reaktionsgruppen sehen, zu denen Sie gehören.</span><span class="sxs-lookup"><span data-stu-id="f20d5-427">They cannot see any of the Lync Server 2013 Response Groups that they belong to.</span></span>

<span data-ttu-id="f20d5-428">**Problemumgehung**</span><span class="sxs-lookup"><span data-stu-id="f20d5-428">**Workaround:**</span></span>

<span data-ttu-id="f20d5-429">Wenn der Reaktionsgruppen-Agent ein lync Server 2013er Benutzer und Teil einer lync Server 2013 formellen Agentgruppe ist, muss der Benutzer direkt über einen Weblink in einem Browser auf die lync Server 2013-Agent-Konsole zugreifen, um sich bei lync Server 2013 Agentgruppen anzumelden und abzumelden.</span><span class="sxs-lookup"><span data-stu-id="f20d5-429">If the Response Group agent is a Lync Server 2013 user, and part of a Lync Server 2013 formal Agent Group, the user must access the Lync Server 2013 Agent Console directly via a web link in a browser to sign in to and sign out from Lync Server 2013 Agent Groups.</span></span>

</div>

<div>

## <a name="a-lync-server-2010response-group-agent-cannot-place-calls-on-behalf-of-a-lync-server-2013response-group"></a><span data-ttu-id="f20d5-430">Ein lync Server 2010 Reaktionsgruppen-Agent kann keine Anrufe im Namen einer lync Server 2013 Reaktionsgruppe tätigen.</span><span class="sxs-lookup"><span data-stu-id="f20d5-430">A Lync Server 2010 Response Group agent cannot place calls on behalf of a Lync Server 2013 Response Group</span></span>

<span data-ttu-id="f20d5-431">**Problem**</span><span class="sxs-lookup"><span data-stu-id="f20d5-431">**Issue:**</span></span>

<span data-ttu-id="f20d5-432">Ein lync Server 2010 Benutzer, der ein Agent einer lync Server 2013 Reaktionsgruppe ist, kann im Namen der Reaktionsgruppe keinen Anruf tätigen.</span><span class="sxs-lookup"><span data-stu-id="f20d5-432">A Lync Server 2010 user who is an Agent of a Lync Server 2013 Response Group is not able to place a call on behalf of the Response Group.</span></span> <span data-ttu-id="f20d5-433">Die lync Server 2013 Reaktionsgruppe steht im lync-Client nicht zur Verfügung, um einen Anruf zu tätigen.</span><span class="sxs-lookup"><span data-stu-id="f20d5-433">The Lync Server 2013 Response Group will not be available in the Lync Client to place a call.</span></span>

<span data-ttu-id="f20d5-434">**Problemumgehung**</span><span class="sxs-lookup"><span data-stu-id="f20d5-434">**Workaround:**</span></span>

<span data-ttu-id="f20d5-435">Um dieses Problem zu umgehen, müssen Sie den lync Server 2010 Benutzer in lync Server 2013 bewegen.</span><span class="sxs-lookup"><span data-stu-id="f20d5-435">To work around this issue, you must move the Lync Server 2010 user to Lync Server 2013.</span></span>

</div>

<div>

## <a name="removing-a-response-group-from-lync-server-2010-after-it-has-been-migrated-to-lync-server-2013-will-prevent-the-response-group-from-accepting-any-incoming-calls"></a><span data-ttu-id="f20d5-436">Wenn Sie eine Reaktionsgruppe aus lync Server 2010 entfernen, nachdem Sie zu lync Server 2013 migriert wurde, wird verhindert, dass die Reaktionsgruppe eingehende Anrufe akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="f20d5-436">Removing a Response Group from Lync Server 2010 after it has been migrated to Lync Server 2013 will prevent the Response Group from accepting any incoming calls</span></span>

<span data-ttu-id="f20d5-437">**Problem**</span><span class="sxs-lookup"><span data-stu-id="f20d5-437">**Issue:**</span></span>

<span data-ttu-id="f20d5-438">Wenn eine Reaktionsgruppe, die von lync Server 2010 zu lync Server 2013 migriert wurde, aus lync Server 2010 über das lync Server-Systemsteuerung oder den lync Server-Verwaltungsshell entfernt wird, wird die Reaktionsgruppe in lync Server 2013 keine eingehenden Anrufe mehr empfangen.</span><span class="sxs-lookup"><span data-stu-id="f20d5-438">If a Response Group that has been migrated from Lync Server 2010 to Lync Server 2013 is removed from Lync Server 2010 through the Lync Server Control Panel or the Lync Server Management Shell, the Response Group in Lync Server 2013 will stop receiving any incoming calls.</span></span>

<span data-ttu-id="f20d5-439">**Problemumgehung**</span><span class="sxs-lookup"><span data-stu-id="f20d5-439">**Workaround:**</span></span>

<span data-ttu-id="f20d5-440">Um dieses Problem zu umgehen, entfernen Sie keine Reaktionsgruppen aus lync Server 2010, die von lync Server 2010 zu lync Server 2013 migriert wurden.</span><span class="sxs-lookup"><span data-stu-id="f20d5-440">To work around this issue, do not remove any Response Groups from Lync Server 2010 that have been migrated from Lync Server 2010 to Lync Server 2013.</span></span>

<span data-ttu-id="f20d5-441">Wenn die Reaktionsgruppe bereits entfernt wurde, sollten Sie Sie in lync Server 2013 erneut bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="f20d5-441">If the Response Group has already been removed, you should redeploy it in Lync Server 2013.</span></span>

</div>

<div>

## <a name="when-a-new-managed-workflow-is-set-to-inactive-when-created-deployment-of-the-workflow-will-fail"></a><span data-ttu-id="f20d5-442">Wenn ein neuer verwalteter Workflow bei der Erstellung auf inaktiv festgelegt ist, wird die Bereitstellung des Workflows fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="f20d5-442">When a new managed workflow is set to inactive when created, deployment of the workflow will fail</span></span>

<span data-ttu-id="f20d5-443">**Problem**</span><span class="sxs-lookup"><span data-stu-id="f20d5-443">**Issue:**</span></span>

<span data-ttu-id="f20d5-p143">Wenn ein neuer verwalteter Workflow bei seiner Erstellung auf inaktiv festgelegt wird, gibt die Bereitstellung des Workflows einen Fehler zurück. Dieses Problem tritt auf, wenn der Workflow bei seiner Erstellung auf inaktiv festgelegt wird. Es wirkt sich jedoch nicht auf einen Workflow aus, der nach seiner Bereitstellung bearbeitet wurde, um auf inaktiv festgelegt zu werden.</span><span class="sxs-lookup"><span data-stu-id="f20d5-p143">When a new managed workflow is set to inactive when created, deployment of the workflow will fail. This issue is encountered when the workflow is set to inactive when created, but does not affect a workflow that is edited to set it to inactive after is has been deployed.</span></span>

<span data-ttu-id="f20d5-446">**Problemumgehung**</span><span class="sxs-lookup"><span data-stu-id="f20d5-446">**Workaround:**</span></span>

<span data-ttu-id="f20d5-p144">Wenn Sie einen Workflow erstellen und bereitstellen, legen Sie den Workflow als aktiv fest, und stellen Sie ihn anschließend bereit. Nachdem der Workflow erfolgreich bereitgestellt wurde, kann er bearbeitet und auf inaktiv festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="f20d5-p144">When creating and deploying a workflow, set the workflow as active and then deploy it. After the workflow is successfully deployed, the workflow can be edited and set to inactive.</span></span>

</div>

<div>

## <a name="removing-a-response-group-from-the-owner-pool-will-prevent-the-response-group-of-the-backup-pool-from-accepting-any-incoming-calls-during-failover-if-the-response-group-has-been-imported-to-the-backup-pool"></a><span data-ttu-id="f20d5-449">Durch das Entfernen einer Reaktionsgruppe aus dem Besitzer Pool wird verhindert, dass die Reaktionsgruppe des Sicherungs Pools eingehende Anrufe während eines Failovers akzeptiert, wenn die Reaktionsgruppe in den Sicherungspool importiert wurde.</span><span class="sxs-lookup"><span data-stu-id="f20d5-449">Removing a Response Group from the Owner pool will prevent the Response Group of the Backup pool from accepting any incoming calls during failover if the Response Group has been imported to the Backup pool</span></span>

<span data-ttu-id="f20d5-450">**Problem**</span><span class="sxs-lookup"><span data-stu-id="f20d5-450">**Issue:**</span></span>

<span data-ttu-id="f20d5-451">Wenn eine Reaktionsgruppe, die dem primären Pool gehört, in den Sicherungspool importiert wurde, ohne den Besitzer zu überschreiben, und die Reaktionsgruppe aus dem Besitzer Pool entfernt wurde, akzeptiert die Reaktionsgruppe im Sicherungspool keine eingehenden Anrufe während eines Failovers.</span><span class="sxs-lookup"><span data-stu-id="f20d5-451">If a Response Group that is owned by the primary pool has been imported to the backup pool without overwriting the owner, and the Response Group is removed from the owner pool, the Response Group in the Backup pool will not accept any incoming calls during failover.</span></span>

<span data-ttu-id="f20d5-452">**Problemumgehung**</span><span class="sxs-lookup"><span data-stu-id="f20d5-452">**Workaround:**</span></span>

<span data-ttu-id="f20d5-453">Sie müssen die Reaktionsgruppe im primären Pool erneut bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="f20d5-453">You will need to redeploy the Response Group in the Primary pool.</span></span> <span data-ttu-id="f20d5-454">Anschließend müssen Sie die Reaktionsgruppen Konfiguration aus dem primären Pool exportieren und erneut in den Sicherungspool importieren.</span><span class="sxs-lookup"><span data-stu-id="f20d5-454">You will then need to export the Response Group configuration from the Primary pool and import it to the Backup pool again.</span></span>

<span data-ttu-id="f20d5-455">Sie können die Reaktionsgruppe auch im Sicherungspool neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f20d5-455">You can also recreate the Response Group in the Backup pool.</span></span> <span data-ttu-id="f20d5-456">In diesem Fall ist der Sicherungspool der Besitzer Pool der Reaktionsgruppe.</span><span class="sxs-lookup"><span data-stu-id="f20d5-456">In this case, the Backup pool will be the owner pool of the Response Group.</span></span>

</div>

<div>

## <a name="a-parked-call-cant-be-retrieved-from-the-call-park-application-if-the-retrieve-request-is-done-on-behalf-of-a-response-group"></a><span data-ttu-id="f20d5-457">Ein geparkter Anruf kann nicht aus dem Anwendung zum Parken von Anrufen abgerufen werden, wenn die Abrufanforderung im Namen einer Reaktionsgruppe erfolgt.</span><span class="sxs-lookup"><span data-stu-id="f20d5-457">A parked call can't be retrieved from the Call Park application if the retrieve request is done on behalf of a Response Group</span></span>

<span data-ttu-id="f20d5-458">**Problem**</span><span class="sxs-lookup"><span data-stu-id="f20d5-458">**Issue:**</span></span>

<span data-ttu-id="f20d5-459">Wenn die folgenden Bedingungen wahr sind, schlägt eine Abrufanforderung für einen geparkten Anruf fehl:</span><span class="sxs-lookup"><span data-stu-id="f20d5-459">When the following conditions are true, a retrieve request for a parked call will fail:</span></span>

  - <span data-ttu-id="f20d5-460">Ein Agent ist Teil einer anonymen Reaktionsgruppe</span><span class="sxs-lookup"><span data-stu-id="f20d5-460">An agent is part of an anonymous Response Group</span></span>

  - <span data-ttu-id="f20d5-461">Der Agent versucht, einen geparkten Anruf aus dem Anwendung zum Parken von Anrufen über die anonyme Reaktionsgruppe abzurufen.</span><span class="sxs-lookup"><span data-stu-id="f20d5-461">The agent attempts to retrieve a parked call from the Call Park application through the anonymous Response Group</span></span>

  - <span data-ttu-id="f20d5-462">Der Agent versucht, den Anruf durch Wählen der Orbitnummer über die Option "Anruf im Namen von" oder über dieselbe Option im Lync-Telefonzentralen-Client abzurufen</span><span class="sxs-lookup"><span data-stu-id="f20d5-462">The agent attempts to retrieve the call by dialing the orbit number through the Call On Behalf option or through the same option in the Lync attendant client</span></span>

<span data-ttu-id="f20d5-463">**Problemumgehung**</span><span class="sxs-lookup"><span data-stu-id="f20d5-463">**Workaround:**</span></span>

<span data-ttu-id="f20d5-464">Das Problem kann nicht umgangen werden.</span><span class="sxs-lookup"><span data-stu-id="f20d5-464">There are no workarounds for this issue.</span></span> <span data-ttu-id="f20d5-465">Der geparkte Anruf sollte ohne dies im Namen einer Reaktionsgruppe abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f20d5-465">The parked call should be retrieved without doing so on behalf of a Response Group.</span></span>

</div>

</div>

<span id="TopoBuilder"></span>

<div>

## <a name="lync-server-control-panel-topology-builder-and-planning-tool"></a><span data-ttu-id="f20d5-466">Lync Server-Systemsteuerung, -Topologie-Generator und -Planungstool</span><span class="sxs-lookup"><span data-stu-id="f20d5-466">Lync Server Control Panel, Topology Builder, and Planning Tool</span></span>

<div>

## <a name="planning-tool-limitations"></a><span data-ttu-id="f20d5-467">Einschränkungen des Planungstools</span><span class="sxs-lookup"><span data-stu-id="f20d5-467">Planning Tool Limitations</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="f20d5-468">Die Informationen in diesem Abschnitt beziehen sich auf kumulative Updates für lync Server 2013: Februar 2013.</span><span class="sxs-lookup"><span data-stu-id="f20d5-468">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="f20d5-469">**Problem**</span><span class="sxs-lookup"><span data-stu-id="f20d5-469">**Issue:**</span></span>

<span data-ttu-id="f20d5-470">Das Planungs Tool weist bei der Planung Ihrer Bereitstellung die folgenden Einschränkungen auf:</span><span class="sxs-lookup"><span data-stu-id="f20d5-470">The Planning Tool has the following limitations when planning for your deployment:</span></span>

  - <span data-ttu-id="f20d5-471">Es werden maximal 10 Zentrale Standorte unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f20d5-471">There is a maximum of 10 central sites supported</span></span>

  - <span data-ttu-id="f20d5-472">Jeder zentrale Standort kann maximal 14 Zweigstellen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="f20d5-472">Each central site can have a maximum of 14 branch sites</span></span>

  - <span data-ttu-id="f20d5-473">Jeder zentrale Standort kann maximal 240.000 Benutzer aufweisen.</span><span class="sxs-lookup"><span data-stu-id="f20d5-473">Each central site can have a maximum of 240,000 users</span></span>

<span data-ttu-id="f20d5-474">Darüber hinaus enthält das Planungs Tool bei der Berechnung der empfohlenen Topologie keine Werte für Folgendes:</span><span class="sxs-lookup"><span data-stu-id="f20d5-474">In addition, the Planning Tool does not include values for the following when calculating the recommended topology:</span></span>

  - <span data-ttu-id="f20d5-475">Die Anzahl der Benutzer, die Online verwaltet werden</span><span class="sxs-lookup"><span data-stu-id="f20d5-475">The number of users that are homed online</span></span>

  - <span data-ttu-id="f20d5-476">Der Prozentsatz der Benutzer, die für den XMPP-Partnerverbund aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="f20d5-476">The percentage of users that are enabled for XMPP federation</span></span>

  - <span data-ttu-id="f20d5-477">Prozentsatz der Benutzer, die lync Web App verwenden</span><span class="sxs-lookup"><span data-stu-id="f20d5-477">Percentage of users that are using Lync Web App</span></span>

<span data-ttu-id="f20d5-478">**Problemumgehung**</span><span class="sxs-lookup"><span data-stu-id="f20d5-478">**Workaround:**</span></span>

<span data-ttu-id="f20d5-479">Es gibt keine Umgehungslösung für diese Probleme.</span><span class="sxs-lookup"><span data-stu-id="f20d5-479">There is no workaround for these issues.</span></span> <span data-ttu-id="f20d5-480">Weitere Informationen zum Planungstool finden Sie unter [Entwerfen der Topologie für lync Server 2013 mithilfe des Planungstools](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md).</span><span class="sxs-lookup"><span data-stu-id="f20d5-480">For more information about the Planning Tool, see [Designing the topology for Lync Server 2013 by using the Planning Tool](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md).</span></span>

</div>

<div>

## <a name="planning-tool-may-not-use-previously-defined-ip-addresses-for-the-edge-network-when-updating-options"></a><span data-ttu-id="f20d5-481">Planungs Tool verwendet möglicherweise nicht zuvor definierte IP-Adressen für das Edge-Netzwerk beim Aktualisieren von Optionen</span><span class="sxs-lookup"><span data-stu-id="f20d5-481">Planning Tool may not use previously defined IP addresses for the Edge network when updating options</span></span>

<span data-ttu-id="f20d5-482">**Problem**</span><span class="sxs-lookup"><span data-stu-id="f20d5-482">**Issue:**</span></span>

<span data-ttu-id="f20d5-483">Nachdem Sie Ihren Entwurf mit dem Planungs Tool abgeschlossen haben und Änderungen an den Edge-Netzwerkoptionen vorgenommen haben, werden dem Entwurf möglicherweise zusätzliche IP-Adressen hinzugefügt, anstatt die vorhandenen IP-Adressen zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="f20d5-483">After you complete your design using the Planning Tool, if you make changes to the Edge Network options, additional IP addresses may be added to the design instead of updating the existing IP addresses.</span></span> <span data-ttu-id="f20d5-484">Dies kann auftreten, wenn Sie die Details des Edge-Netzplandiagramms anzeigen, wählen Sie **Klicken Sie hier, um Ihre Optionen zu aktualisieren**, und wählen Sie dann im Dialogfeld Konfigurationsoptionen die Option Edge-Netzwerk auswählen **Ich möchte dieselben FQDNs und IP-Adressen verwenden, aber unterschiedliche Ports für die Edge-Dienste auf meinem Edgeserver**.</span><span class="sxs-lookup"><span data-stu-id="f20d5-484">This can occur when you are viewing the details of the Edge Network Diagram, select **Click here to update your options**, and then, on the Configuration Options dialog, you select Edge Network select **I want to use the same FQDNs and IP addresses, but different ports for the edge services on my Edge Server**.</span></span> <span data-ttu-id="f20d5-485">Das Anwenden von Änderungen kann dazu führen, dass neue IP-Adressen und Edgeserver zum Entwurf hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="f20d5-485">Applying any changes may result in new IP addresses and Edge servers being added to the design.</span></span>

<span data-ttu-id="f20d5-486">**Problemumgehung**</span><span class="sxs-lookup"><span data-stu-id="f20d5-486">**Workaround:**</span></span>

<span data-ttu-id="f20d5-487">Es gibt derzeit keine Umgehungslösung für dieses Problem.</span><span class="sxs-lookup"><span data-stu-id="f20d5-487">There is no workaround for this issue at this time.</span></span>

</div>

<div>

## <a name="in-lync-server-control-panel-move-all-users-to-pool-may-not-work-as-expected"></a><span data-ttu-id="f20d5-488">In lync Server-Systemsteuerung kann "alle Benutzer in Pool migrieren" möglicherweise nicht erwartungsgemäß ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f20d5-488">In Lync Server Control Panel, "Move all users to pool" may not work as expected</span></span>

<span data-ttu-id="f20d5-489">**Problem**</span><span class="sxs-lookup"><span data-stu-id="f20d5-489">**Issue:**</span></span>

<span data-ttu-id="f20d5-490">Wenn Sie die lync Server-Systemsteuerung verwenden, um alle Benutzer von einem Pool in einen anderen Pool in einer komplexen Active Directory Umgebung zu versetzen, beispielsweise mit mehreren Domänencontrollern und übergeordneten/untergeordneten Domänen, wird möglicherweise eine Fehlermeldung zurückgegeben, die besagt, dass "der angegebene Benutzer kein älterer Benutzer ist" stattdessen das Cmdlet "CsUser" verwendet.</span><span class="sxs-lookup"><span data-stu-id="f20d5-490">When using the Lync Server Control Panel to move all users from one pool to another pool in a complex Active Directory environment, such as one with multiple Domain Controllers and parent/child domains, an error message may be returned that states, “Specified user is not a legacy user, use Move-CsUser cmdlet instead.”</span></span> <span data-ttu-id="f20d5-491">Dies ist ein Ergebnis längerer Replikationszeiten in komplexen Active Directory Umgebungen.</span><span class="sxs-lookup"><span data-stu-id="f20d5-491">This is a result of longer replication times in complex Active Directory environments.</span></span>

<span data-ttu-id="f20d5-492">**Problemumgehung**</span><span class="sxs-lookup"><span data-stu-id="f20d5-492">**Workaround:**</span></span>

<span data-ttu-id="f20d5-493">Führen Sie einen der folgenden Schritte aus, um das Problem zu umgehen:</span><span class="sxs-lookup"><span data-stu-id="f20d5-493">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="f20d5-494">Verwenden Sie Filter im lync Server-Systemsteuerung, um nach älteren Benutzern zu suchen, wählen Sie diese Benutzer aus, und verwenden Sie dann den **Befehl ausgewählte Benutzer zum Pool verlegen** , anstatt **alle Benutzer in den Pool**zu stellen.</span><span class="sxs-lookup"><span data-stu-id="f20d5-494">Use filters in the Lync Server Control Panel to search for legacy users, select those users, and then use the **Move selected users to pool command** instead of **Move all users to pool**.</span></span>

  - <span data-ttu-id="f20d5-495">Verwenden Sie die lync Server-Verwaltungsshell, um ältere Benutzer in Batches mithilfe von lync Server-Cmdlets zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="f20d5-495">Use the Lync Server Management Shell to move legacy users in batches by using Lync Server cmdlets.</span></span>

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-the-microsoft-silverlight-browser-plug-in-is-updated-to-version-5"></a><span data-ttu-id="f20d5-496">Das lync Server-Systemsteuerung funktioniert in einer VMware-Umgebung nicht mehr, nachdem das Plug-in Microsoft Silverlight Browser auf Version 5 aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="f20d5-496">The Lync Server Control Panel stops working in a VMware environment after the Microsoft Silverlight browser plug-in is updated to version 5</span></span>

<span data-ttu-id="f20d5-497">**Problem**</span><span class="sxs-lookup"><span data-stu-id="f20d5-497">**Issue:**</span></span>

<span data-ttu-id="f20d5-498">Wenn Sie das lync Server-Systemsteuerung in einer VMware-Umgebung verwenden, funktioniert das lync Server-Systemsteuerung nach dem Upgrade von Silverlight auf Version 5 möglicherweise nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="f20d5-498">If you use the Lync Server Control Panel in a VMware environment, the Lync Server Control Panel may stop working after you upgrade Silverlight to version 5.</span></span>

<span data-ttu-id="f20d5-499">**Problemumgehung**</span><span class="sxs-lookup"><span data-stu-id="f20d5-499">**Workaround:**</span></span>

<span data-ttu-id="f20d5-500">Führen Sie einen der folgenden Schritte aus, um das Problem zu umgehen:</span><span class="sxs-lookup"><span data-stu-id="f20d5-500">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="f20d5-501">Deinstallieren Sie Silverlight 5, und installieren Sie dann Silverlight [https://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](https://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0)4 aus.</span><span class="sxs-lookup"><span data-stu-id="f20d5-501">Uninstall Silverlight 5, and then install Silverlight 4 from [https://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](https://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0).</span></span>

  - <span data-ttu-id="f20d5-502">Öffnen Sie die lync Server-Systemsteuerung von einem Computer, auf dem es sich nicht um einen virtuellen VMware-Computer handelt.</span><span class="sxs-lookup"><span data-stu-id="f20d5-502">Open the Lync Server Control Panel from a computer that is not a VMware virtual computer.</span></span>
    
    <span data-ttu-id="f20d5-503">Um die lync Server-Systemsteuerung von einem Remotecomputer aus zu öffnen, installieren Sie lync Server Verwaltungstools auf dem Computer, und starten Sie dann die lync Server-Systemsteuerung aus dem Windows- **Startmenü** .</span><span class="sxs-lookup"><span data-stu-id="f20d5-503">To open the Lync Server Control Panel from a remote computer, install Lync Server Administration tools on the computer, and then start the Lync Server Control Panel from the Windows **Start** menu.</span></span>
    
    <span data-ttu-id="f20d5-504">Sie können das lync Server-Systemsteuerung auch öffnen, indem Sie die URL in einen Webbrowser eingeben.</span><span class="sxs-lookup"><span data-stu-id="f20d5-504">You can also open the Lync Server Control Panel by entering the URL in a web browser.</span></span> <span data-ttu-id="f20d5-505">\<Die URL ähnelt dem FQDN\_\_\>des https://-Front-End-Pools/CSCP.</span><span class="sxs-lookup"><span data-stu-id="f20d5-505">The URL will be similar to https://\<frontend\_pool\_fqdn\>/cscp.</span></span>

</div>

<div>

## <a name="an-administrator-cannot-run-the-uninstall-csmirrordb-cmdlet-after-removing-the-mirroring-database-in-topology-builder"></a><span data-ttu-id="f20d5-506">Ein Administrator kann das Cmdlet "Uninstall-csMirrorDB" nicht ausführen, nachdem die Spiegelungsdatenbank im Topologie-Generator entfernt wurde.</span><span class="sxs-lookup"><span data-stu-id="f20d5-506">An administrator cannot run the Uninstall-csMirrorDB cmdlet after removing the mirroring database in Topology Builder</span></span>

<span data-ttu-id="f20d5-507">**Problem**</span><span class="sxs-lookup"><span data-stu-id="f20d5-507">**Issue:**</span></span>

<span data-ttu-id="f20d5-508">Wenn ein Administrator eine Spiegelungsdatenbank im Topologie-Generator deaktiviert und dann die Spiegelungsdatenbank im Topologie-Generator löscht, wird eine Meldung in der Aufgabenliste angezeigt, mit der der Administrator das Cmdlet **Uninstall-csMirrorDatabase** ausführt, um die Spiegelung von SQL Server zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="f20d5-508">When an administrator disables a mirroring database in Topology Builder, and then deletes the mirroring database in Topology Builder, a message is displayed in the To do list for the administrator to run the **Uninstall-csMirrorDatabase** cmdlet to remove mirroring from SQL Server.</span></span> <span data-ttu-id="f20d5-509">Wenn der Administrator versucht, das Cmdlet auszuführen, wird ein Fehler zurückgegebenl.</span><span class="sxs-lookup"><span data-stu-id="f20d5-509">When the administrator attempts to run the cmdlet, it fails.</span></span>

<span data-ttu-id="f20d5-510">**Problemumgehung**</span><span class="sxs-lookup"><span data-stu-id="f20d5-510">**Workaround:**</span></span>

<span data-ttu-id="f20d5-511">Zum Entfernen der SQL-Spiegelung eines Pools im Topologie-Generator müssen Sie zunächst ein Cmdlet verwenden, um die Spiegelung in SQL Server zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="f20d5-511">To remove SQL mirroring of a pool in Topology Builder, you must first use a cmdlet to remove the mirror in SQL Server.</span></span> <span data-ttu-id="f20d5-512">Anschließend können Sie den Topologie-Generator verwenden, um den Spiegel aus der Topologie zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="f20d5-512">You can then use Topology Builder to remove the mirror from the topology.</span></span> <span data-ttu-id="f20d5-513">Verwenden Sie das folgende Cmdlet, um die Spiegelung in SQL Server zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="f20d5-513">To remove the mirror in SQL Server, use the following cmdlet:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

<span data-ttu-id="f20d5-514">Geben Sie beispielsweise Folgendes ein, um die Spiegelung zu entfernen und die Datenbanken für die Benutzerdatenbanken zu löschen:</span><span class="sxs-lookup"><span data-stu-id="f20d5-514">For example, to remove mirroring and drop the databases for the user databases, type the following:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

<span data-ttu-id="f20d5-515">Der Parameter *DropExistingDatabasesOnMirror* bewirkt, dass die betroffenen Datenbanken aus dem Spiegel gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="f20d5-515">The *DropExistingDatabasesOnMirror* parameter causes the affected databases to be deleted from the mirror.</span></span> <span data-ttu-id="f20d5-516">Führen Sie anschließend die folgenden Schritte aus, um den Spiegel aus der Topologie zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="f20d5-516">Then, to remove the mirror from the topology, do the following:</span></span>

1.  <span data-ttu-id="f20d5-517">Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den Pool, und klicken Sie auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="f20d5-517">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="f20d5-518">Deaktivieren Sie die Option **Spiegelung des SQL-Speichers aktivieren**, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f20d5-518">Clear **Enable SQL Store Mirroring** and click **OK**.</span></span>

3.  <span data-ttu-id="f20d5-519">Veröffentlichen Sie die Topologie.</span><span class="sxs-lookup"><span data-stu-id="f20d5-519">Publish the topology.</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="f20d5-520">Wenn Sie eine Änderung an einer Back-End-Datenbank-Spiegelungs Beziehung vornehmen, müssen Sie alle Front-End-Server im Pool neu starten.</span><span class="sxs-lookup"><span data-stu-id="f20d5-520">Whenever you make a change to a back-end database mirroring relationship, you must restart all the Front End Servers in the pool.</span></span>



</div>

</div>

<div>

## <a name="validation-errors-are-returned-in-topology-builder-when-an-administrator-attempts-to-remove-a-deployment-with-a-front-end-pool-that-has-an-associated-witness-store"></a><span data-ttu-id="f20d5-521">Validierungsfehler werden im Topologie-Generator zurückgegeben, wenn ein Administrator versucht, eine Bereitstellung mit einem Front-End-Pool zu entfernen, der über einen zugeordneten Zeugen Speicher verfügt.</span><span class="sxs-lookup"><span data-stu-id="f20d5-521">Validation errors are returned in Topology Builder when an administrator attempts to remove a deployment with a Front End pool that has an associated witness store</span></span>

<span data-ttu-id="f20d5-522">**Problem**</span><span class="sxs-lookup"><span data-stu-id="f20d5-522">**Issue:**</span></span>

<span data-ttu-id="f20d5-523">Wenn ein Administrator versucht, den Befehl " **Bereitstellung entfernen** " im Topologie-Generator zu verwenden, um eine Bereitstellung zu entfernen, die eine Front-End-Pool mit einem zugeordneten Zeugen Speicher enthält, wird im Topologie-Generator ein Validierungsfehler angezeigt, und die Aktion wird nicht fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="f20d5-523">If an administrator attempts to use the **Remove Deployment** command in Topology Builder to remove a deployment that includes a Front End pool with an associated witness store, a validation error is displayed in Topology Builder and the action will not proceed.</span></span>

<span data-ttu-id="f20d5-524">**Problemumgehung**</span><span class="sxs-lookup"><span data-stu-id="f20d5-524">**Workaround:**</span></span>

<span data-ttu-id="f20d5-525">Führen Sie einen der folgenden Schritte aus, um das Problem zu umgehen:</span><span class="sxs-lookup"><span data-stu-id="f20d5-525">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="f20d5-526">Entfernen Sie den Zeugenspeicher, bevor Sie versuchen, die Bereitstellung zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="f20d5-526">Remove the witness store before attempting to remove the deployment.</span></span>

  - <span data-ttu-id="f20d5-527">Fügen Sie einen Zeugenspeicher für den Front-End-Pool hinzu, und entfernen Sie ihn dann.</span><span class="sxs-lookup"><span data-stu-id="f20d5-527">Add a witness store for the Front End pool and then remove it.</span></span>

</div>

<div>

## <a name="persistent-chat-server-deployment-information-is-inconsistent-between-the-planning-tool-and-topology-builder"></a><span data-ttu-id="f20d5-528">Bereitstellungsinformationen für persistent Chat Server sind inkonsistent zwischen dem Planungs Tool und dem Topologie-Generator</span><span class="sxs-lookup"><span data-stu-id="f20d5-528">Persistent Chat Server deployment information is inconsistent between the Planning Tool and Topology Builder</span></span>

<span data-ttu-id="f20d5-529">**Problem**</span><span class="sxs-lookup"><span data-stu-id="f20d5-529">**Issue:**</span></span>

<span data-ttu-id="f20d5-530">Wenn lync Server 2013 das Planungs Tool das Website Topologie-Diagramm für eine Server Bereitstellung für beständigen Chat bereitstellt und die Notfallwiederherstellung aktiviert ist, enthält das Diagramm für die Standorttopologie mehrere (physikalische) Websites mit gleichmäßig zugewiesenen beständigen Chatservern in jedem der beiden Seiten. Website.</span><span class="sxs-lookup"><span data-stu-id="f20d5-530">When the Lync Server 2013, Planning Tool outputs the site topology diagram for a Persistent Chat Server deployment with disaster recovery enabled, the site topology diagram includes multiple (physical) sites, with evenly assigned Persistent Chat Servers at each site.</span></span> <span data-ttu-id="f20d5-531">Im Topologie-Generator werden alle Server für beständigen Chat als Zugehörigkeit zu einem einzigen (logischen) Standort dargestellt und unter demselben Serverpool Knoten für beständigen Chat aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="f20d5-531">In Topology Builder, all Persistent Chat Servers are represented as belonging to a single (logical) site, and are listed under the same Persistent Chat Server pool node.</span></span>

<span data-ttu-id="f20d5-532">**Problemumgehung**</span><span class="sxs-lookup"><span data-stu-id="f20d5-532">**Workaround:**</span></span>

<span data-ttu-id="f20d5-533">Derzeit kann dieses Problem nicht umgangen werden.</span><span class="sxs-lookup"><span data-stu-id="f20d5-533">Currently, we do not have a workaround for this issue.</span></span> <span data-ttu-id="f20d5-534">Der Benutzer sollte die Ausgabe des Planungstools für die Server Bereitstellung für beständigen Chat analysieren und den Plan so ändern, dass er den spezifischen Anforderungen entspricht.</span><span class="sxs-lookup"><span data-stu-id="f20d5-534">The user should analyze the output of the Planning Tool for the Persistent Chat Server deployment, and modify the plan to meet their specific needs.</span></span>

</div>

</div>

<span id="Localization"></span>

<div>

## <a name="localization"></a><span data-ttu-id="f20d5-535">Lokalisierung</span><span class="sxs-lookup"><span data-stu-id="f20d5-535">Localization</span></span>

<div>

## <a name="monitoring"></a><span data-ttu-id="f20d5-536">Überwachung</span><span class="sxs-lookup"><span data-stu-id="f20d5-536">Monitoring</span></span>

<div>

## <a name="the-deploy-monitoring-reports-wizard-displays-incorrect-characters-under-certain-circumstances-when-using-the-east-asian-version-of-lync-server"></a><span data-ttu-id="f20d5-537">Der Assistent zum Bereitstellen von Überwachungsberichten zeigt unter bestimmten Umständen falsche Zeichen an, wenn Sie die ostasiatische Version von lync Server verwenden.</span><span class="sxs-lookup"><span data-stu-id="f20d5-537">The Deploy Monitoring Reports wizard displays incorrect characters under certain circumstances when using the East Asian version of Lync Server</span></span>

<span data-ttu-id="f20d5-538">**Problem**</span><span class="sxs-lookup"><span data-stu-id="f20d5-538">**Issue:**</span></span>

<span data-ttu-id="f20d5-539">Bei Verwendung einer ostasiatischen Version von lync Server 2013-beispielsweise Chinesisch (vereinfacht), Chinesisch (traditionell), Japanisch oder Koreanisch – auf einem Betriebssystem, auf dem das Systemgebietsschema nicht auf eine ostasiatische Sprache festgelegt ist, wird der Assistent zum Bereitstellen von Überwachungsberichten Anzeigen von Fragezeichen oder anderen Zeichen anstelle lokalisierter Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="f20d5-539">When using an East Asian version of Lync Server 2013—for example, Chinese (Simplified), Chinese (Traditional), Japanese, or Korean—on an operating system that has the system locale not set to an East Asian language, the Deploy Monitoring Reports wizard will display question marks or other characters instead of localized messages.</span></span>

<span data-ttu-id="f20d5-540">**Problemumgehung**</span><span class="sxs-lookup"><span data-stu-id="f20d5-540">**Workaround:**</span></span>

<span data-ttu-id="f20d5-541">Um dieses Problem zu beheben, legen Sie das Gebietsschema für das Betriebssystem und die lync Server 2013 auf dieselbe Sprache fest, in der alle Nachrichten ordnungsgemäß angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f20d5-541">To correct this issue, set the locale for the operating system and Lync Server 2013 to the same language, which will display all messages correctly.</span></span>

</div>

</div>

<div>

## <a name="lync-server-control-panel"></a><span data-ttu-id="f20d5-542">Lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="f20d5-542">Lync Server Control Panel</span></span>

<div>

## <a name="in-certain-cases-the-first-item-in-the-top-navigation-bar-on-a-page-of-lync-server-control-panel-disappears-when-the-last-item-in-the-top-navigation-bar-is-clicked"></a><span data-ttu-id="f20d5-543">In bestimmten Fällen wird das erste Element in der oberen Navigationsleiste auf einer Seite mit lync Server-Systemsteuerung ausgeblendet, wenn das letzte Element in der oberen Navigationsleiste geklickt wird.</span><span class="sxs-lookup"><span data-stu-id="f20d5-543">In certain cases, the first item in the top navigation bar on a page of Lync Server Control Panel disappears when the last item in the top navigation bar is clicked</span></span>

<span data-ttu-id="f20d5-544">**Problem**</span><span class="sxs-lookup"><span data-stu-id="f20d5-544">**Issue:**</span></span>

<span data-ttu-id="f20d5-545">Es gibt drei bekannte Fälle, in denen durch Klicken auf das letzte Element in der oberen Navigationsleiste auf einer Seite des lync Server-Systemsteuerung das erste Element in der oberen Navigationsleiste ausgeblendet wird:</span><span class="sxs-lookup"><span data-stu-id="f20d5-545">There are three known cases where clicking the last item in the top navigation bar on a page of the Lync Server Control Panel will cause the first item in the top navigation bar to disappear:</span></span>

  - <span data-ttu-id="f20d5-546">In der französischen Version wird auf der Seite "Féderation et accès externe" das Element "Stratégie d'accès externe" nicht mehr angezeigt, wenn der Benutzer auf "Partenaires fédérés XMPP" klickt.</span><span class="sxs-lookup"><span data-stu-id="f20d5-546">In the French of version, on the page "Féderation et accès externe," the item "Stratégie d'accès externe" will disappear when "Partenaires fédérés XMPP" is clicked.</span></span>

  - <span data-ttu-id="f20d5-547">In der deutschen Version wird auf der Seite "Clients" das Element "Clientversionskonfiguration" nicht mehr angezeigt, wenn der Benutzer auf "Pushbenachrichtigungskonfiguration" klickt.</span><span class="sxs-lookup"><span data-stu-id="f20d5-547">In the German version, on the "Clients" page, the item "Clientversionskonfiguration" disappears when "Pushbenachrichtigungskonfiguration" is clicked.</span></span>

  - <span data-ttu-id="f20d5-548">In der russischen Version wird auf der Seite "Конфигурация сети" das Element "Глобально" nicht mehr angezeigt, wenn der Benutzer auf "Маршрут региона" klickt.</span><span class="sxs-lookup"><span data-stu-id="f20d5-548">In the Russian version, on "Конфигурация сети" page, the item "Глобально" disappears when "Маршрут региона" is clicked.</span></span>

<span data-ttu-id="f20d5-549">**Problemumgehung**</span><span class="sxs-lookup"><span data-stu-id="f20d5-549">**Workaround:**</span></span>

<span data-ttu-id="f20d5-550">Um dieses Problem zu umgehen, aktualisieren Sie die Seite des lync Server-Systemsteuerung in Ihrem Browser.</span><span class="sxs-lookup"><span data-stu-id="f20d5-550">To work around this issue, refresh the page of the Lync Server Control Panel in your browser.</span></span> <span data-ttu-id="f20d5-551">Daraufhin wird die Seite im Browser geladen, und alle Elemente in der oberen Navigationsleiste werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f20d5-551">The page will load in the browser with all of the items in the top navigation bar displayed.</span></span>

</div>

</div>

<div>

## <a name="address-book"></a><span data-ttu-id="f20d5-552">Adressbuch</span><span class="sxs-lookup"><span data-stu-id="f20d5-552">Address Book</span></span>

<div>

## <a name="indexing-in-the-address-book-does-not-work-as-expected-in-some-languages"></a><span data-ttu-id="f20d5-553">Die Indizierung im Adressbuch funktioniert in einigen Sprachen nicht wie erwartet.</span><span class="sxs-lookup"><span data-stu-id="f20d5-553">Indexing in the Address Book does not work as expected in some languages</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="f20d5-554">Die Informationen in diesem Abschnitt beziehen sich auf kumulative Updates für lync Server 2013: Februar 2013.</span><span class="sxs-lookup"><span data-stu-id="f20d5-554">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="f20d5-555">Wenn die Eigenschaften eines Benutzers ein indiziertes Feld enthalten und dieses Feld nur Zeichen enthält, die nicht indiziert werden können, wird der Benutzer nicht in Suchvorgängen angezeigt, die im Adressbuch ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f20d5-555">If a user’s properties contain an indexed field, and that field contains only characters that cannot be indexed, then the user will not appear in searches performed in the Address Book.</span></span>

<span data-ttu-id="f20d5-556">Die folgenden Zeichen und Gebietsschemas können nicht indiziert werden:</span><span class="sxs-lookup"><span data-stu-id="f20d5-556">The following characters and locales cannot be indexed:</span></span>

  - <span data-ttu-id="f20d5-557">Großschreibung Kyrillisch, Griechisch und Armenisch Zeichen</span><span class="sxs-lookup"><span data-stu-id="f20d5-557">Upper-case Cyrillic, Greek, and Armenian characters</span></span>

  - <span data-ttu-id="f20d5-558">Großbuchstaben mit akzentuierten Zeichen</span><span class="sxs-lookup"><span data-stu-id="f20d5-558">Upper-case accented characters</span></span>

  - <span data-ttu-id="f20d5-559">Thailändisch</span><span class="sxs-lookup"><span data-stu-id="f20d5-559">Thai</span></span>

  - <span data-ttu-id="f20d5-560">Laotisch</span><span class="sxs-lookup"><span data-stu-id="f20d5-560">Lao</span></span>

  - <span data-ttu-id="f20d5-561">Myanmar</span><span class="sxs-lookup"><span data-stu-id="f20d5-561">Myanmar</span></span>

  - <span data-ttu-id="f20d5-562">Devanagari</span><span class="sxs-lookup"><span data-stu-id="f20d5-562">Devanagari</span></span>

  - <span data-ttu-id="f20d5-563">Äthiopisch</span><span class="sxs-lookup"><span data-stu-id="f20d5-563">Ethiopic</span></span>

  - <span data-ttu-id="f20d5-564">Tibetanisch</span><span class="sxs-lookup"><span data-stu-id="f20d5-564">Tibetan</span></span>

  - <span data-ttu-id="f20d5-565">Bengali</span><span class="sxs-lookup"><span data-stu-id="f20d5-565">Bengali</span></span>

  - <span data-ttu-id="f20d5-566">Gujarati</span><span class="sxs-lookup"><span data-stu-id="f20d5-566">Gujarati</span></span>

  - <span data-ttu-id="f20d5-567">Telugu</span><span class="sxs-lookup"><span data-stu-id="f20d5-567">Telugu</span></span>

  - <span data-ttu-id="f20d5-568">Alle anderen indischen Skripts</span><span class="sxs-lookup"><span data-stu-id="f20d5-568">All other Indic scripts</span></span>

</div>

</div>

<div>

## <a name="lync-web-app-web-scheduler-and-web-components"></a><span data-ttu-id="f20d5-569">Lync Web App-, Webplaner-und Webkomponenten</span><span class="sxs-lookup"><span data-stu-id="f20d5-569">Lync Web App, Web Scheduler, and Web components</span></span>

<div>

## <a name="language-fallback-for-certain-languages-in-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-might-not-work-as-expected"></a><span data-ttu-id="f20d5-570">Sprach Fallback für bestimmte Sprachen in lync-Webplaner, Einwahl, Startprogramm, beständiger chatroomverwaltung und OCTab funktionieren möglicherweise nicht wie erwartet</span><span class="sxs-lookup"><span data-stu-id="f20d5-570">Language fallback for certain languages in Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab might not work as expected</span></span>

<span data-ttu-id="f20d5-571">**Problem**</span><span class="sxs-lookup"><span data-stu-id="f20d5-571">**Issue:**</span></span>

<span data-ttu-id="f20d5-572">Bei der Auswahl eines neutralen Gebietsschemas in einem Webbrowser (in Internet Explorer beispielsweise kann der Name der Sprache ohne weitere Angaben wie " \[Norwegisch\]Nein" anstelle eines Gebietsschemas, das die Sprache, das Skript und das Gebietsschema angibt (wie "Norwegisch \[, Nynorsk (\]Norwegen) nb-no") zu unerwartetem Anzeigeverhalten für bestimmte Sprachen in lync-Webplaner, Einwahl, Join Launcher, beständiger chatroomverwaltung und OCTab führen.</span><span class="sxs-lookup"><span data-stu-id="f20d5-572">When selecting a neutral locale in a web browser (in Internet Explorer, for example, the language name without further specification, like "Norwegian \[no\]") instead of a locale specifying language, script and locale (such as "Norwegian, Bokmål (Norway) \[nb-NO\]") might lead to unexpected display behavior for certain languages in Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab.</span></span> <span data-ttu-id="f20d5-573">Beispielsweise wird den Benutzern beim Auswählen einer der folgenden Sprachen möglicherweise die englische Seite angezeigt:</span><span class="sxs-lookup"><span data-stu-id="f20d5-573">For example, users might see the English page when one of the following languages is selected:</span></span>

  - <span data-ttu-id="f20d5-574">Norwegisch</span><span class="sxs-lookup"><span data-stu-id="f20d5-574">Norwegian</span></span>

  - <span data-ttu-id="f20d5-575">Portugiesisch</span><span class="sxs-lookup"><span data-stu-id="f20d5-575">Portuguese</span></span>

  - <span data-ttu-id="f20d5-576">Serbisch</span><span class="sxs-lookup"><span data-stu-id="f20d5-576">Serbian</span></span>

<span data-ttu-id="f20d5-577">**Problemumgehung**</span><span class="sxs-lookup"><span data-stu-id="f20d5-577">**Workaround:**</span></span>

<span data-ttu-id="f20d5-578">Wenn Sie eine Sprache mit neutralem Gebietsschema auswählen möchten, achten Sie darauf, dass Sie in der Spracheinstellungsliste Ihres Browsers auch die Sprache mit einem spezifischen Gebietsschema (einschließlich Skript und/oder Ländercode) als zusätzliche Sprache hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="f20d5-578">If you want to select a language with a neutral locale, always make sure that you also add the language with a specific locale (with script and/or country code) as an additional language in your browser's language preference list.</span></span>

</div>

<div>

## <a name="there-is-limited-support-for-azeri-and-uzbek-locales-when-using-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-in-some-web-browsers"></a><span data-ttu-id="f20d5-579">Es gibt nur beschränkte Unterstützung für aserbaidschanische und usbekische Gebietsschemas bei Verwendung von lync-Webplaner, Einwahl, Join Launcher, beständiger chatroomverwaltung und OCTab in einigen Webbrowsern.</span><span class="sxs-lookup"><span data-stu-id="f20d5-579">There is limited support for Azeri and Uzbek locales when using Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab in some web browsers</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="f20d5-580">Die Informationen in diesem Abschnitt beziehen sich auf kumulative Updates für lync Server 2013: Februar 2013.</span><span class="sxs-lookup"><span data-stu-id="f20d5-580">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="f20d5-581">**Problem**</span><span class="sxs-lookup"><span data-stu-id="f20d5-581">**Issue:**</span></span>

<span data-ttu-id="f20d5-582">Wenn Sie Internet Explorer 8 oder Internet Explorer 9 verwenden und die Browsersprache auf Aserbaidschanisch (lateinisch) oder Usbekistan (lateinisch) festlegen, werden die Seiten für Einwahl-und Join-Startprogramm in Englisch oder im Browser als bevorzugte Sprache angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f20d5-582">When you use Internet Explorer 8 or Internet Explorer 9, and set the browser language to Azeri (Latin) or Uzbek (Latin), the Dial-in and Join Launcher pages will be displayed in English or the preferred language set in the browser.</span></span>

<span data-ttu-id="f20d5-583">Wenn Sie Firefox oder Chrome Browser verwenden und die Browsersprache auf Aserbaidschanisch (lateinisch) oder Usbekistan (lateinisch) festlegen, werden lync Web App, lync-Webplaner und RGS-OCTab in Englisch oder in der bevorzugten Spracheinstellung für den Browser angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f20d5-583">When you use Firefox or Chrome browsers, and you set the browser language to Azeri (Latin) or Uzbek (Latin), the Lync Web App, Lync Web Scheduler, and RGS OCTab will be shown in English or the preferred language set for the browser.</span></span>

<span data-ttu-id="f20d5-584">Das Gebietsschema usbekischen (lateinisch) wird im Safari-Browser nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f20d5-584">The Uzbek (Latin) locale is not supported in the Safari browser.</span></span>

<span data-ttu-id="f20d5-585">**Problemumgehung**</span><span class="sxs-lookup"><span data-stu-id="f20d5-585">**Workaround:**</span></span>

<span data-ttu-id="f20d5-586">Es gibt keine Umgehungslösung für diese Probleme.</span><span class="sxs-lookup"><span data-stu-id="f20d5-586">There is not workaround for these issues.</span></span>

</div>

</div>

<div>

## <a name="the-drop-down-arrow-is-missing-for-join-meeting-from-list-in-the-romanian-version-of-lync-web-app"></a><span data-ttu-id="f20d5-587">Der Dropdownpfeil fehlt bei der Liste "an der Besprechung teilnehmen" in der rumänischen Version von lync Web App</span><span class="sxs-lookup"><span data-stu-id="f20d5-587">The drop-down arrow is missing for "Join meeting from" list in the Romanian version of Lync Web App</span></span>

<span data-ttu-id="f20d5-588">**Problem**</span><span class="sxs-lookup"><span data-stu-id="f20d5-588">**Issue:**</span></span>

<span data-ttu-id="f20d5-589">Wenn ein Benutzer, der die rumänische Version von lync Web App verwendet, die folgenden Schritte ausführt, wird der Dropdownpfeil für **Teilnahme an Besprechung** in der Dropdownliste nicht angezeigt:</span><span class="sxs-lookup"><span data-stu-id="f20d5-589">When a user who is using the Romanian version of Lync Web App performs the following steps, the drop-down arrow is not displayed for **Join meeting** in drop-down list:</span></span>

1.  <span data-ttu-id="f20d5-590">Wählen Sie auf der Registerkarte **Allgemein** die Option **Meine Daten auf diesem Computer speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="f20d5-590">Select **Remember me on this computer** on the **General** tab.</span></span>

2.  <span data-ttu-id="f20d5-591">Wählen Sie die Registerkarte **Telefon** aus.</span><span class="sxs-lookup"><span data-stu-id="f20d5-591">Select the **Phone** tab.</span></span>

3.  <span data-ttu-id="f20d5-592">Klicken Sie auf die Dropdownliste unter **An Besprechung teilnehmen über**.</span><span class="sxs-lookup"><span data-stu-id="f20d5-592">Click the drop-down list for **Join meeting from**.</span></span>
    
    <span data-ttu-id="f20d5-593">Benutzern wird kein Pfeil angezeigt, der angibt, dass es mehr Optionen als die Standard **lync Web App**gibt, die Folgendes umfassen: **Join Audio** (in Rumänisch, "Nu SE asociaža La Componenta Audio") und **New Number**"(in rumänischer Sprache," Număr Nou ").</span><span class="sxs-lookup"><span data-stu-id="f20d5-593">Users will not see an arrow that indicates that there are more options than the default **Lync Web App**, which include: **Don't join audio** (in Romanian, "Nu se asociaža la componenta audio") and **New number**" (in Romanian, "Număr nou").</span></span>

<span data-ttu-id="f20d5-594">**Problemumgehung**</span><span class="sxs-lookup"><span data-stu-id="f20d5-594">**Workaround:**</span></span>

<span data-ttu-id="f20d5-595">Obwohl der Pfeil für diese Dropdownliste nicht angezeigt wird, können die Benutzer die zusätzlichen Einstellungen in der Liste auswählen, indem Sie auf den Standardwert klicken.</span><span class="sxs-lookup"><span data-stu-id="f20d5-595">Even though the arrow for this drop-down list is not displayed, users can still select the additional settings in the list by clicking on the default value.</span></span>

</div>

<div>

## <a name="when-using-the-turkish-version-of-lync-web-scheduler-a-meeting-cannot-be-saved-when-using-the-people-i-choose-option-under-who-is-a-presenter"></a><span data-ttu-id="f20d5-596">Bei Verwendung der türkischen Version von lync-Webplaner kann eine Besprechung nicht gespeichert werden, wenn die Option "Personen, die ich auswählen" unter "Wer ist ein Referent ist" verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f20d5-596">When using the Turkish version of Lync Web Scheduler, a meeting cannot be saved when using the "People I choose" option under "Who is a presenter"</span></span>

<span data-ttu-id="f20d5-597">**Problem**</span><span class="sxs-lookup"><span data-stu-id="f20d5-597">**Issue:**</span></span>

<span data-ttu-id="f20d5-p159">Beim Erstellen oder Bearbeiten einer Besprechung in der türkischen Version des Lync-Webplaners wird die Option "Von mir ausgewählte Personen" unter "Wer agiert als Referent" nicht unterstützt. Bei Auswahl dieser Option kann die Besprechung nicht gespeichert werden. Stattdessen wird eine Fehlermeldung mit dem Hinweis angezeigt, dass eine oder mehrere Personen nicht als Referenten agieren können.</span><span class="sxs-lookup"><span data-stu-id="f20d5-p159">When creating or editing a meeting in the Turkish version of the Lync Web Scheduler, the option "People I choose" under "Who is a presenter" is not supported. When this option is selected, the meeting can't be saved. Instead, an error message appears, indicating that one or more people cannot be made presenters.</span></span>

<span data-ttu-id="f20d5-601">**Problemumgehung**</span><span class="sxs-lookup"><span data-stu-id="f20d5-601">**Workaround:**</span></span>

<span data-ttu-id="f20d5-p160">Um dieses Problem zu umgehen, können die Benutzer die Standardoption "Personen in meinem Unternehmen" oder eine andere Option wie "Nur Organisator" oder "Alle, auch Personen außerhalb meines Unternehmens" verwenden. Der Organisator kann Personen später auf die richtigen Rollen herunter- oder heraufstufen, nachdem sie der Besprechung beigetreten sind.</span><span class="sxs-lookup"><span data-stu-id="f20d5-p160">To work around this issue, users can use the default option of "People from my company," or any other choice, such as "Only Organizer" or "Everyone including people outside of my company." The organizer can demote or promote people to their correct roles later, after they have joined the meeting.</span></span>

<span data-ttu-id="f20d5-604">Alternativ dazu können Benutzer, die eine andere Sprache verstehen, die Sprachauswahl in ihrem Browser in eine der anderen 43 unterstützten Sprachen ändern und versuchen, die Option "Von mir ausgewählte Personen" zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f20d5-604">Alternatively, users who understand another language can change the language selection in their browser to one of the other 43 supported languages and attempt to use the “People I choose” option.</span></span>

</div>

</div>

<span id="Copyright"></span>

<div>

## <a name="copyright"></a><span data-ttu-id="f20d5-605">Copyright</span><span class="sxs-lookup"><span data-stu-id="f20d5-605">Copyright</span></span>

<span data-ttu-id="f20d5-p161">Dieses Dokument unterstützt eine Vorabversion eines Softwareprodukts, die vor der endgültigen Freigabe für den Handel wesentlich geändert werden kann. Im Dokument sind geschützte und vertrauliche Informationen von Microsoft enthalten. Das Informationsmaterial wird gemäß einer Vertraulichkeitsvereinbarung zwischen dem Empfänger und Microsoft zugänglich gemacht. Dieses Dokument dient nur zu Informationszwecken, und Microsoft schließt jede ausdrückliche oder konkludente Gewährleistung für dieses Dokument aus. Die in diesem Dokument enthaltenen Informationen, einschließlich URLs und anderer Verweise auf Internetwebsites, können ohne vorherige Ankündigung geändert werden. Das gesamte Risiko bezüglich der Verwendung oder der Ergebnisse der Verwendung dieses Dokuments verbleibt beim Benutzer. Die in den Beispielen verwendeten Namen von Firmen, Organisationen, Produkten, Domänen, Personen, Orten, Ereignissen sowie E-Mail-Adressen und Logos sind frei erfunden, soweit nichts anderes angegeben ist. Jede Ähnlichkeit mit tatsächlichen Firmen, Organisationen, Produkten, Domänennamen, Personen, Orten, Ereignissen, E-Mail-Adressen und Logos ist rein zufällig. Die Benutzer/innen sind verpflichtet, sich an alle anwendbaren Urheberrechtsgesetze zu halten. Unabhängig von der Anwendbarkeit der entsprechenden Urheberrechtsgesetze darf ohne ausdrückliche schriftliche Erlaubnis der Microsoft Corporation kein Teil dieses Dokuments für irgendwelche Zwecke vervielfältigt oder in einem Datenempfangssystem gespeichert oder darin eingelesen werden, unabhängig davon, auf welche Art und Weise oder mit welchen Mitteln (elektronisch, mechanisch, durch Fotokopieren, Aufzeichnen usw.) dies geschieht.</span><span class="sxs-lookup"><span data-stu-id="f20d5-p161">This document supports a preliminary release of a software product that may be changed substantially prior to final commercial release, and is the confidential and proprietary information of Microsoft Corporation. It is disclosed pursuant to a non-disclosure agreement between the recipient and Microsoft. This document is provided for informational purposes only and Microsoft makes no warranties, either express or implied, in this document. Information in this document, including URL and other Internet website references, is subject to change without notice. The entire risk of the use or the results from the use of this document remains with the user. Unless otherwise noted, the companies, organizations, products, domain names, email addresses, logos, people, places, and events depicted in examples herein are fictitious. No association with any real company, organization, product, domain name, email address, logo, person, place, or event is intended or should be inferred. Complying with all applicable copyright laws is the responsibility of the user. Without limiting the rights under copyright, no part of this document may be reproduced, stored in or introduced into a retrieval system, or transmitted in any form or by any means (electronic, mechanical, photocopying, recording, or otherwise), or for any purpose, without the express written permission of Microsoft Corporation.</span></span>

<span data-ttu-id="f20d5-p162">Microsoft kann Inhaber von Patenten oder Patentanträgen, Marken, Urheberrechten oder anderem geistigen Eigentum sein, die den Inhalt dieses Dokuments betreffen. Die Bereitstellung dieses Dokuments gewährt keinerlei Lizenzrechte an diesen Patenten, Marken, Urheberrechten oder anderem geistigen Eigentum, es sei denn, dies wurde ausdrücklich durch einen schriftlichen Lizenzvertrag mit der Microsoft Corporation vereinbart.</span><span class="sxs-lookup"><span data-stu-id="f20d5-p162">Microsoft may have patents, patent applications, trademarks, copyrights, or other intellectual property rights covering subject matter in this document. Except as expressly provided in any written license agreement from Microsoft, the furnishing of this document does not give you any license to these patents, trademarks, copyrights, or other intellectual property.</span></span>

<span data-ttu-id="f20d5-p163">© 2012 Microsoft Corporation. Alle Rechte vorbehalten.</span><span class="sxs-lookup"><span data-stu-id="f20d5-p163">© 2012 Microsoft Corporation. All rights reserved.</span></span>

<span data-ttu-id="f20d5-619">Microsoft, Windows, Windows Live, Active Directory, Internet Explorer, MSN, Outlook und SQL Server sind eingetragene Marken oder Marken der Microsoft Corporation in den USA und/oder anderen Ländern/Regionen.</span><span class="sxs-lookup"><span data-stu-id="f20d5-619">Microsoft, Windows, Windows Live, Active Directory, Internet Explorer, MSN, Outlook, and SQL Server are either registered trademarks or trademarks of Microsoft Corporation in the United States and/or other countries/regions.</span></span>

<span data-ttu-id="f20d5-620">Alle anderen Marken sind Eigentum der jeweiligen Inhaber.</span><span class="sxs-lookup"><span data-stu-id="f20d5-620">All other trademarks are property of their respective owners.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

