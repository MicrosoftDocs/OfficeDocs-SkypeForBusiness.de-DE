---
title: 'Lync Server 2013: Erstellen eines Testfalls für das VoIP-Routing'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a voice routing test case
ms:assetid: 43a07a5b-2f20-462a-81e5-d628c18391e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425935(v=OCS.15)
ms:contentKeyID: 48183979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c706064cbe7319d3cb485b0bb1ecf6d34902edde
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726345"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-voice-routing-test-case-in-lync-server-2013"></a><span data-ttu-id="9f751-102">Erstellen eines Testfalls für das VoIP-Routing in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f751-102">Create a voice routing test case in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f751-103">_**Letztes Änderungsdatum des Themas:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="9f751-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<div>

## <a name="to-create-a-test-case"></a><span data-ttu-id="9f751-104">So erstellen Sie einen Test Case</span><span class="sxs-lookup"><span data-stu-id="9f751-104">To create a test case</span></span>

1.  <span data-ttu-id="9f751-105">Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an.</span><span class="sxs-lookup"><span data-stu-id="9f751-105">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="9f751-106">Ausführliche Informationen finden Sie unter [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="9f751-106">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="9f751-107">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="9f751-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9f751-108">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9f751-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9f751-109">Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** , und klicken Sie dann auf VoIP- **Routing testen**.</span><span class="sxs-lookup"><span data-stu-id="9f751-109">In the left navigation bar, click **Voice Routing** and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="9f751-110">Klicken Sie auf der Seite **VoIP-Routing testen** auf **neu** , um einen neuen Testfall zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9f751-110">On the **Test Voice Routing** page, click **New** to create a new test case.</span></span>

5.  <span data-ttu-id="9f751-111">Geben Sie im Feld **Name**einen eindeutigen Namen für den Testfall ein.</span><span class="sxs-lookup"><span data-stu-id="9f751-111">In **Name**, type in a unique name for the test case.</span></span>
    
    <span data-ttu-id="9f751-112">Der Name muss bei allen Sprach Routing-Testfälle in Ihrer Enterprise-VoIP-Bereitstellung eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="9f751-112">The name must be unique among all voice routing test cases in your Enterprise Voice deployment.</span></span> <span data-ttu-id="9f751-113">Es kann bis zu 32 Zeichen lang sein und kann neben dem umgekehrten Schrägstrich (\\), Punkt (.) oder Unterstrich (\_) auch beliebige alphanumerische Zeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="9f751-113">It can be up to 32 characters in length and may contain any alphanumeric characters, in addition to the backslash (\\), period (.), or underscore (\_).</span></span>

6.  <span data-ttu-id="9f751-114">Geben Sie in **zu testende Nummer**die gewählte Nummer ein, die Sie zum Testen der Routingkonfiguration verwenden möchten, die Sie für diesen Testfall angeben.</span><span class="sxs-lookup"><span data-stu-id="9f751-114">In **Dialed number to test**, type in the dialed number that you want to use to test the routing configuration that you specify for this test case.</span></span> <span data-ttu-id="9f751-115">Basierend auf den Wähleinstellungen, der Route und der VoIP-Richtlinie wird diese Nummer normalisiert und als Ausgabe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9f751-115">Based on the dial plan, route, and voice policy, this number will be normalized and displayed as output.</span></span>

7.  <span data-ttu-id="9f751-116">Wählen Sie in der Liste **Wählplan** die Wähleinstellungen aus, die Sie beim Ausführen des Tests verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="9f751-116">In the **Dial Plan** list, select the dial plan to use when running the test.</span></span> <span data-ttu-id="9f751-117">Standardmäßig ist der globale Wählplan vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="9f751-117">Default is the Global dial plan.</span></span>

8.  <span data-ttu-id="9f751-118">Wählen Sie in der Liste **VoIP-Richtlinie** die VoIP-Richtlinie aus, die Sie beim Ausführen des Tests verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="9f751-118">In the **Voice Policy** list, select the voice policy to use when running the test.</span></span> <span data-ttu-id="9f751-119">Standard ist die globale VoIP-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="9f751-119">Default is the Global voice policy.</span></span>

9.  <span data-ttu-id="9f751-120">Geben Sie in **erwartete Übersetzung**die Telefonnummer in das Format ein, das Sie nach der Übersetzung erwarten.</span><span class="sxs-lookup"><span data-stu-id="9f751-120">In **Expected translation**, type in the phone number in the format you expect to see it after translation.</span></span> <span data-ttu-id="9f751-121">Hierbei handelt es sich um den Wert der Telefonnummer, die Sie testen, nachdem Sie von der ersten Normalisierungsregel, die im ausgewählten Wählplan übereinstimmt, übersetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="9f751-121">This is the value of the phone number that you are testing after it has been translated by the first normalization rule that matches in the selected dial plan.</span></span> <span data-ttu-id="9f751-122">Wenn Sie den Testfall ausführen, schlägt der Test fehl, wenn die von Ihnen getestete Zahl nicht zu dem Wert in der **erwarteten Übersetzung**führt.</span><span class="sxs-lookup"><span data-stu-id="9f751-122">When you run the test case, if the number you are testing does not result in the value in **Expected translation**, the test fails.</span></span>

10. <span data-ttu-id="9f751-123">Optional In der Liste **Erwarteter PSTN-Verbrauch** können Sie den PSTN-Verwendungsdaten Satz (Public Switched Telephone Network) auswählen, der auf der Grundlage der angegebenen Wähleinstellungen und VoIP-Richtlinie verwendet werden soll, wenn Sie den Testfall ausführen.</span><span class="sxs-lookup"><span data-stu-id="9f751-123">(Optional) In the **Expected PSTN usage** list, you can select the public switched telephone network (PSTN) usage record that you expect to be used when you run the test case, based on the specified dial plan and voice policy.</span></span> <span data-ttu-id="9f751-124">Wenn ein anderer PSTN-Verwendungsdaten Satz verwendet wird, schlägt der Test fehl.</span><span class="sxs-lookup"><span data-stu-id="9f751-124">If a different PSTN usage record is used, the test fails.</span></span>

11. <span data-ttu-id="9f751-125">Optional In der Liste **erwartete Route** können Sie die VoIP-Route auswählen, die Sie bei der Ausführung des Testfalls erwarten, basierend auf den angegebenen Wähleinstellungen und VoIP-Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="9f751-125">(Optional) In the **Expected route** list, you can select the voice route that you expect to be used when you run the test case, based on the specified dial plan and voice policy.</span></span> <span data-ttu-id="9f751-126">Wenn eine andere VoIP-Route verwendet wird, schlägt der Test fehl.</span><span class="sxs-lookup"><span data-stu-id="9f751-126">If a different voice route is used, the test fails.</span></span>

12. <span data-ttu-id="9f751-127">Optional Klicken Sie auf **Ausführen** , um den Testfall auszuführen.</span><span class="sxs-lookup"><span data-stu-id="9f751-127">(Optional) Click **Run** to run the test case.</span></span> <span data-ttu-id="9f751-128">Die Ergebnisse werden im rechten Panel der Seite angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9f751-128">The results are shown in the right panel of the page.</span></span>

13. <span data-ttu-id="9f751-129">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="9f751-129">Click **OK**.</span></span>

14. <span data-ttu-id="9f751-130">Klicken Sie auf **Commit ausführen** und anschließend auf **Commit für alle Elemente ausführen**.</span><span class="sxs-lookup"><span data-stu-id="9f751-130">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9f751-131">Wenn Sie einen Test Case für VoIP-Routing erstellen, müssen Sie den Befehl <STRONG>alle</STRONG> übernehmen ausführen, um die Konfigurationsänderung zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="9f751-131">Whenever you create a voice routing test case, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="9f751-132">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</A> in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="9f751-132">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="9f751-133">Wenn der Wählplan, der im Test verwendet wird, Telefonnummern normalisiert, die mit einem Pluszeichen beginnen (beispielsweise + 12065551219), kann dieser Plan dazu führen, dass der VoIP-Routing Test fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="9f751-133">If the dial plan being employed in the test normalizes phone numbers that begin with a plus sign (for example, +12065551219), that plan might cause the voice routing test to fail.</span></span> <span data-ttu-id="9f751-134">(Die Wähleinstellungen und die VoIP-Route funktionieren; in der Tat ist Test-CsDialPlan erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="9f751-134">(The dial plan and the voice route will work; in fact, Test-CsDialPlan will succeed.</span></span> <span data-ttu-id="9f751-135">Der sprach Routing Test schlägt jedoch möglicherweise fehl.) Dies ist etwas, das Sie beim Testen von VoIP-Routen beachten sollten.</span><span class="sxs-lookup"><span data-stu-id="9f751-135">However, the voice routing test might fail.) This is something to keep in mind when testing voice routes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9f751-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9f751-136">See Also</span></span>


[<span data-ttu-id="9f751-137">Exportieren von Testfällen für das VoIP-Routing in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f751-137">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)  
[<span data-ttu-id="9f751-138">Importieren von Testfällen für das VoIP-Routing in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f751-138">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)  


[<span data-ttu-id="9f751-139">Konfigurieren von Wählplänen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f751-139">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)  
[<span data-ttu-id="9f751-140">Konfigurieren von VoIP-Richtlinien, PSTN-Verwendungsdatensätzen und VoIP-Routen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f751-140">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

