---
title: Erstellen oder Ändern einer Normalisierungsregel in Skype for Business
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
description: 'Zusammenfassung: Erfahren Sie, wie Sie eine Normalisierungsregel in Skype for Business Server definieren, erstellen und ändern.'
ms.openlocfilehash: c624e9bb42b113a87c5774f90df77c23488d1b32
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60773275"
---
# <a name="create-or-modify-a-normalization-rule-in-skype-for-business"></a>Erstellen oder Ändern einer Normalisierungsregel in Skype for Business

**Zusammenfassung:** Erfahren Sie, wie Sie eine Normalisierungsregel in Skype for Business Server definieren, erstellen und ändern.

Definieren, Erstellen und Ändern von Normalisierungsregeln in Skype for Business Server.

### <a name="to-define-a-normalization-rule-by-using-build-a-normalization-rule"></a>So definieren Sie eine Normalisierungsregel mithilfe von Build a Normalization Rule

1. Öffnen Skype for Business Server Systemsteuerung

2. (Optional) Führen Sie die Schritte unter ["Erstellen oder Ändern eines Wählplans in Skype for Business Server](dial-plans.md) bis Schritt 11" aus, oder [ändern Sie einen Wählplan](/previous-versions/office/lync-server-2013/lync-server-2013-modify-a-dial-plan) bis Schritt 10.

3. Geben Sie in **"Neue Normalisierungsregel"** oder **"Normalisierungsregel bearbeiten"** einen Namen ein, der das Nummernmuster beschreibt, das in **"Name"** normalisiert wird (z. B. "5DigitExtension").

4. (Optional) Geben Sie in **"Beschreibung"** eine Beschreibung der Normalisierungsregel ein (z. B. "Übersetzt 5-stellige Durchwahlnummern").

5. Geben Sie in **Build a Normalization Rule** Werte in die folgenden Felder ein:

   - **Anfangsziffern** (optional) Geben Sie die vorangestellten Ziffern der gewählten Nummern an, mit denen das Muster übereinstimmen soll. Geben Sie z. B. "425" ein, wenn das Muster gewählte Nummern ab 425 abgleichen soll.

   - **Länge** Geben Sie die Anzahl der Ziffern im Vergleichsmuster an, und wählen Sie aus, ob das Muster genau mit dieser Länge übereinstimmen soll, ob gewählte Nummern mit mindestens dieser Länge übereinstimmen sollen oder ob gewählte Nummern beliebiger Länge übereinstimmen sollen.

   - **Zu entfernende Ziffern** (optional) Geben Sie die Anzahl der Anfangsziffern an, die aus gewählten Nummern entfernt werden sollen, die mit dem Muster übereinstimmen sollen.

   - **Hinzuzufügende Ziffern** (optional) Geben Sie Ziffern an, die gewählten Nummern hinzugefügt werden sollen, die mit dem Muster übereinstimmen sollen.

     Die Werte, die Sie in diese Felder eingeben, werden in **Muster-zu-Übereinstimmung** und **Übersetzungsregel** widergespiegelt. Wenn Sie **z. B. die Anfangsziffern** leer lassen, geben Sie7 in das **Feld Length** ein, und wählen Sie **Genau** aus, und geben Sie 0 in Ziffern an, lautet der resultierende reguläre Ausdruck im **Muster** wie folgt: 

     ^(\d{7})$

6. Geben Sie in der **Übersetzungsregel** wie folgt ein Muster für das Format übersetzter E.164-Telefonnummern an:

   - Ein Wert, der die Anzahl der im Vergleichsmuster angegebenen Ziffern darstellt. Wenn das Vergleichsmuster beispielsweise ^(\d )$ lautet, {7} stellt $1 in der Übersetzungsregel siebenstellige gewählte Nummern dar.

   - (Optional) Geben Sie einen Wert in die **Ziffern ein, um** ein Feld hinzuzufügen, um Ziffern anzugeben, die der übersetzten Nummer vorangestellt werden sollen (z. B. +1425).

     Wenn **"Pattern to match"** beispielsweise "contains^(\d {7} )$" als Muster für gewählte Nummern und die **Übersetzungsregel** +1425 $1 als Muster für E.164-Telefonnummern enthält, normalisiert die Regel 5550100 auf +14255550100.

7. (Optional) Wenn die Normalisierungsregel zu einer telefonnummer führt, die für Ihre Organisation intern ist, wählen Sie **interne Erweiterung** aus.

8. (Optional) Geben Sie eine Zahl ein, um die Normalisierungsregel zu testen, und klicken Sie dann auf **"Los".** Die Testergebnisse werden unterhalb von **Geben Sie eine Testnummer ein** angezeigt.

    > [!NOTE]
    > Sie können eine Normalisierungsregel speichern, die den Test noch nicht bestanden hat, und sie später neu konfigurieren. Ausführliche Informationen dazu finden Sie unter [Test Voice Routing](/previous-versions/office/lync-server-2013/lync-server-2013-test-voice-routing).

9. Klicken Sie auf **"OK",** um die Normalisierungsregel zu speichern.

10. Klicken Sie auf **"OK",** um den Wählplan zu speichern.

11. Klicken Sie auf der Seite **Wähleinstellungen** auf **Commit** und anschließend auf **Commit für alle**.

    > [!NOTE]
    > Wenn Sie eine Normalisierungsregel erstellen oder ändern, müssen Sie den Befehl **"Commit für alle** Elemente ausführen" ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter [Veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in Skype for Business](voice-route-config-changes.md) in der Betriebsdokumentation.

### <a name="to-define-a-normalization-rule-manually"></a>So definieren Sie eine Normalisierungsregel manuell

1. Öffnen Skype for Business Server Systemsteuerung

2. (Optional) Führen Sie die Schritte unter [Erstellen oder Ändern eines Wählplans in Skype for Business Server](dial-plans.md)aus.

3. Geben Sie in **"Neue Normalisierungsregel"** oder **"Normalisierungsregel bearbeiten"** einen Namen ein, der das Nummernmuster beschreibt, das in **Name** normalisiert wird (z. B. benennen Sie die Normalisierungsregel5DigitExtension).

4. (Optional) Geben Sie im Feld **Beschreibung** eine Beschreibung der Normalisierungsregel ein (z. B. "Übersetzt 5-stellige Durchwahlnummern").

5. Klicken Sie unter **"Normalisierungsregel erstellen"** auf **"Bearbeiten".**

6. Geben Sie in **Regulären Ausdruck eingeben** Folgendes ein:

   - Geben Sie in **Übereinstimmung mit diesem Muster** das Muster an, das Sie für die Übereinstimmung mit der gewählten Telefonnummer verwenden möchten.

   - Geben Sie in der **Übersetzungsregel** ein Muster für das Format übersetzter E.164-Telefonnummern an.

     Wenn Sie beispielsweise ^(\d {7} )$ in **Übereinstimmung mit diesem Muster** und +1425 $1 in der **Übersetzungsregel** eingeben, normalisiert die Regel 5550100 auf +14255550100.

7. (Optional) Wenn die Normalisierungsregel zu einer telefonnummer führt, die für Ihre Organisation intern ist, wählen Sie **interne Erweiterung** aus.

8. (Optional) Geben Sie eine Zahl ein, um die Normalisierungsregel zu testen, und klicken Sie dann auf **"Los".** Die Testergebnisse werden unterhalb von **Geben Sie eine Testnummer ein** angezeigt.

9. Klicken Sie auf **"OK",** um die Normalisierungsregel zu speichern.

10. Klicken Sie auf **"OK",** um den Wählplan zu speichern.

11. Klicken Sie auf der Seite **Wähleinstellungen** auf **Commit** und anschließend auf **Commit für alle**.

    > [!NOTE]
    > Wenn Sie eine Normalisierungsregel erstellen oder ändern, müssen Sie den Befehl **"Commit für alle** Elemente ausführen" ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter [Veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in Skype for Business](voice-route-config-changes.md) in der Betriebsdokumentation.