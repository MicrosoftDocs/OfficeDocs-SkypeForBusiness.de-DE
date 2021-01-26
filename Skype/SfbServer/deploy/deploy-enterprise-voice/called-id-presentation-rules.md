---
title: Erstellen oder Ändern einer Übersetzungsregel für die Darstellung der angerufenen ID in Skype for Business Server
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
ms.assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
description: 'Zusammenfassung: Informationen zum Definieren einer Übersetzungsregel mithilfe des Tools zum Erstellen einer Übersetzungsregel in Skype for Business Server.'
ms.openlocfilehash: b93d271abd0ade1b178e859f2a0599464a6759e5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804195"
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server"></a>Erstellen oder Ändern einer Übersetzungsregel für die Darstellung der angerufenen ID in Skype for Business Server

**Zusammenfassung:** Erfahren Sie, wie Sie eine Übersetzungsregel mithilfe des Tools zum Erstellen einer Übersetzungsregel in Skype for Business Server definieren.

Führen Sie die folgenden Schritte aus, wenn Sie eine Übersetzungsregel definieren möchten, indem Sie einen Wertesatz in das Tool zum Erstellen einer Übersetzungsregel eingeben und die Skype for Business Server-Systemsteuerung aktivieren, um das entsprechende Vergleichsmuster und die übersetzungsregel für Sie zu generieren.  Alternativ können Sie einen regulären Ausdruck manuell schreiben, um das Vergleichsmuster und die Übersetzungsregel zu definieren. Weitere Informationen finden Sie unter ["Manuelles Erstellen oder Ändern einer Übersetzungsregel".](https://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx)

### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a>So definieren Sie eine Regel mithilfe des Tools zum Erstellen einer Übersetzungsregel

1. Öffnen Sie die Skype for Business Server-Systemsteuerung.

2. Führen Sie zum Definieren einer Übersetzungsregel die Schritte in "Konfigurieren eines Trunks mit Medienumgehung [in Skype for Business Server"](configure-trunk-with-media-bypass.md) bis Schritt 10 oder "Konfigurieren eines Trunks ohne Medienumgehung in Skype for Business [Server"](configure-trunk-without-media-bypass.md) bis Schritt 9 aus.

3. Geben **Sie auf** der Seite "Neue **Übersetzungsregel"** oder "Übersetzungsregel bearbeiten" unter "Name" einen Namen ein, der das zu übersetzende Nummernmuster beschreibt. 

4. (Optional) Geben **Sie** unter Beschreibung eine Beschreibung der Übersetzungsregel ein, z. B. us-amerikanische Fernwahlen.

5. Geben Sie **im Abschnitt "Übersetzungsregel** erstellen" des Dialogfelds Werte in die folgenden Felder ein:

   - **Anfangsziffern:**(Optional) Geben Sie die führenden Ziffern von Zahlen an, die mit dem Muster übereinstimmen. Geben Sie beispielsweise +in dieses Feld ein, um Zahlen im E.164-Format zu entsprechen (die mit +beginnen).

   - **Length**: Geben Sie die Anzahl der Ziffern im Vergleichsmuster an, und wählen Sie aus, ob das Muster Zahlen mit dieser Länge genau, mindestens dieser Länge oder einer beliebigen Länge entsprechen soll. Geben Sie beispielsweise "11" ein, und wählen Sie "Mindestens" in der Dropdownliste aus, um Nummern mit einer Länge von mindestens 11 Ziffern zu finden.

   - **Zu entfernende Ziffern:**(Optional) Geben Sie die Anzahl der zu entfernenden Anfangsziffern an. Geben Sie z. B. 1 ein, um das Pluszeichen vom Anfang der Zahl zu streifen.

   - **Hinzuzufügende** Ziffern: (Optional) Geben Sie Ziffern an, die den übersetzten Nummern vorausgestellt werden sollen. Geben Sie beispielsweise "011" ein, wenn 011 den übersetzten Nummern vorangef?en soll, wenn die Regel angewendet wird.

     Die Werte, die Sie in diese Felder eingeben, werden in den Feldern "Muster für **Übereinstimmung"** und **"Übersetzungsregel"** angezeigt. Wenn Sie z. B. die vorherigen Beispielwerte angeben, ist der resultierende reguläre Ausdruck im Feld **"Pattern"** der folgende:

     ^\+(\d {9} \d+)$

     Das **Feld "Übersetzungsregel"** gibt ein Muster für das Format übersetzter Nummern an. Dieses Muster hat zwei Teile:

   - Ein Wert (z. B. $1), der die Anzahl der Ziffern im Vergleichsmuster darstellt.

   - (Optional) Ein Wert, den Sie vorbestellen können, indem Sie ihn in die Ziffern **eingeben, um das Feld hinzuzufügen**

     Mithilfe der vorstehenden Beispielwerte wird 011$1 im Feld **Übersetzungsregel** angezeigt.

     Wenn diese Übersetzungsregel angewendet wird, wird +441235551010 zu 011441235551010.

6. Klicken Sie auf **OK**, um die Übersetzungsregel zu speichern.

7. Klicken Sie auf **OK**, um die Trunkkonfiguration zu speichern.

8. Klicken Sie auf der Seite **Trunkkonfiguration** auf **Commit**, und klicken Sie anschließend auf **Commit für alle**.

   > [!NOTE]
   > Jedes Mal, wenn Sie eine Übersetzungsregel erstellen oder ändern, müssen Sie den Befehl **Commit für alle Elemente ausführen** ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter [Veröffentlichen ausstehender Änderungen an der Voiceroutingkonfiguration in Skype for Business](voice-route-config-changes.md) in der Betriebsdokumentation.

### <a name="to-define-a-translation-rule-manually"></a>So definieren Sie eine Übersetzungsregel manuell

1. Öffnen der Skype for Business Server-Systemsteuerung

2. Um mit dem Definieren einer Übersetzungsregel zu beginnen, führen Sie die Schritte in "Konfigurieren eines Trunks mit Medienumgehung [in Skype for Business Server"](configure-trunk-with-media-bypass.md) bis Schritt 10 oder "Konfigurieren eines Trunks ohne Medienumgehung in Skype for Business [Server"](configure-trunk-without-media-bypass.md) bis Schritt 9 aus.

3. Geben Sie im Feld **Name** auf der Seite **Neue Übersetzungsregel** oder **Übersetzungsregel bearbeiten** einen Namen ein, der das zu übersetzende Nummernmuster beschreibt.

4. (Optional) Geben **Sie** in "Beschreibung" eine Beschreibung der Übersetzungsregel ein, z. B. us-amerikanische Fernwahlen.

5. Klicken Sie im unteren Bereich des Abschnitts **Übersetzungsregel erstellen** auf **Bearbeiten**.

6. Geben Sie in **Regulären Ausdruck eingeben** Folgendes ein:

   - Geben Sie unter **Übereinstimmung mit dem folgenden Muster** das Muster an, das für den Abgleich der zu übersetzenden Nummern verwendet werden soll.

   - Geben Sie unter **Übersetzungsregel** ein Muster für das Format der übersetzten Nummern an.

     Wenn Sie beispielsweise ^ (\d \d+)$ in Übereinstimmung mit diesem Muster und011$1 in der Übersetzungsregel eingeben, übersetzt die Regel \+ {9} +441235551010 in 011441235551010.  

7. Klicken Sie auf **OK**, um die Übersetzungsregel zu speichern.

8. Klicken Sie auf **OK**, um die Trunkkonfiguration zu speichern.

9. Klicken Sie auf der Seite **Trunkkonfiguration** auf **Commit**, und klicken Sie anschließend auf **Commit für alle**.

    > [!NOTE]
    > Jedes Mal, wenn Sie eine Übersetzungsregel erstellen oder ändern, müssen Sie den Befehl **Commit für alle Elemente ausführen** ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter [Veröffentlichen ausstehender Änderungen an der Voiceroutingkonfiguration in Skype for Business](voice-route-config-changes.md) in der Betriebsdokumentation.

## <a name="see-also"></a>Siehe auch

[Konfigurieren eines Trunks mit Medienumgehung in Skype for Business Server](configure-trunk-with-media-bypass.md)

[Konfigurieren eines Trunks ohne Medienumgehung in Skype for Business Server](configure-trunk-without-media-bypass.md)

[Veröffentlichen ausstehender Änderungen an der Voiceroutingkonfiguration in Skype for Business](voice-route-config-changes.md)

[Bereitstellen der Medienumgehung in Skype for Business Server](deploy-media-bypass.md)

