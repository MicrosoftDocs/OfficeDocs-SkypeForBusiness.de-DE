---
title: 'Lync Server 2013: Planen der Notfallwiederherstellung für Reaktionsgruppen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for response group disaster recovery
ms:assetid: 14e0f5dc-77cd-42cd-a9c9-4d0da38fb1cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204699(v=OCS.15)
ms:contentKeyID: 48183482
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6cc238665ecb0222ded43e438e9f9370b561b85d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530572"
---
# <a name="planning-for-response-group-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="26f37-102">Planen der Notfallwiederherstellung für Reaktionsgruppen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="26f37-102">Planning for response group disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="26f37-103">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="26f37-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="26f37-104">In diesem Abschnitt werden einige Methoden zum Vorbereiten von Reaktionsgruppen auf die Notfallwiederherstellung beschrieben. Außerdem enthält er eine Übersicht über den Notfallwiederherstellungsprozess.</span><span class="sxs-lookup"><span data-stu-id="26f37-104">This section describes some ways to prepare response groups for disaster recovery and provides an overview of the disaster recovery process.</span></span>

<div>

## <a name="preparing-for-response-group-disaster-recovery"></a><span data-ttu-id="26f37-105">Vorbereiten der Notfallwiederherstellung für Reaktionsgruppen</span><span class="sxs-lookup"><span data-stu-id="26f37-105">Preparing for Response Group Disaster Recovery</span></span>

<span data-ttu-id="26f37-106">Beachten Sie beim Vorbereiten und Ausführen von Notfallwiederherstellungsverfahren Folgendes.</span><span class="sxs-lookup"><span data-stu-id="26f37-106">Keep the following in mind when you prepare for and carry out disaster recovery procedures.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="26f37-107">In einer Umgebung mit Koexistenz werden nur die lync Server 2013 Reaktionsgruppen für die in diesem Dokument beschriebenen Notfallwiederherstellungsverfahren unterstützt.</span><span class="sxs-lookup"><span data-stu-id="26f37-107">In a coexistence environment, only the Lync Server 2013 response groups are supported for the disaster recovery procedures described in this document.</span></span>



</div>

  - <span data-ttu-id="26f37-108">Planen Sie die Notfallwiederherstellung gleichzeitig mit der Kapazitätsplanung.</span><span class="sxs-lookup"><span data-stu-id="26f37-108">Plan for disaster recovery when you do your capacity planning.</span></span> <span data-ttu-id="26f37-109">Für die Notfallwiederherstellungskapazität sollte jeder Pool in einem Poolpaar die Arbeitsauslastung aller Reaktionsgruppen in beiden Pools bewältigen können.</span><span class="sxs-lookup"><span data-stu-id="26f37-109">For disaster recovery capacity, each pool in a paired pool should be able to handle the workloads of all the response groups in both pools.</span></span> <span data-ttu-id="26f37-110">Ausführliche Informationen zur Kapazitätsplanung für Reaktionsgruppen finden Sie unter [Kapazitätsplanung für Reaktionsgruppe in lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md).</span><span class="sxs-lookup"><span data-stu-id="26f37-110">For details about Response Group capacity planning, see [Capacity planning for Response Group in Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md).</span></span>

  - <span data-ttu-id="26f37-111">Nehmen Sie regelmäßig Sicherungskopien aller Reaktionsgruppen Konfigurationen in allen Front-End-Pools vor, in denen Sie die Reaktionsgruppenanwendung mithilfe des in diesem Dokument beschriebenen Exportverfahrens bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="26f37-111">Take regular backup copies of all the response group configurations in all the Front End pools where you deployed the Response Group application by using the export procedure described in this document.</span></span> <span data-ttu-id="26f37-112">Ausführliche Informationen finden Sie unter [Notfallwiederherstellungsverfahren für Reaktionsgruppen in lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="26f37-112">For details, see [Response group disaster recovery procedures in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span></span> <span data-ttu-id="26f37-113">Bewahren Sie die Sicherungskopien an einem sicheren Ort auf.</span><span class="sxs-lookup"><span data-stu-id="26f37-113">Keep the backup copies in a safe location.</span></span>

  - <span data-ttu-id="26f37-114">Bewahren Sie eine separate Sicherungskopie aller ursprünglichen Audiodateien auf, die Sie für die Reaktionsgruppenanwendung verwendet haben, einschließlich Aufzeichnungen und Dateien mit Wartemusik.</span><span class="sxs-lookup"><span data-stu-id="26f37-114">Keep a separate backup copy of all the original audio files you used for the Response Group application, including any recordings and music-on-hold files.</span></span> <span data-ttu-id="26f37-115">Bewahren Sie die Sicherungsdateien an einem sicheren Ort auf.</span><span class="sxs-lookup"><span data-stu-id="26f37-115">Keep the backup files in a safe location.</span></span>

  - <span data-ttu-id="26f37-116">Für lync Server 2013 Notfallwiederherstellung müssen alle Einstellungen für Reaktionsgruppen eindeutige Namen in der gesamten Bereitstellung aufweisen.</span><span class="sxs-lookup"><span data-stu-id="26f37-116">For Lync Server 2013 disaster recovery, all Response Group settings must have unique names across your deployment.</span></span> <span data-ttu-id="26f37-117">Diese Anforderung gilt für Workflows, Warteschlangen, Agentgruppen, Feiertagssätze und Geschäftszeiten.</span><span class="sxs-lookup"><span data-stu-id="26f37-117">This requirement applies to workflows, queues, agent groups, holiday sets, and hours of business.</span></span> <span data-ttu-id="26f37-118">Überprüfen Sie, ob diese Anforderung erfüllt ist, wenn die primären Pools und Sicherungspools aktiv sind, bevor Sie ein Failoververfahren einleiten müssen.</span><span class="sxs-lookup"><span data-stu-id="26f37-118">You should verify that this requirement is met when the primary and backup pools are still active, and before you need to initiate any failover procedure.</span></span> <span data-ttu-id="26f37-119">Wenn beim Importieren von Reaktionsgruppendaten in den Sicherungspool Namenskonflikte auftreten, schlägt der Import fehl.</span><span class="sxs-lookup"><span data-stu-id="26f37-119">If you encounter name conflicts while importing response group data to the backup pool, the import fails.</span></span> <span data-ttu-id="26f37-120">Zum Abschließen des Imports und des Failoververfahrens müssen Sie die Namenskonflikte lösen, indem Sie das Reaktionsgruppenobjekt im Sicherungspool ändern oder das Cmdlet **Import-CsRgsConfiguration** mit dem Parameter "–ResolveNameConflicts" ausführen, um den Konflikt automatisch zu lösen, indem eine eindeutige Identifikationsnummer an das Reaktionsgruppenobjekt angehängt wird.</span><span class="sxs-lookup"><span data-stu-id="26f37-120">To complete the import and failover procedure, you need to resolve the name conflicts by renaming the response group object in the backup pool or by using the **Import-CsRgsConfiguration** cmdlet with the –ResolveNameConflicts parameter to automatically resolve the conflict by appending a unique identifying number to the response group object.</span></span>

  - <span data-ttu-id="26f37-p105">Im Allgemeinen wird empfohlen, täglich eine Sicherung anzulegen. Wenn jedoch große Mengen von Daten innerhalb einer kurzen Zeit geändert werden, sollten Sie häufigere Sicherungen ansetzen. Die Menge an Informationen, die bei einem Notfall verloren gehen kann, hängt von der Häufigkeit Ihrer Sicherungen sowie von der Häufigkeit und Menge der Änderungen ab.</span><span class="sxs-lookup"><span data-stu-id="26f37-p105">In general, we recommend that you perform daily backups, but if you have a high volume of changes, you might want to schedule more frequent backups. The amount of information you can lose in the event of a disaster depends on the frequency of your backups, as well as the frequency and volume of changes.</span></span>

  - <span data-ttu-id="26f37-123">Das Importieren von Reaktionsgruppen in einen Sicherungspool vor dem Ausführen eines Notfallwiederherstellungs- oder Failoververfahrens ist möglich.</span><span class="sxs-lookup"><span data-stu-id="26f37-123">It is possible to import response groups to a backup pool before a disaster or failover operation occurs.</span></span> <span data-ttu-id="26f37-124">Das vorab Importieren von Reaktionsgruppen reduziert die Ausfallzeit, da der lync Server Reaktionsgruppendienst im Sicherungspool wiederhergestellt werden kann, sobald Anrufe an den Sicherungspool weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="26f37-124">Importing response groups in advance reduces downtime, because the Lync Server Response Group service can be restored in the backup pool as soon as calls are routed to the backup pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="26f37-125">Der Reaktionsgruppenanwendung kann keine Agents erreichen, die in einem inaktiven Pool verwaltet werden, bis das Failover abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="26f37-125">The Response Group application cannot reach any agents homed in an inactive pool until failover is complete.</span></span> <span data-ttu-id="26f37-126">Während dieser Zeit verarbeitet der Reaktionsgruppenanwendung Anrufe, als ob diese Agents nicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="26f37-126">During this time, the Response Group application processes calls as if those agents are unavailable.</span></span>

    
    </div>

</div>

<div>

## <a name="response-group-disaster-recovery-process"></a><span data-ttu-id="26f37-127">Notfallwiederherstellungsprozess für Reaktionsgruppen</span><span class="sxs-lookup"><span data-stu-id="26f37-127">Response Group Disaster Recovery Process</span></span>

<span data-ttu-id="26f37-128">In einem Notfall können Sie Reaktionsgruppen mit einer der folgenden Methoden wiederherstellen:</span><span class="sxs-lookup"><span data-stu-id="26f37-128">In the event of a disaster, you can recover response groups by using either of the following recovery approaches:</span></span>

  - <span data-ttu-id="26f37-129">Ausführen eines Failovers zu einem Sicherungspool und eines Failbacks zum ursprünglichen Pool.</span><span class="sxs-lookup"><span data-stu-id="26f37-129">Fail over to a backup pool and then fail back to the original pool.</span></span>

  - <span data-ttu-id="26f37-130">Ausführen eines Failovers zu einem Sicherungspool, Erstellen eines neuen Pools mit einem anderen vollqualifizierten Domänennamen (FQDN) und anschließendes Importieren der Reaktionsgruppen in den neuen Pool.</span><span class="sxs-lookup"><span data-stu-id="26f37-130">Fail over to a backup pool, create a new pool with a different fully qualified domain name (FQDN), and then import the response groups to the new pool.</span></span>

<span data-ttu-id="26f37-p108">Während der Failoverphase der Notfallwiederherstellung befinden sich die Reaktionsgruppen in mehreren Pools: im (nicht verfügbaren) primären Pool und im Sicherungspool. Die Reaktionsgruppen in den beiden Pools haben denselben Namen und denselben Besitzer (den primären Pool), sie haben jedoch unterschiedliche übergeordnete Elemente.</span><span class="sxs-lookup"><span data-stu-id="26f37-p108">During the failover phase of disaster recovery, the response groups reside in multiple pools: in the primary pool (which is unavailable) and in the backup pool. The response groups in both pools have the same name and the same owner (the primary pool), but they have different parents.</span></span>

<span data-ttu-id="26f37-133">Wenn Sie die Wiederherstellung durch das Erstellen eines neuen Pools mit einem anderen FQDN durchführen, müssen Sie den neuen Pool als Besitzer der Reaktionsgruppen zuordnen, wenn Sie diese importieren.</span><span class="sxs-lookup"><span data-stu-id="26f37-133">When you recover by creating a new pool with a different FQDN, you need to assign the new pool as the owner of the response groups when you import them.</span></span> <span data-ttu-id="26f37-134">Der Besitz von Reaktionsgruppen verbleibt beim ursprünglichen Pool, außer Sie ordnen den Besitz explizit neu zu, indem Sie das Cmdlet **Import-CsRgsConfiguration** mit dem Parameter "–OverwriteOwner" ausführen.</span><span class="sxs-lookup"><span data-stu-id="26f37-134">Ownership of response groups remains with the original pool unless or until you explicitly reassign ownership by using the –OverwriteOwner parameter with the **Import-CsRgsConfiguration** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="26f37-135">Sie müssen auch den Parameter "– OverwriteOwner" verwenden, wenn Sie den Pool während der Wiederherstellung neu erstellt haben (also die Reaktionsgruppen Datenbank leer ist), unabhängig davon, ob Sie denselben FQDN verwenden oder nicht.</span><span class="sxs-lookup"><span data-stu-id="26f37-135">You also need to use the –OverwriteOwner parameter if you rebuilt the pool during the recovery (that is, the Response Group database is empty), whether or not you use the same FQDN.</span></span> <span data-ttu-id="26f37-136">Wenn Sie den Pool nicht neu erstellt haben, müssen Sie den Parameter "–OverwriteOwner" nicht verwenden, die Verwendung dieses Parameters ist jedoch zulässig, wenn Sie Reaktionsgruppen in den ursprünglichen Pool zurückimportieren.</span><span class="sxs-lookup"><span data-stu-id="26f37-136">You do not need to use the –OverwriteOwner parameter if you did not rebuild the pool, but it is permissible to use this parameter whenever you import response groups back to the primary pool.</span></span>



</div>

<span data-ttu-id="26f37-137">Sie können nur eine Gruppe von Reaktionsgruppen-Konfigurationseinstellungen auf Anwendungsebene pro Pool definieren.</span><span class="sxs-lookup"><span data-stu-id="26f37-137">You can define only one set of application-level Response Group configuration settings per pool.</span></span> <span data-ttu-id="26f37-138">Diese Einstellungen umfassen die Standardkonfiguration für Wartemusik, die Standardaudiodatei für Wartemusik, die Kulanzfrist für Agentrückrufe und die Anrufkontextkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="26f37-138">These settings include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="26f37-139">Zum Anzeigen dieser Konfigurationseinstellungen führen Sie das Cmdlet **Get-CsRgsConfiguration** aus.</span><span class="sxs-lookup"><span data-stu-id="26f37-139">To view these configuration settings, run the **Get-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="26f37-140">Ausführliche Informationen zum Cmdlet **Get-CsRgsConfiguration** finden Sie unter [Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration).</span><span class="sxs-lookup"><span data-stu-id="26f37-140">For details about the **Get-CsRgsConfiguration** cmdlet, see [Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration).</span></span>

<span data-ttu-id="26f37-141">Sie können diese Einstellungen auf Anwendungsebene mithilfe des Cmdlets **Import-CsRgsConfiguration** und dem Parameter "–ReplaceExistingSettings" von einem Pool auf einen anderen übertragen. Dadurch werden jedoch die Einstellungen im Zielpool überschrieben.</span><span class="sxs-lookup"><span data-stu-id="26f37-141">You can transfer these application-level settings from one pool to another by using the **Import-CsRgsConfiguration** cmdlet with the –ReplaceExistingSettings parameter, but doing so overrides the settings in the destination pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="26f37-p112">Diese Einschränkung beim Übertragen von Einstellungen auf einen anderen Pool gilt nur für Einstellungen auf Anwendungsebene und die Standarddatei für die Wartemusik. Für Agentgruppen, Warteschlangen, Workflows, Geschäftszeiten und Feiertagssätze gilt die Einschränkung nicht.</span><span class="sxs-lookup"><span data-stu-id="26f37-p112">This constraint about transferring settings to another pool is true only for the application-level settings and the default music-on-hold audio file. It does not apply to agent groups, queues, workflows, business hours, and holiday sets.</span></span>



</div>

<span data-ttu-id="26f37-p113">Wenn Sie die Einstellungen auf Anwendungsebene im Sicherungspool während eines Notfalls nicht ersetzen möchten und der primäre Pool nicht wiederhergestellt werden kann, gehen die Einstellungen auf Anwendungsebene des primären Pools verloren. Wenn Sie während der Wiederherstellung einen neuen Pool als Ersatz für den primären Pool erstellen – entweder mit demselben oder einem anderen FQDN – können Sie die ursprünglichen Einstellungen auf Anwendungsebene nicht wiederherstellen. In diesem Fall müssen Sie den neuen Pool mit diesen Einstellungen konfigurieren und die Wartemusik-Audiodatei hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="26f37-p113">If you don't want to replace the application-level settings in the backup pool during a disaster and the primary pool can't be recovered, the application-level settings from the primary pool will be lost. If you need to create a new pool to replace the primary pool during recovery, either with the same FQDN or with a different FQDN, you can't recover the original application-level settings. In this case, you need to configure the new pool with these settings and include the music-on-hold audio file.</span></span>

<span data-ttu-id="26f37-147">Wenn Sie Einstellungen auf Anwendungsebene bei einem Notfall mithilfe des Cmdlets **Import-CsRgsConfiguration** vom primären Pool auf den Sicherungspool übertragen möchten, können Sie die Einstellungen vom Sicherungspool bei der Wiederherstellung auf die gleiche Weise auf den neuen Pool übertragen, wie vom primären Pool auf den Sicherungspool.</span><span class="sxs-lookup"><span data-stu-id="26f37-147">If you decide to use the **Import-CsRgsConfiguration** cmdlet to transfer application-level settings from the primary pool to the backup pool during a disaster, you can then transfer the settings from the backup pool to the new pool during recovery in the same way that you transferred them from the primary pool to the backup pool.</span></span>

<span data-ttu-id="26f37-148">Die folgende Tabelle zeigt eine Übersicht über die Schritte beim Wiederherstellen von Reaktionsgruppen.</span><span class="sxs-lookup"><span data-stu-id="26f37-148">The following table is an overview of the steps involved in recovering response groups.</span></span>

<span data-ttu-id="26f37-149">Ausführliche Informationen zum Ausführen dieser Schritte finden Sie unter [Notfallwiederherstellungsverfahren für Reaktionsgruppen in lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="26f37-149">For details about performing these steps, see [Response group disaster recovery procedures in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span></span>

### <a name="response-group-disaster-recovery-steps"></a><span data-ttu-id="26f37-150">Schritte der Notfallwiederherstellung für Reaktionsgruppen</span><span class="sxs-lookup"><span data-stu-id="26f37-150">Response Group Disaster Recovery Steps</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="26f37-151">Phase</span><span class="sxs-lookup"><span data-stu-id="26f37-151">Phase</span></span></th>
<th><span data-ttu-id="26f37-152">Schritte</span><span class="sxs-lookup"><span data-stu-id="26f37-152">Steps</span></span></th>
<th><span data-ttu-id="26f37-153">Erforderliche Gruppen und Rollen</span><span class="sxs-lookup"><span data-stu-id="26f37-153">Required groups and roles</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="26f37-154">Vor dem Ausfall</span><span class="sxs-lookup"><span data-stu-id="26f37-154">Before outage</span></span></p></td>
<td><p><span data-ttu-id="26f37-155">Führen Sie das Cmdlet <strong>Export-CsRgsConfiguration</strong> auf Routinebasis aus, um Sicherungen aller Reaktionsgruppen Konfigurationen in allen Front-End-Pools zu erstellen, in denen Reaktionsgruppenanwendung bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="26f37-155">On a routine basis, run the <strong>Export-CsRgsConfiguration</strong> cmdlet to create backups of all Response Group configurations in all Front End pools where Response Group application is deployed.</span></span></p></td>
<td><p><span data-ttu-id="26f37-156">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="26f37-156">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="26f37-157">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="26f37-157">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26f37-158">Während des Ausfalls</span><span class="sxs-lookup"><span data-stu-id="26f37-158">During outage</span></span></p></td>
<td><p><span data-ttu-id="26f37-159">Führen Sie das Cmdlet <strong>Import-CsRgsConfiguration</strong> aus, um die gesicherte lync Server Reaktionsgruppendienst-Konfiguration aus dem primären Pool in den Sicherungspool zu importieren.</span><span class="sxs-lookup"><span data-stu-id="26f37-159">Run the <strong>Import-CsRgsConfiguration</strong> cmdlet to import the backed up Lync Server Response Group service configuration from the primary pool to the backup pool.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="26f37-160">Verwenden Sie den Parameter – ReplaceExistingSettings, wenn Sie Reaktionsgruppeneinstellungen auf Anwendungsebene im Sicherungspool durch die Einstellungen aus dem primären Pool ersetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="26f37-160">Use the –ReplaceExistingSettings parameter if you want to replace application-level Response Group settings in the backup pool with the settings from the primary pool.</span></span> <span data-ttu-id="26f37-161">Wenn Sie die Einstellungen auf Anwendungsebene nicht vom primären Pool auf den Sicherungspool übertragen und der primäre Pool nicht wiederhergestellt werden kann, gehen die Einstellungen aus dem primären Pool verloren.</span><span class="sxs-lookup"><span data-stu-id="26f37-161">If you do not transfer the application-level settings from the primary pool to the backup pool, and the primary pool can't be recovered, you will lose the settings from the primary pool.</span></span>


</div></td>
<td><p><span data-ttu-id="26f37-162">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="26f37-162">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="26f37-163">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="26f37-163">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26f37-164">Nach dem Importieren</span><span class="sxs-lookup"><span data-stu-id="26f37-164">After importing</span></span></p></td>
<td><p><span data-ttu-id="26f37-165">Ausführen von Cmdlets für Reaktionsgruppen mit dem Parameter "– ShowAll" (zum Anzeigen aller Reaktionsgruppen) oder dem Parameter "– Owner" (um nur importierte Reaktionsgruppen anzuzeigen), um zu überprüfen, ob alle Reaktionsgruppen Konfigurationen in den Sicherungspool importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="26f37-165">Run Response Group cmdlets with either the –ShowAll parameter (to display all response groups) or the –Owner parameter (to display only imported response groups) to verify that all response group configurations were imported to the backup pool.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="26f37-166">Wenn Sie weder den Parameter "–ShowAll" noch den Parameter "–Owner" verwenden, werden die in den Sicherungspool importierten Reaktionsgruppen nicht in den von den Cmdlets zurückgegebenen Ergebnissen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="26f37-166">If you do not use either the –ShowAll parameter or the –Owner parameter, the response groups that you imported to the backup pool will not be listed in the results returned by the cmdlets.</span></span>


</div>
<p><span data-ttu-id="26f37-167">Führen Sie die folgenden Cmdlets aus:</span><span class="sxs-lookup"><span data-stu-id="26f37-167">Run the following cmdlets:</span></span></p>
<ul>
<li><p><span data-ttu-id="26f37-168"><strong>Get-CsRgsWorkflow</strong></span><span class="sxs-lookup"><span data-stu-id="26f37-168"><strong>Get-CsRgsWorkflow</strong></span></span></p></li>
<li><p><span data-ttu-id="26f37-169"><strong>Get-CsRgsQueue</strong></span><span class="sxs-lookup"><span data-stu-id="26f37-169"><strong>Get-CsRgsQueue</strong></span></span></p></li>
<li><p><span data-ttu-id="26f37-170"><strong>Get-CsRgsAgentGroup</strong></span><span class="sxs-lookup"><span data-stu-id="26f37-170"><strong>Get-CsRgsAgentGroup</strong></span></span></p></li>
<li><p><span data-ttu-id="26f37-171"><strong>Get-CsRgsHoursOfBusiness</strong></span><span class="sxs-lookup"><span data-stu-id="26f37-171"><strong>Get-CsRgsHoursOfBusiness</strong></span></span></p></li>
<li><p><span data-ttu-id="26f37-172"><strong>Get-CsRgsHolidaySet</strong></span><span class="sxs-lookup"><span data-stu-id="26f37-172"><strong>Get-CsRgsHolidaySet</strong></span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="26f37-173">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="26f37-173">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="26f37-174">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="26f37-174">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26f37-175">Nach dem Failover</span><span class="sxs-lookup"><span data-stu-id="26f37-175">After failover</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="26f37-176">Führen Sie einen Testanruf an eine in den Sicherungspool importierte Reaktionsgruppe durch, und überprüfen Sie, ob der Anruf ordnungsgemäß verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="26f37-176">Place a test call to a response group that was imported to the backup pool and verify that the call is handled correctly.</span></span></p></li>
<li><p><span data-ttu-id="26f37-177">Alle formellen Agents müssen sich bei ihren formellen Gruppen im Sicherungspool erneut anmelden.</span><span class="sxs-lookup"><span data-stu-id="26f37-177">All formal agents must sign in again to their formal groups on backup pool.</span></span></p></li>
<li><p><span data-ttu-id="26f37-178">Verwalten von Konfigurationsänderungen:</span><span class="sxs-lookup"><span data-stu-id="26f37-178">Manage configuration changes:</span></span></p>
<p><span data-ttu-id="26f37-179">Reaktionsgruppen im Sicherungspool können unabhängig davon, ob sie in den Sicherungspool importiert wurden oder im Besitz des Sicherungspools sind, während des Ausfalls normal geändert werden.</span><span class="sxs-lookup"><span data-stu-id="26f37-179">Response groups in the backup pool, whether imported to the backup pool or owned by the backup pool, can be modified as usual during the outage.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="26f37-180">Sie müssen lync Server-Verwaltungsshell verwenden, um die Reaktionsgruppen zu verwalten, die Sie in den Sicherungspool importiert haben.</span><span class="sxs-lookup"><span data-stu-id="26f37-180">You must use Lync Server Management Shell to manage the response groups that you imported to the backup pool.</span></span> <span data-ttu-id="26f37-181">Sie können diese Reaktionsgruppen nicht mithilfe von lync Server-Systemsteuerung verwalten, während Sie sich im Sicherungspool befinden.</span><span class="sxs-lookup"><span data-stu-id="26f37-181">You cannot use Lync Server Control Panel to manage these response groups while they are in the backup pool.</span></span>


</div></li>
</ul></td>
<td><p><span data-ttu-id="26f37-182">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="26f37-182">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26f37-183">Nach der Wiederherstellung, vor dem Failback</span><span class="sxs-lookup"><span data-stu-id="26f37-183">After recovery, before failback</span></span></p></td>
<td><p><span data-ttu-id="26f37-184">Führen Sie das Cmdlet <strong>Export-CsRgsConfiguration</strong> aus, und geben Sie dabei den Parameter "-Source" als Sicherungspool und den Parameter "–Owner" als primären Pool an, in den die Reaktionsgruppen im Besitz des primären Pools aus dem Sicherungspool importiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="26f37-184">Run the <strong>Export-CsRgsConfiguration</strong> cmdlet specifying the -Source parameter as the backup pool and the –Owner parameter as the primary pool to export the response groups owned by the primary pool from the backup pool.</span></span></p></td>
<td><p><span data-ttu-id="26f37-185">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="26f37-185">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="26f37-186">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="26f37-186">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26f37-187">Nach dem Failback</span><span class="sxs-lookup"><span data-stu-id="26f37-187">After failback</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="26f37-188">Führen Sie das Cmdlet <strong>Import-CsRgsConfiguration</strong> aus, um die Reaktionsgruppen zurück in den primären Pool zu importieren.</span><span class="sxs-lookup"><span data-stu-id="26f37-188">Run the <strong>Import-CsRgsConfiguration</strong> cmdlet to import the response groups back to the primary pool.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="26f37-p116">Wenn der primäre Pool nicht wiederhergestellt werden kann und Sie einen neuen Pool als Ersatz bereitstellen, verwenden Sie den Parameter "–ReplaceExistingSettings", um die Einstellungen auf Anwendungsebene vom Sicherungspool auf den neuen Pool zu übertragen. Wenn Sie die Einstellungen aus dem Sicherungspool nicht übertragen, verwendet der neue Pool die Standardeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="26f37-p116">If the primary pool can't be recovered and you deploy a new pool to replace it, use the –ReplaceExistingSettings parameter to transfer the application-level settings from the backup pool to the new pool. If you do not transfer the settings from the backup pool, the new pool will use the default settings.</span></span>


</div></li>
<li><p><span data-ttu-id="26f37-191">Führen Sie die folgenden -Cmdlets entweder mit dem Parameter "–ShowAll" (um alle Reaktionsgruppen anzuzeigen) oder dem Parameter "–Owner" (um nur importierte Reaktionsgruppen anzuzeigen) aus, um zu überprüfen, ob alle Reaktionsgruppenkonfigurationen erfolgreich zurück in den Sicherungspool importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="26f37-191">Run the following cmdlets with either the –ShowAll parameter (to display all response groups) or the –Owner parameter (to display only imported response groups) to verify that all response group configurations were successfully imported back to the primary pool:</span></span></p>
<ul>
<li><p><span data-ttu-id="26f37-192"><strong>Get-CsRgsWorkflow</strong></span><span class="sxs-lookup"><span data-stu-id="26f37-192"><strong>Get-CsRgsWorkflow</strong></span></span></p></li>
<li><p><span data-ttu-id="26f37-193"><strong>Get-CsRgsQueue</strong></span><span class="sxs-lookup"><span data-stu-id="26f37-193"><strong>Get-CsRgsQueue</strong></span></span></p></li>
<li><p><span data-ttu-id="26f37-194"><strong>Get-CsRgsAgentGroup</strong></span><span class="sxs-lookup"><span data-stu-id="26f37-194"><strong>Get-CsRgsAgentGroup</strong></span></span></p></li>
<li><p><span data-ttu-id="26f37-195"><strong>Get-CsRgsHoursOfBusiness</strong></span><span class="sxs-lookup"><span data-stu-id="26f37-195"><strong>Get-CsRgsHoursOfBusiness</strong></span></span></p></li>
<li><p><span data-ttu-id="26f37-196"><strong>Get-CsRgsHolidaySet</strong></span><span class="sxs-lookup"><span data-stu-id="26f37-196"><strong>Get-CsRgsHolidaySet</strong></span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="26f37-197">Führen Sie einen Testanruf an eine in den primären Pool zurückimportierte Reaktionsgruppe durch, und überprüfen Sie, ob der Anruf ordnungsgemäß verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="26f37-197">Place a test call to a response group that was imported back to the primary pool and verify that the call is handled correctly.</span></span></p></li>
<li><p><span data-ttu-id="26f37-198">Führen Sie optional das Cmdlet <strong>Export-CsRgsConfiguration</strong> auf mit dem Parameter "–RemoveExportedConfiguration" auf dem Sicherungspool aus, um die Reaktionsgruppen im Besitz des primären Pool aus dem Sicherungspool zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="26f37-198">Optionally, run the <strong>Export-CsRgsConfiguration</strong> cmdlet on the backup pool with the –RemoveExportedConfiguration parameter to remove the response groups owned by the primary pool from the backup pool.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="26f37-199">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="26f37-199">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="26f37-200">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="26f37-200">CsResponseGroupAdministrator</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

