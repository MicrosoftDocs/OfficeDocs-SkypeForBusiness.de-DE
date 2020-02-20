---
title: 'Lync Server 2013: Erstellen von Wähleinstellungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a dial plan
ms:assetid: d2fef3d0-7e78-4591-b712-d62ac71d71a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398909(v=OCS.15)
ms:contentKeyID: 48185424
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3166352556925034d6b947600af99a10570b6933
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154487"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-dial-plan-in-lync-server-2013"></a><span data-ttu-id="77ebb-102">Erstellen von Wähleinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77ebb-102">Create a dial plan in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77ebb-103">_**Letztes Änderungsstand des Themas:** 2013-10-24_</span><span class="sxs-lookup"><span data-stu-id="77ebb-103">_**Topic Last Modified:** 2013-10-24_</span></span>

<span data-ttu-id="77ebb-104">Führen Sie die folgenden Schritte aus, um einen Wählplan zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="77ebb-104">To create a new dial plan, perform the steps in the following procedure.</span></span> <span data-ttu-id="77ebb-105">Wenn Sie einen Wählplan bearbeiten möchten, finden Sie weitere Informationen unter [Modify a Dial Plan in lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="77ebb-105">If you want to edit a dial plan, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span>

<div>

## <a name="to-create-a-dial-plan"></a><span data-ttu-id="77ebb-106">So erstellen Sie einen Wählplan</span><span class="sxs-lookup"><span data-stu-id="77ebb-106">To create a dial plan</span></span>

1.  <span data-ttu-id="77ebb-107">Melden Sie sich am Computer als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied der CsVoiceAdministrator-, CsServerAdministrator-oder CsAdministrator-Rolle an.</span><span class="sxs-lookup"><span data-stu-id="77ebb-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="77ebb-108">Ausführliche Informationen finden Sie unter [Delegate Setup Permissions in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="77ebb-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="77ebb-109">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="77ebb-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="77ebb-110">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="77ebb-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="77ebb-111">Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **Wählplan**.</span><span class="sxs-lookup"><span data-stu-id="77ebb-111">In the left navigation bar, click **Voice Routing** and then click **Dial Plan**.</span></span>

4.  <span data-ttu-id="77ebb-112">Klicken Sie auf der Seite **Wählplan** auf **Neu**, und wählen Sie einen Bereich für den Wählplan aus:</span><span class="sxs-lookup"><span data-stu-id="77ebb-112">On the **Dial Plan** page, click **New** and select a scope for the dial plan:</span></span>
    
      - <span data-ttu-id="77ebb-p104">**Standortwählplan** werden auf einen gesamten Standort angewendet, ausgenommen auf Benutzer oder Gruppen, die einem Wählplan zugeordnet wurden. Wenn Sie die Einstellung **Standort** als Bereich für einen Wählplan auswählen, müssen Sie im Dialogfeld **Standort auswählen** den gewünschten Standort angeben. Wenn bereits ein Wählplan für einen Standort erstellt wurde, wird der Standort nicht im Dialogfeld **Standort auswählen** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="77ebb-p104">**Site dial plan** applies to an entire site, except any users or groups that are assigned to a user dial plan. If you select **Site** for a dial plan’s scope, you must choose the site from the **Select a Site** dialog box. If a dial plan has already been created for a site, the site does not appear in the **Select a Site** dialog box.</span></span>
    
      - <span data-ttu-id="77ebb-p105">**Poolwählplan** kann auf ein PSTN-Gateway oder eine Registrierungsstelle angewendet werden. Wenn Sie die Einstellung **Pool** als Bereich für einen Wählplan auswählen, müssen Sie im Dialogfeld **Dienst auswählen** das gewünschte PSTN-Gateway oder die Registrierungsstelle angeben. Wenn bereits ein Wählplan für einen Dienst (PSTN-Gateway oder Registrierungsstelle) erstellt wurde, wird der Dienst nicht in der Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="77ebb-p105">**Pool dial plan** can apply to a public switched telephone network (PSTN) gateway or a Registrar. If you select **Pool** for a dial plan’s scope, choose the PSTN gateway or Registrar from the **Select a Service** dialog box. If a dial plan has already been created for a service (PSTN gateway or Registrar), the service does not appear in the list.</span></span>
    
      - <span data-ttu-id="77ebb-119">**Benutzerwählplan** kann auf bestimmte Benutzer oder Gruppen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="77ebb-119">**User dial plan** can be applied to specified users or groups.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="77ebb-120">Nachdem Sie den Bereich für den Wählplan ausgewählt haben, kann dieser nicht mehr geändert werden.</span><span class="sxs-lookup"><span data-stu-id="77ebb-120">After you select the dial plan scope, it cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="77ebb-p106">Wenn Sie einen Wählplan erstellen, geben Sie im Dialogfeld **Neuer Wählplan** im Feld **Name** einen beschreibenden Namen ein. Nach dem Speichern kann dieser Name nicht mehr geändert werden.</span><span class="sxs-lookup"><span data-stu-id="77ebb-p106">If you are creating a user dial plan, enter a descriptive name in the **Name** field on the **New Dial Plan** dialog box. After this name is saved, it cannot be changed.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="77ebb-123">Für Standortwählpläne wird das Feld <STRONG>Name</STRONG> mit dem Namen des Standorts vorausgefüllt und kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="77ebb-123">For site dial plans, the <STRONG>Name</STRONG> field is prepopulated with the site name and cannot be changed.</span></span><BR><span data-ttu-id="77ebb-124">Für Poolwählpläne wird das Feld <STRONG>Name</STRONG> mit dem Namen des PSTN-Gateways oder der Registrierungsstelle vorausgefüllt und kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="77ebb-124">For pool dial plans, the <STRONG>Name</STRONG> field is prepopulated with the PSTN gateway or Registrar name and cannot be changed.</span></span>

    
    </div>

6.  <span data-ttu-id="77ebb-p107">Das Feld **Einfacher Name** wird mit demselben Namen vorausgefüllt, der im Feld **Name** erscheint. Sie können dieses Feld optional bearbeiten, um einen aussagekräftigeren Namen anzugeben, der den Standort, Dienst oder Benutzer zur Anwendung des Wählplans besser beschreibt.</span><span class="sxs-lookup"><span data-stu-id="77ebb-p107">The **Simple name** field is prepopulated with the same name that appears in the **Name** field. You can optionally edit this field to specify a more descriptive name that reflects the site, service, or user to which the dial plan applies.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="77ebb-127">Der <STRONG>einfache Name</STRONG> muss unter allen Wählplänen innerhalb der lync Server-Bereitstellung eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="77ebb-127">The <STRONG>Simple name</STRONG> must be unique among all dial plans within the Lync Server deployment.</span></span> <span data-ttu-id="77ebb-128">Er darf 256 Unicode-Zeichen nicht überschreiten, von denen jedes ein alphabetisches oder numerisches Zeichen, ein Bindestrich (-), ein Punkt (.) oder ein Unterstrich (_) sein kann.</span><span class="sxs-lookup"><span data-stu-id="77ebb-128">It cannot exceed 256 Unicode characters, each of which can be an alphabetic or numeric character, a hyphen (-), a period (.), or an underscore (_).</span></span><BR><span data-ttu-id="77ebb-129"><STRONG>Nicht unterstützte</STRONG> Zeichen umfassen Leerzeichen und reservierte Zeichen gemäßhttp://www.ietf.org/rfc/rfc3966.txt)der Definition in RFC 3966 (.</span><span class="sxs-lookup"><span data-stu-id="77ebb-129">Characters <STRONG>not supported</STRONG> include spaces and Reserved characters as defined in RFC 3966 (http://www.ietf.org/rfc/rfc3966.txt).</span></span> <span data-ttu-id="77ebb-130">Reservierte Zeichen, die im <STRONG>einfachen Namen</STRONG> <STRONG>nicht unterstützt</STRONG> werden, umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="77ebb-130">Reserved characters that are <STRONG>not supported</STRONG> in the <STRONG>Simple Name</STRONG> include the following:</span></span><BR><span data-ttu-id="77ebb-131">";" "/" "?" ":" "@" "&amp;" "=" "+" "$" ","</span><span class="sxs-lookup"><span data-stu-id="77ebb-131">";" "/" "?" ":" "@" "&amp;" "=" "+" "$" ","</span></span>

    
    </div>

7.  <span data-ttu-id="77ebb-132">(Optional) Geben Sie im Feld **Beschreibung** zusätzliche beschreibende Informationen zum Wählplan ein.</span><span class="sxs-lookup"><span data-stu-id="77ebb-132">(Optional) In the **Description** field, you can type additional descriptive information about the dial plan.</span></span>

8.  <span data-ttu-id="77ebb-p110">(Optional) Wenn Sie diesen Wählplan als eine Region für Einwählnummern verwenden möchten, geben Sie eine **Einwahlkonferenzregion** an. Wenn Sie diesen Wählplan nicht für Einwählnummern verwenden möchten, lassen Sie dieses Feld leer.</span><span class="sxs-lookup"><span data-stu-id="77ebb-p110">(Optional) If you want to use this dial plan as a region for dial-in access numbers, specify a **Dial-in conferencing region**. If you do not want to use this dial plan for dial-in access numbers, leave this field empty.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="77ebb-135">Regionen für Einwahlkonferenzen werden benötigt, um Einwählnummern für Konferenzen einem oder mehreren Wählplänen zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="77ebb-135">Dial-in conferencing regions are required to associate dial-in conferencing access numbers with one or more dial plans.</span></span>

    
    </div>

9.  <span data-ttu-id="77ebb-136">(Optional) Geben Sie im Feld **Präfix für externen Zugriff** nur dann einen Wert an, wenn Benutzer eine oder mehrere zusätzliche Nummern wählen müssen, um eine externe Leitung zu erhalten (z. B. 9).</span><span class="sxs-lookup"><span data-stu-id="77ebb-136">(Optional) In the **External access prefix** field, specify a value only if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span> <span data-ttu-id="77ebb-137">Sie können einen Präfixwert von bis zu vier Zeichen eingeben (\#, \*und 0-9).</span><span class="sxs-lookup"><span data-stu-id="77ebb-137">You can type in a prefix value of up to four characters (\#, \*, and 0-9).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="77ebb-138">Wenn Sie ein Präfix für den externen Zugriff eingeben, müssen Sie keine neue Normalisierungsregel zur Unterstützung des Präfix erstellen.</span><span class="sxs-lookup"><span data-stu-id="77ebb-138">If you specify an external access prefix, you do not need to create a new normalization rule to accommodate the prefix.</span></span>

    
    </div>

10. <span data-ttu-id="77ebb-139">Führen Sie die folgenden Schritte aus, um Normalisierungsregeln für den Wählplan zuzuordnen und zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="77ebb-139">Associate and configure normalization rules for the dial plan as follows:</span></span>
    
      - <span data-ttu-id="77ebb-140">Klicken Sie auf **auswählen**, um eine oder mehrere Regeln aus einer Liste aller in Ihrer Enterprise-VoIP-Bereitstellung verfügbaren Normalisierungsregeln auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="77ebb-140">To choose one or more rules from a list of all normalization rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="77ebb-141">Klicken Sie im Dialogfeld **Normalisierungsregeln auswählen** auf die Regeln, die Sie dem Wählplan zuordnen möchten, und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="77ebb-141">In **Select Normalization Rules**, highlight the rules you want to associate with the dial plan and then click **OK**.</span></span>
    
      - <span data-ttu-id="77ebb-142">Klicken Sie auf **Neu**, um eine neue Normalisierungsregel zu definieren und dem Wählplan zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="77ebb-142">To define a new normalization rule and associate it with the dial plan, click **New**.</span></span> <span data-ttu-id="77ebb-143">Ausführliche Informationen zum Definieren einer neuen Regel finden Sie unter [Definieren von Normalisierungsregeln in lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="77ebb-143">For details about defining a new rule, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="77ebb-144">Klicken Sie auf den Regelnamen und anschließend auf **Details anzeigen**, um eine Normalisierungsregel zu bearbeiten, die bereits den Wähleinstellungen zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="77ebb-144">To edit a normalization rule that is already associated with the dial plan, highlight the rule name and click **Show details**.</span></span> <span data-ttu-id="77ebb-145">Ausführliche Informationen zum Bearbeiten der Regel finden Sie unter [Definieren von Normalisierungsregeln in lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="77ebb-145">For details about editing the rule, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="77ebb-146">Um eine vorhandene Normalisierungsregel als Startpunkt für die Definition einer neuen Regel zu verwenden, markieren Sie den Regelnamen, klicken Sie auf **Kopieren** und anschließend auf **Einfügen**.</span><span class="sxs-lookup"><span data-stu-id="77ebb-146">To copy an existing normalization rule to use as a starting point for defining a new rule, highlight the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="77ebb-147">Ausführliche Informationen zum Bearbeiten der Kopie finden Sie unter [Definieren von Normalisierungsregeln in lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="77ebb-147">For details about editing the copy, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="77ebb-148">Wenn Sie eine Normalisierungsregel aus den Wähleinstellungen entfernen möchten, markieren Sie den Regelnamen, und klicken Sie auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="77ebb-148">To remove a normalization rule from the dial plan, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="77ebb-149">Jedem Satz mit Wähleinstellungen muss mindestens eine Normalisierungsregel zugeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="77ebb-149">Each dial plan must have at least one associated normalization rule.</span></span> <span data-ttu-id="77ebb-150">Informationen zum Ermitteln aller Normalisierungsregeln, die für einen Wählplan erforderlich sind, finden Sie unter <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial Plans and normalize Rules in lync Server 2013</A> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="77ebb-150">For information about how to determine all of the normalization rules a dial plan requires, see <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial plans and normalization rules in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

11. <span data-ttu-id="77ebb-p117">Stellen Sie sicher, dass die Normalisierungsregeln für die Wähleinstellungen in der richtigen Reihenfolge angeordnet sind. Wenn Sie die Position einer Regel in der Liste ändern möchten, markieren Sie den Regelnamen, und klicken Sie auf den nach oben oder nach unten weisenden Pfeil.</span><span class="sxs-lookup"><span data-stu-id="77ebb-p117">Verify that the dial plan’s normalization rules are arranged in the correct order. To change a rule’s position in the list, highlight the rule name and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="77ebb-153">Lync Server durchläuft die Liste Normalisierungsregel von oben nach unten und verwendet die erste Regel, die mit der gewählten Nummer übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="77ebb-153">Lync Server traverses the normalization rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="77ebb-154">Wenn Sie einen Satz mit Wähleinstellungen so konfigurieren, dass eine gewählte Nummer mit mehr als einer Normalisierungsregel übereinstimmen kann, müssen Sie sicherstellen, dass die einschränkenderen Regeln über den weniger einschränkenden Regeln angeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="77ebb-154">If you configure a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span><BR><span data-ttu-id="77ebb-155">Die standardmäßige Normalisierungsregel " <STRONG>Keep all</STRONG> " <STRONG>^ ({11}\d) $</STRONG> entspricht einer beliebigen 11-stelligen Zahl.</span><span class="sxs-lookup"><span data-stu-id="77ebb-155">The default <STRONG>Keep All</STRONG> normalization rule <STRONG>^(\d{11})$</STRONG> matches any 11-digit number.</span></span> <span data-ttu-id="77ebb-156">Wenn Sie beispielsweise eine Normalisierungsregel hinzufügen, die 11-stelligen Zahlen entspricht, die mit 1425 beginnen, stellen Sie sicher, dass <STRONG>Alle beibehalten</STRONG> unter der restriktiveren <STRONG>^ (1425 \{7}d) $</STRONG> -Regel sortiert ist.</span><span class="sxs-lookup"><span data-stu-id="77ebb-156">For example, if you add a normalization rule that matches 11-digit numbers that start with 1425, make sure that <STRONG>Keep All</STRONG> is sorted below the more restrictive <STRONG>^(1425\d{7})$</STRONG> rule.</span></span>

    
    </div>

12. <span data-ttu-id="77ebb-p120">(Optional) Geben Sie eine Nummer zum Testen der Wähleinstellungen ein, und klicken Sie auf **Los**. Die Testergebnisse werden unterhalb von **Geben Sie eine Testnummer ein** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="77ebb-p120">(Optional) Enter a number to test the dial plan and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="77ebb-159">Sie können einen Satz mit Wähleinstellungen speichern, der den Test nicht bestanden hat, und ihn später neu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="77ebb-159">You can save a dial plan that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="77ebb-160">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-test-voice-routing.md">Testen der VoIP-Weiterleitung in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="77ebb-160">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

13. <span data-ttu-id="77ebb-161">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="77ebb-161">Click **OK**.</span></span>

14. <span data-ttu-id="77ebb-162">Klicken Sie auf der Seite **Wähleinstellungen** auf **Commit** und anschließend auf **Commit für alle**.</span><span class="sxs-lookup"><span data-stu-id="77ebb-162">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="77ebb-163">Jedes Mal, wenn Sie einen Wählplan erstellen, müssen Sie den Befehl <STRONG>Commit für alle Elemente ausführen</STRONG> aufrufen, um die Konfigurationsänderung zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="77ebb-163">Any time you create a dial plan, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="77ebb-164">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</A> in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="77ebb-164">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="77ebb-165">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="77ebb-165">See Also</span></span>


[<span data-ttu-id="77ebb-166">Ändern von Wähleinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77ebb-166">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
[<span data-ttu-id="77ebb-167">Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77ebb-167">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="77ebb-168">Definieren von Normalisierungsregeln in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77ebb-168">Defining normalization rules in Lync Server 2013</span></span>](lync-server-2013-defining-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

