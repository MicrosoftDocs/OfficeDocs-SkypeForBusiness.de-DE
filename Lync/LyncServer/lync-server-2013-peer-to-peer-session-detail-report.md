---
title: 'Lync Server 2013: Detail Bericht über Peer-to-Peer-Sitzungen'
description: 'Lync Server 2013: Detail Bericht über Peer-to-Peer-Sitzungen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Session Detail Report
ms:assetid: 6be1d676-68f7-4a53-a72a-de73296c5571
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558659(v=OCS.15)
ms:contentKeyID: 48184416
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e712225fddabb646cc3b862f59601857a7df8eff
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557281"
---
# <a name="peer-to-peer-session-detail-report-in-lync-server-2013"></a><span data-ttu-id="27f3d-103">Detail Bericht über Peer-to-Peer-Sitzungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27f3d-103">Peer-to-Peer Session Detail Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27f3d-104">_**Letztes Änderungsstand des Themas:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="27f3d-104">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="27f3d-p101">Der Detailbericht über Peer-zu-Peer-Sitzungen gibt detaillierte Informationen über eine Peer-zu-Peer-Sitzung zurück. Wenn Sie beispielsweise eine Sofortnachrichtensitzung auswählen, gibt der Bericht Ihnen die Anzahl an Nachrichten an, die jeweils von den beiden an der Sitzung beteiligten Benutzern gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="27f3d-p101">The Peer-to-Peer Session Detail Report returns detailed information about a peer-to-peer session. For example, if you select an instant messaging session, the report will tell you the number of messages sent by each of the two users in the session.</span></span>

<div>

## <a name="accessing-the-peer-to-peer-session-detail-report"></a><span data-ttu-id="27f3d-107">Zugriff auf den Detailbericht über Peer-zu-Peer-Sitzungen</span><span class="sxs-lookup"><span data-stu-id="27f3d-107">Accessing the Peer-to-Peer Session Detail Report</span></span>

<span data-ttu-id="27f3d-108">Sie können über die folgenden Berichte (die alle über die Startseite für Überwachungsberichte aufgerufen werden können) auf den  Detailbericht über Peer-zu-Peer-Sitzungen zugreifen:</span><span class="sxs-lookup"><span data-stu-id="27f3d-108">The Peer-to-Peer Session Detail Report can be accessed from any of the following reports (all of which can be accessed from the Monitoring Reports home page):</span></span>

  - <span data-ttu-id="27f3d-109">Inventurbericht über IP-Telefone</span><span class="sxs-lookup"><span data-stu-id="27f3d-109">IP Phone Inventory Report</span></span>

  - <span data-ttu-id="27f3d-110">Bericht über Benutzeraktivität</span><span class="sxs-lookup"><span data-stu-id="27f3d-110">User Activity Report</span></span>

  - <span data-ttu-id="27f3d-111">Bericht über Anrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="27f3d-111">Call Admission Control Report</span></span>

  - <span data-ttu-id="27f3d-112">Fehlerlistenbericht</span><span class="sxs-lookup"><span data-stu-id="27f3d-112">Failure List Report</span></span>

<span data-ttu-id="27f3d-113">Innerhalb des Detail Berichts über Peer-to-Peer-Sitzungen können Sie auf den [Diagnosebericht in lync Server 2013](lync-server-2013-diagnostic-report.md) zugreifen, indem Sie auf die Metrik für den Diagnosebericht (Details) klicken.</span><span class="sxs-lookup"><span data-stu-id="27f3d-113">From within the Peer-to-Peer Session Detail Report you can access the [Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md) by clicking the Diagnostic Report (Details) metric.</span></span> <span data-ttu-id="27f3d-114">Sie können zudem auf den Bericht über häufigste Fehler zugreifen, indem Sie auf eine der folgenden beiden Metriken klicken:</span><span class="sxs-lookup"><span data-stu-id="27f3d-114">You can also access the Top Failures Report by clicking either of these two metrics:</span></span>

  - <span data-ttu-id="27f3d-115">Antwort</span><span class="sxs-lookup"><span data-stu-id="27f3d-115">Response</span></span>

  - <span data-ttu-id="27f3d-116">Diagnose-ID</span><span class="sxs-lookup"><span data-stu-id="27f3d-116">Diagnostic ID</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-session-detail-report"></a><span data-ttu-id="27f3d-117">Optimale Verwendung des Detailberichts über Peer-zu-Peer-Sitzungen</span><span class="sxs-lookup"><span data-stu-id="27f3d-117">Making the Best Use of the Peer-to-Peer session Detail Report</span></span>

<span data-ttu-id="27f3d-p103">Der Detailbericht über Peer-zu-Peer-Sitzungen enthält zahlreiche Metriken, mit denen die Systemadministratoren möglicherweise zum Teil nicht vertraut sind. Häufig können Sie jedoch ein Tooltip mit einer kurzen Beschreibung der Metrik anzeigen, indem Sie den Mauszeiger über die Bezeichnung der jeweiligen Metrik bewegen.</span><span class="sxs-lookup"><span data-stu-id="27f3d-p103">The Peer-to-Peer Session Detail Report includes a large number of metrics, many of which might not be familiar to system administrators. Often-times, however, you can view a tooltip that offers a brief description of that metric simply by holding your mouse over the metric label.</span></span>

<span data-ttu-id="27f3d-p104">Beachten Sie, dass die tatsächlichen Metriken, die in einem bestimmten Bericht angezeigt werden, von der ausgewählten Peer-zu-Peer-Sitzung abhängen. So wird für eine Audio-/Videositzung ein anderer Satz an Metriken ausgegeben als für eine Sofortnachrichtensitzung.</span><span class="sxs-lookup"><span data-stu-id="27f3d-p104">Note that the actual metrics shown on a given report will depend on the type of peer-to-peer session you selected. An audio/video session will report a different set of metrics than an instant messaging session.</span></span>

<span data-ttu-id="27f3d-122">Sie können den Mauszeiger auch über die Antwortcode- und Diagnose-ID-Metriken bewegen, um eine Beschreibung der folgenden Werte anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="27f3d-122">You can also hold your mouse over the Response code and Diagnostic ID metrics in order to obtain a description of those values:</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="27f3d-123">Filter</span><span class="sxs-lookup"><span data-stu-id="27f3d-123">Filters</span></span>

<span data-ttu-id="27f3d-p105">Keine. Der Detailbericht über Peer-zu-Peer-Sitzungen kann nicht gefiltert werden.</span><span class="sxs-lookup"><span data-stu-id="27f3d-p105">None. You cannot filter the Peer-to-Peer Session Detail Report.</span></span>

</div>

<div>

## <a name="session-information-metrics"></a><span data-ttu-id="27f3d-126">Sitzungsinformationen – Metriken</span><span class="sxs-lookup"><span data-stu-id="27f3d-126">Session Information Metrics</span></span>

<span data-ttu-id="27f3d-127">In der folgenden Tabelle sind die Informationen aufgelistet, die im Detailbericht über Peer-zu-Peer-Sitzungen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="27f3d-127">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each session.</span></span>

### <a name="session-information-metrics"></a><span data-ttu-id="27f3d-128">Sitzungsinformationen – Metriken</span><span class="sxs-lookup"><span data-stu-id="27f3d-128">Session Information Metrics</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="27f3d-129">Name</span><span class="sxs-lookup"><span data-stu-id="27f3d-129">Name</span></span></th>
<th><span data-ttu-id="27f3d-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="27f3d-130">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27f3d-131"><strong>Pool-FQDN</strong></span><span class="sxs-lookup"><span data-stu-id="27f3d-131"><strong>Pool FQDN</strong></span></span></p></td>
<td><p><span data-ttu-id="27f3d-132">Vollqualifizierter Domänenname (FQDN) des Registrar-Pools oder Edgeservers in der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="27f3d-132">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27f3d-133"><strong>Zeitpunkt der Einladung</strong></span><span class="sxs-lookup"><span data-stu-id="27f3d-133"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="27f3d-134">Datum und Uhrzeit, an dem bzw. zu der die Sitzungseinladung ursprünglich gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="27f3d-134">Date and time the session invitation was originally sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27f3d-135"><strong>Antwortzeit</strong></span><span class="sxs-lookup"><span data-stu-id="27f3d-135"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="27f3d-136">Datum und Uhrzeit, an dem bzw. zu der die Annahme der Einladung empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="27f3d-136">Date and time that the invitation acceptance was received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27f3d-137"><strong>Von Benutzer</strong></span><span class="sxs-lookup"><span data-stu-id="27f3d-137"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="27f3d-138">SIP-Adresse des Benutzers, der die Sitzung initiiert hat.</span><span class="sxs-lookup"><span data-stu-id="27f3d-138">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27f3d-139"><strong>Von Benutzer-Agent</strong></span><span class="sxs-lookup"><span data-stu-id="27f3d-139"><strong>From user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="27f3d-140">Die vom Endpunkt des Benutzers verwendete Software, der die Sitzung initiiert hat.</span><span class="sxs-lookup"><span data-stu-id="27f3d-140">Software used by the endpoint of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27f3d-141"><strong>Von Benutzer intern</strong></span><span class="sxs-lookup"><span data-stu-id="27f3d-141"><strong>Is From user internal</strong></span></span></p></td>
<td><p><span data-ttu-id="27f3d-142">Gibt an, ob der Benutzer, der die Sitzung initiiert hat, am internen Netzwerk angemeldet war.</span><span class="sxs-lookup"><span data-stu-id="27f3d-142">Indicates whether the user who initiated the session was logged on to the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27f3d-143"><strong>Von Benutzer mit Telefonapparat</strong></span><span class="sxs-lookup"><span data-stu-id="27f3d-143"><strong>Is From user integrated with desk phone</strong></span></span></p></td>
<td><p><span data-ttu-id="27f3d-144">Gibt an, ob der Endpunkt des Benutzers, der die Sitzung initiiert hat, mit seinem Desktoptelefon integriert ist.</span><span class="sxs-lookup"><span data-stu-id="27f3d-144">Indicates whether the endpoint used by the user who initiated the session is integrated with his or her desktop phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27f3d-145"><strong>Sitzungspriorität</strong></span><span class="sxs-lookup"><span data-stu-id="27f3d-145"><strong>Session Priority</strong></span></span></p></td>
<td><p><span data-ttu-id="27f3d-p106">Die der Sitzung zugewiesene Priorität. Gültige Prioritäten umfassen "Unbekannt", "Nicht dringend", "Normal", "Dringend" und "Notfall".</span><span class="sxs-lookup"><span data-stu-id="27f3d-p106">Priority assigned to the session. Valid priorities are: Unknown; Non-Urgent; Normal; Urgent; and Emergency.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27f3d-148"><strong>Antwortcode</strong></span><span class="sxs-lookup"><span data-stu-id="27f3d-148"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="27f3d-149">Bei fehlgeschlagener Sitzung gesendeter SIP-Antwortcode.</span><span class="sxs-lookup"><span data-stu-id="27f3d-149">SIP response code sent when the session failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27f3d-150"><strong>Front-End</strong></span><span class="sxs-lookup"><span data-stu-id="27f3d-150"><strong>Front end</strong></span></span></p></td>
<td><p><span data-ttu-id="27f3d-151">Name des in der Konferenz verwendeten Front-End-Servers.</span><span class="sxs-lookup"><span data-stu-id="27f3d-151">Name of the Front End Server used in the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27f3d-152"><strong>Zeitpunkt der Erfassung</strong></span><span class="sxs-lookup"><span data-stu-id="27f3d-152"><strong>Capture time</strong></span></span></p></td>
<td><p><span data-ttu-id="27f3d-153">Datum und Uhrzeit, an dem bzw. zu der die Sitzungsinformationen erfasst wurden.</span><span class="sxs-lookup"><span data-stu-id="27f3d-153">Date and time that the session information was recorded.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27f3d-154"><strong>Endzeit</strong></span><span class="sxs-lookup"><span data-stu-id="27f3d-154"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="27f3d-155">Datum und Uhrzeit, an dem bzw. zu der die Sitzung endete.</span><span class="sxs-lookup"><span data-stu-id="27f3d-155">Date and time the session ended.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27f3d-156"><strong>An Benutzer</strong></span><span class="sxs-lookup"><span data-stu-id="27f3d-156"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="27f3d-157">SIP-Adresse des Benutzers, der zur Teilnahme an der Sitzung eingeladen wurde.</span><span class="sxs-lookup"><span data-stu-id="27f3d-157">SIP address of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27f3d-158"><strong>To user agent</strong> (An Benutzer-Agent)</span><span class="sxs-lookup"><span data-stu-id="27f3d-158"><strong>To user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="27f3d-159">Die vom Endpunkt des Benutzers verwendete Software, der zur Teilnahme an der Sitzung eingeladen wurde.</span><span class="sxs-lookup"><span data-stu-id="27f3d-159">Software used by the endpoint of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27f3d-160"><strong>An Benutzer intern</strong></span><span class="sxs-lookup"><span data-stu-id="27f3d-160"><strong>Is To user internal</strong></span></span></p></td>
<td><p><span data-ttu-id="27f3d-161">Gibt an, ob der Benutzer, der zur Teilnahme an der Sitzung eingeladen wurde, am internen Netzwerk angemeldet war.</span><span class="sxs-lookup"><span data-stu-id="27f3d-161">Indicates whether the user who was invited to the session was logged on to the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27f3d-162"><strong>An Benutzer mit Telefonapparat</strong></span><span class="sxs-lookup"><span data-stu-id="27f3d-162"><strong>Is To user integrated with desk phone</strong></span></span></p></td>
<td><p><span data-ttu-id="27f3d-163">Gibt an, ob der Endpunkt des Benutzers, der zur Teilnahme an der Sitzung eingeladen wurde, mit seinem Desktoptelefon integriert ist.</span><span class="sxs-lookup"><span data-stu-id="27f3d-163">Indicates whether the endpoint used by the user who was invited to the session is integrated with his or her desktop phone.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27f3d-164"><strong>Wiederholungsversuch der Sitzung</strong></span><span class="sxs-lookup"><span data-stu-id="27f3d-164"><strong>Is retried session</strong></span></span></p></td>
<td><p><span data-ttu-id="27f3d-165">Gibt an, ob die Sitzung ein Wiederholungsversuch einer zuvor fehlgeschlagenen Sitzung ist.</span><span class="sxs-lookup"><span data-stu-id="27f3d-165">Indicates whether the session is an attempt to retry a session that previously failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27f3d-166"><strong>Diagnose-ID</strong></span><span class="sxs-lookup"><span data-stu-id="27f3d-166"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="27f3d-p107">Eindeutige ID (in der Form eines Headers vom Typ "ms-diagnostics"), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt. Halten Sie den Mauszeiger über die ID-Nummer, um zusätzliche Information zu dieser ID anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="27f3d-p107">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Hold the mouse over the ID number to view additional information about that ID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-modalities"></a><span data-ttu-id="27f3d-169">Metriken für Modalitäten</span><span class="sxs-lookup"><span data-stu-id="27f3d-169">Metrics for Modalities</span></span>

<span data-ttu-id="27f3d-170">In der folgenden Tabelle sind die Informationen aufgelistet, die im Detailbericht über Peer-zu-Peer-Sitzungen zu jeder Sitzungsmodalität angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="27f3d-170">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each session modality.</span></span>

### <a name="metrics-for-modalities"></a><span data-ttu-id="27f3d-171">Metriken für Modalitäten</span><span class="sxs-lookup"><span data-stu-id="27f3d-171">Metrics for Modalities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="27f3d-172">Name</span><span class="sxs-lookup"><span data-stu-id="27f3d-172">Name</span></span></th>
<th><span data-ttu-id="27f3d-173">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="27f3d-173">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="27f3d-174">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="27f3d-174">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27f3d-175"><strong>Modalitäten</strong></span><span class="sxs-lookup"><span data-stu-id="27f3d-175"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="27f3d-176">Nein</span><span class="sxs-lookup"><span data-stu-id="27f3d-176">No</span></span></p></td>
<td><p><span data-ttu-id="27f3d-p108">In der Sitzung verwendete Modalitäten, z. B. Instant Messaging (IM), Audio oder Dateiübertragung.</span><span class="sxs-lookup"><span data-stu-id="27f3d-p108">Modalities used in the session. For example, instant messaging (IM) or file transfer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27f3d-179"><strong>Nachrichten "Von Benutzer"</strong></span><span class="sxs-lookup"><span data-stu-id="27f3d-179"><strong>From user messages</strong></span></span></p></td>
<td><p><span data-ttu-id="27f3d-180">Nein</span><span class="sxs-lookup"><span data-stu-id="27f3d-180">No</span></span></p></td>
<td><p><span data-ttu-id="27f3d-181">Anzahl der gesendeten Nachrichten des Benutzers, der die Sitzung initiiert hat.</span><span class="sxs-lookup"><span data-stu-id="27f3d-181">Number of messages sent by the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27f3d-182"><strong>Nachrichten "An Benutzer"</strong></span><span class="sxs-lookup"><span data-stu-id="27f3d-182"><strong>To user messages</strong></span></span></p></td>
<td><p><span data-ttu-id="27f3d-183">Nein</span><span class="sxs-lookup"><span data-stu-id="27f3d-183">No</span></span></p></td>
<td><p><span data-ttu-id="27f3d-184">Anzahl der gesendeten Nachrichten des Benutzers, der zur Teilnahme an der Sitzung eingeladen wurde.</span><span class="sxs-lookup"><span data-stu-id="27f3d-184">Number of messages sent by the user who was invited to join the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-diagnostic-reports"></a><span data-ttu-id="27f3d-185">Metriken für Diagnoseberichte</span><span class="sxs-lookup"><span data-stu-id="27f3d-185">Metrics for Diagnostic Reports</span></span>

<span data-ttu-id="27f3d-186">In der folgenden Tabelle sind die Informationen aufgelistet, die im Detailbericht über Peer-zu-Peer-Sitzungen zu jeden Diagnosebericht angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="27f3d-186">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each diagnostic report.</span></span>

### <a name="metrics-for-diagnostic-reports"></a><span data-ttu-id="27f3d-187">Metriken für Diagnoseberichte</span><span class="sxs-lookup"><span data-stu-id="27f3d-187">Metrics for Diagnostic Reports</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="27f3d-188">Name</span><span class="sxs-lookup"><span data-stu-id="27f3d-188">Name</span></span></th>
<th><span data-ttu-id="27f3d-189">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="27f3d-189">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="27f3d-190">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="27f3d-190">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27f3d-191"><strong>Detail</strong></span><span class="sxs-lookup"><span data-stu-id="27f3d-191"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="27f3d-192">Nein</span><span class="sxs-lookup"><span data-stu-id="27f3d-192">No</span></span></p></td>
<td><p><span data-ttu-id="27f3d-193">Klicken Sie auf dieses Element, um den Diagnosebericht für die Sitzung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="27f3d-193">When you click this item, the report shows the Diagnostic Report for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27f3d-194"><strong>Berichtszeit</strong></span><span class="sxs-lookup"><span data-stu-id="27f3d-194"><strong>Report time</strong></span></span></p></td>
<td><p><span data-ttu-id="27f3d-195">Nein</span><span class="sxs-lookup"><span data-stu-id="27f3d-195">No</span></span></p></td>
<td><p><span data-ttu-id="27f3d-196">Datum und Uhrzeit, an dem bzw. zu der der Bericht erfasst wurde.</span><span class="sxs-lookup"><span data-stu-id="27f3d-196">Date and time the report was recorded.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27f3d-197"><strong>Anforderung</strong></span><span class="sxs-lookup"><span data-stu-id="27f3d-197"><strong>Request</strong></span></span></p></td>
<td><p><span data-ttu-id="27f3d-198">Nein</span><span class="sxs-lookup"><span data-stu-id="27f3d-198">No</span></span></p></td>
<td><p><span data-ttu-id="27f3d-p109">SIP-Anforderungstyp, z. B. INVITE oder BYE.</span><span class="sxs-lookup"><span data-stu-id="27f3d-p109">SIP request type. For example, INVITE or BYE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27f3d-201"><strong>Diagnose-ID</strong></span><span class="sxs-lookup"><span data-stu-id="27f3d-201"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="27f3d-202">Nein</span><span class="sxs-lookup"><span data-stu-id="27f3d-202">No</span></span></p></td>
<td><p><span data-ttu-id="27f3d-203">Eindeutige ID (in der Form eines Headers vom Typ "ms-diagnostics"), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="27f3d-203">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27f3d-204"><strong>Inhaltstyp</strong></span><span class="sxs-lookup"><span data-stu-id="27f3d-204"><strong>Content type</strong></span></span></p></td>
<td><p><span data-ttu-id="27f3d-205">Nein</span><span class="sxs-lookup"><span data-stu-id="27f3d-205">No</span></span></p></td>
<td><p><span data-ttu-id="27f3d-p110">In der Konferenz verwendeter Medieninhaltstyp. Ein gängiger Inhaltstyp ist beispielsweise "Application/sdp". SDP (Session Description Protocol) ist ein Standardinternetprotokoll, das für Sitzungsankündigungen, Sitzungseinladungen und andere Formen des Multimediasitzungsaufbaus verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="27f3d-p110">Type of media content used in the conference. For example, a common content type is Application/sdp. Session Description Protocol (SDP) is a standard Internet protocol used for session announcements, session invitations, and other forms of multimedia session initiation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27f3d-209"><strong>Berichtet von</strong></span><span class="sxs-lookup"><span data-stu-id="27f3d-209"><strong>Reported by</strong></span></span></p></td>
<td><p><span data-ttu-id="27f3d-210">Nein</span><span class="sxs-lookup"><span data-stu-id="27f3d-210">No</span></span></p></td>
<td><p><span data-ttu-id="27f3d-211">Computer (d. h. Client oder Server), der das Problem berichtet hat.</span><span class="sxs-lookup"><span data-stu-id="27f3d-211">Computer (that is, client or server) that reported the problem.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

