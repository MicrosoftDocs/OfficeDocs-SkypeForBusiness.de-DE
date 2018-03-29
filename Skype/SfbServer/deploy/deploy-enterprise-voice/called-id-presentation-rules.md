---
title: Erstellen oder Ändern einer Übersetzungsregel für die Darstellung der ID des Angerufenen in Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
description: 'Zusammenfassung: Erfahren Sie, wie Sie eine übersetzungsregel definieren, indem Sie mit dem Erstellen einer Übersetzungsregel-Tool in Skype für Business Server 2015.'
ms.openlocfilehash: aa433375ad4dfa2dcc0c141d36b6d51ae28647f1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server-2015"></a><span data-ttu-id="6a464-103">Erstellen oder Ändern einer Übersetzungsregel für die Darstellung der ID des Angerufenen in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="6a464-103">Create or modify a translation rule for called ID presentation in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="6a464-104">**Zusammenfassung:** Hier erfahren Sie, wie Sie eine übersetzungsregel definieren, indem Sie mit dem Erstellen einer Übersetzungsregel-Tool in Skype für Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="6a464-104">**Summary:** Learn how to define a translation rule by using the Build a Translation Rule tool in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="6a464-105">Gehen Sie folgendermaßen vor, wenn Sie eine übersetzungsregel definieren durch Eingabe einer Gruppe von Werten in das Tool **eine Übersetzungsregel erstellen** und Aktivieren von Skype Business Server-Systemsteuerung auf den entsprechenden Vergleichsmuster und die übersetzungsregel zu generieren möchten.</span><span class="sxs-lookup"><span data-stu-id="6a464-105">Follow these steps if you want to define a translation rule by entering a set of values in the **Build a Translation Rule** tool and enabling Skype for Business Server Control Panel to generate the corresponding matching pattern and translation rule for you.</span></span> <span data-ttu-id="6a464-106">Alternativ können Sie manuell einen regulären Ausdruck erstellen, um das Vergleichsmuster und die Übersetzungsregel zu definieren.</span><span class="sxs-lookup"><span data-stu-id="6a464-106">Alternatively, you can a write regular expression manually to define the matching pattern and translation rule.</span></span> <span data-ttu-id="6a464-107">Weitere Informationen hierzu finden Sie unter [Erstellen oder Ändern einer Übersetzung Regel manuell](http://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx).</span><span class="sxs-lookup"><span data-stu-id="6a464-107">For details, see [Create or Modify a Translation Rule Manually](http://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx).</span></span>
  
### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a><span data-ttu-id="6a464-108">So definieren Sie eine Regel mit dem Tool zum Erstellen einer Übersetzungsregel</span><span class="sxs-lookup"><span data-stu-id="6a464-108">To define a rule by using the Build a Translation Rule tool</span></span>

1. <span data-ttu-id="6a464-109">Öffnen von Skype Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="6a464-109">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="6a464-110">Führen Sie zur Definition einer übersetzungsregel, führen Sie die Schritte in [Konfigurieren eines Trunks mit Medien in Skype für Business Server 2015 umgehen](configure-trunk-with-media-bypass.md) bis Schritt 10 oder [Konfigurieren eines Trunks ohne Medien in Skype für Business Server 2015 umgehen](configure-trunk-without-media-bypass.md) bis Schritt 9.</span><span class="sxs-lookup"><span data-stu-id="6a464-110">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server 2015](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server 2015](configure-trunk-without-media-bypass.md) through step 9.</span></span>
    
3. <span data-ttu-id="6a464-111">Geben Sie unter **Name** auf der Seite **Neue Übersetzungsregel** oder **Übersetzungsregel bearbeiten** einen Namen ein, der das zu übersetzende Nummernmuster beschreibt.</span><span class="sxs-lookup"><span data-stu-id="6a464-111">Under **Name** on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>
    
4. <span data-ttu-id="6a464-112">(Optional) Geben Sie unter **Beschreibung**eine Beschreibung der übersetzungsregel für Beispiel uns International Ferngespräche.</span><span class="sxs-lookup"><span data-stu-id="6a464-112">(Optional) Under **Description**, type a description of the translation rule, for example US International long-distance dialing.</span></span>
    
5. <span data-ttu-id="6a464-113">Geben Sie im Abschnitt **Übersetzungsregel erstellen** des Dialogfelds die folgenden Werte ein:</span><span class="sxs-lookup"><span data-stu-id="6a464-113">In the **Build a Translation Rule** section of the dialog box, enter values in the following fields:</span></span>
    
   - <span data-ttu-id="6a464-114">**Anfangsziffern**: (Optional) Geben Sie die Anfangsziffern der Nummern ein, die Sie mit dem Muster abgleichen möchten.</span><span class="sxs-lookup"><span data-stu-id="6a464-114">**Starting digits**: (Optional) Specify the leading digits of numbers you want the pattern to match.</span></span> <span data-ttu-id="6a464-115">Beispiel: Geben Sie + in dieses Feld, um Nummern im e. 164-format (die beginnen mit +).</span><span class="sxs-lookup"><span data-stu-id="6a464-115">For example, enter + in this field to match numbers in E.164 format (which begin with +).</span></span>
    
   - <span data-ttu-id="6a464-116">**Länge**: Geben Sie die Anzahl von Ziffern im Vergleichsmuster ein und wählen Sie aus, ob mit dem Muster Nummern abgeglichen werden sollen, die exakt diese Länge, mindestens diese Länge oder eine beliebige Länge aufweisen.</span><span class="sxs-lookup"><span data-stu-id="6a464-116">**Length**: Specify the number of digits in the matching pattern and select whether you want the pattern to match numbers that are this length exactly, at least this length, or any length.</span></span> <span data-ttu-id="6a464-117">Geben Sie beispielsweise 11 und SelectAt in der Dropdown-Liste mit Zahlen übereinstimmen, die mindestens 11 Ziffern umfassen sind mindestens.</span><span class="sxs-lookup"><span data-stu-id="6a464-117">For example, enter 11 and selectAt least in the drop-down list to match numbers that are at least 11 digits in length.</span></span>
    
   - <span data-ttu-id="6a464-118">**Zu entfernende Ziffern**: (Optional) Geben Sie die Anzahl von Anfangsziffern ein, die entfernt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6a464-118">**Digits to remove**: (Optional) Specify the number of starting digits to be removed.</span></span> <span data-ttu-id="6a464-119">Geben Sie beispielsweise 1 entfernen, um die + vom Beginn der Zahl.</span><span class="sxs-lookup"><span data-stu-id="6a464-119">For example, enter 1 to strip out the+ from the beginning of the number.</span></span>
    
   - <span data-ttu-id="6a464-120">**Hinzuzufügende Ziffern**: (Optional) Geben Sie die Ziffern ein, die der übersetzten Nummer vorangestellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6a464-120">**Digits to add**: (Optional) Specify digits to be prepended to the translated numbers.</span></span> <span data-ttu-id="6a464-121">Geben Sie beispielsweise 011 wie gewünscht 011 an der übersetzten Nummern vorangestellt werden, wenn die Regel angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="6a464-121">For example, enter 011 if you want 011 to be prepended to the translated numbers when the rule is applied.</span></span>
    
    <span data-ttu-id="6a464-p106">Die in diesen Feldern eingegebenen Werte werden in den Feldern **Muster für Vergleich** und **Übersetzungsregel** widergespiegelt. Wenn Sie beispielsweise die vorstehend genannten Beispielwerte verwenden, lautet der reguläre Ausdruck im Feld **Muster für Vergleich** wie folgt:</span><span class="sxs-lookup"><span data-stu-id="6a464-p106">The values you enter in these fields are reflected in the **Pattern to match** and **Translation rule** fields. For example, if you specify the preceding example values, the resulting regular expression in the **Pattern to match** field is:</span></span>
    
    <span data-ttu-id="6a464-124">^\+(\d{9}\d+)$</span><span class="sxs-lookup"><span data-stu-id="6a464-124">^\+(\d{9}\d+)$</span></span>
    
    <span data-ttu-id="6a464-p107">Das Feld **Übersetzungsregel** gibt ein Muster für das Format der übersetzten Nummern an. Dieses Muster besteht aus zwei Teilen:</span><span class="sxs-lookup"><span data-stu-id="6a464-p107">The **Translation rule** field specifies a pattern for the format of translated numbers. This pattern has two parts:</span></span>
    
   - <span data-ttu-id="6a464-127">Ein Wert (z. B. $1), der die Anzahl der Nachkommastellen in das Vergleichsmuster darstellt</span><span class="sxs-lookup"><span data-stu-id="6a464-127">A value (for example, $1) that represents the number of digits in the matching pattern</span></span>
    
   - <span data-ttu-id="6a464-128">(Optional) Einem Wert, den Sie durch eine Eingabe im Feld **Hinzuzufügende Ziffern** voranstellen können</span><span class="sxs-lookup"><span data-stu-id="6a464-128">(Optional) A value that you can prepend by entering it in the **Digits to add** field</span></span>
    
    <span data-ttu-id="6a464-129">Verwendung der vorstehend 011$ 1 wird im Feld **übersetzungsregel** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6a464-129">Using the preceding example values, 011$1 appears in the **Translation rule** field.</span></span>
    
    <span data-ttu-id="6a464-130">Bei Anwendung dieser Übersetzungsregel wird die Nummer +441235551010 in 011441235551010 umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="6a464-130">When this translation rule is applied, +441235551010 becomes 011441235551010.</span></span>
    
6. <span data-ttu-id="6a464-131">Klicken Sie auf **OK**, um die Übersetzungsregel zu speichern.</span><span class="sxs-lookup"><span data-stu-id="6a464-131">Click **OK** to save the translation rule.</span></span>
    
7. <span data-ttu-id="6a464-132">Klicken Sie auf **OK**, um die Trunkkonfiguration zu speichern.</span><span class="sxs-lookup"><span data-stu-id="6a464-132">Click **OK** to save the trunk configuration.</span></span>
    
8. <span data-ttu-id="6a464-133">Klicken Sie auf der Seite **Trunkkonfiguration** auf **Commit** und klicken Sie anschließend auf **Commit für alle Elemente ausführen**.</span><span class="sxs-lookup"><span data-stu-id="6a464-133">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span> 
    
   > [!NOTE]
   > <span data-ttu-id="6a464-134">Immer dann, wenn Sie eine Übersetzungsregel erstellen oder ändern, müssen Sie den Befehl **Commit für alle Elemente ausführen** ausführen, um die Konfigurationsänderung zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="6a464-134">Whenever you create or modify a translation rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="6a464-135">Weitere Informationen hierzu finden Sie unter [Veröffentlichen ausstehenden Änderungen an der VoIP-Routingkonfiguration in Skype für Business 2015](voice-route-config-changes.md) in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="6a464-135">For details, see [Publish pending changes to the voice routing configuration in Skype for Business 2015](voice-route-config-changes.md) in the Operations documentation.</span></span>
  
### <a name="to-define-a-translation-rule-manually"></a><span data-ttu-id="6a464-136">So definieren Sie eine Übersetzungsregel manuell</span><span class="sxs-lookup"><span data-stu-id="6a464-136">To define a translation rule manually</span></span>

1. <span data-ttu-id="6a464-137">Öffnen von Skype Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="6a464-137">Open Skype for Business Server Control Panel</span></span>
    
2. <span data-ttu-id="6a464-138">Führen Sie zur Definition einer übersetzungsregel, führen Sie die Schritte in [Konfigurieren eines Trunks mit Medien in Skype für Business Server 2015 umgehen](configure-trunk-with-media-bypass.md) bis Schritt 10 oder [Konfigurieren eines Trunks ohne Medien in Skype für Business Server 2015 umgehen](configure-trunk-without-media-bypass.md) bis Schritt 9.</span><span class="sxs-lookup"><span data-stu-id="6a464-138">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server 2015](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server 2015](configure-trunk-without-media-bypass.md) through step 9.</span></span>
    
3. <span data-ttu-id="6a464-139">Geben Sie im Feld **Name** auf der Seite **Neue Übersetzungsregel** oder **Übersetzungsregel bearbeiten** einen Namen ein, der das zu übersetzende Nummernmuster beschreibt.</span><span class="sxs-lookup"><span data-stu-id="6a464-139">In the **Name** field on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>
    
4. <span data-ttu-id="6a464-140">(Optional) Geben Sie eine Beschreibung der übersetzungsregel, beispielsweise uns International Ferngespräche wählen im Feld **Beschreibung**.</span><span class="sxs-lookup"><span data-stu-id="6a464-140">(Optional) In **Description**, type a description of the translation rule, for example US International long-distance dialing.</span></span>
    
5. <span data-ttu-id="6a464-141">Klicken Sie im unteren Bereich des Abschnitts **Übersetzungsregel erstellen** auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="6a464-141">Click **Edit** at the bottom of the **Build a Translation Rule** section.</span></span>
    
6. <span data-ttu-id="6a464-142">Geben Sie unter **Regulären Ausdruck eingeben** Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="6a464-142">Enter the following in **Type a Regular Expression**:</span></span>
    
   - <span data-ttu-id="6a464-143">Geben Sie unter **Übereinstimmung mit dem folgenden Muster** das Muster an, das für den Abgleich der zu übersetzenden Nummern verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="6a464-143">In **Match this pattern**, specify the pattern that will be used to match the numbers to be translated.</span></span>
    
   - <span data-ttu-id="6a464-144">Geben Sie unter **Übersetzungsregel** ein Muster für das Format der übersetzten Nummern an.</span><span class="sxs-lookup"><span data-stu-id="6a464-144">In **Translation rule**, specify a pattern for the format of translated numbers.</span></span>
    
    <span data-ttu-id="6a464-145">Beispiel: bei Eingabe ^\+(\d{9}\d+)$ in **dieses Muster abgleichen** and011$ 1 in **übersetzungsregel**, die Regel + 441235551010 in 011441235551010 übersetzt.</span><span class="sxs-lookup"><span data-stu-id="6a464-145">For example, if you enter ^\+(\d{9}\d+)$ in **Match this pattern** and011$1 in **Translation rule**, the rule will translate +441235551010 to 011441235551010.</span></span>
    
7. <span data-ttu-id="6a464-146">Klicken Sie auf **OK**, um die Übersetzungsregel zu speichern.</span><span class="sxs-lookup"><span data-stu-id="6a464-146">Click **OK** to save the translation rule.</span></span>
    
8. <span data-ttu-id="6a464-147">Klicken Sie auf **OK**, um die Trunkkonfiguration zu speichern.</span><span class="sxs-lookup"><span data-stu-id="6a464-147">Click **OK** to save the trunk configuration.</span></span>
    
9. <span data-ttu-id="6a464-148">Klicken Sie auf der Seite **Trunkkonfiguration** auf **Commit** und klicken Sie anschließend auf **Commit für alle Elemente ausführen**.</span><span class="sxs-lookup"><span data-stu-id="6a464-148">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="6a464-149">Immer dann, wenn Sie eine Übersetzungsregel erstellen oder ändern, müssen Sie den Befehl **Commit für alle Elemente ausführen** ausführen, um die Konfigurationsänderung zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="6a464-149">Whenever you create or modify a translation rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="6a464-150">Weitere Informationen hierzu finden Sie unter [Veröffentlichen ausstehenden Änderungen an der VoIP-Routingkonfiguration in Skype für Business 2015](voice-route-config-changes.md) in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="6a464-150">For details, see [Publish pending changes to the voice routing configuration in Skype for Business 2015](voice-route-config-changes.md) in the Operations documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6a464-151">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6a464-151">See also</span></span>

#### 

[<span data-ttu-id="6a464-152">Konfigurieren eines Trunks mit medienumgehung in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="6a464-152">Configure a trunk with media bypass in Skype for Business Server 2015</span></span>](configure-trunk-with-media-bypass.md)
  
[<span data-ttu-id="6a464-153">Konfigurieren eines Trunks ohne medienumgehung in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="6a464-153">Configure a trunk without media bypass in Skype for Business Server 2015</span></span>](configure-trunk-without-media-bypass.md)
  
[<span data-ttu-id="6a464-154">Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in Skype für Business 2015</span><span class="sxs-lookup"><span data-stu-id="6a464-154">Publish pending changes to the voice routing configuration in Skype for Business 2015</span></span>](voice-route-config-changes.md)
#### 

[<span data-ttu-id="6a464-155">Bereitstellen von medienumgehung in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="6a464-155">Deploy media bypass in Skype for Business Server 2015</span></span>](deploy-media-bypass.md)

