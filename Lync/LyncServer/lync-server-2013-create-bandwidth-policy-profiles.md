---
title: 'Lync Server 2013: Erstellen von Bandbreitenrichtlinien Profilen'
description: 'Lync Server 2013: Erstellen von Bandbreitenrichtlinien Profilen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create bandwidth policy profiles
ms:assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412785(v=OCS.15)
ms:contentKeyID: 48185086
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9646657c84806bff8caef3352774cdc5ddeab862
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562331"
---
# <a name="create-bandwidth-policy-profiles-in-lync-server-2013"></a><span data-ttu-id="88ea1-103">Erstellen von Bandbreitenrichtlinien Profilen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88ea1-103">Create bandwidth policy profiles in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88ea1-104">_**Letztes Änderungsstand des Themas:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="88ea1-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="88ea1-105">*Bandbreitenrichtlinien* definieren Einschränkungen der Bandbreitennutzung für Audio-und Video-Echt Zeit Modalitäten.</span><span class="sxs-lookup"><span data-stu-id="88ea1-105">*Bandwidth policies* define limitations on bandwidth usage for real-time audio and video modalities.</span></span> <span data-ttu-id="88ea1-106">Bandbreitenrichtlinien werden auf *bandbreitenrichtlinienprofile*angewendet, die auf mehrere Netzwerkstandorte für die Anrufsteuerung angewendet werden können.</span><span class="sxs-lookup"><span data-stu-id="88ea1-106">Bandwidth policies are applied to *bandwidth policy profiles*, which can be applied to multiple network sites for call admission control.</span></span>

<span data-ttu-id="88ea1-107">Richtlinien zu den Bandbreiten Grenzwerten, die Sie in ihrer CAC-Bereitstellung festlegen sollten, finden Sie unter [Definieren der Anforderungen für die Anrufsteuerung in lync Server 2013](lync-server-2013-defining-your-requirements-for-call-admission-control.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="88ea1-107">For guidelines about what bandwidth limits you should set in your CAC deployment, see [Defining your requirements for call admission control in Lync Server 2013](lync-server-2013-defining-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="88ea1-108">Ausführliche Informationen zum Arbeiten mit Bandbreitenrichtlinien und Richtlinienprofilen finden Sie in der lync Server-Verwaltungsshell Dokumentation zu den folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="88ea1-108">For details about working with bandwidth policies and policy profiles, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="88ea1-109">New-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="88ea1-109">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)

  - [<span data-ttu-id="88ea1-110">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="88ea1-110">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)

  - [<span data-ttu-id="88ea1-111">Gruppe-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="88ea1-111">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)

  - [<span data-ttu-id="88ea1-112">Remove-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="88ea1-112">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)

<span data-ttu-id="88ea1-113">Die im folgenden Verfahren erstellten Beispiel Richtlinien legen Grenzwerte für den gesamten Audioverkehr, einzelne audiositzungen, den gesamten Videodatenverkehr und einzelne Videositzungen fest.</span><span class="sxs-lookup"><span data-stu-id="88ea1-113">The example policies created in the following procedure set limits for overall audio traffic, individual audio sessions, overall video traffic, and individual video sessions.</span></span> <span data-ttu-id="88ea1-114">Beispielsweise \_ legt das bandbreitenrichtlinienprofil für 5MB-Link die folgenden Grenzwerte fest:</span><span class="sxs-lookup"><span data-stu-id="88ea1-114">For example, the 5Mb\_Link bandwidth policy profile sets the following limits:</span></span>

  - <span data-ttu-id="88ea1-115">Grenzwert für Audiodaten: 2.000 Kbit/s</span><span class="sxs-lookup"><span data-stu-id="88ea1-115">Audio Limit: 2,000 kbps</span></span>

  - <span data-ttu-id="88ea1-116">Grenzwert für Audiositzung: 200 Kbit/s</span><span class="sxs-lookup"><span data-stu-id="88ea1-116">Audio Session Limit: 200 kbps</span></span>

  - <span data-ttu-id="88ea1-117">Grenzwert für Video: 1.400 KBit/s</span><span class="sxs-lookup"><span data-stu-id="88ea1-117">Video Limit: 1,400 kbps</span></span>

  - <span data-ttu-id="88ea1-118">Grenzwert für Video Sitzung: 700 Kbit/s</span><span class="sxs-lookup"><span data-stu-id="88ea1-118">Video Session Limit: 700 kbps</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="88ea1-119">Der Grenzwert für die minimale Audiositzung beträgt 40 Kbit/s.</span><span class="sxs-lookup"><span data-stu-id="88ea1-119">The minimum Audio Session Limit value is 40 kbps.</span></span> <span data-ttu-id="88ea1-120">Der Grenzwert für die minimale Video Sitzung beträgt 100 kbit/s.</span><span class="sxs-lookup"><span data-stu-id="88ea1-120">The minimum Video Session Limit value is 100 kbps.</span></span>



</div>

<div>

## <a name="to-create-bandwidth-policy-profiles-by-using-management-shell"></a><span data-ttu-id="88ea1-121">So erstellen Sie bandbreitenrichtlinienprofile mithilfe der Management-Shell</span><span class="sxs-lookup"><span data-stu-id="88ea1-121">To create bandwidth policy profiles by using Management Shell</span></span>

1.  <span data-ttu-id="88ea1-122">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="88ea1-122">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="88ea1-123">Führen Sie für jedes bandbreitenrichtlinienprofil, das Sie erstellen möchten, das New-CsNetworkBandwidthPolicyProfile-Cmdlet aus.</span><span class="sxs-lookup"><span data-stu-id="88ea1-123">For each bandwidth policy profile that you want to create, run the New-CsNetworkBandwidthPolicyProfile cmdlet.</span></span> <span data-ttu-id="88ea1-124">Führen Sie beispielsweise den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="88ea1-124">For example, run:</span></span>
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400  -VideoBWSessionLimit 700
       ```
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 10Mb_Link -Description "BW profile for 10Mb links" -AudioBWLimit 4000 -AudioBWSessionLimit 200 -VideoBWLimit 2800 -VideoBWSessionLimit 700
       ```
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 50Mb_Link -Description "BW profile for 50Mb links" -AudioBWLimit 20000 -AudioBWSessionLimit 200 -VideoBWLimit 14000 -VideoBWSessionLimit 700
       ```
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 25Mb_Link -Description "BW profile for 25Mb links" -AudioBWLimit 10000 -AudioBWSessionLimit 200 -VideoBWLimit 7000 -VideoBWSessionLimit 700
       ```

</div>

<div>

## <a name="to-create-bandwidth-policy-profiles-by-using-lync-server-control-panel"></a><span data-ttu-id="88ea1-125">So erstellen Sie bandbreitenrichtlinienprofile mithilfe von lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="88ea1-125">To create bandwidth policy profiles by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="88ea1-126">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="88ea1-126">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="88ea1-127">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="88ea1-127">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="88ea1-128">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="88ea1-128">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="88ea1-129">Klicken Sie auf die Navigationsschaltfläche **Richtlinienprofil** .</span><span class="sxs-lookup"><span data-stu-id="88ea1-129">Click the **Policy Profile** navigation button.</span></span>

4.  <span data-ttu-id="88ea1-130">Klicken Sie auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="88ea1-130">Click **New**.</span></span>

5.  <span data-ttu-id="88ea1-131">Klicken Sie auf der Seite **Neues Richtlinienprofil** auf **Name** , und geben Sie dann einen Namen für das bandbreitenrichtlinienprofil ein.</span><span class="sxs-lookup"><span data-stu-id="88ea1-131">On the **New Policy Profile** page, click **Name** and then type a name for the bandwidth policy profile.</span></span>

6.  <span data-ttu-id="88ea1-132">Klicken Sie auf **audiolimit**, und geben Sie die maximale Anzahl von Kbit/s ein, die für alle audiositzungen kombiniert werden dürfen.</span><span class="sxs-lookup"><span data-stu-id="88ea1-132">Click **Audio limit**, and then type in the maximum number of kbps to allow for all audio sessions combined.</span></span>

7.  <span data-ttu-id="88ea1-133">Klicken Sie auf **audiositzungs Grenzwert**, und geben Sie die maximale Anzahl von Kbit/s ein, die für jede einzelne Audiositzung zulässig sein soll.</span><span class="sxs-lookup"><span data-stu-id="88ea1-133">Click **Audio session limit**, and then type in the maximum number of kbps to allow for each individual audio session.</span></span>

8.  <span data-ttu-id="88ea1-134">Klicken Sie auf **Video Limit**, und geben Sie dann die maximale Anzahl von Kbit/s ein, die für alle kombinierten Videositzungen zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="88ea1-134">Click **Video limit**, and then type in the maximum number of kbps to allow for all video sessions combined.</span></span>

9.  <span data-ttu-id="88ea1-135">Klicken Sie auf **Video Sitzungs Grenzwert**, und geben Sie die maximale Anzahl von Kbit/s ein, die für jede einzelne Videositzung zulässig sein soll.</span><span class="sxs-lookup"><span data-stu-id="88ea1-135">Click **Video session limit**, and then type in the maximum number of kbps to allow for each individual video session.</span></span>

10. <span data-ttu-id="88ea1-136">Klicken Sie optional auf **Beschreibung**, und geben Sie weitere Informationen zur Beschreibung dieses bandbreitenrichtlinienprofils ein.</span><span class="sxs-lookup"><span data-stu-id="88ea1-136">Optionally, click **Description**, and then type additional information to describe this bandwidth policy profile.</span></span>

11. <span data-ttu-id="88ea1-137">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="88ea1-137">Click **Commit**.</span></span>

12. <span data-ttu-id="88ea1-138">Wiederholen Sie die Schritte 4 bis 11 mit Einstellungen für andere bandbreitenrichtlinienprofile, um die Erstellung von Bandbreitenrichtlinien Profilen für Ihre Topologie abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="88ea1-138">To finish creating bandwidth policy profiles for your topology, repeat steps 4 through 11 with settings for other bandwidth policy profiles.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

