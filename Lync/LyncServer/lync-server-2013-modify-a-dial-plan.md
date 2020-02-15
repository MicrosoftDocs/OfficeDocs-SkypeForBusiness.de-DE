---
title: 'Lync Server 2013: Ändern von Wähleinstellungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify a dial plan
ms:assetid: a91f02df-cf60-40cf-82fe-e0342c118b91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412797(v=OCS.15)
ms:contentKeyID: 48185099
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e20b05a85daa50003ca0062ea427473eae1bf95
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035941"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-a-dial-plan-in-lync-server-2013"></a><span data-ttu-id="a150a-102">Ändern von Wähleinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a150a-102">Modify a dial plan in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a150a-103">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a150a-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a150a-104">Führen Sie die folgenden Schritte aus, um einen vorhandenen Satz mit Wähleinstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="a150a-104">To modify an existing dial plan, perform the steps in the following procedure.</span></span> <span data-ttu-id="a150a-105">Informationen zum Erstellen eines neuen Wählplans finden Sie unter [Create a Dial Plan in lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="a150a-105">If you want to create a new dial plan, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span></span>

<div>

## <a name="to-modify-a-dial-plan"></a><span data-ttu-id="a150a-106">So ändern Sie einen Satz mit Wähleinstellungen</span><span class="sxs-lookup"><span data-stu-id="a150a-106">To modify a dial plan</span></span>

1.  <span data-ttu-id="a150a-107">Melden Sie sich am Computer als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied der CsVoiceAdministrator-, CsServerAdministrator-oder CsAdministrator-Rolle an.</span><span class="sxs-lookup"><span data-stu-id="a150a-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="a150a-108">Ausführliche Informationen finden Sie unter [Delegate Setup Permissions in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="a150a-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="a150a-109">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="a150a-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a150a-110">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a150a-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a150a-111">Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **Wähleinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="a150a-111">In the left navigation bar, click **Voice Routing** and then click **Dial Plan**.</span></span>

4.  <span data-ttu-id="a150a-112">Doppelklicken Sie auf der Seite **Wähleinstellungen** auf einen Satz mit Wähleinstellungen.</span><span class="sxs-lookup"><span data-stu-id="a150a-112">On the **Dial Plan** page, double-click a dial plan name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a150a-p104">Bereich und Name der Wähleinstellungen wurden beim Erstellen der Wähleinstellungen festgelegt.  Sie können nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="a150a-p104">The dial plan scope and name were set when the dial plan was created. They cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="a150a-115">(Optional) Bearbeiten Sie im Abschnitt **Wähleinstellungen bearbeiten** das Feld **Einfacher Name** (dieses wird mit dem Namen im Feld **Name** vorausgefüllt), um einen beschreibenderen Namen einzugeben, der den Standort, Dienst oder Benutzer angibt, für den die Wähleinstellungen gelten.</span><span class="sxs-lookup"><span data-stu-id="a150a-115">(Optional) In **Edit Dial Plan**, edit the **Simple name** field, which is prepopulated with the same name that appears in the **Name** field to specify a more descriptive name that reflects the site, service, or user to which the dial plan applies.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a150a-116">Der <STRONG>einfache Name</STRONG> muss unter allen Wählplänen innerhalb der lync Server 2013-Bereitstellung eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="a150a-116">The <STRONG>Simple name</STRONG> must be unique among all dial plans within the Lync Server 2013 deployment.</span></span> <span data-ttu-id="a150a-117">Der Name darf nicht mehr als 256 Unicode-Zeichen umfassen und kann Buchstaben oder Zahlen, Bindestriche (-), Punkte (.), Pluszeichen (+) oder Unterstriche (_) enthalten.</span><span class="sxs-lookup"><span data-stu-id="a150a-117">It cannot exceed 256 Unicode characters, each of which can be an alphabetic or numeric character, a hyphen (-), a period (.), a plus sign (+), or an underscore (_).</span></span><BR><span data-ttu-id="a150a-118">Leerzeichen sind im Feld <STRONG>Einfacher Name</STRONG> nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="a150a-118">Spaces are not allowed in the <STRONG>Simple name</STRONG> field.</span></span>

    
    </div>

6.  <span data-ttu-id="a150a-119">(Optional) Geben Sie im Feld **Beschreibung** beschreibende Informationen zu den Wähleinstellungen ein.</span><span class="sxs-lookup"><span data-stu-id="a150a-119">(Optional) In the **Description** field, type descriptive information about the dial plan.</span></span>

7.  <span data-ttu-id="a150a-p106">(Optional) Wenn Sie diese Wähleinstellungen als eine Region für Einwählnummern verwenden möchten, geben Sie eine **Region für Einwahlkonferenzen** an. Wenn Sie diese Wähleinstellungen nicht für Einwählnummern verwenden möchten, lassen Sie dieses Feld leer.</span><span class="sxs-lookup"><span data-stu-id="a150a-p106">(Optional) If you want to use this dial plan as a region for dial-in access numbers, specify a **Dial-in conferencing region**. If you do not want to use this dial plan for dial-in access numbers, leave this field empty.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a150a-122">Regionen für Einwahlkonferenzen werden benötigt, um Einwählnummern für Konferenzen einem oder mehreren Sätzen mit Wähleinstellungen zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="a150a-122">Dial-in conferencing regions are required to associate dial-in conferencing access numbers with one or more dial plans.</span></span>

    
    </div>

8.  <span data-ttu-id="a150a-123">(Optional) Geben Sie im Feld **Präfix für externen Zugriff** nur dann einen Wert an, wenn Benutzer eine oder mehrere zusätzliche Nummern wählen müssen, um eine externe Leitung zu erhalten (z. B. 9).</span><span class="sxs-lookup"><span data-stu-id="a150a-123">(Optional) In the **External access prefix** field, specify a value only if users need to dial one or more additional leading digits to get an external line (for example, 9).</span></span> <span data-ttu-id="a150a-124">Sie können einen Präfixwert von bis zu vier Zeichen eingeben (also \# \*,, und 0-9).</span><span class="sxs-lookup"><span data-stu-id="a150a-124">You can type in a prefix value of up to four characters (that is, \#, \*, and 0-9).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a150a-125">Wenn Sie ein Präfix für den externen Zugriff eingeben, müssen Sie keine neue Normalisierungsregel zur Unterstützung des Präfix erstellen.</span><span class="sxs-lookup"><span data-stu-id="a150a-125">If you specify an external access prefix, you do not need to create a new normalization rule to accommodate the prefix.</span></span>

    
    </div>

9.  <span data-ttu-id="a150a-126">Zuordnen und Konfigurieren von Normalisierungsregeln für die Wähleinstellungen:</span><span class="sxs-lookup"><span data-stu-id="a150a-126">Associate and configure normalization rules for the dial plan:</span></span>
    
      - <span data-ttu-id="a150a-127">Klicken Sie auf **auswählen**, um eine oder mehrere Regeln aus einer Liste aller in Ihrer Enterprise-VoIP-Bereitstellung verfügbaren Normalisierungsregeln auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="a150a-127">To choose one or more rules from a list of all normalization rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="a150a-128">Klicken Sie im Dialogfeld **Normalisierungsregeln auswählen** auf die Regeln, die Sie den Wähleinstellungen zuordnen möchten, und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a150a-128">In the **Select Normalization Rules** dialog box, highlight the rules that you want to associate with the dial plan and then click **OK**.</span></span>
    
      - <span data-ttu-id="a150a-129">Klicken Sie auf **Neu**, um eine neue Normalisierungsregel zu definieren und den Wähleinstellungen zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="a150a-129">To define a new normalization rule and associate it with the dial plan, click **New**.</span></span> <span data-ttu-id="a150a-130">Ausführliche Informationen zum Definieren einer neuen Regel finden Sie unter [Definieren von Normalisierungsregeln in lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="a150a-130">For details about defining a new rule, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="a150a-131">Klicken Sie auf den Regelnamen und anschließend auf **Details anzeigen**, um eine Normalisierungsregel zu bearbeiten, die bereits den Wähleinstellungen zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="a150a-131">To edit a normalization rule that is already associated with the dial plan, highlight the rule name and click **Show details**.</span></span> <span data-ttu-id="a150a-132">Ausführliche Informationen zum Bearbeiten der Regel finden Sie unter [Definieren von Normalisierungsregeln in lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="a150a-132">For details about editing the rule, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="a150a-133">Um eine vorhandene Normalisierungsregel als Startpunkt für die Definition einer neuen Regel zu verwenden, markieren Sie den Regelnamen, klicken Sie auf **Kopieren** und anschließend auf **Einfügen**.</span><span class="sxs-lookup"><span data-stu-id="a150a-133">To copy an existing normalization rule to use as a starting point for defining a new rule, highlight the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="a150a-134">Ausführliche Informationen zum Bearbeiten der Kopie finden Sie unter [Definieren von Normalisierungsregeln in lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="a150a-134">For details about editing the copy, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="a150a-135">Wenn Sie eine Normalisierungsregel aus den Wähleinstellungen entfernen möchten, markieren Sie den Regelnamen, und klicken Sie auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="a150a-135">To remove a normalization rule from the dial plan, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a150a-136">Jedem Satz mit Wähleinstellungen muss mindestens eine Normalisierungsregel zugeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="a150a-136">Each dial plan must have at least one associated normalization rule.</span></span> <span data-ttu-id="a150a-137">Ausführliche Informationen zum Ermitteln aller Normalisierungsregeln, die für einen Wählplan erforderlich sind, finden Sie unter <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial Plans and normalize Rules in lync Server 2013</A> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="a150a-137">For details about how to determine all of the normalization rules a dial plan requires, see <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial plans and normalization rules in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

10. <span data-ttu-id="a150a-p113">Stellen Sie sicher, dass die Normalisierungsregeln für die Wähleinstellungen in der richtigen Reihenfolge angeordnet sind. Wenn Sie die Position einer Regel in der Liste ändern möchten, markieren Sie den Regelnamen, und klicken Sie auf den nach oben oder nach unten weisenden Pfeil.</span><span class="sxs-lookup"><span data-stu-id="a150a-p113">Verify that the dial plan’s normalization rules are arranged in the correct order. To change a rule’s position in the list, highlight the rule name and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a150a-140">Lync Server durchläuft die Liste Normalisierungsregel von oben nach unten und verwendet die erste Regel, die mit der gewählten Nummer übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="a150a-140">Lync Server traverses the normalization rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="a150a-141">Wenn Sie einen Satz mit Wähleinstellungen so konfigurieren, dass eine gewählte Nummer mit mehr als einer Normalisierungsregel übereinstimmen kann, müssen Sie sicherstellen, dass die einschränkenderen Regeln über den weniger einschränkenden Regeln angeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="a150a-141">If you configure a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span><BR><span data-ttu-id="a150a-142">Die standardmäßige Normalisierungsregel " <STRONG>Keep all</STRONG> " <STRONG>^ ({11}\d) $</STRONG> entspricht einer beliebigen 11-stelligen Zahl.</span><span class="sxs-lookup"><span data-stu-id="a150a-142">The default <STRONG>Keep All</STRONG> normalization rule <STRONG>^(\d{11})$</STRONG> matches any 11-digit number.</span></span> <span data-ttu-id="a150a-143">Wenn Sie beispielsweise eine Normalisierungsregel hinzufügen, die 11-stelligen Zahlen entspricht, die mit 1425 beginnen, stellen Sie sicher, dass <STRONG>Alle beibehalten</STRONG> unter der restriktiveren <STRONG>^ (1425 \ d{7}) $</STRONG> -Regel sortiert ist.</span><span class="sxs-lookup"><span data-stu-id="a150a-143">If, for example, you add a normalization rule that matches 11-digit numbers that start with 1425, make sure that <STRONG>Keep All</STRONG> is sorted below the more restrictive <STRONG>^(1425\d{7})$</STRONG> rule.</span></span>

    
    </div>

11. <span data-ttu-id="a150a-p116">(Optional) Geben Sie eine Nummer zum Testen der Wähleinstellungen ein, und klicken Sie auf **Los**. Die Testergebnisse werden unterhalb von **Geben Sie eine Testnummer ein** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a150a-p116">(Optional) Enter a number to test the dial plan and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a150a-146">Sie können einen Satz mit Wähleinstellungen speichern, der den Test nicht bestanden hat, und ihn später neu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="a150a-146">You can save a dial plan that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="a150a-147">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-test-voice-routing.md">Testen der VoIP-Weiterleitung in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="a150a-147">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="a150a-148">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a150a-148">Click **OK**.</span></span>

13. <span data-ttu-id="a150a-149">Klicken Sie auf der Seite **Wähleinstellungen** auf **Commit** und anschließend auf **Commit für alle**.</span><span class="sxs-lookup"><span data-stu-id="a150a-149">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a150a-150">Jedes Mal, wenn Sie einen Satz mit Wähleinstellungen erstellen oder ändern, müssen Sie den Befehl <STRONG>Commit für alle</STRONG> ausführen, um die Konfigurationsänderung zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="a150a-150">Any time you create or modify a dial plan, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="a150a-151">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</A> in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="a150a-151">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a150a-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a150a-152">See Also</span></span>


[<span data-ttu-id="a150a-153">Erstellen von Wähleinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a150a-153">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="a150a-154">Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a150a-154">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="a150a-155">Definieren von Normalisierungsregeln in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a150a-155">Defining normalization rules in Lync Server 2013</span></span>](lync-server-2013-defining-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

