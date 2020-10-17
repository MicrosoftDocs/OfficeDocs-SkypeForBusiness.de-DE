---
title: 'Lync Server 2013: Video Anforderungen für lync-Clients'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync client video requirements
ms:assetid: 8f68f4c2-3194-487c-bd2f-fbe71ba8ad70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688132(v=OCS.15)
ms:contentKeyID: 49733731
ms.date: 01/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 883242824a6dfc45dbae923736a7a88bc1784d62
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506062"
---
# <a name="lync-client-video-requirements-for-lync-server-2013"></a><span data-ttu-id="ff47c-102">Video Anforderungen für lync-Clients für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff47c-102">Lync client video requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff47c-103">_**Letztes Änderungsstand des Themas:** 2016-01-29_</span><span class="sxs-lookup"><span data-stu-id="ff47c-103">_**Topic Last Modified:** 2016-01-29_</span></span>

<span data-ttu-id="ff47c-104">In diesem Abschnitt wird die Videohardware Unterstützung für lync 2013 Videoanrufe beschrieben, und es wird beschrieben, wie Sie die erwartete Videoqualität für verschiedene Computer-, Tablet-und Mobile Gerätekonfigurationen bestimmen.</span><span class="sxs-lookup"><span data-stu-id="ff47c-104">This section describes video hardware support for Lync 2013 video calls and describes how to determine the expected video quality for various computer, tablet, and mobile device configurations.</span></span>

<div>

## <a name="windows-desktop-and-tablet-video-requirements-and-capabilities"></a><span data-ttu-id="ff47c-105">Windows-Desktop-und Tablet-Video Anforderungen und-Funktionen</span><span class="sxs-lookup"><span data-stu-id="ff47c-105">Windows Desktop and Tablet Video Requirements and Capabilities</span></span>

<span data-ttu-id="ff47c-106">Lync 2013 bietet eine Einführung in die Hardwarebeschleunigung für Videocodierung und-Decodierung basierend auf dem Standard H. 264/MPEG-4 Part 10 Advanced Video Coding.</span><span class="sxs-lookup"><span data-stu-id="ff47c-106">Lync 2013 introduces hardware acceleration for video encoding and decoding based on the H.264/MPEG-4 Part 10 Advanced Video Coding standard.</span></span> <span data-ttu-id="ff47c-107">Diese Funktion sorgt dafür, dass auch Computer mit geringeren CPU-Taktgeschwindigkeiten höher auflösende Videos codieren und decodieren können.</span><span class="sxs-lookup"><span data-stu-id="ff47c-107">This feature allows computers with lower CPU clock speeds to encode and decode higher resolution video.</span></span> <span data-ttu-id="ff47c-108">Die Videohardware-Anforderungen hängen von der Computerkonfiguration und der gewünschten Videoauflösung ab.</span><span class="sxs-lookup"><span data-stu-id="ff47c-108">Video hardware requirements vary depending on the computer configuration and the video resolution wanted.</span></span>

<div>

## <a name="video-hardware-requirements"></a><span data-ttu-id="ff47c-109">Videohardware-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ff47c-109">Video Hardware Requirements</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ff47c-110">Feature</span><span class="sxs-lookup"><span data-stu-id="ff47c-110">Feature</span></span></th>
<th><span data-ttu-id="ff47c-111">Anforderung</span><span class="sxs-lookup"><span data-stu-id="ff47c-111">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff47c-112">Hardwarebeschleunigte H.264-Decodierung mit DirectX Video Acceleration (DXVA)</span><span class="sxs-lookup"><span data-stu-id="ff47c-112">Hardware accelerated H.264 decoding using DirectX Video Acceleration (DXVA)</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="ff47c-113">Die Grafikkarte muss DirectX 9.0 unterstützen und den Decodierungsmodus DXVA2_ModeH264_VLD_NoFGT beherrschen.</span><span class="sxs-lookup"><span data-stu-id="ff47c-113">Graphics card must support DirectX 9.0 and must expose the DXVA2_ModeH264_VLD_NoFGT decoding mode.</span></span></p></li>
<li><p><span data-ttu-id="ff47c-114">Der aktuellste Grafikkartentreiber muss installiert sein.</span><span class="sxs-lookup"><span data-stu-id="ff47c-114">The latest graphics card driver must be installed.</span></span></p></li>
</ul>
<div>

> [!NOTE]  
> <span data-ttu-id="ff47c-115">Ausführliche Informationen zu den Decodierungs Modi finden Sie unter <A href="https://go.microsoft.com/fwlink/p/?linkid=268530">https://go.microsoft.com/fwlink/p/?LinkId=268530</A> .</span><span class="sxs-lookup"><span data-stu-id="ff47c-115">For details about decoding modes, see <A href="https://go.microsoft.com/fwlink/p/?linkid=268530">https://go.microsoft.com/fwlink/p/?LinkId=268530</A>.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff47c-116">Hardwarebeschleunigte H.264-Codierung: Chipsatzanforderungen</span><span class="sxs-lookup"><span data-stu-id="ff47c-116">Hardware accelerated H.264 encoding: Chipset Requirements</span></span></p></td>
<td><p><span data-ttu-id="ff47c-117">Die folgenden Intel hardwarebeschleunigten Video Codierungs Lösungen werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="ff47c-117">The following Intel hardware accelerated video encoding solutions are supported:</span></span></p>
<ul>
<li><p><span data-ttu-id="ff47c-118">Intel HD Graphics 2000, 2500, 3000 und 4000 Chipsätze (oder aktuellere Versionen) der zweiten und dritten Generation mit integrierter Hardware-Videocodierung.</span><span class="sxs-lookup"><span data-stu-id="ff47c-118">Second and third generation Intel HD Graphics 2000, 2500, 3000, and 4000 chipsets (or later versions) with integrated hardware video encoders.</span></span> <span data-ttu-id="ff47c-119">Die Installation des Intel HD-Grafiktreibers 15.28.9.2884 oder des neuesten Treibers, der Folgendes enthält, ist erforderlich:</span><span class="sxs-lookup"><span data-stu-id="ff47c-119">Installation of the Intel HD Graphics driver 15.28.9.2884 or the latest driver containing the following is required:</span></span></p>
<ul>
<li><p><span data-ttu-id="ff47c-120">Anzeigen des Treibers 9.17.10.2884 oder des neuesten Treibers</span><span class="sxs-lookup"><span data-stu-id="ff47c-120">Display driver 9.17.10.2884 or the latest driver</span></span></p></li>
<li><p><span data-ttu-id="ff47c-121">Hardware Media Foundation Transform (HMFT) Version 3.12.10.31 oder die neueste HMFT</span><span class="sxs-lookup"><span data-stu-id="ff47c-121">Hardware media foundation transform (HMFT) version 3.12.10.31 or the latest HMFT</span></span></p></li>
</ul></li>
</ul>
<p><span data-ttu-id="ff47c-122">Die folgenden AMD-hardwarebeschleunigten Video Codierungs Lösungen werden unterstützt (erfordert ku1-Updates für lync Server 2013):</span><span class="sxs-lookup"><span data-stu-id="ff47c-122">The following AMD hardware accelerated video encoding solutions are supported (requires CU1 Updates for Lync Server 2013):</span></span></p>
<ul>
<li><p><span data-ttu-id="ff47c-123">AMD Video Codec Engine, die in mehreren diskreten Grafikkarten und in integrierten beschleunigten Verarbeitungseinheiten von AMD A-Series Accelerated Processors verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="ff47c-123">AMD Video Codec Engine, which is available in several discrete graphics cards and in integrated accelerated processing units of AMD A-Series Accelerated Processors.</span></span> <span data-ttu-id="ff47c-124">Der AMD Video Codec Engine Driver 9.12.0.0 oder höher muss installiert sein.</span><span class="sxs-lookup"><span data-stu-id="ff47c-124">The AMD Video Codec Engine driver 9.12.0.0 or higher must be installed.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff47c-125">Hardwarebeschleunigte H.264-Codierung: Kameraanforderungen</span><span class="sxs-lookup"><span data-stu-id="ff47c-125">Hardware accelerated H.264 encoding: Camera Requirements</span></span></p></td>
<td><p><span data-ttu-id="ff47c-126">USB-Videokameras mit integrierter H.264-Hardwarecodierung entsprechend der USB Video Class (UVC-)Spezifikation Version 1.5.</span><span class="sxs-lookup"><span data-stu-id="ff47c-126">USB video cameras with integrated H.264 hardware encoder that conforms to the USB Video Class (UVC) specification version 1.5.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="ff47c-127">Lync 2013 unterstützt UVC 1,5-Kameras mit Windows 8 oder Windows 8.1, einschließlich Unterstützung für UVC 1,5.</span><span class="sxs-lookup"><span data-stu-id="ff47c-127">Lync 2013 supports UVC 1.5 cameras with Windows 8 or Windows 8.1, which includes support for UVC 1.5.</span></span> <span data-ttu-id="ff47c-128">Da Windows 7 UVC 1.5 nicht unterstützt, behandelt Lync 2013 UVC 1.5-Kameras als normale Kameras ohne Hardwarecodierung.</span><span class="sxs-lookup"><span data-stu-id="ff47c-128">Because Windows 7 does not include support for UVC 1.5, Lync 2013 treats UVC 1.5 cameras as regular cameras with no hardware encoding support.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="determining-h264-video-encoding-and-decoding-capabilities"></a><span data-ttu-id="ff47c-129">Ermitteln der Fähigkeiten zur H.264-Videocodierung und -decodierung</span><span class="sxs-lookup"><span data-stu-id="ff47c-129">Determining H.264 Video Encoding and Decoding Capabilities</span></span>

<span data-ttu-id="ff47c-130">In der Regel werden die maximalen Codierungs- und Decodierungsmöglichkeiten einer konkreten Computerkonfiguration durch vier Hauptfaktoren bestimmt:</span><span class="sxs-lookup"><span data-stu-id="ff47c-130">Generally, there are four major factors that determine the maximum encoding and decoding capability of a particular computer configuration:</span></span>

  - <span data-ttu-id="ff47c-131">Unterstützung einer hardwarebeschleunigten Decodierung mittels DXVA</span><span class="sxs-lookup"><span data-stu-id="ff47c-131">Support for hardware accelerated decoding by using DXVA</span></span>

  - <span data-ttu-id="ff47c-132">Unterstützung einer hardwarebeschleunigten Codierung</span><span class="sxs-lookup"><span data-stu-id="ff47c-132">Support for hardware accelerated encoding</span></span>

  - <span data-ttu-id="ff47c-133">Anzahl der physischen Kerne</span><span class="sxs-lookup"><span data-stu-id="ff47c-133">Number of physical cores</span></span>

  - <span data-ttu-id="ff47c-134">Windows Experience Index (WEI)</span><span class="sxs-lookup"><span data-stu-id="ff47c-134">Windows Experience Index (WEI)</span></span>

<span data-ttu-id="ff47c-135">Das Windows System Assessment Tool (WinSAT) ermittelt den WEI-Wert.</span><span class="sxs-lookup"><span data-stu-id="ff47c-135">The Windows System Assessment Tool (WinSAT) determines the WEI.</span></span> <span data-ttu-id="ff47c-136">Wenn Sie das WinSAT-Tool ausführen, generiert es ein formal. Assessment XML-Dokument auf dem Computer im WinSAT- \\ \\ DataStore-Verzeichnis "% windir% Performance" \\ .</span><span class="sxs-lookup"><span data-stu-id="ff47c-136">When you run the WinSAT tool, it generates a Formal.Assessment XML document on the computer in the %windir%\\Performance\\WinSAT\\DataStore directory.</span></span> <span data-ttu-id="ff47c-137">Diese XML-Datei enthält die beiden folgenden Bewertungen, die für die Ermittlung der Codierungs- und Decodierungsmöglichkeiten ausgesprochen wichtig sind:</span><span class="sxs-lookup"><span data-stu-id="ff47c-137">This XML file contains the following two scores that are of particular importance for determining encoding and decoding capabilities:</span></span>

  - <span data-ttu-id="ff47c-138">Der Wert "VideoEncodeScore" gibt die softwarebasierte Viedeocodierungsfähigkeit des Computers an.</span><span class="sxs-lookup"><span data-stu-id="ff47c-138">The VideoEncodeScore indicates the software-based video encoding capability of the computer.</span></span>

  - <span data-ttu-id="ff47c-139">Der Wert "GraphicsScore" gibt die hardwarebeschleunigte Codierungsfähigkeit des Computers an.</span><span class="sxs-lookup"><span data-stu-id="ff47c-139">The GraphicsScore value indicates the hardware accelerated encoding capability of the computer.</span></span>

<span data-ttu-id="ff47c-p106">Die folgenden drei Tabellen erläutern die maximale Codierungs- und Decodierungsfähigkeiten verschiedener PC-Typen in Abhängigkeit der unterstützten Hardwarebeschleunigung. Für Auflösungen von 640 x 360 und darüber beträgt die maximal unterstützte Framerate 30 Frames pro Sekunde (fps). Für Auflösungen unter 640 x 360 beträgt die maximal unterstützte Framerate 15 fps.</span><span class="sxs-lookup"><span data-stu-id="ff47c-p106">The following three tables explain the maximum encoding and decoding capability for different PC types depending on what hardware acceleration they support. For resolutions of 640x360 and higher, the maximum supported frame rate is 30 frames per second (fps). For resolutions lower than 640x360, the maximum supported frame rate is 15 fps.</span></span>

### <a name="computer-without-dxva-and-without-hardware-accelerated-encoder"></a><span data-ttu-id="ff47c-143">Computer ohne DXVA und ohne hardwarebeschleunigten Codierer</span><span class="sxs-lookup"><span data-stu-id="ff47c-143">Computer Without DXVA And Without Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ff47c-144">Mögliche Codiererauflösung</span><span class="sxs-lookup"><span data-stu-id="ff47c-144">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="ff47c-145">Mögliche Decodiererauflösung</span><span class="sxs-lookup"><span data-stu-id="ff47c-145">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="ff47c-146">Anforderung</span><span class="sxs-lookup"><span data-stu-id="ff47c-146">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff47c-147">424 x 240</span><span class="sxs-lookup"><span data-stu-id="ff47c-147">424x240</span></span></p></td>
<td><p><span data-ttu-id="ff47c-148">424 x 240 (640 x 360 bei 15 fps für Szenarien bei denen nur empfangen wird)</span><span class="sxs-lookup"><span data-stu-id="ff47c-148">424x240 (640x360 at 15fps for receive only scenarios)</span></span></p></td>
<td><p><span data-ttu-id="ff47c-149">1 Kern und VideoEncodeScore ≥ 4,0</span><span class="sxs-lookup"><span data-stu-id="ff47c-149">1 Core and VideoEncodeScore ≥ 4.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff47c-150">640 x 360</span><span class="sxs-lookup"><span data-stu-id="ff47c-150">640x360</span></span></p></td>
<td><p><span data-ttu-id="ff47c-151">640 x 360</span><span class="sxs-lookup"><span data-stu-id="ff47c-151">640x360</span></span></p></td>
<td><p><span data-ttu-id="ff47c-152">2 Kerne und VideoEncodeScore ≥ 4,5</span><span class="sxs-lookup"><span data-stu-id="ff47c-152">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff47c-153">640 x 360</span><span class="sxs-lookup"><span data-stu-id="ff47c-153">640x360</span></span></p></td>
<td><p><span data-ttu-id="ff47c-154">1280X720</span><span class="sxs-lookup"><span data-stu-id="ff47c-154">1280x720</span></span></p></td>
<td><p><span data-ttu-id="ff47c-155">2 Kerne und VideoEncodeScore ≥ 4,5</span><span class="sxs-lookup"><span data-stu-id="ff47c-155">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff47c-156">640 x 360</span><span class="sxs-lookup"><span data-stu-id="ff47c-156">640x360</span></span></p></td>
<td><p><span data-ttu-id="ff47c-157">1920x1080</span><span class="sxs-lookup"><span data-stu-id="ff47c-157">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="ff47c-158">4 Kerne und VideoEncodeScore ≥ 4,5</span><span class="sxs-lookup"><span data-stu-id="ff47c-158">4 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff47c-159">1280X720</span><span class="sxs-lookup"><span data-stu-id="ff47c-159">1280x720</span></span></p></td>
<td><p><span data-ttu-id="ff47c-160">1280X720</span><span class="sxs-lookup"><span data-stu-id="ff47c-160">1280x720</span></span></p></td>
<td><p><span data-ttu-id="ff47c-161">4 Kerne und VideoEncodeScore ≥ 7,3</span><span class="sxs-lookup"><span data-stu-id="ff47c-161">4 Cores and VideoEncodeScore ≥ 7.3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff47c-162">1280X720</span><span class="sxs-lookup"><span data-stu-id="ff47c-162">1280x720</span></span></p></td>
<td><p><span data-ttu-id="ff47c-163">1920x1080</span><span class="sxs-lookup"><span data-stu-id="ff47c-163">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="ff47c-164">4 Kerne und VideoEncodeScore ≥ 7,3</span><span class="sxs-lookup"><span data-stu-id="ff47c-164">4 Cores and VideoEncodeScore ≥ 7.3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff47c-165">1920x1080</span><span class="sxs-lookup"><span data-stu-id="ff47c-165">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="ff47c-166">1920x1080</span><span class="sxs-lookup"><span data-stu-id="ff47c-166">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="ff47c-167">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="ff47c-167">N/A</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="computer-with-dxva-but-without-hardware-accelerated-encoder"></a><span data-ttu-id="ff47c-168">Computer mit DXVA, aber ohne hardwarebeschleunigten Codierer</span><span class="sxs-lookup"><span data-stu-id="ff47c-168">Computer With DXVA But Without Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ff47c-169">Mögliche Codiererauflösung</span><span class="sxs-lookup"><span data-stu-id="ff47c-169">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="ff47c-170">Mögliche Decodiererauflösung</span><span class="sxs-lookup"><span data-stu-id="ff47c-170">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="ff47c-171">Anforderung</span><span class="sxs-lookup"><span data-stu-id="ff47c-171">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff47c-172">424 x 240</span><span class="sxs-lookup"><span data-stu-id="ff47c-172">424x240</span></span></p></td>
<td><p><span data-ttu-id="ff47c-173">1920x1080</span><span class="sxs-lookup"><span data-stu-id="ff47c-173">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="ff47c-174">1 Kern und VideoEncodeScore = 3,0</span><span class="sxs-lookup"><span data-stu-id="ff47c-174">1 Core and VideoEncodeScore ≥ 3.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff47c-175">640 x 360</span><span class="sxs-lookup"><span data-stu-id="ff47c-175">640x360</span></span></p></td>
<td><p><span data-ttu-id="ff47c-176">1920x1080</span><span class="sxs-lookup"><span data-stu-id="ff47c-176">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="ff47c-177">2 Kerne und VideoEncodeScore = 4,5</span><span class="sxs-lookup"><span data-stu-id="ff47c-177">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff47c-178">960x540</span><span class="sxs-lookup"><span data-stu-id="ff47c-178">960x540</span></span></p></td>
<td><p><span data-ttu-id="ff47c-179">1920x1080</span><span class="sxs-lookup"><span data-stu-id="ff47c-179">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="ff47c-180">2 Kerne und VideoEncodeScore = 6,0</span><span class="sxs-lookup"><span data-stu-id="ff47c-180">2 Cores and VideoEncodeScore ≥ 6.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff47c-181">1280X720</span><span class="sxs-lookup"><span data-stu-id="ff47c-181">1280x720</span></span></p></td>
<td><p><span data-ttu-id="ff47c-182">1920x1080</span><span class="sxs-lookup"><span data-stu-id="ff47c-182">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="ff47c-183">4 Kerne und VideoEncodeScore = 6,7</span><span class="sxs-lookup"><span data-stu-id="ff47c-183">4 Cores and VideoEncodeScore ≥ 6.7</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff47c-184">1920x1080</span><span class="sxs-lookup"><span data-stu-id="ff47c-184">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="ff47c-185">1920x1080</span><span class="sxs-lookup"><span data-stu-id="ff47c-185">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="ff47c-186">4 Kerne und VideoEncodeScore = 8,2</span><span class="sxs-lookup"><span data-stu-id="ff47c-186">4 Cores and VideoEncodeScore ≥ 8.2</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="ff47c-187">Die WinSAT-Bewertung ist unter Windows 7 auf maximal 7,9 beschränkt.</span><span class="sxs-lookup"><span data-stu-id="ff47c-187">The WinSAT score on Windows 7 is limited to a maximum of 7.9.</span></span> <span data-ttu-id="ff47c-188">Die Codierungsfunktion für einen Computer ohne einen hardwarebeschleunigten Encoder kann daher nur auf Windows 8 oder Windows 8.1 erreicht werden, wobei die maximale WinSAT-Punktzahl 9,9 beträgt.</span><span class="sxs-lookup"><span data-stu-id="ff47c-188">Therefore, the encoding capability for a computer without a hardware accelerated encoder can only be achieved on Windows 8 or Windows 8.1, where the maximum WinSAT score is 9.9.</span></span>



</div>

### <a name="computer-with-dxva-and-with-intel-hd-graphics-hardware-accelerated-encoder"></a><span data-ttu-id="ff47c-189">Computer mit DXVA und mit durch Intel HD Graphics hardwarebeschleunigtem Codierer</span><span class="sxs-lookup"><span data-stu-id="ff47c-189">Computer With DXVA And With Intel HD Graphics Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ff47c-190">Mögliche Codiererauflösung</span><span class="sxs-lookup"><span data-stu-id="ff47c-190">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="ff47c-191">Mögliche Decodiererauflösung</span><span class="sxs-lookup"><span data-stu-id="ff47c-191">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="ff47c-192">Anforderung</span><span class="sxs-lookup"><span data-stu-id="ff47c-192">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff47c-193">1280X720</span><span class="sxs-lookup"><span data-stu-id="ff47c-193">1280x720</span></span></p></td>
<td><p><span data-ttu-id="ff47c-194">1920x1080</span><span class="sxs-lookup"><span data-stu-id="ff47c-194">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="ff47c-195">Alle Intel HD Graphics-Modelle der 2. und 3. Generation</span><span class="sxs-lookup"><span data-stu-id="ff47c-195">All 2nd and 3rd generation Intel HD Graphics</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff47c-196">1920x1080</span><span class="sxs-lookup"><span data-stu-id="ff47c-196">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="ff47c-197">1920x1080</span><span class="sxs-lookup"><span data-stu-id="ff47c-197">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="ff47c-198">Intel HD Graphics-Modelle der 2. und 3. Generation und GraphicsScore ≥ 5,0</span><span class="sxs-lookup"><span data-stu-id="ff47c-198">2nd and 3rd generation Intel HD Graphics and GraphicsScore ≥ 5.0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="mobile-device-video-capabilities"></a><span data-ttu-id="ff47c-199">Video Funktionen für mobile Geräte</span><span class="sxs-lookup"><span data-stu-id="ff47c-199">Mobile Device Video Capabilities</span></span>

<span data-ttu-id="ff47c-200">In der folgenden Tabelle werden die maximalen Videofunktionen für unterstützte mobile Geräte beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ff47c-200">The following table describes the maximum video capabilities for supported mobile devices.</span></span> <span data-ttu-id="ff47c-201">Weitere Informationen zur Unterstützung mobiler Geräte finden Sie unter [Planning for Mobile Clients in lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span><span class="sxs-lookup"><span data-stu-id="ff47c-201">For more information about mobile device support, see [Planning for mobile clients in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span></span>


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ff47c-202">Feature</span><span class="sxs-lookup"><span data-stu-id="ff47c-202">Feature</span></span></th>
<th><span data-ttu-id="ff47c-203">Windows Phone</span><span class="sxs-lookup"><span data-stu-id="ff47c-203">Windows Phone</span></span></th>
<th><span data-ttu-id="ff47c-204">iPhone</span><span class="sxs-lookup"><span data-stu-id="ff47c-204">iPhone</span></span></th>
<th><span data-ttu-id="ff47c-205">iPad</span><span class="sxs-lookup"><span data-stu-id="ff47c-205">iPad</span></span></th>
<th><span data-ttu-id="ff47c-206">Android</span><span class="sxs-lookup"><span data-stu-id="ff47c-206">Android</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff47c-207">Maximale Auflösung der H. 264-Codierung</span><span class="sxs-lookup"><span data-stu-id="ff47c-207">H.264 encoding maximum resolution</span></span></p></td>
<td><p><span data-ttu-id="ff47c-208">VGA</span><span class="sxs-lookup"><span data-stu-id="ff47c-208">VGA</span></span></p></td>
<td><p><span data-ttu-id="ff47c-209">QVGA: iPhone 4S</span><span class="sxs-lookup"><span data-stu-id="ff47c-209">QVGA: iPhone 4S</span></span></p>
<p><span data-ttu-id="ff47c-210">VGA: iPhone 5</span><span class="sxs-lookup"><span data-stu-id="ff47c-210">VGA: iPhone 5</span></span></p>
<p><span data-ttu-id="ff47c-211">720p: iPhone 5S und höher</span><span class="sxs-lookup"><span data-stu-id="ff47c-211">720p: iPhone 5S and later</span></span></p></td>
<td><p><span data-ttu-id="ff47c-212">VGA: iPad 2 und höher/iPad Mini 1 und höher</span><span class="sxs-lookup"><span data-stu-id="ff47c-212">VGA: iPad 2 and later/iPad mini 1 and later</span></span></p>
<p><span data-ttu-id="ff47c-213">720p: iPad Air/iPad Mini 2/iPad pro und höher</span><span class="sxs-lookup"><span data-stu-id="ff47c-213">720p: iPad Air/iPad mini 2/iPad Pro and later</span></span></p></td>
<td><p><span data-ttu-id="ff47c-214">Je nach Gerätemodell bis zu VGA</span><span class="sxs-lookup"><span data-stu-id="ff47c-214">Up to VGA depending on device model</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff47c-215">H. 264-Decodierungs maximale Auflösung</span><span class="sxs-lookup"><span data-stu-id="ff47c-215">H.264 decoding maximum resolution</span></span></p></td>
<td><p><span data-ttu-id="ff47c-216">VGA</span><span class="sxs-lookup"><span data-stu-id="ff47c-216">VGA</span></span></p></td>
<td><p><span data-ttu-id="ff47c-217">QVGA: iPhone 4S</span><span class="sxs-lookup"><span data-stu-id="ff47c-217">QVGA: iPhone 4S</span></span></p>
<p><span data-ttu-id="ff47c-218">VGA: iPhone 5</span><span class="sxs-lookup"><span data-stu-id="ff47c-218">VGA: iPhone 5</span></span></p>
<p><span data-ttu-id="ff47c-219">720p: iPhone 5S und höher</span><span class="sxs-lookup"><span data-stu-id="ff47c-219">720p: iPhone 5S and later</span></span></p></td>
<td><p><span data-ttu-id="ff47c-220">VGA: iPad 2 und höher/iPad Mini 1 und höher</span><span class="sxs-lookup"><span data-stu-id="ff47c-220">VGA: iPad 2 and later/iPad mini 1 and later</span></span></p>
<p><span data-ttu-id="ff47c-221">720p: iPad Air/iPad Mini 2/iPad pro und höher</span><span class="sxs-lookup"><span data-stu-id="ff47c-221">720p: iPad Air/iPad mini 2/iPad Pro and later</span></span></p></td>
<td><p><span data-ttu-id="ff47c-222">Je nach Gerätemodell bis zu VGA</span><span class="sxs-lookup"><span data-stu-id="ff47c-222">Up to VGA depending on device model</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

