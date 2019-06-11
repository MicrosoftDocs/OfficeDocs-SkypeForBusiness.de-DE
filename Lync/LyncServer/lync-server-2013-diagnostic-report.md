---
title: 'Lync Server 2013: Diagnosebericht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Diagnostic Report
ms:assetid: b389dbd9-f2e8-4184-93d0-2e504796ac16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615445(v=OCS.15)
ms:contentKeyID: 48185159
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b314bccb0c1df539598e17ffc8ca12b30287b8eb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832413"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="diagnostic-report-in-lync-server-2013"></a><span data-ttu-id="7a844-102">Diagnosebericht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7a844-102">Diagnostic Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a844-103">_**Letztes Änderungsdatum des Themas:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="7a844-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="7a844-104">Der Diagnosebericht enthält Diagnose- und Problembehandlungsinformationen der fehlerhaften Sitzung.</span><span class="sxs-lookup"><span data-stu-id="7a844-104">The Diagnostic Report provides diagnostic and troubleshooting information for a failed session.</span></span> <span data-ttu-id="7a844-105">Er enthält sowohl die während einer fehlerhaften Sitzung berichtete Diagnose-ID als auch den Diagnoseheader.</span><span class="sxs-lookup"><span data-stu-id="7a844-105">This information includes both the Diagnostic ID and the Diagnostic header that were reported when the session failed.</span></span> <span data-ttu-id="7a844-106">Die Diagnose-ID ist ein eindeutiger Bezeichner (in der Form eines Headers vom Typ „ms-diagnostics“) der an eine SIP-Nachricht angefügt wird, während der Diagnoseheader eine begleitende Beschreibung für die Diagnose-ID bietet.</span><span class="sxs-lookup"><span data-stu-id="7a844-106">The Diagnostic ID is a unique identifier (in the form of an ms-diagnostics header) that gets attached to a SIP message, while the Diagnostic header provides an accompanying description for the Diagnostic ID.</span></span> <span data-ttu-id="7a844-107">Der Bericht enthält möglicherweise auch wertvolle Details für die Problembehandlung, die der Reporting-Komponente bekannt sind.</span><span class="sxs-lookup"><span data-stu-id="7a844-107">The report might also contain valuable troubleshooting details that are known by the reporting component.</span></span> <span data-ttu-id="7a844-108">Beispielsweise:</span><span class="sxs-lookup"><span data-stu-id="7a844-108">For example:</span></span>

  - <span data-ttu-id="7a844-p102">Der vom PSTN-Gateway bereitgestellte Ursachencode, der den Fehler generiert hat. Wenn ein ausgehender Anruf im Telefonfestnetz nicht getätigt werden kann, wird automatisch ein ISUP-Ursachencode (ISDN User Part) generiert. Beispielsweise kann ein PSTN-Gateway den Ursachencode 34 senden, um anzuzeigen, dass keine Verbindung bzw. kein Kanal zum Tätigen des Anrufs verfügbar war.</span><span class="sxs-lookup"><span data-stu-id="7a844-p102">The cause code provided by the PSTN gateway that generated the failure. When an outgoing call fails on the PSTN network, an ISDN User Part (ISUP) cause code is automatically generated. For example, a PSTN gateway might send cause code 34 to indicate that no circuit or channel was available for completing the call.</span></span>

  - <span data-ttu-id="7a844-112">FQDN des Peers, Port und Winsock-Fehler für Verbindungsfehler.</span><span class="sxs-lookup"><span data-stu-id="7a844-112">Peer FQDN, port, and Winsock errors for connectivity failures.</span></span>

  - <span data-ttu-id="7a844-p103">Namen, die für DNS-Auflösungsfehler ermittelt werden. Die DNS-Auflösung findet immer dann statt, wenn ein Client einen Namenserver kontaktiert und die IP-Adresse anfordert, die dem angegebenen Gerätenamen entspricht.</span><span class="sxs-lookup"><span data-stu-id="7a844-p103">Names being looked up for DNS resolution failures. DNS resolution takes place any time a client contacts a name server and requests the IP address that corresponds to specified device name.</span></span>

<div>

## <a name="accessing-the-diagnostic-report"></a><span data-ttu-id="7a844-115">Zugreifen auf den Diagnosebericht</span><span class="sxs-lookup"><span data-stu-id="7a844-115">Accessing the Diagnostic Report</span></span>

<span data-ttu-id="7a844-116">Sie können auf den Diagnosebericht zugreifen, indem Sie im [Bericht Peer-to-Peer-Sitzungs Detail in lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) oder im Konferenz Detailbericht auf die Metrik für den Diagnosebericht (Detail) klicken.</span><span class="sxs-lookup"><span data-stu-id="7a844-116">The Diagnostic Report can be accessed by clicking the Diagnostic Report (Detail) metric on either the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) or the Conference Detail Report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="7a844-117">Filter</span><span class="sxs-lookup"><span data-stu-id="7a844-117">Filters</span></span>

<span data-ttu-id="7a844-p104">Keine. Sie können den Diagnosebericht nicht filtern.</span><span class="sxs-lookup"><span data-stu-id="7a844-p104">None. You cannot filter the Diagnostic Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="7a844-120">Metriken</span><span class="sxs-lookup"><span data-stu-id="7a844-120">Metrics</span></span>

<span data-ttu-id="7a844-121">In der folgenden Tabelle sind die im Diagnosebericht enthaltenen Informationen für jeden Anruf aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="7a844-121">The following table lists the information provided in the Diagnostic Report for each session.</span></span>

### <a name="diagnostic-report-metrics"></a><span data-ttu-id="7a844-122">Metriken des Diagnoseberichts</span><span class="sxs-lookup"><span data-stu-id="7a844-122">Diagnostic Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7a844-123">Name</span><span class="sxs-lookup"><span data-stu-id="7a844-123">Name</span></span></th>
<th><span data-ttu-id="7a844-124">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="7a844-124">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="7a844-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7a844-125">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7a844-126"><strong>Berichtszeitpunkt</strong></span><span class="sxs-lookup"><span data-stu-id="7a844-126"><strong>Report time</strong></span></span></p></td>
<td><p><span data-ttu-id="7a844-127">Nein</span><span class="sxs-lookup"><span data-stu-id="7a844-127">No</span></span></p></td>
<td><p><span data-ttu-id="7a844-128">Datum und Uhrzeit der Aufzeichnung des Berichts.</span><span class="sxs-lookup"><span data-stu-id="7a844-128">Date and time that the report was recorded.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a844-129"><strong>Antwortcode</strong></span><span class="sxs-lookup"><span data-stu-id="7a844-129"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="7a844-130">Nein</span><span class="sxs-lookup"><span data-stu-id="7a844-130">No</span></span></p></td>
<td><p><span data-ttu-id="7a844-131">SIP-Antwortcode, der bei einem Sitzungsfehler gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="7a844-131">SIP response code sent when the session failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a844-132"><strong>Anforderungstyp</strong></span><span class="sxs-lookup"><span data-stu-id="7a844-132"><strong>Request type</strong></span></span></p></td>
<td><p><span data-ttu-id="7a844-133">Nein</span><span class="sxs-lookup"><span data-stu-id="7a844-133">No</span></span></p></td>
<td><p><span data-ttu-id="7a844-p105">Typ der fehlerhaften SIP-Anforderung. Beispielsweise: INVITE, BYE oder SERVICE.</span><span class="sxs-lookup"><span data-stu-id="7a844-p105">SIP request type that failed. For example, INVITE, BYE, or SERVICE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a844-136"><strong>Quelle</strong></span><span class="sxs-lookup"><span data-stu-id="7a844-136"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="7a844-137">Nein</span><span class="sxs-lookup"><span data-stu-id="7a844-137">No</span></span></p></td>
<td><p><span data-ttu-id="7a844-138">Ursache des Fehlers.</span><span class="sxs-lookup"><span data-stu-id="7a844-138">Source of the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a844-139"><strong>Von Benutzer-URI</strong></span><span class="sxs-lookup"><span data-stu-id="7a844-139"><strong>From user URI</strong></span></span></p></td>
<td><p><span data-ttu-id="7a844-140">Nein</span><span class="sxs-lookup"><span data-stu-id="7a844-140">No</span></span></p></td>
<td><p><span data-ttu-id="7a844-141">SIP-Adresse des Benutzers, der die Sitzung initiiert hat.</span><span class="sxs-lookup"><span data-stu-id="7a844-141">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a844-142"><strong>Von Benutzeragent</strong></span><span class="sxs-lookup"><span data-stu-id="7a844-142"><strong>From user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="7a844-143">Nein</span><span class="sxs-lookup"><span data-stu-id="7a844-143">No</span></span></p></td>
<td><p><span data-ttu-id="7a844-144">Software, die vom Endpunkt des Benutzers, der die Sitzung initiiert hat, verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7a844-144">Software used by the endpoint of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a844-145"><strong>Diagnose-ID</strong></span><span class="sxs-lookup"><span data-stu-id="7a844-145"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="7a844-146">Nein</span><span class="sxs-lookup"><span data-stu-id="7a844-146">No</span></span></p></td>
<td><p><span data-ttu-id="7a844-147">Eindeutige ID (in der Form eines Headers vom Typ „ms-diagnostics“), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="7a844-147">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a844-148"><strong>Inhaltstyp</strong></span><span class="sxs-lookup"><span data-stu-id="7a844-148"><strong>Content type</strong></span></span></p></td>
<td><p><span data-ttu-id="7a844-149">Nein</span><span class="sxs-lookup"><span data-stu-id="7a844-149">No</span></span></p></td>
<td><p><span data-ttu-id="7a844-p106">Typ der fehlerhaften Medieninhalte. Ein gebräuchlicher Inhaltstyp ist beispielsweise Application/sdp. SDP (Session Description Protocol) ist ein Standardinternetprotokoll, das für Sitzungsankündigungen, Sitzungseinladungen und andere Formen von Einladungen für Multimediasitzungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7a844-p106">Type of media content that failed. For example, a common content type is Application/sdp. Session Description Protocol (SDP) is a standard Internet protocol used for session announcements, session invitations, and other forms of multimedia session initiation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a844-153"><strong>Anwendung</strong></span><span class="sxs-lookup"><span data-stu-id="7a844-153"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="7a844-154">Nein</span><span class="sxs-lookup"><span data-stu-id="7a844-154">No</span></span></p></td>
<td><p><span data-ttu-id="7a844-155">Anwendung, die am Fehler beteiligt ist.</span><span class="sxs-lookup"><span data-stu-id="7a844-155">Application involved in the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a844-156"><strong>An Benutzer-URI</strong></span><span class="sxs-lookup"><span data-stu-id="7a844-156"><strong>To user URI</strong></span></span></p></td>
<td><p><span data-ttu-id="7a844-157">Nein</span><span class="sxs-lookup"><span data-stu-id="7a844-157">No</span></span></p></td>
<td><p><span data-ttu-id="7a844-158">SIP-Adresse des Benutzers, der zur Sitzung eingeladen wurde.</span><span class="sxs-lookup"><span data-stu-id="7a844-158">SIP address of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a844-159">Zeitpunkt des Beitritts für die Konferenz (ms)</span><span class="sxs-lookup"><span data-stu-id="7a844-159">Conference join times (ms)</span></span></p></td>
<td><p><span data-ttu-id="7a844-160">Nein</span><span class="sxs-lookup"><span data-stu-id="7a844-160">No</span></span></p></td>
<td><p><span data-ttu-id="7a844-161">Gesamtdauer (in Millisekunden), die der Benutzer benötigt, um an der Konferenz teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="7a844-161">Amount of time (in milliseconds) it took for the user to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a844-162"><strong>Diagnoseheader</strong></span><span class="sxs-lookup"><span data-stu-id="7a844-162"><strong>Diagnostic header</strong></span></span></p></td>
<td><p><span data-ttu-id="7a844-163">Nein</span><span class="sxs-lookup"><span data-stu-id="7a844-163">No</span></span></p></td>
<td><p><span data-ttu-id="7a844-164">Beschreibung der Diagnose-ID.</span><span class="sxs-lookup"><span data-stu-id="7a844-164">Diagnostic ID description.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7a844-165">Eine Liste der Diagnosefehler finden Sie auf der [Header Seite MS-Diagnostics](http://msdn.microsoft.com/en-us/library/gg132446\(v=office.12\).aspx).</span><span class="sxs-lookup"><span data-stu-id="7a844-165">A list of diagnostic errors can be found on the [Ms-Diagnostics Header page](http://msdn.microsoft.com/en-us/library/gg132446\(v=office.12\).aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

