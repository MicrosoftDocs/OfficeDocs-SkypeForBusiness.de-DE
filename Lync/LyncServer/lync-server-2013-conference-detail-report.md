---
title: 'Lync Server 2013: Konferenz Detail Bericht'
description: 'Lync Server 2013: Konferenz Detail Bericht.'
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
ms.openlocfilehash: 07c50b545f4a9ee3308a840fc2aa5a15e617a5bd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577631"
---
# <a name="conference-detail-report-in-lync-server-2013"></a><span data-ttu-id="f8e4b-103">Konferenz Detail Bericht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8e4b-103">Conference Detail Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8e4b-104">_**Letztes Änderungsstand des Themas:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="f8e4b-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="f8e4b-p101">Der detaillierte Konferenzbericht enthält ausführliche Informationen zu allen Benutzern, die an einer Konferenz teilgenommen haben. Sie können beispielsweise Informationen wie Datum und Uhrzeit, an dem bzw. zu der ein Benutzer einer Konferenz beigetreten ist und die Konferenz verlassen hat, sowie den Benutzer-Agent des Endpunkts anzeigen, mit dem der Benutzer mit der Konferenz verbunden wurde. Darüber hinaus können Sie Informationen zu der Rolle des Benutzers in den einzelnen Konferenzen (z. B. Referent oder Teilnehmer) anzeigen. Der vielleicht wichtigste Aspekt ist, dass Sie auf einen Blick erkennen können, welche Benutzer der Konferenz erfolgreich beigetreten und sie abgeschlossen haben und welche Benutzer der Konferenz nicht beitreten konnten und sie daher nicht abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="f8e4b-p101">The Conference Detail Report provides detailed information about all the users who participated in a conference. For example, you can see such information as the date and time that a user joined the conference, the date and time that the user left the conference, and the user agent of the endpoint that was used to connect that user to the conference. You can also see information the user's role in each conference (for example, Presenter or Attendee). Perhaps most important, you get quickly see which users successfully join and complete the conference, and which users were not able to successfully join and complete the conference.</span></span>

<div>

## <a name="accessing-the-conference-detail-report"></a><span data-ttu-id="f8e4b-109">Zugreifen auf den detaillierten Konferenzbericht</span><span class="sxs-lookup"><span data-stu-id="f8e4b-109">Accessing the Conference Detail Report</span></span>

<span data-ttu-id="f8e4b-110">Auf den detaillierten Konferenzbericht kann über die folgenden Berichte zugegriffen werden:</span><span class="sxs-lookup"><span data-stu-id="f8e4b-110">The Conference Detail Report can be accessed from the following reports:</span></span>

  - <span data-ttu-id="f8e4b-111">Der [anrufsteuerungsbericht in lync Server 2013](lync-server-2013-call-admission-control-report.md) (durch Klicken auf die Metrik "Detail" für eine Konferenz)</span><span class="sxs-lookup"><span data-stu-id="f8e4b-111">The [Call Admission Control Report in Lync Server 2013](lync-server-2013-call-admission-control-report.md) (by clicking the Detail metric for a conference)</span></span>

  - <span data-ttu-id="f8e4b-112">Der [fehlerlistenbericht in lync Server 2013](lync-server-2013-failure-list-report.md) (durch Klicken auf die Konferenz Metrik)</span><span class="sxs-lookup"><span data-stu-id="f8e4b-112">The [Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md) (by clicking the Conference metric)</span></span>

  - <span data-ttu-id="f8e4b-113">Der [Bericht über Benutzeraktivität in lync Server 2013](lync-server-2013-user-activity-report.md) (durch Klicken auf die Metrik Konferenz-URI)</span><span class="sxs-lookup"><span data-stu-id="f8e4b-113">The [User Activity Report in Lync Server 2013](lync-server-2013-user-activity-report.md) (by clicking the Conference URI metric)</span></span>

<span data-ttu-id="f8e4b-114">Aus dem Konferenz Detail Bericht können Sie auf den [Diagnosebericht in lync Server 2013](lync-server-2013-diagnostic-report.md) zugreifen, indem Sie auf die Metrik für den Diagnosebericht (Detail) klicken.</span><span class="sxs-lookup"><span data-stu-id="f8e4b-114">From the Conference Detail Report you can access the [Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md) by clicking the Diagnostic Report (Detail) metric.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="f8e4b-115">Filter</span><span class="sxs-lookup"><span data-stu-id="f8e4b-115">Filters</span></span>

<span data-ttu-id="f8e4b-p102">Keine. Der detaillierte Konferenzbericht lässt sich nicht filtern.</span><span class="sxs-lookup"><span data-stu-id="f8e4b-p102">None. You cannot filter on the Conference Detail Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="f8e4b-118">Metriken</span><span class="sxs-lookup"><span data-stu-id="f8e4b-118">Metrics</span></span>

<span data-ttu-id="f8e4b-119">In der folgenden Tabelle werden die Informationen aus dem Abschnitt zu Konferenzinformationen des detaillierten Konferenzberichts aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="f8e4b-119">The following table lists the information provided in the Conference Information section of the Conference Detail Report.</span></span>

### <a name="conference-information-metrics"></a><span data-ttu-id="f8e4b-120">Konferenzinformationen – Metriken</span><span class="sxs-lookup"><span data-stu-id="f8e4b-120">Conference Information Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f8e4b-121">Name</span><span class="sxs-lookup"><span data-stu-id="f8e4b-121">Name</span></span></th>
<th><span data-ttu-id="f8e4b-122">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="f8e4b-122">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="f8e4b-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f8e4b-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f8e4b-124"><strong>Konferenz-URI</strong></span><span class="sxs-lookup"><span data-stu-id="f8e4b-124"><strong>Conference URI</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f8e4b-p103">Der Konferenz zugewiesener URI. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f8e4b-p103">URI assigned to the conference. For example:</span></span></p>
<p><span data-ttu-id="f8e4b-127">SIP: kmyer@litwareinc. com; GRUU; Opaque = App: conf: Focus: ID: drg2y8v4</span><span class="sxs-lookup"><span data-stu-id="f8e4b-127">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8e4b-128"><strong>Pool-FQDN</strong></span><span class="sxs-lookup"><span data-stu-id="f8e4b-128"><strong>Pool FQDN</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f8e4b-129">Vollqualifizierter Domänenname des Registrierungspools oder Edgeservers in einer Sitzung.</span><span class="sxs-lookup"><span data-stu-id="f8e4b-129">Fully-qualified domain name of the Registrar pool or Edge Server involved in a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8e4b-130"><strong>Beginn</strong></span><span class="sxs-lookup"><span data-stu-id="f8e4b-130"><strong>Start time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f8e4b-131">Datum und Uhrzeit, an dem bzw. zu der Konferenz begann.</span><span class="sxs-lookup"><span data-stu-id="f8e4b-131">Date and time that the conference started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8e4b-132"><strong>Organisator</strong></span><span class="sxs-lookup"><span data-stu-id="f8e4b-132"><strong>Organizer</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f8e4b-133">SIP-Adresse des Benutzers, der die Sitzung organisiert hat.</span><span class="sxs-lookup"><span data-stu-id="f8e4b-133">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8e4b-134"><strong>Endzeit</strong></span><span class="sxs-lookup"><span data-stu-id="f8e4b-134"><strong>End time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f8e4b-135">Datum und Uhrzeit, an dem bzw. zu der die Konferenz endete.</span><span class="sxs-lookup"><span data-stu-id="f8e4b-135">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f8e4b-136">In der folgenden Tabelle werden die Informationen aus dem Abschnitt zur Konferenzteilnahme des detaillierten Konferenzberichts aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="f8e4b-136">The following table lists the information provided in the Conference Participation Section of the Conference Detail Report.</span></span>

### <a name="conference-participation-metrics"></a><span data-ttu-id="f8e4b-137">Konferenzteilnahme – Metriken</span><span class="sxs-lookup"><span data-stu-id="f8e4b-137">Conference Participation Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f8e4b-138">Name</span><span class="sxs-lookup"><span data-stu-id="f8e4b-138">Name</span></span></th>
<th><span data-ttu-id="f8e4b-139">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="f8e4b-139">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="f8e4b-140">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f8e4b-140">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f8e4b-141"><strong>Benutzende</strong></span><span class="sxs-lookup"><span data-stu-id="f8e4b-141"><strong>User</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f8e4b-142">SIP-Adresse des Benutzers, der an der Konferenz teilgenommen hat.</span><span class="sxs-lookup"><span data-stu-id="f8e4b-142">SIP address of the user who participated in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8e4b-143"><strong>Rolle</strong></span><span class="sxs-lookup"><span data-stu-id="f8e4b-143"><strong>Role</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f8e4b-144">Rolle (z. B. Referent) des Konferenzteilnehmers.</span><span class="sxs-lookup"><span data-stu-id="f8e4b-144">Role (for example, Presenter) played by the conference participant.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8e4b-145"><strong>Konnektivität</strong></span><span class="sxs-lookup"><span data-stu-id="f8e4b-145"><strong>Connectivity</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f8e4b-146">Netzwerkverbindungen (in der Regel "From Internal" oder "From External") des Teilnehmers.</span><span class="sxs-lookup"><span data-stu-id="f8e4b-146">Network connectivity (typically From Internal or From External) for the participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8e4b-147">Zeitpunkt des Beitritts</span><span class="sxs-lookup"><span data-stu-id="f8e4b-147">Join time</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f8e4b-148">Datum und Uhrzeit, an dem bzw. zu der der Teilnehmer der Konferenz beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="f8e4b-148">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8e4b-149"><strong>Zeitpunkt der Beendigung</strong></span><span class="sxs-lookup"><span data-stu-id="f8e4b-149"><strong>Leave time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f8e4b-150">Datum und Uhrzeit, an dem bzw. zu der der Teilnehmer die Konferenz verlassen hat.</span><span class="sxs-lookup"><span data-stu-id="f8e4b-150">Date and time that the participant left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8e4b-151"><strong>Benutzer-Agent</strong></span><span class="sxs-lookup"><span data-stu-id="f8e4b-151"><strong>User agent</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f8e4b-152">ID für die vom Endpunkt des Teilnehmers verwendete Software.</span><span class="sxs-lookup"><span data-stu-id="f8e4b-152">Identifier for the software used by the participant’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8e4b-153"><strong>Diagnoseberichte</strong></span><span class="sxs-lookup"><span data-stu-id="f8e4b-153"><strong>Diagnostic reports</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f8e4b-p104">Enthält Diagnose- und Problembehandlungsinformationen, einschließlich SIP-Antwortcodes, Diagnoseheader, Zeitpunkt des Konferenzbeitritts und Diagnose-IDs für fehlgeschlagene Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="f8e4b-p104">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f8e4b-156">In der folgenden Tabelle sind die Informationen aufgeführt, die im Abschnitt "Konferenz Modalitäten" des Konferenz Detail Berichts angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="f8e4b-156">The following table lists the information provided in the Conference Modalities section of the Conference Detail Report.</span></span>

### <a name="conference-modalities-metrics"></a><span data-ttu-id="f8e4b-157">Konferenzmodalitäten – Metriken</span><span class="sxs-lookup"><span data-stu-id="f8e4b-157">Conference Modalities Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f8e4b-158">Name</span><span class="sxs-lookup"><span data-stu-id="f8e4b-158">Name</span></span></th>
<th><span data-ttu-id="f8e4b-159">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="f8e4b-159">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="f8e4b-160">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f8e4b-160">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f8e4b-161"><strong>Benutzende</strong></span><span class="sxs-lookup"><span data-stu-id="f8e4b-161"><strong>User</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f8e4b-162">SIP-Adresse des Benutzers, der an der Konferenz teilgenommen hat.</span><span class="sxs-lookup"><span data-stu-id="f8e4b-162">SIP address of the user who participated in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8e4b-163"><strong>Zeitpunkt des Beitritts</strong></span><span class="sxs-lookup"><span data-stu-id="f8e4b-163"><strong>Join time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f8e4b-164">Datum und Uhrzeit, an dem bzw. zu der der Teilnehmer der Konferenz beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="f8e4b-164">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8e4b-165"><strong>Zeitpunkt der Beendigung</strong></span><span class="sxs-lookup"><span data-stu-id="f8e4b-165"><strong>Leave time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f8e4b-166">Datum und Uhrzeit, an dem bzw. zu der ein Teilnehmer die Konferenz verlassen hat.</span><span class="sxs-lookup"><span data-stu-id="f8e4b-166">Date and time that a participant left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8e4b-167"><strong>Konferenzserver-URI</strong></span><span class="sxs-lookup"><span data-stu-id="f8e4b-167"><strong>Conferencing server URI</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f8e4b-168">URI für den in der Konferenz verwendeten Konferenzserver.</span><span class="sxs-lookup"><span data-stu-id="f8e4b-168">URI for the Conferencing server used in the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8e4b-169"><strong>Diagnoseberichte</strong></span><span class="sxs-lookup"><span data-stu-id="f8e4b-169"><strong>Diagnostic reports</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f8e4b-p105">Enthält Diagnose- und Problembehandlungsinformationen, einschließlich SIP-Antwortcodes, Diagnoseheader, Zeitpunkt des Konferenzbeitritts und Diagnose-IDs für fehlgeschlagene Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="f8e4b-p105">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

