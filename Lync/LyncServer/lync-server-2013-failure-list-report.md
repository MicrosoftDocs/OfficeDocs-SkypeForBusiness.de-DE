---
title: 'Lync Server 2013: fehlerlistenbericht'
description: 'Lync Server 2013: fehlerlistenbericht.'
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
ms.openlocfilehash: 7467144fe207ab61fd086cd35aac74779fd4f771
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575051"
---
# <a name="failure-list-report-in-lync-server-2013"></a><span data-ttu-id="bd3aa-103">Fehlerlistenbericht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd3aa-103">Failure List Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd3aa-104">_**Letztes Änderungsstand des Themas:** 2012-07-02_</span><span class="sxs-lookup"><span data-stu-id="bd3aa-104">_**Topic Last Modified:** 2012-07-02_</span></span>

<span data-ttu-id="bd3aa-105">Der fehlerlistenbericht enthält Informationen zu den einzelnen Teilnehmern, die an einer fehlgeschlagenen Peer-to-Peer-oder Konferenzsitzung teilgenommen haben.</span><span class="sxs-lookup"><span data-stu-id="bd3aa-105">The Failure List report provides information about the individual participants who took part in a failed peer-to-peer or conferencing session.</span></span> <span data-ttu-id="bd3aa-106">Diese Informationen umfassen den URI des Benutzers, der das Problem auftrat, sowie den SIP-Antwortcode und die Diagnose-ID, die dem Fehler zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="bd3aa-106">This information includes the URI of the user who experienced the problem, as well as the SIP Response code and Diagnostic ID associated with the failure.</span></span>

<div>

## <a name="accessing-the-failure-list-report"></a><span data-ttu-id="bd3aa-107">Zugriff auf den fehlerlistenbericht</span><span class="sxs-lookup"><span data-stu-id="bd3aa-107">Accessing the Failure List Report</span></span>

<span data-ttu-id="bd3aa-108">Der Zugriff auf den fehlerlistenbericht erfolgt durch Klicken auf eine der folgenden Metriken im [Bericht über Fehlerverteilung in lync Server 2013](lync-server-2013-failure-distribution-report.md):</span><span class="sxs-lookup"><span data-stu-id="bd3aa-108">The Failure List Report is accessed by clicking any of the following metrics on the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md):</span></span>

  - <span data-ttu-id="bd3aa-109">Häufigste Diagnosegründe (Sitzungen)</span><span class="sxs-lookup"><span data-stu-id="bd3aa-109">Top diagnostic reasons (sessions)</span></span>

  - <span data-ttu-id="bd3aa-110">Häufigste Modalitäten (Sitzungen)</span><span class="sxs-lookup"><span data-stu-id="bd3aa-110">Top modalities (sessions)</span></span>

  - <span data-ttu-id="bd3aa-111">Häufigste Pools (Sitzungen)</span><span class="sxs-lookup"><span data-stu-id="bd3aa-111">Top pools (sessions)</span></span>

  - <span data-ttu-id="bd3aa-112">Häufigste Quellen (Sitzungen)</span><span class="sxs-lookup"><span data-stu-id="bd3aa-112">Top sources (sessions)</span></span>

  - <span data-ttu-id="bd3aa-113">Häufigste Komponenten (Sitzungen)</span><span class="sxs-lookup"><span data-stu-id="bd3aa-113">Top components (sessions)</span></span>

  - <span data-ttu-id="bd3aa-114">Häufigste Absenderbenutzer (Sitzungen)</span><span class="sxs-lookup"><span data-stu-id="bd3aa-114">Top from users (sessions)</span></span>

  - <span data-ttu-id="bd3aa-115">Häufigste Empfängerbenutzer (Sitzungen)</span><span class="sxs-lookup"><span data-stu-id="bd3aa-115">Top to users (sessions)</span></span>

  - <span data-ttu-id="bd3aa-116">Häufigste Absenderbenutzer-Agents (Sitzungen)</span><span class="sxs-lookup"><span data-stu-id="bd3aa-116">Top from user agents (sessions)</span></span>

<span data-ttu-id="bd3aa-117">Im fehlerlistenbericht können Sie auf den [Detailbericht über Peer-to-Peer-Sitzungen in lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) zugreifen, indem Sie auf die Metrik Sitzungsdetails für eine Peer-to-Peer-Sitzung klicken.</span><span class="sxs-lookup"><span data-stu-id="bd3aa-117">From the Failure List Report you can access the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) by clicking the Session detail metric for a peer-to-peer session.</span></span> <span data-ttu-id="bd3aa-118">Sie können auch auf den Konferenz Detail Bericht zugreifen, indem Sie auf die Konferenz Metrik für eine Konferenz klicken.</span><span class="sxs-lookup"><span data-stu-id="bd3aa-118">You can also access the Conference Detail Report by clicking the Conference metric for a conference.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-failure-list-report"></a><span data-ttu-id="bd3aa-119">Optimale Verwendung des Fehlerlisten Berichts</span><span class="sxs-lookup"><span data-stu-id="bd3aa-119">Making the Best Use of the Failure List Report</span></span>

<span data-ttu-id="bd3aa-120">Im fehlerlistenbericht können Sie einfach eine Beschreibung für jeden Antwortcode oder jede Diagnose-ID anzeigen, indem Sie die Maus über diesen Wert halten.</span><span class="sxs-lookup"><span data-stu-id="bd3aa-120">In the Failure List Report, you can view a description for each Response code or each Diagnostic ID simply by holding your mouse over that value.</span></span> <span data-ttu-id="bd3aa-121">Wenn Sie beispielsweise die Maus über die Diagnose-ID 7025 halten, wird Folgendes in einer QuickInfo angezeigt:</span><span class="sxs-lookup"><span data-stu-id="bd3aa-121">For example, if you hold your mouse over Diagnostic ID 7025 you'll see the following displayed in a tooltip:</span></span>

<span data-ttu-id="bd3aa-122">Interner Serverfehler beim Erstellen von Medien für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="bd3aa-122">Internal server error creating media for user.</span></span>

<span data-ttu-id="bd3aa-123">Beachten Sie, dass der fehlerlistenbericht keine direkte Möglichkeit bietet, eine Liste aller Benutzer direkt abzurufen, die an mindestens einer fehlgeschlagenen Sitzung teilgenommen haben, und es ist auch nicht möglich, festzustellen, welche Benutzer am häufigsten an einer fehlgeschlagenen Sitzung beteiligt waren.</span><span class="sxs-lookup"><span data-stu-id="bd3aa-123">It's important to note that the Failure List Report does not provide a straightforward way to directly retrieve a list of all the users who participated in at least one failed session, nor does it provide a way to determine which users were most-often involved in a failed session.</span></span> <span data-ttu-id="bd3aa-124">(Für eine Sache hat der fehlerlistenbericht keine Filterfunktionen.) Wenn Sie die Daten jedoch exportieren und dann in eine Datei mit Komma getrennten Werten konvertieren, können Sie Windows PowerShell verwenden, um die Antworten auf Fragen wie diese zu finden.</span><span class="sxs-lookup"><span data-stu-id="bd3aa-124">(For one thing, the Failure List Report has no filtering capabilities.) However, if you export the data and then convert it to a comma-separated values file, you can use Windows PowerShell to find the answers to questions like those.</span></span> <span data-ttu-id="bd3aa-125">Nehmen Sie beispielsweise an, dass Sie die Daten in a speichern. CSV-Datei mit dem Namen C: \\ Daten \\ Fehler \_List.csv.</span><span class="sxs-lookup"><span data-stu-id="bd3aa-125">For example, suppose you save the data to a .CSV file named C:\\Data\\Failure\_List.csv.</span></span> <span data-ttu-id="bd3aa-126">Basierend auf den in dieser Datei gespeicherten Daten listet dieser Befehl alle Benutzer auf, die an mindestens einer fehlgeschlagenen Sitzung beteiligt waren:</span><span class="sxs-lookup"><span data-stu-id="bd3aa-126">Based on the data saved in that file, this command lists all the users who were involved in at least one failed session:</span></span>

    $failures = Import-Csv -Path " C:\Data\Failure_List.csv"
    $failure |Sort-Object "From user" | Select-Object "From user" -Unique

<span data-ttu-id="bd3aa-127">Dieser Befehl gibt eine Liste zurück, die der folgenden ähnelt:</span><span class="sxs-lookup"><span data-stu-id="bd3aa-127">That command will return a list similar to this:</span></span>

    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com

<span data-ttu-id="bd3aa-128">Mit diesen beiden Befehlen wird die Gesamtzahl der fehlerhaften Sitzungen zurückgemeldet, an denen jeder Benutzer beteiligt war:</span><span class="sxs-lookup"><span data-stu-id="bd3aa-128">These two commands report back the total number of failed sessions that each user was involved in:</span></span>

    $failures = Import-Csv -Path "C:\Data\Failure_List.csv"
    $failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending

<span data-ttu-id="bd3aa-129">Es werden Daten nach dem folgenden Muster zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="bd3aa-129">That will return data similar to this:</span></span>

    Count    Name
     -----    ----
        20    Pilar.Ackerman@litwareinc.com
        20    David.Ahs@litwareinc.com
        16    Gilead.Amosnino@litwareinc.com
        16    Ken.Myero@litwareinc.com
        14    Henrik.Jensen@litwareinc.com

</div>

<div>

## <a name="filters"></a><span data-ttu-id="bd3aa-130">Filter</span><span class="sxs-lookup"><span data-stu-id="bd3aa-130">Filters</span></span>

<span data-ttu-id="bd3aa-131">Keine.</span><span class="sxs-lookup"><span data-stu-id="bd3aa-131">None.</span></span> <span data-ttu-id="bd3aa-132">Sie können den fehlerlistenbericht nicht filtern.</span><span class="sxs-lookup"><span data-stu-id="bd3aa-132">You cannot filter the Failure List Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="bd3aa-133">Metriken</span><span class="sxs-lookup"><span data-stu-id="bd3aa-133">Metrics</span></span>

<span data-ttu-id="bd3aa-134">In der folgenden Tabelle sind die Informationen aufgeführt, die im fehlerlistenbericht für jeden fehlgeschlagenen Anruf angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="bd3aa-134">The following table lists the information provided in the Failure List Report for each failed call.</span></span>

### <a name="failure-list-report-metrics"></a><span data-ttu-id="bd3aa-135">Metriken des Fehlerlisten Berichts</span><span class="sxs-lookup"><span data-stu-id="bd3aa-135">Failure List Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bd3aa-136">Name</span><span class="sxs-lookup"><span data-stu-id="bd3aa-136">Name</span></span></th>
<th><span data-ttu-id="bd3aa-137">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="bd3aa-137">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="bd3aa-138">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bd3aa-138">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bd3aa-139"><strong>Gemeldete Zeit</strong></span><span class="sxs-lookup"><span data-stu-id="bd3aa-139"><strong>Reported time</strong></span></span></p></td>
<td><p><span data-ttu-id="bd3aa-140">Nein</span><span class="sxs-lookup"><span data-stu-id="bd3aa-140">No</span></span></p></td>
<td><p><span data-ttu-id="bd3aa-141">Datum und Uhrzeit, an dem bzw. zu der der Bericht erfasst wurde.</span><span class="sxs-lookup"><span data-stu-id="bd3aa-141">Date and time the report was recorded.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd3aa-142"><strong>Anforderung</strong></span><span class="sxs-lookup"><span data-stu-id="bd3aa-142"><strong>Request</strong></span></span></p></td>
<td><p><span data-ttu-id="bd3aa-143">Nein</span><span class="sxs-lookup"><span data-stu-id="bd3aa-143">No</span></span></p></td>
<td><p><span data-ttu-id="bd3aa-144">Typ der fehlerhaften SIP-Anforderung.</span><span class="sxs-lookup"><span data-stu-id="bd3aa-144">SIP request type that failed.</span></span> <span data-ttu-id="bd3aa-145">Beispielsweise invite oder bye.</span><span class="sxs-lookup"><span data-stu-id="bd3aa-145">For example, INVITE or BYE.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd3aa-146"><strong>Antwortcode</strong></span><span class="sxs-lookup"><span data-stu-id="bd3aa-146"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="bd3aa-147">Nein</span><span class="sxs-lookup"><span data-stu-id="bd3aa-147">No</span></span></p></td>
<td><p><span data-ttu-id="bd3aa-148">SIP-Antwortcode, der bei einem Konferenz Fehler gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="bd3aa-148">SIP response code sent when the conference failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd3aa-149"><strong>Diagnose-ID</strong></span><span class="sxs-lookup"><span data-stu-id="bd3aa-149"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="bd3aa-150">Nein</span><span class="sxs-lookup"><span data-stu-id="bd3aa-150">No</span></span></p></td>
<td><p><span data-ttu-id="bd3aa-151">Eindeutige ID (in der Form eines Headers vom Typ "ms-diagnostics"), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="bd3aa-151">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd3aa-152"><strong>Join Cost time (MS)</strong></span><span class="sxs-lookup"><span data-stu-id="bd3aa-152"><strong>Join cost time (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="bd3aa-153">Nein</span><span class="sxs-lookup"><span data-stu-id="bd3aa-153">No</span></span></p></td>
<td><p><span data-ttu-id="bd3aa-154">Zeit (in Millisekunden), die der Benutzer benötigt, um an der Konferenz teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="bd3aa-154">Amount of time (in milliseconds) required for the user to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd3aa-155"><strong>Von Benutzer</strong></span><span class="sxs-lookup"><span data-stu-id="bd3aa-155"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="bd3aa-156">Nein</span><span class="sxs-lookup"><span data-stu-id="bd3aa-156">No</span></span></p></td>
<td><p><span data-ttu-id="bd3aa-157">Die SIP-Adresse des Benutzers, der den Anruf initiiert hat.</span><span class="sxs-lookup"><span data-stu-id="bd3aa-157">SIP address of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd3aa-158"><strong>Von Benutzer-Agent</strong></span><span class="sxs-lookup"><span data-stu-id="bd3aa-158"><strong>From user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="bd3aa-159">Nein</span><span class="sxs-lookup"><span data-stu-id="bd3aa-159">No</span></span></p></td>
<td><p><span data-ttu-id="bd3aa-160">Software, die vom Endpunkt des Benutzers verwendet wird, der den Anruf initiiert hat.</span><span class="sxs-lookup"><span data-stu-id="bd3aa-160">Software used by the endpoint of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd3aa-161"><strong>An Benutzer</strong></span><span class="sxs-lookup"><span data-stu-id="bd3aa-161"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="bd3aa-162">Nein</span><span class="sxs-lookup"><span data-stu-id="bd3aa-162">No</span></span></p></td>
<td><p><span data-ttu-id="bd3aa-163">SIP-Adresse des Benutzers, der aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="bd3aa-163">SIP address of the user who was being called.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

