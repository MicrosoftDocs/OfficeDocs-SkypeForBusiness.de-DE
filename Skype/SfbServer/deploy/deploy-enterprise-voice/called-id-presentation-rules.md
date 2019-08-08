---
title: Erstellen oder Ändern einer Übersetzungsregel für die benannte ID-Präsentation in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie mithilfe des Tools zum Erstellen einer Übersetzungsregel in Skype for Business Server eine Übersetzungsregel definieren.'
ms.openlocfilehash: 3c72e53044abe44660423bbd9bc1adbbeed2a3ed
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233784"
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server"></a>Erstellen oder Ändern einer Übersetzungsregel für die benannte ID-Präsentation in Skype for Business Server

**Zusammenfassung:** Hier erfahren Sie, wie Sie mithilfe des Tools zum Erstellen einer Übersetzungsregel in Skype for Business Server eine Übersetzungsregel definieren.

Führen Sie die folgenden Schritte aus, wenn Sie eine Übersetzungsregel definieren möchten, indem Sie eine Gruppe von Werten in das Tool zum **Erstellen einer Übersetzungsregel** eingeben und die Skype for Business Server-Systemsteuerung aktivieren, um das entsprechende Übereinstimmungsmuster und die Übersetzungsregel für Sie zu generieren. Alternativ können Sie manuell einen regulären Ausdruck erstellen, um das Vergleichsmuster und die Übersetzungsregel zu definieren. Ausführliche Informationen finden Sie unter [Create or Modify a Translation Rule Manually](https://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx).

### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a>So definieren Sie eine Regel mit dem Tool zum Erstellen einer Übersetzungsregel

1. Öffnen Sie die Skype for Business Server-Systemsteuerung.

2. Wenn Sie mit der Definition einer Übersetzungsregel beginnen möchten, führen Sie die Schritte unter [Konfigurieren eines Trunks mit medienumgehung in Skype for Business Server](configure-trunk-with-media-bypass.md) bis Schritt 10 aus, oder [Konfigurieren Sie einen trunk ohne medienumgehung in Skype for Business Server](configure-trunk-without-media-bypass.md) bis Schritt 9.

3. Geben Sie unter **Name** auf der Seite **Neue Übersetzungsregel** oder **Übersetzungsregel bearbeiten** einen Namen ein, der das zu übersetzende Nummernmuster beschreibt.

4. Optional Geben Sie unter **Beschreibung**eine Beschreibung der Übersetzungsregel ein, beispielsweise US-Auslands Wahl für Ferngespräche.

5. Geben Sie im Abschnitt **Übersetzungsregel erstellen** des Dialogfelds die folgenden Werte ein:

   - **Anfangsziffern**: (Optional) Geben Sie die Anfangsziffern der Nummern ein, die Sie mit dem Muster abgleichen möchten. Geben Sie beispielsweise + in dieses Feld ein, um Nummern im E.164-Format abzugleichen (diese beginnen mit +).

   - **Länge**: Geben Sie die Anzahl von Ziffern im Vergleichsmuster ein und wählen Sie aus, ob mit dem Muster Nummern abgeglichen werden sollen, die exakt diese Länge, mindestens diese Länge oder eine beliebige Länge aufweisen. Geben Sie beispielsweise in der Dropdownliste den Wert 11 und mindestens in der Dropdownliste ein, um Zahlen mit einer Länge von mindestens 11 Ziffern zuzuordnen.

   - **Zu entfernende Ziffern**: (Optional) Geben Sie die Anzahl von Anfangsziffern ein, die entfernt werden sollen. Geben Sie beispielsweise 1 ein, um den + vom Anfang der Zahl zu entfernen.

   - **Hinzuzufügende Ziffern**: (Optional) Geben Sie die Ziffern ein, die der übersetzten Nummer vorangestellt werden sollen. Geben Sie beispielsweise 011 ein, wenn bei Anwendung der Regel der übersetzten Nummer die Ziffernfolge 011 vorangestellt werden soll.

     Die in diesen Feldern eingegebenen Werte werden in den Feldern **Muster für Vergleich** und **Übersetzungsregel** widergespiegelt. Wenn Sie beispielsweise die vorstehend genannten Beispielwerte verwenden, lautet der reguläre Ausdruck im Feld **Muster für Vergleich** wie folgt:

     ^\+(\d{9}\d +) $

     Das Feld **Übersetzungsregel** gibt ein Muster für das Format der übersetzten Nummern an. Dieses Muster besteht aus zwei Teilen:

   - Einem Wert (z. B. $1), der die Anzahl von Ziffern im Vergleichsmuster repräsentiert

   - (Optional) Einem Wert, den Sie durch eine Eingabe im Feld **Hinzuzufügende Ziffern** voranstellen können

     Bei Verwendung der vorstehend genannten Beispiele wird der Wert 011$1 im Feld **Übersetzungsregel** angezeigt.

     Bei Anwendung dieser Übersetzungsregel wird die Nummer +441235551010 in 011441235551010 umgewandelt.

6. Klicken Sie auf **OK**, um die Übersetzungsregel zu speichern.

7. Klicken Sie auf **OK**, um die Trunkkonfiguration zu speichern.

8. Klicken Sie auf der Seite **Trunkkonfiguration** auf **Commit** und klicken Sie anschließend auf **Commit für alle Elemente ausführen**.

   > [!NOTE]
   > Immer dann, wenn Sie eine Übersetzungsregel erstellen oder ändern, müssen Sie den Befehl **Commit für alle Elemente ausführen** ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter [veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in Skype for Business](voice-route-config-changes.md) in der Betriebsdokumentation.

### <a name="to-define-a-translation-rule-manually"></a>So definieren Sie eine Übersetzungsregel manuell

1. Öffnen Sie die Skype for Business Server-Systemsteuerung.

2. Wenn Sie mit der Definition einer Übersetzungsregel beginnen möchten, führen Sie die Schritte unter [Konfigurieren eines Trunks mit medienumgehung in Skype for Business Server](configure-trunk-with-media-bypass.md) bis Schritt 10 aus, oder [Konfigurieren Sie einen trunk ohne medienumgehung in Skype for Business Server](configure-trunk-without-media-bypass.md) bis Schritt 9.

3. Geben Sie im Feld **Name** auf der Seite **Neue Übersetzungsregel** oder **Übersetzungsregel bearbeiten** einen Namen ein, der das zu übersetzende Nummernmuster beschreibt.

4. Optional Geben Sie in **Beschreibung**eine Beschreibung der Übersetzungsregel ein, beispielsweise US-Auslands Wahl für Ferngespräche.

5. Klicken Sie im unteren Bereich des Abschnitts **Übersetzungsregel erstellen** auf **Bearbeiten**.

6. Geben Sie unter **Regulären Ausdruck eingeben** Folgendes ein:

   - Geben Sie unter **Übereinstimmung mit dem folgenden Muster** das Muster an, das für den Abgleich der zu übersetzenden Nummern verwendet werden soll.

   - Geben Sie unter **Übersetzungsregel** ein Muster für das Format der übersetzten Nummern an.

     Wenn\+Sie beispielsweise ^ (\d{9}\d +) $ in **Übereinstimmung mit diesem Muster** and011 $1 in der **Übersetzungsregel**eingeben, wird die Regel + 441235551010 in 011441235551010 übersetzen.

7. Klicken Sie auf **OK**, um die Übersetzungsregel zu speichern.

8. Klicken Sie auf **OK**, um die Trunkkonfiguration zu speichern.

9. Klicken Sie auf der Seite **Trunkkonfiguration** auf **Commit** und klicken Sie anschließend auf **Commit für alle Elemente ausführen**.

    > [!NOTE]
    > Immer dann, wenn Sie eine Übersetzungsregel erstellen oder ändern, müssen Sie den Befehl **Commit für alle Elemente ausführen** ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter [veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in Skype for Business](voice-route-config-changes.md) in der Betriebsdokumentation.

## <a name="see-also"></a>Siehe auch

[Konfigurieren eines Trunks mit medienumgehung in Skype for Business Server](configure-trunk-with-media-bypass.md)

[Konfigurieren eines Trunks ohne medienumgehung in Skype for Business Server](configure-trunk-without-media-bypass.md)

[Veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in Skype for Business](voice-route-config-changes.md)

[Bereitstellen der medienumgehung in Skype for Business Server](deploy-media-bypass.md)

