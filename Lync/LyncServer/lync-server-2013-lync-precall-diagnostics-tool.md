---
title: 'Lync Server 2013: lync-Tool zur voranruf Diagnose'
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
ms.openlocfilehash: 004d3b30dc2c2886eb7a2d8977f1da062277cc92
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742335"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-precall-diagnostics-tool-in-lync-server-2013"></a><span data-ttu-id="ec70f-102">Lync-Tool für die voranruf Diagnose in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ec70f-102">Lync PreCall Diagnostics Tool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ec70f-103">_**Letztes Änderungsdatum des Themas:** 2016-11-04_</span><span class="sxs-lookup"><span data-stu-id="ec70f-103">_**Topic Last Modified:** 2016-11-04_</span></span>

<span data-ttu-id="ec70f-104">Das lync precall Diagnostics Tool (PCD) ist eine clientbasierte Anwendung, mit der Sie sehen können, wie sich der aktuelle Zustand Ihres Netzwerks in einem bevorstehenden Enterprise-VoIP-Anruf auf die Audioqualität auswirken kann.</span><span class="sxs-lookup"><span data-stu-id="ec70f-104">The Lync PreCall Diagnostics Tool (PCD) is a client-based application that allows you to see how the current state of your network might impact the audio quality in an upcoming Enterprise Voice call.</span></span>

<span data-ttu-id="ec70f-105">PCD eignet sich besonders für Situationen, in denen der letzte Hop eines Netzwerks wahrscheinlich am schwächsten ist (beispielsweise bei Laptops mit einem öffentlichen WLAN-Netzwerk oder privaten Benutzern).</span><span class="sxs-lookup"><span data-stu-id="ec70f-105">PCD is most useful in situations where the last hop of a network is likely to be the weakest (for example, with laptops on a public WiFi network or home users).</span></span> <span data-ttu-id="ec70f-106">PCD erstellt einen kleinen Paketdaten Strom, der diese letzte Etappe des Netzwerks durchläuft.</span><span class="sxs-lookup"><span data-stu-id="ec70f-106">PCD creates a small packet stream that traverses this final leg of the network.</span></span> <span data-ttu-id="ec70f-107">Das Tool analysiert dann den Paketdaten Strom, um zu schätzen, wie sich der Jitter und der Verlust an diesem Bein auf die Anrufqualität auswirken können, und stellt dann einen Bericht bereit.</span><span class="sxs-lookup"><span data-stu-id="ec70f-107">The tool then analyzes the packet stream to estimate how the jitter and loss along this leg might impact call quality, and then provides a report.</span></span> <span data-ttu-id="ec70f-108">Sie können PCD kontinuierlich auf dem Client ausführen, auch wenn Anrufe getätigt werden.</span><span class="sxs-lookup"><span data-stu-id="ec70f-108">You can run PCD continuously on the client, even while calls are being placed.</span></span> <span data-ttu-id="ec70f-109">Der Paketdaten Strom hat keinen signifikanten Einfluss auf die Bandbreite.</span><span class="sxs-lookup"><span data-stu-id="ec70f-109">The packet stream does not have a significant effect on bandwidth.</span></span>

<span data-ttu-id="ec70f-110">**Die neueste Version der PCD, Version 1,1, umfasst die folgenden Verbesserungen:**</span><span class="sxs-lookup"><span data-stu-id="ec70f-110">**The latest release of the PCD, version 1.1, includes the following enhancements:**</span></span>

  - <span data-ttu-id="ec70f-111">Unterstützung für längere Kennwörter, die nun bis zu 127 Zeichen lang sein können</span><span class="sxs-lookup"><span data-stu-id="ec70f-111">Support for longer passwords, which can now be up to 127 characters</span></span>

  - <span data-ttu-id="ec70f-112">Zusätzliche Diagnose für Anmeldeprobleme bei der Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="ec70f-112">Additional diagnostics for authentication sign-in issues</span></span>

  - <span data-ttu-id="ec70f-113">Bessere Unterstützung für lync-hybridbereitstellungen</span><span class="sxs-lookup"><span data-stu-id="ec70f-113">Better support for Lync hybrid deployments</span></span>

  - <span data-ttu-id="ec70f-114">Aktualisierungen der Anmelde Informationsauswahl</span><span class="sxs-lookup"><span data-stu-id="ec70f-114">Updates to credential picker</span></span>

  - <span data-ttu-id="ec70f-115">Verbesserungen bei der Stabilität</span><span class="sxs-lookup"><span data-stu-id="ec70f-115">Stability improvements</span></span>

<span data-ttu-id="ec70f-116">Wir freuen uns über Ihr Feedback.</span><span class="sxs-lookup"><span data-stu-id="ec70f-116">We appreciate any feedback.</span></span> <span data-ttu-id="ec70f-117">Senden Sie bitte alle Support <pcdfb@microsoft.com>-Fragen oder Probleme an den PCD- [Feedback](mailto:pcdfb@microsoft.com) -Alias unter.</span><span class="sxs-lookup"><span data-stu-id="ec70f-117">Please send all support questions or issues to the [PCD Feedback](mailto:pcdfb@microsoft.com) alias at <pcdfb@microsoft.com>.</span></span>

<span data-ttu-id="ec70f-118">Dieses Thema enthält die folgenden Abschnitte:</span><span class="sxs-lookup"><span data-stu-id="ec70f-118">This topic includes the following sections:</span></span>

  - <span data-ttu-id="ec70f-119">Lync-PCD-Versionen</span><span class="sxs-lookup"><span data-stu-id="ec70f-119">Lync PCD Versions</span></span>

  - <span data-ttu-id="ec70f-120">System Anforderungen für lync-PCD</span><span class="sxs-lookup"><span data-stu-id="ec70f-120">Lync PCD System Requirements</span></span>

  - <span data-ttu-id="ec70f-121">Funktionen von lync PCD</span><span class="sxs-lookup"><span data-stu-id="ec70f-121">Lync PCD Features</span></span>

  - <span data-ttu-id="ec70f-122">Ausführen von lync PCD</span><span class="sxs-lookup"><span data-stu-id="ec70f-122">Running Lync PCD</span></span>

  - <span data-ttu-id="ec70f-123">Deinstallieren von lync PCD</span><span class="sxs-lookup"><span data-stu-id="ec70f-123">Uninstalling Lync PCD</span></span>

<span id="Version"></span>

<div>

## <a name="lync-pcd-versions"></a><span data-ttu-id="ec70f-124">Lync-PCD-Versionen</span><span class="sxs-lookup"><span data-stu-id="ec70f-124">Lync PCD Versions</span></span>

<span data-ttu-id="ec70f-125">In diesem Thema werden die folgenden Versionen des Tools beschrieben, die zum kostenlosen Download zur Verfügung stehen:</span><span class="sxs-lookup"><span data-stu-id="ec70f-125">This topic describes the following versions of the tool, available for free download:</span></span>

  - <span data-ttu-id="ec70f-126">Windows-Desktop-[http://go.microsoft.com/fwlink/?LinkId=327914](http://go.microsoft.com/fwlink/p/?linkid=327914)app ()</span><span class="sxs-lookup"><span data-stu-id="ec70f-126">Windows Desktop App ([http://go.microsoft.com/fwlink/?LinkId=327914](http://go.microsoft.com/fwlink/p/?linkid=327914))</span></span>

</div>

<span id="Requirements"></span>

<div>

## <a name="lync-pcd-system-requirements"></a><span data-ttu-id="ec70f-127">System Anforderungen für lync-PCD</span><span class="sxs-lookup"><span data-stu-id="ec70f-127">Lync PCD System Requirements</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ec70f-128">Für PCD muss die Unified Communications Web API (UCWA) installiert und für die Unterstützung mobiler Clients in der lync Server-Bereitstellung konfiguriert sein.</span><span class="sxs-lookup"><span data-stu-id="ec70f-128">PCD requires that Unified Communications Web API (UCWA) be installed and configured to support mobile clients in the Lync Server deployment.</span></span> <span data-ttu-id="ec70f-129">UCWA wird mit lync Server installiert.</span><span class="sxs-lookup"><span data-stu-id="ec70f-129">UCWA is installed with Lync Server.</span></span>



</div>

<div>

## <a name="windows-desktop-app-requirements"></a><span data-ttu-id="ec70f-130">Windows-Desktop-App-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ec70f-130">Windows Desktop App Requirements</span></span>

  - <span data-ttu-id="ec70f-131">Eine beliebige Edition des Betriebssystems Windows 7 oder Windows 8</span><span class="sxs-lookup"><span data-stu-id="ec70f-131">Any edition of the Windows 7 or Windows 8 operating system</span></span>

  - <span data-ttu-id="ec70f-132">Microsoft .NET Framework 4,5 verfügbar unter[http://go.microsoft.com/fwlink/?LinkId=327790](http://go.microsoft.com/fwlink/p/?linkid=327790)</span><span class="sxs-lookup"><span data-stu-id="ec70f-132">Microsoft .NET Framework 4.5 available at [http://go.microsoft.com/fwlink/?LinkId=327790](http://go.microsoft.com/fwlink/p/?linkid=327790)</span></span>

</div>

</div>

<span id="features"></span>

<div>

## <a name="lync-pcd-features"></a><span data-ttu-id="ec70f-133">Funktionen von lync PCD</span><span class="sxs-lookup"><span data-stu-id="ec70f-133">Lync PCD Features</span></span>

<span data-ttu-id="ec70f-134">Lync PCD umfasst die folgenden Features:</span><span class="sxs-lookup"><span data-stu-id="ec70f-134">Lync PCD includes the following features:</span></span>

  - <span data-ttu-id="ec70f-135">Standardmäßige Ausführung bei Bedarf (2 Minuten Bursts)</span><span class="sxs-lookup"><span data-stu-id="ec70f-135">Run in default On Demand (2 minute bursts)</span></span>

  - <span data-ttu-id="ec70f-136">Ausführen von "immer aktiviert" (bis zu 24 Stunden in der angedockten Ansicht)</span><span class="sxs-lookup"><span data-stu-id="ec70f-136">Run in Always On (up to 24 hours in snapped view) mode</span></span>

  - <span data-ttu-id="ec70f-137">Verlaufsansicht ihrer Testläufe</span><span class="sxs-lookup"><span data-stu-id="ec70f-137">Historical view of your test runs</span></span>

  - <span data-ttu-id="ec70f-138">Diagnostizieren von Anmeldefehlern (nur lync PCD für Windows 8)</span><span class="sxs-lookup"><span data-stu-id="ec70f-138">Diagnose sign-in failures (Lync PCD for Windows 8 only)</span></span>

<span data-ttu-id="ec70f-139">![Bildschirmfoto der lync PCD-Features für den Anmeldestatus](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Bildschirmfoto der lync PCD-Features für den Anmeldestatus")</span><span class="sxs-lookup"><span data-stu-id="ec70f-139">![Lync PCD features Sign in progress screen shot](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Lync PCD features Sign in progress screen shot")</span></span>

  - <span data-ttu-id="ec70f-140">Grafische Ansicht von Netzwerk Metriken – Netzwerk-MOS, Paketverlust und interarrival-Jitter im Vollbildmodus und angedockten Ansicht.</span><span class="sxs-lookup"><span data-stu-id="ec70f-140">Graphical view of network metrics – Network MOS, Packet Loss and Interarrival Jitter in full screen and snapped view.</span></span>

<span data-ttu-id="ec70f-141">**Vollbildansicht**</span><span class="sxs-lookup"><span data-stu-id="ec70f-141">**Full screen view**</span></span>

<span data-ttu-id="ec70f-142">![Testergebnis Diagramme für precall-Diagnosetools](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "Testergebnis Diagramme für precall-Diagnosetools")</span><span class="sxs-lookup"><span data-stu-id="ec70f-142">![PreCall Diagnostic Tool test result graphs](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "PreCall Diagnostic Tool test result graphs")</span></span>

<span data-ttu-id="ec70f-143">**Angedockte Ansicht**</span><span class="sxs-lookup"><span data-stu-id="ec70f-143">**Snapped view**</span></span>

<span data-ttu-id="ec70f-144">![Testergebnisse für die Nutzung des precall-Diagnosetools](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "Testergebnisse für die Nutzung des precall-Diagnosetools")</span><span class="sxs-lookup"><span data-stu-id="ec70f-144">![PreCall Diagnostic Tool Utilization test results](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "PreCall Diagnostic Tool Utilization test results")</span></span>

</div>

<span id="running"></span>

<div>

## <a name="running-lync-pcd"></a><span data-ttu-id="ec70f-145">Ausführen von lync PCD</span><span class="sxs-lookup"><span data-stu-id="ec70f-145">Running Lync PCD</span></span>

<div>

## <a name="running-windows-desktop-app"></a><span data-ttu-id="ec70f-146">Ausführen der Windows-Desktop-App</span><span class="sxs-lookup"><span data-stu-id="ec70f-146">Running Windows Desktop App</span></span>

1.  <span data-ttu-id="ec70f-147">Wenn Sie die PCD auf einem Windows 7-System starten möchten, wählen Sie im **Startmenü** die Option **precall Diagnostics** aus.</span><span class="sxs-lookup"><span data-stu-id="ec70f-147">To start the PCD on a Windows 7 system, select **PreCall Diagnostics** from the **Start** menu.</span></span>
    
    <span data-ttu-id="ec70f-148">Wenn Sie die PCD unter einem Windows 8-System starten möchten, wählen Sie das Symbol auf dem Startbildschirm aus, oder suchen Sie nach "Diagnose für Vorgespräche".</span><span class="sxs-lookup"><span data-stu-id="ec70f-148">To start the PCD on a Windows 8 system, select the icon on your Start screen, or search for “PreCall Diagnostics.”</span></span>
    
    <span data-ttu-id="ec70f-149">![Symbol für das precall-Diagnosetool](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "Symbol für das precall-Diagnosetool")</span><span class="sxs-lookup"><span data-stu-id="ec70f-149">![PreCall Diagnostic tool icon](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "PreCall Diagnostic tool icon")</span></span>

2.  <span data-ttu-id="ec70f-150">Wenn das Tool gestartet wird, wählen Sie die bevorzugte Methode zum Bereitstellen von Anmeldeinformationen aus, und wählen Sie im Dialogfeldoptionen für das Tool für die **voranruf-Diagnose** den Netzwerkmodus aus, und wählen Sie dann **OK**aus:</span><span class="sxs-lookup"><span data-stu-id="ec70f-150">When the tool starts, select your preferred method of providing credentials and select the network operating mode in the **PreCall Diagnostics Tool Options** dialog box, then select **OK**:</span></span>

3.  <span data-ttu-id="ec70f-151">Wählen Sie die Schaltfläche **Test starten** aus, um mit der Ausführung der Diagnose zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="ec70f-151">Select the **Start Test** button to start running diagnostics.</span></span>
    
    <span data-ttu-id="ec70f-152">Wenn Sie die Option **Netzwerkanmeldeinformationen verwenden** ausgewählt haben, wird der Test sofort gestartet.</span><span class="sxs-lookup"><span data-stu-id="ec70f-152">If you selected the **Use network credentials** option, the test begins immediately.</span></span>
    
    <span data-ttu-id="ec70f-153">Wenn Sie die Option **Ich möchte meine Anmeldeinformationen eingeben** aktiviert haben, wird das Dialogfeld **Windows-Sicherheit** geöffnet.</span><span class="sxs-lookup"><span data-stu-id="ec70f-153">If you selected the **Let me enter my credentials** option, the **Windows Security** dialog box opens.</span></span> <span data-ttu-id="ec70f-154">Nachdem Sie Ihre Anmeldeinformationen eingegeben haben, wird der Test gestartet.</span><span class="sxs-lookup"><span data-stu-id="ec70f-154">After you enter your credentials, the test starts.</span></span>

</div>

</div>

<span id="uninstall"></span>

<div>

## <a name="uninstalling-lync-pcd"></a><span data-ttu-id="ec70f-155">Deinstallieren von lync PCD</span><span class="sxs-lookup"><span data-stu-id="ec70f-155">Uninstalling Lync PCD</span></span>

<span data-ttu-id="ec70f-156">Um lync PCD zu entfernen, führen Sie das Verfahren für Ihr Betriebssystem aus:</span><span class="sxs-lookup"><span data-stu-id="ec70f-156">To remove Lync PCD, follow the procedure for your operating system:</span></span>

  - <span data-ttu-id="ec70f-157">Öffnen Sie auf einem Windows 7-System **die Systemsteuerung,** wählen Sie **Programme und Funktionen**aus, und doppelklicken Sie auf **lync 2013-Diagnose**.</span><span class="sxs-lookup"><span data-stu-id="ec70f-157">On a Windows 7 system, open the **Control Panel**, select **Programs and Features**, and double-click **Lync 2013 PreCall Diagnostics**.</span></span>

  - <span data-ttu-id="ec70f-158">Klicken Sie unter Windows 8 mit der rechten Maustaste auf die PCD-Kachel, und klicken Sie auf der APP-Leiste am unteren Rand des Startbildschirms auf **deinstallieren** .</span><span class="sxs-lookup"><span data-stu-id="ec70f-158">On a Windows 8 system, right-click on the PCD tile and click **Uninstall** from the app bar at the bottom of the start screen.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

