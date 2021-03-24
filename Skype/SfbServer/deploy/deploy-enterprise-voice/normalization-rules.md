---
title: Erstellen oder Ändern einer Normalisierungsregel in Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
description: 'Zusammenfassung: Informationen zum Definieren, Erstellen und Ändern einer Normalisierungsregel in Skype for Business Server.'
ms.openlocfilehash: 3550e27884d125f065c4688fec2ace797f9e8ce2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103391"
---
# <a name="create-or-modify-a-normalization-rule-in-skype-for-business"></a>Erstellen oder Ändern einer Normalisierungsregel in Skype for Business

**Zusammenfassung:** Erfahren Sie, wie Sie eine Normalisierungsregel in Skype for Business Server definieren, erstellen und ändern.

Definieren, Erstellen und Ändern von Normalisierungsregeln in Skype for Business Server.

### <a name="to-define-a-normalization-rule-by-using-build-a-normalization-rule"></a>So definieren Sie eine Normalisierungsregel mithilfe einer Normalisierungsregel erstellen

1. Öffnen der Skype for Business Server-Systemsteuerung

2. (Optional) Führen Sie die Schritte unter Erstellen oder Ändern eines Wählplans [in Skype for Business Server](dial-plans.md) durch Schritt 11 oder Ändern [eines](/previous-versions/office/lync-server-2013/lync-server-2013-modify-a-dial-plan) Wählplans über Schritt 10 aus.

3. Geben **Sie in Neue Normalisierungsregel** oder **Normalisierungsregel** bearbeiten einen Namen ein, der das Normalisierungsmuster in **Name** beschreibt (z. B. 5DigitExtension).

4. (Optional) Geben **Sie in Beschreibung** eine Beschreibung der Normalisierungsregel ein (z. B. "Übersetzt 5-stellige Erweiterungen").

5. Geben **Sie in Build a Normalization Rule** Werte in die folgenden Felder ein:

   - **Anfangsziffern** (Optional) Geben Sie die führenden Ziffern von gewählten Nummern an, die mit dem Muster übereinstimmen soll. Geben Sie z. B.425 ein, wenn das Muster den gewählten Nummern ab 425 entsprechen soll.

   - **Length** Geben Sie die Anzahl der Ziffern im übereinstimmenden Muster an, und wählen Sie aus, ob das Muster genau mit dieser Länge übereinstimmen soll, ob gewählte Nummern mit mindestens dieser Länge übereinstimmen oder ob gewählte Nummern beliebiger Länge übereinstimmen sollen.

   - **Zu entfernende** Ziffern (Optional) Geben Sie die Anzahl der Anfangsziffern an, die aus gewählten Nummern entfernt werden sollen, die mit dem Muster übereinstimmen sollen.

   - **Hinzuzufügende** Ziffern (Optional) Geben Sie Ziffern an, die gewählten Nummern hinzugefügt werden sollen, die mit dem Muster übereinstimmen sollen.

     Die Werte, die Sie in diese Felder eingeben, werden in **Muster für Übereinstimmung** und **Übersetzungsregel angezeigt.** Wenn Sie z.  B. Startziffern leer lassen, geben Sie7 in das Feld **Länge** ein, und wählen Sie **Exakt** aus, und geben Sie 0 in **Zu** entfernende Ziffern an, ist der resultierende reguläre Ausdruck im Muster, das übereinstimmen **soll:**

     ^(\d{7})$

6. Geben **Sie in** Übersetzungsregel ein Muster für das Format der übersetzten E.164-Telefonnummern wie folgt an:

   - Ein Wert, der die Anzahl der Im Vergleichsmuster angegebenen Ziffern darstellt. Wenn das Übereinstimmende Muster beispielsweise ^(\d )$ ist, stellt $1 in der Übersetzungsregel {7} 7-stellige gewählte Nummern dar.

   - (Optional) Geben Sie einen Wert in das Feld Ziffern **ein,** das hinzugefügt werden soll, um Ziffern anzugeben, die der übersetzten Zahl voranstellen sollen (z. B. +1425).

     Wenn beispielsweise  Muster für Übereinstimmung ^(\d )$ als Muster für gewählte Nummern enthält und {7} übersetzungsregel +1425$1 als Muster für E.164-Telefonnummern enthält, normalisiert die Regel 5550100 bis +14255550100. 

7. (Optional) Wenn die Normalisierungsregel zu einer telefonnummer führt, die in Ihrer Organisation intern ist, wählen Sie **Interne Durchwahl aus.**

8. (Optional) Geben Sie eine Zahl ein, um die Normalisierungsregel zu testen, und klicken Sie dann auf **Los**. Die Testergebnisse werden unterhalb von **Geben Sie eine Testnummer ein** angezeigt.

    > [!NOTE]
    > Sie können eine Normalisierungsregel speichern, die den Test noch nicht bestanden hat, und sie später erneut konfigurieren. Ausführliche Informationen dazu finden Sie unter [Test Voice Routing](/previous-versions/office/lync-server-2013/lync-server-2013-test-voice-routing).

9. Klicken Sie **auf OK,** um die Normalisierungsregel zu speichern.

10. Klicken Sie **auf OK,** um den Wählplan zu speichern.

11. Klicken Sie auf der Seite **Wähleinstellungen** auf **Commit** und anschließend auf **Commit für alle**.

    > [!NOTE]
    > Wenn Sie eine Normalisierungsregel erstellen oder ändern, müssen Sie den Befehl **Commit für** alle ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie [unter Veröffentlichen ausstehender Änderungen an der Voiceroutingkonfiguration in Skype for Business](voice-route-config-changes.md) in der Betriebsdokumentation.

### <a name="to-define-a-normalization-rule-manually"></a>So definieren Sie eine Normalisierungsregel manuell

1. Öffnen der Skype for Business Server-Systemsteuerung

2. (Optional) Führen Sie die Schritte unter [Erstellen oder Ändern eines Wählplans in Skype for Business Server aus.](dial-plans.md)

3. Geben **Sie in Neue Normalisierungsregel** oder **Normalisierungsregel** bearbeiten einen Namen ein, der das normalisierte Nummernmuster in **Name** beschreibt (nennen Sie beispielsweise die Normalisierungsregel5DigitExtension).

4. (Optional) Geben **Sie im** Feld Beschreibung eine Beschreibung der Normalisierungsregel ein (z. B. "Übersetzt 5-stellige Erweiterungen").

5. Klicken **Sie in Build a Normalization Rule** auf **Bearbeiten**.

6. Geben Sie in **Regulären Ausdruck eingeben** Folgendes ein:

   - Geben **Sie unter Dieses Muster übereinstimmen** das Muster an, das Sie verwenden möchten, um der gewählten Telefonnummer zu entsprechen.

   - Geben **Sie in** Übersetzungsregel ein Muster für das Format der übersetzten E.164-Telefonnummern an.

     Wenn Sie beispielsweise ^(\d )$ in Übereinstimmung mit diesem Muster {7} und+1425$1 in Übersetzungsregel eingeben, normalisiert die Regel 5550100 bis +14255550100.  

7. (Optional) Wenn die Normalisierungsregel zu einer telefonnummer führt, die in Ihrer Organisation intern ist, wählen Sie **Interne Durchwahl aus.**

8. (Optional) Geben Sie eine Zahl ein, um die Normalisierungsregel zu testen, und klicken Sie dann auf **Los**. Die Testergebnisse werden unterhalb von **Geben Sie eine Testnummer ein** angezeigt.

9. Klicken Sie **auf OK,** um die Normalisierungsregel zu speichern.

10. Klicken Sie **auf OK,** um den Wählplan zu speichern.

11. Klicken Sie auf der Seite **Wähleinstellungen** auf **Commit** und anschließend auf **Commit für alle**.

    > [!NOTE]
    > Wenn Sie eine Normalisierungsregel erstellen oder ändern, müssen Sie den Befehl **Commit für** alle ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie [unter Veröffentlichen ausstehender Änderungen an der Voiceroutingkonfiguration in Skype for Business](voice-route-config-changes.md) in der Betriebsdokumentation.