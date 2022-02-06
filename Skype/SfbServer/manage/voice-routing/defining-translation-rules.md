---
title: Definieren von Übersetzungsregeln in Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
description: 'Skype for Business Server Enterprise-VoIP leitet Anrufe basierend auf Telefonnummern weiter, die in das E.164-Format normalisiert sind. Dies bedeutet, dass alle gewählten Zeichenfolgen in das E.164-Format normalisiert werden müssen, um eine umgekehrte Nummernsuche (Reverse Number Lookup, RNL) durchzuführen, damit sie in den entsprechenden SIP-URI übersetzt werden können. Skype for Business Server bietet die Möglichkeit, die aufgerufene ID und die Darstellung der Anrufer-ID zu bearbeiten.'
---

# <a name="defining-translation-rules-in-skype-for-business-server"></a>Definieren von Übersetzungsregeln in Skype for Business Server

Skype for Business Server Enterprise-VoIP leitet Anrufe basierend auf Telefonnummern weiter, die in das E.164-Format normalisiert sind. Dies bedeutet, dass alle gewählten Zeichenfolgen in das E.164-Format normalisiert werden müssen, um eine umgekehrte Nummernsuche (Reverse Number Lookup, RNL) durchzuführen, damit sie in den entsprechenden SIP-URI übersetzt werden können. Skype for Business Server bietet die Möglichkeit, die aufgerufene ID und die Darstellung der Anrufer-ID zu bearbeiten.

Mit Skype for Business Server kann die Telefonnummer des angerufenen Teilnehmers (d. h. die angerufene Telefonnummer) aus dem E.164-Format in das lokale Wählformat übersetzt werden, das vom Trunkpeer (d. h. dem zugeordneten Gateway, der Nebenstellenanlage oder dem SIP-Trunk) benötigt wird. Dazu müssen Sie eine oder mehrere Übersetzungsregeln definieren, die die Anforderungs-URI übersetzen, bevor sie zu dem Trunk-Peer geroutet wird.

## <a name="caller-id-presentation"></a>Darstellung der Anrufer-ID

Skype for Business Server bietet die Möglichkeit, auch die Telefonnummer des Anrufers (d. h. die Telefonnummer, aus der der Anrufer anruft) aus dem E.164-Format in das lokale Wählformat zu übersetzen, das vom Trunkpeer benötigt wird. So können Sie zum Beispiel eine Übersetzungsregel schreiben, die die Angabe "+44" am Beginn einer Wählzeichenfolge entfernt und durch "0144" ersetzt.

**So konfigurieren Sie die Anrufer-ID mithilfe der Skype for Business Server Systemsteuerung**

1. Melden Sie sich am Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter ["Stellvertretungs-Setupberechtigungen"](/previous-versions/office/lync-server-2013/lync-server-2013-delegate-setup-permissions).
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten der Skype for Business Systemsteuerung verwenden können, finden Sie unter [Installieren und Öffnen von Verwaltungstools](../../management-tools/install-and-open-administrative-tools.md).
3. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **Trunkkonfiguration**.
4. Doppelklicken Sie auf der Seite Trunkkonfiguration auf einen vorhandenen Trunk (z. B. auf den Trunk **Global**), um das Dialogfeld **Trunkkonfiguration bearbeiten** zu öffnen.
5. So konfigurieren Sie die Rufnummernanzeige:
    - Klicken Sie auf **Auswählen**, um eine oder mehrere Regeln aus einer Liste aller Übersetzungsregeln auszuwählen, die für Ihre Enterprise-VoIP-Bereitstellung zur Verfügung stehen. Klicken Sie in **Übersetzungsregeln für Anrufernummern** auf die Regeln, die Sie dem Trunk zuordnen möchten, und klicken Sie dann auf **OK**.
    - Wenn Sie eine neue Übersetzungsregel erstellen und dem Trunk zuordnen möchten, klicken Sie auf **Neu**. 
    - Klicken Sie auf den Regelnamen und anschließend auf **Details anzeigen**, um eine Übersetzungsregel zu bearbeiten, die bereits dem Trunk zugeordnet ist.
    - Um eine vorhandene Übersetzungsregel zu kopieren, die als Ausgangspunkt für die Definition einer neuen Regel verwendet wird, klicken Sie auf den Regelnamen, klicken Sie auf **"Kopieren**" und dann auf " **Einfügen**".
    - Wenn Sie eine Übersetzungsregel vom Trunk entfernen möchten, markieren Sie den Regelnamen, und klicken Sie auf **Entfernen**.

> [!Warning] 
> Ordnen Sie einem Trunk keine Übersetzungsregeln zu, wenn Sie Übersetzungsregeln für den zugeordneten Trunkpeer konfiguriert haben, da zwischen den zwei Regeln Konflikte auftreten können. 

## <a name="called-id-presentation"></a>Id-Präsentation aufgerufen

> [!Important]
> Die Möglichkeit, einer Enterprise-VoIP-Trunkkonfiguration eine oder mehrere Übersetzungsregeln zuzuweisen, bietet eine *Alternative* zur Konfiguration von Übersetzungsregeln für den Trunkpeer. Ordnen Sie einer Enterprise-VoIP-Trunkkonfiguration keine Übersetzungsregeln zu, wenn Sie Übersetzungsregeln für den Trunkpeer konfiguriert haben, da zwischen den zwei Regeln Konflikte auftreten könnten. 

Mithilfe einer der beiden folgenden Methoden können Sie eine Übersetzungsregel erstellen oder ändern:

- [Verwenden Sie das Tool Zum Erstellen einer Übersetzungsregel](#create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool), um Werte für die anfangsziffern, die Länge, die zu entfernenden Ziffern und die hinzuzufügenden Ziffern anzugeben, und lassen Sie dann die Skype for Business Server Systemsteuerung das entsprechende Vergleichsmuster und die Übersetzungsregel für Sie generieren.
- [Schreiben Sie reguläre Ausdrücke manuell](#create-or-modify-a-translation-rule-manually) , um das Übereinstimmungsmuster und die Übersetzungsregel zu definieren.

> [!Note]
> Informationen zum Schreiben regulärer Ausdrücke finden Sie unter [.NET Framework Reguläre Ausdrücke](/dotnet/standard/base-types/regular-expressions). 

### <a name="create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool"></a>Erstellen oder Ändern einer Übersetzungsregel mithilfe des Tools "Übersetzungsregel erstellen"

Führen Sie die folgenden Schritte aus, wenn Sie eine Übersetzungsregel definieren möchten, indem Sie einen Satz von Werten in das Tool "Übersetzungsregel erstellen" eingeben und die Skype for Business Server Systemsteuerung aktivieren, um das entsprechende Übereinstimmungsmuster und die Übersetzungsregel für Sie zu generieren. 

**So definieren Sie eine Regel mithilfe des Tools zum Erstellen einer Übersetzungsregel**

1. Melden Sie sich am Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter ["Stellvertretungs-Setupberechtigungen"](/previous-versions/office/lync-server-2013/lync-server-2013-delegate-setup-permissions).
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten der Skype for Business Systemsteuerung verwenden können, finden Sie unter [Installieren und Öffnen von Verwaltungstools](../../management-tools/install-and-open-administrative-tools.md).
3. Um mit dem Definieren einer Übersetzungsregel zu beginnen, führen Sie die Schritte unter [Konfigurieren eines Trunks mit Medienumgehung](GET LINK AFTER MIGRATION) durch Schritt 10 oder [Konfigurieren eines Trunks ohne Medienumgehung](GET LINK AFTER MIGRATION) durch Schritt 9 aus.
4. Geben Sie unter **"Name** " auf der Seite **"Neue Übersetzungsregel** " oder " **Übersetzungsregel bearbeiten** " einen Namen ein, der das zu übersetzende Nummernmuster beschreibt.
5. (Optional) Geben Sie unter **"Beschreibung**" eine Beschreibung der Übersetzungsregel ein, z. B. **US International-Ferngespräche**.
6. Geben Sie im Abschnitt " **Übersetzungsregel** erstellen" des Dialogfelds Werte in die folgenden Felder ein:
    - **Anfangsziffern**: (Optional) Geben Sie die führenden Ziffern von Zahlen an, mit denen das Muster übereinstimmen soll. Geben Sie z. B. in diesem Feld +ein, um Zahlen im E.164-Format zuzuordnen (die mit +beginnen).
    - **Länge**: Geben Sie die Anzahl der Ziffern im Vergleichsmuster an, und wählen Sie aus, ob das Muster Zahlen mit dieser Länge genau, mindestens dieser Länge oder einer beliebigen Länge entsprechen soll. Geben Sie beispielsweise **"11"** ein, und wählen Sie **"Mindestens** " in der Dropdownliste aus, um Nummern mit einer Länge von mindestens 11 Ziffern zuzuordnen.
    - **Zu entfernende Ziffern**: (Optional) Geben Sie die Anzahl der zu entfernenden Anfangsziffern an. For example, enter **1** to strip out the + from the beginning of the number.
    - **Hinzuzufügende Ziffern**: (Optional) Geben Sie Ziffern an, die den übersetzten Nummern vorangestellt werden sollen. Geben Sie z. B. **011** ein, wenn 011 den übersetzten Zahlen vorangestellt werden soll, wenn die Regel angewendet wird.
    
    The values you enter in these fields are reflected in the **Pattern to match** and **Translation** rule fields. For example, if you specify the preceding example values, the resulting regular expression in the **Pattern to matc** h field is:
    
    **^\+(\d{9}\d+)$** 

    Das **Feld "Übersetzungsregel** " gibt ein Muster für das Format übersetzter Zahlen an. Dieses Muster hat zwei Teile:
    - Ein Wert (z **. B. $1**), der die Anzahl der Ziffern im Vergleichsmuster darstellt
    - (Optional) Ein Wert, dem Sie voranstellen können, indem Sie ihn in die **Ziffern eingeben, um** ein Feld hinzuzufügen.

    Unter Verwendung der vorstehenden Beispielwerte wird **011 $1** im **Feld "Übersetzungsregel** " angezeigt.
    
    Wenn diese Übersetzungsregel angewendet wird, wird +441235551010 011441235551010.
7. Klicken Sie auf **OK**, um die Übersetzungsregel zu speichern.
8. Klicken Sie auf **OK**, um die Trunkkonfiguration zu speichern.
9. Klicken Sie auf der **Seite "Trunk-Konfiguration"** auf **"Commit ausführen**", und klicken Sie dann auf **"Commit ausführen"**. 

> [!Note]
> Jedes Mal, wenn Sie eine Übersetzungsregel erstellen oder ändern, müssen Sie den Befehl **Commit für alle Elemente ausführen** ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter [Veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration](/previous-versions/office/lync-server-2013/lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration). 

### <a name="create-or-modify-a-translation-rule-manually"></a>Manuelles Erstellen oder Ändern einer Übersetzungsregel

Führen Sie diese Schritte aus, um eine Übersetzungsregel zu definieren, indem Sie einen regulären Ausdruck für das Vergleichsmuster und die Übersetzungsregel schreiben. 

**So definieren Sie eine Übersetzungsregel manuell**

1. Melden Sie sich am Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter ["Stellvertretungs-Setupberechtigungen"](/previous-versions/office/lync-server-2013/lync-server-2013-delegate-setup-permissions).
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten der Skype for Business Systemsteuerung verwenden können, finden Sie unter [Installieren und Öffnen von Verwaltungstools](../../management-tools/install-and-open-administrative-tools.md).
3. Um mit dem Definieren einer Übersetzungsregel zu beginnen, führen Sie die Schritte unter [Konfigurieren eines Trunks mit Medienumgehung](GET LINK AFTER MIGRATION) durch Schritt 10 oder [Konfigurieren eines Trunks ohne Medienumgehung](GET LINK AFTER MIGRATION) durch Schritt 9 aus.
4. Geben Sie im Feld **Name** auf der Seite **Neue Übersetzungsregel** oder **Übersetzungsregel bearbeiten** einen Namen ein, der das zu übersetzende Nummernmuster beschreibt.
5. (Optional) Geben Sie in **Beschreibung** eine Beschreibung der Übersetzungsregel ein. z. B. **US International-Ferngespräche**.
6. Klicken Sie im unteren Bereich des Abschnitts **Übersetzungsregel erstellen** auf **Bearbeiten**.
7. Geben Sie Folgendes unter "Typ eines **regulären Ausdrucks"** ein:
    - Geben Sie unter **Übereinstimmung mit dem folgenden Muster** das Muster an, das für den Abgleich der zu übersetzenden Nummern verwendet werden soll.
    - Geben Sie unter **Übersetzungsregel** ein Muster für das Format der übersetzten Nummern an.

    Wenn Sie beispielsweise **(\d\d{9}\d+)$ in Übereinstimmung mit diesem Muster und 011 $1 in der Übersetzungsregel eingeben^\+**, übersetzt die Regel +441235551010 in 011441235551010.  
8. Klicken Sie auf **OK**, um die Übersetzungsregel zu speichern.
9. Klicken Sie auf **OK**, um die Trunkkonfiguration zu speichern.
10. Klicken Sie auf der Seite **Trunkkonfiguration** auf **Commit**, und klicken Sie anschließend auf **Commit für alle**. 

> [!Note] 
> Jedes Mal, wenn Sie eine Übersetzungsregel erstellen oder ändern, müssen Sie den Befehl **Commit für alle Elemente ausführen** ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter [Veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration](/previous-versions/office/lync-server-2013/lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration).