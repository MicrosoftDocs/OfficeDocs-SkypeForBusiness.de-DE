---
title: 'Lync Server 2013: Ausführen von Testfällen für das VoIP-Routing'
description: 'Lync Server 2013: führen Sie Test Fälle für das VoIP-Routing aus.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Run voice routing test cases
ms:assetid: fb4d32df-b9ea-4944-8cd7-a6102c78c465
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413068(v=OCS.15)
ms:contentKeyID: 48185948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e521216a12fba6b78913e7f4a79432809bb6e252
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566791"
---
# <a name="run-voice-routing-test-cases-in-lync-server-2013"></a><span data-ttu-id="c5da5-103">Ausführen von Testfällen für das VoIP-Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5da5-103">Run voice routing test cases in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5da5-104">_**Letztes Änderungsstand des Themas:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="c5da5-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="c5da5-105">Sie können alle Testfälle in ihrer Testfall-Suite für das VoIP-Routing ausführen, oder Sie können einen oder mehrere ausgewählte Test Cases ausführen.</span><span class="sxs-lookup"><span data-stu-id="c5da5-105">You can run all of the test cases in your voice routing test case suite, or you can run one or more selected test cases.</span></span>

<div>

## <a name="to-run-all-voice-routing-test-cases"></a><span data-ttu-id="c5da5-106">So führen Sie alle Test Fälle für das VoIP-Routing aus</span><span class="sxs-lookup"><span data-stu-id="c5da5-106">To run all voice routing test cases</span></span>

1.  <span data-ttu-id="c5da5-107">Melden Sie sich am Computer als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied der CsVoiceAdministrator-, CsServerAdministrator-oder CsAdministrator-Rolle an.</span><span class="sxs-lookup"><span data-stu-id="c5da5-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="c5da5-108">Ausführliche Informationen finden Sie unter [Delegate Setup Permissions in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="c5da5-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="c5da5-109">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="c5da5-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c5da5-110">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c5da5-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c5da5-111">Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **VoIP-Routing testen**.</span><span class="sxs-lookup"><span data-stu-id="c5da5-111">In the left navigation bar, click **Voice Routing** and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="c5da5-112">Klicken Sie auf der Seite **VoIP-Routing testen** auf **Aktion** , und klicken Sie dann auf **alle ausführen**.</span><span class="sxs-lookup"><span data-stu-id="c5da5-112">On the **Test Voice Routing** page, click **Action** and then click **Run all**.</span></span>
    
    <span data-ttu-id="c5da5-113">Der Status "Pass" oder "Fehler" jedes Testfalls wird in der Spalte " **Pass/Fehler** " angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c5da5-113">The pass or fail status of each test case is shown in the **Pass/fail** column.</span></span> <span data-ttu-id="c5da5-114">Wenn ein Testfall noch nicht ausgeführt wurde, wird N/a in der Spalte **Pass/Fail** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c5da5-114">If a test case has not yet been run, N/A is shown in the **Pass/fail** column.</span></span>

5.  <span data-ttu-id="c5da5-115">Optional Wenn Sie detaillierte Ergebnisse für jeden Testfall anzeigen möchten, doppelklicken Sie auf den Namen des Test Falls.</span><span class="sxs-lookup"><span data-stu-id="c5da5-115">(Optional) To see detailed results for each test case, double-click the test case name.</span></span> <span data-ttu-id="c5da5-116">Die Ergebnisse werden im schattierten Bereich auf der rechten Seite der Seite **Testfall bearbeiten** angezeigt:</span><span class="sxs-lookup"><span data-stu-id="c5da5-116">Results are shown in the shaded area on the right side of the **Edit Test Case** page:</span></span>
    
    1.  <span data-ttu-id="c5da5-117">**Test Ergebnis:** Der Gesamtstatus der Pass-oder Fehlerzustände der Test Fall Ausführung.</span><span class="sxs-lookup"><span data-stu-id="c5da5-117">**Test result:** Overall pass or fail status of the test case run.</span></span>
    
    2.  <span data-ttu-id="c5da5-118">**Normalisierungsregel:** Die erste Normalisierungsregel in den Wähleinstellungen, die für diesen Testfall ausgewählt wurde, der mit der gewählten Nummer übereinstimmt (der Wert im Feld **zu testende Zahl** ).</span><span class="sxs-lookup"><span data-stu-id="c5da5-118">**Normalization rule:** The first normalization rule in the dial plan selected for this test case that matches the dialed number (the value in the **Number to test** field).</span></span>
    
    3.  <span data-ttu-id="c5da5-119">**Normalisierte Zahl:** Der Wert der gewählten Nummer, nachdem die Normalisierungsregel übersetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="c5da5-119">**Normalized number:** The value of the dialed number after the normalization rule has translated it.</span></span>
    
    4.  <span data-ttu-id="c5da5-120">**Erste PSTN-Verwendung:** Der erste PSTN-Verwendungsdaten Satz (Public Switched Telephone Network) in der VoIP-Richtlinie, der für diesen Testfall ausgewählt wurde, der mit der gewählten Nummer übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="c5da5-120">**First PSTN usage:** The first public switched telephone network (PSTN) usage record in the voice policy selected for this test case that matches the dialed number.</span></span>
    
    5.  <span data-ttu-id="c5da5-121">**Erste Route:** Die erste VoIP-Route im ersten PSTN-Verwendungsdaten Satz, der mit der gewählten Nummer übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="c5da5-121">**First route:** The first voice route in the first PSTN usage record that matches the dialed number.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="c5da5-122">Der <STRONG>erwartete PSTN-Verwendungsdaten Satz</STRONG> und die <STRONG>erwarteten Routen</STRONG> Felder sind in der Konfiguration für das VoIP-Routing Test Case optional.</span><span class="sxs-lookup"><span data-stu-id="c5da5-122">The <STRONG>Expected PSTN usage record</STRONG> and <STRONG>Expected route</STRONG> fields are optional in voice routing test case configuration.</span></span> <span data-ttu-id="c5da5-123">Wenn der Testfall diese Werte nicht angibt, ist das entsprechende Feld in den Testergebnissen leer.</span><span class="sxs-lookup"><span data-stu-id="c5da5-123">If the test case does not specify these values, the corresponding field in the test results will be empty.</span></span>

        
        </div>

</div>

<div>

## <a name="to-run-one-or-more-selected-voice-routing-test-cases"></a><span data-ttu-id="c5da5-124">So führen Sie ein oder mehrere ausgewählte VoIP-Routing Testfälle aus</span><span class="sxs-lookup"><span data-stu-id="c5da5-124">To run one or more selected voice routing test cases</span></span>

1.  <span data-ttu-id="c5da5-125">Melden Sie sich am Computer als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied der CsVoiceAdministrator-, CsServerAdministrator-oder CsAdministrator-Rolle an.</span><span class="sxs-lookup"><span data-stu-id="c5da5-125">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="c5da5-126">Ausführliche Informationen finden Sie unter [Delegate Setup Permissions in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="c5da5-126">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="c5da5-127">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="c5da5-127">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c5da5-128">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c5da5-128">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c5da5-129">Klicken Sie auf der linken Navigationsleiste auf **VoIP-Routing** und dann auf **VoIP-Routing testen**.</span><span class="sxs-lookup"><span data-stu-id="c5da5-129">In the left navigation bar, click **Voice Routing**, and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="c5da5-130">Klicken Sie auf der Seite **VoIP-Routing testen** auf die Namen der Test Fälle, die Sie ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="c5da5-130">On the **Test Voice Routing** page, click the names of the test cases that you want to run.</span></span>

5.  <span data-ttu-id="c5da5-131">Klicken Sie im Menü **Aktion** auf **ausgewählt ausführen**.</span><span class="sxs-lookup"><span data-stu-id="c5da5-131">On the **Action** menu, click **Run selected**.</span></span>
    
    <span data-ttu-id="c5da5-132">Der Status "Pass" oder "Fehler" jedes Testfalls wird in der Spalte " **Pass/Fehler** " angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c5da5-132">The pass or fail status of each test case is shown in the **Pass/fail** column.</span></span> <span data-ttu-id="c5da5-133">Wenn ein Testfall noch nicht ausgeführt wurde, wird N/a in der Spalte **Pass/Fail** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c5da5-133">If a test case has not yet been run, N/A is shown in the **Pass/fail** column.</span></span>

6.  <span data-ttu-id="c5da5-134">Optional Wenn Sie detaillierte Ergebnisse für jeden Testfall anzeigen möchten, doppelklicken Sie auf den Namen des Test Falls.</span><span class="sxs-lookup"><span data-stu-id="c5da5-134">(Optional) To see detailed results for each test case, double-click the test case name.</span></span> <span data-ttu-id="c5da5-135">Die Ergebnisse werden im schattierten Bereich auf der rechten Seite der Seite **Testfall bearbeiten** angezeigt:</span><span class="sxs-lookup"><span data-stu-id="c5da5-135">Results are shown in the shaded area on the right side of the **Edit Test Case** page:</span></span>
    
    1.  <span data-ttu-id="c5da5-136">**Test Ergebnis:** Der Gesamtstatus der Pass-oder Fehlerzustände der Test Fall Ausführung.</span><span class="sxs-lookup"><span data-stu-id="c5da5-136">**Test result:** Overall pass or fail status of the test case run.</span></span>
    
    2.  <span data-ttu-id="c5da5-137">**Normalisierungsregel:** Die erste Normalisierungsregel in den Wähleinstellungen, die für diesen Testfall ausgewählt wurde, der mit der gewählten Nummer übereinstimmt (der Wert im Feld **zu testende Zahl** ).</span><span class="sxs-lookup"><span data-stu-id="c5da5-137">**Normalization rule:** The first normalization rule in the dial plan selected for this test case that matches the dialed number (the value in the **Number to test** field).</span></span>
    
    3.  <span data-ttu-id="c5da5-138">**Normalisierte Zahl:** Der Wert der gewählten Nummer, nachdem die Normalisierungsregel übersetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="c5da5-138">**Normalized number:** The value of the dialed number after the normalization rule has translated it.</span></span>
    
    4.  <span data-ttu-id="c5da5-139">**Erste PSTN-Verwendung:** Der erste PSTN-Verwendungsdaten Satz in der VoIP-Richtlinie, der für diesen Testfall ausgewählt wurde, der mit der gewählten Nummer übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="c5da5-139">**First PSTN usage:** The first PSTN usage record in the voice policy selected for this test case that matches the dialed number.</span></span>
    
    5.  <span data-ttu-id="c5da5-140">**Erste Route:** Die erste VoIP-Route im ersten PSTN-Verwendungsdaten Satz, der mit der gewählten Nummer übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="c5da5-140">**First route:** The first voice route in the first PSTN usage record that matches the dialed number.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="c5da5-141">Der <STRONG>erwartete PSTN-Verwendungsdaten Satz</STRONG> und die <STRONG>erwarteten Routen</STRONG> Felder sind in der Konfiguration für das VoIP-Routing Test Case optional.</span><span class="sxs-lookup"><span data-stu-id="c5da5-141">The <STRONG>Expected PSTN usage record</STRONG> and <STRONG>Expected route</STRONG> fields are optional in voice routing test case configuration.</span></span> <span data-ttu-id="c5da5-142">Wenn der Testfall diese Werte nicht angibt, ist das entsprechende Feld in den Testergebnissen leer.</span><span class="sxs-lookup"><span data-stu-id="c5da5-142">If the test case does not specify these values, the corresponding field in the test results will be empty.</span></span>

        
        </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c5da5-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c5da5-143">See Also</span></span>


[<span data-ttu-id="c5da5-144">Testen des VoIP-Routings in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5da5-144">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
[<span data-ttu-id="c5da5-145">Durchführen von Tests für das VoIP-Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5da5-145">Running voice routing tests in Lync Server 2013</span></span>](lync-server-2013-running-voice-routing-tests.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

