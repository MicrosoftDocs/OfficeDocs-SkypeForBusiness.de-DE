---
title: Erstellen oder Ändern einer Normalisierungsregel in Skype für Unternehmen
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
description: 'Zusammenfassung: Informationen Sie zum definieren, erstellen und Ändern einer Normalisierungsregel in Skype für Business Server.'
ms.openlocfilehash: ef796d1484ec3848d7c6488127009f97ccc565ee
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882155"
---
# <a name="create-or-modify-a-normalization-rule-in-skype-for-business"></a><span data-ttu-id="be829-103">Erstellen oder Ändern einer Normalisierungsregel in Skype für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="be829-103">Create or modify a normalization rule in Skype for Business</span></span>

<span data-ttu-id="be829-104">**Zusammenfassung:** Informationen Sie zum definieren, erstellen und Ändern einer Normalisierungsregel in Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="be829-104">**Summary:** Learn how to define, create, and modify a normalization rule in Skype for Business Server.</span></span>

<span data-ttu-id="be829-105">Definieren, erstellen und Ändern von Normalisierungsregeln in Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="be829-105">Define, create, and modify normalization rules in Skype for Business Server.</span></span>

### <a name="to-define-a-normalization-rule-by-using-build-a-normalization-rule"></a><span data-ttu-id="be829-106">So definieren Sie eine Normalisierungsregel mit Normalisierungsregel erstellen</span><span class="sxs-lookup"><span data-stu-id="be829-106">To define a normalization rule by using Build a Normalization Rule</span></span>

1. <span data-ttu-id="be829-107">Öffnen von Skype Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="be829-107">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="be829-108">(Optional) Führen Sie die Schritte in [Erstellen oder Ändern von Wähleinstellungen in Skype für Business Server](dial-plans.md) bis Schritt 11 oder [Modify a Dial Plan](https://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx) bis Schritt 10.</span><span class="sxs-lookup"><span data-stu-id="be829-108">(Optional) Follow the steps in [Create or modify a dial plan in Skype for Business Server](dial-plans.md) through step 11 or [Modify a Dial Plan](https://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx) through step 10.</span></span>

3. <span data-ttu-id="be829-109">Geben Sie unter **Neue Normalisierungsregel** oder **Normalisierungsregel bearbeiten**einen Namen, der das im **Namen** (beispielsweise 5stellendurchwahl).) normalisierende Nummernmuster beschreibt.</span><span class="sxs-lookup"><span data-stu-id="be829-109">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example,5DigitExtension).</span></span>

4. <span data-ttu-id="be829-110">(Optional) Geben Sie in **Beschreibung** eine Beschreibung der Normalisierungsregel ein (beispielsweise „Übersetzt 5-stellige Durchwahlnummern“).</span><span class="sxs-lookup"><span data-stu-id="be829-110">(Optional) In **Description**, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

5. <span data-ttu-id="be829-111">Geben Sie im Abschnitt **Normalisierungsregel erstellen** Werte in die folgenden Felder ein:</span><span class="sxs-lookup"><span data-stu-id="be829-111">In **Build a Normalization Rule**, enter values in the following fields:</span></span>

   - <span data-ttu-id="be829-112">**Anfangsziffern** (Optional) Geben Sie die führenden Ziffern gewählter Nummern, die Sie das Muster abgleichen möchten.</span><span class="sxs-lookup"><span data-stu-id="be829-112">**Starting digits** (Optional) Specify the leading digits of dialed numbers you want the pattern to match.</span></span> <span data-ttu-id="be829-113">Wenn Sie das Muster abgleichen möchten gewählte type425 beispielsweise Zahlen mit 425 beginnt.</span><span class="sxs-lookup"><span data-stu-id="be829-113">For example, type425 if you want the pattern to match dialed numbers beginning with 425.</span></span>

   - <span data-ttu-id="be829-114">**Länge** Geben Sie die Anzahl der Nachkommastellen in das Vergleichsmuster, und wählen Sie, ob Übereinstimmung Nummern beliebiger Länge gewählten Übereinstimmung Rufnummern, die mindestens diese Länge sind oder das Muster dieser Länge genau entsprechen soll.</span><span class="sxs-lookup"><span data-stu-id="be829-114">**Length** Specify the number of digits in the matching pattern and select whether you want the pattern to match this length exactly, match dialed numbers that are at least this length, or match dialed numbers of any length.</span></span>

   - <span data-ttu-id="be829-115">**So entfernen Sie Ziffern** (Optional) Geben Sie die Anzahl von Anfangsziffern ein, die aus gewählten Nummern entfernt werden Sie das Muster abgleichen möchten.</span><span class="sxs-lookup"><span data-stu-id="be829-115">**Digits to remove** (Optional) Specify the number of starting digits to be removed from dialed numbers you want the pattern to match.</span></span>

   - <span data-ttu-id="be829-116">**Hinzuzufügende Ziffern** (Optional) Geben Sie die Ziffern auf gewählten Nummern hinzugefügt werden soll, dass Sie das Muster abgleichen möchten.</span><span class="sxs-lookup"><span data-stu-id="be829-116">**Digits to add** (Optional) Specify digits to be added to dialed numbers you want the pattern to match.</span></span>

    <span data-ttu-id="be829-117">Die in diesen Feldern eingegebenen Werte werden in den Feldern **Muster für Vergleich** und **Übersetzungsregel** widergespiegelt.</span><span class="sxs-lookup"><span data-stu-id="be829-117">The values you enter in these fields are reflected in **Pattern to match** and **Translation rule**.</span></span> <span data-ttu-id="be829-118">Beispielsweise wenn Sie leer ist, Typ7 **Starten Ziffern** in das Feld **Länge verlassen** und wählen Sie **genau**, und geben Sie 0 in **Ziffern zu entfernen**, wird der resultierende reguläre Ausdruck in dem **Muster abgleichen** :</span><span class="sxs-lookup"><span data-stu-id="be829-118">For example, if you leave **Starting digits** empty, type7 into the **Length** field and select **Exactly**, and specify 0 in **Digits to remove**, the resulting regular expression in the **Pattern to match** is:</span></span>

    <span data-ttu-id="be829-119">^(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="be829-119">^(\d{7})$</span></span>

6. <span data-ttu-id="be829-120">Geben Sie in **Übersetzungsregel** ein Muster für das Format der übersetzten E.164-Telefonnummern ein:</span><span class="sxs-lookup"><span data-stu-id="be829-120">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers as follows:</span></span>

   - <span data-ttu-id="be829-121">Ein Wert, der die Anzahl von Ziffern repräsentiert, die im Vergleichsmuster angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="be829-121">A value that represents the number of digits specified in the matching pattern.</span></span> <span data-ttu-id="be829-122">Wenn das Vergleichsmuster beispielsweise ^(\d{7})$ dann$ 1 in der Regel stellt 7 Ziffer gewählter Nummern.</span><span class="sxs-lookup"><span data-stu-id="be829-122">For example, if the matching pattern is ^(\d{7})$ then$1 in the translation rule represents 7-digit dialed numbers.</span></span>

   - <span data-ttu-id="be829-123">(Optional) Geben Sie einen Wert in das Feld **hinzuzufügende Ziffern** an Stellen die übersetzte Nummer (beispielsweise + 1425) vorangestellt werden.</span><span class="sxs-lookup"><span data-stu-id="be829-123">(Optional) Type a value into the **Digits to add** field to specify digits to be prepended to the translated number (for example,+1425).</span></span>

    <span data-ttu-id="be829-124">Wenn enthält **Muster an,** beispielsweise ^(\d{7})$ als das Muster für die gewählten Nummern und **übersetzungsregel** enthält + 1425$ 1 als das Muster für das e. 164 Telefonnummern, übersetzt die Regel 5550100 in + 14255550100.</span><span class="sxs-lookup"><span data-stu-id="be829-124">For example, if **Pattern to match** contains^(\d{7})$ as the pattern for dialed numbers and **Translation rule** contains+1425$1 as the pattern for E.164 phone numbers, the rule normalizes 5550100 to +14255550100.</span></span>

7. <span data-ttu-id="be829-125">(Optional) Falls die Normalisierungsregel eine interne Telefonnummer des Unternehmens ergibt, klicken Sie auf **Interne Durchwahl**.</span><span class="sxs-lookup"><span data-stu-id="be829-125">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

8. <span data-ttu-id="be829-p104">(Optional) Geben Sie eine Nummer zum Testen der Normalisierungsregel ein und klicken Sie auf **Los**. Die Testergebnisse werden unterhalb von **Geben Sie eine Testnummer ein** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="be829-p104">(Optional) Enter a number to test the normalization rule, and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="be829-128">Sie können eine Normalisierungsregel speichern, die den Test nicht bestanden hat und sie später neu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="be829-128">You can save a normalization rule that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="be829-129">Weitere Informationen hierzu finden Sie unter [VoIP-Routing testen](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx).</span><span class="sxs-lookup"><span data-stu-id="be829-129">For details, see [Test Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx).</span></span>

9. <span data-ttu-id="be829-130">Klicken Sie auf **OK**, um die Normalisierungsregel zu speichern.</span><span class="sxs-lookup"><span data-stu-id="be829-130">Click **OK** to save the normalization rule.</span></span>

10. <span data-ttu-id="be829-131">Klicken Sie auf **OK**, um die Wähleinstellungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="be829-131">Click **OK** to save the dial plan.</span></span>

11. <span data-ttu-id="be829-132">Klicken Sie auf der Seite **Wählplan** auf **Commit ausführen** und anschließend auf **Commit für alle Elemente ausführen**.</span><span class="sxs-lookup"><span data-stu-id="be829-132">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="be829-133">Jedes Mal, wenn Sie eine Normalisierungsregel erstellen oder ändern, müssen Sie den Befehl **Commit für alle** ausführen, um die Konfigurationsänderung zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="be829-133">Whenever you create or change a normalization rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="be829-134">Weitere Informationen hierzu finden Sie unter [Veröffentlichen ausstehenden Änderungen an der VoIP-Routingkonfiguration in Skype für Unternehmen](voice-route-config-changes.md) in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="be829-134">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

### <a name="to-define-a-normalization-rule-manually"></a><span data-ttu-id="be829-135">So definieren Sie eine Normalisierungsregel manuell</span><span class="sxs-lookup"><span data-stu-id="be829-135">To define a normalization rule manually</span></span>

1. <span data-ttu-id="be829-136">Öffnen von Skype Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="be829-136">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="be829-137">(Optional) Führen Sie die Schritte in [Erstellen oder Ändern von Wähleinstellungen in Skype für Business Server](dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="be829-137">(Optional) Follow the steps in [Create or modify a dial plan in Skype for Business Server](dial-plans.md).</span></span>

3. <span data-ttu-id="be829-138">Geben Sie unter **Neue Normalisierungsregel** oder **Normalisierungsregel bearbeiten**einen Namen, der das im **Feld Name** (beispielsweise Name der Normalisierung rule5DigitExtension) normalisierende Nummernmuster beschreibt.</span><span class="sxs-lookup"><span data-stu-id="be829-138">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example, name the normalization rule5DigitExtension).</span></span>

4. <span data-ttu-id="be829-139">(Optional) Geben Sie im Feld **Beschreibung** eine Beschreibung der Normalisierungsregel ein (beispielsweise „Übersetzt 5-stellige Durchwahlnummern“).</span><span class="sxs-lookup"><span data-stu-id="be829-139">(Optional) In **Description** field, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

5. <span data-ttu-id="be829-140">Klicken Sie in **Normalisierungsregel erstellen** auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="be829-140">In **Build a Normalization Rule**, click **Edit**.</span></span>

6. <span data-ttu-id="be829-141">Geben Sie in **Regulären Ausdruck eingeben** Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="be829-141">Enter the following in **Type a Regular Expression**:</span></span>

   - <span data-ttu-id="be829-142">Geben Sie in **Dieses Muster abgleichen** das Muster an, das für den Abgleich der gewählten Telefonnummer verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="be829-142">In **Match this pattern**, specify the pattern that you want to use to match the dialed phone number.</span></span>

   - <span data-ttu-id="be829-143">Geben Sie in **Übersetzungsregel** ein Muster für das Format der übersetzten E.164-Telefonnummern ein.</span><span class="sxs-lookup"><span data-stu-id="be829-143">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers.</span></span>

    <span data-ttu-id="be829-144">Beispiel: bei Eingabe von ^(\d{7})$ in **dieses Muster abgleichen** und + 1425$ 1 in **übersetzungsregel**, die Regel 5550100 in + 14255550100 normalisiert.</span><span class="sxs-lookup"><span data-stu-id="be829-144">For example, if you enter ^(\d{7})$ in **Match this pattern** and+1425$1 in **Translation rule**, the rule normalizes 5550100 to +14255550100.</span></span>

7. <span data-ttu-id="be829-145">(Optional) Falls die Normalisierungsregel eine interne Telefonnummer des Unternehmens ergibt, klicken Sie auf **Interne Durchwahl**.</span><span class="sxs-lookup"><span data-stu-id="be829-145">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

8. <span data-ttu-id="be829-p107">(Optional) Geben Sie eine Nummer zum Testen der Normalisierungsregel ein und klicken Sie auf **Los**. Die Testergebnisse werden unterhalb von **Geben Sie eine Testnummer ein** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="be829-p107">(Optional) Enter a number to test the normalization rule and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>

9. <span data-ttu-id="be829-148">Klicken Sie auf **OK**, um die Normalisierungsregel zu speichern.</span><span class="sxs-lookup"><span data-stu-id="be829-148">Click **OK** to save the normalization rule.</span></span>

10. <span data-ttu-id="be829-149">Klicken Sie auf **OK**, um die Wähleinstellungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="be829-149">Click **OK** to save the dial plan.</span></span>

11. <span data-ttu-id="be829-150">Klicken Sie auf der Seite **Wählplan** auf **Commit ausführen** und anschließend auf **Commit für alle Elemente ausführen**.</span><span class="sxs-lookup"><span data-stu-id="be829-150">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="be829-151">Jedes Mal, wenn Sie eine Normalisierungsregel erstellen oder ändern, müssen Sie den Befehl **Commit für alle** ausführen, um die Konfigurationsänderung zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="be829-151">Whenever you create or change a normalization rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="be829-152">Weitere Informationen hierzu finden Sie unter [Veröffentlichen ausstehenden Änderungen an der VoIP-Routingkonfiguration in Skype für Unternehmen](voice-route-config-changes.md) in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="be829-152">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>


