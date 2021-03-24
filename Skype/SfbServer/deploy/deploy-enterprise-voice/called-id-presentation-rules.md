---
title: Erstellen oder Ändern einer Übersetzungsregel für die aufgerufene ID-Präsentation in Skype for Business Server
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
description: 'Zusammenfassung: Erfahren Sie, wie Sie eine Übersetzungsregel mithilfe des Tools Zum Erstellen einer Übersetzungsregel in Skype for Business Server definieren.'
ms.openlocfilehash: 3f4754184e69e7b574709d0272afc9989553cfe5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103641"
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server"></a>Erstellen oder Ändern einer Übersetzungsregel für die aufgerufene ID-Präsentation in Skype for Business Server

**Zusammenfassung:** Erfahren Sie, wie Sie eine Übersetzungsregel mithilfe des Tools Zum Erstellen einer Übersetzungsregel in Skype for Business Server definieren.

Führen Sie diese Schritte aus, wenn Sie eine Übersetzungsregel definieren möchten, indem Sie einen Satz von Werten im **Tool** Übersetzungsregel erstellen eingeben und skype for Business Server-Systemsteuerung das entsprechende Übereinstimmungsmuster und die entsprechende Übersetzungsregel für Sie generieren können. Alternativ können Sie einen regulären Ausdruck manuell schreiben, um das übereinstimmende Muster und die Übersetzungsregel zu definieren. Weitere Informationen finden Sie unter [Manuelles Erstellen oder Ändern einer Übersetzungsregel.](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-translation-rule-manually)

### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a>So definieren Sie eine Regel mithilfe des Tools Übersetzungsregel erstellen

1. Öffnen Sie die Skype for Business Server-Systemsteuerung.

2. Führen Sie die Schritte unter Konfigurieren eines Trunks mit Medienumgehung [in Skype for Business Server](configure-trunk-with-media-bypass.md) bis Schritt 10 oder Konfigurieren eines Trunks ohne Medienumgehung in Skype for Business [Server](configure-trunk-without-media-bypass.md) bis Schritt 9 aus, um mit dem Definieren einer Übersetzungsregel zu beginnen.

3. Geben **Sie unter Name** auf der Seite Neue **Übersetzungsregel** oder **Übersetzungsregel** bearbeiten einen Namen ein, der das zu übersetzende Nummernmuster beschreibt.

4. (Optional) Geben **Sie unter** Beschreibung eine Beschreibung der Übersetzungsregel ein, z. B. us International Long-Distance Dialing.

5. Geben Sie **im Abschnitt** Erstellen einer Übersetzungsregel des Dialogfelds Werte in die folgenden Felder ein:

   - **Anfangsziffern**: (Optional) Geben Sie die führenden Ziffern von Zahlen an, mit der das Muster übereinstimmen soll. Geben Sie z. B. + in dieses Feld ein, um Nummern im E.164-Format zu entsprechen (die mit +beginnen).

   - **Length**: Geben Sie die Anzahl der Ziffern im übereinstimmenden Muster an, und wählen Sie aus, ob das Muster Zahlen mit dieser Länge, mindestens dieser Länge oder einer beliebigen Länge entsprechen soll. Geben Sie z. B. 11 ein, und wählen Sie Mindestens in der Dropdownliste aus, um Zahlen zu entsprechen, die mindestens 11 Ziffern lang sind.

   - **Zu entfernende Ziffern:**(Optional) Geben Sie die Anzahl der zu entfernenden Anfangsziffern an. Geben Sie z. B. 1 ein, um das + vom Anfang der Zahl zu streifen.

   - **Hinzuzufügende** Ziffern: (Optional) Geben Sie die Ziffern an, die den übersetzten Zahlen vorausgestellt werden sollen. Geben Sie z. B. 011 ein, wenn 011 auf die übersetzten Zahlen vorkondiert werden soll, wenn die Regel angewendet wird.

     Die Werte, die Sie in diese Felder eingeben, werden in den Feldern **Muster zu Übereinstimmung** und **Übersetzungsregel** angezeigt. Wenn Sie z. B. die obigen Beispielwerte angeben, ist der resultierende reguläre Ausdruck im **Feld Muster für Übereinstimmung:**

     ^\+(\d {9} \d+)$

     Das **Feld Übersetzungsregel** gibt ein Muster für das Format der übersetzten Zahlen an. Dieses Muster hat zwei Teile:

   - Ein Wert (z. B. $1), der die Anzahl der Ziffern im übereinstimmenden Muster darstellt.

   - (Optional) Ein Wert, den Sie vorausstellen können, indem Sie ihn in das Feld **Ziffern eingeben, das Hinzugefügt werden soll.**

     Unter Verwendung der obigen Beispielwerte wird 011$1 im Feld **Übersetzungsregel** angezeigt.

     Wenn diese Übersetzungsregel angewendet wird, wird +441235551010 zu 011441235551010.

6. Klicken Sie auf **OK**, um die Übersetzungsregel zu speichern.

7. Klicken Sie auf **OK**, um die Trunkkonfiguration zu speichern.

8. Klicken Sie auf der Seite **Trunkkonfiguration** auf **Commit**, und klicken Sie anschließend auf **Commit für alle**.

   > [!NOTE]
   > Jedes Mal, wenn Sie eine Übersetzungsregel erstellen oder ändern, müssen Sie den Befehl **Commit für alle Elemente ausführen** ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie [unter Veröffentlichen ausstehender Änderungen an der Voiceroutingkonfiguration in Skype for Business](voice-route-config-changes.md) in der Betriebsdokumentation.

### <a name="to-define-a-translation-rule-manually"></a>So definieren Sie eine Übersetzungsregel manuell

1. Öffnen der Skype for Business Server-Systemsteuerung

2. Führen Sie die Schritte unter Konfigurieren eines Trunks mit Medienumgehung [in Skype for Business Server](configure-trunk-with-media-bypass.md) bis Schritt 10 oder Konfigurieren eines Trunks ohne Medienumgehung in Skype for Business [Server](configure-trunk-without-media-bypass.md) bis Schritt 9 aus, um mit dem Definieren einer Übersetzungsregel zu beginnen.

3. Geben Sie im Feld **Name** auf der Seite **Neue Übersetzungsregel** oder **Übersetzungsregel bearbeiten** einen Namen ein, der das zu übersetzende Nummernmuster beschreibt.

4. (Optional) Geben **Sie in Beschreibung** eine Beschreibung der Übersetzungsregel ein, z. B. us International Long-Distance Dialing.

5. Klicken Sie im unteren Bereich des Abschnitts **Übersetzungsregel erstellen** auf **Bearbeiten**.

6. Geben Sie in **Regulären Ausdruck eingeben** Folgendes ein:

   - Geben Sie unter **Übereinstimmung mit dem folgenden Muster** das Muster an, das für den Abgleich der zu übersetzenden Nummern verwendet werden soll.

   - Geben Sie unter **Übersetzungsregel** ein Muster für das Format der übersetzten Nummern an.

     Wenn Sie beispielsweise ^(\d \d+)$ in Übereinstimmung mit diesem Muster und011$1 in Übersetzungsregel eingeben, übersetzt die Regel \+ {9} +441235551010 in 011441235551010.  

7. Klicken Sie auf **OK**, um die Übersetzungsregel zu speichern.

8. Klicken Sie auf **OK**, um die Trunkkonfiguration zu speichern.

9. Klicken Sie auf der Seite **Trunkkonfiguration** auf **Commit**, und klicken Sie anschließend auf **Commit für alle**.

    > [!NOTE]
    > Jedes Mal, wenn Sie eine Übersetzungsregel erstellen oder ändern, müssen Sie den Befehl **Commit für alle Elemente ausführen** ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie [unter Veröffentlichen ausstehender Änderungen an der Voiceroutingkonfiguration in Skype for Business](voice-route-config-changes.md) in der Betriebsdokumentation.

## <a name="see-also"></a>Siehe auch

[Konfigurieren eines Trunks mit Medienumgehung in Skype for Business Server](configure-trunk-with-media-bypass.md)

[Konfigurieren eines Trunks ohne Medienumgehung in Skype for Business Server](configure-trunk-without-media-bypass.md)

[Veröffentlichen ausstehender Änderungen an der Voiceroutingkonfiguration in Skype for Business](voice-route-config-changes.md)

[Bereitstellen der Medienumgehung in Skype for Business Server](deploy-media-bypass.md)