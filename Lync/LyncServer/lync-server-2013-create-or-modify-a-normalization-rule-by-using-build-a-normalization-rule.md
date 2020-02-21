---
title: Erstellen oder Ändern einer Normalisierungsregel mit Normalisierungsregel erstellen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a normalization rule by using Build a Normalization Rule
ms:assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399036(v=OCS.15)
ms:contentKeyID: 48185889
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02bbebae55504fcc27550bae3b90d7fca662a487
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205477"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule-in-lync-server-2013"></a><span data-ttu-id="ca155-102">Erstellen oder Ändern einer Normalisierungsregel mithilfe der Regel zum Erstellen einer Normalisierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca155-102">Create or modify a normalization rule by using Build a Normalization Rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca155-103">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="ca155-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="ca155-104">Führen Sie die folgenden Schritte aus, wenn Sie eine Normalisierungsregel in lync Server-Systemsteuerung erstellen oder ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="ca155-104">Complete the following steps if you want to create or modify a normalization rule in Lync Server Control Panel.</span></span> <span data-ttu-id="ca155-105">Wenn Sie eine Normalisierungsregel manuell erstellen oder ändern möchten, finden Sie weitere Informationen unter [erstellen oder Ändern einer Normalisierungsregel manuell in lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-manually.md).</span><span class="sxs-lookup"><span data-stu-id="ca155-105">Alternatively, if you want to create or modify a normalization rule manually, see [Create or modify a normalization rule manually in Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-manually.md).</span></span>

<div>

## <a name="to-define-a-rule-by-using-build-a-normalization-rule"></a><span data-ttu-id="ca155-106">So definieren Sie eine Regel mit dem Erstellen einer Normalisierungsregel</span><span class="sxs-lookup"><span data-stu-id="ca155-106">To define a rule by using Build a Normalization Rule</span></span>

1.  <span data-ttu-id="ca155-107">Melden Sie sich am Computer als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied der CsVoiceAdministrator-, CsServerAdministrator-oder CsAdministrator-Rolle an.</span><span class="sxs-lookup"><span data-stu-id="ca155-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="ca155-108">Ausführliche Informationen finden Sie unter [Delegate Setup Permissions in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="ca155-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="ca155-109">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="ca155-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ca155-110">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ca155-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ca155-111">Optional Führen Sie die Schritte unter [Erstellen von Wähleinstellungen in lync Server 2013](lync-server-2013-create-a-dial-plan.md) bis Schritt 11 oder [Ändern eines Wählplans in lync Server 2013](lync-server-2013-modify-a-dial-plan.md) bis Schritt 10 aus.</span><span class="sxs-lookup"><span data-stu-id="ca155-111">(Optional) Follow the steps in [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) through step 11 or [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md) through step 10.</span></span>

4.  <span data-ttu-id="ca155-112">Geben Sie unter **neue Normalisierungsregel** oder **Normalisierungsregel bearbeiten**einen Namen ein, der das im **Namen** normalisierte Nummernmuster beschreibt (beispielsweise **5DigitExtension**).</span><span class="sxs-lookup"><span data-stu-id="ca155-112">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example, **5DigitExtension**).</span></span>

5.  <span data-ttu-id="ca155-113">Optional Geben Sie in **Beschreibung**eine Beschreibung der Normalisierungsregel ein (beispielsweise "übersetzt 5-stellige Durchwahlnummern").</span><span class="sxs-lookup"><span data-stu-id="ca155-113">(Optional) In **Description**, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

6.  <span data-ttu-id="ca155-114">Geben Sie unter **Normalisierungsregel erstellen**Werte in die folgenden Felder ein:</span><span class="sxs-lookup"><span data-stu-id="ca155-114">In **Build a Normalization Rule**, enter values in the following fields:</span></span>
    
      - <span data-ttu-id="ca155-115">**Starting digits**   (optional) geben Sie die führenden Ziffern von gewählten Nummern an, die mit dem Muster übereinstimmen sollen.</span><span class="sxs-lookup"><span data-stu-id="ca155-115">**Starting digits**   (Optional) Specify the leading digits of dialed numbers you want the pattern to match.</span></span> <span data-ttu-id="ca155-116">Geben Sie beispielsweise **425** ein, wenn das Muster mit den gewählten Nummern beginnend mit 425 übereinstimmen soll.</span><span class="sxs-lookup"><span data-stu-id="ca155-116">For example, type **425** if you want the pattern to match dialed numbers beginning with 425.</span></span>
    
      - <span data-ttu-id="ca155-117">**Length**   geben Sie die Anzahl der Stellen im übereinstimmenden Muster an, und wählen Sie aus, ob das Muster genau mit dieser Länge übereinstimmen soll, mit ausgewählten Nummern, die mindestens diese Länge aufweisen, oder mit den gewählten Nummern einer beliebigen Länge übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="ca155-117">**Length**   Specify the number of digits in the matching pattern and select whether you want the pattern to match this length exactly, match dialed numbers that are at least this length, or match dialed numbers of any length.</span></span>
    
      - <span data-ttu-id="ca155-118">**Zu entfern**   Ende Ziffern (optional) geben Sie die Anzahl der Start Ziffern an, die aus gewählten Nummern entfernt werden sollen, die mit dem Muster übereinstimmen sollen.</span><span class="sxs-lookup"><span data-stu-id="ca155-118">**Digits to remove**   (Optional) Specify the number of starting digits to be removed from dialed numbers you want the pattern to match.</span></span>
    
      - <span data-ttu-id="ca155-119">**Hinzuzufügende**   Ziffern (optional) geben Sie Ziffern an, die gewählten Nummern hinzugefügt werden sollen, die mit dem Muster übereinstimmen sollen.</span><span class="sxs-lookup"><span data-stu-id="ca155-119">**Digits to add**   (Optional) Specify digits to be added to dialed numbers you want the pattern to match.</span></span>
    
    <span data-ttu-id="ca155-120">Die Werte, die Sie in diese Felder eingeben, werden in **Übereinstimmung mit Muster** und **Übersetzungsregel**übernommen.</span><span class="sxs-lookup"><span data-stu-id="ca155-120">The values you enter in these fields are reflected in **Pattern to match** and **Translation rule**.</span></span> <span data-ttu-id="ca155-121">Wenn Sie beispielsweise **Start Ziffern** leer lassen, geben Sie **7** in das Feld **length** ein, und wählen Sie **genau**aus, und geben Sie **0** in **Ziffern zum Entfernen**an, sodass der resultierende reguläre Ausdruck im **Muster mit folgendem übereinstimmt** :</span><span class="sxs-lookup"><span data-stu-id="ca155-121">For example, if you leave **Starting digits** empty, type **7** into the **Length** field and select **Exactly**, and specify **0** in **Digits to remove**, the resulting regular expression in the **Pattern to match** is:</span></span>
    
    <span data-ttu-id="ca155-122">**^ (\\d{7}) $**</span><span class="sxs-lookup"><span data-stu-id="ca155-122">**^(\\d{7})$**</span></span>

7.  <span data-ttu-id="ca155-123">Geben Sie in **Übersetzungsregel**ein Muster für das Format der übersetzten E. 164-Telefonnummern wie folgt an:</span><span class="sxs-lookup"><span data-stu-id="ca155-123">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers as follows:</span></span>
    
      - <span data-ttu-id="ca155-124">Ein Wert, der die Anzahl der im übereinstimmenden Muster angegebenen Ziffern darstellt.</span><span class="sxs-lookup"><span data-stu-id="ca155-124">A value that represents the number of digits specified in the matching pattern.</span></span> <span data-ttu-id="ca155-125">Wenn das übereinstimmende Musterbeispiels Weise **^ (\\d{7}) $** ist, dann **$1** in der Übersetzungsregel 7-stellige gewählte Nummern darstellt.</span><span class="sxs-lookup"><span data-stu-id="ca155-125">For example, if the matching pattern is **^(\\d{7})$** then **$1** in the translation rule represents 7-digit dialed numbers.</span></span>
    
      - <span data-ttu-id="ca155-126">Optional Geben Sie einen Wert in das Feld **Ziffern hinzufügen** ein, um Ziffern anzugeben, die der übersetzten Zahl vorangestellt werden sollen (beispielsweise **+ 1425**).</span><span class="sxs-lookup"><span data-stu-id="ca155-126">(Optional) Type a value into the **Digits to add** field to specify digits to be prepended to the translated number (for example, **+1425**).</span></span>
    
    <span data-ttu-id="ca155-127">Enthält beispielsweise das Muster für die **Übereinstimmung** **^\\({7}d) $** , da das Muster für gewählte Nummern und die **Übersetzungsregel** **+ 1425 $1** als Muster für E. 164-Telefonnummern enthält, normalisiert die Regel 5550100 bis + 14255550100.</span><span class="sxs-lookup"><span data-stu-id="ca155-127">For example, if **Pattern to match** contains **^(\\d{7})$** as the pattern for dialed numbers and **Translation rule** contains **+1425$1** as the pattern for E.164 phone numbers, the rule normalizes 5550100 to +14255550100.</span></span>

8.  <span data-ttu-id="ca155-128">Optional Wenn die Normalisierungsregel eine interne Telefonnummer für Ihre Organisation ergibt, wählen Sie **interne Durchwahl**aus.</span><span class="sxs-lookup"><span data-stu-id="ca155-128">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

9.  <span data-ttu-id="ca155-129">Optional Geben Sie eine Zahl ein, um die Normalisierungsregel zu testen, und klicken Sie dann auf **go**.</span><span class="sxs-lookup"><span data-stu-id="ca155-129">(Optional) Enter a number to test the normalization rule, and then click **Go**.</span></span> <span data-ttu-id="ca155-130">Die Testergebnisse werden unterhalb von **Geben Sie eine Testnummer ein** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ca155-130">The test results are displayed under **Enter a number to test**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="ca155-131">Sie können eine Normalisierungsregel speichern, die den Test noch nicht besteht, und Sie dann später neu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ca155-131">You can save a normalization rule that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="ca155-132">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-test-voice-routing.md">Testen der VoIP-Weiterleitung in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ca155-132">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

10. <span data-ttu-id="ca155-133">Klicken Sie auf **OK** , um die Normalisierungsregel zu speichern.</span><span class="sxs-lookup"><span data-stu-id="ca155-133">Click **OK** to save the normalization rule.</span></span>

11. <span data-ttu-id="ca155-134">Klicken Sie auf **OK** , um die Wähleinstellungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="ca155-134">Click **OK** to save the dial plan.</span></span>

12. <span data-ttu-id="ca155-135">Klicken Sie auf der Seite **Wähleinstellungen** auf **Commit** und anschließend auf **Commit für alle**.</span><span class="sxs-lookup"><span data-stu-id="ca155-135">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="ca155-136">Wenn Sie eine Normalisierungsregel erstellen oder ändern, müssen Sie den Befehl <STRONG>Commit all</STRONG> ausführen, um die Konfigurationsänderung zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="ca155-136">Whenever you create or change a normalization rule, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="ca155-137">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</A> in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="ca155-137">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ca155-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ca155-138">See Also</span></span>


[<span data-ttu-id="ca155-139">Manuelles Erstellen oder Ändern einer Normalisierungsregel in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca155-139">Create or modify a normalization rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)  
[<span data-ttu-id="ca155-140">Erstellen von Wähleinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca155-140">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="ca155-141">Ändern von Wähleinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca155-141">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
[<span data-ttu-id="ca155-142">Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca155-142">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="ca155-143">Testen des VoIP-Routings in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca155-143">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

