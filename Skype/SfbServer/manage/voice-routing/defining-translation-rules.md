---
title: Definieren von Übersetzungsregeln in Skype für Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype für Business Server Enterprise-VoIP leitet Anrufe anhand von Telefonnummern in das e. 164-Format normalisiert. Dies bedeutet, dass alle gewählte Zeichenfolgen normalisiert werden müssen, in das e. 164-Format für die inverssuche (RNL) durchgeführt, damit sie ihren entsprechenden SIP-URI übersetzt werden können. Skype für Business Server bietet die Möglichkeit, die Darstellung der ID und die Rufnummernanzeige zu bearbeiten.
ms.openlocfilehash: e3feda41a3057ea6f0ae6d7946f3e21e75ba7f81
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "27223003"
---
# <a name="defining-translation-rules-in-skype-for-business-server"></a>Definieren von Übersetzungsregeln in Skype für Business Server

Skype für Business Server Enterprise-VoIP leitet Anrufe anhand von Telefonnummern in das e. 164-Format normalisiert. Dies bedeutet, dass alle gewählte Zeichenfolgen normalisiert werden müssen, in das e. 164-Format für die inverssuche (RNL) durchgeführt, damit sie ihren entsprechenden SIP-URI übersetzt werden können. Skype für Business Server bietet die Möglichkeit, die Darstellung der ID und die Rufnummernanzeige zu bearbeiten.

Mit Skype für Business Server Telefonnummer des angerufenen (d. h., die Telefonnummer genannt) aus dem e. 164-Format übersetzt werden kann, um die lokale Wählformat, die durch den trunkpeer (d. h., die zugehörigen Gateway, private Branch Exchange, Nebenstellenanlage (PBX) oder SIP erforderlich ist Trunk). Dazu müssen Sie eine oder mehrere Übersetzungsregeln definieren, um den Anforderungs-URI vor dem Routen an den Trunkpeer zu übersetzen.

## <a name="caller-id-presentation"></a>Rufnummernanzeige

Skype für Business Server bietet die Möglichkeit, auch die Rufnummer des Anrufers (d. h., die Telefonnummer, die der Aufrufer den Aufruf ausführt) übersetzen aus dem e. 164-Format an das lokale Wählformat, das durch den trunkpeer erforderlich ist. So können Sie zum Beispiel eine Übersetzungsregel schreiben, die die Angabe „+44“ am Beginn einer Wählzeichenfolge entfernt und durch „0144“ ersetzt.

**Anrufer-ID so konfigurieren Sie mithilfe der Skype Business Server-Systemsteuerung**

1. Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Weitere Informationen hierzu finden Sie unter [Delegieren von setupberechtigungen](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx).
2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL zum Öffnen der Systemsteuerung. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten der Skype für die Business-Systemsteuerung verwenden können, finden Sie unter [Installieren und open-Verwaltungstools](../../management-tools/install-and-open-administrative-tools.md).
3. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **Trunkkonfiguration**.
4. Doppelklicken Sie auf der Seite Trunkkonfiguration auf einen vorhandenen Trunk (z. B. auf den Trunk **Global**), um das Dialogfeld **Trunkkonfiguration bearbeiten** zu öffnen.
5. So konfigurieren Sie die Rufnummernanzeige:
    - Um eine oder mehrere Regeln aus einer Liste mit allen Übersetzungsregeln in Ihrer Bereitstellung von Enterprise-VoIP verfügbar auszuwählen, klicken Sie auf **auswählen**. Klicken Sie in **Übersetzungsregeln für die wählende Nummer** auf die Regeln, die Sie dem Trunk zuordnen möchten, und klicken Sie dann auf **OK**.
    - Klicken Sie auf **Neu**, um eine neue Übersetzungsregel zu definieren und dem Trunk zuzuordnen. 
    - Klicken Sie auf den Regelnamen und anschließend auf **Details anzeigen**, um eine Übersetzungsregel zu bearbeiten, die dem Trunk bereits zugeordnet ist.
    - Um eine vorhandene übersetzungsregel zu, als Ausgangspunkt zum Definieren einer neuen Regel zu kopieren, klicken Sie auf den Namen der Regel, klicken Sie auf **Kopieren**, und klicken Sie dann auf **Einfügen**.
    - Wenn Sie eine Übersetzungsregel vom Trunk entfernen möchten, markieren Sie den Regelnamen und klicken Sie auf **Entfernen**.

> [!Warning] 
> Ordnen Sie einem Trunk keine Übersetzungsregeln zu, wenn Sie Übersetzungsregeln für den zugeordneten Trunkpeer konfiguriert haben, da zwischen den beiden Regeln Konflikte auftreten könnten. 

## <a name="called-id-presentation"></a>Gewählte ID des angerufenen

> [!Important]
> Die Möglichkeit, einen Enterprise-VoIP-Routing testen eine oder mehrere Übersetzungsregeln zugeordnet ist als eine *alternative* zum Konfigurieren von Übersetzungsregeln für den trunkpeer verwendet werden soll. Ordnen Sie Übersetzungsregeln nicht mit einer Enterprise-VoIP-Routing testen, wenn Sie Übersetzungsregeln für den trunkpeer konfiguriert haben, da zwischen die zwei Regeln Konflikte auftreten könnten. 

Sie können eine der folgenden Methoden zum Erstellen oder Ändern einer übersetzungsregel zu verwenden:

- [Erstellen einer Übersetzungsregel-Tool verwenden](#create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool) , geben Sie Werte für die Anfangs-Ziffern, Länge, Ziffern zu entfernen und Ziffern hinzugefügt, und klicken Sie dann die Skype Business Server-Systemsteuerung zu den entsprechenden übereinstimmenden und die übersetzungsregel zu generieren.
- [Schreiben Sie reguläre Ausdrücke manuell](#create-or-modify-a-translation-rule-manually) in die entsprechenden und die übersetzungsregel zu definieren.

> [!Note]
> Informationen zum Schreiben von reguläre Ausdrücken finden Sie unter [Reguläre Ausdrücke von .NET Framework](http://go.microsoft.com/fwlink/p/?linkId=140927). 

### <a name="create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool"></a>Erstellen oder Ändern einer übersetzungsregel mit dem Erstellen einer Übersetzungsregel-tool

Gehen Sie folgendermaßen vor, wenn Sie eine übersetzungsregel definieren, indem Sie eine Gruppe von Werten in der Build ein Übersetzungsregel Tool eingeben und Aktivieren der Skype Business Server-Systemsteuerung auf den entsprechenden Vergleichsmuster und die übersetzungsregel zu generieren möchten. 

**So definieren Sie eine Regel mit dem Tool zum Erstellen einer Übersetzungsregel**

1. Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Weitere Informationen hierzu finden Sie unter [Delegieren von setupberechtigungen](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx).
2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL zum Öffnen der Systemsteuerung. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten der Skype für die Business-Systemsteuerung verwenden können, finden Sie unter [Installieren und open-Verwaltungstools](../../management-tools/install-and-open-administrative-tools.md).
3. Führen Sie zur Definition einer übersetzungsregel, führen Sie die Schritte in [Konfigurieren eines Trunks mit Medien umgehen](GET LINK AFTER MIGRATION)bis Schritt 10 oder [Konfigurieren eines Trunks ohne Media umgehen](GET LINK AFTER MIGRATION) bis Schritt 9.
4. Geben Sie unter **Name** auf der Seite **Neue Übersetzungsregel** oder **Übersetzungsregel bearbeiten** einen Namen ein, der das zu übersetzende Nummernmuster beschreibt.
5. (Optional) Geben Sie unter **Beschreibung**eine Beschreibung der übersetzungsregel - beispielsweise **US internationale Ferngespräche einwählen**.
6. Geben Sie im Abschnitt **Übersetzungsregel erstellen** des Dialogfelds die folgenden Werte ein:
    - **Anfangsziffern**: (Optional) Geben Sie die Anfangsziffern der Nummern ein, die Sie mit dem Muster abgleichen möchten. Geben Sie beispielsweise + in dieses Feld ein, um Nummern im E.164-Format abzugleichen (diese beginnen mit +).
    - **Länge**: Geben Sie die Anzahl von Ziffern im Vergleichsmuster ein und wählen Sie aus, ob mit dem Muster Nummern abgeglichen werden sollen, die exakt diese Länge, mindestens diese Länge oder eine beliebige Länge aufweisen. Geben Sie beispielsweise **11** ein und wählen Sie in der Dropdownliste die Einstellung **At least**, um Nummern abzugleichen, die mindestens 11 Ziffern umfassen.
    - **Zu entfernende Ziffern**: (Optional) Geben Sie die Anzahl von Anfangsziffern ein, die entfernt werden sollen. Geben Sie beispielsweise **1** ein, um das + am Anfang der Nummer zu entfernen.
    - **Hinzuzufügende Ziffern**: (Optional) Geben Sie die Ziffern ein, die der übersetzten Nummer vorangestellt werden sollen. Geben Sie beispielsweise **011** ein, wenn bei Anwendung der Regel der übersetzten Nummer die Ziffernfolge 011 vorangestellt werden soll.
    
    Die Werte, die Sie in diese Felder eingeben werden in den Feldern der Regel **Muster abgleichen** und **Übersetzung** wiedergegeben. Beispielsweise wenn Sie der vorstehend angeben, ist der resultierende reguläre Ausdruck im Feld **Muster für übereinstimmende**h:
    
    **^\+(\d{9}\d+)$** 

    Das Feld **Übersetzungsregel** gibt ein Muster für das Format der übersetzten Nummern an. Dieses Muster besteht aus zwei Teilen:
    - Einem Wert (z. B. **$1**), der die Anzahl von Ziffern im Vergleichsmuster repräsentiert
    - (Optional) Einem Wert, den Sie durch eine Eingabe im Feld **Hinzuzufügende Ziffern** voranstellen können

    Bei Verwendung der vorstehend genannten Beispiele wird der Wert **011$1** im Feld **Übersetzungsregel** angezeigt.
    
    Bei Anwendung dieser Übersetzungsregel wird die Nummer +441235551010 in 011441235551010 umgewandelt.
7. Klicken Sie auf **OK**, um die Übersetzungsregel zu speichern.
8. Klicken Sie auf **OK**, um die Trunkkonfiguration zu speichern.
9. Klicken Sie auf der Seite n **Trunk Configuratio**auf **Commit**, und klicken Sie dann auf **Commit alle**. 

> [!Note]
> Immer dann, wenn Sie eine Übersetzungsregel erstellen oder ändern, müssen Sie den Befehl **Commit für alle Elemente ausführen** ausführen, um die Konfigurationsänderung zu veröffentlichen. Weitere Informationen hierzu finden Sie unter [Veröffentlichen ausstehenden Änderungen an der VoIP-Routingkonfiguration](https://technet.microsoft.com/en-us/library/gg413088(v=ocs.15).aspx). 

### <a name="create-or-modify-a-translation-rule-manually"></a>Manuelles Erstellen oder Ändern einer übersetzungsregel

Gehen Sie folgendermaßen vor, wenn Sie eine übersetzungsregel, indem Sie einen regulären Ausdruck für das Vergleichsmuster schreiben und übersetzungsregel definieren möchten. 

**So definieren Sie eine Übersetzungsregel manuell**

1. Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Weitere Informationen hierzu finden Sie unter [Delegieren von setupberechtigungen](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx).
2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL zum Öffnen der Systemsteuerung. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten der Skype für die Business-Systemsteuerung verwenden können, finden Sie unter [Installieren und open-Verwaltungstools](../../management-tools/install-and-open-administrative-tools.md).
3. Führen Sie zur Definition einer übersetzungsregel, führen Sie die Schritte in [Konfigurieren eines Trunks mit Medien umgehen](GET LINK AFTER MIGRATION)bis Schritt 10 oder [Konfigurieren eines Trunks ohne Media umgehen](GET LINK AFTER MIGRATION) bis Schritt 9.
4. Geben Sie im Feld **Name** auf der Seite **Neue Übersetzungsregel** oder **Übersetzungsregel bearbeiten** einen Namen ein, der das zu übersetzende Nummernmuster beschreibt.
5. (Optional) Geben Sie im Feld **Beschreibung**eine Beschreibung der übersetzungsregel; beispielsweise **US internationale Ferngespräche einwählen**.
6. Klicken Sie im unteren Bereich des Abschnitts **Übersetzungsregel erstellen** auf **Bearbeiten**.
7. Geben Sie Folgendes in Typ einen **Regulären Ausdruck**:
    - Geben Sie unter **Übereinstimmung mit dem folgenden Muster** das Muster an, das für den Abgleich der zu übersetzenden Nummern verwendet werden soll.
    - Geben Sie unter **Übersetzungsregel** ein Muster für das Format der übersetzten Nummern an.

    Beispiel: bei Eingabe von ** ^ \+(\d{9}\d+)$** in **dieses Muster abgleichen** und **011$ 1** in **übersetzungsregel**übersetzt die Regel + 441235551010 in 011441235551010.
8. Klicken Sie auf **OK**, um die Übersetzungsregel zu speichern.
9. Klicken Sie auf **OK**, um die Trunkkonfiguration zu speichern.
10. Klicken Sie auf der Seite **Trunkkonfiguration** auf **Commit** und klicken Sie anschließend auf **Commit für alle Elemente ausführen**. 

> [!Note] 
> Immer dann, wenn Sie eine Übersetzungsregel erstellen oder ändern, müssen Sie den Befehl **Commit für alle Elemente ausführen** ausführen, um die Konfigurationsänderung zu veröffentlichen. Weitere Informationen hierzu finden Sie unter [Veröffentlichen ausstehenden Änderungen an der VoIP-Routingkonfiguration](https://technet.microsoft.com/en-us/library/gg413088(v=ocs.15).aspx). 