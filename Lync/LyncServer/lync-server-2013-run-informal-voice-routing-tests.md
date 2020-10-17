---
title: 'Lync Server 2013: Ausführen von Tests für informelles VoIP-Routing'
description: 'Lync Server 2013: führen Sie informelle VoIP-Routing Tests aus.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Run informal voice routing tests
ms:assetid: ea0e6059-bf04-4b03-b6d3-8f5534b731e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399049(v=OCS.15)
ms:contentKeyID: 48185904
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6029be34f4e4e7b366cb73f56ca611b4773331fd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545031"
---
# <a name="run-informal-voice-routing-tests-in-lync-server-2013"></a><span data-ttu-id="7f8d4-103">Ausführen von informellen VoIP-Routing Tests in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f8d4-103">Run informal voice routing tests in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f8d4-104">_**Letztes Änderungsstand des Themas:** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="7f8d4-104">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="7f8d4-p101">Sie können mit dem Dialogfeld **Testfallinformationen für das VoIP-Routing erstellen** interne Tests ausführen, bevor Sie einen tatsächlichen Testfall erstellen. Wenn Sie mit dem Ergebnis eines Tests zufrieden sind, können Sie den Test als formalen Testfall speichern.</span><span class="sxs-lookup"><span data-stu-id="7f8d4-p101">You can use the **Create voice routing test case information** dialog box to run informal tests before creating an actual test case. When you are satisfied with the outcome of a test, you have the option of saving it as a formal test case.</span></span>

<div>

## <a name="to-run-an-informal-voice-routing-test"></a><span data-ttu-id="7f8d4-107">So führen Sie einen informellen Test für das VoIP-Routing aus</span><span class="sxs-lookup"><span data-stu-id="7f8d4-107">To run an informal voice routing test</span></span>

1.  <span data-ttu-id="7f8d4-108">Melden Sie sich am Computer als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied der CsVoiceAdministrator-, CsServerAdministrator-oder CsAdministrator-Rolle an.</span><span class="sxs-lookup"><span data-stu-id="7f8d4-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="7f8d4-109">Ausführliche Informationen finden Sie unter [Delegate Setup Permissions in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="7f8d4-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="7f8d4-110">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="7f8d4-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7f8d4-111">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7f8d4-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7f8d4-112">Klicken Sie auf der linken Navigationsleiste auf **VoIP-Routing** und dann auf **VoIP-Routing testen**.</span><span class="sxs-lookup"><span data-stu-id="7f8d4-112">In the left navigation bar, click **Voice Routing**, and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="7f8d4-113">Klicken Sie auf der Seite **VoIP-Routing testen** auf **Testfallinformationen für das VoIP-Routing erstellen**.</span><span class="sxs-lookup"><span data-stu-id="7f8d4-113">On the **Test Voice Routing** page, click **Create voice routing test case information**.</span></span>

5.  <span data-ttu-id="7f8d4-p104">Geben Sie im Feld **Gewählte Nummer** die Telefonnummer ein, die Sie für diesen Test verwenden möchten. Diese Nummer wird normalisiert und im Feld **Normalisierte Nummer** des Ergebnisbereichs\*\*\*\* angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7f8d4-p104">In the **Dialed number** field, type in the phone number you want to use for this test. This number will be normalized and displayed in the **Normalized number** field of the **Results** pane.</span></span>

6.  <span data-ttu-id="7f8d4-p105">Wählen Sie in der Liste **Wähleinstellungen** den Satz mit Wähleinstellungen, der zum Testen der gewählten Nummer verwendet werden soll. Standardeinstellung ist der globale Satz mit Wähleinstellungen.</span><span class="sxs-lookup"><span data-stu-id="7f8d4-p105">In the **Dial plan** list, select the dial plan to use for testing the dialed number. Default is the Global dial plan.</span></span>
    
    <span data-ttu-id="7f8d4-118">Wenn Sie den Test ausführen, wird die erste Normalisierungsregel in diesen Wähleinstellungen, die mit der gewählten Nummer übereinstimmt, im Feld **Normalisierungsregel** des Ergebnisbereichs\*\*\*\* angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7f8d4-118">When you run the test, the first normalization rule in this dial plan that matches the dialed number will be displayed in the **Normalization rule** field of the **Results** pane.</span></span>

7.  <span data-ttu-id="7f8d4-p106">Wählen Sie in der Liste **VoIP-Richtlinie** die VoIP-Richtlinie aus, die zum Testen der gewählten Nummer verwendet werden soll. Standardeinstellung ist die globale VoIP-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="7f8d4-p106">In the **Voice Policy** list, select the voice policy to use for testing the dialed number. Default is the Global voice policy.</span></span>
    
    <span data-ttu-id="7f8d4-p107">Wenn Sie den Test ausführen, wird der erste übereinstimmende PSTN-Verwendungsdatensatz in dieser VoIP-Richtlinie im Feld **Erste PSTN-Verwendung** des Ergebnisbereichs angezeigt\*\*\*\*. Außerdem wird die erste übereinstimmende VoIP-Route, die diesem PSTN-Verwendungsdatensatz zugeordnet ist, im Feld **Erste Route** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7f8d4-p107">When you run the test, the first matching PSTN usage record in this voice policy will be displayed in the **First PSTN usage** field of the **Results** pane. Also, the first matching voice route that is associated with this PSTN usage record will be displayed in the **First route** field.</span></span>

8.  <span data-ttu-id="7f8d4-123">(Optional) Aktivieren Sie das Kontrollkästchen **Aus Benutzer auffüllen**, wenn Sie die gewählte Nummer für eine VoIP-Richtlinie testen möchten, die einem bestimmten Benutzer zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="7f8d4-123">(Optional) Select the **Populate from user** check box if you want to test the dialed number against the voice policy assigned to a particular user.</span></span>
    
    1.  <span data-ttu-id="7f8d4-124">Klicken Sie auf **Durchsuchen**, um das Dialogfeld **Enterprise-VoIP-Benutzer auswählen** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="7f8d4-124">Click **Browse** to display the **Select Enterprise Voice Users** dialog box.</span></span>
    
    2.  <span data-ttu-id="7f8d4-125">Klicken Sie auf **Suchen**, um die Liste der Benutzer anzuzeigen, die für Enterprise-VoIP aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="7f8d4-125">Click **Find** to display the list of users who are enabled for Enterprise Voice.</span></span>
    
    3.  <span data-ttu-id="7f8d4-p108">Doppelklicken Sie auf den Benutzernamen, dessen zugewiesene VoIP-Richtlinie Sie für diesen Test verwenden möchten. Das Feld **Richtlinie** wird jetzt mit der VoIP-Richtlinie gefüllt, die dem ausgewählten Benutzer zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="7f8d4-p108">Double-click the user name whose assigned voice policy you want to use for this test. The **Policy** field is now populated with the voice policy assigned to the selected user.</span></span>
    
    <span data-ttu-id="7f8d4-p109">Wenn Sie den Test ausführen, wird der erste übereinstimmende PSTN-Verwendungsdatensatz in dieser VoIP-Richtlinie im Feld **Erste PSTN-Verwendung** des Ergebnisbereichs angezeigt\*\*\*\*. Außerdem wird die erste übereinstimmende VoIP-Route, die diesem PSTN-Verwendungsdatensatz zugeordnet ist, im Feld **Erste Route** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7f8d4-p109">When you run the test, the first matching public switched telephone network (PSTN) usage record in this voice policy will be displayed in the **First PSTN usage** field of the **Results** pane. Also, the first matching voice route that is associated with this PSTN usage record will be displayed in the **First route** field.</span></span>

9.  <span data-ttu-id="7f8d4-p110">Klicken Sie auf **Ausführen**, um den Testfall auszuführen. Die Ergebnisse werden im rechten Bereich des Dialogfelds angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7f8d4-p110">Click **Run** to run the test case. The results are shown in the right panel of the dialog box.</span></span>

10. <span data-ttu-id="7f8d4-132">(Optional) Klicken Sie auf **Speichern unter**, wenn Sie diese Testkonfiguration als formalen Testfall speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="7f8d4-132">(Optional) Click **Save as** if you want to save this test configuration as a formal test case.</span></span>
    
    1.  <span data-ttu-id="7f8d4-133">Geben Sie im Feld **Name** des Dialogfelds **Testfallinformationen für das VoIP-Routing speichern** einen eindeutigen Namen für den Testfall ein.</span><span class="sxs-lookup"><span data-stu-id="7f8d4-133">In the **Name** field of the **Save Voice Routing Test Case Information** dialog box, type a unique name for the test case.</span></span>
        
        <span data-ttu-id="7f8d4-134">Der Name muss bei allen VoIP-Routing Testfälle in Ihrer Enterprise-VoIP-Bereitstellung eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="7f8d4-134">The name must be unique among all voice routing test cases in your Enterprise Voice deployment.</span></span> <span data-ttu-id="7f8d4-135">Es kann bis zu 32 Zeichen lang sein und kann neben dem umgekehrten Schrägstrich ( \\ ), Punkt (.) oder Unterstrich () auch beliebige alphanumerische Zeichen enthalten \_ .</span><span class="sxs-lookup"><span data-stu-id="7f8d4-135">It can be up to 32 characters in length and may contain any alphanumeric characters, in addition to the backslash (\\), period (.), or underscore (\_).</span></span>
    
    2.  <span data-ttu-id="7f8d4-p112">Beachten Sie, dass die verbleibenden Felder im Dialogfeld **Testfallinformationen für das VoIP-Routing speichern** schreibgeschützt sind und mit den Daten *und* Ergebnissen aus der informellen Testkonfiguration vorausgefüllt werden. Stellen Sie sicher, dass dies die Konfiguration ist, die Sie für den Testfall speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="7f8d4-p112">Note that the remaining fields on the **Save Voice Routing Test Case Information** dialog box are read-only, and are prepopulated from the informal test configuration *and* results. Verify that this is the configuration that you want to save for the test case.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="7f8d4-138">Die Werte aus den Testergebnissen werden folgendermaßen zum Vorausfüllen der Felder im Dialogfeld <STRONG>Testfallinformationen für das VoIP-Routing speichern</STRONG> verwendet:</span><span class="sxs-lookup"><span data-stu-id="7f8d4-138">Values from the test results are used to prepopulate fields on the <STRONG>Save Voice Routing Test Case Information</STRONG> dialog box as follows:</span></span> 
        > <UL>
        > <LI>
        > <P><span data-ttu-id="7f8d4-139"><STRONG>Erwartete Übersetzung</STRONG> wird mit dem Wert im Feld <STRONG>Normalisierte Nummer</STRONG> vorausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="7f8d4-139"><STRONG>Expected translation</STRONG> is prepopulated with the value in the <STRONG>Normalized number</STRONG> field.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="7f8d4-140"><STRONG>Erwartete Route</STRONG> wird mit dem Wert im Feld <STRONG>Erste Route</STRONG> vorausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="7f8d4-140"><STRONG>Expected route</STRONG> is prepopulated with the value in the <STRONG>First route</STRONG> field.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="7f8d4-141"><STRONG>Erwarteter PSTN-Verwendungsdatensatz</STRONG> wird mit dem Wert im Feld <STRONG>Erste PSTN-Verwendung</STRONG> vorausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="7f8d4-141"><STRONG>Expected PSTN usage record</STRONG> is prepopulated with the value in the <STRONG>First PSTN usage</STRONG> field.</span></span></P></LI></UL><span data-ttu-id="7f8d4-p113">Wenn für einen dieser Werte beim Test keine Übereinstimmungen gefunden werden, bleibt das entsprechende Feld im Dialogfeld <STRONG>Testfallinformationen für das VoIP-Routing speichern</STRONG> leer.</span><span class="sxs-lookup"><span data-stu-id="7f8d4-p113">If matches for any of these values were not found during the test run, the corresponding field is empty on the <STRONG>Save Voice Routing Test Case Information</STRONG> dialog box.   </span></span></div>
    
    3.  <span data-ttu-id="7f8d4-143">Klicken Sie auf **OK**, um den Testfall zu speichern, oder klicken Sie auf **Abbrechen**, um zum Dialogfeld **Testfallinformationen für das VoIP-Routing anzeigen** zurückzukehren und weitere Änderungen vorzunehmen, bevor Sie den Test speichern.</span><span class="sxs-lookup"><span data-stu-id="7f8d4-143">Click **Ok** to save the test case, or click **Cancel** to return to return to the **View voice routing test case information** dialog box to further develop the test before saving it.</span></span>

11. <span data-ttu-id="7f8d4-144">Klicken Sie auf **Commit** und anschließend auf **Commit für alle**.</span><span class="sxs-lookup"><span data-stu-id="7f8d4-144">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7f8d4-145">Jedes Mal, wenn Sie einen Testfall für das VoIP-Routing erstellen, müssen Sie den Befehl <STRONG>Commit für alle</STRONG> ausführen, um den Testfall zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="7f8d4-145">Whenever you create a voice routing test case, you must run the <STRONG>Commit all</STRONG> command to publish the test case.</span></span> <span data-ttu-id="7f8d4-146">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</A> in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="7f8d4-146">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7f8d4-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7f8d4-147">See Also</span></span>


[<span data-ttu-id="7f8d4-148">Erstellen eines Testfalls für das VoIP-Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f8d4-148">Create a voice routing test case in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-routing-test-case.md)  
[<span data-ttu-id="7f8d4-149">Ausführen von Testfällen für das VoIP-Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f8d4-149">Run voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-run-voice-routing-test-cases.md)  
[<span data-ttu-id="7f8d4-150">Exportieren von Testfällen für das VoIP-Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f8d4-150">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)  
[<span data-ttu-id="7f8d4-151">Importieren von Testfällen für das VoIP-Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f8d4-151">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)  


[<span data-ttu-id="7f8d4-152">Konfigurieren von Wählplänen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f8d4-152">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)  
[<span data-ttu-id="7f8d4-153">Konfigurieren von VoIP-Richtlinien, PSTN-Verwendungsdatensätzen und VoIP-Routen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f8d4-153">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

