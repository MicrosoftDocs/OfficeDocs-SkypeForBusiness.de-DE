---
title: 'Lync Server 2013: Kapazitäts-und Verfügbarkeitsverwaltung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Capacity and availability management
ms:assetid: 207a2997-f482-4bee-892d-d2b112294481
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720325(v=OCS.15)
ms:contentKeyID: 63969586
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 923dd7a4133da52a68e4d66ee6d5c7c47e7c0421
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839693"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-and-availability-management-in-lync-server-2013"></a><span data-ttu-id="49a9d-102">Kapazitäts-und Verfügbarkeitsverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49a9d-102">Capacity and availability management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49a9d-103">_**Letztes Änderungsdatum des Themas:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="49a9d-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="49a9d-104">Der Zweck des Kapazitätsmanagements und des Verfügbarkeits Managements besteht in der Messung und Steuerung der Systemleistung.</span><span class="sxs-lookup"><span data-stu-id="49a9d-104">The purpose of capacity management and availability management is to measure and control system performance.</span></span> <span data-ttu-id="49a9d-105">Wir empfehlen, dass Sie die Verwaltungsverfahren für die Kapazitätsverwaltung und die Verfügbarkeit implementieren, damit Sie die Systemleistung messen und steuern können.</span><span class="sxs-lookup"><span data-stu-id="49a9d-105">We recommend that you implement capacity management and availability management procedures so that you can measure and control system performance.</span></span> <span data-ttu-id="49a9d-106">Sie müssen wissen, ob das System verfügbar ist und ob es die aktuellen und die voraussichtlichen Anforderungen verarbeiten kann, indem Sie Baselines festlegen und das System überwachen, um nach Trends zu suchen.</span><span class="sxs-lookup"><span data-stu-id="49a9d-106">You have to know whether the system is available and if it can handle the current and the projected demands by setting baselines and monitoring the system to look for trends.</span></span>

<div>

## <a name="capacity-management"></a><span data-ttu-id="49a9d-107">Kapazitätsverwaltung</span><span class="sxs-lookup"><span data-stu-id="49a9d-107">Capacity management</span></span>

<span data-ttu-id="49a9d-108">Das Kapazitätsmanagement umfasst die Planung, die Größenanpassung und die Steuerung der Servicekapazität, um sicherzustellen, dass die in Ihrer SLA angegebenen Mindestleistungen überschritten werden.</span><span class="sxs-lookup"><span data-stu-id="49a9d-108">Capacity management involves planning, sizing, and controlling service capacity to help guarantee that the minimum performance levels specified in your SLA are exceeded.</span></span> <span data-ttu-id="49a9d-109">Eine gute Kapazitätsverwaltung sorgt dafür, dass Sie IT-Services zu einem vertretbaren Preis bereitstellen und dennoch die in ihren SLAs mit dem Client definierten Leistungsniveaus erfüllen können.</span><span class="sxs-lookup"><span data-stu-id="49a9d-109">Good capacity management helps ensure that you can provide IT services at a reasonable cost and still meet the levels of performance defined in your SLAs with the client.</span></span> <span data-ttu-id="49a9d-110">Diese Kriterien können Folgendes umfassen:</span><span class="sxs-lookup"><span data-stu-id="49a9d-110">These criteria can include the following:</span></span>

  - <span data-ttu-id="49a9d-111">**Systemantwortzeit**   Dies ist die Zeit, die das System für typische Aktionen benötigt.</span><span class="sxs-lookup"><span data-stu-id="49a9d-111">**System Response Time**   This is the measured time that the system takes to do typical actions.</span></span> <span data-ttu-id="49a9d-112">Beispiele sind die Zeit, die erforderlich ist, damit die Audio/Video-Serverrolle Audio/Video-Datenverkehr verarbeitet, die Zeitdauer, die für einen Client zum Erstellen und teilnehmen an einer Konferenz erforderlich ist, oder die Zeit, die für die Aktualisierung von Anwesenheitsinformationen in allen Watcher-Clients benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="49a9d-112">Examples include the time that is required for the audio/video server role to process audio/video traffic, the time that is required for a client to create and join a conference, or the time taken for presence to be updated in all watcher clients.</span></span>

  - <span data-ttu-id="49a9d-113">**Speicherkapazität**   hierbei handelt es sich um die Kapazität eines Speichersystems, ob es sich um eine Inhaltsdatenbank, ein Sicherungsmedium oder ein lokales Laufwerk handelt.</span><span class="sxs-lookup"><span data-stu-id="49a9d-113">**Storage Capacity**   This is the capacity of a storage system, whether it is a content database, a backup device, or a local drive.</span></span> <span data-ttu-id="49a9d-114">Beispiele sind die maximale Menge an Speicherplatz, die pro Website bereitgestellt werden soll, und der Zeitpunkt, zu dem Sicherungen gespeichert werden sollen, bevor Sie überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="49a9d-114">Examples include the maximum amount of storage space to be provided per site and the time that backups should be stored before they are overwritten.</span></span>

<span data-ttu-id="49a9d-115">Das Anpassen der Kapazität ist häufig ein Fall, um sicherzustellen, dass genügend physische Ressourcen wie Speicherplatz und Netzwerkbandbreite verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="49a9d-115">Adjusting capacity is frequently a case of making sure that enough physical resources are available, such as disk space and network bandwidth.</span></span> <span data-ttu-id="49a9d-116">In der folgenden Tabelle sind typische Lösungen für kapazitätsbezogene Probleme aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="49a9d-116">The following table lists typical resolutions for capacity-related issues.</span></span>

### <a name="typical-resolutions-for-capacity-related-issues"></a><span data-ttu-id="49a9d-117">Typische Lösungen für kapazitätsbezogene Probleme</span><span class="sxs-lookup"><span data-stu-id="49a9d-117">Typical resolutions for capacity-related issues</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="49a9d-118">Problem</span><span class="sxs-lookup"><span data-stu-id="49a9d-118">Issue</span></span></th>
<th><span data-ttu-id="49a9d-119">Mögliche Auflösung</span><span class="sxs-lookup"><span data-stu-id="49a9d-119">Possible resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="49a9d-120">Remote Benutzer mit schlechter Audio-/Videoleistung</span><span class="sxs-lookup"><span data-stu-id="49a9d-120">Remote users having poor audio/video performance</span></span></p></td>
<td><p><span data-ttu-id="49a9d-121">Überprüfen Sie, ob für die WAN-Links geeignete Bandbreite verfügbar ist und ob QoS aktiviert und entsprechend konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="49a9d-121">Check to see whether appropriate bandwidth is available on the WAN links and if QoS is enabled and appropriately configured.</span></span> <span data-ttu-id="49a9d-122">Überprüfen Sie die QoE-Daten.</span><span class="sxs-lookup"><span data-stu-id="49a9d-122">Check QoE data.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49a9d-123">Die Gesamtantwort der lync-Umgebung ist langsam.</span><span class="sxs-lookup"><span data-stu-id="49a9d-123">Overall response of the Lync environment is slow.</span></span></p></td>
<td><p><span data-ttu-id="49a9d-124">Führen Sie Tests aus, um zu überprüfen, ob die vorhandenen Front-End-Server die Auslastung bewältigen können.</span><span class="sxs-lookup"><span data-stu-id="49a9d-124">Run tests to check that the existing front-end servers can deal with the load.</span></span> <span data-ttu-id="49a9d-125">Führen Sie bei Bedarf einen neuen Front-End-Server ein. Überprüfen Sie die Antwortzeiten der SQL-Datenbank, und beheben Sie die Ursachen für Verzögerungen (beispielsweise verbessern Sie die Datenträger-e/a).</span><span class="sxs-lookup"><span data-stu-id="49a9d-125">Introduce a new front-end server if it is needed.Check SQL database response times and fix the causes for the delays (for example, improve disk I/O).</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="49a9d-126">Ausführlichere Informationen zur Problembehandlung sind im lync Server-Netzwerkhandbuch beschrieben.</span><span class="sxs-lookup"><span data-stu-id="49a9d-126">Troubleshooting in greater detail is covered in the Lync Server Networking Guide.</span></span>

<span data-ttu-id="49a9d-127">Die Kapazität wird von der Systemkonfiguration beeinflusst und hängt von physikalischen Ressourcen wie Netzwerkbandbreite ab.</span><span class="sxs-lookup"><span data-stu-id="49a9d-127">Capacity is affected by system configuration and depends on physical resources such as network bandwidth.</span></span> <span data-ttu-id="49a9d-128">Wenn beispielsweise eine lync-Umgebung so konfiguriert ist, dass nächtlich eine vollständige Sicherung durchgeführt wird, müssen Sie sicherstellen, dass die Auswirkungen auf die interaktive Leistung von Endbenutzern minimiert werden.</span><span class="sxs-lookup"><span data-stu-id="49a9d-128">For example, if a Lync environment is configured to perform a full backup nightly, care must be taken to help guarantee that the effect on the interactive performance experienced by end-users is minimized.</span></span>

<span data-ttu-id="49a9d-129">Capacity Management ist der Prozess, bei dem die Kapazität eines Systems innerhalb akzeptabler Ebenen bleibt und die folgenden Probleme behoben werden:</span><span class="sxs-lookup"><span data-stu-id="49a9d-129">Capacity management is the process of keeping the capacity of a system within acceptable levels and addresses the following issues:</span></span>

  - <span data-ttu-id="49a9d-130">**Die Reaktion auf Änderungen**   an den Anforderungen der Kapazitätsanforderungen muss angepasst werden, um Änderungen am System oder in der Organisation Rechnung zu tragen.</span><span class="sxs-lookup"><span data-stu-id="49a9d-130">**Reacting to changes in requirements**   Capacity requirements have to be adjusted to account for changes in the system or the organization.</span></span> <span data-ttu-id="49a9d-131">Wenn Ihre Umgebung beispielsweise entscheidet, Enterprise-VoIP zu implementieren, ist die Anzahl und Platzierung von Vermittlungsservern und PSTN-Gateways (Public Switched Telephone Network) sehr wichtig.</span><span class="sxs-lookup"><span data-stu-id="49a9d-131">For example, if your environment decides to implement Enterprise Voice, the number and placement of Mediation Servers and public switched telephone network (PSTN) gateways will be very important.</span></span> <span data-ttu-id="49a9d-132">Wenn Sie SIP-Trunking (Session Initiation Protocol) oder Direct SIP ausführen, wird das Gesamtdesign erheblich geändert, um die beste Leistung für Unternehmens-VoIP zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="49a9d-132">If you'll be doing Session Initiation Protocol (SIP) trunking or direct SIP, the overall design will be significantly changed to provide the best Enterprise Voice performance.</span></span>

  - <span data-ttu-id="49a9d-133">**Voraussagen zukünftiger Anforderungen**   einige Kapazitätsanforderungen ändern sich im Laufe der Zeit vorhersehbar.</span><span class="sxs-lookup"><span data-stu-id="49a9d-133">**Predicting future requirements**   Some capacity requirements change predictably over time.</span></span> <span data-ttu-id="49a9d-134">Durch Nachverfolgen von Trends können Sie Upgrades im Voraus planen.</span><span class="sxs-lookup"><span data-stu-id="49a9d-134">By tracking trends you can plan upgrades in advance.</span></span> <span data-ttu-id="49a9d-135">Beispielsweise muss die verfügbare Bandbreite zwischen verschiedenen lync-Websites überwacht werden, um einen Basisplan zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="49a9d-135">For example, available bandwidth between various Lync sites must be monitored to create a baseline.</span></span> <span data-ttu-id="49a9d-136">Mit diesem Basisplan können Sie Vorhersagen, wann Sie diesen Links mehr Bandbreite hinzufügen müssen, da sich die Anzahl der Benutzer in diesen Remotestandorten mit der Zeit vergrößert.</span><span class="sxs-lookup"><span data-stu-id="49a9d-136">This baseline will allow you to predict when you have to add more bandwidth to these links as user count in these remote sites increases with time.</span></span>

</div>

<div>

## <a name="availability-management"></a><span data-ttu-id="49a9d-137">Verfügbarkeitsverwaltung</span><span class="sxs-lookup"><span data-stu-id="49a9d-137">Availability management</span></span>

<span data-ttu-id="49a9d-138">Bei der Verfügbarkeitsverwaltung wird sichergestellt, dass jeder IT-Dienst konsistent und kostengünstig den konsistenten, zuverlässigen Service bereitstellt, der vom Kunden benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="49a9d-138">Availability management is the process of making sure that any IT service consistently and cost effectively delivers the level of consistent, reliable service that is required by the customer.</span></span> <span data-ttu-id="49a9d-139">Die Verfügbarkeitsverwaltung befasst sich mit dem Minimieren des Service Verlusts und mit der Sicherstellung, dass entsprechende Maßnahmen ergriffen werden, wenn der Dienst verloren geht.</span><span class="sxs-lookup"><span data-stu-id="49a9d-139">Availability management deals with minimizing loss of service and with making sure that appropriate action is taken if service is lost.</span></span> <span data-ttu-id="49a9d-140">In einer lync-Umgebung sind Sie möglicherweise besorgt darüber, ob der Enterprise-VoIP-Dienst verfügbar ist, ob Benutzer an geplanten Konferenzen teilnehmen können usw.</span><span class="sxs-lookup"><span data-stu-id="49a9d-140">In a Lync environment, you may be concerned about whether the Enterprise Voice service is available, whether users can join scheduled conferences, and so on.</span></span> <span data-ttu-id="49a9d-141">Eine SLA definiert eine akzeptable Häufigkeit und Dauer von Ausfällen und ermöglicht bestimmte Zeiträume, wenn das System für geplante Wartungsarbeiten nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="49a9d-141">An SLA defines an acceptable frequency and length of outages and allows for certain periods when the system is unavailable for planned maintenance.</span></span>

<span data-ttu-id="49a9d-142">Wenn Sie Ihrem Managementberichte zur Verfügbarkeit von Systemen bereitstellen müssen oder wenn Sie finanzielle oder andere Strafen mit fehlenden Verfügbarkeitszielen verbunden haben, müssen Sie Verfügbarkeitsdaten aufzeichnen.</span><span class="sxs-lookup"><span data-stu-id="49a9d-142">If you have to provide reports to your management about the availability of systems, or if you have financial or other penalties associated with missing availability targets, you must record availability data.</span></span> <span data-ttu-id="49a9d-143">Auch wenn Sie keine derartigen formalen Anforderungen haben, empfiehlt es sich, zumindest zu wissen, wie häufig ein System in einem bestimmten Zeitraum fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="49a9d-143">Even if you do not have such formal requirements, it is a good idea to at least know how frequently a system has failed in a certain time period.</span></span> <span data-ttu-id="49a9d-144">Beispielsweise die Systemverfügbarkeit in den letzten 12 Monaten und die Dauer der Wiederherstellung nach jedem Fehler.</span><span class="sxs-lookup"><span data-stu-id="49a9d-144">For example, system availability in the last 12 months and how long it took to recover from each failure.</span></span> <span data-ttu-id="49a9d-145">Diese Informationen werden Ihnen helfen, die Effektivität Ihres Teams bei der Reaktion auf einen Systemfehler zu messen und zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="49a9d-145">This information will help you measure and improve your team’s effectiveness in responding to a system failure.</span></span> <span data-ttu-id="49a9d-146">Es kann Ihnen auch nützliche Informationen geben, wenn es eine Unstimmigkeit gibt.</span><span class="sxs-lookup"><span data-stu-id="49a9d-146">It can also give you useful information if there is a dispute.</span></span>

<span data-ttu-id="49a9d-147">Im Zusammenhang mit der Verfügbarkeit sind folgende Maßnahmen zu finden:</span><span class="sxs-lookup"><span data-stu-id="49a9d-147">Measures related to availability are as follows:</span></span>

  - <span data-ttu-id="49a9d-148">**Verfügbarkeit**   Dies wird in der Regel als die Zeit ausgedrückt, zu der auf ein System oder einen Dienst zugegriffen werden kann, verglichen mit dem Zeitpunkt, zu dem er abläuft.</span><span class="sxs-lookup"><span data-stu-id="49a9d-148">**Availability**   This is typically expressed as the time that a system or service can be accessed compared to the time that it is down.</span></span> <span data-ttu-id="49a9d-149">Sie wird in der Regel als Prozentsatz ausgedrückt.</span><span class="sxs-lookup"><span data-stu-id="49a9d-149">It is typically expressed as a percentage.</span></span> <span data-ttu-id="49a9d-150">(Möglicherweise werden Verweise auf "drei Neunen" oder "fünf Neunen" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="49a9d-150">(You may see references to “three nines” or “five nines”.</span></span> <span data-ttu-id="49a9d-151">Diese beziehen sich auf die Verfügbarkeit von 99,9 Prozent oder 99,999 Prozent.)</span><span class="sxs-lookup"><span data-stu-id="49a9d-151">These refer to 99.9 percent or 99.999 percent availability.)</span></span>

  - <span data-ttu-id="49a9d-152">**Zuverlässigkeit**   Dies ist ein Maß für die Zeit zwischen Fehlern eines Systems und wird manchmal als Mittelwert (oder Mittelwert) Zeit zwischen Fehlern (MTBF) ausgedrückt.</span><span class="sxs-lookup"><span data-stu-id="49a9d-152">**Reliability**   This is a measure of the time between failures of a system and is sometimes expressed as mean (or average) time between failures (MTBF).</span></span>

  - <span data-ttu-id="49a9d-153">**Zeit zum Reparieren**   Dies ist die Zeit, die für die Wiederherstellung eines Diensts nach einem Fehler aufgetreten ist, und wird häufig als Mittelwert (Mittelwert) für die Reparaturzeit ausgedrückt (MTTR).</span><span class="sxs-lookup"><span data-stu-id="49a9d-153">**Time to Repair**   This is the time taken to recover a service after a failure has occurred and is often expressed as mean (meaning average) time to repair (MTTR).</span></span>

<span data-ttu-id="49a9d-154">Verfügbarkeit, Zuverlässigkeit und Reparaturzeit hängen wie folgt zusammen:</span><span class="sxs-lookup"><span data-stu-id="49a9d-154">Availability, reliability, and time to repair are related as follows:</span></span>

<span data-ttu-id="49a9d-155">**Verfügbarkeit = (MTBF-MTTR)/MTBF**   Wenn beispielsweise ein Server zwei Mal über einen Zeitraum von sechs Monaten nicht verfügbar ist und für durchschnittlich 20 Minuten nicht zur Verfügung steht, beträgt die MTBF drei Monate oder 90 Tage, und die MTTR beträgt 20 Minuten.</span><span class="sxs-lookup"><span data-stu-id="49a9d-155">**Availability = (MTBF – MTTR) / MTBF**   For example, if a server fails two times over a six-month period and is unavailable for an average of 20 minutes, the MTBF is three months or 90 days and the MTTR is 20 minutes.</span></span> <span data-ttu-id="49a9d-156">Daher Verfügbarkeit = (90 Tage – 20 Minuten)/90 Tage = 99,985 Prozent.</span><span class="sxs-lookup"><span data-stu-id="49a9d-156">Therefore, Availability = (90 days – 20 minutes) / 90 days = 99.985 percent.</span></span>

<span data-ttu-id="49a9d-157">Bei der Verfügbarkeitsverwaltung wird sichergestellt, dass die Verfügbarkeit maximiert und innerhalb der in SLAs definierten Parameter beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="49a9d-157">Availability management is the process of making sure that availability is maximized and kept within the parameters that are defined in SLAs.</span></span> <span data-ttu-id="49a9d-158">Die Verfügbarkeitsverwaltung umfasst die folgenden Prozesse:</span><span class="sxs-lookup"><span data-stu-id="49a9d-158">Availability management includes the following processes:</span></span>

  - <span data-ttu-id="49a9d-159">**Überwachung**     der Untersuchung, wann und wie lange Dienste nicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="49a9d-159">**Monitoring**    Examining when and for how long services are unavailable.</span></span>

  - <span data-ttu-id="49a9d-160">\*\*\*\*   Informationen zur Verfügbarkeit von Berichten sollten regelmäßig für Verwaltungs-, Benutzer-und Betriebsteams bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="49a9d-160">**Reporting**   Availability figures should be regularly provided to management, users, and operations teams.</span></span> <span data-ttu-id="49a9d-161">Diese Berichte sollten Trends hervorheben und Bereiche ermitteln, die gut funktionieren, und Bereiche, die berücksichtigt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="49a9d-161">These reports should highlight trends and identify areas that are doing well and areas that require attention.</span></span> <span data-ttu-id="49a9d-162">Der Bericht sollte die Einhaltung der in den SLAs festgelegten Ziele zusammenfassen.</span><span class="sxs-lookup"><span data-stu-id="49a9d-162">The report should summarize compliance with targets set in the SLAs.</span></span>

  - <span data-ttu-id="49a9d-163">**Verbesserung**   wenn die Verfügbarkeit nicht den in den SLAs definierten Zielen entspricht oder der Trend zu einer reduzierten Verfügbarkeit führt, sollte der Verfügbarkeits Verwaltungsprozess Sanierungsschritte planen.</span><span class="sxs-lookup"><span data-stu-id="49a9d-163">**Improvement**   If availability does not meet targets that are defined in the SLAs or where the trend is toward reduced availability, the availability management process should plan remedial steps.</span></span> <span data-ttu-id="49a9d-164">Dazu gehören die Zusammenarbeit mit anderen zuständigen Teams, um Ursachen für Ausfälle hervorzuheben und Sanierungsmaßnahmen zu planen, um eine Wiederholung der Ausfälle zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="49a9d-164">This should include working with other responsible teams to highlight reasons for outages and to plan remedial actions to prevent a recurrence of the outages.</span></span>

<span data-ttu-id="49a9d-165">Kapazitäts-und Verfügbarkeits Messungen sind sich wiederholende Aufgaben, die ideal für automatisierte Tools und Skripts wie Microsoft System Center Operations Manager (vormals Microsoft Operations Manager) geeignet sind, die später in diesem Dokument erläutert werden.</span><span class="sxs-lookup"><span data-stu-id="49a9d-165">Capacity and availability measurements are repetitive tasks that are ideally suited to automated tools and scripts such as Microsoft System Center Operations Manager (formerly Microsoft Operations Manager), which is discussed later in this document.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="49a9d-166">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="49a9d-166">See Also</span></span>


[<span data-ttu-id="49a9d-167">Überwachen von lync Server 2013 mit System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="49a9d-167">Monitoring Lync Server 2013 with System Center Operations Manager</span></span>](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

