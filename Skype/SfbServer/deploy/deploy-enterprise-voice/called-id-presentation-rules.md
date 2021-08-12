---
title: Erstellen oder Ändern einer Übersetzungsregel für die Präsentation mit der Bezeichnung "ID" in Skype for Business Server
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
description: 'Zusammenfassung: Erfahren Sie, wie Sie eine Übersetzungsregel mithilfe des Tools zum Erstellen einer Übersetzungsregel in Skype for Business Server definieren.'
ms.openlocfilehash: 0f8f511996c8d3a578087c9f4252492fa03ef4237688bcaf68a04f09ed944116
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54281288"
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server"></a>Erstellen oder Ändern einer Übersetzungsregel für die Präsentation mit der Bezeichnung "ID" in Skype for Business Server

**Zusammenfassung:** Erfahren Sie, wie Sie eine Übersetzungsregel mithilfe des Tools zum Erstellen einer Übersetzungsregel in Skype for Business Server definieren.

Führen Sie die folgenden Schritte aus, wenn Sie eine Übersetzungsregel definieren möchten, indem Sie einen Satz von Werten in das Tool **"Übersetzungsregel** erstellen" eingeben und Skype for Business Server Systemsteuerung aktivieren, um das entsprechende Übereinstimmungsmuster und die Übersetzungsregel für Sie zu generieren. Alternativ können Sie einen regulären Ausdruck manuell schreiben, um das Übereinstimmungsmuster und die Übersetzungsregel zu definieren. Ausführliche Informationen finden Sie unter ["Manuelles Erstellen oder Ändern einer Übersetzungsregel".](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-translation-rule-manually)

### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a>So definieren Sie eine Regel mithilfe des Tools zum Erstellen einer Übersetzungsregel

1. Öffnen Sie Skype for Business Server Systemsteuerung.

2. Um mit dem Definieren einer Übersetzungsregel zu beginnen, führen Sie die Schritte unter [Konfigurieren eines Trunks mit Medienumgehung in Skype for Business Server](configure-trunk-with-media-bypass.md) bis Schritt 10 oder Konfigurieren eines [Trunks ohne Medienumgehung in Skype for Business Server](configure-trunk-without-media-bypass.md) bis Schritt 9 aus.

3. Geben Sie unter **"Name"** auf der Seite **"Neue Übersetzungsregel"** oder **"Übersetzungsregel bearbeiten"** einen Namen ein, der das zu übersetzende Nummernmuster beschreibt.

4. (Optional) Geben Sie unter **"Beschreibung"** eine Beschreibung der Übersetzungsregel ein, z. B. US International-Ferngespräche.

5. Geben Sie im Abschnitt **"Übersetzungsregel** erstellen" des Dialogfelds Werte in die folgenden Felder ein:

   - **Anfangsziffern:**(Optional) Geben Sie die führenden Ziffern von Zahlen an, mit denen das Muster übereinstimmen soll. Geben Sie z. B. in diesem Feld +ein, um Zahlen im E.164-Format zuzuordnen (die mit +beginnen).

   - **Länge:** Geben Sie die Anzahl der Ziffern im Vergleichsmuster an, und wählen Sie aus, ob das Muster Zahlen mit dieser Länge, mindestens dieser Länge oder einer beliebigen Länge entsprechen soll. Geben Sie beispielsweise 11 ein, und wählen Sie "Mindestens" in der Dropdownliste aus, um Nummern mit einer Länge von mindestens 11 Ziffern zuzuordnen.

   - **Zu entfernende Ziffern:**(Optional) Geben Sie die Anzahl der zu entfernenden Anfangsziffern an. Geben Sie beispielsweise 1 ein, um das Pluszeichen vom Anfang der Zahl zu entfernen.

   - **Hinzuzufügende Ziffern:**(Optional) Geben Sie Ziffern an, die den übersetzten Nummern vorangestellt werden sollen. Geben Sie z. B. 011 ein, wenn 011 den übersetzten Zahlen vorangestellt werden soll, wenn die Regel angewendet wird.

     Die Werte, die Sie in diese Felder eingeben, werden in den Feldern **Muster für** Übereinstimmung und **Übersetzungsregel** widergespiegelt. Wenn Sie beispielsweise die vorherigen Beispielwerte angeben, lautet der resultierende reguläre Ausdruck im Feld **"Muster zum Abgleichen"** wie folgt:

     ^\+(\d {9} \d+)$

     Das **Feld "Übersetzungsregel"** gibt ein Muster für das Format übersetzter Zahlen an. Dieses Muster hat zwei Teile:

   - Ein Wert (z. B. $1), der die Anzahl der Ziffern im Vergleichsmuster darstellt

   - (Optional) Ein Wert, dem Sie voranstellen können, indem Sie ihn in die **Ziffern eingeben, um** ein Feld hinzuzufügen.

     Unter Verwendung der vorstehenden Beispielwerte wird 011 $1 im **Feld "Übersetzungsregel"** angezeigt.

     Wenn diese Übersetzungsregel angewendet wird, wird +441235551010 011441235551010.

6. Klicken Sie auf **OK**, um die Übersetzungsregel zu speichern.

7. Klicken Sie auf **OK**, um die Trunkkonfiguration zu speichern.

8. Klicken Sie auf der Seite **Trunkkonfiguration** auf **Commit**, und klicken Sie anschließend auf **Commit für alle**.

   > [!NOTE]
   > Jedes Mal, wenn Sie eine Übersetzungsregel erstellen oder ändern, müssen Sie den Befehl **Commit für alle Elemente ausführen** ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter [Veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in Skype for Business](voice-route-config-changes.md) in der Betriebsdokumentation.

### <a name="to-define-a-translation-rule-manually"></a>So definieren Sie eine Übersetzungsregel manuell

1. Öffnen Skype for Business Server Systemsteuerung

2. Um mit dem Definieren einer Übersetzungsregel zu beginnen, führen Sie die Schritte unter [Konfigurieren eines Trunks mit Medienumgehung in Skype for Business Server](configure-trunk-with-media-bypass.md) bis Schritt 10 oder Konfigurieren eines [Trunks ohne Medienumgehung in Skype for Business Server](configure-trunk-without-media-bypass.md) bis Schritt 9 aus.

3. Geben Sie im Feld **Name** auf der Seite **Neue Übersetzungsregel** oder **Übersetzungsregel bearbeiten** einen Namen ein, der das zu übersetzende Nummernmuster beschreibt.

4. (Optional) Geben Sie in Beschreibung eine Beschreibung der Übersetzungsregel ein, z. B. US International-Ferngespräche.

5. Klicken Sie im unteren Bereich des Abschnitts **Übersetzungsregel erstellen** auf **Bearbeiten**.

6. Geben Sie in **Regulären Ausdruck eingeben** Folgendes ein:

   - Geben Sie unter **Übereinstimmung mit dem folgenden Muster** das Muster an, das für den Abgleich der zu übersetzenden Nummern verwendet werden soll.

   - Geben Sie unter **Übersetzungsregel** ein Muster für das Format der übersetzten Nummern an.

     Wenn Sie z. B. ^ \+ (\d {9} \d+)$ in **Übereinstimmung mit diesem Muster** und 011 $1 in der **Übersetzungsregel** eingeben, übersetzt die Regel +441235551010 in 011441235551010.

7. Klicken Sie auf **OK**, um die Übersetzungsregel zu speichern.

8. Klicken Sie auf **OK**, um die Trunkkonfiguration zu speichern.

9. Klicken Sie auf der Seite **Trunkkonfiguration** auf **Commit**, und klicken Sie anschließend auf **Commit für alle**.

    > [!NOTE]
    > Jedes Mal, wenn Sie eine Übersetzungsregel erstellen oder ändern, müssen Sie den Befehl **Commit für alle Elemente ausführen** ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter [Veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in Skype for Business](voice-route-config-changes.md) in der Betriebsdokumentation.

## <a name="see-also"></a>Siehe auch

[Konfigurieren eines Trunks mit Medienumgehung in Skype for Business Server](configure-trunk-with-media-bypass.md)

[Konfigurieren eines Trunks ohne Medienumgehung in Skype for Business Server](configure-trunk-without-media-bypass.md)

[Veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in Skype for Business](voice-route-config-changes.md)

[Bereitstellen der Medienumgehung in Skype for Business Server](deploy-media-bypass.md)