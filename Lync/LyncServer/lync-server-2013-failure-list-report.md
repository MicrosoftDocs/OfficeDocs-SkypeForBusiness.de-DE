---
title: 'Lync Server 2013: fehlerlistenbericht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failure List Report
ms:assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615446(v=OCS.15)
ms:contentKeyID: 48185194
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 467dbfe14cbcbe7a032439fd437d3ce2c58c6d46
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515382"
---
# <a name="failure-list-report-in-lync-server-2013"></a><span data-ttu-id="611ed-102">Fehlerlistenbericht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="611ed-102">Failure List Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="611ed-103">_**Letztes Änderungsstand des Themas:** 2012-07-02_</span><span class="sxs-lookup"><span data-stu-id="611ed-103">_**Topic Last Modified:** 2012-07-02_</span></span>

<span data-ttu-id="611ed-104">Der fehlerlistenbericht enthält Informationen zu den einzelnen Teilnehmern, die an einer fehlgeschlagenen Peer-to-Peer-oder Konferenzsitzung teilgenommen haben.</span><span class="sxs-lookup"><span data-stu-id="611ed-104">The Failure List report provides information about the individual participants who took part in a failed peer-to-peer or conferencing session.</span></span> <span data-ttu-id="611ed-105">Diese Informationen umfassen den URI des Benutzers, der das Problem auftrat, sowie den SIP-Antwortcode und die Diagnose-ID, die dem Fehler zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="611ed-105">This information includes the URI of the user who experienced the problem, as well as the SIP Response code and Diagnostic ID associated with the failure.</span></span>

<div>

## <a name="accessing-the-failure-list-report"></a><span data-ttu-id="611ed-106">Zugriff auf den fehlerlistenbericht</span><span class="sxs-lookup"><span data-stu-id="611ed-106">Accessing the Failure List Report</span></span>

<span data-ttu-id="611ed-107">Der Zugriff auf den fehlerlistenbericht erfolgt durch Klicken auf eine der folgenden Metriken im [Bericht über Fehlerverteilung in lync Server 2013](lync-server-2013-failure-distribution-report.md):</span><span class="sxs-lookup"><span data-stu-id="611ed-107">The Failure List Report is accessed by clicking any of the following metrics on the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md):</span></span>

  - <span data-ttu-id="611ed-108">Häufigste Diagnosegründe (Sitzungen)</span><span class="sxs-lookup"><span data-stu-id="611ed-108">Top diagnostic reasons (sessions)</span></span>

  - <span data-ttu-id="611ed-109">Häufigste Modalitäten (Sitzungen)</span><span class="sxs-lookup"><span data-stu-id="611ed-109">Top modalities (sessions)</span></span>

  - <span data-ttu-id="611ed-110">Häufigste Pools (Sitzungen)</span><span class="sxs-lookup"><span data-stu-id="611ed-110">Top pools (sessions)</span></span>

  - <span data-ttu-id="611ed-111">Häufigste Quellen (Sitzungen)</span><span class="sxs-lookup"><span data-stu-id="611ed-111">Top sources (sessions)</span></span>

  - <span data-ttu-id="611ed-112">Häufigste Komponenten (Sitzungen)</span><span class="sxs-lookup"><span data-stu-id="611ed-112">Top components (sessions)</span></span>

  - <span data-ttu-id="611ed-113">Häufigste Absenderbenutzer (Sitzungen)</span><span class="sxs-lookup"><span data-stu-id="611ed-113">Top from users (sessions)</span></span>

  - <span data-ttu-id="611ed-114">Häufigste Empfängerbenutzer (Sitzungen)</span><span class="sxs-lookup"><span data-stu-id="611ed-114">Top to users (sessions)</span></span>

  - <span data-ttu-id="611ed-115">Häufigste Absenderbenutzer-Agents (Sitzungen)</span><span class="sxs-lookup"><span data-stu-id="611ed-115">Top from user agents (sessions)</span></span>

<span data-ttu-id="611ed-116">Im fehlerlistenbericht können Sie auf den [Detailbericht über Peer-to-Peer-Sitzungen in lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) zugreifen, indem Sie auf die Metrik Sitzungsdetails für eine Peer-to-Peer-Sitzung klicken.</span><span class="sxs-lookup"><span data-stu-id="611ed-116">From the Failure List Report you can access the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) by clicking the Session detail metric for a peer-to-peer session.</span></span> <span data-ttu-id="611ed-117">Sie können auch auf den Konferenz Detail Bericht zugreifen, indem Sie auf die Konferenz Metrik für eine Konferenz klicken.</span><span class="sxs-lookup"><span data-stu-id="611ed-117">You can also access the Conference Detail Report by clicking the Conference metric for a conference.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-failure-list-report"></a><span data-ttu-id="611ed-118">Optimale Verwendung des Fehlerlisten Berichts</span><span class="sxs-lookup"><span data-stu-id="611ed-118">Making the Best Use of the Failure List Report</span></span>

<span data-ttu-id="611ed-119">Im fehlerlistenbericht können Sie einfach eine Beschreibung für jeden Antwortcode oder jede Diagnose-ID anzeigen, indem Sie die Maus über diesen Wert halten.</span><span class="sxs-lookup"><span data-stu-id="611ed-119">In the Failure List Report, you can view a description for each Response code or each Diagnostic ID simply by holding your mouse over that value.</span></span> <span data-ttu-id="611ed-120">Wenn Sie beispielsweise die Maus über die Diagnose-ID 7025 halten, wird Folgendes in einer QuickInfo angezeigt:</span><span class="sxs-lookup"><span data-stu-id="611ed-120">For example, if you hold your mouse over Diagnostic ID 7025 you'll see the following displayed in a tooltip:</span></span>

<span data-ttu-id="611ed-121">Interner Serverfehler beim Erstellen von Medien für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="611ed-121">Internal server error creating media for user.</span></span>

<span data-ttu-id="611ed-122">Beachten Sie, dass der fehlerlistenbericht keine direkte Möglichkeit bietet, eine Liste aller Benutzer direkt abzurufen, die an mindestens einer fehlgeschlagenen Sitzung teilgenommen haben, und es ist auch nicht möglich, festzustellen, welche Benutzer am häufigsten an einer fehlgeschlagenen Sitzung beteiligt waren.</span><span class="sxs-lookup"><span data-stu-id="611ed-122">It's important to note that the Failure List Report does not provide a straightforward way to directly retrieve a list of all the users who participated in at least one failed session, nor does it provide a way to determine which users were most-often involved in a failed session.</span></span> <span data-ttu-id="611ed-123">(Für eine Sache hat der fehlerlistenbericht keine Filterfunktionen.) Wenn Sie die Daten jedoch exportieren und dann in eine Datei mit Komma getrennten Werten konvertieren, können Sie Windows PowerShell verwenden, um die Antworten auf Fragen wie diese zu finden.</span><span class="sxs-lookup"><span data-stu-id="611ed-123">(For one thing, the Failure List Report has no filtering capabilities.) However, if you export the data and then convert it to a comma-separated values file, you can use Windows PowerShell to find the answers to questions like those.</span></span> <span data-ttu-id="611ed-124">Nehmen Sie beispielsweise an, dass Sie die Daten in a speichern. CSV-Datei mit dem Namen C: \\ Daten \\ Fehler \_List.csv.</span><span class="sxs-lookup"><span data-stu-id="611ed-124">For example, suppose you save the data to a .CSV file named C:\\Data\\Failure\_List.csv.</span></span> <span data-ttu-id="611ed-125">Basierend auf den in dieser Datei gespeicherten Daten listet dieser Befehl alle Benutzer auf, die an mindestens einer fehlgeschlagenen Sitzung beteiligt waren:</span><span class="sxs-lookup"><span data-stu-id="611ed-125">Based on the data saved in that file, this command lists all the users who were involved in at least one failed session:</span></span>

    $failures = Import-Csv -Path " C:\Data\Failure_List.csv"
    $failure |Sort-Object "From user" | Select-Object "From user" -Unique

<span data-ttu-id="611ed-126">Dieser Befehl gibt eine Liste zurück, die der folgenden ähnelt:</span><span class="sxs-lookup"><span data-stu-id="611ed-126">That command will return a list similar to this:</span></span>

    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com

<span data-ttu-id="611ed-127">Mit diesen beiden Befehlen wird die Gesamtzahl der fehlerhaften Sitzungen zurückgemeldet, an denen jeder Benutzer beteiligt war:</span><span class="sxs-lookup"><span data-stu-id="611ed-127">These two commands report back the total number of failed sessions that each user was involved in:</span></span>

    $failures = Import-Csv -Path "C:\Data\Failure_List.csv"
    $failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending

<span data-ttu-id="611ed-128">Es werden Daten nach dem folgenden Muster zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="611ed-128">That will return data similar to this:</span></span>

    Count    Name
     -----    ----
        20    Pilar.Ackerman@litwareinc.com
        20    David.Ahs@litwareinc.com
        16    Gilead.Amosnino@litwareinc.com
        16    Ken.Myero@litwareinc.com
        14    Henrik.Jensen@litwareinc.com

</div>

<div>

## <a name="filters"></a><span data-ttu-id="611ed-129">Filter</span><span class="sxs-lookup"><span data-stu-id="611ed-129">Filters</span></span>

<span data-ttu-id="611ed-130">Keine.</span><span class="sxs-lookup"><span data-stu-id="611ed-130">None.</span></span> <span data-ttu-id="611ed-131">Sie können den fehlerlistenbericht nicht filtern.</span><span class="sxs-lookup"><span data-stu-id="611ed-131">You cannot filter the Failure List Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="611ed-132">Metriken</span><span class="sxs-lookup"><span data-stu-id="611ed-132">Metrics</span></span>

<span data-ttu-id="611ed-133">In der folgenden Tabelle sind die Informationen aufgeführt, die im fehlerlistenbericht für jeden fehlgeschlagenen Anruf angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="611ed-133">The following table lists the information provided in the Failure List Report for each failed call.</span></span>

### <a name="failure-list-report-metrics"></a><span data-ttu-id="611ed-134">Metriken des Fehlerlisten Berichts</span><span class="sxs-lookup"><span data-stu-id="611ed-134">Failure List Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="611ed-135">Name</span><span class="sxs-lookup"><span data-stu-id="611ed-135">Name</span></span></th>
<th><span data-ttu-id="611ed-136">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="611ed-136">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="611ed-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="611ed-137">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="611ed-138"><strong>Gemeldete Zeit</strong></span><span class="sxs-lookup"><span data-stu-id="611ed-138"><strong>Reported time</strong></span></span></p></td>
<td><p><span data-ttu-id="611ed-139">Nein</span><span class="sxs-lookup"><span data-stu-id="611ed-139">No</span></span></p></td>
<td><p><span data-ttu-id="611ed-140">Datum und Uhrzeit, an dem bzw. zu der der Bericht erfasst wurde.</span><span class="sxs-lookup"><span data-stu-id="611ed-140">Date and time the report was recorded.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="611ed-141"><strong>Anforderung</strong></span><span class="sxs-lookup"><span data-stu-id="611ed-141"><strong>Request</strong></span></span></p></td>
<td><p><span data-ttu-id="611ed-142">Nein</span><span class="sxs-lookup"><span data-stu-id="611ed-142">No</span></span></p></td>
<td><p><span data-ttu-id="611ed-143">Typ der fehlerhaften SIP-Anforderung.</span><span class="sxs-lookup"><span data-stu-id="611ed-143">SIP request type that failed.</span></span> <span data-ttu-id="611ed-144">Beispielsweise invite oder bye.</span><span class="sxs-lookup"><span data-stu-id="611ed-144">For example, INVITE or BYE.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="611ed-145"><strong>Antwortcode</strong></span><span class="sxs-lookup"><span data-stu-id="611ed-145"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="611ed-146">Nein</span><span class="sxs-lookup"><span data-stu-id="611ed-146">No</span></span></p></td>
<td><p><span data-ttu-id="611ed-147">SIP-Antwortcode, der bei einem Konferenz Fehler gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="611ed-147">SIP response code sent when the conference failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="611ed-148"><strong>Diagnose-ID</strong></span><span class="sxs-lookup"><span data-stu-id="611ed-148"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="611ed-149">Nein</span><span class="sxs-lookup"><span data-stu-id="611ed-149">No</span></span></p></td>
<td><p><span data-ttu-id="611ed-150">Eindeutige ID (in der Form eines Headers vom Typ "ms-diagnostics"), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="611ed-150">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="611ed-151"><strong>Join Cost time (MS)</strong></span><span class="sxs-lookup"><span data-stu-id="611ed-151"><strong>Join cost time (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="611ed-152">Nein</span><span class="sxs-lookup"><span data-stu-id="611ed-152">No</span></span></p></td>
<td><p><span data-ttu-id="611ed-153">Zeit (in Millisekunden), die der Benutzer benötigt, um an der Konferenz teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="611ed-153">Amount of time (in milliseconds) required for the user to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="611ed-154"><strong>Von Benutzer</strong></span><span class="sxs-lookup"><span data-stu-id="611ed-154"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="611ed-155">Nein</span><span class="sxs-lookup"><span data-stu-id="611ed-155">No</span></span></p></td>
<td><p><span data-ttu-id="611ed-156">Die SIP-Adresse des Benutzers, der den Anruf initiiert hat.</span><span class="sxs-lookup"><span data-stu-id="611ed-156">SIP address of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="611ed-157"><strong>Von Benutzer-Agent</strong></span><span class="sxs-lookup"><span data-stu-id="611ed-157"><strong>From user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="611ed-158">Nein</span><span class="sxs-lookup"><span data-stu-id="611ed-158">No</span></span></p></td>
<td><p><span data-ttu-id="611ed-159">Software, die vom Endpunkt des Benutzers verwendet wird, der den Anruf initiiert hat.</span><span class="sxs-lookup"><span data-stu-id="611ed-159">Software used by the endpoint of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="611ed-160"><strong>An Benutzer</strong></span><span class="sxs-lookup"><span data-stu-id="611ed-160"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="611ed-161">Nein</span><span class="sxs-lookup"><span data-stu-id="611ed-161">No</span></span></p></td>
<td><p><span data-ttu-id="611ed-162">SIP-Adresse des Benutzers, der aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="611ed-162">SIP address of the user who was being called.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

