---
title: 'Lync Server 2013: Ausführen informeller VoIP-Routing Tests'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Run informal voice routing tests
ms:assetid: ea0e6059-bf04-4b03-b6d3-8f5534b731e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399049(v=OCS.15)
ms:contentKeyID: 48185904
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b47394f595926fe37df9a0809380ed96fa1dec66
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822300"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-informal-voice-routing-tests-in-lync-server-2013"></a><span data-ttu-id="afaf3-102">Ausführen informeller VoIP-Routing Tests in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="afaf3-102">Run informal voice routing tests in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="afaf3-103">_**Letztes Änderungsdatum des Themas:** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="afaf3-103">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="afaf3-104">Sie können das Dialogfeld **Informationen zum Erstellen von sprach Routing Testfällen** verwenden, um informelle Tests auszuführen, bevor Sie einen tatsächlichen Testfall erstellen.</span><span class="sxs-lookup"><span data-stu-id="afaf3-104">You can use the **Create voice routing test case information** dialog box to run informal tests before creating an actual test case.</span></span> <span data-ttu-id="afaf3-105">Wenn Sie mit dem Ergebnis eines Tests zufrieden sind, haben Sie die Möglichkeit, es als formalen Testfall zu speichern.</span><span class="sxs-lookup"><span data-stu-id="afaf3-105">When you are satisfied with the outcome of a test, you have the option of saving it as a formal test case.</span></span>

<div>

## <a name="to-run-an-informal-voice-routing-test"></a><span data-ttu-id="afaf3-106">So führen Sie einen informellen VoIP-Routing Test aus</span><span class="sxs-lookup"><span data-stu-id="afaf3-106">To run an informal voice routing test</span></span>

1.  <span data-ttu-id="afaf3-107">Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an.</span><span class="sxs-lookup"><span data-stu-id="afaf3-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="afaf3-108">Ausführliche Informationen finden Sie unter Delegieren von [Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="afaf3-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="afaf3-109">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="afaf3-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="afaf3-110">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="afaf3-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="afaf3-111">Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing**, und klicken Sie dann auf VoIP- **Routing testen**.</span><span class="sxs-lookup"><span data-stu-id="afaf3-111">In the left navigation bar, click **Voice Routing**, and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="afaf3-112">Klicken Sie auf der Seite **VoIP-Routing testen** auf VoIP-Weiterleitungs **testfallinformationen erstellen**.</span><span class="sxs-lookup"><span data-stu-id="afaf3-112">On the **Test Voice Routing** page, click **Create voice routing test case information**.</span></span>

5.  <span data-ttu-id="afaf3-113">Geben Sie im Feld **gewählte Nummer** die Telefonnummer ein, die Sie für diesen Test verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="afaf3-113">In the **Dialed number** field, type in the phone number you want to use for this test.</span></span> <span data-ttu-id="afaf3-114">Diese Nummer wird normalisiert und im Feld "normalisierte **Zahl** " des **Ergebnis** Bereichs angezeigt.</span><span class="sxs-lookup"><span data-stu-id="afaf3-114">This number will be normalized and displayed in the **Normalized number** field of the **Results** pane.</span></span>

6.  <span data-ttu-id="afaf3-115">Wählen Sie in der Liste **Wählplan** die Wähleinstellungen aus, die Sie zum Testen der gewählten Nummer verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="afaf3-115">In the **Dial plan** list, select the dial plan to use for testing the dialed number.</span></span> <span data-ttu-id="afaf3-116">Standardmäßig ist der globale Wählplan vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="afaf3-116">Default is the Global dial plan.</span></span>
    
    <span data-ttu-id="afaf3-117">Wenn Sie den Test ausführen, wird die erste Normalisierungsregel in diesem Wählplan, die der gewählten Nummer entspricht, im Feld normalisierungs **Regel** des **Ergebnis** Bereichs angezeigt.</span><span class="sxs-lookup"><span data-stu-id="afaf3-117">When you run the test, the first normalization rule in this dial plan that matches the dialed number will be displayed in the **Normalization rule** field of the **Results** pane.</span></span>

7.  <span data-ttu-id="afaf3-118">Wählen Sie in der Liste **VoIP-Richtlinie** die VoIP-Richtlinie aus, die Sie zum Testen der gewählten Nummer verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="afaf3-118">In the **Voice Policy** list, select the voice policy to use for testing the dialed number.</span></span> <span data-ttu-id="afaf3-119">Standard ist die globale VoIP-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="afaf3-119">Default is the Global voice policy.</span></span>
    
    <span data-ttu-id="afaf3-120">Wenn Sie den Test ausführen, wird der erste übereinstimmende PSTN-Verwendungs Eintrag in dieser VoIP-Richtlinie im ersten Feld für die **PSTN-Nutzung** des **Ergebnis** Bereichs angezeigt.</span><span class="sxs-lookup"><span data-stu-id="afaf3-120">When you run the test, the first matching PSTN usage record in this voice policy will be displayed in the **First PSTN usage** field of the **Results** pane.</span></span> <span data-ttu-id="afaf3-121">Außerdem wird die erste übereinstimmende VoIP-Route, die diesem PSTN-Verwendungsdaten Satz zugeordnet ist, im Feld **erste Route** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="afaf3-121">Also, the first matching voice route that is associated with this PSTN usage record will be displayed in the **First route** field.</span></span>

8.  <span data-ttu-id="afaf3-122">Optional Aktivieren Sie das Kontrollkästchen **vom Benutzer auffüllen** , wenn Sie die gewählte Nummer anhand der VoIP-Richtlinie testen möchten, die einem bestimmten Benutzer zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="afaf3-122">(Optional) Select the **Populate from user** check box if you want to test the dialed number against the voice policy assigned to a particular user.</span></span>
    
    1.  <span data-ttu-id="afaf3-123">Klicken Sie auf **Durchsuchen** , um das Dialogfeld **Enterprise-VoIP-Benutzer auswählen** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="afaf3-123">Click **Browse** to display the **Select Enterprise Voice Users** dialog box.</span></span>
    
    2.  <span data-ttu-id="afaf3-124">Klicken Sie auf **Suchen** , um die Liste der Benutzer anzuzeigen, die für Enterprise-VoIP aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="afaf3-124">Click **Find** to display the list of users who are enabled for Enterprise Voice.</span></span>
    
    3.  <span data-ttu-id="afaf3-125">Doppelklicken Sie auf den Benutzernamen, dessen zugewiesene VoIP-Richtlinie Sie für diesen Test verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="afaf3-125">Double-click the user name whose assigned voice policy you want to use for this test.</span></span> <span data-ttu-id="afaf3-126">Das Feld " **Richtlinie** " ist jetzt mit der VoIP-Richtlinie gefüllt, die dem ausgewählten Benutzer zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="afaf3-126">The **Policy** field is now populated with the voice policy assigned to the selected user.</span></span>
    
    <span data-ttu-id="afaf3-127">Wenn Sie den Test ausführen, wird der erste übereinstimmende Usage-Eintrag (Public Switched Telephone Network, PSTN) in dieser VoIP-Richtlinie im ersten Feld für die **PSTN-Nutzung** des **Ergebnis** Bereichs angezeigt.</span><span class="sxs-lookup"><span data-stu-id="afaf3-127">When you run the test, the first matching public switched telephone network (PSTN) usage record in this voice policy will be displayed in the **First PSTN usage** field of the **Results** pane.</span></span> <span data-ttu-id="afaf3-128">Außerdem wird die erste übereinstimmende VoIP-Route, die diesem PSTN-Verwendungsdaten Satz zugeordnet ist, im Feld **erste Route** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="afaf3-128">Also, the first matching voice route that is associated with this PSTN usage record will be displayed in the **First route** field.</span></span>

9.  <span data-ttu-id="afaf3-129">Klicken Sie auf **Ausführen** , um den Testfall auszuführen.</span><span class="sxs-lookup"><span data-stu-id="afaf3-129">Click **Run** to run the test case.</span></span> <span data-ttu-id="afaf3-130">Die Ergebnisse werden im rechten Fenster des Dialogfelds angezeigt.</span><span class="sxs-lookup"><span data-stu-id="afaf3-130">The results are shown in the right panel of the dialog box.</span></span>

10. <span data-ttu-id="afaf3-131">Optional Klicken Sie auf **Speichern** unter, wenn Sie diese Testkonfiguration als formalen Testfall speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="afaf3-131">(Optional) Click **Save as** if you want to save this test configuration as a formal test case.</span></span>
    
    1.  <span data-ttu-id="afaf3-132">Geben Sie im Feld **Name** des Dialogfelds **VoIP-Routing Test Case-Informationen speichern** einen eindeutigen Namen für den Testfall ein.</span><span class="sxs-lookup"><span data-stu-id="afaf3-132">In the **Name** field of the **Save Voice Routing Test Case Information** dialog box, type a unique name for the test case.</span></span>
        
        <span data-ttu-id="afaf3-133">Der Name muss bei allen Sprach Routing-Testfälle in Ihrer Enterprise-VoIP-Bereitstellung eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="afaf3-133">The name must be unique among all voice routing test cases in your Enterprise Voice deployment.</span></span> <span data-ttu-id="afaf3-134">Es kann bis zu 32 Zeichen lang sein und kann neben dem umgekehrten Schrägstrich (\\), Punkt (.) oder Unterstrich (\_) auch beliebige alphanumerische Zeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="afaf3-134">It can be up to 32 characters in length and may contain any alphanumeric characters, in addition to the backslash (\\), period (.), or underscore (\_).</span></span>
    
    2.  <span data-ttu-id="afaf3-135">Beachten Sie, dass die verbleibenden Felder im Dialogfeld **sprach Routing-Testfall-Informationen speichern** schreibgeschützt sind und aus der informellen Testkonfiguration *und* den Ergebnissen ausgefüllt werden.</span><span class="sxs-lookup"><span data-stu-id="afaf3-135">Note that the remaining fields on the **Save Voice Routing Test Case Information** dialog box are read-only, and are prepopulated from the informal test configuration *and* results.</span></span> <span data-ttu-id="afaf3-136">Überprüfen Sie, ob es sich um die Konfiguration handelt, die Sie für den Testfall speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="afaf3-136">Verify that this is the configuration that you want to save for the test case.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="afaf3-137">Die Werte aus den Testergebnissen werden verwendet, um die Felder im Dialogfeld <STRONG>VoIP-Routing Test Case-Informationen speichern</STRONG> wie folgt zu füllen:</span><span class="sxs-lookup"><span data-stu-id="afaf3-137">Values from the test results are used to prepopulate fields on the <STRONG>Save Voice Routing Test Case Information</STRONG> dialog box as follows:</span></span> 
        > <UL>
        > <LI>
        > <P><span data-ttu-id="afaf3-138">Die <STRONG>erwartete Übersetzung</STRONG> wird mit dem Wert im Feld <STRONG>normalisierte Zahl</STRONG> vorab ausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="afaf3-138"><STRONG>Expected translation</STRONG> is prepopulated with the value in the <STRONG>Normalized number</STRONG> field.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="afaf3-139">Die <STRONG>erwartete Route</STRONG> wird mit dem Wert im <STRONG>ersten Routen</STRONG> Feld ausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="afaf3-139"><STRONG>Expected route</STRONG> is prepopulated with the value in the <STRONG>First route</STRONG> field.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="afaf3-140"><STRONG>Voraussichtlicher PSTN-Verwendungsdaten Satz</STRONG> wird mit dem Wert im <STRONG>ersten PSTN-Nutzungs</STRONG> Feld vorab ausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="afaf3-140"><STRONG>Expected PSTN usage record</STRONG> is prepopulated with the value in the <STRONG>First PSTN usage</STRONG> field.</span></span></P></LI></UL><span data-ttu-id="afaf3-141">Wenn Übereinstimmungen für einen dieser Werte während des Testlaufs nicht gefunden wurden, ist das entsprechende Feld im Dialogfeld <STRONG>Informationen zum Speichern von sprach Routing Testfällen</STRONG> leer.</span><span class="sxs-lookup"><span data-stu-id="afaf3-141">If matches for any of these values were not found during the test run, the corresponding field is empty on the <STRONG>Save Voice Routing Test Case Information</STRONG> dialog box.</span></span>

        
        </div>
    
    3.  <span data-ttu-id="afaf3-142">Klicken Sie auf **OK** , um den Testfall zu speichern, oder klicken Sie auf **Abbrechen** , um zurückzukehren, um zum Dialogfeld **sprach Routing Test Case-Informationen anzeigen** zu wechseln, um den Test weiter zu entwickeln, bevor Sie ihn speichern.</span><span class="sxs-lookup"><span data-stu-id="afaf3-142">Click **Ok** to save the test case, or click **Cancel** to return to return to the **View voice routing test case information** dialog box to further develop the test before saving it.</span></span>

11. <span data-ttu-id="afaf3-143">Klicken Sie auf **Commit ausführen** und anschließend auf **Commit für alle Elemente ausführen**.</span><span class="sxs-lookup"><span data-stu-id="afaf3-143">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="afaf3-144">Wenn Sie einen Test Case für VoIP-Routing erstellen, müssen Sie den Befehl <STRONG>Commit all</STRONG> ausführen, um den Testfall zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="afaf3-144">Whenever you create a voice routing test case, you must run the <STRONG>Commit all</STRONG> command to publish the test case.</span></span> <span data-ttu-id="afaf3-145">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</A> in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="afaf3-145">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="afaf3-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="afaf3-146">See Also</span></span>


[<span data-ttu-id="afaf3-147">Erstellen eines Testfalls für das VoIP-Routing in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="afaf3-147">Create a voice routing test case in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-routing-test-case.md)  
[<span data-ttu-id="afaf3-148">Ausführen von Testfällen für das VoIP-Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="afaf3-148">Run voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-run-voice-routing-test-cases.md)  
[<span data-ttu-id="afaf3-149">Exportieren von Testfällen für das VoIP-Routing in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="afaf3-149">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)  
[<span data-ttu-id="afaf3-150">Importieren von Testfällen für das VoIP-Routing in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="afaf3-150">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)  


[<span data-ttu-id="afaf3-151">Konfigurieren von Wählplänen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="afaf3-151">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)  
[<span data-ttu-id="afaf3-152">Konfigurieren von VoIP-Richtlinien, PSTN-Verwendungsdatensätzen und VoIP-Routen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="afaf3-152">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

