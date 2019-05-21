---
title: Erstellen oder Ändern einer Übersetzungsregel für die benannte ID-Präsentation in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie mithilfe des Tools zum Erstellen einer Übersetzungsregel in Skype for Business Server eine Übersetzungsregel definieren.'
ms.openlocfilehash: 13e89fd836c971085a3a1fc40b7e60793e10eb68
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275871"
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server"></a><span data-ttu-id="264af-103">Erstellen oder Ändern einer Übersetzungsregel für die benannte ID-Präsentation in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="264af-103">Create or modify a translation rule for called ID presentation in Skype for Business Server</span></span>

<span data-ttu-id="264af-104">**Zusammenfassung:** Hier erfahren Sie, wie Sie mithilfe des Tools zum Erstellen einer Übersetzungsregel in Skype for Business Server eine Übersetzungsregel definieren.</span><span class="sxs-lookup"><span data-stu-id="264af-104">**Summary:** Learn how to define a translation rule by using the Build a Translation Rule tool in Skype for Business Server.</span></span>

<span data-ttu-id="264af-105">Führen Sie die folgenden Schritte aus, wenn Sie eine Übersetzungsregel definieren möchten, indem Sie eine Gruppe von Werten in das Tool zum **Erstellen einer Übersetzungsregel** eingeben und die Skype for Business Server-Systemsteuerung aktivieren, um das entsprechende Übereinstimmungsmuster und die Übersetzungsregel für Sie zu generieren.</span><span class="sxs-lookup"><span data-stu-id="264af-105">Follow these steps if you want to define a translation rule by entering a set of values in the **Build a Translation Rule** tool and enabling Skype for Business Server Control Panel to generate the corresponding matching pattern and translation rule for you.</span></span> <span data-ttu-id="264af-106">Alternativ können Sie manuell einen regulären Ausdruck erstellen, um das Vergleichsmuster und die Übersetzungsregel zu definieren.</span><span class="sxs-lookup"><span data-stu-id="264af-106">Alternatively, you can a write regular expression manually to define the matching pattern and translation rule.</span></span> <span data-ttu-id="264af-107">Ausführliche Informationen finden Sie unter [Create or Modify a Translation Rule Manually](https://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx).</span><span class="sxs-lookup"><span data-stu-id="264af-107">For details, see [Create or Modify a Translation Rule Manually](https://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx).</span></span>

### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a><span data-ttu-id="264af-108">So definieren Sie eine Regel mit dem Tool zum Erstellen einer Übersetzungsregel</span><span class="sxs-lookup"><span data-stu-id="264af-108">To define a rule by using the Build a Translation Rule tool</span></span>

1. <span data-ttu-id="264af-109">Öffnen Sie die Skype for Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="264af-109">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="264af-110">Wenn Sie mit der Definition einer Übersetzungsregel beginnen möchten, führen Sie die Schritte unter [Konfigurieren eines Trunks mit medienumgehung in Skype for Business Server](configure-trunk-with-media-bypass.md) bis Schritt 10 aus, oder [Konfigurieren Sie einen trunk ohne medienumgehung in Skype for Business Server](configure-trunk-without-media-bypass.md) bis Schritt 9.</span><span class="sxs-lookup"><span data-stu-id="264af-110">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md) through step 9.</span></span>

3. <span data-ttu-id="264af-111">Geben Sie unter **Name** auf der Seite **Neue Übersetzungsregel** oder **Übersetzungsregel bearbeiten** einen Namen ein, der das zu übersetzende Nummernmuster beschreibt.</span><span class="sxs-lookup"><span data-stu-id="264af-111">Under **Name** on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

4. <span data-ttu-id="264af-112">Optional Geben Sie unter **Beschreibung**eine Beschreibung der Übersetzungsregel ein, beispielsweise US-Auslands Wahl für Ferngespräche.</span><span class="sxs-lookup"><span data-stu-id="264af-112">(Optional) Under **Description**, type a description of the translation rule, for example US International long-distance dialing.</span></span>

5. <span data-ttu-id="264af-113">Geben Sie im Abschnitt **Übersetzungsregel erstellen** des Dialogfelds die folgenden Werte ein:</span><span class="sxs-lookup"><span data-stu-id="264af-113">In the **Build a Translation Rule** section of the dialog box, enter values in the following fields:</span></span>

   - <span data-ttu-id="264af-114">**Anfangsziffern**: (Optional) Geben Sie die Anfangsziffern der Nummern ein, die Sie mit dem Muster abgleichen möchten.</span><span class="sxs-lookup"><span data-stu-id="264af-114">**Starting digits**: (Optional) Specify the leading digits of numbers you want the pattern to match.</span></span> <span data-ttu-id="264af-115">Geben Sie beispielsweise + in dieses Feld ein, um Nummern im E.164-Format abzugleichen (diese beginnen mit +).</span><span class="sxs-lookup"><span data-stu-id="264af-115">For example, enter + in this field to match numbers in E.164 format (which begin with +).</span></span>

   - <span data-ttu-id="264af-116">**Länge**: Geben Sie die Anzahl von Ziffern im Vergleichsmuster ein und wählen Sie aus, ob mit dem Muster Nummern abgeglichen werden sollen, die exakt diese Länge, mindestens diese Länge oder eine beliebige Länge aufweisen.</span><span class="sxs-lookup"><span data-stu-id="264af-116">**Length**: Specify the number of digits in the matching pattern and select whether you want the pattern to match numbers that are this length exactly, at least this length, or any length.</span></span> <span data-ttu-id="264af-117">Geben Sie beispielsweise in der Dropdownliste den Wert 11 und mindestens in der Dropdownliste ein, um Zahlen mit einer Länge von mindestens 11 Ziffern zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="264af-117">For example, enter 11 and selectAt least in the drop-down list to match numbers that are at least 11 digits in length.</span></span>

   - <span data-ttu-id="264af-118">**Zu entfernende Ziffern**: (Optional) Geben Sie die Anzahl von Anfangsziffern ein, die entfernt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="264af-118">**Digits to remove**: (Optional) Specify the number of starting digits to be removed.</span></span> <span data-ttu-id="264af-119">Geben Sie beispielsweise 1 ein, um den + vom Anfang der Zahl zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="264af-119">For example, enter 1 to strip out the+ from the beginning of the number.</span></span>

   - <span data-ttu-id="264af-120">**Hinzuzufügende Ziffern**: (Optional) Geben Sie die Ziffern ein, die der übersetzten Nummer vorangestellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="264af-120">**Digits to add**: (Optional) Specify digits to be prepended to the translated numbers.</span></span> <span data-ttu-id="264af-121">Geben Sie beispielsweise 011 ein, wenn bei Anwendung der Regel der übersetzten Nummer die Ziffernfolge 011 vorangestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="264af-121">For example, enter 011 if you want 011 to be prepended to the translated numbers when the rule is applied.</span></span>

     <span data-ttu-id="264af-p106">Die in diesen Feldern eingegebenen Werte werden in den Feldern **Muster für Vergleich** und **Übersetzungsregel** widergespiegelt. Wenn Sie beispielsweise die vorstehend genannten Beispielwerte verwenden, lautet der reguläre Ausdruck im Feld **Muster für Vergleich** wie folgt:</span><span class="sxs-lookup"><span data-stu-id="264af-p106">The values you enter in these fields are reflected in the **Pattern to match** and **Translation rule** fields. For example, if you specify the preceding example values, the resulting regular expression in the **Pattern to match** field is:</span></span>

     <span data-ttu-id="264af-124">^\+(\d{9}\d +) $</span><span class="sxs-lookup"><span data-stu-id="264af-124">^\+(\d{9}\d+)$</span></span>

     <span data-ttu-id="264af-125">Das Feld **Übersetzungsregel** gibt ein Muster für das Format der übersetzten Nummern an.</span><span class="sxs-lookup"><span data-stu-id="264af-125">The **Translation rule** field specifies a pattern for the format of translated numbers.</span></span> <span data-ttu-id="264af-126">Dieses Muster besteht aus zwei Teilen:</span><span class="sxs-lookup"><span data-stu-id="264af-126">This pattern has two parts:</span></span>

   - <span data-ttu-id="264af-127">Einem Wert (z. B. $1), der die Anzahl von Ziffern im Vergleichsmuster repräsentiert</span><span class="sxs-lookup"><span data-stu-id="264af-127">A value (for example, $1) that represents the number of digits in the matching pattern</span></span>

   - <span data-ttu-id="264af-128">(Optional) Einem Wert, den Sie durch eine Eingabe im Feld **Hinzuzufügende Ziffern** voranstellen können</span><span class="sxs-lookup"><span data-stu-id="264af-128">(Optional) A value that you can prepend by entering it in the **Digits to add** field</span></span>

     <span data-ttu-id="264af-129">Bei Verwendung der vorstehend genannten Beispiele wird der Wert 011$1 im Feld **Übersetzungsregel** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="264af-129">Using the preceding example values, 011$1 appears in the **Translation rule** field.</span></span>

     <span data-ttu-id="264af-130">Bei Anwendung dieser Übersetzungsregel wird die Nummer +441235551010 in 011441235551010 umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="264af-130">When this translation rule is applied, +441235551010 becomes 011441235551010.</span></span>

6. <span data-ttu-id="264af-131">Klicken Sie auf **OK**, um die Übersetzungsregel zu speichern.</span><span class="sxs-lookup"><span data-stu-id="264af-131">Click **OK** to save the translation rule.</span></span>

7. <span data-ttu-id="264af-132">Klicken Sie auf **OK**, um die Trunkkonfiguration zu speichern.</span><span class="sxs-lookup"><span data-stu-id="264af-132">Click **OK** to save the trunk configuration.</span></span>

8. <span data-ttu-id="264af-133">Klicken Sie auf der Seite **Trunkkonfiguration** auf **Commit** und klicken Sie anschließend auf **Commit für alle Elemente ausführen**.</span><span class="sxs-lookup"><span data-stu-id="264af-133">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="264af-134">Immer dann, wenn Sie eine Übersetzungsregel erstellen oder ändern, müssen Sie den Befehl **Commit für alle Elemente ausführen** ausführen, um die Konfigurationsänderung zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="264af-134">Whenever you create or modify a translation rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="264af-135">Ausführliche Informationen finden Sie unter [veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in Skype for Business](voice-route-config-changes.md) in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="264af-135">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

### <a name="to-define-a-translation-rule-manually"></a><span data-ttu-id="264af-136">So definieren Sie eine Übersetzungsregel manuell</span><span class="sxs-lookup"><span data-stu-id="264af-136">To define a translation rule manually</span></span>

1. <span data-ttu-id="264af-137">Öffnen Sie die Skype for Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="264af-137">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="264af-138">Wenn Sie mit der Definition einer Übersetzungsregel beginnen möchten, führen Sie die Schritte unter [Konfigurieren eines Trunks mit medienumgehung in Skype for Business Server](configure-trunk-with-media-bypass.md) bis Schritt 10 aus, oder [Konfigurieren Sie einen trunk ohne medienumgehung in Skype for Business Server](configure-trunk-without-media-bypass.md) bis Schritt 9.</span><span class="sxs-lookup"><span data-stu-id="264af-138">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md) through step 9.</span></span>

3. <span data-ttu-id="264af-139">Geben Sie im Feld **Name** auf der Seite **Neue Übersetzungsregel** oder **Übersetzungsregel bearbeiten** einen Namen ein, der das zu übersetzende Nummernmuster beschreibt.</span><span class="sxs-lookup"><span data-stu-id="264af-139">In the **Name** field on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

4. <span data-ttu-id="264af-140">Optional Geben Sie in **Beschreibung**eine Beschreibung der Übersetzungsregel ein, beispielsweise US-Auslands Wahl für Ferngespräche.</span><span class="sxs-lookup"><span data-stu-id="264af-140">(Optional) In **Description**, type a description of the translation rule, for example US International long-distance dialing.</span></span>

5. <span data-ttu-id="264af-141">Klicken Sie im unteren Bereich des Abschnitts **Übersetzungsregel erstellen** auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="264af-141">Click **Edit** at the bottom of the **Build a Translation Rule** section.</span></span>

6. <span data-ttu-id="264af-142">Geben Sie unter **Regulären Ausdruck eingeben** Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="264af-142">Enter the following in **Type a Regular Expression**:</span></span>

   - <span data-ttu-id="264af-143">Geben Sie unter **Übereinstimmung mit dem folgenden Muster** das Muster an, das für den Abgleich der zu übersetzenden Nummern verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="264af-143">In **Match this pattern**, specify the pattern that will be used to match the numbers to be translated.</span></span>

   - <span data-ttu-id="264af-144">Geben Sie unter **Übersetzungsregel** ein Muster für das Format der übersetzten Nummern an.</span><span class="sxs-lookup"><span data-stu-id="264af-144">In **Translation rule**, specify a pattern for the format of translated numbers.</span></span>

     <span data-ttu-id="264af-145">Wenn\+Sie beispielsweise ^ (\d{9}\d +) $ in **Übereinstimmung mit diesem Muster** and011 $1 in der **Übersetzungsregel**eingeben, wird die Regel + 441235551010 in 011441235551010 übersetzen.</span><span class="sxs-lookup"><span data-stu-id="264af-145">For example, if you enter ^\+(\d{9}\d+)$ in **Match this pattern** and011$1 in **Translation rule**, the rule will translate +441235551010 to 011441235551010.</span></span>

7. <span data-ttu-id="264af-146">Klicken Sie auf **OK**, um die Übersetzungsregel zu speichern.</span><span class="sxs-lookup"><span data-stu-id="264af-146">Click **OK** to save the translation rule.</span></span>

8. <span data-ttu-id="264af-147">Klicken Sie auf **OK**, um die Trunkkonfiguration zu speichern.</span><span class="sxs-lookup"><span data-stu-id="264af-147">Click **OK** to save the trunk configuration.</span></span>

9. <span data-ttu-id="264af-148">Klicken Sie auf der Seite **Trunkkonfiguration** auf **Commit** und klicken Sie anschließend auf **Commit für alle Elemente ausführen**.</span><span class="sxs-lookup"><span data-stu-id="264af-148">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="264af-149">Immer dann, wenn Sie eine Übersetzungsregel erstellen oder ändern, müssen Sie den Befehl **Commit für alle Elemente ausführen** ausführen, um die Konfigurationsänderung zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="264af-149">Whenever you create or modify a translation rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="264af-150">Ausführliche Informationen finden Sie unter [veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in Skype for Business](voice-route-config-changes.md) in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="264af-150">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="264af-151">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="264af-151">See also</span></span>

[<span data-ttu-id="264af-152">Konfigurieren eines Trunks mit medienumgehung in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="264af-152">Configure a trunk with media bypass in Skype for Business Server</span></span>](configure-trunk-with-media-bypass.md)

[<span data-ttu-id="264af-153">Konfigurieren eines Trunks ohne medienumgehung in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="264af-153">Configure a trunk without media bypass in Skype for Business Server</span></span>](configure-trunk-without-media-bypass.md)

[<span data-ttu-id="264af-154">Veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="264af-154">Publish pending changes to the voice routing configuration in Skype for Business</span></span>](voice-route-config-changes.md)

[<span data-ttu-id="264af-155">Bereitstellen der medienumgehung in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="264af-155">Deploy media bypass in Skype for Business Server</span></span>](deploy-media-bypass.md)

