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
ms.openlocfilehash: b9fac6f65d1bb1c04b8d8597454df775f8545d2a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205751"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-voice-routing-test-case-in-lync-server-2013"></a><span data-ttu-id="33feb-102">Erstellen eines Testfalls für das VoIP-Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33feb-102">Create a voice routing test case in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33feb-103">_**Letztes Änderungsstand des Themas:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="33feb-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<div>

## <a name="to-create-a-test-case"></a><span data-ttu-id="33feb-104">So erstellen Sie einen Testfall</span><span class="sxs-lookup"><span data-stu-id="33feb-104">To create a test case</span></span>

1.  <span data-ttu-id="33feb-105">Melden Sie sich am Computer als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied der CsVoiceAdministrator-, CsServerAdministrator-oder CsAdministrator-Rolle an.</span><span class="sxs-lookup"><span data-stu-id="33feb-105">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="33feb-106">Ausführliche Informationen finden Sie unter [Delegate Setup Permissions in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="33feb-106">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="33feb-107">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="33feb-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="33feb-108">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="33feb-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="33feb-109">Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **VoIP-Routing testen**.</span><span class="sxs-lookup"><span data-stu-id="33feb-109">In the left navigation bar, click **Voice Routing** and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="33feb-110">Klicken Sie auf der Seite **VoIP-Routing testen** auf **Neu**, um einen neuen Testfall zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="33feb-110">On the **Test Voice Routing** page, click **New** to create a new test case.</span></span>

5.  <span data-ttu-id="33feb-111">Geben Sie unter **Name** einen eindeutigen Namen für den Testfall ein.</span><span class="sxs-lookup"><span data-stu-id="33feb-111">In **Name**, type in a unique name for the test case.</span></span>
    
    <span data-ttu-id="33feb-112">Der Name muss bei allen VoIP-Routing Testfälle in Ihrer Enterprise-VoIP-Bereitstellung eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="33feb-112">The name must be unique among all voice routing test cases in your Enterprise Voice deployment.</span></span> <span data-ttu-id="33feb-113">Es kann bis zu 32 Zeichen lang sein und kann neben dem umgekehrten Schrägstrich (\\), Punkt (.) oder Unterstrich (\_) auch beliebige alphanumerische Zeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="33feb-113">It can be up to 32 characters in length and may contain any alphanumeric characters, in addition to the backslash (\\), period (.), or underscore (\_).</span></span>

6.  <span data-ttu-id="33feb-p104">Geben Sie unter **Zu testende gewählte Rufnummer** die gewählte Rufnummer ein, die Sie zum Testen der für diesen Testfall angegebenen Routingkonfiguration verwenden möchten. Basierend auf dem Satz mit Wähleinstellungen, der Route und der VoIP-Richtlinie wird diese Nummer normalisiert und als Ausgabe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="33feb-p104">In **Dialed number to test**, type in the dialed number that you want to use to test the routing configuration that you specify for this test case. Based on the dial plan, route, and voice policy, this number will be normalized and displayed as output.</span></span>

7.  <span data-ttu-id="33feb-p105">Wählen Sie in der Liste **Wähleinstellungen** den Satz mit Wähleinstellungen aus, der bei Ausführung des Tests verwendet werden soll. Standardeinstellung ist der globale Satz mit Wähleinstellungen.</span><span class="sxs-lookup"><span data-stu-id="33feb-p105">In the **Dial Plan** list, select the dial plan to use when running the test. Default is the Global dial plan.</span></span>

8.  <span data-ttu-id="33feb-p106">Wählen Sie in der Liste **VoIP-Richtlinie** die VoIP-Richtlinie aus, die bei Ausführung des Tests verwendet werden soll. Standardeinstellung ist die globale VoIP-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="33feb-p106">In the **Voice Policy** list, select the voice policy to use when running the test. Default is the Global voice policy.</span></span>

9.  <span data-ttu-id="33feb-p107">Geben Sie unter **Erwartete Übersetzung** die Telefonnummer in dem Format ein, in dem sie nach der Übersetzung vorliegen soll. Hierbei handelt es sich um den Wert der getesteten Telefonnummer, nachdem diese durch die erste den Kriterien entsprechende Normalisierungsregel in den ausgewählten Wähleinstellungen übersetzt wurde. Wenn die getestete Nummer bei Ausführung des Testfalls nicht den Wert in **Erwartete Übersetzung** ergibt, ist der Test nicht erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="33feb-p107">In **Expected translation**, type in the phone number in the format you expect to see it after translation. This is the value of the phone number that you are testing after it has been translated by the first normalization rule that matches in the selected dial plan. When you run the test case, if the number you are testing does not result in the value in **Expected translation**, the test fails.</span></span>

10. <span data-ttu-id="33feb-p108">(Optional) In der Liste **Erwartete PSTN-Verwendung** können Sie basierend auf den ausgewählten Wähleinstellungen und der VoIP-Richtlinie den PSTN-Verwendungsdatensatz (Public Switched Telephone Network, Telefonfestnetz) auswählen, der beim Ausführen des Testfalls verwendet werden soll. Wird ein anderer PSTN-Verwendungsdatensatz verwendet, ist der Test nicht erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="33feb-p108">(Optional) In the **Expected PSTN usage** list, you can select the public switched telephone network (PSTN) usage record that you expect to be used when you run the test case, based on the specified dial plan and voice policy. If a different PSTN usage record is used, the test fails.</span></span>

11. <span data-ttu-id="33feb-p109">(Optional) In der Liste **Erwartete Route** können Sie basierend auf den ausgewählten Wähleinstellungen und der VoIP-Richtlinie die VoIP-Route auswählen, die beim Ausführen des Testfalls verwendet werden soll. Wird eine andere VoIP-Route verwendet, ist der Test nicht erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="33feb-p109">(Optional) In the **Expected route** list, you can select the voice route that you expect to be used when you run the test case, based on the specified dial plan and voice policy. If a different voice route is used, the test fails.</span></span>

12. <span data-ttu-id="33feb-p110">(Optional) Klicken Sie auf **Ausführen**, um den Testfall auszuführen. Die Ergebnisse werden im rechten Seitenbereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="33feb-p110">(Optional) Click **Run** to run the test case. The results are shown in the right panel of the page.</span></span>

13. <span data-ttu-id="33feb-129">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="33feb-129">Click **OK**.</span></span>

14. <span data-ttu-id="33feb-130">Klicken Sie auf **Commit** und anschließend auf **Commit für alle**.</span><span class="sxs-lookup"><span data-stu-id="33feb-130">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="33feb-131">Jedes Mal, wenn Sie einen Testplan für das VoIP-Routing erstellen, müssen Sie den Befehl <STRONG>Commit für alle</STRONG> ausführen, um die Konfigurationsänderung zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="33feb-131">Whenever you create a voice routing test case, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="33feb-132">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</A> in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="33feb-132">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="33feb-133">Wenn der im Test verwendete Wählplan die Telefonnummern normalisiert, die mit einem Pluszeichen beginnen (beispielsweise + 12065551219), kann dieser Plan dazu führen, dass der VoIP-Routing Test fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="33feb-133">If the dial plan being employed in the test normalizes phone numbers that begin with a plus sign (for example, +12065551219), that plan might cause the voice routing test to fail.</span></span> <span data-ttu-id="33feb-134">(Die Wähleinstellungen und die VoIP-Route funktionieren; tatsächlich ist Test-CsDialPlan erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="33feb-134">(The dial plan and the voice route will work; in fact, Test-CsDialPlan will succeed.</span></span> <span data-ttu-id="33feb-135">Der VoIP-Routing Test schlägt jedoch möglicherweise fehl.) Dies sollten Sie beim Testen von VoIP-Routen beachten.</span><span class="sxs-lookup"><span data-stu-id="33feb-135">However, the voice routing test might fail.) This is something to keep in mind when testing voice routes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="33feb-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="33feb-136">See Also</span></span>


[<span data-ttu-id="33feb-137">Exportieren von Testfällen für das VoIP-Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33feb-137">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)  
[<span data-ttu-id="33feb-138">Importieren von Testfällen für das VoIP-Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33feb-138">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)  


[<span data-ttu-id="33feb-139">Konfigurieren von Wählplänen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33feb-139">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)  
[<span data-ttu-id="33feb-140">Konfigurieren von VoIP-Richtlinien, PSTN-Verwendungsdatensätzen und VoIP-Routen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33feb-140">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

