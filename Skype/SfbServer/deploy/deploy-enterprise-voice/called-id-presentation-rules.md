---
title: Erstellen oder Ändern einer übersetzungsregel für die gewählte ID Präsentation in Skype für Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
description: 'Zusammenfassung: Erfahren Sie, wie Sie eine übersetzungsregel mit dem Erstellen einer Übersetzungsregel-Tool in Skype für Business Server definieren.'
ms.openlocfilehash: 61c68f03ab3c9f1a34f9ae5c24f727954365fb6a
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "21006567"
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server"></a>Erstellen oder Ändern einer übersetzungsregel für die gewählte ID Präsentation in Skype für Business Server
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie eine übersetzungsregel mit dem Erstellen einer Übersetzungsregel-Tool in Skype für Business Server definieren.
  
Gehen Sie folgendermaßen vor, wenn Sie eine übersetzungsregel definieren durch Eingabe einer Gruppe von Werten in das Tool **eine Übersetzungsregel erstellen** und Aktivieren von Skype Business Server-Systemsteuerung auf den entsprechenden Vergleichsmuster und die übersetzungsregel zu generieren möchten. Alternativ können Sie manuell einen regulären Ausdruck erstellen, um das Vergleichsmuster und die Übersetzungsregel zu definieren. Weitere Informationen hierzu finden Sie unter [Erstellen oder Ändern einer Übersetzung Regel manuell](http://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx).
  
### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a>So definieren Sie eine Regel mit dem Tool zum Erstellen einer Übersetzungsregel

1. Öffnen von Skype Business Server-Systemsteuerung.
    
2. Führen Sie zur Definition einer übersetzungsregel, führen Sie die Schritte in [Konfigurieren eines Trunks mit Medien in Skype für Business Server umgehen](configure-trunk-with-media-bypass.md) bis Schritt 10 oder [Konfigurieren eines Trunks ohne Medien in Skype für Business Server umgehen](configure-trunk-without-media-bypass.md) bis Schritt 9.
    
3. Geben Sie unter **Name** auf der Seite **Neue Übersetzungsregel** oder **Übersetzungsregel bearbeiten** einen Namen ein, der das zu übersetzende Nummernmuster beschreibt.
    
4. (Optional) Geben Sie unter **Beschreibung**eine Beschreibung der übersetzungsregel für Beispiel uns International Ferngespräche.
    
5. Geben Sie im Abschnitt **Übersetzungsregel erstellen** des Dialogfelds die folgenden Werte ein:
    
   - **Anfangsziffern**: (Optional) Geben Sie die Anfangsziffern der Nummern ein, die Sie mit dem Muster abgleichen möchten. Geben Sie beispielsweise + in dieses Feld ein, um Nummern im E.164-Format abzugleichen (diese beginnen mit +).
    
   - **Länge**: Geben Sie die Anzahl von Ziffern im Vergleichsmuster ein und wählen Sie aus, ob mit dem Muster Nummern abgeglichen werden sollen, die exakt diese Länge, mindestens diese Länge oder eine beliebige Länge aufweisen. Geben Sie beispielsweise 11 und SelectAt in der Dropdown-Liste mit Zahlen übereinstimmen, die mindestens 11 Ziffern umfassen sind mindestens.
    
   - **Zu entfernende Ziffern**: (Optional) Geben Sie die Anzahl von Anfangsziffern ein, die entfernt werden sollen. Geben Sie beispielsweise 1 entfernen, um die + vom Beginn der Zahl.
    
   - **Hinzuzufügende Ziffern**: (Optional) Geben Sie die Ziffern ein, die der übersetzten Nummer vorangestellt werden sollen. Geben Sie beispielsweise 011 ein, wenn bei Anwendung der Regel der übersetzten Nummer die Ziffernfolge 011 vorangestellt werden soll.
    
    Die in diesen Feldern eingegebenen Werte werden in den Feldern **Muster für Vergleich** und **Übersetzungsregel** widergespiegelt. Wenn Sie beispielsweise die vorstehend genannten Beispielwerte verwenden, lautet der reguläre Ausdruck im Feld **Muster für Vergleich** wie folgt:
    
    ^\+(\d{9}\d+)$
    
    Das Feld **Übersetzungsregel** gibt ein Muster für das Format der übersetzten Nummern an. Dieses Muster besteht aus zwei Teilen:
    
   - Einem Wert (z. B. $1), der die Anzahl von Ziffern im Vergleichsmuster repräsentiert
    
   - (Optional) Einem Wert, den Sie durch eine Eingabe im Feld **Hinzuzufügende Ziffern** voranstellen können
    
    Bei Verwendung der vorstehend genannten Beispiele wird der Wert 011$1 im Feld **Übersetzungsregel** angezeigt.
    
    Bei Anwendung dieser Übersetzungsregel wird die Nummer +441235551010 in 011441235551010 umgewandelt.
    
6. Klicken Sie auf **OK**, um die Übersetzungsregel zu speichern.
    
7. Klicken Sie auf **OK**, um die Trunkkonfiguration zu speichern.
    
8. Klicken Sie auf der Seite **Trunkkonfiguration** auf **Commit** und klicken Sie anschließend auf **Commit für alle Elemente ausführen**. 
    
   > [!NOTE]
   > Immer dann, wenn Sie eine Übersetzungsregel erstellen oder ändern, müssen Sie den Befehl **Commit für alle Elemente ausführen** ausführen, um die Konfigurationsänderung zu veröffentlichen. Weitere Informationen hierzu finden Sie unter [Veröffentlichen ausstehenden Änderungen an der VoIP-Routingkonfiguration in Skype für Unternehmen](voice-route-config-changes.md) in der Betriebsdokumentation.
  
### <a name="to-define-a-translation-rule-manually"></a>So definieren Sie eine Übersetzungsregel manuell

1. Öffnen von Skype Business Server-Systemsteuerung
    
2. Führen Sie zur Definition einer übersetzungsregel, führen Sie die Schritte in [Konfigurieren eines Trunks mit Medien in Skype für Business Server umgehen](configure-trunk-with-media-bypass.md) bis Schritt 10 oder [Konfigurieren eines Trunks ohne Medien in Skype für Business Server umgehen](configure-trunk-without-media-bypass.md) bis Schritt 9.
    
3. Geben Sie im Feld **Name** auf der Seite **Neue Übersetzungsregel** oder **Übersetzungsregel bearbeiten** einen Namen ein, der das zu übersetzende Nummernmuster beschreibt.
    
4. (Optional) Geben Sie eine Beschreibung der übersetzungsregel, beispielsweise uns International Ferngespräche wählen im Feld **Beschreibung**.
    
5. Klicken Sie im unteren Bereich des Abschnitts **Übersetzungsregel erstellen** auf **Bearbeiten**.
    
6. Geben Sie unter **Regulären Ausdruck eingeben** Folgendes ein:
    
   - Geben Sie unter **Übereinstimmung mit dem folgenden Muster** das Muster an, das für den Abgleich der zu übersetzenden Nummern verwendet werden soll.
    
   - Geben Sie unter **Übersetzungsregel** ein Muster für das Format der übersetzten Nummern an.
    
    Beispiel: bei Eingabe ^\+(\d{9}\d+)$ in **dieses Muster abgleichen** and011$ 1 in **übersetzungsregel**, die Regel + 441235551010 in 011441235551010 übersetzt.
    
7. Klicken Sie auf **OK**, um die Übersetzungsregel zu speichern.
    
8. Klicken Sie auf **OK**, um die Trunkkonfiguration zu speichern.
    
9. Klicken Sie auf der Seite **Trunkkonfiguration** auf **Commit** und klicken Sie anschließend auf **Commit für alle Elemente ausführen**. 
    
    > [!NOTE]
    > Immer dann, wenn Sie eine Übersetzungsregel erstellen oder ändern, müssen Sie den Befehl **Commit für alle Elemente ausführen** ausführen, um die Konfigurationsänderung zu veröffentlichen. Weitere Informationen hierzu finden Sie unter [Veröffentlichen ausstehenden Änderungen an der VoIP-Routingkonfiguration in Skype für Unternehmen](voice-route-config-changes.md) in der Betriebsdokumentation.
  
## <a name="see-also"></a>Siehe auch

[Konfigurieren eines Trunks mit medienumgehung in Skype für Business Server](configure-trunk-with-media-bypass.md)
  
[Konfigurieren eines Trunks ohne medienumgehung in Skype für Business Server](configure-trunk-without-media-bypass.md)
  
[Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in Skype für Unternehmen](voice-route-config-changes.md)

[Die medienumgehung in Skype für Business Server bereitstellen](deploy-media-bypass.md)

