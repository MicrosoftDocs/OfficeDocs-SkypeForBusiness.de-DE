---
title: Definieren von Übersetzungsregeln in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business Server Enterprise-VoIP anrufe basierend auf Telefonnummern, die auf dem E.164-Format normalisiert sind. Dies bedeutet, dass alle gewählten Zeichenfolgen im E.164-Format normalisiert werden müssen, um die Reverse Number Lookup (RNL) durchführen zu können, damit sie in den entsprechenden SIP-URI übersetzt werden können. Skype for Business Server bietet die Möglichkeit, die aufgerufene ID und die Präsentation der Anrufer-ID zu bearbeiten.
ms.openlocfilehash: f3a37a48ec2e4497d644e2051a6e6d37ccef9707
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120907"
---
# <a name="defining-translation-rules-in-skype-for-business-server"></a>Definieren von Übersetzungsregeln in Skype for Business Server

Skype for Business Server Enterprise-VoIP anrufe basierend auf Telefonnummern, die auf dem E.164-Format normalisiert sind. Dies bedeutet, dass alle gewählten Zeichenfolgen im E.164-Format normalisiert werden müssen, um die Reverse Number Lookup (RNL) durchführen zu können, damit sie in den entsprechenden SIP-URI übersetzt werden können. Skype for Business Server bietet die Möglichkeit, die aufgerufene ID und die Präsentation der Anrufer-ID zu bearbeiten.

Bei Skype for Business Server kann die Telefonnummer des Angerufenen (d. h. die angerufene Telefonnummer) aus dem E.164-Format in das lokale Wählformat übersetzt werden, das vom Trunk-Peer (d. h. dem zugeordneten Gateway, der Nebenstellenanlage oder dem SIP-Trunk) benötigt wird. Dazu müssen Sie eine oder mehrere Übersetzungsregeln definieren, die die Anforderungs-URI übersetzen, bevor sie zu dem Trunk-Peer geroutet wird.

## <a name="caller-id-presentation"></a>Präsentation der Anrufer-ID

Skype for Business Server bietet die Möglichkeit, auch die Telefonnummer des Anrufers (d. h. die Telefonnummer, von der der Anrufer anruft) aus dem E.164-Format in das lokale Wählformat zu übersetzen, das vom Trunk-Peer benötigt wird. So können Sie zum Beispiel eine Übersetzungsregel schreiben, die die Angabe "+44" am Beginn einer Wählzeichenfolge entfernt und durch "0144" ersetzt.

**So konfigurieren Sie die Anrufer-ID mithilfe der Skype for Business Server-Systemsteuerung**

1. Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" am Computer an. Weitere Informationen finden Sie unter [Delegieren von Setupberechtigungen](/previous-versions/office/lync-server-2013/lync-server-2013-delegate-setup-permissions).
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Systemsteuerung zu öffnen. Weitere Informationen zu den verschiedenen Methoden zum Starten der Skype for Business-Systemsteuerung finden Sie unter [Installieren und Öffnen von Verwaltungstools](../../management-tools/install-and-open-administrative-tools.md).
3. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **Trunkkonfiguration**.
4. Doppelklicken Sie auf der Seite Trunkkonfiguration auf einen vorhandenen Trunk (z. B. auf den Trunk **Global**), um das Dialogfeld **Trunkkonfiguration bearbeiten** zu öffnen.
5. So konfigurieren Sie die Rufnummernanzeige:
    - Klicken Sie auf **Auswählen**, um eine oder mehrere Regeln aus einer Liste aller Übersetzungsregeln auszuwählen, die für Ihre Enterprise-VoIP-Bereitstellung zur Verfügung stehen. Klicken Sie in **Übersetzungsregeln für Anrufernummern** auf die Regeln, die Sie dem Trunk zuordnen möchten, und klicken Sie dann auf **OK**.
    - Wenn Sie eine neue Übersetzungsregel erstellen und dem Trunk zuordnen möchten, klicken Sie auf **Neu**. 
    - Klicken Sie auf den Regelnamen und anschließend auf **Details anzeigen**, um eine Übersetzungsregel zu bearbeiten, die bereits dem Trunk zugeordnet ist.
    - Klicken Sie zum Kopieren einer vorhandenen Übersetzungsregel, die als Ausgangspunkt zum Definieren einer neuen Regel verwendet werden soll, auf den Regelnamen, klicken Sie auf **Kopieren** und dann auf **Einfügen**.
    - Wenn Sie eine Übersetzungsregel vom Trunk entfernen möchten, markieren Sie den Regelnamen, und klicken Sie auf **Entfernen**.

> [!Warning] 
> Ordnen Sie einem Trunk keine Übersetzungsregeln zu, wenn Sie Übersetzungsregeln für den zugeordneten Trunkpeer konfiguriert haben, da zwischen den zwei Regeln Konflikte auftreten können. 

## <a name="called-id-presentation"></a>Präsentation mit der aufgerufenen ID

> [!Important]
> Die Möglichkeit, einer Enterprise-VoIP-Trunkkonfiguration eine oder mehrere Übersetzungsregeln zuzuweisen, bietet eine *Alternative* zur Konfiguration von Übersetzungsregeln für den Trunkpeer. Ordnen Sie einer Enterprise-VoIP-Trunkkonfiguration keine Übersetzungsregeln zu, wenn Sie Übersetzungsregeln für den Trunkpeer konfiguriert haben, da zwischen den zwei Regeln Konflikte auftreten könnten. 

Mithilfe einer der beiden folgenden Methoden können Sie eine Übersetzungsregel erstellen oder ändern:

- [](#create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool) Verwenden Sie das Tool Übersetzungsregel erstellen, um Werte für die anfangs zu entfernenden Ziffern, Längen, Ziffern und hinzuzufügenden Ziffern anzugeben, und lassen Sie dann die Skype for Business Server-Systemsteuerung das entsprechende Übereinstimmungsmuster und die entsprechende Übersetzungsregel generieren.
- [Schreiben Sie reguläre Ausdrücke manuell,](#create-or-modify-a-translation-rule-manually) um das übereinstimmende Muster und die Übersetzungsregel zu definieren.

> [!Note]
> Informationen zum Schreiben regulärer Ausdrücke finden Sie unter [.NET Framework Reguläre Ausdrücke](/dotnet/standard/base-types/regular-expressions). 

### <a name="create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool"></a>Erstellen oder Ändern einer Übersetzungsregel mithilfe des Tools Zum Erstellen einer Übersetzungsregel

Führen Sie diese Schritte aus, wenn Sie eine Übersetzungsregel definieren möchten, indem Sie einen Satz von Werten im Tool Übersetzungsregel erstellen eingeben und die Skype for Business Server-Systemsteuerung aktivieren, um das entsprechende Übereinstimmungsmuster und die entsprechende Übersetzungsregel für Sie zu generieren. 

**So definieren Sie eine Regel mithilfe des Tools Übersetzungsregel erstellen**

1. Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" am Computer an. Weitere Informationen finden Sie unter [Delegieren von Setupberechtigungen](/previous-versions/office/lync-server-2013/lync-server-2013-delegate-setup-permissions).
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Systemsteuerung zu öffnen. Weitere Informationen zu den verschiedenen Methoden zum Starten der Skype for Business-Systemsteuerung finden Sie unter [Installieren und Öffnen von Verwaltungstools](../../management-tools/install-and-open-administrative-tools.md).
3. Führen Sie die Schritte unter [Konfigurieren](GET LINK AFTER MIGRATION)eines Trunks mit Medienumgehung durch Schritt 10 oder [Konfigurieren](GET LINK AFTER MIGRATION) eines Trunks ohne Medienumgehung bis Schritt 9 aus, um mit dem Definieren einer Übersetzungsregel zu beginnen.
4. Geben **Sie unter Name** auf der Seite Neue **Übersetzungsregel** oder **Übersetzungsregel** bearbeiten einen Namen ein, der das zu übersetzende Nummernmuster beschreibt.
5. (Optional) Geben **Sie unter** Beschreibung eine Beschreibung der Übersetzungsregel ein, z. B. US International **Long-Distance Dialing**.
6. Geben Sie **im Abschnitt** Erstellen einer Übersetzungsregel des Dialogfelds Werte in die folgenden Felder ein:
    - **Anfangsziffern**: (Optional) Geben Sie die führenden Ziffern von Zahlen an, mit der das Muster übereinstimmen soll. Geben Sie z. B. + in dieses Feld ein, um Nummern im E.164-Format zu entsprechen (die mit +beginnen).
    - **Length**: Geben Sie die Anzahl der Ziffern im übereinstimmenden Muster an, und wählen Sie aus, ob das Muster Zahlen mit dieser Länge, mindestens dieser Länge oder einer beliebigen Länge entsprechen soll. Geben Sie beispielsweise **11 ein,** und wählen Sie **mindestens** in der Dropdownliste aus, um Zahlen mit einer Länge von mindestens 11 Ziffern zu entsprechen.
    - **Zu entfernende Ziffern:**(Optional) Geben Sie die Anzahl der zu entfernenden Anfangsziffern an. Geben Sie beispielsweise **1 ein,** um das + vom Anfang der Zahl zu streifen.
    - **Hinzuzufügende** Ziffern: (Optional) Geben Sie die Ziffern an, die den übersetzten Zahlen vorausgestellt werden sollen. Geben Sie z. **B. 011 ein,** wenn 011 auf die übersetzten Zahlen vorkondiert werden soll, wenn die Regel angewendet wird.
    
    Die Werte, die Sie in diese Felder eingeben, werden in den Feldern **Muster zu Übereinstimmung** und **Übersetzungsregel** angezeigt. Wenn Sie beispielsweise die vorherigen Beispielwerte angeben, ist der resultierende reguläre Ausdruck im Feld **Pattern to matc** h:
    
    **^\+(\d {9} \d+)$** 

    Das **Feld Übersetzungsregel** gibt ein Muster für das Format der übersetzten Zahlen an. Dieses Muster hat zwei Teile:
    - Ein Wert (z. B. **$1),** der die Anzahl der Ziffern im übereinstimmenden Muster darstellt.
    - (Optional) Ein Wert, den Sie vorausstellen können, indem Sie ihn in das Feld **Ziffern eingeben, das Hinzugefügt werden soll.**

    Unter Verwendung der obigen Beispielwerte wird **011$1** im Feld **Übersetzungsregel** angezeigt.
    
    Wenn diese Übersetzungsregel angewendet wird, wird +441235551010 zu 011441235551010.
7. Klicken Sie auf **OK**, um die Übersetzungsregel zu speichern.
8. Klicken Sie auf **OK**, um die Trunkkonfiguration zu speichern.
9. Klicken Sie **auf der Seite Trunk Configuratio** n auf **Commit** und dann auf Commit **für alle**. 

> [!Note]
> Jedes Mal, wenn Sie eine Übersetzungsregel erstellen oder ändern, müssen Sie den Befehl **Commit für alle Elemente ausführen** ausführen, um die Konfigurationsänderung zu veröffentlichen. Weitere Informationen finden Sie [unter Publish pending changes to the voice routing configuration](/previous-versions/office/lync-server-2013/lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration). 

### <a name="create-or-modify-a-translation-rule-manually"></a>Manuelles Erstellen oder Ändern einer Übersetzungsregel

Führen Sie diese Schritte aus, um eine Übersetzungsregel zu definieren, indem Sie einen regulären Ausdruck für das Vergleichsmuster und die Übersetzungsregel schreiben. 

**So definieren Sie eine Übersetzungsregel manuell**

1. Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" am Computer an. Weitere Informationen finden Sie unter [Delegieren von Setupberechtigungen](/previous-versions/office/lync-server-2013/lync-server-2013-delegate-setup-permissions).
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Systemsteuerung zu öffnen. Weitere Informationen zu den verschiedenen Methoden zum Starten der Skype for Business-Systemsteuerung finden Sie unter [Installieren und Öffnen von Verwaltungstools](../../management-tools/install-and-open-administrative-tools.md).
3. Führen Sie die Schritte unter [Konfigurieren](GET LINK AFTER MIGRATION)eines Trunks mit Medienumgehung durch Schritt 10 oder [Konfigurieren](GET LINK AFTER MIGRATION) eines Trunks ohne Medienumgehung bis Schritt 9 aus, um mit dem Definieren einer Übersetzungsregel zu beginnen.
4. Geben Sie im Feld **Name** auf der Seite **Neue Übersetzungsregel** oder **Übersetzungsregel bearbeiten** einen Namen ein, der das zu übersetzende Nummernmuster beschreibt.
5. (Optional) Geben **Sie unter Beschreibung** eine Beschreibung der Übersetzungsregel ein. beispiel: **US International long-distance dialing**.
6. Klicken Sie im unteren Bereich des Abschnitts **Übersetzungsregel erstellen** auf **Bearbeiten**.
7. Geben Sie Folgendes unter Geben Sie einen **regulären Ausdruck ein:**
    - Geben Sie unter **Übereinstimmung mit dem folgenden Muster** das Muster an, das für den Abgleich der zu übersetzenden Nummern verwendet werden soll.
    - Geben Sie unter **Übersetzungsregel** ein Muster für das Format der übersetzten Nummern an.

    Wenn Sie beispielsweise **^ \+ (\d {9} \d+)$** **in** Übereinstimmung mit diesem Muster und **011$1** **in** Übersetzungsregel eingeben, übersetzt die Regel +441235551010 in 011441235551010.
8. Klicken Sie auf **OK**, um die Übersetzungsregel zu speichern.
9. Klicken Sie auf **OK**, um die Trunkkonfiguration zu speichern.
10. Klicken Sie auf der Seite **Trunkkonfiguration** auf **Commit**, und klicken Sie anschließend auf **Commit für alle**. 

> [!Note] 
> Jedes Mal, wenn Sie eine Übersetzungsregel erstellen oder ändern, müssen Sie den Befehl **Commit für alle Elemente ausführen** ausführen, um die Konfigurationsänderung zu veröffentlichen. Weitere Informationen finden Sie [unter Publish pending changes to the voice routing configuration](/previous-versions/office/lync-server-2013/lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration).