---
title: 'Lync Server 2013: lync precall Diagnostics Tool'
description: 'Lync Server 2013: lync precall Diagnostics Tool.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync PreCall Diagnostics Tool
ms:assetid: 0ff291ec-cfb4-43eb-b5d6-a7a325681e3f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn451255(v=OCS.15)
ms:contentKeyID: 56708404
ms.date: 11/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17c2c51551fe0991eb354a628b1d4660baa1532b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571991"
---
# <a name="lync-precall-diagnostics-tool-in-lync-server-2013"></a><span data-ttu-id="80580-103">Tool für die lync-voranruf Diagnose in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="80580-103">Lync PreCall Diagnostics Tool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="80580-104">_**Letztes Änderungsstand des Themas:** 2016-11-04_</span><span class="sxs-lookup"><span data-stu-id="80580-104">_**Topic Last Modified:** 2016-11-04_</span></span>

<span data-ttu-id="80580-105">Das lync precall Diagnostics Tool (PCD) ist eine clientbasierte Anwendung, mit der Sie sehen können, wie sich der aktuelle Status Ihres Netzwerks auf die Audioqualität in einem bevorstehenden Enterprise-VoIP-Anruf auswirkt.</span><span class="sxs-lookup"><span data-stu-id="80580-105">The Lync PreCall Diagnostics Tool (PCD) is a client-based application that allows you to see how the current state of your network might impact the audio quality in an upcoming Enterprise Voice call.</span></span>

<span data-ttu-id="80580-106">PCD ist besonders nützlich in Situationen, in denen der letzte Hop eines Netzwerks am schwächsten ist (beispielsweise mit Laptops in einem öffentlichen WLAN-Netzwerk oder mit privaten Benutzern).</span><span class="sxs-lookup"><span data-stu-id="80580-106">PCD is most useful in situations where the last hop of a network is likely to be the weakest (for example, with laptops on a public WiFi network or home users).</span></span> <span data-ttu-id="80580-107">PCD erstellt einen kleinen Paketdaten Strom, der diese letzte Etappe des Netzwerks durchläuft.</span><span class="sxs-lookup"><span data-stu-id="80580-107">PCD creates a small packet stream that traverses this final leg of the network.</span></span> <span data-ttu-id="80580-108">Das Tool analysiert dann den Paketdaten Strom, um abzuschätzen, wie sich Jitter und Verlust entlang dieses Beins möglicherweise auf die Anrufqualität auswirken und dann einen Bericht bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="80580-108">The tool then analyzes the packet stream to estimate how the jitter and loss along this leg might impact call quality, and then provides a report.</span></span> <span data-ttu-id="80580-109">Sie können PCD kontinuierlich auf dem Client ausführen, auch wenn Anrufe getätigt werden.</span><span class="sxs-lookup"><span data-stu-id="80580-109">You can run PCD continuously on the client, even while calls are being placed.</span></span> <span data-ttu-id="80580-110">Der Paketdaten Strom hat keinen wesentlichen Einfluss auf die Bandbreite.</span><span class="sxs-lookup"><span data-stu-id="80580-110">The packet stream does not have a significant effect on bandwidth.</span></span>

<span data-ttu-id="80580-111">**Die neueste Version der PCD, Version 1,1, umfasst die folgenden Verbesserungen:**</span><span class="sxs-lookup"><span data-stu-id="80580-111">**The latest release of the PCD, version 1.1, includes the following enhancements:**</span></span>

  - <span data-ttu-id="80580-112">Unterstützung für längere Kennwörter, die jetzt bis zu 127 Zeichen lang sein können</span><span class="sxs-lookup"><span data-stu-id="80580-112">Support for longer passwords, which can now be up to 127 characters</span></span>

  - <span data-ttu-id="80580-113">Zusätzliche Diagnose für Authentifizierungs Anmeldeprobleme</span><span class="sxs-lookup"><span data-stu-id="80580-113">Additional diagnostics for authentication sign-in issues</span></span>

  - <span data-ttu-id="80580-114">Bessere Unterstützung für lync-hybridbereitstellungen</span><span class="sxs-lookup"><span data-stu-id="80580-114">Better support for Lync hybrid deployments</span></span>

  - <span data-ttu-id="80580-115">Aktualisierungen der Anmelde Informationsauswahl</span><span class="sxs-lookup"><span data-stu-id="80580-115">Updates to credential picker</span></span>

  - <span data-ttu-id="80580-116">Stabilitätsverbesserungen</span><span class="sxs-lookup"><span data-stu-id="80580-116">Stability improvements</span></span>

<span data-ttu-id="80580-117">Wir freuen uns über Feedback.</span><span class="sxs-lookup"><span data-stu-id="80580-117">We appreciate any feedback.</span></span> <span data-ttu-id="80580-118">Senden Sie alle Support Fragen oder Probleme an den [PCD-Feedback](mailto:pcdfb@microsoft.com) -Alias unter <pcdfb@microsoft.com> .</span><span class="sxs-lookup"><span data-stu-id="80580-118">Please send all support questions or issues to the [PCD Feedback](mailto:pcdfb@microsoft.com) alias at <pcdfb@microsoft.com>.</span></span>

<span data-ttu-id="80580-119">Dieses Thema enthält die folgenden Abschnitte:</span><span class="sxs-lookup"><span data-stu-id="80580-119">This topic includes the following sections:</span></span>

  - <span data-ttu-id="80580-120">Lync PCD-Versionen</span><span class="sxs-lookup"><span data-stu-id="80580-120">Lync PCD Versions</span></span>

  - <span data-ttu-id="80580-121">Lync PCD-System Anforderungen</span><span class="sxs-lookup"><span data-stu-id="80580-121">Lync PCD System Requirements</span></span>

  - <span data-ttu-id="80580-122">Lync PCD-Features</span><span class="sxs-lookup"><span data-stu-id="80580-122">Lync PCD Features</span></span>

  - <span data-ttu-id="80580-123">Ausführung von lync PCD</span><span class="sxs-lookup"><span data-stu-id="80580-123">Running Lync PCD</span></span>

  - <span data-ttu-id="80580-124">Deinstallieren von lync PCD</span><span class="sxs-lookup"><span data-stu-id="80580-124">Uninstalling Lync PCD</span></span>

<span id="Version"></span>

<div>

## <a name="lync-pcd-versions"></a><span data-ttu-id="80580-125">Lync PCD-Versionen</span><span class="sxs-lookup"><span data-stu-id="80580-125">Lync PCD Versions</span></span>

<span data-ttu-id="80580-126">In diesem Thema werden die folgenden Versionen des Tools beschrieben, die zum kostenlosen Download zur Verfügung stehen:</span><span class="sxs-lookup"><span data-stu-id="80580-126">This topic describes the following versions of the tool, available for free download:</span></span>

  - <span data-ttu-id="80580-127">Windows-Desktop-App ( [https://go.microsoft.com/fwlink/?LinkId=327914](https://go.microsoft.com/fwlink/p/?linkid=327914) )</span><span class="sxs-lookup"><span data-stu-id="80580-127">Windows Desktop App ([https://go.microsoft.com/fwlink/?LinkId=327914](https://go.microsoft.com/fwlink/p/?linkid=327914))</span></span>

</div>

<span id="Requirements"></span>

<div>

## <a name="lync-pcd-system-requirements"></a><span data-ttu-id="80580-128">Lync PCD-System Anforderungen</span><span class="sxs-lookup"><span data-stu-id="80580-128">Lync PCD System Requirements</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="80580-129">Für PCD ist es erforderlich, dass Unified Communications Web API (UCWA) installiert und konfiguriert werden, um Mobile Clients in der lync Server-Bereitstellung zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="80580-129">PCD requires that Unified Communications Web API (UCWA) be installed and configured to support mobile clients in the Lync Server deployment.</span></span> <span data-ttu-id="80580-130">UCWA wird mit lync Server installiert.</span><span class="sxs-lookup"><span data-stu-id="80580-130">UCWA is installed with Lync Server.</span></span>



</div>

<div>

## <a name="windows-desktop-app-requirements"></a><span data-ttu-id="80580-131">Windows-Desktop-App-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="80580-131">Windows Desktop App Requirements</span></span>

  - <span data-ttu-id="80580-132">Eine beliebige Edition des Windows 7 oder Windows 8 Betriebssystems</span><span class="sxs-lookup"><span data-stu-id="80580-132">Any edition of the Windows 7 or Windows 8 operating system</span></span>

  - <span data-ttu-id="80580-133">Microsoft .NET Framework 4.5 verfügbar unter [https://go.microsoft.com/fwlink/?LinkId=327790](https://go.microsoft.com/fwlink/p/?linkid=327790)</span><span class="sxs-lookup"><span data-stu-id="80580-133">Microsoft .NET Framework 4.5 available at [https://go.microsoft.com/fwlink/?LinkId=327790](https://go.microsoft.com/fwlink/p/?linkid=327790)</span></span>

</div>

</div>

<span id="features"></span>

<div>

## <a name="lync-pcd-features"></a><span data-ttu-id="80580-134">Lync PCD-Features</span><span class="sxs-lookup"><span data-stu-id="80580-134">Lync PCD Features</span></span>

<span data-ttu-id="80580-135">Lync PCD umfasst die folgenden Features:</span><span class="sxs-lookup"><span data-stu-id="80580-135">Lync PCD includes the following features:</span></span>

  - <span data-ttu-id="80580-136">Bei Bedarf in Standardausführung ausführen (2 Minuten Bursts)</span><span class="sxs-lookup"><span data-stu-id="80580-136">Run in default On Demand (2 minute bursts)</span></span>

  - <span data-ttu-id="80580-137">Ausführen von Always on (bis zu 24 Stunden im Modus "Angedockte Ansicht")</span><span class="sxs-lookup"><span data-stu-id="80580-137">Run in Always On (up to 24 hours in snapped view) mode</span></span>

  - <span data-ttu-id="80580-138">Verlaufsansicht der Test Läufe</span><span class="sxs-lookup"><span data-stu-id="80580-138">Historical view of your test runs</span></span>

  - <span data-ttu-id="80580-139">Diagnostizieren von Anmeldefehlern (nur lync PCD für Windows 8)</span><span class="sxs-lookup"><span data-stu-id="80580-139">Diagnose sign-in failures (Lync PCD for Windows 8 only)</span></span>

<span data-ttu-id="80580-140">![Anmeldebildschirm Schuss für lync PCD-Features](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Anmeldebildschirm Schuss für lync PCD-Features")</span><span class="sxs-lookup"><span data-stu-id="80580-140">![Lync PCD features Sign in progress screen shot](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Lync PCD features Sign in progress screen shot")</span></span>

  - <span data-ttu-id="80580-141">Grafische Ansicht der Netzwerk Metriken – Netzwerk-MOS, Paketverlust und interarrival-Jitter im Vollbildmodus und angedockte Ansicht.</span><span class="sxs-lookup"><span data-stu-id="80580-141">Graphical view of network metrics – Network MOS, Packet Loss and Interarrival Jitter in full screen and snapped view.</span></span>

<span data-ttu-id="80580-142">**Vollbildansicht**</span><span class="sxs-lookup"><span data-stu-id="80580-142">**Full screen view**</span></span>

<span data-ttu-id="80580-143">![Testergebnis Diagramme für das precall-Diagnose Tool](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "Testergebnis Diagramme für das precall-Diagnose Tool")</span><span class="sxs-lookup"><span data-stu-id="80580-143">![PreCall Diagnostic Tool test result graphs](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "PreCall Diagnostic Tool test result graphs")</span></span>

<span data-ttu-id="80580-144">**Angedockte Ansicht**</span><span class="sxs-lookup"><span data-stu-id="80580-144">**Snapped view**</span></span>

<span data-ttu-id="80580-145">![Testergebnisse für die Verwendung des precall-Diagnosetools](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "Testergebnisse für die Verwendung des precall-Diagnosetools")</span><span class="sxs-lookup"><span data-stu-id="80580-145">![PreCall Diagnostic Tool Utilization test results](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "PreCall Diagnostic Tool Utilization test results")</span></span>

</div>

<span id="running"></span>

<div>

## <a name="running-lync-pcd"></a><span data-ttu-id="80580-146">Ausführung von lync PCD</span><span class="sxs-lookup"><span data-stu-id="80580-146">Running Lync PCD</span></span>

<div>

## <a name="running-windows-desktop-app"></a><span data-ttu-id="80580-147">Windows-Desktop-App wird gestartet</span><span class="sxs-lookup"><span data-stu-id="80580-147">Running Windows Desktop App</span></span>

1.  <span data-ttu-id="80580-148">Um die PCD auf einem Windows 7 System zu starten, wählen Sie im **Startmenü** die Option " **Diagnose precall** " aus.</span><span class="sxs-lookup"><span data-stu-id="80580-148">To start the PCD on a Windows 7 system, select **PreCall Diagnostics** from the **Start** menu.</span></span>
    
    <span data-ttu-id="80580-149">Um die PCD auf einem Windows 8 System zu starten, wählen Sie das Symbol auf dem Startbildschirm aus, oder suchen Sie nach "Diagnose mit vorrufen".</span><span class="sxs-lookup"><span data-stu-id="80580-149">To start the PCD on a Windows 8 system, select the icon on your Start screen, or search for “PreCall Diagnostics.”</span></span>
    
    <span data-ttu-id="80580-150">![Symbol für das precall-Diagnosetool](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "Symbol für das precall-Diagnosetool")</span><span class="sxs-lookup"><span data-stu-id="80580-150">![PreCall Diagnostic tool icon](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "PreCall Diagnostic tool icon")</span></span>

2.  <span data-ttu-id="80580-151">Wenn das Tool gestartet wird, wählen Sie Ihre bevorzugte Methode zum Bereitstellen von Anmeldeinformationen aus, und wählen Sie im Dialogfeldoptionen für das Tool für die **Anruf Diagnose** den Netzwerkbetriebs Modus aus, und wählen Sie dann **OK**aus:</span><span class="sxs-lookup"><span data-stu-id="80580-151">When the tool starts, select your preferred method of providing credentials and select the network operating mode in the **PreCall Diagnostics Tool Options** dialog box, then select **OK**:</span></span>

3.  <span data-ttu-id="80580-152">Wählen Sie die Schaltfläche **Test starten** aus, um die Diagnose zu starten.</span><span class="sxs-lookup"><span data-stu-id="80580-152">Select the **Start Test** button to start running diagnostics.</span></span>
    
    <span data-ttu-id="80580-153">Wenn Sie die Option **Netzwerkanmeldeinformationen verwenden** ausgewählt haben, wird der Test sofort gestartet.</span><span class="sxs-lookup"><span data-stu-id="80580-153">If you selected the **Use network credentials** option, the test begins immediately.</span></span>
    
    <span data-ttu-id="80580-154">Wenn Sie die Option **Meine Anmeldeinformationen eingeben** aktiviert haben, wird das Dialogfeld **Windows-Sicherheit** geöffnet.</span><span class="sxs-lookup"><span data-stu-id="80580-154">If you selected the **Let me enter my credentials** option, the **Windows Security** dialog box opens.</span></span> <span data-ttu-id="80580-155">Nachdem Sie Ihre Anmeldeinformationen eingegeben haben, wird der Test gestartet.</span><span class="sxs-lookup"><span data-stu-id="80580-155">After you enter your credentials, the test starts.</span></span>

</div>

</div>

<span id="uninstall"></span>

<div>

## <a name="uninstalling-lync-pcd"></a><span data-ttu-id="80580-156">Deinstallieren von lync PCD</span><span class="sxs-lookup"><span data-stu-id="80580-156">Uninstalling Lync PCD</span></span>

<span data-ttu-id="80580-157">Um lync PCD zu entfernen, führen Sie das Verfahren für Ihr Betriebssystem aus:</span><span class="sxs-lookup"><span data-stu-id="80580-157">To remove Lync PCD, follow the procedure for your operating system:</span></span>

  - <span data-ttu-id="80580-158">Öffnen Sie auf einem Windows 7 **System die Systemsteuerung,** wählen Sie **Programme und Funktionen**aus, und doppelklicken Sie auf **lync 2013 Diagnose**für die vorab Verbindung.</span><span class="sxs-lookup"><span data-stu-id="80580-158">On a Windows 7 system, open the **Control Panel**, select **Programs and Features**, and double-click **Lync 2013 PreCall Diagnostics**.</span></span>

  - <span data-ttu-id="80580-159">Klicken Sie auf einem Windows 8 System mit der rechten Maustaste auf die PCD-Kachel, und klicken Sie auf der APP-Leiste am unteren Rand des Startbildschirms auf **deinstallieren** .</span><span class="sxs-lookup"><span data-stu-id="80580-159">On a Windows 8 system, right-click on the PCD tile and click **Uninstall** from the app bar at the bottom of the start screen.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

