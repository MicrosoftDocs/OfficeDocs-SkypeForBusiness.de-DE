---
title: Erstellen oder Ändern einer Normalisierungsregel in Skype for Business
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
ms.assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie eine Normalisierungsregel in Skype for Business Server definieren, erstellen und ändern.'
ms.openlocfilehash: 4739bdb50e0a76c088cb6129539438c1ac6d795a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306150"
---
# <a name="create-or-modify-a-normalization-rule-in-skype-for-business"></a>Erstellen oder Ändern einer Normalisierungsregel in Skype for Business

**Zusammenfassung:** Hier erfahren Sie, wie Sie eine Normalisierungsregel in Skype for Business Server definieren, erstellen und ändern.

Sie können Normalisierungsregeln in Skype for Business Server definieren, erstellen und ändern.

### <a name="to-define-a-normalization-rule-by-using-build-a-normalization-rule"></a>So definieren Sie eine Normalisierungsregel mit Normalisierungsregel erstellen

1. Öffnen Sie die Skype for Business Server-Systemsteuerung.

2. Optional Führen Sie die Schritte unter [erstellen oder Ändern eines Wählplans in Skype for Business Server](dial-plans.md) bis Schritt 11 aus, oder [Ändern Sie einen Wählplan](https://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx) bis Schritt 10.

3. Geben Sie in **neue Normalisierungsregel** oder **Normalisierungsregel bearbeiten**einen Namen ein, der das Zahlenmuster beschreibt, das im **Namen** normalisiert wird (beispielsweise 5DigitExtension).

4. (Optional) Geben Sie in **Beschreibung** eine Beschreibung der Normalisierungsregel ein (beispielsweise „Übersetzt 5-stellige Durchwahlnummern“).

5. Geben Sie im Abschnitt **Normalisierungsregel erstellen** Werte in die folgenden Felder ein:

   - **Anfangsziffern** Optional Geben Sie die führenden Ziffern für gewählte Nummern an, die mit dem Muster übereinstimmen sollen. Beispiel: type425, wenn Sie möchten, dass das Muster an gewählte Nummern ab 425 anpasst.

   - **Länge** Geben Sie die Anzahl der Ziffern im übereinstimmenden Muster an, und wählen Sie aus, ob das Muster genau mit dieser Länge übereinstimmen soll, wählen Sie Nummern aus, die mindestens diese Länge aufweisen, oder passen Sie gewählte Nummern einer beliebigen Länge an.

   - **Zu entfernende Ziffern** Optional Geben Sie die Anzahl der Anfangsziffern an, die aus den gewählten Nummern entfernt werden sollen, die das Muster erfüllen soll.

   - **Zu addierende Ziffern** Optional Geben Sie Ziffern an, die zu gewählten Nummern hinzugefügt werden sollen, damit das Muster übereinstimmen kann.

     Die in diesen Feldern eingegebenen Werte werden in den Feldern **Muster für Vergleich** und **Übersetzungsregel** widergespiegelt. Wenn Sie beispielsweise die **Anfangsziffern** leer lassen, type7 in das **Feld Länge** eingeben und **genau**auswählen und 0 in den **zu entfernenden Ziffern**angeben, lautet der resultierende reguläre Ausdruck in dem **übereinstimmenden Muster** wie folgt:

     ^ (\d{7}) $

6. Geben Sie in **Übersetzungsregel** ein Muster für das Format der übersetzten E.164-Telefonnummern ein:

   - Ein Wert, der die Anzahl von Ziffern repräsentiert, die im Vergleichsmuster angegeben ist. Wenn beispielsweise das Übereinstimmungsmuster ^ (\d{7}) $ ist, stellt $1 in der Übersetzungsregel siebenstellige, gewählte Nummern dar.

   - Optional Geben Sie einen Wert in das Feld zu **addierende Ziffern** ein, um Ziffern anzugeben, die der übersetzten Zahl vorangestellt werden sollen (beispielsweise + 1425).

     Wenn beispielsweise **Muster für Vergleich** ^ (\d{7}) $ als Muster für gewählte Nummern und die **Übersetzungsregel** + 1425 $1 als Muster für E. 164-Telefonnummern enthält, normalisiert die Regel 5550100 auf + 14255550100.

7. (Optional) Falls die Normalisierungsregel eine interne Telefonnummer des Unternehmens ergibt, klicken Sie auf **Interne Durchwahl**.

8. (Optional) Geben Sie eine Nummer zum Testen der Normalisierungsregel ein und klicken Sie auf **Los**. Die Testergebnisse werden unterhalb von **Geben Sie eine Testnummer ein** angezeigt.

    > [!NOTE]
    > Sie können eine Normalisierungsregel speichern, die den Test nicht bestanden hat und sie später neu konfigurieren. Ausführliche Informationen dazu finden Sie unter [Test Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx).

9. Klicken Sie auf **OK**, um die Normalisierungsregel zu speichern.

10. Klicken Sie auf **OK**, um die Wähleinstellungen zu speichern.

11. Klicken Sie auf der Seite **Wählplan** auf **Commit ausführen** und anschließend auf **Commit für alle Elemente ausführen**.

    > [!NOTE]
    > Jedes Mal, wenn Sie eine Normalisierungsregel erstellen oder ändern, müssen Sie den Befehl **Commit für alle** ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter [veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in Skype for Business](voice-route-config-changes.md) in der Betriebsdokumentation.

### <a name="to-define-a-normalization-rule-manually"></a>So definieren Sie eine Normalisierungsregel manuell

1. Öffnen Sie die Skype for Business Server-Systemsteuerung.

2. Optional Führen Sie die Schritte unter [erstellen oder Ändern eines Wählplans in Skype for Business Server](dial-plans.md)aus.

3. Geben Sie in **neue Normalisierungsregel** oder **Normalisierungsregel bearbeiten**einen Namen ein, der das Zahlenmuster beschreibt, das im **Namen** normalisiert wird (beispielsweise den Namen normalisierungs-rule5DigitExtension).

4. (Optional) Geben Sie im Feld **Beschreibung** eine Beschreibung der Normalisierungsregel ein (beispielsweise „Übersetzt 5-stellige Durchwahlnummern“).

5. Klicken Sie in **Normalisierungsregel erstellen** auf **Bearbeiten**.

6. Geben Sie in **Regulären Ausdruck eingeben** Folgendes ein:

   - Geben Sie in **Dieses Muster abgleichen** das Muster an, das für den Abgleich der gewählten Telefonnummer verwendet werden soll.

   - Geben Sie in **Übersetzungsregel** ein Muster für das Format der übersetzten E.164-Telefonnummern ein.

     Wenn Sie beispielsweise ^ (\d{7}) $ in **Übereinstimmung mit diesem Muster** und + 1425 $1 in der **Übersetzungsregel**eingeben, normalisiert die Regel 5550100 auf + 14255550100.

7. (Optional) Falls die Normalisierungsregel eine interne Telefonnummer des Unternehmens ergibt, klicken Sie auf **Interne Durchwahl**.

8. (Optional) Geben Sie eine Nummer zum Testen der Normalisierungsregel ein und klicken Sie auf **Los**. Die Testergebnisse werden unterhalb von **Geben Sie eine Testnummer ein** angezeigt.

9. Klicken Sie auf **OK**, um die Normalisierungsregel zu speichern.

10. Klicken Sie auf **OK**, um die Wähleinstellungen zu speichern.

11. Klicken Sie auf der Seite **Wählplan** auf **Commit ausführen** und anschließend auf **Commit für alle Elemente ausführen**.

    > [!NOTE]
    > Jedes Mal, wenn Sie eine Normalisierungsregel erstellen oder ändern, müssen Sie den Befehl **Commit für alle** ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter [veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in Skype for Business](voice-route-config-changes.md) in der Betriebsdokumentation.


