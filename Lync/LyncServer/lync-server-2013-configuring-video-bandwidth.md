---
title: 'Lync Server 2013: Konfigurieren der Videobandbreite'
description: 'Lync Server 2013: Konfigurieren der Videobandbreite.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring video bandwidth in Lync Server
ms:assetid: 446bed91-b26f-4ab2-b2f5-36e6810b405b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204842(v=OCS.15)
ms:contentKeyID: 48183984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 85fedbe2fb856696236e79c3bbcece34d5af4a34
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550671"
---
# <a name="configuring-video-bandwidth-in-lync-server-2013"></a><span data-ttu-id="02b0e-103">Konfigurieren der Videobandbreite in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02b0e-103">Configuring video bandwidth in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02b0e-104">_**Letztes Änderungsstand des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="02b0e-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="02b0e-105">Lync Server 2013 enthält verschiedene Einstellungen für die Verwaltung von Videos für Anrufe mit zwei Teilnehmern und Konferenzen mit mehreren Teilnehmern.</span><span class="sxs-lookup"><span data-stu-id="02b0e-105">Lync Server 2013 includes several settings for managing video for two-party calls and multiparty conferences.</span></span> <span data-ttu-id="02b0e-106">Wenn Sie lync Server 2013 bereitstellen, sollten Sie überprüfen, ob die Standardeinstellungen für Ihre Organisation geeignet sind, und Sie bei Bedarf ändern.</span><span class="sxs-lookup"><span data-stu-id="02b0e-106">When you deploy Lync Server 2013, you should evaluate whether the default settings are appropriate for your organization, and modify them as necessary.</span></span>

<span data-ttu-id="02b0e-p102">Die in diesem Abschnitt beschriebenen Parameter gelten für Anrufe mit zwei und Konferenzen mit mehreren Teilnehmern. Sie können diese Einstellungen mithilfe eines der folgenden Cmdlets anzeigen oder ändern:</span><span class="sxs-lookup"><span data-stu-id="02b0e-p102">The parameters described in this section apply to both two-party calls and multiparty conferencing. View or modify these settings by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="02b0e-109">**Get-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="02b0e-109">**Get-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="02b0e-110">**Gruppe-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="02b0e-110">**Set-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="02b0e-111">**New-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="02b0e-111">**New-CsConferencingPolicy**</span></span>

<span data-ttu-id="02b0e-112">Überprüfen Sie in Ihrer Konferenzrichtlinie die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="02b0e-112">Verify the following settings in your conferencing policy:</span></span>

  - <span data-ttu-id="02b0e-113">**VideoBitRateKb**     Diese Einstellung gibt die maximale Video Bitrate (Kbit/s) an, die für von einem Benutzer gesendete Videodaten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="02b0e-113">**VideoBitRateKb**   This setting specifies the maximum video bit rate in kilobits per second (kbps) used for video sent by a user.</span></span> <span data-ttu-id="02b0e-114">Der Standardwert ist 50.000 KBit/s.</span><span class="sxs-lookup"><span data-stu-id="02b0e-114">The default value is 50000 kbps.</span></span> <span data-ttu-id="02b0e-115">Gültige Werte sind 0 bis 50.000 KBit/s.</span><span class="sxs-lookup"><span data-stu-id="02b0e-115">Valid values are 0 to 50000.</span></span>
    
    <span data-ttu-id="02b0e-116">Diese Einstellung gilt separat für Haupt- und Panoramavideo.</span><span class="sxs-lookup"><span data-stu-id="02b0e-116">This setting applies separately to main video and panoramic video.</span></span>
    
    <span data-ttu-id="02b0e-117">Beispiel: Wenn Sie 2000 Kbit/s angeben, können lync Server 2000 Kbit/s für den Haupt-Videodatenstrom und 2000 Kbit/s für den Panorama-Videostream senden.</span><span class="sxs-lookup"><span data-stu-id="02b0e-117">Example: if you specify 2000 kbps, then Lync Server can send 2000 kbps for the main video stream and 2000 kbps for the panoramic video stream.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="02b0e-118">Die maximale Video Netzwerkbandbreite für einen lync 2013 Endpunkt beträgt 8000 kBit/s für das Hauptvideo und 2500 Kbit/s für Panorama Video.</span><span class="sxs-lookup"><span data-stu-id="02b0e-118">The maximum video network bandwidth for a Lync 2013 endpoint is 8000 kbps for the main video and 2500 kbps for panoramic video.</span></span> <span data-ttu-id="02b0e-119">Diese Höchstwerte werden nur erreicht, wenn mehrere Videos gesendet oder empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="02b0e-119">These maximum values are reached only if multiple videos are received or sent.</span></span> <span data-ttu-id="02b0e-120">Ausführliche Informationen finden Sie im Abschnitt "Verwendung des Medien Verkehrs Netzwerks" unter Anforderungen an die <A href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">Netzwerkbandbreite für Mediendatenverkehr in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="02b0e-120">For details, see the "Media Traffic Network Usage" section in <A href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">Network bandwidth requirements for media traffic in Lync Server 2013</A>.</span></span> <span data-ttu-id="02b0e-121">In diesem Abschnitt sind die maximale und typische Videostream-Bandbreite für alle unterstützen Auflösungen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="02b0e-121">This section lists the maximum and typical video stream bandwidth for all supported resolutions.</span></span>

    
    </div>

  - <span data-ttu-id="02b0e-122">**TotalReceiveVideoBitRateKb**     Diese Einstellung, die neu in lync Server 2013 ist, gibt die maximal zulässige Bitrate (in Kbit/s) für alle Videodatenströme an, die von einem Client empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="02b0e-122">**TotalReceiveVideoBitRateKb**   This setting, which is new in Lync Server 2013, specifies the maximum allowed bitrate (in kilobits per second) for all the video streams received by a client.</span></span> <span data-ttu-id="02b0e-123">Dies bedeutet, dass damit der kombinierte Gesamtwert für alle Videostreams mit Ausnahme der Panoramavideo-Streams angegeben wird, die ein Client empfangen kann.</span><span class="sxs-lookup"><span data-stu-id="02b0e-123">That is, it specifies the combined total for all the video streams, except for panoramic video streams, that a client can receive.</span></span> <span data-ttu-id="02b0e-124">Wenn Sie beispielsweise 1.500 KBit/s angeben, kann ein Client bis zu 1.500 KBit/s an Videoinhalten empfangen, die aus einem einzelnen oder mehreren Videostreams bestehen können.</span><span class="sxs-lookup"><span data-stu-id="02b0e-124">For example, if you specify 1500 kbps, then a client can receive up to 1500 kbps of video, which may consist of multiple video streams or a single video stream.</span></span> <span data-ttu-id="02b0e-125">Diese Einstellung gilt nur für lync Server 2013 Clients.</span><span class="sxs-lookup"><span data-stu-id="02b0e-125">This setting applies only to Lync Server 2013 clients.</span></span>
    
    <span data-ttu-id="02b0e-p106">Der Standardwert für **TotalReceiveVideoBitRateKb** ist 50.000 KBit/s. Wenn die **EnableMultiviewJoin**-Einstellung für die Katalogansicht auf "True" festgelegt ist, darf **TotalReceiveVideoBitRateKb** nicht auf weniger als 420 KBit/s festgelegt sein. Wenn die **EnableMultiviewJoin**-Einstellung für die Katalogansicht auf "True" festgelegt ist, darf **TotalReceiveVideoBitRateKb** nicht auf weniger als 100 KBit/s festgelegt sein. Wenn **EnableMultiviewJoin** auf "True" festgelegt ist und Sie den Wert auf weniger als 420 KBit/s festlegen, werden die Werte standardmäßig auf den Schwellenwert festgelegt. Dieser Schwellenwert verhindert versehentliche Fehlkonfigurationen, die eine schlechte Benutzererfahrung zur Folge haben könnten.</span><span class="sxs-lookup"><span data-stu-id="02b0e-p106">The default value for **TotalReceiveVideoBitRateKb** is 50000 kbps. If the **EnableMultiviewJoin** setting for Gallery View is set to True, **TotalReceiveVideoBitRateKb** must not be set below 420 kbps. If the **EnableMultiviewJoin** setting for Gallery View is set to False, **TotalReceiveVideoBitRateKb** must not be set below 100 kbps. If **EnableMultiviewJoin** is set to True and you set the value below 420 kbps, the values will default to the threshold value. This threshold helps prevent accidental misconfiguration that might result in poor user experience.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="02b0e-131">Ausführliche Informationen zur <STRONG>EnableMultiviewJoin</STRONG> -Einstellung finden Sie unter <A href="lync-server-2013-configuring-gallery-view.md">Configuring Gallery View in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="02b0e-131">For details about the <STRONG>EnableMultiviewJoin</STRONG> setting, see <A href="lync-server-2013-configuring-gallery-view.md">Configuring Gallery View in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="02b0e-132">**MaxVideoConferencingResolution**     Dieser Parameter wird nicht mehr für lync Server 2013 Clients in lync Server 2013 Konferenzen verwendet.</span><span class="sxs-lookup"><span data-stu-id="02b0e-132">**MaxVideoConferencingResolution**   This parameter is no longer used for Lync Server 2013 clients in Lync Server 2013 conferences.</span></span> <span data-ttu-id="02b0e-133">In lync Server 2013 Konferenzen werden die weiter oben in diesem Abschnitt beschriebenen Bitraten Steuerelemente verwendet.</span><span class="sxs-lookup"><span data-stu-id="02b0e-133">Lync Server 2013 conferences use the bit rate controls described earlier in this section.</span></span> <span data-ttu-id="02b0e-134">Diese Einstellung wird weiterhin für Legacyclients verwendet, die einer lync Server 2013 Konferenz beitreten.</span><span class="sxs-lookup"><span data-stu-id="02b0e-134">This setting is still used for legacy clients joining a Lync Server 2013 conference.</span></span> <span data-ttu-id="02b0e-135">Dieser Parameter bestimmt die maximal zulässige Auflösung für Legacyclients in Konferenzen, die von Benutzern organisiert werden, die in lync Server 2013 verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="02b0e-135">This parameter determines the maximum resolution allowed for legacy clients in conferences organized by users who are homed on Lync Server 2013.</span></span> <span data-ttu-id="02b0e-136">Ältere Clients werden also genauso behandelt wie in früheren Versionen von lync Server oder Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="02b0e-136">That is, legacy clients are treated the same as they were in previous versions of Lync Server or Office Communications Server.</span></span>

<span data-ttu-id="02b0e-p108">Überprüfen Sie zusätzlich zu den für Benutzer geltenden Einstellungen für Konferenzrichtlinien die Medienkonfigurationseinstellungen. Sie können diese Einstellungen mithilfe eines der folgenden Cmdlets anzeigen oder ändern:</span><span class="sxs-lookup"><span data-stu-id="02b0e-p108">In addition to conferencing policy settings that apply to users, evaluate media configuration settings. View or modify these settings by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="02b0e-139">**Get-CsMediaConfiguration**</span><span class="sxs-lookup"><span data-stu-id="02b0e-139">**Get-CsMediaConfiguration**</span></span>

  - <span data-ttu-id="02b0e-140">**Gruppe-CsMediaConfiguration**</span><span class="sxs-lookup"><span data-stu-id="02b0e-140">**Set- CsMediaConfiguration**</span></span>

  - <span data-ttu-id="02b0e-141">**New-CsMediaConfiguration**</span><span class="sxs-lookup"><span data-stu-id="02b0e-141">**New- CsMediaConfiguration**</span></span>

<span data-ttu-id="02b0e-142">Überprüfen Sie die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="02b0e-142">Verify the following setting:</span></span>

  - <span data-ttu-id="02b0e-143">**MaxVideoRateAllowed**     Diese Einstellung pro Pool gibt die maximale Rate an, mit der Videosignale an den Clientendpunkten übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="02b0e-143">**MaxVideoRateAllowed**   This per-pool setting specifies the maximum rate at which video signals will be transferred at the client endpoints.</span></span> <span data-ttu-id="02b0e-144">Sie gilt nur für frühere Versionen von lync Server Clients.</span><span class="sxs-lookup"><span data-stu-id="02b0e-144">It applies only to previous versions of Lync Server clients.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="02b0e-145">Lync Server 2013 Clients ignorieren diese Einstellung und verwenden stattdessen die TotalReceiveVideoBitRateKb-Einstellung in der konferenzrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="02b0e-145">Lync Server 2013 clients ignore this setting and use the TotalReceiveVideoBitRateKb setting in conferencing policy instead.</span></span>

    
    </div>
    
    <span data-ttu-id="02b0e-p110">Der Standardwert ist HD720P. Gültige Werte sind HD720p15M, VGA600K und CIF250K.</span><span class="sxs-lookup"><span data-stu-id="02b0e-p110">The default value is HD720P. Valid values are HD720p15M, VGA600K, and CIF250K.</span></span>
    
    <span data-ttu-id="02b0e-148">Beispiel: Wenn Sie 1.500 KBit/s angeben, können alle Clients von Vorversionen im Pool in Konferenzen mit zwei oder mehr Teilnehmern bis zu 1.500 KBit/s an Videoinhalten empfangen.</span><span class="sxs-lookup"><span data-stu-id="02b0e-148">Example: If you specify 1500 kbps, then all the legacy clients in the pool can receive up to 1500 kbps of video in two-party or multiparty conferences.</span></span>

<span data-ttu-id="02b0e-149">Die folgenden Verfahren sind Beispiele für die Verwendung von lync Server-Verwaltungsshell zum Ändern der in diesem Abschnitt beschriebenen Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="02b0e-149">The following procedures are examples of using Lync Server Management Shell to modify the settings described in this section.</span></span>

<div>

## <a name="to-modify-conferencing-policy-for-video-settings"></a><span data-ttu-id="02b0e-150">So ändern Sie die Einstellungen der Konferenzrichtlinie für Videos</span><span class="sxs-lookup"><span data-stu-id="02b0e-150">To modify conferencing policy for video settings</span></span>

1.  <span data-ttu-id="02b0e-151">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="02b0e-151">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="02b0e-152">Führen Sie an der Befehlszeile das folgende Cmdlet aus, um die Konferenzrichtlinie zu bearbeiten:</span><span class="sxs-lookup"><span data-stu-id="02b0e-152">At the command line, run the following cmdlet to edit conferencing policy:</span></span>
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -VideoBitRateKb 2000 -TotalReceiveVideoBitRateKb 2000 

</div>

<div>

## <a name="to-modify-media-configuration-for-legacy-clients"></a><span data-ttu-id="02b0e-153">So ändern Sie die Medienkonfiguration für Clients von Vorversionen</span><span class="sxs-lookup"><span data-stu-id="02b0e-153">To modify media configuration for legacy clients</span></span>

1.  <span data-ttu-id="02b0e-154">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="02b0e-154">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="02b0e-155">Führen Sie an der Befehlszeile das folgende Cmdlet aus, um die Medienklonfiguration zu bearbeiten:</span><span class="sxs-lookup"><span data-stu-id="02b0e-155">At the command line, run the following cmdlet to edit the media configuration:</span></span>
    
        Set-CsMediaConfiguration -Identity site:Redmond01 -MaxVideoRateAllowed CIF250K

</div>

</div>

<span> </span>

</div>

</div>

</div>

