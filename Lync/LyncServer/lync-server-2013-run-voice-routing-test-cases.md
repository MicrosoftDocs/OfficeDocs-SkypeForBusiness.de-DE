---
title: 'Lync Server 2013: Ausführen von Testfällen für das VoIP-Routing'
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
ms.openlocfilehash: 0b13ed9c5f9f4e42216877f7d117f5659425848b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182808"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="run-voice-routing-test-cases-in-lync-server-2013"></a><span data-ttu-id="30753-102">Ausführen von Testfällen für das VoIP-Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="30753-102">Run voice routing test cases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30753-103">_**Letztes Änderungsstand des Themas:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="30753-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="30753-104">Sie können alle Testfälle in ihrer Testfall-Suite für das VoIP-Routing ausführen, oder Sie können einen oder mehrere ausgewählte Test Cases ausführen.</span><span class="sxs-lookup"><span data-stu-id="30753-104">You can run all of the test cases in your voice routing test case suite, or you can run one or more selected test cases.</span></span>

<div>

## <a name="to-run-all-voice-routing-test-cases"></a><span data-ttu-id="30753-105">So führen Sie alle Test Fälle für das VoIP-Routing aus</span><span class="sxs-lookup"><span data-stu-id="30753-105">To run all voice routing test cases</span></span>

1.  <span data-ttu-id="30753-106">Melden Sie sich am Computer als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied der CsVoiceAdministrator-, CsServerAdministrator-oder CsAdministrator-Rolle an.</span><span class="sxs-lookup"><span data-stu-id="30753-106">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="30753-107">Ausführliche Informationen finden Sie unter [Delegate Setup Permissions in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="30753-107">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="30753-108">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="30753-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="30753-109">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="30753-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="30753-110">Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **VoIP-Routing testen**.</span><span class="sxs-lookup"><span data-stu-id="30753-110">In the left navigation bar, click **Voice Routing** and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="30753-111">Klicken Sie auf der Seite **VoIP-Routing testen** auf **Aktion** , und klicken Sie dann auf **alle ausführen**.</span><span class="sxs-lookup"><span data-stu-id="30753-111">On the **Test Voice Routing** page, click **Action** and then click **Run all**.</span></span>
    
    <span data-ttu-id="30753-112">Der Status "Pass" oder "Fehler" jedes Testfalls wird in der Spalte " **Pass/Fehler** " angezeigt.</span><span class="sxs-lookup"><span data-stu-id="30753-112">The pass or fail status of each test case is shown in the **Pass/fail** column.</span></span> <span data-ttu-id="30753-113">Wenn ein Testfall noch nicht ausgeführt wurde, wird N/a in der Spalte **Pass/Fail** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="30753-113">If a test case has not yet been run, N/A is shown in the **Pass/fail** column.</span></span>

5.  <span data-ttu-id="30753-114">Optional Wenn Sie detaillierte Ergebnisse für jeden Testfall anzeigen möchten, doppelklicken Sie auf den Namen des Test Falls.</span><span class="sxs-lookup"><span data-stu-id="30753-114">(Optional) To see detailed results for each test case, double-click the test case name.</span></span> <span data-ttu-id="30753-115">Die Ergebnisse werden im schattierten Bereich auf der rechten Seite der Seite **Testfall bearbeiten** angezeigt:</span><span class="sxs-lookup"><span data-stu-id="30753-115">Results are shown in the shaded area on the right side of the **Edit Test Case** page:</span></span>
    
    1.  <span data-ttu-id="30753-116">**Test Ergebnis:** Der Gesamtstatus der Pass-oder Fehlerzustände der Test Fall Ausführung.</span><span class="sxs-lookup"><span data-stu-id="30753-116">**Test result:** Overall pass or fail status of the test case run.</span></span>
    
    2.  <span data-ttu-id="30753-117">**Normalisierungsregel:** Die erste Normalisierungsregel in den Wähleinstellungen, die für diesen Testfall ausgewählt wurde, der mit der gewählten Nummer übereinstimmt (der Wert im Feld **zu testende Zahl** ).</span><span class="sxs-lookup"><span data-stu-id="30753-117">**Normalization rule:** The first normalization rule in the dial plan selected for this test case that matches the dialed number (the value in the **Number to test** field).</span></span>
    
    3.  <span data-ttu-id="30753-118">**Normalisierte Zahl:** Der Wert der gewählten Nummer, nachdem die Normalisierungsregel übersetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="30753-118">**Normalized number:** The value of the dialed number after the normalization rule has translated it.</span></span>
    
    4.  <span data-ttu-id="30753-119">**Erste PSTN-Verwendung:** Der erste PSTN-Verwendungsdaten Satz (Public Switched Telephone Network) in der VoIP-Richtlinie, der für diesen Testfall ausgewählt wurde, der mit der gewählten Nummer übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="30753-119">**First PSTN usage:** The first public switched telephone network (PSTN) usage record in the voice policy selected for this test case that matches the dialed number.</span></span>
    
    5.  <span data-ttu-id="30753-120">**Erste Route:** Die erste VoIP-Route im ersten PSTN-Verwendungsdaten Satz, der mit der gewählten Nummer übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="30753-120">**First route:** The first voice route in the first PSTN usage record that matches the dialed number.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="30753-121">Der <STRONG>erwartete PSTN-Verwendungsdaten Satz</STRONG> und die <STRONG>erwarteten Routen</STRONG> Felder sind in der Konfiguration für das VoIP-Routing Test Case optional.</span><span class="sxs-lookup"><span data-stu-id="30753-121">The <STRONG>Expected PSTN usage record</STRONG> and <STRONG>Expected route</STRONG> fields are optional in voice routing test case configuration.</span></span> <span data-ttu-id="30753-122">Wenn der Testfall diese Werte nicht angibt, ist das entsprechende Feld in den Testergebnissen leer.</span><span class="sxs-lookup"><span data-stu-id="30753-122">If the test case does not specify these values, the corresponding field in the test results will be empty.</span></span>

        
        </div>

</div>

<div>

## <a name="to-run-one-or-more-selected-voice-routing-test-cases"></a><span data-ttu-id="30753-123">So führen Sie ein oder mehrere ausgewählte VoIP-Routing Testfälle aus</span><span class="sxs-lookup"><span data-stu-id="30753-123">To run one or more selected voice routing test cases</span></span>

1.  <span data-ttu-id="30753-124">Melden Sie sich am Computer als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied der CsVoiceAdministrator-, CsServerAdministrator-oder CsAdministrator-Rolle an.</span><span class="sxs-lookup"><span data-stu-id="30753-124">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="30753-125">Ausführliche Informationen finden Sie unter [Delegate Setup Permissions in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="30753-125">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="30753-126">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="30753-126">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="30753-127">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="30753-127">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="30753-128">Klicken Sie auf der linken Navigationsleiste auf **VoIP-Routing** und dann auf **VoIP-Routing testen**.</span><span class="sxs-lookup"><span data-stu-id="30753-128">In the left navigation bar, click **Voice Routing**, and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="30753-129">Klicken Sie auf der Seite **VoIP-Routing testen** auf die Namen der Test Fälle, die Sie ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="30753-129">On the **Test Voice Routing** page, click the names of the test cases that you want to run.</span></span>

5.  <span data-ttu-id="30753-130">Klicken Sie im Menü **Aktion** auf **ausgewählt ausführen**.</span><span class="sxs-lookup"><span data-stu-id="30753-130">On the **Action** menu, click **Run selected**.</span></span>
    
    <span data-ttu-id="30753-131">Der Status "Pass" oder "Fehler" jedes Testfalls wird in der Spalte " **Pass/Fehler** " angezeigt.</span><span class="sxs-lookup"><span data-stu-id="30753-131">The pass or fail status of each test case is shown in the **Pass/fail** column.</span></span> <span data-ttu-id="30753-132">Wenn ein Testfall noch nicht ausgeführt wurde, wird N/a in der Spalte **Pass/Fail** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="30753-132">If a test case has not yet been run, N/A is shown in the **Pass/fail** column.</span></span>

6.  <span data-ttu-id="30753-133">Optional Wenn Sie detaillierte Ergebnisse für jeden Testfall anzeigen möchten, doppelklicken Sie auf den Namen des Test Falls.</span><span class="sxs-lookup"><span data-stu-id="30753-133">(Optional) To see detailed results for each test case, double-click the test case name.</span></span> <span data-ttu-id="30753-134">Die Ergebnisse werden im schattierten Bereich auf der rechten Seite der Seite **Testfall bearbeiten** angezeigt:</span><span class="sxs-lookup"><span data-stu-id="30753-134">Results are shown in the shaded area on the right side of the **Edit Test Case** page:</span></span>
    
    1.  <span data-ttu-id="30753-135">**Test Ergebnis:** Der Gesamtstatus der Pass-oder Fehlerzustände der Test Fall Ausführung.</span><span class="sxs-lookup"><span data-stu-id="30753-135">**Test result:** Overall pass or fail status of the test case run.</span></span>
    
    2.  <span data-ttu-id="30753-136">**Normalisierungsregel:** Die erste Normalisierungsregel in den Wähleinstellungen, die für diesen Testfall ausgewählt wurde, der mit der gewählten Nummer übereinstimmt (der Wert im Feld **zu testende Zahl** ).</span><span class="sxs-lookup"><span data-stu-id="30753-136">**Normalization rule:** The first normalization rule in the dial plan selected for this test case that matches the dialed number (the value in the **Number to test** field).</span></span>
    
    3.  <span data-ttu-id="30753-137">**Normalisierte Zahl:** Der Wert der gewählten Nummer, nachdem die Normalisierungsregel übersetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="30753-137">**Normalized number:** The value of the dialed number after the normalization rule has translated it.</span></span>
    
    4.  <span data-ttu-id="30753-138">**Erste PSTN-Verwendung:** Der erste PSTN-Verwendungsdaten Satz in der VoIP-Richtlinie, der für diesen Testfall ausgewählt wurde, der mit der gewählten Nummer übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="30753-138">**First PSTN usage:** The first PSTN usage record in the voice policy selected for this test case that matches the dialed number.</span></span>
    
    5.  <span data-ttu-id="30753-139">**Erste Route:** Die erste VoIP-Route im ersten PSTN-Verwendungsdaten Satz, der mit der gewählten Nummer übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="30753-139">**First route:** The first voice route in the first PSTN usage record that matches the dialed number.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="30753-140">Der <STRONG>erwartete PSTN-Verwendungsdaten Satz</STRONG> und die <STRONG>erwarteten Routen</STRONG> Felder sind in der Konfiguration für das VoIP-Routing Test Case optional.</span><span class="sxs-lookup"><span data-stu-id="30753-140">The <STRONG>Expected PSTN usage record</STRONG> and <STRONG>Expected route</STRONG> fields are optional in voice routing test case configuration.</span></span> <span data-ttu-id="30753-141">Wenn der Testfall diese Werte nicht angibt, ist das entsprechende Feld in den Testergebnissen leer.</span><span class="sxs-lookup"><span data-stu-id="30753-141">If the test case does not specify these values, the corresponding field in the test results will be empty.</span></span>

        
        </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="30753-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="30753-142">See Also</span></span>


[<span data-ttu-id="30753-143">Testen des VoIP-Routings in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="30753-143">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
[<span data-ttu-id="30753-144">Durchführen von Tests für das VoIP-Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="30753-144">Running voice routing tests in Lync Server 2013</span></span>](lync-server-2013-running-voice-routing-tests.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

