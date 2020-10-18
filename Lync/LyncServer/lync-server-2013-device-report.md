---
title: 'Lync Server 2013: gerätebericht'
description: 'Lync Server 2013: gerätebericht.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device Report
ms:assetid: f42e4d60-699b-4870-8bb5-13b51bb6eb2b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615049(v=OCS.15)
ms:contentKeyID: 48185807
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8bff8e973d5c3e2d96c18992a2a2d917d4deb1c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575121"
---
# <a name="device-report-in-lync-server-2013"></a><span data-ttu-id="5396f-103">Gerätebericht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5396f-103">Device Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5396f-104">_**Letztes Änderungsstand des Themas:** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="5396f-104">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="5396f-105">Der gerätebericht kann besser mit dem Titel Mikrofon und Lautsprecher gemeldet werden. Das liegt daran, dass der gerätebericht anrufbezogene Metriken (wie Prozentsatz für schlechte Anrufe, Echos und Zeit für den Sprachwechsel) abruft, die von den Mikrofonen und Lautsprechern gruppiert werden, die im Anruf verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5396f-105">The Device Report might be better titled the Microphone and Speakers Report; that's because the Device Report retrieves call-related metrics (such as poor call percentage, echo, and voice switch time) grouped by the microphones and speakers used in the call.</span></span> <span data-ttu-id="5396f-106">Wenn Sie an IP-Telefonen interessiert sind (auch allgemein als "Geräte" bezeichnet), verwenden Sie stattdessen den Bericht über den [IP-Telefon bestand in lync Server 2013](lync-server-2013-ip-phone-inventory-report.md) .</span><span class="sxs-lookup"><span data-stu-id="5396f-106">If you are interested in IP phones (also commonly referred to as "devices"), use the [IP Phone Inventory Report in Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md) instead.</span></span>

<span data-ttu-id="5396f-107">Der gerätebericht ist für Administratoren äußerst nützlich, wenn Sie feststellen, ob ein bestimmter Gerätetyp hohe Mengen schlechter Qualität als andere Anrufe erfährt.</span><span class="sxs-lookup"><span data-stu-id="5396f-107">The Device Report is extremely useful for administrators in determining if a specific type of device is experiencing high volumes of poor quality calls than others.</span></span> <span data-ttu-id="5396f-108">Dies kann wiederum alle Entscheidungen beeinflussen, die Sie treffen müssen, wenn es an der Zeit ist, neue Geräte zu kaufen oder vorhandene Geräte zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="5396f-108">In turn, this could influence any decisions you must make when it comes time to buy new devices or to replace existing devices.</span></span>

<span data-ttu-id="5396f-109">Die im gerätebericht angezeigten Informationen basieren standardmäßig auch auf dem Mikrofon (dem Aufnahmegerät) und dem Lautsprecher/Headset (dem Render-Gerät), das im Anruf verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5396f-109">By default, the information displayed in the Device Report is also based on the microphone (the capture device) and speakers/headset (the render device) used in the call.</span></span> <span data-ttu-id="5396f-110">Nehmen wir beispielsweise an, Sie haben mehrere Benutzer, die das folgende Aufnahmegerät und das folgende Render-Gerät verwenden: Standardmäßig basieren die im gerätebericht angezeigten Informationen auch auf dem Mikrofon (dem Aufnahmegerät) und dem Lautsprecher/Headset (dem Render-Gerät), das im Anruf verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5396f-110">For example, suppose you have several users who use the following capture device and the following render device: By default, the information displayed in the Device Report is also based on the microphone (the capture device) and speakers/headset (the render device) used in the call.</span></span> <span data-ttu-id="5396f-111">Nehmen wir beispielsweise an, Sie haben mehrere Benutzer, die das folgende Capture-Gerät und das folgende Render-Gerät verwenden:</span><span class="sxs-lookup"><span data-stu-id="5396f-111">For example, suppose you have several users who use the following capture device and the following render device:</span></span>

  - <span data-ttu-id="5396f-112">Capture Device--Mikrofon (Soundmax Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="5396f-112">Capture device -- Microphone (SoundMAX Integrated Digital HD Audio)</span></span>

  - <span data-ttu-id="5396f-113">Render-Gerät--Headset-Ohrhörer (Microsoft LifeChat LX-3000)</span><span class="sxs-lookup"><span data-stu-id="5396f-113">Render device -- Headset Earphone (Microsoft LifeChat LX-3000)</span></span>

<span data-ttu-id="5396f-114">Wenn diese Benutzer insgesamt 254 Anrufe getätigt haben, sehen Sie einen Eintrag wie den folgenden im Bericht:</span><span class="sxs-lookup"><span data-stu-id="5396f-114">If those users made a total of 254 calls you'll see an entry like this in the report:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5396f-115">Aufnahmegerät</span><span class="sxs-lookup"><span data-stu-id="5396f-115">Capture device</span></span></th>
<th><span data-ttu-id="5396f-116">Darstellungsgerät</span><span class="sxs-lookup"><span data-stu-id="5396f-116">Render device</span></span></th>
<th><span data-ttu-id="5396f-117">Anruflautstärke</span><span class="sxs-lookup"><span data-stu-id="5396f-117">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5396f-118">Mikrofon (Soundmax Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="5396f-118">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="5396f-119">Headset-Ohrhörer (Microsoft LifeChat LX-3000)</span><span class="sxs-lookup"><span data-stu-id="5396f-119">Headset Earphone (Microsoft LifeChat LX-3000)</span></span></p></td>
<td><p><span data-ttu-id="5396f-120">254</span><span class="sxs-lookup"><span data-stu-id="5396f-120">254</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5396f-121">Angenommen, Sie verfügen über eine Reihe von Benutzern, die dasselbe Aufnahmegerät verwenden, aber ein anderes Render-Gerät.</span><span class="sxs-lookup"><span data-stu-id="5396f-121">Now, suppose you have a number of users who use that same capture device but a different render device.</span></span> <span data-ttu-id="5396f-122">In diesem Fall haben Sie einen zweiten Zeile-Eintrag im Bericht, einen für diese eindeutige Kombination aus Capture Device und Render Device:</span><span class="sxs-lookup"><span data-stu-id="5396f-122">In that case, you'll have a second line entry in the report, one for that unique combination of capture device and render device:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5396f-123">Aufnahmegerät</span><span class="sxs-lookup"><span data-stu-id="5396f-123">Capture device</span></span></th>
<th><span data-ttu-id="5396f-124">Darstellungsgerät</span><span class="sxs-lookup"><span data-stu-id="5396f-124">Render device</span></span></th>
<th><span data-ttu-id="5396f-125">Anruflautstärke</span><span class="sxs-lookup"><span data-stu-id="5396f-125">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5396f-126">Mikrofon (Soundmax Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="5396f-126">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="5396f-127">Headset-Ohrhörer (Microsoft LifeChat LX-3000)</span><span class="sxs-lookup"><span data-stu-id="5396f-127">Headset Earphone (Microsoft LifeChat LX-3000)</span></span></p></td>
<td><p><span data-ttu-id="5396f-128">254</span><span class="sxs-lookup"><span data-stu-id="5396f-128">254</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5396f-129">Mikrofon (Soundmax Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="5396f-129">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="5396f-130">Lautsprecher (Soundmax Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="5396f-130">Speakers (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="5396f-131">319</span><span class="sxs-lookup"><span data-stu-id="5396f-131">319</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5396f-132">Wenn Sie lieber kombinierte Gesamtsummen für ein bestimmtes Gerät (beispielsweise für das SoundMAX-Aufnahmegerät, unabhängig vom verwendeten Render-Gerät) anzeigen möchten, wählen Sie in der Dropdownliste Gerätetyp die entsprechende Option aus (entweder Capture-Gerät oder Render-Gerät).</span><span class="sxs-lookup"><span data-stu-id="5396f-132">If you would rather see combined totals for a given device (for example, for the SoundMAX capture device, regardless of the render device used), select the appropriate option from the Device type dropdown list (either Capture device or Render device).</span></span> <span data-ttu-id="5396f-133">Wenn Sie in diesem Beispiel Capture Device auswählen, erhalten Sie eine ähnliche Ausgabe wie die folgende:</span><span class="sxs-lookup"><span data-stu-id="5396f-133">If you select Capture device in this example, that will give you output similar to this:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5396f-134">Aufnahmegerät</span><span class="sxs-lookup"><span data-stu-id="5396f-134">Capture device</span></span></th>
<th><span data-ttu-id="5396f-135">Anruflautstärke</span><span class="sxs-lookup"><span data-stu-id="5396f-135">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5396f-136">Mikrofon (Soundmax Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="5396f-136">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="5396f-137">573</span><span class="sxs-lookup"><span data-stu-id="5396f-137">573</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="accessing-the-device-report"></a><span data-ttu-id="5396f-138">Zugreifen auf den gerätebericht</span><span class="sxs-lookup"><span data-stu-id="5396f-138">Accessing the Device Report</span></span>

<span data-ttu-id="5396f-139">Auf den gerätebericht wird normalerweise über die Startseite für Überwachungsberichte zugegriffen.</span><span class="sxs-lookup"><span data-stu-id="5396f-139">The Device Report is typically accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="5396f-140">Wenn Sie jedoch den [Anruf Detail Bericht in lync Server 2013](lync-server-2013-call-detail-report.md) anzeigen, können Sie durch Klicken auf eine der folgenden Metriken einen Drilldown zum gerätebericht für ein bestimmtes Gerät ausführen:</span><span class="sxs-lookup"><span data-stu-id="5396f-140">However, if you are viewing the [Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) you can drill down to the Device Report for a specific device by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="5396f-141">Capture-Gerät</span><span class="sxs-lookup"><span data-stu-id="5396f-141">Capture Device</span></span>

  - <span data-ttu-id="5396f-142">Render-Gerät</span><span class="sxs-lookup"><span data-stu-id="5396f-142">Render Device</span></span>

<span data-ttu-id="5396f-143">Im gerätebericht können Sie einen Drilldown zum [Anruflistenbericht in lync Server 2013](lync-server-2013-call-list-report.md) durchführen, indem Sie auf eine der folgenden Metriken klicken:</span><span class="sxs-lookup"><span data-stu-id="5396f-143">From the Device Report you can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="5396f-144">Anrufvolumen</span><span class="sxs-lookup"><span data-stu-id="5396f-144">Call volume</span></span>

  - <span data-ttu-id="5396f-145">Prozentsatz der Anrufe schlechter Qualität</span><span class="sxs-lookup"><span data-stu-id="5396f-145">Poor call percentage</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-device-report"></a><span data-ttu-id="5396f-146">Optimale Verwendung des Geräte Berichts</span><span class="sxs-lookup"><span data-stu-id="5396f-146">Making the Best Use of the Device Report</span></span>

<span data-ttu-id="5396f-147">Wenn es um Gerätenamen geht, ist der gerätebericht äußerst detailliert; nehmen wir beispielsweise an, Sie haben die folgenden Capture-Geräte:</span><span class="sxs-lookup"><span data-stu-id="5396f-147">When it comes to device names, the Device Report is extremely detailed; for example, suppose you have the following capture devices:</span></span>

  - <span data-ttu-id="5396f-148">Aastra 3002-Mikrofon (2-Aastra 3002)</span><span class="sxs-lookup"><span data-stu-id="5396f-148">Aastra 3002 Microphone (2- Aastra 3002)</span></span>

  - <span data-ttu-id="5396f-149">Aastra 3002-Mikrofon (3-Aastra 3002)</span><span class="sxs-lookup"><span data-stu-id="5396f-149">Aastra 3002 Microphone (3- Aastra 3002)</span></span>

  - <span data-ttu-id="5396f-150">Aastra 3002-Mikrofon (Aastra 3002)</span><span class="sxs-lookup"><span data-stu-id="5396f-150">Aastra 3002 Microphone (Aastra 3002)</span></span>

  - <span data-ttu-id="5396f-151">Aastra 6725ip</span><span class="sxs-lookup"><span data-stu-id="5396f-151">Aastra 6725ip</span></span>

  - <span data-ttu-id="5396f-152">Aastra 6725ip-Mikrofon (10-Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="5396f-152">Aastra 6725ip Microphone (10- Aastra 6725ip)</span></span>

  - <span data-ttu-id="5396f-153">Aastra 6725ip-Mikrofon (10-Aastra 6725ip)-v0</span><span class="sxs-lookup"><span data-stu-id="5396f-153">Aastra 6725ip Microphone (10- Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="5396f-154">Aastra 6725ip-Mikrofon (2-Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="5396f-154">Aastra 6725ip Microphone (2- Aastra 6725ip)</span></span>

  - <span data-ttu-id="5396f-155">Aastra 6725ip-Mikrofon (3-Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="5396f-155">Aastra 6725ip Microphone (3- Aastra 6725ip)</span></span>

  - <span data-ttu-id="5396f-156">Aastra 6725ip-Mikrofon (4-Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="5396f-156">Aastra 6725ip Microphone (4- Aastra 6725ip)</span></span>

  - <span data-ttu-id="5396f-157">Aastra 6725ip-Mikrofon (5-Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="5396f-157">Aastra 6725ip Microphone (5- Aastra 6725ip)</span></span>

  - <span data-ttu-id="5396f-158">Aastra 6725ip-Mikrofon (6-Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="5396f-158">Aastra 6725ip Microphone (6- Aastra 6725ip)</span></span>

  - <span data-ttu-id="5396f-159">Aastra 6725ip-Mikrofon (7-Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="5396f-159">Aastra 6725ip Microphone (7- Aastra 6725ip)</span></span>

  - <span data-ttu-id="5396f-160">Aastra 6725ip-Mikrofon (9-Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="5396f-160">Aastra 6725ip Microphone (9- Aastra 6725ip)</span></span>

  - <span data-ttu-id="5396f-161">Aastra 6725ip-Mikrofon (9-Aastra 6725ip)-v0</span><span class="sxs-lookup"><span data-stu-id="5396f-161">Aastra 6725ip Microphone (9- Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="5396f-162">Aastra 6725ip-Mikrofon (Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="5396f-162">Aastra 6725ip Microphone (Aastra 6725ip)</span></span>

  - <span data-ttu-id="5396f-163">Aastra 6725ip-Mikrofon (Aastra 6725ip)-v0</span><span class="sxs-lookup"><span data-stu-id="5396f-163">Aastra 6725ip Microphone (Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="5396f-164">Aastra 6725ip-Mikrofon (USB-Audiogerät)</span><span class="sxs-lookup"><span data-stu-id="5396f-164">Aastra 6725ip Microphone (USB Audio Device)</span></span>

  - <span data-ttu-id="5396f-165">Aastra 6725ip-Mikrofon (USB-Audiogerät)-v0</span><span class="sxs-lookup"><span data-stu-id="5396f-165">Aastra 6725ip Microphone (USB Audio Device)-V0</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5396f-166">Beachten Sie, dass Capture-Gerätenamen möglicherweise nicht identisch sind, wenn Sie lokalisierte Versionen von lync Server 2013 durchführen.</span><span class="sxs-lookup"><span data-stu-id="5396f-166">Keep in mind that capture device names might not be the same if you are running localized versions of Lync Server 2013.</span></span> <span data-ttu-id="5396f-167">Ein Gerät namens Aastra 6725ip Mikrofon (Aastra 6725ip)-v0 in US-Englisch könnte in Französisch oder Spanisch einen anderen Namen haben.</span><span class="sxs-lookup"><span data-stu-id="5396f-167">A device named Aastra 6725ip Microphone (Aastra 6725ip)-V0 in US English could have a different name in French or Spanish.</span></span>



</div>

<span data-ttu-id="5396f-168">Oft werden Sie diese Detailgenauigkeit wünschen. zu anderen Zeiten sind Sie jedoch möglicherweise nur daran interessiert, wie viele Anrufe ein Aastra-Mikrofon unabhängig von der Modellnummer verwenden.</span><span class="sxs-lookup"><span data-stu-id="5396f-168">Often times you'll want that level of detail; at other times, however, you might only be interested in how many calls use any Aastra microphone, regardless of model number.</span></span> <span data-ttu-id="5396f-169">Eine Möglichkeit zum Abrufen von Informationen wie das ist das Exportieren der Geräte Berichtsdaten in Microsoft Excel und das anschließende Speichern dieser Daten in einer Datei mit Komma getrennten Werten (beispielsweise C: \\ Daten \\ Geräte \_Report.csv).</span><span class="sxs-lookup"><span data-stu-id="5396f-169">One way to get information like that is to export the Device Report data to Microsoft Excel and then save that data to a comma-separated values file (for example, C:\\Data\\Devices\_Report.csv).</span></span> <span data-ttu-id="5396f-170">Anschließend können Sie eine Reihe von Befehlen wie diese verwenden, um die zu importieren. CSV-Datei in Windows PowerShell und melden Sie die Gesamtzahl der Anrufe, die mit einem Aastra Capture-Gerät ausgeführt wurden, zurück:</span><span class="sxs-lookup"><span data-stu-id="5396f-170">You can then use a set of commands similar to these to import the .CSV file into Windows PowerShell and report back the total number of calls made using an Aastra capture device:</span></span>

    $devices = Import-Csv "C:\Data\Device_Report.csv
    $sum = $devices | Where-Object {$_."Capture device" -match "Aastra"}
    $sum | foreach-object {[Int]$x = [Int]$x + [Int]$_."call volume"}
    $x

<span data-ttu-id="5396f-171">Dadurch wird ein einzelner Wert zurückgegeben, der die Gesamtzahl der mit einem Aastra Capture-Gerät getätigten Anrufe darstellt.</span><span class="sxs-lookup"><span data-stu-id="5396f-171">That will return a single value representing the total number of calls made using an Aastra capture device.</span></span> <span data-ttu-id="5396f-172">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="5396f-172">For example:</span></span>

    384

</div>

<div>

## <a name="filters"></a><span data-ttu-id="5396f-173">Filter</span><span class="sxs-lookup"><span data-stu-id="5396f-173">Filters</span></span>

<span data-ttu-id="5396f-174">Mithilfe von Filtern können Sie eine gezieltere Datenauswahl zurückgeben oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen.</span><span class="sxs-lookup"><span data-stu-id="5396f-174">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="5396f-175">Beispielsweise können Sie mit dem gerätebericht nach solchen Dingen wie dem Anruftyp (also dem Anruf eines Client Anrufs), einer Telefonkonferenz oder einem PSTN-Anruf (Public Switched Telephone Network) filtern.</span><span class="sxs-lookup"><span data-stu-id="5396f-175">For example, the Device Report enables you to filter on such things as call type (that is, was the call a client call), a conference call, or a public switched telephone network (PSTN) call.</span></span> <span data-ttu-id="5396f-176">Sie können außerdem festlegen, wie Daten gruppiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="5396f-176">You can also choose how data should be grouped.</span></span> <span data-ttu-id="5396f-177">In diesem Fall werden Geräte nach Stunde, Tag, Woche oder Monat gruppiert.</span><span class="sxs-lookup"><span data-stu-id="5396f-177">In this case, devices are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="5396f-178">In der folgenden Tabelle sind die Filter aufgeführt, die Sie mit dem gerätebericht verwenden können.</span><span class="sxs-lookup"><span data-stu-id="5396f-178">The following table lists the filters that you can use with the Device Report.</span></span>

### <a name="device-report-filters"></a><span data-ttu-id="5396f-179">Geräte Berichtsfilter</span><span class="sxs-lookup"><span data-stu-id="5396f-179">Device Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5396f-180">Name</span><span class="sxs-lookup"><span data-stu-id="5396f-180">Name</span></span></th>
<th><span data-ttu-id="5396f-181">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5396f-181">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5396f-182"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="5396f-182"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="5396f-p111">Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="5396f-p111">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="5396f-185">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="5396f-185">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="5396f-p112">Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="5396f-p112">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="5396f-188">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="5396f-188">7/7/2012</span></span></p>
<p><span data-ttu-id="5396f-189">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="5396f-189">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="5396f-190">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="5396f-190">7/3/2012</span></span></p>
<p><span data-ttu-id="5396f-191">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="5396f-191">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5396f-192"><strong>Ziel</strong></span><span class="sxs-lookup"><span data-stu-id="5396f-192"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="5396f-p113">Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="5396f-p113">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="5396f-195">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="5396f-195">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="5396f-p114">Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="5396f-p114">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="5396f-198">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="5396f-198">7/7/2012</span></span></p>
<p><span data-ttu-id="5396f-199">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="5396f-199">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="5396f-200">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="5396f-200">7/3/2012</span></span></p>
<p><span data-ttu-id="5396f-201">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="5396f-201">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5396f-202"><strong>Ursache für VoIP-Switch</strong></span><span class="sxs-lookup"><span data-stu-id="5396f-202"><strong>Voice switch cause</strong></span></span></p></td>
<td><p><span data-ttu-id="5396f-203">Grund, warum ein Anruf in den Halbduplexmodus versetzt werden musste, um Echo zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="5396f-203">Reason why a call had to be placed into half duplex mode in order to prevent echo.</span></span> <span data-ttu-id="5396f-204">Im Halbduplexmodus kann die Kommunikation gleichzeitig nur in eine Richtung erfolgen, ähnlich wie die Benutzer beim kommunizieren mit einem Walkie-Talkie abwechselnd wechseln.</span><span class="sxs-lookup"><span data-stu-id="5396f-204">In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie.</span></span> <span data-ttu-id="5396f-205">Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="5396f-205">Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="5396f-206">Alle</span><span class="sxs-lookup"><span data-stu-id="5396f-206">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="5396f-207">Keine</span><span class="sxs-lookup"><span data-stu-id="5396f-207">None</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="5396f-208">Falscher Zeitstempel</span><span class="sxs-lookup"><span data-stu-id="5396f-208">Bad timestamp</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="5396f-209">Echo</span><span class="sxs-lookup"><span data-stu-id="5396f-209">Echo</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="5396f-210">DNLP (dynamischer nichtlinearer Prozessor)</span><span class="sxs-lookup"><span data-stu-id="5396f-210">DNLP (dynamic nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="5396f-211">Geringe Komplexität</span><span class="sxs-lookup"><span data-stu-id="5396f-211">Low complexity</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="5396f-212">Ungültiger Gerätestatus</span><span class="sxs-lookup"><span data-stu-id="5396f-212">Bad device state</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="5396f-213">Post-AEC-Echo (akustische Echounterdrückung)</span><span class="sxs-lookup"><span data-stu-id="5396f-213">Post-AEC echo (acoustic echo cancellation)</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5396f-214"><strong>Echo Ursache</strong></span><span class="sxs-lookup"><span data-stu-id="5396f-214"><strong>Echo cause</strong></span></span></p></td>
<td><p><span data-ttu-id="5396f-215">Grund, warum Echo oberhalb der akzeptierten Ebene in einem Anruf erkannt wurde.</span><span class="sxs-lookup"><span data-stu-id="5396f-215">Reason why echo above the accepted level was detected in a call.</span></span> <span data-ttu-id="5396f-216">(In der Telekommunikation ist ECHO eine Reflexion des Klangs, das gleiche Phänomen, das Sie hören, wenn Sie auf den Grund eines Brunnens schreien.) Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="5396f-216">(In telecommunications, echo is a reflection of sound, the same phenomenon you will hear if you yell down to the bottom of a well.) Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="5396f-217">Alle</span><span class="sxs-lookup"><span data-stu-id="5396f-217">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="5396f-218">Keine</span><span class="sxs-lookup"><span data-stu-id="5396f-218">None</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="5396f-219">Falscher Zeitstempel</span><span class="sxs-lookup"><span data-stu-id="5396f-219">Bad timestamp</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="5396f-220">Post-AEC-Echo (akustische Echounterdrückung)</span><span class="sxs-lookup"><span data-stu-id="5396f-220">Post-AEC echo (acoustic echo cancellation)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="5396f-221">ANLP (adaptiver nichtlinearer Prozessor)</span><span class="sxs-lookup"><span data-stu-id="5396f-221">ANLP (adaptive nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="5396f-222">DNLP (dynamischer nichtlinearer Prozessor)</span><span class="sxs-lookup"><span data-stu-id="5396f-222">DNLP (dynamic nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="5396f-223">Mikrofon Clipping</span><span class="sxs-lookup"><span data-stu-id="5396f-223">Microphone clipping</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5396f-224"><strong>Anruftyp</strong></span><span class="sxs-lookup"><span data-stu-id="5396f-224"><strong>Call type</strong></span></span></p></td>
<td><p><span data-ttu-id="5396f-225">Gibt den Typ des Anrufs an, der ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="5396f-225">Indicates the type of call that was made.</span></span> <span data-ttu-id="5396f-226">Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="5396f-226">Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="5396f-227">Alle</span><span class="sxs-lookup"><span data-stu-id="5396f-227">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="5396f-228">Client Anruf</span><span class="sxs-lookup"><span data-stu-id="5396f-228">Client call</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="5396f-229">PSTN-Anruf</span><span class="sxs-lookup"><span data-stu-id="5396f-229">PSTN call</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="5396f-230">Konferenzanruf</span><span class="sxs-lookup"><span data-stu-id="5396f-230">Conference call</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5396f-231"><strong>Zugriffstyp</strong></span><span class="sxs-lookup"><span data-stu-id="5396f-231"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="5396f-p118">Gibt an, ob der Client am internen oder am externen Netzwerk angemeldet wurde, als der Anruf getätigt wurde. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="5396f-p118">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="5396f-234">Alle</span><span class="sxs-lookup"><span data-stu-id="5396f-234">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="5396f-235">Intern</span><span class="sxs-lookup"><span data-stu-id="5396f-235">Internal</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="5396f-236">Extern</span><span class="sxs-lookup"><span data-stu-id="5396f-236">External</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5396f-237"><strong>Netzwerktyp</strong></span><span class="sxs-lookup"><span data-stu-id="5396f-237"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="5396f-p119">Gibt den Typ des Netzwerks an, mit dem der Client verbunden wurde, als der Anruf erfolgte. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="5396f-p119">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="5396f-240">Alle</span><span class="sxs-lookup"><span data-stu-id="5396f-240">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="5396f-241">Wired</span><span class="sxs-lookup"><span data-stu-id="5396f-241">Wired</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="5396f-242">Drahtlos</span><span class="sxs-lookup"><span data-stu-id="5396f-242">Wireless</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5396f-243"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="5396f-243"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="5396f-p120">Gibt an, ob ein externer Client eine VPN-Verbindung (Virtual Private Network) verwendete, als der Anruf getätigt wurde. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="5396f-p120">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="5396f-246">Alle</span><span class="sxs-lookup"><span data-stu-id="5396f-246">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="5396f-247">VPN</span><span class="sxs-lookup"><span data-stu-id="5396f-247">VPN</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="5396f-248">Nicht-VPN</span><span class="sxs-lookup"><span data-stu-id="5396f-248">Non-VPN</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5396f-249"><strong>Gerätetyp</strong></span><span class="sxs-lookup"><span data-stu-id="5396f-249"><strong>Device type</strong></span></span></p></td>
<td><p><span data-ttu-id="5396f-250">Gibt den Gerätetyp an.</span><span class="sxs-lookup"><span data-stu-id="5396f-250">Indicates the type of device.</span></span> <span data-ttu-id="5396f-251">Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="5396f-251">Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="5396f-252">Aufnahmegerät</span><span class="sxs-lookup"><span data-stu-id="5396f-252">Capture device</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="5396f-253">Darstellungsgerät</span><span class="sxs-lookup"><span data-stu-id="5396f-253">Render device</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="5396f-254">Paar für Capture/Render-Geräte</span><span class="sxs-lookup"><span data-stu-id="5396f-254">Capture/Render device pair</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5396f-255"><strong>Gerätename</strong></span><span class="sxs-lookup"><span data-stu-id="5396f-255"><strong>Device name</strong></span></span></p></td>
<td><p><span data-ttu-id="5396f-256">Name des Capture-oder Render-Geräts.</span><span class="sxs-lookup"><span data-stu-id="5396f-256">Name of the capture or render device.</span></span> <span data-ttu-id="5396f-257">Sie können den vollständigen Gerätenamen oder einen Teil des Gerätenamens eingeben.</span><span class="sxs-lookup"><span data-stu-id="5396f-257">You can enter the complete device name or any portion of the device name.</span></span> <span data-ttu-id="5396f-258">Um beispielsweise das Gerätemikrofon zu finden (Microsoft LifeCam VX-1000.), können Sie den vollständigen Gerätenamen wie folgt eingeben:</span><span class="sxs-lookup"><span data-stu-id="5396f-258">For example, to find the device Microphone (Microsoft LifeCam VX-1000.), you can enter the complete device name as follows:</span></span></p>
<p><span data-ttu-id="5396f-259">Mikrofon (Microsoft LifeCam VX-1000.)</span><span class="sxs-lookup"><span data-stu-id="5396f-259">Microphone (Microsoft LifeCam VX-1000.)</span></span></p>
<p><span data-ttu-id="5396f-260">Sie können auch nur einen Teil des Namens eingeben.</span><span class="sxs-lookup"><span data-stu-id="5396f-260">Or, you can enter just a portion of the name.</span></span> <span data-ttu-id="5396f-261">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="5396f-261">For example:</span></span></p>
<p><span data-ttu-id="5396f-262">LifeCam</span><span class="sxs-lookup"><span data-stu-id="5396f-262">LifeCam</span></span></p>
<p><span data-ttu-id="5396f-263">Beachten Sie, dass der obige Filter jedes Gerät zurückgibt, das die Zeichenfolge &quot; LifeCam &quot; Anywhere in seinem Namen enthält.</span><span class="sxs-lookup"><span data-stu-id="5396f-263">Note that the preceding filter returns any device that contains the string &quot;LifeCam&quot; anywhere in its name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="5396f-264">Metriken</span><span class="sxs-lookup"><span data-stu-id="5396f-264">Metrics</span></span>

<span data-ttu-id="5396f-265">In der folgenden Tabelle sind die Informationen aufgeführt, die im gerätebericht angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="5396f-265">The following table lists the information provided in the Device Report.</span></span>

### <a name="device-report-metrics"></a><span data-ttu-id="5396f-266">Metriken für den gerätebericht</span><span class="sxs-lookup"><span data-stu-id="5396f-266">Device Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5396f-267">Name</span><span class="sxs-lookup"><span data-stu-id="5396f-267">Name</span></span></th>
<th><span data-ttu-id="5396f-268">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="5396f-268">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="5396f-269">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5396f-269">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5396f-270"><strong>Aufnahmegerät</strong></span><span class="sxs-lookup"><span data-stu-id="5396f-270"><strong>Capture device</strong></span></span></p></td>
<td><p><span data-ttu-id="5396f-271">Ja</span><span class="sxs-lookup"><span data-stu-id="5396f-271">Yes</span></span></p></td>
<td><p><span data-ttu-id="5396f-272">Gerät (zum Beispiel ein Mikrofon oder eine Webcam), das für die Übertragung von Audio verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5396f-272">Device (for example, a microphone or webcam) used for transmitting audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5396f-273"><strong>Darstellungsgerät</strong></span><span class="sxs-lookup"><span data-stu-id="5396f-273"><strong>Render device</strong></span></span></p></td>
<td><p><span data-ttu-id="5396f-274">Ja</span><span class="sxs-lookup"><span data-stu-id="5396f-274">Yes</span></span></p></td>
<td><p><span data-ttu-id="5396f-275">Gerät (zum Beispiel ein Headset oder Lautsprecher), das zum Empfangen von Audio verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5396f-275">Device (for example, a headset or speakers) used for receiving audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5396f-276"><strong>Anruflautstärke</strong></span><span class="sxs-lookup"><span data-stu-id="5396f-276"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="5396f-277">Ja</span><span class="sxs-lookup"><span data-stu-id="5396f-277">Yes</span></span></p></td>
<td><p><span data-ttu-id="5396f-278">Die Gesamtzahl der getätigten Anrufe.</span><span class="sxs-lookup"><span data-stu-id="5396f-278">Total number of calls placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5396f-279"><strong>Prozentsatz der Anrufe schlechter Qualität</strong></span><span class="sxs-lookup"><span data-stu-id="5396f-279"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="5396f-280">Ja</span><span class="sxs-lookup"><span data-stu-id="5396f-280">Yes</span></span></p></td>
<td><p><span data-ttu-id="5396f-281">Prozentsatz der Anrufe, die als unzureichend klassifiziert wurden &quot; . &quot; Bei einem schlechten Anruf handelt es sich um einen Anruf, bei dem mindestens eine der gemessenen Metriken den zulässigen Wert überschritten hat (beispielsweise ein Anruf, bei dem übermäßiger Jitter aufgetreten ist).</span><span class="sxs-lookup"><span data-stu-id="5396f-281">Percentage of calls that were classified as &quot;poor.&quot; A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5396f-282"><strong>Eindeutige Benutzer</strong></span><span class="sxs-lookup"><span data-stu-id="5396f-282"><strong>Unique users</strong></span></span></p></td>
<td><p><span data-ttu-id="5396f-283">Ja</span><span class="sxs-lookup"><span data-stu-id="5396f-283">Yes</span></span></p></td>
<td><p><span data-ttu-id="5396f-284">Eindeutige Benutzer, die das Gerät verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="5396f-284">Unique users who used the device.</span></span> <span data-ttu-id="5396f-285">Wenn ein Benutzer das Gerät 13 Mal verwendet hat, würde er als ein eindeutiger Benutzer gezählt, derselbe wie ein Benutzer, der das Gerät nur ein einziges Mal verwendet hat.</span><span class="sxs-lookup"><span data-stu-id="5396f-285">If a user used the device 13 times he or she would count as one unique user, the same as a user who only used the device a single time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5396f-286"><strong>Verhältnis der Zeit für die Sprachumstellung</strong></span><span class="sxs-lookup"><span data-stu-id="5396f-286"><strong>Ratio of voice switch time</strong></span></span></p></td>
<td><p><span data-ttu-id="5396f-287">Ja</span><span class="sxs-lookup"><span data-stu-id="5396f-287">Yes</span></span></p></td>
<td><p><span data-ttu-id="5396f-288">Prozentsatz des Anrufs, der im Halbduplexmodus durchgeführt werden musste, um Echo zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="5396f-288">Percentage of the call that had to be conducted in half duplex mode in order to prevent echo.</span></span> <span data-ttu-id="5396f-289">Im Halbduplexmodus kann die Kommunikation gleichzeitig nur in eine Richtung erfolgen, ähnlich wie die Benutzer beim kommunizieren mit einem Walkie-Talkie abwechselnd wechseln.</span><span class="sxs-lookup"><span data-stu-id="5396f-289">In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5396f-290"><strong>Verhältnis des nicht funktionierenden Mikrofons</strong></span><span class="sxs-lookup"><span data-stu-id="5396f-290"><strong>Ratio of microphone not functioning</strong></span></span></p></td>
<td><p><span data-ttu-id="5396f-291">Ja</span><span class="sxs-lookup"><span data-stu-id="5396f-291">Yes</span></span></p></td>
<td><p><span data-ttu-id="5396f-292">Prozentsatz des Anrufs, bei dem das Aufnahmegerät nicht ordnungsgemäß funktioniert hat.</span><span class="sxs-lookup"><span data-stu-id="5396f-292">Percentage of the call in which the capture device was not functioning at an acceptable level.</span></span> <span data-ttu-id="5396f-293">Ein hoher Wert deutet darauf hin, dass Qualitätsprobleme beim Anruf hauptsächlich darauf zurückzuführen sind, dass das Aufnahmegerät nicht erwartungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="5396f-293">A high values suggests that quality issues with the call were primarily due to the capture device not working as expected.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5396f-294"><strong>Verhältnis des nicht funktionierenden Lautsprechers</strong></span><span class="sxs-lookup"><span data-stu-id="5396f-294"><strong>Ratio of speaker not functioning</strong></span></span></p></td>
<td><p><span data-ttu-id="5396f-295">Ja</span><span class="sxs-lookup"><span data-stu-id="5396f-295">Yes</span></span></p></td>
<td><p><span data-ttu-id="5396f-296">Prozentsatz des Anrufs, bei dem das Render-Gerät nicht ordnungsgemäß funktioniert hat.</span><span class="sxs-lookup"><span data-stu-id="5396f-296">Percentage of the call in which the render device was not functioning at an acceptable level.</span></span> <span data-ttu-id="5396f-297">Ein hoher Wert deutet darauf hin, dass Qualitätsprobleme beim Anruf hauptsächlich darauf zurückzuführen sind, dass das Render-Gerät nicht erwartungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="5396f-297">A high values suggests that quality issues with the call were primarily due to the render device not working as expected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5396f-298"><strong>Anrufe mit Sprachumschaltung (%)</strong></span><span class="sxs-lookup"><span data-stu-id="5396f-298"><strong>Calls with voice switch (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="5396f-299">Ja</span><span class="sxs-lookup"><span data-stu-id="5396f-299">Yes</span></span></p></td>
<td><p><span data-ttu-id="5396f-300">Prozentsatz der Gesamt Anrufe, die im Halbduplexmodus getätigt werden mussten.</span><span class="sxs-lookup"><span data-stu-id="5396f-300">Percentage of the total calls which had to be placed into half duplex mode.</span></span> <span data-ttu-id="5396f-301">Im Halbduplexmodus kann die Kommunikation gleichzeitig nur in eine Richtung erfolgen, ähnlich wie die Benutzer beim kommunizieren mit einem Walkie-Talkie abwechselnd wechseln.</span><span class="sxs-lookup"><span data-stu-id="5396f-301">In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5396f-302"><strong>Echo Mikrofon in (%)</strong></span><span class="sxs-lookup"><span data-stu-id="5396f-302"><strong>Echo microphone in (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="5396f-303">Ja</span><span class="sxs-lookup"><span data-stu-id="5396f-303">Yes</span></span></p></td>
<td><p><span data-ttu-id="5396f-304">Prozentsatz der Zeit, als Echo im Mikrofon Erfassungsdaten Strom erkannt wurde.</span><span class="sxs-lookup"><span data-stu-id="5396f-304">Percentage of time when echo was detected in the microphone capture stream.</span></span> <span data-ttu-id="5396f-305">Normalerweise sind die Werte für Headsets oder Mobiltelefone niedrig und für Lautsprecher Telefone oder eigenständige Lautsprecher höher.</span><span class="sxs-lookup"><span data-stu-id="5396f-305">Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers.</span></span> <span data-ttu-id="5396f-306">Bei Geräten, die die akustische Echounterdrückung auf dem Mainboard unterstützen, deuten hohe Werte auf Echo Lecks hin.</span><span class="sxs-lookup"><span data-stu-id="5396f-306">For devices that support on-board acoustic echo cancellation, high values indicate echo leak.</span></span> <span data-ttu-id="5396f-307">Für andere Geräte sollte diese Metrik nicht verwendet werden, um die Gerätequalität auszuwerten.</span><span class="sxs-lookup"><span data-stu-id="5396f-307">For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5396f-308"><strong>Echo senden (%)</strong></span><span class="sxs-lookup"><span data-stu-id="5396f-308"><strong>Echo send (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="5396f-309">Ja</span><span class="sxs-lookup"><span data-stu-id="5396f-309">Yes</span></span></p></td>
<td><p><span data-ttu-id="5396f-310">Prozentsatz des Echos, das an andere Benutzer übermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="5396f-310">Percentage of echo transmitted to other users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5396f-311"><strong>Anrufe mit Echo (%)</strong></span><span class="sxs-lookup"><span data-stu-id="5396f-311"><strong>Calls with echo (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="5396f-312">Ja</span><span class="sxs-lookup"><span data-stu-id="5396f-312">Yes</span></span></p></td>
<td><p><span data-ttu-id="5396f-313">Prozentsatz der Gesamt Anrufe, bei denen Echo den zulässigen Wert überschreitet.</span><span class="sxs-lookup"><span data-stu-id="5396f-313">Percentage of the total calls that had echo exceeding the acceptable level.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

