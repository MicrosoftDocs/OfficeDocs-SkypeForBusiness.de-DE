---
title: Definieren von Übersetzungsregeln in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business Server Enterprise-VoIP leitet Anrufe basierend auf Telefonnummern, die im E. 164-Format normalisiert sind, weiter. Das bedeutet, dass alle gewählten Zeichenfolgen im E. 164-Format normalisiert werden müssen, um RNL (Reverse Number Lookup) durchzuführen, damit Sie in den entsprechenden SIP-URI übersetzt werden können. Skype for Business Server bietet die Möglichkeit zum Manipulieren der angerufenen ID und der Rufnummernanzeige.
ms.openlocfilehash: cdcfe3a847e148461b97abed33df070057dcd00b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816985"
---
# <a name="defining-translation-rules-in-skype-for-business-server"></a>Definieren von Übersetzungsregeln in Skype for Business Server

Skype for Business Server Enterprise-VoIP leitet Anrufe basierend auf Telefonnummern, die im E. 164-Format normalisiert sind, weiter. Das bedeutet, dass alle gewählten Zeichenfolgen im E. 164-Format normalisiert werden müssen, um RNL (Reverse Number Lookup) durchzuführen, damit Sie in den entsprechenden SIP-URI übersetzt werden können. Skype for Business Server bietet die Möglichkeit zum Manipulieren der angerufenen ID und der Rufnummernanzeige.

Mit Skype for Business Server kann die Telefonnummer des angerufenen (also die Telefonnummer) vom E. 164-Format in das lokale Wählformat übersetzt werden, das für den trunk-Peer erforderlich ist (also das zugeordnete Gateway, die Private Branch Exchange (PBX) oder SIP trunk). Dazu müssen Sie eine oder mehrere Übersetzungsregeln definieren, um den Anforderungs-URI vor dem Routen an den Trunkpeer zu übersetzen.

## <a name="caller-id-presentation"></a>Präsentation für Anrufer-ID

Skype for Business Server bietet die Möglichkeit, die Telefonnummer des anrufenden Mitarbeiters (also die Telefonnummer, von der der Anrufer angerufen wird) aus dem E. 164-Format in das lokale Wählformat zu übersetzen, das vom trunk-Peer benötigt wird. So können Sie zum Beispiel eine Übersetzungsregel schreiben, die die Angabe „+44“ am Beginn einer Wählzeichenfolge entfernt und durch „0144“ ersetzt.

**So konfigurieren Sie die Rufnummernanzeige mithilfe des Skype for Business Server-Control Panels**

1. Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter [Delegieren von Setup Berechtigungen](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx).
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die Systemsteuerung zu öffnen. Einzelheiten zu den verschiedenen Methoden, mit denen Sie das Skype Control Panel für Unternehmen starten können, finden Sie unter [Installieren und Öffnen von Verwaltungstools](../../management-tools/install-and-open-administrative-tools.md).
3. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **Trunkkonfiguration**.
4. Doppelklicken Sie auf der Seite Trunkkonfiguration auf einen vorhandenen Trunk (z. B. auf den Trunk **Global**), um das Dialogfeld **Trunkkonfiguration bearbeiten** zu öffnen.
5. So konfigurieren Sie die Rufnummernanzeige:
    - Wenn Sie eine oder mehrere Regeln aus einer Liste aller Übersetzungen auswählen möchten, die in Ihrer Enterprise-VoIP-Bereitstellung verfügbar sind, klicken Sie auf **auswählen**. Klicken Sie in **Übersetzungsregeln für die wählende Nummer** auf die Regeln, die Sie dem Trunk zuordnen möchten, und klicken Sie dann auf **OK**.
    - Klicken Sie auf **Neu**, um eine neue Übersetzungsregel zu definieren und dem Trunk zuzuordnen. 
    - Klicken Sie auf den Regelnamen und anschließend auf **Details anzeigen**, um eine Übersetzungsregel zu bearbeiten, die dem Trunk bereits zugeordnet ist.
    - Wenn Sie eine vorhandene Übersetzungsregel kopieren möchten, um Sie als Ausgangspunkt für die Definition einer neuen Regel zu verwenden, klicken Sie auf den Namen der Regel, klicken Sie auf **Kopieren**, und klicken Sie dann auf **Einfügen**.
    - Wenn Sie eine Übersetzungsregel vom Trunk entfernen möchten, markieren Sie den Regelnamen und klicken Sie auf **Entfernen**.

> [!Warning] 
> Ordnen Sie einem Trunk keine Übersetzungsregeln zu, wenn Sie Übersetzungsregeln für den zugeordneten Trunkpeer konfiguriert haben, da zwischen den beiden Regeln Konflikte auftreten könnten. 

## <a name="called-id-presentation"></a>Aufgerufene ID-Präsentation

> [!Important]
> Die Möglichkeit, eine oder mehrere Übersetzungsregeln einer Enterprise Voice trunk-Konfiguration zuzuordnen, dient als *Alternative* zum Konfigurieren von Übersetzungsregeln für den trunk-Peer. Ordnen Sie Übersetzungsregeln keiner Enterprise-VoIP-trunk-Konfiguration zu, wenn Sie Übersetzungsregeln für den trunk-Peer konfiguriert haben, da die beiden Regeln möglicherweise in Konflikt stehen. 

Sie können eine der folgenden Methoden verwenden, um eine Übersetzungsregel zu erstellen oder zu ändern:

- [Verwenden Sie das Tool zum Erstellen einer Übersetzungsregel](#create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool) , um Werte für die Anfangsziffern, die Länge, die zu entfernenden Ziffern und die hinzuzufügenden Ziffern anzugeben, und lassen Sie dann das entsprechende Übereinstimmungsmuster und die Übersetzungsregel für das Skype for Business Server-Control Panel generieren.
- [Schreiben Sie reguläre Ausdrücke manuell](#create-or-modify-a-translation-rule-manually) , um das übereinstimmende Muster und die Übersetzungsregel zu definieren.

> [!Note]
> Informationen dazu, wie reguläre Ausdrücke geschrieben werden, finden Sie unter [.NET Framework-reguläre Ausdrücke](http://go.microsoft.com/fwlink/p/?linkId=140927). 

### <a name="create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool"></a>Erstellen oder Ändern einer Übersetzungsregel mithilfe des Tools zum Erstellen einer Übersetzungsregel

Führen Sie die folgenden Schritte aus, wenn Sie eine Übersetzungsregel definieren möchten, indem Sie eine Gruppe von Werten in das Tool zum Erstellen einer Übersetzungsregel eingeben und die Skype for Business Server-Systemsteuerung aktivieren, um das entsprechende Übereinstimmungsmuster und die Übersetzungsregel für Sie zu generieren. 

**So definieren Sie eine Regel mit dem Tool zum Erstellen einer Übersetzungsregel**

1. Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter [Delegieren von Setup Berechtigungen](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx).
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die Systemsteuerung zu öffnen. Einzelheiten zu den verschiedenen Methoden, mit denen Sie das Skype Control Panel für Unternehmen starten können, finden Sie unter [Installieren und Öffnen von Verwaltungstools](../../management-tools/install-and-open-administrative-tools.md).
3. Wenn Sie mit dem Definieren einer Übersetzungsregel beginnen möchten, führen Sie die Schritte unter [Konfigurieren eines Trunks mit medienumgehung](GET LINK AFTER MIGRATION)durch Schritt 10 aus, oder [Konfigurieren Sie einen trunk ohne medienumgehung](GET LINK AFTER MIGRATION) in Schritt 9.
4. Geben Sie unter **Name** auf der Seite **Neue Übersetzungsregel** oder **Übersetzungsregel bearbeiten** einen Namen ein, der das zu übersetzende Nummernmuster beschreibt.
5. Optional Geben Sie unter **Beschreibung**eine Beschreibung der Übersetzungsregel ein, beispielsweise die **US-Auslands Wahl für Ferngespräche**.
6. Geben Sie im Abschnitt **Übersetzungsregel erstellen** des Dialogfelds die folgenden Werte ein:
    - **Anfangsziffern**: (Optional) Geben Sie die Anfangsziffern der Nummern ein, die Sie mit dem Muster abgleichen möchten. Geben Sie beispielsweise + in dieses Feld ein, um Nummern im E.164-Format abzugleichen (diese beginnen mit +).
    - **Länge**: Geben Sie die Anzahl von Ziffern im Vergleichsmuster ein und wählen Sie aus, ob mit dem Muster Nummern abgeglichen werden sollen, die exakt diese Länge, mindestens diese Länge oder eine beliebige Länge aufweisen. Geben Sie beispielsweise **11** ein und wählen Sie in der Dropdownliste die Einstellung **At least**, um Nummern abzugleichen, die mindestens 11 Ziffern umfassen.
    - **Zu entfernende Ziffern**: (Optional) Geben Sie die Anzahl von Anfangsziffern ein, die entfernt werden sollen. Geben Sie beispielsweise **1** ein, um das + am Anfang der Nummer zu entfernen.
    - **Hinzuzufügende Ziffern**: (Optional) Geben Sie die Ziffern ein, die der übersetzten Nummer vorangestellt werden sollen. Geben Sie beispielsweise **011** ein, wenn bei Anwendung der Regel der übersetzten Nummer die Ziffernfolge 011 vorangestellt werden soll.
    
    Die Werte, die Sie in diese Felder eingeben, werden in den Feldern **Muster in Übereinstimmung** und **Übersetzungs** Regel widergespiegelt. Wenn Sie beispielsweise die vorhergehenden Beispielwerte angeben, lautet der resultierende reguläre Ausdruck im Feld **Pattern to matc**h wie folgt:
    
    **^\+(\d{9}\d +) $** 

    Das Feld **Übersetzungsregel** gibt ein Muster für das Format der übersetzten Nummern an. Dieses Muster besteht aus zwei Teilen:
    - Einem Wert (z. B. **$1**), der die Anzahl von Ziffern im Vergleichsmuster repräsentiert
    - (Optional) Einem Wert, den Sie durch eine Eingabe im Feld **Hinzuzufügende Ziffern** voranstellen können

    Bei Verwendung der vorstehend genannten Beispiele wird der Wert **011$1** im Feld **Übersetzungsregel** angezeigt.
    
    Bei Anwendung dieser Übersetzungsregel wird die Nummer +441235551010 in 011441235551010 umgewandelt.
7. Klicken Sie auf **OK**, um die Übersetzungsregel zu speichern.
8. Klicken Sie auf **OK**, um die Trunkkonfiguration zu speichern.
9. Klicken Sie auf der Seite **trunk-Konfiguratio**n auf **Commit**, und klicken Sie dann auf **alle**übernehmen. 

> [!Note]
> Immer dann, wenn Sie eine Übersetzungsregel erstellen oder ändern, müssen Sie den Befehl **Commit für alle Elemente ausführen** ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter [veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration](https://technet.microsoft.com/en-us/library/gg413088(v=ocs.15).aspx). 

### <a name="create-or-modify-a-translation-rule-manually"></a>Manuelles Erstellen oder Ändern einer Übersetzungsregel

Führen Sie die folgenden Schritte aus, wenn Sie eine Übersetzungsregel definieren möchten, indem Sie einen regulären Ausdruck für das Übereinstimmungsmuster und die Übersetzungsregel schreiben. 

**So definieren Sie eine Übersetzungsregel manuell**

1. Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter [Delegieren von Setup Berechtigungen](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx).
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die Systemsteuerung zu öffnen. Einzelheiten zu den verschiedenen Methoden, mit denen Sie das Skype Control Panel für Unternehmen starten können, finden Sie unter [Installieren und Öffnen von Verwaltungstools](../../management-tools/install-and-open-administrative-tools.md).
3. Wenn Sie mit dem Definieren einer Übersetzungsregel beginnen möchten, führen Sie die Schritte unter [Konfigurieren eines Trunks mit medienumgehung](GET LINK AFTER MIGRATION)durch Schritt 10 aus, oder [Konfigurieren Sie einen trunk ohne medienumgehung](GET LINK AFTER MIGRATION) in Schritt 9.
4. Geben Sie im Feld **Name** auf der Seite **Neue Übersetzungsregel** oder **Übersetzungsregel bearbeiten** einen Namen ein, der das zu übersetzende Nummernmuster beschreibt.
5. Optional Geben Sie in **Beschreibung**eine Beschreibung der Übersetzungsregel ein. Beispiel: **Auslandsgespräche**in den USA.
6. Klicken Sie im unteren Bereich des Abschnitts **Übersetzungsregel erstellen** auf **Bearbeiten**.
7. Geben Sie Folgendes ein, und geben Sie einen **regulären Ausdruck**ein:
    - Geben Sie unter **Übereinstimmung mit dem folgenden Muster** das Muster an, das für den Abgleich der zu übersetzenden Nummern verwendet werden soll.
    - Geben Sie unter **Übersetzungsregel** ein Muster für das Format der übersetzten Nummern an.

    Wenn Sie beispielsweise ** ^ \+{9}(\d \d +) $** in **Übereinstimmung mit diesem Muster** und **011 $1** in der **Übersetzungsregel**eingeben, wird die Regel + 441235551010 in 011441235551010 übersetzen.
8. Klicken Sie auf **OK**, um die Übersetzungsregel zu speichern.
9. Klicken Sie auf **OK**, um die Trunkkonfiguration zu speichern.
10. Klicken Sie auf der Seite **Trunkkonfiguration** auf **Commit** und klicken Sie anschließend auf **Commit für alle Elemente ausführen**. 

> [!Note] 
> Immer dann, wenn Sie eine Übersetzungsregel erstellen oder ändern, müssen Sie den Befehl **Commit für alle Elemente ausführen** ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter [veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration](https://technet.microsoft.com/en-us/library/gg413088(v=ocs.15).aspx). 
