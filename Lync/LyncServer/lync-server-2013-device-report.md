---
title: 'Lync Server 2013: gerätebericht'
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
ms.openlocfilehash: 93e750d66f3c18ee0960237ab5ffdfb37784f157
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197988"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="device-report-in-lync-server-2013"></a><span data-ttu-id="c6307-102">Gerätebericht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6307-102">Device Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6307-103">_**Letztes Änderungsstand des Themas:** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="c6307-103">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="c6307-104">Der gerätebericht kann besser mit dem Titel Mikrofon und Lautsprecher gemeldet werden. Das liegt daran, dass der gerätebericht anrufbezogene Metriken (wie Prozentsatz für schlechte Anrufe, Echos und Zeit für den Sprachwechsel) abruft, die von den Mikrofonen und Lautsprechern gruppiert werden, die im Anruf verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c6307-104">The Device Report might be better titled the Microphone and Speakers Report; that's because the Device Report retrieves call-related metrics (such as poor call percentage, echo, and voice switch time) grouped by the microphones and speakers used in the call.</span></span> <span data-ttu-id="c6307-105">Wenn Sie an IP-Telefonen interessiert sind (auch allgemein als "Geräte" bezeichnet), verwenden Sie stattdessen den Bericht über den [IP-Telefon bestand in lync Server 2013](lync-server-2013-ip-phone-inventory-report.md) .</span><span class="sxs-lookup"><span data-stu-id="c6307-105">If you are interested in IP phones (also commonly referred to as "devices"), use the [IP Phone Inventory Report in Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md) instead.</span></span>

<span data-ttu-id="c6307-106">Der gerätebericht ist für Administratoren äußerst nützlich, wenn Sie feststellen, ob ein bestimmter Gerätetyp hohe Mengen schlechter Qualität als andere Anrufe erfährt.</span><span class="sxs-lookup"><span data-stu-id="c6307-106">The Device Report is extremely useful for administrators in determining if a specific type of device is experiencing high volumes of poor quality calls than others.</span></span> <span data-ttu-id="c6307-107">Dies kann wiederum alle Entscheidungen beeinflussen, die Sie treffen müssen, wenn es an der Zeit ist, neue Geräte zu kaufen oder vorhandene Geräte zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="c6307-107">In turn, this could influence any decisions you must make when it comes time to buy new devices or to replace existing devices.</span></span>

<span data-ttu-id="c6307-108">Die im gerätebericht angezeigten Informationen basieren standardmäßig auch auf dem Mikrofon (dem Aufnahmegerät) und dem Lautsprecher/Headset (dem Render-Gerät), das im Anruf verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c6307-108">By default, the information displayed in the Device Report is also based on the microphone (the capture device) and speakers/headset (the render device) used in the call.</span></span> <span data-ttu-id="c6307-109">Nehmen wir beispielsweise an, Sie haben mehrere Benutzer, die das folgende Aufnahmegerät und das folgende Render-Gerät verwenden: Standardmäßig basieren die im gerätebericht angezeigten Informationen auch auf dem Mikrofon (dem Aufnahmegerät) und dem Lautsprecher/Headset (dem Render-Gerät), das im Anruf verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c6307-109">For example, suppose you have several users who use the following capture device and the following render device: By default, the information displayed in the Device Report is also based on the microphone (the capture device) and speakers/headset (the render device) used in the call.</span></span> <span data-ttu-id="c6307-110">Nehmen wir beispielsweise an, Sie haben mehrere Benutzer, die das folgende Capture-Gerät und das folgende Render-Gerät verwenden:</span><span class="sxs-lookup"><span data-stu-id="c6307-110">For example, suppose you have several users who use the following capture device and the following render device:</span></span>

  - <span data-ttu-id="c6307-111">Capture Device--Mikrofon (Soundmax Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="c6307-111">Capture device -- Microphone (SoundMAX Integrated Digital HD Audio)</span></span>

  - <span data-ttu-id="c6307-112">Render-Gerät--Headset-Ohrhörer (Microsoft LifeChat LX-3000)</span><span class="sxs-lookup"><span data-stu-id="c6307-112">Render device -- Headset Earphone (Microsoft LifeChat LX-3000)</span></span>

<span data-ttu-id="c6307-113">Wenn diese Benutzer insgesamt 254 Anrufe getätigt haben, sehen Sie einen Eintrag wie den folgenden im Bericht:</span><span class="sxs-lookup"><span data-stu-id="c6307-113">If those users made a total of 254 calls you'll see an entry like this in the report:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c6307-114">Aufnahmegerät</span><span class="sxs-lookup"><span data-stu-id="c6307-114">Capture device</span></span></th>
<th><span data-ttu-id="c6307-115">Darstellungsgerät</span><span class="sxs-lookup"><span data-stu-id="c6307-115">Render device</span></span></th>
<th><span data-ttu-id="c6307-116">Anruflautstärke</span><span class="sxs-lookup"><span data-stu-id="c6307-116">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c6307-117">Mikrofon (Soundmax Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="c6307-117">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="c6307-118">Headset-Ohrhörer (Microsoft LifeChat LX-3000)</span><span class="sxs-lookup"><span data-stu-id="c6307-118">Headset Earphone (Microsoft LifeChat LX-3000)</span></span></p></td>
<td><p><span data-ttu-id="c6307-119">254</span><span class="sxs-lookup"><span data-stu-id="c6307-119">254</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c6307-120">Angenommen, Sie verfügen über eine Reihe von Benutzern, die dasselbe Aufnahmegerät verwenden, aber ein anderes Render-Gerät.</span><span class="sxs-lookup"><span data-stu-id="c6307-120">Now, suppose you have a number of users who use that same capture device but a different render device.</span></span> <span data-ttu-id="c6307-121">In diesem Fall haben Sie einen zweiten Zeile-Eintrag im Bericht, einen für diese eindeutige Kombination aus Capture Device und Render Device:</span><span class="sxs-lookup"><span data-stu-id="c6307-121">In that case, you'll have a second line entry in the report, one for that unique combination of capture device and render device:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c6307-122">Aufnahmegerät</span><span class="sxs-lookup"><span data-stu-id="c6307-122">Capture device</span></span></th>
<th><span data-ttu-id="c6307-123">Darstellungsgerät</span><span class="sxs-lookup"><span data-stu-id="c6307-123">Render device</span></span></th>
<th><span data-ttu-id="c6307-124">Anruflautstärke</span><span class="sxs-lookup"><span data-stu-id="c6307-124">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c6307-125">Mikrofon (Soundmax Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="c6307-125">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="c6307-126">Headset-Ohrhörer (Microsoft LifeChat LX-3000)</span><span class="sxs-lookup"><span data-stu-id="c6307-126">Headset Earphone (Microsoft LifeChat LX-3000)</span></span></p></td>
<td><p><span data-ttu-id="c6307-127">254</span><span class="sxs-lookup"><span data-stu-id="c6307-127">254</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6307-128">Mikrofon (Soundmax Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="c6307-128">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="c6307-129">Lautsprecher (Soundmax Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="c6307-129">Speakers (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="c6307-130">319</span><span class="sxs-lookup"><span data-stu-id="c6307-130">319</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c6307-131">Wenn Sie lieber kombinierte Gesamtsummen für ein bestimmtes Gerät (beispielsweise für das SoundMAX-Aufnahmegerät, unabhängig vom verwendeten Render-Gerät) anzeigen möchten, wählen Sie in der Dropdownliste Gerätetyp die entsprechende Option aus (entweder Capture-Gerät oder Render-Gerät).</span><span class="sxs-lookup"><span data-stu-id="c6307-131">If you would rather see combined totals for a given device (for example, for the SoundMAX capture device, regardless of the render device used), select the appropriate option from the Device type dropdown list (either Capture device or Render device).</span></span> <span data-ttu-id="c6307-132">Wenn Sie in diesem Beispiel Capture Device auswählen, erhalten Sie eine ähnliche Ausgabe wie die folgende:</span><span class="sxs-lookup"><span data-stu-id="c6307-132">If you select Capture device in this example, that will give you output similar to this:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c6307-133">Aufnahmegerät</span><span class="sxs-lookup"><span data-stu-id="c6307-133">Capture device</span></span></th>
<th><span data-ttu-id="c6307-134">Anruflautstärke</span><span class="sxs-lookup"><span data-stu-id="c6307-134">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c6307-135">Mikrofon (Soundmax Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="c6307-135">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="c6307-136">573</span><span class="sxs-lookup"><span data-stu-id="c6307-136">573</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="accessing-the-device-report"></a><span data-ttu-id="c6307-137">Zugreifen auf den gerätebericht</span><span class="sxs-lookup"><span data-stu-id="c6307-137">Accessing the Device Report</span></span>

<span data-ttu-id="c6307-138">Auf den gerätebericht wird normalerweise über die Startseite für Überwachungsberichte zugegriffen.</span><span class="sxs-lookup"><span data-stu-id="c6307-138">The Device Report is typically accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="c6307-139">Wenn Sie jedoch den [Anruf Detail Bericht in lync Server 2013](lync-server-2013-call-detail-report.md) anzeigen, können Sie durch Klicken auf eine der folgenden Metriken einen Drilldown zum gerätebericht für ein bestimmtes Gerät ausführen:</span><span class="sxs-lookup"><span data-stu-id="c6307-139">However, if you are viewing the [Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) you can drill down to the Device Report for a specific device by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="c6307-140">Capture-Gerät</span><span class="sxs-lookup"><span data-stu-id="c6307-140">Capture Device</span></span>

  - <span data-ttu-id="c6307-141">Render-Gerät</span><span class="sxs-lookup"><span data-stu-id="c6307-141">Render Device</span></span>

<span data-ttu-id="c6307-142">Im gerätebericht können Sie einen Drilldown zum [Anruflistenbericht in lync Server 2013](lync-server-2013-call-list-report.md) durchführen, indem Sie auf eine der folgenden Metriken klicken:</span><span class="sxs-lookup"><span data-stu-id="c6307-142">From the Device Report you can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="c6307-143">Anrufvolumen</span><span class="sxs-lookup"><span data-stu-id="c6307-143">Call volume</span></span>

  - <span data-ttu-id="c6307-144">Prozentsatz der Anrufe schlechter Qualität</span><span class="sxs-lookup"><span data-stu-id="c6307-144">Poor call percentage</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-device-report"></a><span data-ttu-id="c6307-145">Optimale Verwendung des Geräte Berichts</span><span class="sxs-lookup"><span data-stu-id="c6307-145">Making the Best Use of the Device Report</span></span>

<span data-ttu-id="c6307-146">Wenn es um Gerätenamen geht, ist der gerätebericht äußerst detailliert; nehmen wir beispielsweise an, Sie haben die folgenden Capture-Geräte:</span><span class="sxs-lookup"><span data-stu-id="c6307-146">When it comes to device names, the Device Report is extremely detailed; for example, suppose you have the following capture devices:</span></span>

  - <span data-ttu-id="c6307-147">Aastra 3002-Mikrofon (2-Aastra 3002)</span><span class="sxs-lookup"><span data-stu-id="c6307-147">Aastra 3002 Microphone (2- Aastra 3002)</span></span>

  - <span data-ttu-id="c6307-148">Aastra 3002-Mikrofon (3-Aastra 3002)</span><span class="sxs-lookup"><span data-stu-id="c6307-148">Aastra 3002 Microphone (3- Aastra 3002)</span></span>

  - <span data-ttu-id="c6307-149">Aastra 3002-Mikrofon (Aastra 3002)</span><span class="sxs-lookup"><span data-stu-id="c6307-149">Aastra 3002 Microphone (Aastra 3002)</span></span>

  - <span data-ttu-id="c6307-150">Aastra 6725ip</span><span class="sxs-lookup"><span data-stu-id="c6307-150">Aastra 6725ip</span></span>

  - <span data-ttu-id="c6307-151">Aastra 6725ip-Mikrofon (10-Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="c6307-151">Aastra 6725ip Microphone (10- Aastra 6725ip)</span></span>

  - <span data-ttu-id="c6307-152">Aastra 6725ip-Mikrofon (10-Aastra 6725ip)-v0</span><span class="sxs-lookup"><span data-stu-id="c6307-152">Aastra 6725ip Microphone (10- Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="c6307-153">Aastra 6725ip-Mikrofon (2-Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="c6307-153">Aastra 6725ip Microphone (2- Aastra 6725ip)</span></span>

  - <span data-ttu-id="c6307-154">Aastra 6725ip-Mikrofon (3-Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="c6307-154">Aastra 6725ip Microphone (3- Aastra 6725ip)</span></span>

  - <span data-ttu-id="c6307-155">Aastra 6725ip-Mikrofon (4-Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="c6307-155">Aastra 6725ip Microphone (4- Aastra 6725ip)</span></span>

  - <span data-ttu-id="c6307-156">Aastra 6725ip-Mikrofon (5-Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="c6307-156">Aastra 6725ip Microphone (5- Aastra 6725ip)</span></span>

  - <span data-ttu-id="c6307-157">Aastra 6725ip-Mikrofon (6-Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="c6307-157">Aastra 6725ip Microphone (6- Aastra 6725ip)</span></span>

  - <span data-ttu-id="c6307-158">Aastra 6725ip-Mikrofon (7-Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="c6307-158">Aastra 6725ip Microphone (7- Aastra 6725ip)</span></span>

  - <span data-ttu-id="c6307-159">Aastra 6725ip-Mikrofon (9-Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="c6307-159">Aastra 6725ip Microphone (9- Aastra 6725ip)</span></span>

  - <span data-ttu-id="c6307-160">Aastra 6725ip-Mikrofon (9-Aastra 6725ip)-v0</span><span class="sxs-lookup"><span data-stu-id="c6307-160">Aastra 6725ip Microphone (9- Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="c6307-161">Aastra 6725ip-Mikrofon (Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="c6307-161">Aastra 6725ip Microphone (Aastra 6725ip)</span></span>

  - <span data-ttu-id="c6307-162">Aastra 6725ip-Mikrofon (Aastra 6725ip)-v0</span><span class="sxs-lookup"><span data-stu-id="c6307-162">Aastra 6725ip Microphone (Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="c6307-163">Aastra 6725ip-Mikrofon (USB-Audiogerät)</span><span class="sxs-lookup"><span data-stu-id="c6307-163">Aastra 6725ip Microphone (USB Audio Device)</span></span>

  - <span data-ttu-id="c6307-164">Aastra 6725ip-Mikrofon (USB-Audiogerät)-v0</span><span class="sxs-lookup"><span data-stu-id="c6307-164">Aastra 6725ip Microphone (USB Audio Device)-V0</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c6307-165">Beachten Sie, dass Capture-Gerätenamen möglicherweise nicht identisch sind, wenn Sie lokalisierte Versionen von lync Server 2013 durchführen.</span><span class="sxs-lookup"><span data-stu-id="c6307-165">Keep in mind that capture device names might not be the same if you are running localized versions of Lync Server 2013.</span></span> <span data-ttu-id="c6307-166">Ein Gerät namens Aastra 6725ip Mikrofon (Aastra 6725ip)-v0 in US-Englisch könnte in Französisch oder Spanisch einen anderen Namen haben.</span><span class="sxs-lookup"><span data-stu-id="c6307-166">A device named Aastra 6725ip Microphone (Aastra 6725ip)-V0 in US English could have a different name in French or Spanish.</span></span>



</div>

<span data-ttu-id="c6307-167">Oft werden Sie diese Detailgenauigkeit wünschen. zu anderen Zeiten sind Sie jedoch möglicherweise nur daran interessiert, wie viele Anrufe ein Aastra-Mikrofon unabhängig von der Modellnummer verwenden.</span><span class="sxs-lookup"><span data-stu-id="c6307-167">Often times you'll want that level of detail; at other times, however, you might only be interested in how many calls use any Aastra microphone, regardless of model number.</span></span> <span data-ttu-id="c6307-168">Eine Möglichkeit zum Abrufen von Informationen wie das ist das Exportieren der Geräte Berichtsdaten in Microsoft Excel und das anschließende Speichern dieser Daten in einer Datei mit Komma getrennten Werten (beispielsweise C\\:\\Data\_Devices Report. CSV).</span><span class="sxs-lookup"><span data-stu-id="c6307-168">One way to get information like that is to export the Device Report data to Microsoft Excel and then save that data to a comma-separated values file (for example, C:\\Data\\Devices\_Report.csv).</span></span> <span data-ttu-id="c6307-169">Anschließend können Sie eine Reihe von Befehlen wie diese verwenden, um die zu importieren. CSV-Datei in Windows PowerShell und melden Sie die Gesamtzahl der Anrufe, die mit einem Aastra Capture-Gerät ausgeführt wurden, zurück:</span><span class="sxs-lookup"><span data-stu-id="c6307-169">You can then use a set of commands similar to these to import the .CSV file into Windows PowerShell and report back the total number of calls made using an Aastra capture device:</span></span>

    $devices = Import-Csv "C:\Data\Device_Report.csv
    $sum = $devices | Where-Object {$_."Capture device" -match "Aastra"}
    $sum | foreach-object {[Int]$x = [Int]$x + [Int]$_."call volume"}
    $x

<span data-ttu-id="c6307-170">Dadurch wird ein einzelner Wert zurückgegeben, der die Gesamtzahl der mit einem Aastra Capture-Gerät getätigten Anrufe darstellt.</span><span class="sxs-lookup"><span data-stu-id="c6307-170">That will return a single value representing the total number of calls made using an Aastra capture device.</span></span> <span data-ttu-id="c6307-171">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c6307-171">For example:</span></span>

    384

</div>

<div>

## <a name="filters"></a><span data-ttu-id="c6307-172">Filter</span><span class="sxs-lookup"><span data-stu-id="c6307-172">Filters</span></span>

<span data-ttu-id="c6307-173">Mithilfe von Filtern können Sie eine gezieltere Datenauswahl zurückgeben oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen.</span><span class="sxs-lookup"><span data-stu-id="c6307-173">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="c6307-174">Beispielsweise können Sie mit dem gerätebericht nach solchen Dingen wie dem Anruftyp (also dem Anruf eines Client Anrufs), einer Telefonkonferenz oder einem PSTN-Anruf (Public Switched Telephone Network) filtern.</span><span class="sxs-lookup"><span data-stu-id="c6307-174">For example, the Device Report enables you to filter on such things as call type (that is, was the call a client call), a conference call, or a public switched telephone network (PSTN) call.</span></span> <span data-ttu-id="c6307-175">Sie können außerdem festlegen, wie Daten gruppiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c6307-175">You can also choose how data should be grouped.</span></span> <span data-ttu-id="c6307-176">In diesem Fall werden Geräte nach Stunde, Tag, Woche oder Monat gruppiert.</span><span class="sxs-lookup"><span data-stu-id="c6307-176">In this case, devices are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="c6307-177">In der folgenden Tabelle sind die Filter aufgeführt, die Sie mit dem gerätebericht verwenden können.</span><span class="sxs-lookup"><span data-stu-id="c6307-177">The following table lists the filters that you can use with the Device Report.</span></span>

### <a name="device-report-filters"></a><span data-ttu-id="c6307-178">Geräte Berichtsfilter</span><span class="sxs-lookup"><span data-stu-id="c6307-178">Device Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c6307-179">Name</span><span class="sxs-lookup"><span data-stu-id="c6307-179">Name</span></span></th>
<th><span data-ttu-id="c6307-180">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c6307-180">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c6307-181"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="c6307-181"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="c6307-p111">Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="c6307-p111">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="c6307-184">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="c6307-184">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="c6307-p112">Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="c6307-p112">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="c6307-187">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="c6307-187">7/7/2012</span></span></p>
<p><span data-ttu-id="c6307-188">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="c6307-188">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="c6307-189">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="c6307-189">7/3/2012</span></span></p>
<p><span data-ttu-id="c6307-190">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="c6307-190">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6307-191"><strong>Ziel</strong></span><span class="sxs-lookup"><span data-stu-id="c6307-191"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="c6307-p113">Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="c6307-p113">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="c6307-194">07.07.2012 13:00</span><span class="sxs-lookup"><span data-stu-id="c6307-194">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="c6307-p114">Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</span><span class="sxs-lookup"><span data-stu-id="c6307-p114">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="c6307-197">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="c6307-197">7/7/2012</span></span></p>
<p><span data-ttu-id="c6307-198">Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</span><span class="sxs-lookup"><span data-stu-id="c6307-198">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="c6307-199">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="c6307-199">7/3/2012</span></span></p>
<p><span data-ttu-id="c6307-200">Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</span><span class="sxs-lookup"><span data-stu-id="c6307-200">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6307-201"><strong>Ursache für VoIP-Switch</strong></span><span class="sxs-lookup"><span data-stu-id="c6307-201"><strong>Voice switch cause</strong></span></span></p></td>
<td><p><span data-ttu-id="c6307-202">Grund, warum ein Anruf in den Halbduplexmodus versetzt werden musste, um Echo zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="c6307-202">Reason why a call had to be placed into half duplex mode in order to prevent echo.</span></span> <span data-ttu-id="c6307-203">Im Halbduplexmodus kann die Kommunikation gleichzeitig nur in eine Richtung erfolgen, ähnlich wie die Benutzer beim kommunizieren mit einem Walkie-Talkie abwechselnd wechseln.</span><span class="sxs-lookup"><span data-stu-id="c6307-203">In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie.</span></span> <span data-ttu-id="c6307-204">Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="c6307-204">Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c6307-205">Alle</span><span class="sxs-lookup"><span data-stu-id="c6307-205">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c6307-206">Keine</span><span class="sxs-lookup"><span data-stu-id="c6307-206">None</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c6307-207">Falscher Zeitstempel</span><span class="sxs-lookup"><span data-stu-id="c6307-207">Bad timestamp</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c6307-208">Echo</span><span class="sxs-lookup"><span data-stu-id="c6307-208">Echo</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c6307-209">DNLP (dynamischer nichtlinearer Prozessor)</span><span class="sxs-lookup"><span data-stu-id="c6307-209">DNLP (dynamic nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c6307-210">Geringe Komplexität</span><span class="sxs-lookup"><span data-stu-id="c6307-210">Low complexity</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c6307-211">Ungültiger Gerätestatus</span><span class="sxs-lookup"><span data-stu-id="c6307-211">Bad device state</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c6307-212">Post-AEC-Echo (akustische Echounterdrückung)</span><span class="sxs-lookup"><span data-stu-id="c6307-212">Post-AEC echo (acoustic echo cancellation)</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6307-213"><strong>Echo Ursache</strong></span><span class="sxs-lookup"><span data-stu-id="c6307-213"><strong>Echo cause</strong></span></span></p></td>
<td><p><span data-ttu-id="c6307-214">Grund, warum Echo oberhalb der akzeptierten Ebene in einem Anruf erkannt wurde.</span><span class="sxs-lookup"><span data-stu-id="c6307-214">Reason why echo above the accepted level was detected in a call.</span></span> <span data-ttu-id="c6307-215">(In der Telekommunikation ist ECHO eine Reflexion des Klangs, das gleiche Phänomen, das Sie hören, wenn Sie auf den Grund eines Brunnens schreien.) Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="c6307-215">(In telecommunications, echo is a reflection of sound, the same phenomenon you will hear if you yell down to the bottom of a well.) Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c6307-216">Alle</span><span class="sxs-lookup"><span data-stu-id="c6307-216">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c6307-217">Keine</span><span class="sxs-lookup"><span data-stu-id="c6307-217">None</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c6307-218">Falscher Zeitstempel</span><span class="sxs-lookup"><span data-stu-id="c6307-218">Bad timestamp</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c6307-219">Post-AEC-Echo (akustische Echounterdrückung)</span><span class="sxs-lookup"><span data-stu-id="c6307-219">Post-AEC echo (acoustic echo cancellation)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c6307-220">ANLP (adaptiver nichtlinearer Prozessor)</span><span class="sxs-lookup"><span data-stu-id="c6307-220">ANLP (adaptive nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c6307-221">DNLP (dynamischer nichtlinearer Prozessor)</span><span class="sxs-lookup"><span data-stu-id="c6307-221">DNLP (dynamic nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c6307-222">Mikrofon Clipping</span><span class="sxs-lookup"><span data-stu-id="c6307-222">Microphone clipping</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6307-223"><strong>Anruftyp</strong></span><span class="sxs-lookup"><span data-stu-id="c6307-223"><strong>Call type</strong></span></span></p></td>
<td><p><span data-ttu-id="c6307-224">Gibt den Typ des Anrufs an, der ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="c6307-224">Indicates the type of call that was made.</span></span> <span data-ttu-id="c6307-225">Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="c6307-225">Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c6307-226">Alle</span><span class="sxs-lookup"><span data-stu-id="c6307-226">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c6307-227">Client Anruf</span><span class="sxs-lookup"><span data-stu-id="c6307-227">Client call</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c6307-228">PSTN-Anruf</span><span class="sxs-lookup"><span data-stu-id="c6307-228">PSTN call</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c6307-229">Konferenzanruf</span><span class="sxs-lookup"><span data-stu-id="c6307-229">Conference call</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6307-230"><strong>Zugriffstyp</strong></span><span class="sxs-lookup"><span data-stu-id="c6307-230"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="c6307-p118">Gibt an, ob der Client am internen oder am externen Netzwerk angemeldet wurde, als der Anruf getätigt wurde. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="c6307-p118">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c6307-233">Alle</span><span class="sxs-lookup"><span data-stu-id="c6307-233">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c6307-234">Intern</span><span class="sxs-lookup"><span data-stu-id="c6307-234">Internal</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c6307-235">Extern</span><span class="sxs-lookup"><span data-stu-id="c6307-235">External</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6307-236"><strong>Netzwerktyp</strong></span><span class="sxs-lookup"><span data-stu-id="c6307-236"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="c6307-p119">Gibt den Typ des Netzwerks an, mit dem der Client verbunden wurde, als der Anruf erfolgte. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="c6307-p119">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c6307-239">Alle</span><span class="sxs-lookup"><span data-stu-id="c6307-239">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c6307-240">Wired</span><span class="sxs-lookup"><span data-stu-id="c6307-240">Wired</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c6307-241">Drahtlos</span><span class="sxs-lookup"><span data-stu-id="c6307-241">Wireless</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6307-242"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="c6307-242"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="c6307-p120">Gibt an, ob ein externer Client eine VPN-Verbindung (Virtual Private Network) verwendete, als der Anruf getätigt wurde. Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="c6307-p120">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c6307-245">Alle</span><span class="sxs-lookup"><span data-stu-id="c6307-245">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c6307-246">VPN</span><span class="sxs-lookup"><span data-stu-id="c6307-246">VPN</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c6307-247">Nicht-VPN</span><span class="sxs-lookup"><span data-stu-id="c6307-247">Non-VPN</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6307-248"><strong>Gerätetyp</strong></span><span class="sxs-lookup"><span data-stu-id="c6307-248"><strong>Device type</strong></span></span></p></td>
<td><p><span data-ttu-id="c6307-249">Gibt den Gerätetyp an.</span><span class="sxs-lookup"><span data-stu-id="c6307-249">Indicates the type of device.</span></span> <span data-ttu-id="c6307-250">Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="c6307-250">Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c6307-251">Aufnahmegerät</span><span class="sxs-lookup"><span data-stu-id="c6307-251">Capture device</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c6307-252">Darstellungsgerät</span><span class="sxs-lookup"><span data-stu-id="c6307-252">Render device</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="c6307-253">Paar für Capture/Render-Geräte</span><span class="sxs-lookup"><span data-stu-id="c6307-253">Capture/Render device pair</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6307-254"><strong>Gerätename</strong></span><span class="sxs-lookup"><span data-stu-id="c6307-254"><strong>Device name</strong></span></span></p></td>
<td><p><span data-ttu-id="c6307-255">Name des Capture-oder Render-Geräts.</span><span class="sxs-lookup"><span data-stu-id="c6307-255">Name of the capture or render device.</span></span> <span data-ttu-id="c6307-256">Sie können den vollständigen Gerätenamen oder einen Teil des Gerätenamens eingeben.</span><span class="sxs-lookup"><span data-stu-id="c6307-256">You can enter the complete device name or any portion of the device name.</span></span> <span data-ttu-id="c6307-257">Um beispielsweise das Gerätemikrofon zu finden (Microsoft LifeCam VX-1000.), können Sie den vollständigen Gerätenamen wie folgt eingeben:</span><span class="sxs-lookup"><span data-stu-id="c6307-257">For example, to find the device Microphone (Microsoft LifeCam VX-1000.), you can enter the complete device name as follows:</span></span></p>
<p><span data-ttu-id="c6307-258">Mikrofon (Microsoft LifeCam VX-1000.)</span><span class="sxs-lookup"><span data-stu-id="c6307-258">Microphone (Microsoft LifeCam VX-1000.)</span></span></p>
<p><span data-ttu-id="c6307-259">Sie können auch nur einen Teil des Namens eingeben.</span><span class="sxs-lookup"><span data-stu-id="c6307-259">Or, you can enter just a portion of the name.</span></span> <span data-ttu-id="c6307-260">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c6307-260">For example:</span></span></p>
<p><span data-ttu-id="c6307-261">LifeCam</span><span class="sxs-lookup"><span data-stu-id="c6307-261">LifeCam</span></span></p>
<p><span data-ttu-id="c6307-262">Beachten Sie, dass der obige Filter jedes Gerät zurückgibt, &quot;das&quot; die Zeichenfolge LifeCam Anywhere in seinem Namen enthält.</span><span class="sxs-lookup"><span data-stu-id="c6307-262">Note that the preceding filter returns any device that contains the string &quot;LifeCam&quot; anywhere in its name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="c6307-263">Metriken</span><span class="sxs-lookup"><span data-stu-id="c6307-263">Metrics</span></span>

<span data-ttu-id="c6307-264">In der folgenden Tabelle sind die Informationen aufgeführt, die im gerätebericht angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c6307-264">The following table lists the information provided in the Device Report.</span></span>

### <a name="device-report-metrics"></a><span data-ttu-id="c6307-265">Metriken für den gerätebericht</span><span class="sxs-lookup"><span data-stu-id="c6307-265">Device Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c6307-266">Name</span><span class="sxs-lookup"><span data-stu-id="c6307-266">Name</span></span></th>
<th><span data-ttu-id="c6307-267">Kann nach dieser Metrik sortiert werden?</span><span class="sxs-lookup"><span data-stu-id="c6307-267">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c6307-268">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c6307-268">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c6307-269"><strong>Aufnahmegerät</strong></span><span class="sxs-lookup"><span data-stu-id="c6307-269"><strong>Capture device</strong></span></span></p></td>
<td><p><span data-ttu-id="c6307-270">Ja</span><span class="sxs-lookup"><span data-stu-id="c6307-270">Yes</span></span></p></td>
<td><p><span data-ttu-id="c6307-271">Gerät (zum Beispiel ein Mikrofon oder eine Webcam), das für die Übertragung von Audio verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c6307-271">Device (for example, a microphone or webcam) used for transmitting audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6307-272"><strong>Darstellungsgerät</strong></span><span class="sxs-lookup"><span data-stu-id="c6307-272"><strong>Render device</strong></span></span></p></td>
<td><p><span data-ttu-id="c6307-273">Ja</span><span class="sxs-lookup"><span data-stu-id="c6307-273">Yes</span></span></p></td>
<td><p><span data-ttu-id="c6307-274">Gerät (zum Beispiel ein Headset oder Lautsprecher), das zum Empfangen von Audio verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c6307-274">Device (for example, a headset or speakers) used for receiving audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6307-275"><strong>Anruflautstärke</strong></span><span class="sxs-lookup"><span data-stu-id="c6307-275"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="c6307-276">Ja</span><span class="sxs-lookup"><span data-stu-id="c6307-276">Yes</span></span></p></td>
<td><p><span data-ttu-id="c6307-277">Die Gesamtzahl der getätigten Anrufe.</span><span class="sxs-lookup"><span data-stu-id="c6307-277">Total number of calls placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6307-278"><strong>Prozentsatz der Anrufe schlechter Qualität</strong></span><span class="sxs-lookup"><span data-stu-id="c6307-278"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="c6307-279">Ja</span><span class="sxs-lookup"><span data-stu-id="c6307-279">Yes</span></span></p></td>
<td><p><span data-ttu-id="c6307-280">Prozentsatz der Anrufe, die als &quot;unzureichend klassifiziert wurden. &quot; Bei einem schlechten Anruf handelt es sich um einen Anruf, bei dem mindestens eine der gemessenen Metriken den zulässigen Wert überschritten hat (beispielsweise ein Anruf, bei dem übermäßiger Jitter aufgetreten ist).</span><span class="sxs-lookup"><span data-stu-id="c6307-280">Percentage of calls that were classified as &quot;poor.&quot; A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6307-281"><strong>Eindeutige Benutzer</strong></span><span class="sxs-lookup"><span data-stu-id="c6307-281"><strong>Unique users</strong></span></span></p></td>
<td><p><span data-ttu-id="c6307-282">Ja</span><span class="sxs-lookup"><span data-stu-id="c6307-282">Yes</span></span></p></td>
<td><p><span data-ttu-id="c6307-283">Eindeutige Benutzer, die das Gerät verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="c6307-283">Unique users who used the device.</span></span> <span data-ttu-id="c6307-284">Wenn ein Benutzer das Gerät 13 Mal verwendet hat, würde er als ein eindeutiger Benutzer gezählt, derselbe wie ein Benutzer, der das Gerät nur ein einziges Mal verwendet hat.</span><span class="sxs-lookup"><span data-stu-id="c6307-284">If a user used the device 13 times he or she would count as one unique user, the same as a user who only used the device a single time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6307-285"><strong>Verhältnis der Zeit für die Sprachumstellung</strong></span><span class="sxs-lookup"><span data-stu-id="c6307-285"><strong>Ratio of voice switch time</strong></span></span></p></td>
<td><p><span data-ttu-id="c6307-286">Ja</span><span class="sxs-lookup"><span data-stu-id="c6307-286">Yes</span></span></p></td>
<td><p><span data-ttu-id="c6307-287">Prozentsatz des Anrufs, der im Halbduplexmodus durchgeführt werden musste, um Echo zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="c6307-287">Percentage of the call that had to be conducted in half duplex mode in order to prevent echo.</span></span> <span data-ttu-id="c6307-288">Im Halbduplexmodus kann die Kommunikation gleichzeitig nur in eine Richtung erfolgen, ähnlich wie die Benutzer beim kommunizieren mit einem Walkie-Talkie abwechselnd wechseln.</span><span class="sxs-lookup"><span data-stu-id="c6307-288">In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6307-289"><strong>Verhältnis des nicht funktionierenden Mikrofons</strong></span><span class="sxs-lookup"><span data-stu-id="c6307-289"><strong>Ratio of microphone not functioning</strong></span></span></p></td>
<td><p><span data-ttu-id="c6307-290">Ja</span><span class="sxs-lookup"><span data-stu-id="c6307-290">Yes</span></span></p></td>
<td><p><span data-ttu-id="c6307-291">Prozentsatz des Anrufs, bei dem das Aufnahmegerät nicht ordnungsgemäß funktioniert hat.</span><span class="sxs-lookup"><span data-stu-id="c6307-291">Percentage of the call in which the capture device was not functioning at an acceptable level.</span></span> <span data-ttu-id="c6307-292">Ein hoher Wert deutet darauf hin, dass Qualitätsprobleme beim Anruf hauptsächlich darauf zurückzuführen sind, dass das Aufnahmegerät nicht erwartungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="c6307-292">A high values suggests that quality issues with the call were primarily due to the capture device not working as expected.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6307-293"><strong>Verhältnis des nicht funktionierenden Lautsprechers</strong></span><span class="sxs-lookup"><span data-stu-id="c6307-293"><strong>Ratio of speaker not functioning</strong></span></span></p></td>
<td><p><span data-ttu-id="c6307-294">Ja</span><span class="sxs-lookup"><span data-stu-id="c6307-294">Yes</span></span></p></td>
<td><p><span data-ttu-id="c6307-295">Prozentsatz des Anrufs, bei dem das Render-Gerät nicht ordnungsgemäß funktioniert hat.</span><span class="sxs-lookup"><span data-stu-id="c6307-295">Percentage of the call in which the render device was not functioning at an acceptable level.</span></span> <span data-ttu-id="c6307-296">Ein hoher Wert deutet darauf hin, dass Qualitätsprobleme beim Anruf hauptsächlich darauf zurückzuführen sind, dass das Render-Gerät nicht erwartungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="c6307-296">A high values suggests that quality issues with the call were primarily due to the render device not working as expected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6307-297"><strong>Anrufe mit Sprachumschaltung (%)</strong></span><span class="sxs-lookup"><span data-stu-id="c6307-297"><strong>Calls with voice switch (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="c6307-298">Ja</span><span class="sxs-lookup"><span data-stu-id="c6307-298">Yes</span></span></p></td>
<td><p><span data-ttu-id="c6307-299">Prozentsatz der Gesamt Anrufe, die im Halbduplexmodus getätigt werden mussten.</span><span class="sxs-lookup"><span data-stu-id="c6307-299">Percentage of the total calls which had to be placed into half duplex mode.</span></span> <span data-ttu-id="c6307-300">Im Halbduplexmodus kann die Kommunikation gleichzeitig nur in eine Richtung erfolgen, ähnlich wie die Benutzer beim kommunizieren mit einem Walkie-Talkie abwechselnd wechseln.</span><span class="sxs-lookup"><span data-stu-id="c6307-300">In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6307-301"><strong>Echo Mikrofon in (%)</strong></span><span class="sxs-lookup"><span data-stu-id="c6307-301"><strong>Echo microphone in (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="c6307-302">Ja</span><span class="sxs-lookup"><span data-stu-id="c6307-302">Yes</span></span></p></td>
<td><p><span data-ttu-id="c6307-303">Prozentsatz der Zeit, als Echo im Mikrofon Erfassungsdaten Strom erkannt wurde.</span><span class="sxs-lookup"><span data-stu-id="c6307-303">Percentage of time when echo was detected in the microphone capture stream.</span></span> <span data-ttu-id="c6307-304">Normalerweise sind die Werte für Headsets oder Mobiltelefone niedrig und für Lautsprecher Telefone oder eigenständige Lautsprecher höher.</span><span class="sxs-lookup"><span data-stu-id="c6307-304">Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers.</span></span> <span data-ttu-id="c6307-305">Bei Geräten, die die akustische Echounterdrückung auf dem Mainboard unterstützen, deuten hohe Werte auf Echo Lecks hin.</span><span class="sxs-lookup"><span data-stu-id="c6307-305">For devices that support on-board acoustic echo cancellation, high values indicate echo leak.</span></span> <span data-ttu-id="c6307-306">Für andere Geräte sollte diese Metrik nicht verwendet werden, um die Gerätequalität auszuwerten.</span><span class="sxs-lookup"><span data-stu-id="c6307-306">For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6307-307"><strong>Echo senden (%)</strong></span><span class="sxs-lookup"><span data-stu-id="c6307-307"><strong>Echo send (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="c6307-308">Ja</span><span class="sxs-lookup"><span data-stu-id="c6307-308">Yes</span></span></p></td>
<td><p><span data-ttu-id="c6307-309">Prozentsatz des Echos, das an andere Benutzer übermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="c6307-309">Percentage of echo transmitted to other users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6307-310"><strong>Anrufe mit Echo (%)</strong></span><span class="sxs-lookup"><span data-stu-id="c6307-310"><strong>Calls with echo (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="c6307-311">Ja</span><span class="sxs-lookup"><span data-stu-id="c6307-311">Yes</span></span></p></td>
<td><p><span data-ttu-id="c6307-312">Prozentsatz der Gesamt Anrufe, bei denen Echo den zulässigen Wert überschreitet.</span><span class="sxs-lookup"><span data-stu-id="c6307-312">Percentage of the total calls that had echo exceeding the acceptable level.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

