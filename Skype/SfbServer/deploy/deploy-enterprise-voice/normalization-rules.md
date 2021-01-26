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
ms.openlocfilehash: 6f8619304e9d3d801dfa430e6addb5105a2b82a2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830765"
---
# <a name="create-or-modify-a-normalization-rule-in-skype-for-business"></a>Erstellen oder Ändern einer Normalisierungsregel in Skype for Business

**Zusammenfassung:** Erfahren Sie, wie Sie eine Normalisierungsregel in Skype for Business Server definieren, erstellen und ändern.

Definieren, Erstellen und Ändern von Normalisierungsregeln in Skype for Business Server.

### <a name="to-define-a-normalization-rule-by-using-build-a-normalization-rule"></a>So definieren Sie eine Normalisierungsregel mithilfe von "Normalisierungsregel erstellen"

1. Öffnen der Skype for Business Server-Systemsteuerung

2. (Optional) Führen Sie die Schritte unter Erstellen oder Ändern eines Wählplans [in Skype for Business Server](dial-plans.md) bis Schritt 11 oder [Ändern](https://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx) eines Wählplans bis Schritt 10 aus.

3. Geben **Sie in "Neue** Normalisierungsregel" oder **"Normalisierungsregel** bearbeiten" einen Namen ein, der das normalisierte Nummernmuster **im** Namen beschreibt (z. B. 5DigitExtension).

4. (Optional) Geben **Sie** in "Beschreibung" eine Beschreibung der Normalisierungsregel ein (z. B. "Übersetzt 5-stellige Erweiterungen").

5. Geben **Sie in "Normalisierungsregel** erstellen" Werte in die folgenden Felder ein:

   - **Anfangsziffern** (optional) Geben Sie die führenden Ziffern gewählter Nummern an, die mit dem Muster übereinstimmen. Geben Sie beispielsweise "425" ein, wenn das Muster mit gewählten Nummern übereinstimmen soll, die mit 425 beginnen.

   - **Length** Geben Sie die Anzahl der Ziffern im Vergleichsmuster an, und wählen Sie aus, ob das Muster genau mit dieser Länge übereinstimmen soll, ob gewählte Nummern mit mindestens dieser Länge oder gewählte Nummern beliebiger Länge übereinstimmen sollen.

   - **Zu entfernende** Ziffern (optional) Geben Sie die Anzahl der Anfangsziffern an, die aus gewählten Nummern entfernt werden sollen, die mit dem Muster übereinstimmen sollen.

   - **Hinzuzufügende Ziffern** (optional) Geben Sie Ziffern an, die gewählten Nummern hinzugefügt werden sollen, die mit dem Muster übereinstimmen sollen.

     Die Werte, die Sie in diese Felder eingeben, werden in **Muster für** Übereinstimmung und **Übersetzungsregel angezeigt.** Wenn Sie z.  B. die Anfangsziffern  leer lassen, geben Sie7 **in** das Feld Länge ein,  und wählen Sie "Genau" **aus,** und geben Sie "0" in zu entfernenden Ziffern an. Der resultierende reguläre Ausdruck im Muster, der übereinstimmen soll, ist:

     ^(\d{7})$

6. Geben **Sie in der** Übersetzungsregel ein Muster für das Format übersetzter E.164-Telefonnummern wie folgt an:

   - Ein Wert, der die Anzahl der Im Vergleichsmuster angegebenen Ziffern darstellt. Wenn das Vergleichsmuster beispielsweise ^(\d )$ ist, stellt $1 in der Übersetzungsregel siebenstellige gewählte {7} Nummern dar.

   - (Optional) Geben Sie einen  Wert in das Feld "Ziffern" ein, um die Ziffern anzugeben, die der übersetzten Nummer voranstellen sollen (z. B. +1425).

     Wenn "Muster  für Übereinstimmung" beispielsweise ^(\d )$ als Muster für gewählte Nummern und {7} Übersetzungsregel +1425$1 als Muster für E.164-Telefonnummern enthält, normalisiert die Regel 5550100 in +14255550100. 

7. (Optional) Wenn die Normalisierungsregel zu einer internen Telefonnummer in Ihrer Organisation führt, wählen Sie interne **Durchwahl aus.**

8. (Optional) Geben Sie eine Zahl ein, um die Normalisierungsregel zu testen, und klicken Sie dann auf **"Los".** Die Testergebnisse werden unterhalb von **Geben Sie eine Testnummer ein** angezeigt.

    > [!NOTE]
    > Sie können eine Normalisierungsregel speichern, die den Test noch nicht bestanden hat, und sie später neu konfigurieren. Ausführliche Informationen dazu finden Sie unter [Test Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx).

9. Klicken Sie **auf "OK",** um die Normalisierungsregel zu speichern.

10. Klicken Sie **auf "OK",** um den Wählplan zu speichern.

11. Klicken Sie auf der Seite **Wähleinstellungen** auf **Commit** und anschließend auf **Commit für alle**.

    > [!NOTE]
    > Jedes Mal, wenn Sie eine Normalisierungsregel erstellen oder ändern, müssen Sie den Befehl **"Commit** für alle" ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter [Veröffentlichen ausstehender Änderungen an der Voiceroutingkonfiguration in Skype for Business](voice-route-config-changes.md) in der Betriebsdokumentation.

### <a name="to-define-a-normalization-rule-manually"></a>So definieren Sie eine Normalisierungsregel manuell

1. Öffnen der Skype for Business Server-Systemsteuerung

2. (Optional) Führen Sie die Schritte unter [Erstellen oder Ändern eines Wählplans in Skype for Business Server aus.](dial-plans.md)

3. Geben **Sie in** "Neue Normalisierungsregel" oder **"Normalisierungsregel** bearbeiten" einen Namen ein, der das normalisierte Nummernmuster **im** Namen beschreibt (z. B. "Name der Normalisierungsregel5DigitExtension").

4. (Optional) Geben **Sie im** Feld "Beschreibung" eine Beschreibung der Normalisierungsregel ein (z. B. "Übersetzt 5-stellige Durchungen").

5. Klicken **Sie in "Normalisierungsregel erstellen"** auf **"Bearbeiten".**

6. Geben Sie in **Regulären Ausdruck eingeben** Folgendes ein:

   - Geben **Sie in Diesem Muster** das Muster an, das Sie verwenden möchten, um der gewählten Telefonnummer zu entsprechen.

   - Geben **Sie in der** Übersetzungsregel ein Muster für das Format übersetzter E.164-Telefonnummern an.

     Wenn Sie beispielsweise ^(\d )$ in Übereinstimmung mit diesem Muster {7} und+1425 $1 in der Übersetzungsregel eingeben, normalisiert die Regel 5550100 auf +14255550100.  

7. (Optional) Wenn die Normalisierungsregel zu einer internen Telefonnummer in Ihrer Organisation führt, wählen Sie interne **Durchwahl aus.**

8. (Optional) Geben Sie eine Zahl ein, um die Normalisierungsregel zu testen, und klicken Sie dann auf **"Los".** Die Testergebnisse werden unterhalb von **Geben Sie eine Testnummer ein** angezeigt.

9. Klicken Sie **auf "OK",** um die Normalisierungsregel zu speichern.

10. Klicken Sie **auf "OK",** um den Wählplan zu speichern.

11. Klicken Sie auf der Seite **Wähleinstellungen** auf **Commit** und anschließend auf **Commit für alle**.

    > [!NOTE]
    > Jedes Mal, wenn Sie eine Normalisierungsregel erstellen oder ändern, müssen Sie den Befehl **"Commit** für alle" ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter [Veröffentlichen ausstehender Änderungen an der Voiceroutingkonfiguration in Skype for Business](voice-route-config-changes.md) in der Betriebsdokumentation.


