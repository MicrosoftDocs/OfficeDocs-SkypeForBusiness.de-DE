---
title: 'Lync Server 2013: Standort-Trend Bericht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location Trend Report
ms:assetid: 61e2db3c-9f10-4411-8e7e-c6950faf8533
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204941(v=OCS.15)
ms:contentKeyID: 48184280
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e74cf4e763272f2309e358120abb12b0424aa40b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030939"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="location-trend-report-in-lync-server-2013"></a><span data-ttu-id="f00ad-102">Standort Trend Bericht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f00ad-102">Location Trend Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f00ad-103">_**Letztes Änderungsstand des Themas:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="f00ad-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="f00ad-104">Der Standort-Trendbericht enthält Angaben über den Verlauf der Anrufqualität für Netzwerkstandorte.</span><span class="sxs-lookup"><span data-stu-id="f00ad-104">The Location Trend Report provides call quality trend information for network locations.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="f00ad-105">Filter</span><span class="sxs-lookup"><span data-stu-id="f00ad-105">Filters</span></span>

<span data-ttu-id="f00ad-p101">Mithilfe von Filtern können Sie eine bestimmte Untermenge von Daten zurückgeben oder zurückgegebene Daten anders anzeigen lassen. So können Sie zum Beispiel im Standort-Trendbericht die zurückgegebenen Daten nach Aspekten wie dem Zugriffstyp (d. h. interner oder externer Zugriff) oder dem Netzwerktyp (verkabelt oder Funk) filtern. Sie können auch festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden die Anrufe nach Stunde, Tag oder Woche gruppiert.</span><span class="sxs-lookup"><span data-stu-id="f00ad-p101">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Location Trend Report enables you to filter the returned data by such things as access type (that is, interval access vs. external access) or by wired/wireless network connection. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, or week.</span></span>

<span data-ttu-id="f00ad-110">In der folgenden Tabelle sind die Filter aufgeführt, die Sie beim Standort-Trendbericht verwenden können.</span><span class="sxs-lookup"><span data-stu-id="f00ad-110">The following table lists the filters that you can use with the Location Trend Report.</span></span>

### <a name="location-trend-report-filters"></a><span data-ttu-id="f00ad-111">Filter im Standort-Trendbericht</span><span class="sxs-lookup"><span data-stu-id="f00ad-111">Location Trend Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f00ad-112">Name</span><span class="sxs-lookup"><span data-stu-id="f00ad-112">Name</span></span></th>
<th><span data-ttu-id="f00ad-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f00ad-113">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f00ad-114"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="f00ad-114"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="f00ad-p102">Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="f00ad-p102">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="f00ad-117">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="f00ad-117">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="f00ad-p103">Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="f00ad-p103">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="f00ad-120">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="f00ad-120">7/7/2012</span></span></p>
<p><span data-ttu-id="f00ad-121">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="f00ad-121">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="f00ad-122">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="f00ad-122">7/3/2012</span></span></p>
<p><span data-ttu-id="f00ad-123">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="f00ad-123">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f00ad-124"><strong>Ziel</strong></span><span class="sxs-lookup"><span data-stu-id="f00ad-124"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="f00ad-p104">Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="f00ad-p104">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="f00ad-127">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="f00ad-127">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="f00ad-p105">Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="f00ad-p105">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="f00ad-130">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="f00ad-130">7/7/2012</span></span></p>
<p><span data-ttu-id="f00ad-131">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="f00ad-131">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="f00ad-132">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="f00ad-132">7/3/2012</span></span></p>
<p><span data-ttu-id="f00ad-133">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="f00ad-133">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f00ad-134"><strong>Intervall</strong></span><span class="sxs-lookup"><span data-stu-id="f00ad-134"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="f00ad-p106">Zeitintervall. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="f00ad-p106">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="f00ad-137">Stündlich (maximal 25 Stunden können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="f00ad-137">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="f00ad-138">Täglich (maximal 31 Tage können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="f00ad-138">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="f00ad-139">Wöchentlich (maximal 12 Wochen können angezeigt werden)</span><span class="sxs-lookup"><span data-stu-id="f00ad-139">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="f00ad-p107">Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Beispiel: Wenn Sie das Intervall "Täglich" mit dem Startdatum 01.01.2011 und dem Enddatum 28.02.2011 ausgewählt haben, werden Daten für die Tage 01.08.2011 12:00 Uhr bis 01.09.2011 12:00 Uhr angezeigt (d. h. Daten für insgesamt 31 Tage).</span><span class="sxs-lookup"><span data-stu-id="f00ad-p107">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 1/1/2011 and an end date of 2/28/2011, data is displayed for the days 8/1/2011 12:00 AM to 9/1/2011 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f00ad-142"><strong>Zugriffstyp</strong></span><span class="sxs-lookup"><span data-stu-id="f00ad-142"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="f00ad-p108">Gibt an, ob der Client am internen oder am externen Netzwerk angemeldet wurde, als der Anruf getätigt wurde. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="f00ad-p108">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="f00ad-145">Alle</span><span class="sxs-lookup"><span data-stu-id="f00ad-145">[All]</span></span></p></li>
<li><p><span data-ttu-id="f00ad-146">Intern</span><span class="sxs-lookup"><span data-stu-id="f00ad-146">Internal</span></span></p></li>
<li><p><span data-ttu-id="f00ad-147">Extern</span><span class="sxs-lookup"><span data-stu-id="f00ad-147">External</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f00ad-148"><strong>Netzwerktyp</strong></span><span class="sxs-lookup"><span data-stu-id="f00ad-148"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="f00ad-p109">Gibt den Typ des Netzwerks an, mit dem der Client verbunden wurde, als der Anruf erfolgte. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="f00ad-p109">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="f00ad-151">Alle</span><span class="sxs-lookup"><span data-stu-id="f00ad-151">[All]</span></span></p></li>
<li><p><span data-ttu-id="f00ad-152">Wired</span><span class="sxs-lookup"><span data-stu-id="f00ad-152">Wired</span></span></p></li>
<li><p><span data-ttu-id="f00ad-153">Drahtlos</span><span class="sxs-lookup"><span data-stu-id="f00ad-153">Wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f00ad-154"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="f00ad-154"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="f00ad-p110">Gibt an, ob ein externer Client eine VPN-Verbindung (Virtual Private Network) verwendete, als der Anruf getätigt wurde. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="f00ad-p110">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="f00ad-157">Alle</span><span class="sxs-lookup"><span data-stu-id="f00ad-157">[All]</span></span></p></li>
<li><p><span data-ttu-id="f00ad-158">VPN</span><span class="sxs-lookup"><span data-stu-id="f00ad-158">VPN</span></span></p></li>
<li><p><span data-ttu-id="f00ad-159">Nicht-VPN</span><span class="sxs-lookup"><span data-stu-id="f00ad-159">Non-VPN</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

