---
title: 'Lync Server 2013: zusammenfassender Bericht über Medienqualität'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Summary Report
ms:assetid: 8bd59ad6-3087-49c8-b692-5573fe2ffcd8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615012(v=OCS.15)
ms:contentKeyID: 48184776
ms.date: 06/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89a5046ba15534d40c81e1e3b8a4f310873a9e1b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045107"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-quality-summary-report-in-lync-server-2013"></a><span data-ttu-id="665ca-102">Zusammenfassender Bericht über Medienqualität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="665ca-102">Media Quality Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="665ca-103">_**Letztes Änderungsstand des Themas:** 2016-06-29_</span><span class="sxs-lookup"><span data-stu-id="665ca-103">_**Topic Last Modified:** 2016-06-29_</span></span>

<span data-ttu-id="665ca-104">Der "Zusammenfassende Bericht über Medienqualität" ist möglicherweise die beste Option zum Analysieren der Anrufqualität in Ihrer Organisation: In diesem Bericht werden detailliert die QoE-Anrufmetriken (Quality of Experience, QoE) in den folgenden Kategorien aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="665ca-104">The Media Quality Summary Report is perhaps your best bet for analyzing call quality in your organization: this report provides detailed Quality of Experience (QoE) call metrics broken down into the following categories:</span></span>

  - <span data-ttu-id="665ca-105">UC-Peer-to-Peer-Anrufe (beispielsweise eine Microsoft lync 2013 für Microsoft lync 2013 Anruf)</span><span class="sxs-lookup"><span data-stu-id="665ca-105">UC Peer to Peer Calls (such as a Microsoft Lync 2013 to Microsoft Lync 2013 call)</span></span>

  - <span data-ttu-id="665ca-106">UC-Konferenzsitzungen</span><span class="sxs-lookup"><span data-stu-id="665ca-106">UC Conference Sessions</span></span>

  - <span data-ttu-id="665ca-107">PSTN-Konferenzsitzungen</span><span class="sxs-lookup"><span data-stu-id="665ca-107">PSTN Conference Sessions</span></span>

  - <span data-ttu-id="665ca-108">PSTN-Anrufe: Medienumgehung</span><span class="sxs-lookup"><span data-stu-id="665ca-108">PSTN Calls: Media Bypass</span></span>

  - <span data-ttu-id="665ca-109">PSTN-Anrufe (keine Umgehung): UC-Abschnitt</span><span class="sxs-lookup"><span data-stu-id="665ca-109">PSTN Calls (Non-Bypass): UC Leg</span></span>

  - <span data-ttu-id="665ca-110">PSTN-Anrufe (keine Umgehung): Gateway-Abschnitt</span><span class="sxs-lookup"><span data-stu-id="665ca-110">PSTN Calls (Non-Bypass): Gateway Leg</span></span>

  - <span data-ttu-id="665ca-111">Andere Anruftypen</span><span class="sxs-lookup"><span data-stu-id="665ca-111">Other Call Types</span></span>

<span data-ttu-id="665ca-112">Beim ersten Öffnen des Berichts wird eine Zusammenfassung zu den einzelnen Kategorien angezeigt.</span><span class="sxs-lookup"><span data-stu-id="665ca-112">When you first open the report, you see summary information for each of these categories.</span></span> <span data-ttu-id="665ca-113">Ohne den Bericht zu verlassen, können Sie jede Kategorie erweitern, um Unterkategorien wie Aufrufe von Office Communicator 2007 R2 an lync 2013 zu betrachten.</span><span class="sxs-lookup"><span data-stu-id="665ca-113">Without leaving the report, you can expand each category to look at subcategories such as calls made from Office Communicator 2007 R2 to Lync 2013.</span></span> <span data-ttu-id="665ca-114">Diese Unterkategorien können Sie anschließend erweitern, um Details zu jedem in diesen Unterkategorien getätigten Anruf anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="665ca-114">In turn, you can then drill down into these subcategories to see details about each call made within that subcategory.</span></span>

<span data-ttu-id="665ca-115">In Microsoft lync Server 2013 im zusammenfassenden Bericht über Medienqualität werden die Daten weiter in drei Anruftypen unterteilt: Audioanrufe, Videoanrufe und Anwendungsfreigabe Anrufe.</span><span class="sxs-lookup"><span data-stu-id="665ca-115">In Microsoft Lync Server 2013 the Media Quality Summary Report further breaks the data down into three call types: audio calls, video calls, and application sharing calls.</span></span> <span data-ttu-id="665ca-116">Für jeden Anruftyp gibt es im Bericht einen eigenen Bereich und eigenen benutzerdefinierten Satz von Anrufmetriken.</span><span class="sxs-lookup"><span data-stu-id="665ca-116">Each call type has its own section in the report, and its own custom set of call metrics.</span></span>

<span data-ttu-id="665ca-117">Im "Zusammenfassenden Bericht über Medienqualität" können Sie Filter anwenden, mit denen Sie die Anrufqualität zwischen verkabelten und drahtlosen Anrufen, internen und externen Anrufen sowie VPN- und Nicht-VPN-Anrufen vergleichen können.</span><span class="sxs-lookup"><span data-stu-id="665ca-117">The Media Quality Summary Report also allows you to apply filters that enable you to compare the call quality of wired calls vs. wireless calls, internal calls vs. external calls, and VPN calls vs. non-VPN calls.</span></span>

<div>

## <a name="accessing-the-media-quality-summary-report"></a><span data-ttu-id="665ca-118">Zugreifen auf den "Zusammenfassenden Bericht über Medienqualität"</span><span class="sxs-lookup"><span data-stu-id="665ca-118">Accessing the Media Quality Summary Report</span></span>

<span data-ttu-id="665ca-119">Auf den "Zusammenfassenden Bericht über Medienqualität" kann auf der Startseite "Überwachungsberichte" zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="665ca-119">The Media Quality Summary Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="665ca-120">Sie können einen Drilldown zum [Anruflistenbericht in lync Server 2013](lync-server-2013-call-list-report.md) durchführen, indem Sie auf eine der folgenden Metriken klicken:</span><span class="sxs-lookup"><span data-stu-id="665ca-120">You can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="665ca-121">Anruflautstärke</span><span class="sxs-lookup"><span data-stu-id="665ca-121">Call volume</span></span>

  - <span data-ttu-id="665ca-122">Prozentsatz der Anrufe schlechter Qualität</span><span class="sxs-lookup"><span data-stu-id="665ca-122">Poor call percentage</span></span>

<span data-ttu-id="665ca-123">Auf den "Zusammenfassenden Bericht über Medienqualität" können Sie auch zugreifen, indem Sie auf eine beliebige der folgenden Audioanrufmetriken klicken:</span><span class="sxs-lookup"><span data-stu-id="665ca-123">In addition, you can access the Media Quality Metrics Distribution Report by clicking any of the following audio call metrics:</span></span>

  - <span data-ttu-id="665ca-124">Roundtrip (ms)</span><span class="sxs-lookup"><span data-stu-id="665ca-124">Round trip (ms)</span></span>

  - <span data-ttu-id="665ca-125">Beeinträchtigung (MOS)</span><span class="sxs-lookup"><span data-stu-id="665ca-125">Degradation (MOS)</span></span>

  - <span data-ttu-id="665ca-126">Paketverlust</span><span class="sxs-lookup"><span data-stu-id="665ca-126">Packet loss</span></span>

  - <span data-ttu-id="665ca-127">Jitter (ms)</span><span class="sxs-lookup"><span data-stu-id="665ca-127">Jitter (ms)</span></span>

  - <span data-ttu-id="665ca-128">Ausblendungsverhältnis der Reparatur</span><span class="sxs-lookup"><span data-stu-id="665ca-128">Healer concealed ratio</span></span>

  - <span data-ttu-id="665ca-129">Streckungsverhältnis der Reparatur</span><span class="sxs-lookup"><span data-stu-id="665ca-129">Healer stretched ratio</span></span>

  - <span data-ttu-id="665ca-130">Komprimierungsverhältnis der Reparatur</span><span class="sxs-lookup"><span data-stu-id="665ca-130">Healer compressed ratio</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="665ca-131">Filter</span><span class="sxs-lookup"><span data-stu-id="665ca-131">Filters</span></span>

<span data-ttu-id="665ca-p104">Mithilfe von Filtern können Sie eine gezieltere Datenauswahl zurückgeben oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Bespielsweise können Sie im zusammenfassenden Bericht über Medienqualität die zurückgegebenen Daten nach Zugriffstyp (d. h. interner oder externer Zugriff) oder nach Netzwerkverbindung (Kabel- oder Funkverbindung) filtern. Sie können außerdem festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden die Anrufe nach Stunde, Tag, Woche oder Monat zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="665ca-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Media Quality Summary Report enables you to filter the returned data by such things as access type (that is, interval access vs. external access) or by wired/wireless network connection. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="665ca-136">In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Zusammenfassenden Bericht über Medienqualität verwenden können.</span><span class="sxs-lookup"><span data-stu-id="665ca-136">The following table lists the filters that you can use with the Media Quality Summary Report.</span></span>

### <a name="media-quality-summary-report-filters"></a><span data-ttu-id="665ca-137">Filter im Zusammenfassenden Bericht über Medienqualität</span><span class="sxs-lookup"><span data-stu-id="665ca-137">Media Quality Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="665ca-138">Name</span><span class="sxs-lookup"><span data-stu-id="665ca-138">Name</span></span></th>
<th><span data-ttu-id="665ca-139">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="665ca-139">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="665ca-140"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="665ca-140"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="665ca-p105">Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="665ca-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="665ca-143">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="665ca-143">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="665ca-p106">Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="665ca-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="665ca-146">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="665ca-146">7/7/2012</span></span></p>
<p><span data-ttu-id="665ca-147">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="665ca-147">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="665ca-148">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="665ca-148">7/3/2012</span></span></p>
<p><span data-ttu-id="665ca-149">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="665ca-149">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="665ca-150"><strong>Ziel</strong></span><span class="sxs-lookup"><span data-stu-id="665ca-150"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="665ca-p107">Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="665ca-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="665ca-153">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="665ca-153">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="665ca-p108">Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="665ca-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="665ca-156">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="665ca-156">7/7/2012</span></span></p>
<p><span data-ttu-id="665ca-157">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="665ca-157">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="665ca-158">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="665ca-158">7/3/2012</span></span></p>
<p><span data-ttu-id="665ca-159">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="665ca-159">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="665ca-160"><strong>Zugriffstyp</strong></span><span class="sxs-lookup"><span data-stu-id="665ca-160"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="665ca-p109">Gibt an, ob der Client am internen oder am externen Netzwerk angemeldet wurde, als der Anruf getätigt wurde. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="665ca-p109">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="665ca-163">Alle</span><span class="sxs-lookup"><span data-stu-id="665ca-163">[All]</span></span></p></li>
<li><p><span data-ttu-id="665ca-164">Intern</span><span class="sxs-lookup"><span data-stu-id="665ca-164">Internal</span></span></p></li>
<li><p><span data-ttu-id="665ca-165">Extern</span><span class="sxs-lookup"><span data-stu-id="665ca-165">External</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="665ca-166"><strong>Netzwerktyp</strong></span><span class="sxs-lookup"><span data-stu-id="665ca-166"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="665ca-p110">Gibt den Typ des Netzwerks an, mit dem der Client verbunden wurde, als der Anruf erfolgte. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="665ca-p110">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="665ca-169">Alle</span><span class="sxs-lookup"><span data-stu-id="665ca-169">[All]</span></span></p></li>
<li><p><span data-ttu-id="665ca-170">Wired</span><span class="sxs-lookup"><span data-stu-id="665ca-170">Wired</span></span></p></li>
<li><p><span data-ttu-id="665ca-171">Drahtlos</span><span class="sxs-lookup"><span data-stu-id="665ca-171">Wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="665ca-172"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="665ca-172"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="665ca-p111">Gibt an, ob ein externer Client eine VPN-Verbindung (Virtual Private Network) verwendete, als der Anruf getätigt wurde. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="665ca-p111">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="665ca-175">Alle</span><span class="sxs-lookup"><span data-stu-id="665ca-175">[All]</span></span></p></li>
<li><p><span data-ttu-id="665ca-176">VPN</span><span class="sxs-lookup"><span data-stu-id="665ca-176">VPN</span></span></p></li>
<li><p><span data-ttu-id="665ca-177">Nicht-VPN</span><span class="sxs-lookup"><span data-stu-id="665ca-177">Non-VPN</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="665ca-178">Metriken</span><span class="sxs-lookup"><span data-stu-id="665ca-178">Metrics</span></span>

<span data-ttu-id="665ca-179">In der folgenden Tabelle werden Metriken aufgelistet, die im Zusammenfassenden Bericht über Medienqualität angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="665ca-179">The following table lists the information provided in the Media Quality Summary Report.</span></span>

### <a name="media-quality-summary-report-metrics-audio-call-summary"></a><span data-ttu-id="665ca-180">Metriken im "Zusammenfassenden Bericht über Medienqualität": Zusammenfassung der Audioanrufe</span><span class="sxs-lookup"><span data-stu-id="665ca-180">Media Quality Summary Report Metrics: Audio Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="665ca-181">Name</span><span class="sxs-lookup"><span data-stu-id="665ca-181">Name</span></span></th>
<th><span data-ttu-id="665ca-182">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="665ca-182">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="665ca-183">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="665ca-183">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="665ca-184"><strong>Anruftyp/Endpunkttyp</strong></span><span class="sxs-lookup"><span data-stu-id="665ca-184"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="665ca-185">Nein</span><span class="sxs-lookup"><span data-stu-id="665ca-185">No</span></span></p></td>
<td><p><span data-ttu-id="665ca-p112">Wenn Sie auf dieses Element klicken, zeigt der Bericht Details zu den auf diesem Typ basierenden Anrufen. Es gibt folgende Anruftypen:</span><span class="sxs-lookup"><span data-stu-id="665ca-p112">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="665ca-188">UC-Peer-zu-Peer-Anrufe</span><span class="sxs-lookup"><span data-stu-id="665ca-188">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="665ca-189">UC-Konferenzsitzungen</span><span class="sxs-lookup"><span data-stu-id="665ca-189">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="665ca-190">PSTN-Konferenzsitzungen</span><span class="sxs-lookup"><span data-stu-id="665ca-190">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="665ca-191">PSTN-Anrufe: Medienumgehung</span><span class="sxs-lookup"><span data-stu-id="665ca-191">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="665ca-192">PSTN-Anrufe (keine Umgehung): UC-Abschnitt</span><span class="sxs-lookup"><span data-stu-id="665ca-192">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="665ca-193">PSTN-Anrufe (keine Umgehung): Gateway-Abschnitt</span><span class="sxs-lookup"><span data-stu-id="665ca-193">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="665ca-194">Andere Anruftypen</span><span class="sxs-lookup"><span data-stu-id="665ca-194">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="665ca-195"><strong>Anrufvolumen</strong></span><span class="sxs-lookup"><span data-stu-id="665ca-195"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="665ca-196">Nein</span><span class="sxs-lookup"><span data-stu-id="665ca-196">No</span></span></p></td>
<td><p><span data-ttu-id="665ca-197">Die Gesamtzahl der Anrufe pro Anruftyp.</span><span class="sxs-lookup"><span data-stu-id="665ca-197">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="665ca-198"><strong>Prozentsatz der Anrufe schlechter Qualität</strong></span><span class="sxs-lookup"><span data-stu-id="665ca-198"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="665ca-199">Nein</span><span class="sxs-lookup"><span data-stu-id="665ca-199">No</span></span></p></td>
<td><p><span data-ttu-id="665ca-p113">Die Gesamtzahl der Anrufe, die als Anrufe schlechter Qualität klassifiziert werden. Dies sind Anrufe, bei denen für mindestens eine der gemessenen Metriken der zulässige Wert überschritten wurde (z. B. ein Anruf mit übermäßigem Jitter).</span><span class="sxs-lookup"><span data-stu-id="665ca-p113">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="665ca-202"><strong>Anrufvolumen (Funkanruf)</strong></span><span class="sxs-lookup"><span data-stu-id="665ca-202"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="665ca-203">Nein</span><span class="sxs-lookup"><span data-stu-id="665ca-203">No</span></span></p></td>
<td><p><span data-ttu-id="665ca-204">Die Gesamtzahl der Anrufe, für die eine Funkverbindung verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="665ca-204">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="665ca-205"><strong>Anrufvolumen (VPN-Anruf)</strong></span><span class="sxs-lookup"><span data-stu-id="665ca-205"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="665ca-206">Nein</span><span class="sxs-lookup"><span data-stu-id="665ca-206">No</span></span></p></td>
<td><p><span data-ttu-id="665ca-207">Die Gesamtzahl der Anrufe, für die eine VPN-Verbindung verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="665ca-207">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="665ca-208"><strong>Anrufvolumen (externer Anruf)</strong></span><span class="sxs-lookup"><span data-stu-id="665ca-208"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="665ca-209">Nein</span><span class="sxs-lookup"><span data-stu-id="665ca-209">No</span></span></p></td>
<td><p><span data-ttu-id="665ca-210">Die Gesamtzahl der Anrufe, für die eine externe Verbindung verwendet wurde (d. h. eine Verbindung außerhalb des internen Netzwerks).</span><span class="sxs-lookup"><span data-stu-id="665ca-210">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="665ca-211"><strong>Roundtrip (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="665ca-211"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="665ca-212">Nein</span><span class="sxs-lookup"><span data-stu-id="665ca-212">No</span></span></p></td>
<td><p><span data-ttu-id="665ca-p114">Die durchschnittliche Zeit (in Millisekunden), die ein RTP-Paket (Real-time Transport Protocol) benötigt, um zu einem anderen Endpunkt und wieder zurück zu gelangen. Eine Roundtripzeit von 100 ms oder weniger gilt als akzeptable Qualität.</span><span class="sxs-lookup"><span data-stu-id="665ca-p114">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="665ca-p115">Hohe Roundtripwerte können durch internationale Anrufweiterleitung, eine falsche Routingkonfiguration oder einen überlasteten Medienserver verursacht werden. Sie führen zu Problemen bei bidirektionalen Echtzeit-Audiounterhaltungen.</span><span class="sxs-lookup"><span data-stu-id="665ca-p115">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="665ca-217"><strong>Beeinträchtigung (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="665ca-217"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="665ca-218">Nein</span><span class="sxs-lookup"><span data-stu-id="665ca-218">No</span></span></p></td>
<td><p><span data-ttu-id="665ca-219">Die durchschnittliche Beeinträchtigung der Qualität, die gemäß Mean Opinion Score (MOS) während eines Anrufs auftrat.</span><span class="sxs-lookup"><span data-stu-id="665ca-219">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="665ca-220">Die Beeinträchtigungswerte liegen zwischen 0,0 (schlecht) und 5,0 (gut).</span><span class="sxs-lookup"><span data-stu-id="665ca-220">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="665ca-221">Ein Wert von 0,5 oder besser gilt als akzeptable Beeinträchtigung.</span><span class="sxs-lookup"><span data-stu-id="665ca-221">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="665ca-222">Früher wurden Mean Opinion Scores berechnet, indem man Benutzer die Qualität eines Telefongesprächs auf einer Skala von 1 bis 5 bewerten ließ.</span><span class="sxs-lookup"><span data-stu-id="665ca-222">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="665ca-223">In lync Server verwendet lync Server eine Reihe von Algorithmen, um vorherzusagen, wie Benutzer einen Anruf bewertet hätten.</span><span class="sxs-lookup"><span data-stu-id="665ca-223">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="665ca-p117">Hohe Beeinträchtigungswerte können durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver oder Endpunkt verursacht werden. Eine hohe Beeinträchtigung führt zu verzerrter oder unterbrochener Sprachübertragung.</span><span class="sxs-lookup"><span data-stu-id="665ca-p117">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="665ca-226"><strong>Paketverlust</strong></span><span class="sxs-lookup"><span data-stu-id="665ca-226"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="665ca-227">Nein</span><span class="sxs-lookup"><span data-stu-id="665ca-227">No</span></span></p></td>
<td><p><span data-ttu-id="665ca-p118">Die durchschnittliche Rate an RTP-Paketverlusten. Zu Paketverlusten kommt es, wenn RTP-Pakete (RTP ist ein Protokoll für die Übertragung von Audio und Video über das Internet) ihr Ziel nicht erreichen. Hohe Verlustraten werden allgemein durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver verursacht. Paketverluste führen in der Regel zu verzerrter oder unterbrochener Sprachübertragung.</span><span class="sxs-lookup"><span data-stu-id="665ca-p118">Average rate of RTP packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="665ca-231"><strong>Jitter (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="665ca-231"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="665ca-232">Nein</span><span class="sxs-lookup"><span data-stu-id="665ca-232">No</span></span></p></td>
<td><p><span data-ttu-id="665ca-233">Der durchschnittliche Jitter, der zwischen dem Eintreffen von RTP-Paketen ermittelt wurde.</span><span class="sxs-lookup"><span data-stu-id="665ca-233">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="665ca-234">(Jitter ist ein Maß für die &quot;Zittern&quot; eines Aufrufs.) Hohe Jitter-Werte werden normalerweise durch Überlastung oder einen überladenen Medienserver verursacht und führen zu verzerrten oder verlorenen Audiodaten.</span><span class="sxs-lookup"><span data-stu-id="665ca-234">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="665ca-235"><strong>Ausblendungsverhältnis der Reparatur</strong></span><span class="sxs-lookup"><span data-stu-id="665ca-235"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="665ca-236">Nein</span><span class="sxs-lookup"><span data-stu-id="665ca-236">No</span></span></p></td>
<td><p><span data-ttu-id="665ca-p120">Das durchschnittliche Verhältnis zwischen ausgeblendeten Audiosamples und der Gesamtzahl der Samples. (Ausgeblendete Audiosamples sind ein Verfahren zum "Glätten" der "holprigen" Übertragung, die normalerweise von verworfenen Netzwerkpaketen verursacht wird.) Ein hoher Wert gibt an, dass wegen Paketverlusten oder Jitters Verlustausblendung in großem Umfang angewendet wurde und führt zu verzerrter oder unterbrochener Sprachübertragung.</span><span class="sxs-lookup"><span data-stu-id="665ca-p120">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="665ca-239"><strong>Streckungsverhältnis der Reparatur</strong></span><span class="sxs-lookup"><span data-stu-id="665ca-239"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="665ca-240">Nein</span><span class="sxs-lookup"><span data-stu-id="665ca-240">No</span></span></p></td>
<td><p><span data-ttu-id="665ca-p121">Das durchschnittliche Verhältnis zwischen gestreckten Audiosamples und der Gesamtzahl der Samples. (Gestrecktes Audio ist ein Verfahren zum Dehnen von Audiodaten, um die Gesprächsqualität aufrechtzuerhalten, wenn ein verworfenes Netzwerkpaket festgestellt wurde.) Ein hoher Wert gibt an, dass wegen Jitters Samplestreckung in hohem Umfang aufgetreten ist und führt zu roboterhafter oder verzerrter Sprachqualität.</span><span class="sxs-lookup"><span data-stu-id="665ca-p121">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="665ca-243"><strong>Komprimierungsverhältnis der Reparatur</strong></span><span class="sxs-lookup"><span data-stu-id="665ca-243"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="665ca-244">Nein</span><span class="sxs-lookup"><span data-stu-id="665ca-244">No</span></span></p></td>
<td><p><span data-ttu-id="665ca-p122">Das durchschnittliche Verhältnis zwischen komprimierten Audiosamples und der Gesamtzahl der Samples. (Komprimiertes Audio sind Audiodaten, die komprimiert wurden, um die Gesprächsqualität aufrechtzuerhalten, wenn ein verworfenes Netzwerkpaket festgestellt wurde.) Ein hoher Wert gibt an, dass wegen Jitters Samplekomprimierung in hohem Umfang angewendet wurde und führt zu zu schneller Sprachwiedergabe oder zu verzerrter Sprachqualität.</span><span class="sxs-lookup"><span data-stu-id="665ca-p122">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="media-quality-summary-report-metrics-video-call-summary"></a><span data-ttu-id="665ca-247">Metriken im "Zusammenfassenden Bericht über Medienqualität": Zusammenfassung der Videoanrufe</span><span class="sxs-lookup"><span data-stu-id="665ca-247">Media Quality Summary Report Metrics: Video Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="665ca-248">Name</span><span class="sxs-lookup"><span data-stu-id="665ca-248">Name</span></span></th>
<th><span data-ttu-id="665ca-249">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="665ca-249">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="665ca-250">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="665ca-250">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="665ca-251"><strong>Anruftyp/Endpunkttyp</strong></span><span class="sxs-lookup"><span data-stu-id="665ca-251"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="665ca-252">Nein</span><span class="sxs-lookup"><span data-stu-id="665ca-252">No</span></span></p></td>
<td><p><span data-ttu-id="665ca-p123">Wenn Sie auf dieses Element klicken, zeigt der Bericht Details zu den auf diesem Typ basierenden Anrufen. Es gibt folgende Anruftypen:</span><span class="sxs-lookup"><span data-stu-id="665ca-p123">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="665ca-255">UC-Peer-zu-Peer-Anrufe</span><span class="sxs-lookup"><span data-stu-id="665ca-255">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="665ca-256">UC-Konferenzsitzungen</span><span class="sxs-lookup"><span data-stu-id="665ca-256">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="665ca-257">PSTN-Konferenzsitzungen</span><span class="sxs-lookup"><span data-stu-id="665ca-257">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="665ca-258">PSTN-Anrufe: Medienumgehung</span><span class="sxs-lookup"><span data-stu-id="665ca-258">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="665ca-259">PSTN-Anrufe (keine Umgehung): UC-Abschnitt</span><span class="sxs-lookup"><span data-stu-id="665ca-259">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="665ca-260">PSTN-Anrufe (keine Umgehung): Gateway-Abschnitt</span><span class="sxs-lookup"><span data-stu-id="665ca-260">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="665ca-261">Andere Anruftypen</span><span class="sxs-lookup"><span data-stu-id="665ca-261">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="665ca-262"><strong>Anrufvolumen</strong></span><span class="sxs-lookup"><span data-stu-id="665ca-262"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="665ca-263">Nein</span><span class="sxs-lookup"><span data-stu-id="665ca-263">No</span></span></p></td>
<td><p><span data-ttu-id="665ca-264">Die Gesamtzahl der Anrufe pro Anruftyp.</span><span class="sxs-lookup"><span data-stu-id="665ca-264">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="665ca-265"><strong>Prozentsatz der Anrufe schlechter Qualität</strong></span><span class="sxs-lookup"><span data-stu-id="665ca-265"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="665ca-266">Nein</span><span class="sxs-lookup"><span data-stu-id="665ca-266">No</span></span></p></td>
<td><p><span data-ttu-id="665ca-p124">Die Gesamtzahl der Anrufe, die als Anrufe schlechter Qualität klassifiziert werden. Dies sind Anrufe, bei denen für mindestens eine der gemessenen Metriken der zulässige Wert überschritten wurde (z. B. ein Anruf mit übermäßigem Jitter).</span><span class="sxs-lookup"><span data-stu-id="665ca-p124">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="665ca-269"><strong>Anrufvolumen (Funkanruf)</strong></span><span class="sxs-lookup"><span data-stu-id="665ca-269"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="665ca-270">Nein</span><span class="sxs-lookup"><span data-stu-id="665ca-270">No</span></span></p></td>
<td><p><span data-ttu-id="665ca-271">Die Gesamtzahl der Anrufe, für die eine Funkverbindung verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="665ca-271">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="665ca-272"><strong>Anrufvolumen (VPN-Anruf)</strong></span><span class="sxs-lookup"><span data-stu-id="665ca-272"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="665ca-273">Nein</span><span class="sxs-lookup"><span data-stu-id="665ca-273">No</span></span></p></td>
<td><p><span data-ttu-id="665ca-274">Die Gesamtzahl der Anrufe, für die eine VPN-Verbindung verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="665ca-274">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="665ca-275"><strong>Anrufvolumen (externer Anruf)</strong></span><span class="sxs-lookup"><span data-stu-id="665ca-275"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="665ca-276">Nein</span><span class="sxs-lookup"><span data-stu-id="665ca-276">No</span></span></p></td>
<td><p><span data-ttu-id="665ca-277">Die Gesamtzahl der Anrufe, für die eine externe Verbindung verwendet wurde (d. h. eine Verbindung außerhalb des internen Netzwerks).</span><span class="sxs-lookup"><span data-stu-id="665ca-277">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="665ca-278"><strong>Durchschnittliche Bitrate (KBit/s)</strong></span><span class="sxs-lookup"><span data-stu-id="665ca-278"><strong>Avg bit-rate (Kbits/s)</strong></span></span></p></td>
<td><p><span data-ttu-id="665ca-279">Nein</span><span class="sxs-lookup"><span data-stu-id="665ca-279">No</span></span></p></td>
<td><p><span data-ttu-id="665ca-280">Durchschnittliche Video-Bitrate (in Kilobit pro Sekunde).</span><span class="sxs-lookup"><span data-stu-id="665ca-280">Average video bit rate (in kilobits per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="665ca-281"><strong>Niedrige Bitrate %</strong></span><span class="sxs-lookup"><span data-stu-id="665ca-281"><strong>Low bit-rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="665ca-282">Nein</span><span class="sxs-lookup"><span data-stu-id="665ca-282">No</span></span></p></td>
<td><p><span data-ttu-id="665ca-283">Prozentsatz aller Anrufe, bei denen die Bitrate niedrig war.</span><span class="sxs-lookup"><span data-stu-id="665ca-283">Percentage of the call where the bit rate was low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="665ca-284"><strong>Verlust ausgehender Pakete</strong></span><span class="sxs-lookup"><span data-stu-id="665ca-284"><strong>Outbound packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="665ca-285">Nein</span><span class="sxs-lookup"><span data-stu-id="665ca-285">No</span></span></p></td>
<td><p><span data-ttu-id="665ca-p125">RTP-Paketverluste (Real-Time Transport Protocol) bei ausgehenden Paketen. (Zu Paketverlusten kommt es, wenn RTP-Pakete (ein Protokoll für die Übertragung von Audio und Video über das Internet) ihr Ziel nicht erreichen.) Hohe Verlustraten werden allgemein durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver verursacht. Paketverluste führen in der Regel zu verzerrter oder unterbrochener Sprachübertragung.</span><span class="sxs-lookup"><span data-stu-id="665ca-p125">Real-Time Transport Protocol (RTP) packet loss for outbound packets. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="665ca-289"><strong>Prozentzahl der eingefrorenen Frames</strong></span><span class="sxs-lookup"><span data-stu-id="665ca-289"><strong>Frozen frame %</strong></span></span></p></td>
<td><p><span data-ttu-id="665ca-290">Nein</span><span class="sxs-lookup"><span data-stu-id="665ca-290">No</span></span></p></td>
<td><p><span data-ttu-id="665ca-p126">Prozentsatz der "eingefrorenen" Frames. In einem eingefrorenen Frame wird das Video nicht fortgesetzt, während der Audioteil des Anrufs weitergeht.</span><span class="sxs-lookup"><span data-stu-id="665ca-p126">Percentage of “frozen” frames. In a frozen frame, the video stops advancing while the audio portion of the call continues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="665ca-293"><strong>Durchschnittliche ausgehende Framerate</strong></span><span class="sxs-lookup"><span data-stu-id="665ca-293"><strong>Outbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="665ca-294">Nein</span><span class="sxs-lookup"><span data-stu-id="665ca-294">No</span></span></p></td>
<td><p><span data-ttu-id="665ca-295">Durchschnittliche Framerate für ausgehende Übertragungen während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="665ca-295">Average frame rate for outbound transmissions during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="665ca-296"><strong>Durchschnittliche eingehende Framerate</strong></span><span class="sxs-lookup"><span data-stu-id="665ca-296"><strong>Inbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="665ca-297">Nein</span><span class="sxs-lookup"><span data-stu-id="665ca-297">No</span></span></p></td>
<td><p><span data-ttu-id="665ca-298">Durchschnittliche Framerate für eingehende Übertragungen während des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="665ca-298">Average frame rate for incoming transmissions during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="665ca-299"><strong>Niedrige eingehende Framerate %</strong></span><span class="sxs-lookup"><span data-stu-id="665ca-299"><strong>Inbound low frame rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="665ca-300">Nein</span><span class="sxs-lookup"><span data-stu-id="665ca-300">No</span></span></p></td>
<td><p><span data-ttu-id="665ca-301">Prozentsatz aller Anrufe, bei denen die Bitrate für eingehende Videodaten niedrig war.</span><span class="sxs-lookup"><span data-stu-id="665ca-301">Percentage of the call where the bit rate for incoming video was low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="665ca-302"><strong>Clientintegrität %</strong></span><span class="sxs-lookup"><span data-stu-id="665ca-302"><strong>Client health %</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="665ca-303">Gibt die relative Integrität des Clientgeräts während des Anrufs an.</span><span class="sxs-lookup"><span data-stu-id="665ca-303">Indicates the relative health of the client device during the call.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="media-quality-summary-report-metrics-application-sharing-call-summary"></a><span data-ttu-id="665ca-304">Metriken im "Zusammenfassenden Bericht über Medienqualität": Zusammenfassung der Anwendungsfreigabeanrufe</span><span class="sxs-lookup"><span data-stu-id="665ca-304">Media Quality Summary Report Metrics: Application Sharing Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="665ca-305">Name</span><span class="sxs-lookup"><span data-stu-id="665ca-305">Name</span></span></th>
<th><span data-ttu-id="665ca-306">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="665ca-306">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="665ca-307">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="665ca-307">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="665ca-308"><strong>Anruftyp/Endpunkttyp</strong></span><span class="sxs-lookup"><span data-stu-id="665ca-308"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="665ca-309">Nein</span><span class="sxs-lookup"><span data-stu-id="665ca-309">No</span></span></p></td>
<td><p><span data-ttu-id="665ca-p127">Wenn Sie auf dieses Element klicken, zeigt der Bericht Details zu den auf diesem Typ basierenden Anrufen. Es gibt folgende Anruftypen:</span><span class="sxs-lookup"><span data-stu-id="665ca-p127">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="665ca-312">UC-Peer-zu-Peer-Anrufe</span><span class="sxs-lookup"><span data-stu-id="665ca-312">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="665ca-313">UC-Konferenzsitzungen</span><span class="sxs-lookup"><span data-stu-id="665ca-313">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="665ca-314">PSTN-Konferenzsitzungen</span><span class="sxs-lookup"><span data-stu-id="665ca-314">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="665ca-315">PSTN-Anrufe: Medienumgehung</span><span class="sxs-lookup"><span data-stu-id="665ca-315">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="665ca-316">PSTN-Anrufe (keine Umgehung): UC-Abschnitt</span><span class="sxs-lookup"><span data-stu-id="665ca-316">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="665ca-317">PSTN-Anrufe (keine Umgehung): Gateway-Abschnitt</span><span class="sxs-lookup"><span data-stu-id="665ca-317">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="665ca-318">Andere Anruftypen</span><span class="sxs-lookup"><span data-stu-id="665ca-318">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="665ca-319"><strong>Anrufvolumen</strong></span><span class="sxs-lookup"><span data-stu-id="665ca-319"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="665ca-320">Nein</span><span class="sxs-lookup"><span data-stu-id="665ca-320">No</span></span></p></td>
<td><p><span data-ttu-id="665ca-321">Die Gesamtzahl der Anrufe pro Anruftyp.</span><span class="sxs-lookup"><span data-stu-id="665ca-321">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="665ca-322"><strong>Prozentsatz der Anrufe schlechter Qualität</strong></span><span class="sxs-lookup"><span data-stu-id="665ca-322"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="665ca-323">Nein</span><span class="sxs-lookup"><span data-stu-id="665ca-323">No</span></span></p></td>
<td><p><span data-ttu-id="665ca-p128">Die Gesamtzahl der Anrufe, die als Anrufe schlechter Qualität klassifiziert werden. Dies sind Anrufe, bei denen für mindestens eine der gemessenen Metriken der zulässige Wert überschritten wurde (z. B. ein Anruf mit übermäßigem Jitter).</span><span class="sxs-lookup"><span data-stu-id="665ca-p128">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="665ca-326"><strong>Anrufvolumen (Funkanruf)</strong></span><span class="sxs-lookup"><span data-stu-id="665ca-326"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="665ca-327">Nein</span><span class="sxs-lookup"><span data-stu-id="665ca-327">No</span></span></p></td>
<td><p><span data-ttu-id="665ca-328">Die Gesamtzahl der Anrufe, für die eine Funkverbindung verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="665ca-328">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="665ca-329"><strong>Anrufvolumen (VPN-Anruf)</strong></span><span class="sxs-lookup"><span data-stu-id="665ca-329"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="665ca-330">Nein</span><span class="sxs-lookup"><span data-stu-id="665ca-330">No</span></span></p></td>
<td><p><span data-ttu-id="665ca-331">Die Gesamtzahl der Anrufe, für die eine VPN-Verbindung verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="665ca-331">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="665ca-332"><strong>Anrufvolumen (externer Anruf)</strong></span><span class="sxs-lookup"><span data-stu-id="665ca-332"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="665ca-333">Nein</span><span class="sxs-lookup"><span data-stu-id="665ca-333">No</span></span></p></td>
<td><p><span data-ttu-id="665ca-334">Die Gesamtzahl der Anrufe, für die eine externe Verbindung verwendet wurde (d. h. eine Verbindung außerhalb des internen Netzwerks).</span><span class="sxs-lookup"><span data-stu-id="665ca-334">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="665ca-335"><strong>Jitter (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="665ca-335"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="665ca-336">Nein</span><span class="sxs-lookup"><span data-stu-id="665ca-336">No</span></span></p></td>
<td><p><span data-ttu-id="665ca-337">Der durchschnittliche Jitter, der zwischen dem Eintreffen von RTP-Paketen ermittelt wurde.</span><span class="sxs-lookup"><span data-stu-id="665ca-337">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="665ca-338">(Jitter ist ein Maß für die &quot;Zittern&quot; eines Aufrufs.) Hohe Jitter-Werte werden normalerweise durch Überlastung oder einen überladenen Medienserver verursacht und führen zu verzerrten oder verlorenen Audiodaten.</span><span class="sxs-lookup"><span data-stu-id="665ca-338">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="665ca-339"><strong>Durchschnitt relativ unidirektional</strong></span><span class="sxs-lookup"><span data-stu-id="665ca-339"><strong>Avg. relative one way</strong></span></span></p></td>
<td><p><span data-ttu-id="665ca-340">Nein</span><span class="sxs-lookup"><span data-stu-id="665ca-340">No</span></span></p></td>
<td><p><span data-ttu-id="665ca-p130">Durchschnittliche relative unidirektionale Verzögerung zwischen zwei Medienendpunkten. Dies ist ein Single-Hop-Latenzmaß.</span><span class="sxs-lookup"><span data-stu-id="665ca-p130">Average relative one-way delay between two media endpoints. This is a single-hop latency measure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="665ca-343"><strong>Durchschnittliche Latenz der RDP-Kachelverarbeitung</strong></span><span class="sxs-lookup"><span data-stu-id="665ca-343"><strong>Avg. RDP tile processing latency</strong></span></span></p></td>
<td><p><span data-ttu-id="665ca-344">Nein</span><span class="sxs-lookup"><span data-stu-id="665ca-344">No</span></span></p></td>
<td><p><span data-ttu-id="665ca-345">Die durchschnittliche Latenz der RDP-Kachelverarbeitung im AS-Konferenzserver über die Dauer der Anzeigesitzung.</span><span class="sxs-lookup"><span data-stu-id="665ca-345">The average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="665ca-346">Ein hoher Durchschnitt zeigt eine längere Verzögerung bei der Anzeige an und umfasst die Netzwerkwartezeit.</span><span class="sxs-lookup"><span data-stu-id="665ca-346">A high average reflects a longer delay in the viewing experience, and includes network latency.</span></span> <span data-ttu-id="665ca-347">Bei einem überlasteten Konferenzserver können längere durchschnittliche Verzögerungen auftreten.</span><span class="sxs-lookup"><span data-stu-id="665ca-347">An overloaded conferencing server may experience higher average delays.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="665ca-348"><strong>Insgesamt schlechte Kacheln %</strong></span><span class="sxs-lookup"><span data-stu-id="665ca-348"><strong>Total spoiled tile %</strong></span></span></p></td>
<td><p><span data-ttu-id="665ca-349">Nein</span><span class="sxs-lookup"><span data-stu-id="665ca-349">No</span></span></p></td>
<td><p><span data-ttu-id="665ca-350">Gesamtprozentsatz schlechter RDP-Kacheln.</span><span class="sxs-lookup"><span data-stu-id="665ca-350">Total percentage of spoiled RDP tiles.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

