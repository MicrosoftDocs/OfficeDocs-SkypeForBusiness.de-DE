---
title: Erstellen oder Ändern einer Normalisierungsregel mithilfe der Regel zum Erstellen einer Normalisierung
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
ms.openlocfilehash: 519d4d8ee00e0922d40155c541b0f869df095ab1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722345"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule-in-lync-server-2013"></a><span data-ttu-id="c1fad-102">Erstellen oder Ändern einer Normalisierungsregel mithilfe der Regel zum Erstellen einer Normalisierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c1fad-102">Create or modify a normalization rule by using Build a Normalization Rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c1fad-103">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="c1fad-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c1fad-104">Führen Sie die folgenden Schritte aus, wenn Sie eine Normalisierungsregel in der lync Server-Systemsteuerung erstellen oder ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="c1fad-104">Complete the following steps if you want to create or modify a normalization rule in Lync Server Control Panel.</span></span> <span data-ttu-id="c1fad-105">Wenn Sie eine Normalisierungsregel manuell erstellen oder ändern möchten, finden Sie Informationen dazu unter [Manuelles Erstellen oder Ändern einer Normalisierungsregel in lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-manually.md).</span><span class="sxs-lookup"><span data-stu-id="c1fad-105">Alternatively, if you want to create or modify a normalization rule manually, see [Create or modify a normalization rule manually in Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-manually.md).</span></span>

<div>

## <a name="to-define-a-rule-by-using-build-a-normalization-rule"></a><span data-ttu-id="c1fad-106">So definieren Sie eine Regel mithilfe der Regel zum Erstellen einer Normalisierung</span><span class="sxs-lookup"><span data-stu-id="c1fad-106">To define a rule by using Build a Normalization Rule</span></span>

1.  <span data-ttu-id="c1fad-107">Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an.</span><span class="sxs-lookup"><span data-stu-id="c1fad-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="c1fad-108">Ausführliche Informationen finden Sie unter [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="c1fad-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="c1fad-109">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="c1fad-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c1fad-110">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c1fad-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c1fad-111">Optional Führen Sie die Schritte unter [Erstellen eines Wählplans in lync Server 2013](lync-server-2013-create-a-dial-plan.md) bis Schritt 11 aus, oder [Ändern Sie einen Wählplan in lync Server 2013](lync-server-2013-modify-a-dial-plan.md) bis Schritt 10.</span><span class="sxs-lookup"><span data-stu-id="c1fad-111">(Optional) Follow the steps in [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) through step 11 or [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md) through step 10.</span></span>

4.  <span data-ttu-id="c1fad-112">Geben Sie unter **Neue Normalisierungsregel** oder **Normalisierungsregel bearbeiten** im Feld **Name** einen beschreibenden Namen für das zu normalisierende Nummernmuster ein (beispielsweise **5DigitExtension**).</span><span class="sxs-lookup"><span data-stu-id="c1fad-112">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example, **5DigitExtension**).</span></span>

5.  <span data-ttu-id="c1fad-113">(Optional) Geben Sie in **Beschreibung** eine Beschreibung der Normalisierungsregel ein (beispielsweise „Übersetzt 5-stellige Durchwahlnummern“).</span><span class="sxs-lookup"><span data-stu-id="c1fad-113">(Optional) In **Description**, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

6.  <span data-ttu-id="c1fad-114">Geben Sie im Abschnitt **Normalisierungsregel erstellen** Werte in die folgenden Felder ein:</span><span class="sxs-lookup"><span data-stu-id="c1fad-114">In **Build a Normalization Rule**, enter values in the following fields:</span></span>
    
      - <span data-ttu-id="c1fad-115">**Anfangsziffern**   (optional) geben Sie die führenden Ziffern für gewählte Nummern an, die mit dem Muster übereinstimmen sollen.</span><span class="sxs-lookup"><span data-stu-id="c1fad-115">**Starting digits**   (Optional) Specify the leading digits of dialed numbers you want the pattern to match.</span></span> <span data-ttu-id="c1fad-116">Geben Sie beispielsweise **425** ein, wenn das Muster für gewählte Nummern gelten soll, die mit 425 beginnen.</span><span class="sxs-lookup"><span data-stu-id="c1fad-116">For example, type **425** if you want the pattern to match dialed numbers beginning with 425.</span></span>
    
      - <span data-ttu-id="c1fad-117">**Länge**   geben Sie die Anzahl der Ziffern im übereinstimmenden Muster an, und wählen Sie aus, ob das Muster genau mit dieser Länge übereinstimmen soll, wie gewählte Nummern, die mindestens diese Länge aufweisen, oder mit gewählten Nummern beliebiger Länge übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="c1fad-117">**Length**   Specify the number of digits in the matching pattern and select whether you want the pattern to match this length exactly, match dialed numbers that are at least this length, or match dialed numbers of any length.</span></span>
    
      - <span data-ttu-id="c1fad-118">**Zu entfern**   Ende Ziffern (optional) geben Sie die Anzahl der Anfangsziffern an, die aus den gewählten Nummern entfernt werden sollen, die das Muster erfüllen soll.</span><span class="sxs-lookup"><span data-stu-id="c1fad-118">**Digits to remove**   (Optional) Specify the number of starting digits to be removed from dialed numbers you want the pattern to match.</span></span>
    
      - <span data-ttu-id="c1fad-119">**Zu addier**   Ende Ziffern (optional) geben Sie Ziffern an, die zu gewählten Nummern hinzugefügt werden sollen, die dem Muster entsprechen sollen.</span><span class="sxs-lookup"><span data-stu-id="c1fad-119">**Digits to add**   (Optional) Specify digits to be added to dialed numbers you want the pattern to match.</span></span>
    
    <span data-ttu-id="c1fad-p105">Die in diesen Feldern eingegebenen Werte werden in den Feldern **Muster für Vergleich** und **Übersetzungsregel** widergespiegelt. Wenn Sie beispielsweise **Anfangsziffern** leer lassen, den Wert **7** in das Feld **Länge** eingeben und **Genau** auswählen und den Wert **0** unter **Zu entfernende Ziffern** wählen, ergibt sich in **Muster für Vergleich** der folgende reguläre Ausdruck:</span><span class="sxs-lookup"><span data-stu-id="c1fad-p105">The values you enter in these fields are reflected in **Pattern to match** and **Translation rule**. For example, if you leave **Starting digits** empty, type **7** into the **Length** field and select **Exactly**, and specify **0** in **Digits to remove**, the resulting regular expression in the **Pattern to match** is:</span></span>
    
    <span data-ttu-id="c1fad-122">**^ (\\d{7}) $**</span><span class="sxs-lookup"><span data-stu-id="c1fad-122">**^(\\d{7})$**</span></span>

7.  <span data-ttu-id="c1fad-123">Geben Sie in **Übersetzungsregel** ein Muster für das Format der übersetzten E.164-Telefonnummern ein:</span><span class="sxs-lookup"><span data-stu-id="c1fad-123">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers as follows:</span></span>
    
      - <span data-ttu-id="c1fad-124">Ein Wert, der die Anzahl von Ziffern repräsentiert, die im Vergleichsmuster angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="c1fad-124">A value that represents the number of digits specified in the matching pattern.</span></span> <span data-ttu-id="c1fad-125">Wenn das Übereinstimmungsmuster beispielsweise **^ (\\d{7}) $** ist, stellt **$1** in der Übersetzungsregel siebenstellige Wähl Nummern dar.</span><span class="sxs-lookup"><span data-stu-id="c1fad-125">For example, if the matching pattern is **^(\\d{7})$** then **$1** in the translation rule represents 7-digit dialed numbers.</span></span>
    
      - <span data-ttu-id="c1fad-126">(Optional) Geben Sie einen Wert in das Feld **Hinzuzufügende Ziffern** ein, um Ziffern anzugeben, die der übersetzten Nummer vorangestellt werden (z. B. **+1425**).</span><span class="sxs-lookup"><span data-stu-id="c1fad-126">(Optional) Type a value into the **Digits to add** field to specify digits to be prepended to the translated number (for example, **+1425**).</span></span>
    
    <span data-ttu-id="c1fad-127">Wenn Muster für die **Übereinstimmung** beispielsweise **^ (\\d{7}) $** als Muster für gewählte Nummern und die **Übersetzungsregel** **+ 1425 $1** als Muster für E. 164-Telefonnummern enthält, normalisiert die Regel 5550100 auf + 14255550100.</span><span class="sxs-lookup"><span data-stu-id="c1fad-127">For example, if **Pattern to match** contains **^(\\d{7})$** as the pattern for dialed numbers and **Translation rule** contains **+1425$1** as the pattern for E.164 phone numbers, the rule normalizes 5550100 to +14255550100.</span></span>

8.  <span data-ttu-id="c1fad-128">(Optional) Falls die Normalisierungsregel eine interne Telefonnummer des Unternehmens ergibt, klicken Sie auf **Interne Durchwahl**.</span><span class="sxs-lookup"><span data-stu-id="c1fad-128">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

9.  <span data-ttu-id="c1fad-p107">(Optional) Geben Sie eine Nummer zum Testen der Normalisierungsregel ein und klicken Sie auf **Los**. Die Testergebnisse werden unterhalb von **Geben Sie eine Testnummer ein** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c1fad-p107">(Optional) Enter a number to test the normalization rule, and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="c1fad-131">Sie können eine Normalisierungsregel speichern, die den Test nicht bestanden hat und sie später neu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c1fad-131">You can save a normalization rule that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="c1fad-132">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-test-voice-routing.md">Testen des VoIP-Routings in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c1fad-132">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

10. <span data-ttu-id="c1fad-133">Klicken Sie auf **OK**, um die Normalisierungsregel zu speichern.</span><span class="sxs-lookup"><span data-stu-id="c1fad-133">Click **OK** to save the normalization rule.</span></span>

11. <span data-ttu-id="c1fad-134">Klicken Sie auf **OK**, um die Wähleinstellungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="c1fad-134">Click **OK** to save the dial plan.</span></span>

12. <span data-ttu-id="c1fad-135">Klicken Sie auf der Seite **Wählplan** auf **Commit ausführen** und anschließend auf **Commit für alle Elemente ausführen**.</span><span class="sxs-lookup"><span data-stu-id="c1fad-135">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="c1fad-136">Jedes Mal, wenn Sie eine Normalisierungsregel erstellen oder ändern, müssen Sie den Befehl <STRONG>Commit für alle</STRONG> ausführen, um die Konfigurationsänderung zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="c1fad-136">Whenever you create or change a normalization rule, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="c1fad-137">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</A> in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="c1fad-137">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c1fad-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c1fad-138">See Also</span></span>


[<span data-ttu-id="c1fad-139">Manuelles Erstellen oder Ändern einer Normalisierungsregel in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c1fad-139">Create or modify a normalization rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)  
[<span data-ttu-id="c1fad-140">Erstellen eines Wählplans in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c1fad-140">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="c1fad-141">Ändern eines Wählplans in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c1fad-141">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
[<span data-ttu-id="c1fad-142">Veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c1fad-142">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="c1fad-143">Testen des VoIP-Routings in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c1fad-143">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

