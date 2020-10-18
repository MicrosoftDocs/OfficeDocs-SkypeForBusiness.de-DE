---
title: 'Lync Server 2013: Diagnosebericht'
description: 'Lync Server 2013: Diagnosebericht.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Diagnostic Report
ms:assetid: b389dbd9-f2e8-4184-93d0-2e504796ac16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615445(v=OCS.15)
ms:contentKeyID: 48185159
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 198b836437285b464ba9172e59c9a60ed0a53b65
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576251"
---
# <a name="diagnostic-report-in-lync-server-2013"></a><span data-ttu-id="13e61-103">Diagnosebericht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13e61-103">Diagnostic Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13e61-104">_**Letztes Änderungsstand des Themas:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="13e61-104">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="13e61-105">Der Diagnosebericht enthält Diagnose- und Problembehandlungsinformationen der fehlerhaften Sitzung.</span><span class="sxs-lookup"><span data-stu-id="13e61-105">The Diagnostic Report provides diagnostic and troubleshooting information for a failed session.</span></span> <span data-ttu-id="13e61-106">Er enthält sowohl die während einer fehlerhaften Sitzung berichtete Diagnose-ID als auch den Diagnoseheader.</span><span class="sxs-lookup"><span data-stu-id="13e61-106">This information includes both the Diagnostic ID and the Diagnostic header that were reported when the session failed.</span></span> <span data-ttu-id="13e61-107">Die Diagnose-ID ist ein eindeutiger Bezeichner (in der Form eines Headers vom Typ "ms-diagnostics") der an eine SIP-Nachricht angefügt wird, während der Diagnoseheader eine begleitende Beschreibung für die Diagnose-ID bietet.</span><span class="sxs-lookup"><span data-stu-id="13e61-107">The Diagnostic ID is a unique identifier (in the form of an ms-diagnostics header) that gets attached to a SIP message, while the Diagnostic header provides an accompanying description for the Diagnostic ID.</span></span> <span data-ttu-id="13e61-108">Der Bericht enthält möglicherweise auch wertvolle Details für die Problembehandlung, die der Reporting-Komponente bekannt sind.</span><span class="sxs-lookup"><span data-stu-id="13e61-108">The report might also contain valuable troubleshooting details that are known by the reporting component.</span></span> <span data-ttu-id="13e61-109">Beispielsweise:</span><span class="sxs-lookup"><span data-stu-id="13e61-109">For example:</span></span>

  - <span data-ttu-id="13e61-p102">Der vom PSTN-Gateway bereitgestellte Ursachencode, der den Fehler generiert hat. Wenn ein ausgehender Anruf im Telefonfestnetz nicht getätigt werden kann, wird automatisch ein ISUP-Ursachencode (ISDN User Part) generiert. Beispielsweise kann ein PSTN-Gateway den Ursachencode 34 senden, um anzuzeigen, dass keine Verbindung bzw. kein Kanal zum Tätigen des Anrufs verfügbar war.</span><span class="sxs-lookup"><span data-stu-id="13e61-p102">The cause code provided by the PSTN gateway that generated the failure. When an outgoing call fails on the PSTN network, an ISDN User Part (ISUP) cause code is automatically generated. For example, a PSTN gateway might send cause code 34 to indicate that no circuit or channel was available for completing the call.</span></span>

  - <span data-ttu-id="13e61-113">FQDN des Peers, Port und Winsock-Fehler für Verbindungsfehler.</span><span class="sxs-lookup"><span data-stu-id="13e61-113">Peer FQDN, port, and Winsock errors for connectivity failures.</span></span>

  - <span data-ttu-id="13e61-p103">Namen, die für DNS-Auflösungsfehler ermittelt werden. Die DNS-Auflösung findet immer dann statt, wenn ein Client einen Namenserver kontaktiert und die IP-Adresse anfordert, die dem angegebenen Gerätenamen entspricht.</span><span class="sxs-lookup"><span data-stu-id="13e61-p103">Names being looked up for DNS resolution failures. DNS resolution takes place any time a client contacts a name server and requests the IP address that corresponds to specified device name.</span></span>

<div>

## <a name="accessing-the-diagnostic-report"></a><span data-ttu-id="13e61-116">Zugreifen auf den Diagnosebericht</span><span class="sxs-lookup"><span data-stu-id="13e61-116">Accessing the Diagnostic Report</span></span>

<span data-ttu-id="13e61-117">Auf den Diagnosebericht kann zugegriffen werden, indem Sie im [Detailbericht über Peer-to-Peer-Sitzungen in lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) oder im Konferenz Detailbericht auf die Metrik für den Diagnosebericht (Detail) klicken.</span><span class="sxs-lookup"><span data-stu-id="13e61-117">The Diagnostic Report can be accessed by clicking the Diagnostic Report (Detail) metric on either the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) or the Conference Detail Report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="13e61-118">Filter</span><span class="sxs-lookup"><span data-stu-id="13e61-118">Filters</span></span>

<span data-ttu-id="13e61-p104">Keine. Sie können den Diagnosebericht nicht filtern.</span><span class="sxs-lookup"><span data-stu-id="13e61-p104">None. You cannot filter the Diagnostic Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="13e61-121">Metriken</span><span class="sxs-lookup"><span data-stu-id="13e61-121">Metrics</span></span>

<span data-ttu-id="13e61-122">In der folgenden Tabelle sind die im Diagnosebericht enthaltenen Informationen für jeden Anruf aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="13e61-122">The following table lists the information provided in the Diagnostic Report for each session.</span></span>

### <a name="diagnostic-report-metrics"></a><span data-ttu-id="13e61-123">Metriken des Diagnoseberichts</span><span class="sxs-lookup"><span data-stu-id="13e61-123">Diagnostic Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="13e61-124">Name</span><span class="sxs-lookup"><span data-stu-id="13e61-124">Name</span></span></th>
<th><span data-ttu-id="13e61-125">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="13e61-125">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="13e61-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="13e61-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="13e61-127"><strong>Berichtszeit</strong></span><span class="sxs-lookup"><span data-stu-id="13e61-127"><strong>Report time</strong></span></span></p></td>
<td><p><span data-ttu-id="13e61-128">Nein</span><span class="sxs-lookup"><span data-stu-id="13e61-128">No</span></span></p></td>
<td><p><span data-ttu-id="13e61-129">Datum und Uhrzeit der Aufzeichnung des Berichts.</span><span class="sxs-lookup"><span data-stu-id="13e61-129">Date and time that the report was recorded.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="13e61-130"><strong>Antwortcode</strong></span><span class="sxs-lookup"><span data-stu-id="13e61-130"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="13e61-131">Nein</span><span class="sxs-lookup"><span data-stu-id="13e61-131">No</span></span></p></td>
<td><p><span data-ttu-id="13e61-132">SIP-Antwortcode, der bei einem Sitzungsfehler gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="13e61-132">SIP response code sent when the session failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="13e61-133"><strong>Anforderungstyp</strong></span><span class="sxs-lookup"><span data-stu-id="13e61-133"><strong>Request type</strong></span></span></p></td>
<td><p><span data-ttu-id="13e61-134">Nein</span><span class="sxs-lookup"><span data-stu-id="13e61-134">No</span></span></p></td>
<td><p><span data-ttu-id="13e61-p105">Typ der fehlerhaften SIP-Anforderung. Beispielsweise: INVITE, BYE oder SERVICE.</span><span class="sxs-lookup"><span data-stu-id="13e61-p105">SIP request type that failed. For example, INVITE, BYE, or SERVICE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="13e61-137"><strong>Source</strong></span><span class="sxs-lookup"><span data-stu-id="13e61-137"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="13e61-138">Nein</span><span class="sxs-lookup"><span data-stu-id="13e61-138">No</span></span></p></td>
<td><p><span data-ttu-id="13e61-139">Ursache des Fehlers.</span><span class="sxs-lookup"><span data-stu-id="13e61-139">Source of the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="13e61-140"><strong>Von Benutzer-URI</strong></span><span class="sxs-lookup"><span data-stu-id="13e61-140"><strong>From user URI</strong></span></span></p></td>
<td><p><span data-ttu-id="13e61-141">Nein</span><span class="sxs-lookup"><span data-stu-id="13e61-141">No</span></span></p></td>
<td><p><span data-ttu-id="13e61-142">SIP-Adresse des Benutzers, der die Sitzung initiiert hat.</span><span class="sxs-lookup"><span data-stu-id="13e61-142">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="13e61-143"><strong>Von Benutzer-Agent</strong></span><span class="sxs-lookup"><span data-stu-id="13e61-143"><strong>From user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="13e61-144">Nein</span><span class="sxs-lookup"><span data-stu-id="13e61-144">No</span></span></p></td>
<td><p><span data-ttu-id="13e61-145">Software, die vom Endpunkt des Benutzers, der den Anruf initiiert hat, verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="13e61-145">Software used by the endpoint of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="13e61-146"><strong>Diagnose-ID</strong></span><span class="sxs-lookup"><span data-stu-id="13e61-146"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="13e61-147">Nein</span><span class="sxs-lookup"><span data-stu-id="13e61-147">No</span></span></p></td>
<td><p><span data-ttu-id="13e61-148">Eindeutige ID (in der Form eines Headers vom Typ "ms-diagnostics"), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="13e61-148">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="13e61-149"><strong>Inhaltstyp</strong></span><span class="sxs-lookup"><span data-stu-id="13e61-149"><strong>Content type</strong></span></span></p></td>
<td><p><span data-ttu-id="13e61-150">Nein</span><span class="sxs-lookup"><span data-stu-id="13e61-150">No</span></span></p></td>
<td><p><span data-ttu-id="13e61-p106">Typ der fehlerhaften Medieninhalte. Ein gebräuchlicher Inhaltstyp ist beispielsweise Application/sdp. SDP (Session Description Protocol) ist ein Standardinternetprotokoll, das für Sitzungsankündigungen, Sitzungseinladungen und andere Formen von Einladungen für Multimediasitzungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="13e61-p106">Type of media content that failed. For example, a common content type is Application/sdp. Session Description Protocol (SDP) is a standard Internet protocol used for session announcements, session invitations, and other forms of multimedia session initiation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="13e61-154"><strong>Anwendung</strong></span><span class="sxs-lookup"><span data-stu-id="13e61-154"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="13e61-155">Nein</span><span class="sxs-lookup"><span data-stu-id="13e61-155">No</span></span></p></td>
<td><p><span data-ttu-id="13e61-156">Anwendung, die am Fehler beteiligt ist.</span><span class="sxs-lookup"><span data-stu-id="13e61-156">Application involved in the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="13e61-157"><strong>An Benutzer-URI</strong></span><span class="sxs-lookup"><span data-stu-id="13e61-157"><strong>To user URI</strong></span></span></p></td>
<td><p><span data-ttu-id="13e61-158">Nein</span><span class="sxs-lookup"><span data-stu-id="13e61-158">No</span></span></p></td>
<td><p><span data-ttu-id="13e61-159">SIP-Adresse des Benutzers, der zur Sitzung eingeladen wurde.</span><span class="sxs-lookup"><span data-stu-id="13e61-159">SIP address of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="13e61-160">Zeitpunkt des Beitritts für die Konferenz (ms)</span><span class="sxs-lookup"><span data-stu-id="13e61-160">Conference join times (ms)</span></span></p></td>
<td><p><span data-ttu-id="13e61-161">Nein</span><span class="sxs-lookup"><span data-stu-id="13e61-161">No</span></span></p></td>
<td><p><span data-ttu-id="13e61-162">Gesamtdauer (in Millisekunden), die der Benutzer benötigt, um an der Konferenz teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="13e61-162">Amount of time (in milliseconds) it took for the user to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="13e61-163"><strong>Diagnoseheader</strong></span><span class="sxs-lookup"><span data-stu-id="13e61-163"><strong>Diagnostic header</strong></span></span></p></td>
<td><p><span data-ttu-id="13e61-164">Nein</span><span class="sxs-lookup"><span data-stu-id="13e61-164">No</span></span></p></td>
<td><p><span data-ttu-id="13e61-165">Beschreibung der Diagnose-ID.</span><span class="sxs-lookup"><span data-stu-id="13e61-165">Diagnostic ID description.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="13e61-166">Eine Liste der Diagnosefehler finden Sie auf der [Kopfzeilenseite der MS-Diagnostics](https://msdn.microsoft.com/library/gg132446\(v=office.12\).aspx).</span><span class="sxs-lookup"><span data-stu-id="13e61-166">A list of diagnostic errors can be found on the [Ms-Diagnostics Header page](https://msdn.microsoft.com/library/gg132446\(v=office.12\).aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

