---
title: 'Lync Server 2013: Konferenz Detail Bericht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Detail Report
ms:assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204728(v=OCS.15)
ms:contentKeyID: 48183565
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 670696a0945464486e0872b17df330a6ca8140b7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188608"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conference-detail-report-in-lync-server-2013"></a><span data-ttu-id="3a89b-102">Konferenz Detail Bericht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3a89b-102">Conference Detail Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3a89b-103">_**Letztes Änderungsstand des Themas:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="3a89b-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="3a89b-p101">Der detaillierte Konferenzbericht enthält ausführliche Informationen zu allen Benutzern, die an einer Konferenz teilgenommen haben. Sie können beispielsweise Informationen wie Datum und Uhrzeit, an dem bzw. zu der ein Benutzer einer Konferenz beigetreten ist und die Konferenz verlassen hat, sowie den Benutzer-Agent des Endpunkts anzeigen, mit dem der Benutzer mit der Konferenz verbunden wurde. Darüber hinaus können Sie Informationen zu der Rolle des Benutzers in den einzelnen Konferenzen (z. B. Referent oder Teilnehmer) anzeigen. Der vielleicht wichtigste Aspekt ist, dass Sie auf einen Blick erkennen können, welche Benutzer der Konferenz erfolgreich beigetreten und sie abgeschlossen haben und welche Benutzer der Konferenz nicht beitreten konnten und sie daher nicht abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="3a89b-p101">The Conference Detail Report provides detailed information about all the users who participated in a conference. For example, you can see such information as the date and time that a user joined the conference, the date and time that the user left the conference, and the user agent of the endpoint that was used to connect that user to the conference. You can also see information the user's role in each conference (for example, Presenter or Attendee). Perhaps most important, you get quickly see which users successfully join and complete the conference, and which users were not able to successfully join and complete the conference.</span></span>

<div>

## <a name="accessing-the-conference-detail-report"></a><span data-ttu-id="3a89b-108">Zugreifen auf den detaillierten Konferenzbericht</span><span class="sxs-lookup"><span data-stu-id="3a89b-108">Accessing the Conference Detail Report</span></span>

<span data-ttu-id="3a89b-109">Auf den detaillierten Konferenzbericht kann über die folgenden Berichte zugegriffen werden:</span><span class="sxs-lookup"><span data-stu-id="3a89b-109">The Conference Detail Report can be accessed from the following reports:</span></span>

  - <span data-ttu-id="3a89b-110">Der [anrufsteuerungsbericht in lync Server 2013](lync-server-2013-call-admission-control-report.md) (durch Klicken auf die Metrik "Detail" für eine Konferenz)</span><span class="sxs-lookup"><span data-stu-id="3a89b-110">The [Call Admission Control Report in Lync Server 2013](lync-server-2013-call-admission-control-report.md) (by clicking the Detail metric for a conference)</span></span>

  - <span data-ttu-id="3a89b-111">Der [fehlerlistenbericht in lync Server 2013](lync-server-2013-failure-list-report.md) (durch Klicken auf die Konferenz Metrik)</span><span class="sxs-lookup"><span data-stu-id="3a89b-111">The [Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md) (by clicking the Conference metric)</span></span>

  - <span data-ttu-id="3a89b-112">Der [Bericht über Benutzeraktivität in lync Server 2013](lync-server-2013-user-activity-report.md) (durch Klicken auf die Metrik Konferenz-URI)</span><span class="sxs-lookup"><span data-stu-id="3a89b-112">The [User Activity Report in Lync Server 2013](lync-server-2013-user-activity-report.md) (by clicking the Conference URI metric)</span></span>

<span data-ttu-id="3a89b-113">Aus dem Konferenz Detail Bericht können Sie auf den [Diagnosebericht in lync Server 2013](lync-server-2013-diagnostic-report.md) zugreifen, indem Sie auf die Metrik für den Diagnosebericht (Detail) klicken.</span><span class="sxs-lookup"><span data-stu-id="3a89b-113">From the Conference Detail Report you can access the [Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md) by clicking the Diagnostic Report (Detail) metric.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="3a89b-114">Filter</span><span class="sxs-lookup"><span data-stu-id="3a89b-114">Filters</span></span>

<span data-ttu-id="3a89b-p102">Keine. Der detaillierte Konferenzbericht lässt sich nicht filtern.</span><span class="sxs-lookup"><span data-stu-id="3a89b-p102">None. You cannot filter on the Conference Detail Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="3a89b-117">Metriken</span><span class="sxs-lookup"><span data-stu-id="3a89b-117">Metrics</span></span>

<span data-ttu-id="3a89b-118">In der folgenden Tabelle werden die Informationen aus dem Abschnitt zu Konferenzinformationen des detaillierten Konferenzberichts aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="3a89b-118">The following table lists the information provided in the Conference Information section of the Conference Detail Report.</span></span>

### <a name="conference-information-metrics"></a><span data-ttu-id="3a89b-119">Konferenzinformationen – Metriken</span><span class="sxs-lookup"><span data-stu-id="3a89b-119">Conference Information Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3a89b-120">Name</span><span class="sxs-lookup"><span data-stu-id="3a89b-120">Name</span></span></th>
<th><span data-ttu-id="3a89b-121">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="3a89b-121">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="3a89b-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3a89b-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3a89b-123"><strong>Konferenz-URI</strong></span><span class="sxs-lookup"><span data-stu-id="3a89b-123"><strong>Conference URI</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a89b-p103">Der Konferenz zugewiesener URI. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3a89b-p103">URI assigned to the conference. For example:</span></span></p>
<p><span data-ttu-id="3a89b-126">SIP: kmyer@litwareinc. com; GRUU; Opaque = App: conf: Focus: ID: drg2y8v4</span><span class="sxs-lookup"><span data-stu-id="3a89b-126">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a89b-127"><strong>Pool-FQDN</strong></span><span class="sxs-lookup"><span data-stu-id="3a89b-127"><strong>Pool FQDN</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a89b-128">Vollqualifizierter Domänenname des Registrierungspools oder Edgeservers in einer Sitzung.</span><span class="sxs-lookup"><span data-stu-id="3a89b-128">Fully-qualified domain name of the Registrar pool or Edge Server involved in a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a89b-129"><strong>Beginn</strong></span><span class="sxs-lookup"><span data-stu-id="3a89b-129"><strong>Start time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a89b-130">Datum und Uhrzeit, an dem bzw. zu der Konferenz begann.</span><span class="sxs-lookup"><span data-stu-id="3a89b-130">Date and time that the conference started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a89b-131"><strong>Organisator</strong></span><span class="sxs-lookup"><span data-stu-id="3a89b-131"><strong>Organizer</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a89b-132">SIP-Adresse des Benutzers, der die Sitzung organisiert hat.</span><span class="sxs-lookup"><span data-stu-id="3a89b-132">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a89b-133"><strong>Endzeit</strong></span><span class="sxs-lookup"><span data-stu-id="3a89b-133"><strong>End time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a89b-134">Datum und Uhrzeit, an dem bzw. zu der die Konferenz endete.</span><span class="sxs-lookup"><span data-stu-id="3a89b-134">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3a89b-135">In der folgenden Tabelle werden die Informationen aus dem Abschnitt zur Konferenzteilnahme des detaillierten Konferenzberichts aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="3a89b-135">The following table lists the information provided in the Conference Participation Section of the Conference Detail Report.</span></span>

### <a name="conference-participation-metrics"></a><span data-ttu-id="3a89b-136">Konferenzteilnahme – Metriken</span><span class="sxs-lookup"><span data-stu-id="3a89b-136">Conference Participation Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3a89b-137">Name</span><span class="sxs-lookup"><span data-stu-id="3a89b-137">Name</span></span></th>
<th><span data-ttu-id="3a89b-138">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="3a89b-138">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="3a89b-139">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3a89b-139">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3a89b-140"><strong>Benutzer</strong></span><span class="sxs-lookup"><span data-stu-id="3a89b-140"><strong>User</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a89b-141">SIP-Adresse des Benutzers, der an der Konferenz teilgenommen hat.</span><span class="sxs-lookup"><span data-stu-id="3a89b-141">SIP address of the user who participated in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a89b-142"><strong>Rolle</strong></span><span class="sxs-lookup"><span data-stu-id="3a89b-142"><strong>Role</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a89b-143">Rolle (z. B. Referent) des Konferenzteilnehmers.</span><span class="sxs-lookup"><span data-stu-id="3a89b-143">Role (for example, Presenter) played by the conference participant.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a89b-144"><strong>Konnektivität</strong></span><span class="sxs-lookup"><span data-stu-id="3a89b-144"><strong>Connectivity</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a89b-145">Netzwerkverbindungen (in der Regel "From Internal" oder "From External") des Teilnehmers.</span><span class="sxs-lookup"><span data-stu-id="3a89b-145">Network connectivity (typically From Internal or From External) for the participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a89b-146">Zeitpunkt des Beitritts</span><span class="sxs-lookup"><span data-stu-id="3a89b-146">Join time</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a89b-147">Datum und Uhrzeit, an dem bzw. zu der der Teilnehmer der Konferenz beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="3a89b-147">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a89b-148"><strong>Zeitpunkt der Beendigung</strong></span><span class="sxs-lookup"><span data-stu-id="3a89b-148"><strong>Leave time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a89b-149">Datum und Uhrzeit, an dem bzw. zu der der Teilnehmer die Konferenz verlassen hat.</span><span class="sxs-lookup"><span data-stu-id="3a89b-149">Date and time that the participant left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a89b-150"><strong>Benutzer-Agent</strong></span><span class="sxs-lookup"><span data-stu-id="3a89b-150"><strong>User agent</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a89b-151">ID für die vom Endpunkt des Teilnehmers verwendete Software.</span><span class="sxs-lookup"><span data-stu-id="3a89b-151">Identifier for the software used by the participant’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a89b-152"><strong>Diagnoseberichte</strong></span><span class="sxs-lookup"><span data-stu-id="3a89b-152"><strong>Diagnostic reports</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a89b-p104">Enthält Diagnose- und Problembehandlungsinformationen, einschließlich SIP-Antwortcodes, Diagnoseheader, Zeitpunkt des Konferenzbeitritts und Diagnose-IDs für fehlgeschlagene Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="3a89b-p104">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3a89b-155">In der folgenden Tabelle sind die Informationen aufgeführt, die im Abschnitt "Konferenz Modalitäten" des Konferenz Detail Berichts angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="3a89b-155">The following table lists the information provided in the Conference Modalities section of the Conference Detail Report.</span></span>

### <a name="conference-modalities-metrics"></a><span data-ttu-id="3a89b-156">Konferenzmodalitäten – Metriken</span><span class="sxs-lookup"><span data-stu-id="3a89b-156">Conference Modalities Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3a89b-157">Name</span><span class="sxs-lookup"><span data-stu-id="3a89b-157">Name</span></span></th>
<th><span data-ttu-id="3a89b-158">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="3a89b-158">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="3a89b-159">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3a89b-159">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3a89b-160"><strong>Benutzer</strong></span><span class="sxs-lookup"><span data-stu-id="3a89b-160"><strong>User</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a89b-161">SIP-Adresse des Benutzers, der an der Konferenz teilgenommen hat.</span><span class="sxs-lookup"><span data-stu-id="3a89b-161">SIP address of the user who participated in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a89b-162"><strong>Zeitpunkt des Beitritts</strong></span><span class="sxs-lookup"><span data-stu-id="3a89b-162"><strong>Join time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a89b-163">Datum und Uhrzeit, an dem bzw. zu der der Teilnehmer der Konferenz beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="3a89b-163">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a89b-164"><strong>Zeitpunkt der Beendigung</strong></span><span class="sxs-lookup"><span data-stu-id="3a89b-164"><strong>Leave time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a89b-165">Datum und Uhrzeit, an dem bzw. zu der ein Teilnehmer die Konferenz verlassen hat.</span><span class="sxs-lookup"><span data-stu-id="3a89b-165">Date and time that a participant left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a89b-166"><strong>Konferenzserver-URI</strong></span><span class="sxs-lookup"><span data-stu-id="3a89b-166"><strong>Conferencing server URI</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a89b-167">URI für den in der Konferenz verwendeten Konferenzserver.</span><span class="sxs-lookup"><span data-stu-id="3a89b-167">URI for the Conferencing server used in the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a89b-168"><strong>Diagnoseberichte</strong></span><span class="sxs-lookup"><span data-stu-id="3a89b-168"><strong>Diagnostic reports</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a89b-p105">Enthält Diagnose- und Problembehandlungsinformationen, einschließlich SIP-Antwortcodes, Diagnoseheader, Zeitpunkt des Konferenzbeitritts und Diagnose-IDs für fehlgeschlagene Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="3a89b-p105">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

