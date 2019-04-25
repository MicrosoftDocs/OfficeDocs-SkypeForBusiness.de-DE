---
title: Erstellen oder Ändern einer Normalisierungsregel in Skype für Unternehmen
ms.reviewer: ''
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
ms.openlocfilehash: 52f56280c747db702935405ea4c60383c58a6d78
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32223020"
---
# <a name="create-or-modify-a-normalization-rule-in-skype-for-business"></a>Erstellen oder Ändern einer Normalisierungsregel in Skype für Unternehmen

**Zusammenfassung:** Informationen Sie zum definieren, erstellen und Ändern einer Normalisierungsregel in Skype für Business Server.

Definieren, erstellen und Ändern von Normalisierungsregeln in Skype für Business Server.

### <a name="to-define-a-normalization-rule-by-using-build-a-normalization-rule"></a>So definieren Sie eine Normalisierungsregel mit Normalisierungsregel erstellen

1. Öffnen von Skype Business Server-Systemsteuerung

2. (Optional) Führen Sie die Schritte in [Erstellen oder Ändern von Wähleinstellungen in Skype für Business Server](dial-plans.md) bis Schritt 11 oder [Modify a Dial Plan](https://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx) bis Schritt 10.

3. Geben Sie unter **Neue Normalisierungsregel** oder **Normalisierungsregel bearbeiten**einen Namen, der das im **Namen** (beispielsweise 5stellendurchwahl).) normalisierende Nummernmuster beschreibt.

4. (Optional) Geben Sie in **Beschreibung** eine Beschreibung der Normalisierungsregel ein (beispielsweise „Übersetzt 5-stellige Durchwahlnummern“).

5. Geben Sie im Abschnitt **Normalisierungsregel erstellen** Werte in die folgenden Felder ein:

   - **Anfangsziffern** (Optional) Geben Sie die führenden Ziffern gewählter Nummern, die Sie das Muster abgleichen möchten. Wenn Sie das Muster abgleichen möchten gewählte type425 beispielsweise Zahlen mit 425 beginnt.

   - **Länge** Geben Sie die Anzahl der Nachkommastellen in das Vergleichsmuster, und wählen Sie, ob Übereinstimmung Nummern beliebiger Länge gewählten Übereinstimmung Rufnummern, die mindestens diese Länge sind oder das Muster dieser Länge genau entsprechen soll.

   - **So entfernen Sie Ziffern** (Optional) Geben Sie die Anzahl von Anfangsziffern ein, die aus gewählten Nummern entfernt werden Sie das Muster abgleichen möchten.

   - **Hinzuzufügende Ziffern** (Optional) Geben Sie die Ziffern auf gewählten Nummern hinzugefügt werden soll, dass Sie das Muster abgleichen möchten.

     Die in diesen Feldern eingegebenen Werte werden in den Feldern **Muster für Vergleich** und **Übersetzungsregel** widergespiegelt. Beispielsweise wenn Sie leer ist, Typ7 **Starten Ziffern** in das Feld **Länge verlassen** und wählen Sie **genau**, und geben Sie 0 in **Ziffern zu entfernen**, wird der resultierende reguläre Ausdruck in dem **Muster abgleichen** :

     ^(\d{7})$

6. Geben Sie in **Übersetzungsregel** ein Muster für das Format der übersetzten E.164-Telefonnummern ein:

   - Ein Wert, der die Anzahl von Ziffern repräsentiert, die im Vergleichsmuster angegeben ist. Wenn das Vergleichsmuster beispielsweise ^(\d{7})$ dann$ 1 in der Regel stellt 7 Ziffer gewählter Nummern.

   - (Optional) Geben Sie einen Wert in das Feld **hinzuzufügende Ziffern** an Stellen die übersetzte Nummer (beispielsweise + 1425) vorangestellt werden.

     Wenn enthält **Muster an,** beispielsweise ^(\d{7})$ als das Muster für die gewählten Nummern und **übersetzungsregel** enthält + 1425$ 1 als das Muster für das e. 164 Telefonnummern, übersetzt die Regel 5550100 in + 14255550100.

7. (Optional) Falls die Normalisierungsregel eine interne Telefonnummer des Unternehmens ergibt, klicken Sie auf **Interne Durchwahl**.

8. (Optional) Geben Sie eine Nummer zum Testen der Normalisierungsregel ein und klicken Sie auf **Los**. Die Testergebnisse werden unterhalb von **Geben Sie eine Testnummer ein** angezeigt.

    > [!NOTE]
    > Sie können eine Normalisierungsregel speichern, die den Test nicht bestanden hat und sie später neu konfigurieren. Ausführliche Informationen dazu finden Sie unter [Test Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx).

9. Klicken Sie auf **OK**, um die Normalisierungsregel zu speichern.

10. Klicken Sie auf **OK**, um die Wähleinstellungen zu speichern.

11. Klicken Sie auf der Seite **Wählplan** auf **Commit ausführen** und anschließend auf **Commit für alle Elemente ausführen**.

    > [!NOTE]
    > Jedes Mal, wenn Sie eine Normalisierungsregel erstellen oder ändern, müssen Sie den Befehl **Commit für alle** ausführen, um die Konfigurationsänderung zu veröffentlichen. Weitere Informationen hierzu finden Sie unter [Veröffentlichen ausstehenden Änderungen an der VoIP-Routingkonfiguration in Skype für Unternehmen](voice-route-config-changes.md) in der Betriebsdokumentation.

### <a name="to-define-a-normalization-rule-manually"></a>So definieren Sie eine Normalisierungsregel manuell

1. Öffnen von Skype Business Server-Systemsteuerung

2. (Optional) Führen Sie die Schritte in [Erstellen oder Ändern von Wähleinstellungen in Skype für Business Server](dial-plans.md).

3. Geben Sie unter **Neue Normalisierungsregel** oder **Normalisierungsregel bearbeiten**einen Namen, der das im **Feld Name** (beispielsweise Name der Normalisierung rule5DigitExtension) normalisierende Nummernmuster beschreibt.

4. (Optional) Geben Sie im Feld **Beschreibung** eine Beschreibung der Normalisierungsregel ein (beispielsweise „Übersetzt 5-stellige Durchwahlnummern“).

5. Klicken Sie in **Normalisierungsregel erstellen** auf **Bearbeiten**.

6. Geben Sie in **Regulären Ausdruck eingeben** Folgendes ein:

   - Geben Sie in **Dieses Muster abgleichen** das Muster an, das für den Abgleich der gewählten Telefonnummer verwendet werden soll.

   - Geben Sie in **Übersetzungsregel** ein Muster für das Format der übersetzten E.164-Telefonnummern ein.

     Beispiel: bei Eingabe von ^(\d{7})$ in **dieses Muster abgleichen** und + 1425$ 1 in **übersetzungsregel**, die Regel 5550100 in + 14255550100 normalisiert.

7. (Optional) Falls die Normalisierungsregel eine interne Telefonnummer des Unternehmens ergibt, klicken Sie auf **Interne Durchwahl**.

8. (Optional) Geben Sie eine Nummer zum Testen der Normalisierungsregel ein und klicken Sie auf **Los**. Die Testergebnisse werden unterhalb von **Geben Sie eine Testnummer ein** angezeigt.

9. Klicken Sie auf **OK**, um die Normalisierungsregel zu speichern.

10. Klicken Sie auf **OK**, um die Wähleinstellungen zu speichern.

11. Klicken Sie auf der Seite **Wählplan** auf **Commit ausführen** und anschließend auf **Commit für alle Elemente ausführen**.

    > [!NOTE]
    > Jedes Mal, wenn Sie eine Normalisierungsregel erstellen oder ändern, müssen Sie den Befehl **Commit für alle** ausführen, um die Konfigurationsänderung zu veröffentlichen. Weitere Informationen hierzu finden Sie unter [Veröffentlichen ausstehenden Änderungen an der VoIP-Routingkonfiguration in Skype für Unternehmen](voice-route-config-changes.md) in der Betriebsdokumentation.


