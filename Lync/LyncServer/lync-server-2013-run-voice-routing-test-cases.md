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
ms.openlocfilehash: 14f2df8a04c5efbf8c62bc4e17bbdd156913daae
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732835"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-voice-routing-test-cases-in-lync-server-2013"></a><span data-ttu-id="611d6-102">Ausführen von Testfällen für das VoIP-Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="611d6-102">Run voice routing test cases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="611d6-103">_**Letztes Änderungsdatum des Themas:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="611d6-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="611d6-104">Sie können alle Testfälle in Ihrer Suite für den sprach Routing Test ausführen, oder Sie können einen oder mehrere ausgewählte Test Cases ausführen.</span><span class="sxs-lookup"><span data-stu-id="611d6-104">You can run all of the test cases in your voice routing test case suite, or you can run one or more selected test cases.</span></span>

<div>

## <a name="to-run-all-voice-routing-test-cases"></a><span data-ttu-id="611d6-105">So führen Sie alle Test Cases für VoIP-Routing aus</span><span class="sxs-lookup"><span data-stu-id="611d6-105">To run all voice routing test cases</span></span>

1.  <span data-ttu-id="611d6-106">Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an.</span><span class="sxs-lookup"><span data-stu-id="611d6-106">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="611d6-107">Ausführliche Informationen finden Sie unter [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="611d6-107">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="611d6-108">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="611d6-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="611d6-109">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="611d6-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="611d6-110">Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** , und klicken Sie dann auf VoIP- **Routing testen**.</span><span class="sxs-lookup"><span data-stu-id="611d6-110">In the left navigation bar, click **Voice Routing** and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="611d6-111">Klicken Sie auf der Seite **VoIP-Routing testen** auf **Aktion** und dann auf **alle ausführen**.</span><span class="sxs-lookup"><span data-stu-id="611d6-111">On the **Test Voice Routing** page, click **Action** and then click **Run all**.</span></span>
    
    <span data-ttu-id="611d6-112">Der Pass-oder Fehlerstatus jedes Testfalls wird in der Spalte **Pass/Fehler** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="611d6-112">The pass or fail status of each test case is shown in the **Pass/fail** column.</span></span> <span data-ttu-id="611d6-113">Wenn ein Testfall noch nicht ausgeführt wurde, wird N/a in der Spalte **Durchlauf/Fehler** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="611d6-113">If a test case has not yet been run, N/A is shown in the **Pass/fail** column.</span></span>

5.  <span data-ttu-id="611d6-114">Optional Wenn Sie detaillierte Ergebnisse für jeden Testfall anzeigen möchten, doppelklicken Sie auf den Namen des Testfalls.</span><span class="sxs-lookup"><span data-stu-id="611d6-114">(Optional) To see detailed results for each test case, double-click the test case name.</span></span> <span data-ttu-id="611d6-115">Die Ergebnisse werden im schattierten Bereich auf der rechten Seite der Seite **Testfall bearbeiten** angezeigt:</span><span class="sxs-lookup"><span data-stu-id="611d6-115">Results are shown in the shaded area on the right side of the **Edit Test Case** page:</span></span>
    
    1.  <span data-ttu-id="611d6-116">**Test Ergebnis:** Gesamtdurchlauf-oder Fehlerstatus des Test Fall Laufs</span><span class="sxs-lookup"><span data-stu-id="611d6-116">**Test result:** Overall pass or fail status of the test case run.</span></span>
    
    2.  <span data-ttu-id="611d6-117">**Normalisierungsregel:** Die erste Normalisierungsregel im Wählplan, die für diesen Testfall ausgewählt wurde, der der gewählten Nummer entspricht (dem Wert im Feld " **zu testende Zahl** ").</span><span class="sxs-lookup"><span data-stu-id="611d6-117">**Normalization rule:** The first normalization rule in the dial plan selected for this test case that matches the dialed number (the value in the **Number to test** field).</span></span>
    
    3.  <span data-ttu-id="611d6-118">**Normalisierte Zahl:** Der Wert der gewählten Nummer, nachdem Sie von der Normalisierungsregel übersetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="611d6-118">**Normalized number:** The value of the dialed number after the normalization rule has translated it.</span></span>
    
    4.  <span data-ttu-id="611d6-119">**Erste PSTN-Nutzung:** Der erste PSTN-Nutzungs Eintrag (Public Switched Telephone Network) in der VoIP-Richtlinie, der für diesen Testfall ausgewählt wurde, der der gewählten Nummer entspricht.</span><span class="sxs-lookup"><span data-stu-id="611d6-119">**First PSTN usage:** The first public switched telephone network (PSTN) usage record in the voice policy selected for this test case that matches the dialed number.</span></span>
    
    5.  <span data-ttu-id="611d6-120">**Erste Route:** Die erste VoIP-Route im ersten PSTN-Verwendungsdaten Satz, die der gewählten Nummer entspricht.</span><span class="sxs-lookup"><span data-stu-id="611d6-120">**First route:** The first voice route in the first PSTN usage record that matches the dialed number.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="611d6-121">Der <STRONG>erwartete PSTN-Nutzungsdaten Satz</STRONG> und die <STRONG>erwarteten Route</STRONG> -Felder sind in der Konfiguration des Testfalles für sprach Routing optional.</span><span class="sxs-lookup"><span data-stu-id="611d6-121">The <STRONG>Expected PSTN usage record</STRONG> and <STRONG>Expected route</STRONG> fields are optional in voice routing test case configuration.</span></span> <span data-ttu-id="611d6-122">Wenn der Testfall diese Werte nicht angibt, ist das entsprechende Feld in den Testergebnissen leer.</span><span class="sxs-lookup"><span data-stu-id="611d6-122">If the test case does not specify these values, the corresponding field in the test results will be empty.</span></span>

        
        </div>

</div>

<div>

## <a name="to-run-one-or-more-selected-voice-routing-test-cases"></a><span data-ttu-id="611d6-123">So führen Sie einen oder mehrere ausgewählte VoIP-Test Cases aus</span><span class="sxs-lookup"><span data-stu-id="611d6-123">To run one or more selected voice routing test cases</span></span>

1.  <span data-ttu-id="611d6-124">Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an.</span><span class="sxs-lookup"><span data-stu-id="611d6-124">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="611d6-125">Ausführliche Informationen finden Sie unter [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="611d6-125">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="611d6-126">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="611d6-126">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="611d6-127">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="611d6-127">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="611d6-128">Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing**, und klicken Sie dann auf VoIP- **Routing testen**.</span><span class="sxs-lookup"><span data-stu-id="611d6-128">In the left navigation bar, click **Voice Routing**, and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="611d6-129">Klicken Sie auf der Seite **VoIP-Routing testen** auf die Namen der Testfälle, die Sie ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="611d6-129">On the **Test Voice Routing** page, click the names of the test cases that you want to run.</span></span>

5.  <span data-ttu-id="611d6-130">Klicken Sie im Menü **Aktion** auf **ausgewählte ausführen**.</span><span class="sxs-lookup"><span data-stu-id="611d6-130">On the **Action** menu, click **Run selected**.</span></span>
    
    <span data-ttu-id="611d6-131">Der Pass-oder Fehlerstatus jedes Testfalls wird in der Spalte **Pass/Fehler** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="611d6-131">The pass or fail status of each test case is shown in the **Pass/fail** column.</span></span> <span data-ttu-id="611d6-132">Wenn ein Testfall noch nicht ausgeführt wurde, wird N/a in der Spalte **Durchlauf/Fehler** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="611d6-132">If a test case has not yet been run, N/A is shown in the **Pass/fail** column.</span></span>

6.  <span data-ttu-id="611d6-133">Optional Wenn Sie detaillierte Ergebnisse für jeden Testfall anzeigen möchten, doppelklicken Sie auf den Namen des Testfalls.</span><span class="sxs-lookup"><span data-stu-id="611d6-133">(Optional) To see detailed results for each test case, double-click the test case name.</span></span> <span data-ttu-id="611d6-134">Die Ergebnisse werden im schattierten Bereich auf der rechten Seite der Seite **Testfall bearbeiten** angezeigt:</span><span class="sxs-lookup"><span data-stu-id="611d6-134">Results are shown in the shaded area on the right side of the **Edit Test Case** page:</span></span>
    
    1.  <span data-ttu-id="611d6-135">**Test Ergebnis:** Gesamtdurchlauf-oder Fehlerstatus des Test Fall Laufs</span><span class="sxs-lookup"><span data-stu-id="611d6-135">**Test result:** Overall pass or fail status of the test case run.</span></span>
    
    2.  <span data-ttu-id="611d6-136">**Normalisierungsregel:** Die erste Normalisierungsregel im Wählplan, die für diesen Testfall ausgewählt wurde, der der gewählten Nummer entspricht (dem Wert im Feld " **zu testende Zahl** ").</span><span class="sxs-lookup"><span data-stu-id="611d6-136">**Normalization rule:** The first normalization rule in the dial plan selected for this test case that matches the dialed number (the value in the **Number to test** field).</span></span>
    
    3.  <span data-ttu-id="611d6-137">**Normalisierte Zahl:** Der Wert der gewählten Nummer, nachdem Sie von der Normalisierungsregel übersetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="611d6-137">**Normalized number:** The value of the dialed number after the normalization rule has translated it.</span></span>
    
    4.  <span data-ttu-id="611d6-138">**Erste PSTN-Nutzung:** Der erste PSTN-Verwendungs Eintrag in der VoIP-Richtlinie, der für diesen Testfall ausgewählt wurde, der der gewählten Nummer entspricht.</span><span class="sxs-lookup"><span data-stu-id="611d6-138">**First PSTN usage:** The first PSTN usage record in the voice policy selected for this test case that matches the dialed number.</span></span>
    
    5.  <span data-ttu-id="611d6-139">**Erste Route:** Die erste VoIP-Route im ersten PSTN-Verwendungsdaten Satz, die der gewählten Nummer entspricht.</span><span class="sxs-lookup"><span data-stu-id="611d6-139">**First route:** The first voice route in the first PSTN usage record that matches the dialed number.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="611d6-140">Der <STRONG>erwartete PSTN-Nutzungsdaten Satz</STRONG> und die <STRONG>erwarteten Route</STRONG> -Felder sind in der Konfiguration des Testfalles für sprach Routing optional.</span><span class="sxs-lookup"><span data-stu-id="611d6-140">The <STRONG>Expected PSTN usage record</STRONG> and <STRONG>Expected route</STRONG> fields are optional in voice routing test case configuration.</span></span> <span data-ttu-id="611d6-141">Wenn der Testfall diese Werte nicht angibt, ist das entsprechende Feld in den Testergebnissen leer.</span><span class="sxs-lookup"><span data-stu-id="611d6-141">If the test case does not specify these values, the corresponding field in the test results will be empty.</span></span>

        
        </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="611d6-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="611d6-142">See Also</span></span>


[<span data-ttu-id="611d6-143">Testen des VoIP-Routings in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="611d6-143">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
[<span data-ttu-id="611d6-144">Ausführen von Tests für das VoIP-Routing in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="611d6-144">Running voice routing tests in Lync Server 2013</span></span>](lync-server-2013-running-voice-routing-tests.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

