---
title: 'Lync Server 2013: Erstellen oder Ändern einer Warteschleife'
TOCTitle: Erstellen oder Ändern einer Warteschleife
ms:assetid: b9d6366a-839f-4651-a01d-9254546cadeb
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205207(v=OCS.15)
ms:contentKeyID: 49295210
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen oder Ändern einer Warteschleife in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Verwenden Sie eines der folgenden Verfahren, um eine Warteschleife zu erstellen oder zu ändern.

## So verwenden Sie Lync Server-Systemsteuerung zum Erstellen oder Ändern einer Warteschleife

1.  Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.
    

    > [!NOTE]
    > Wenn Sie einer der delegierten Reaktionsgruppen-Manager für einen verwalteten Workflow sind, können Sie Reaktionsgruppen-Warteschleifen erstellen und ändern und diese den von Ihnen verwalteten Workflows zuweisen.



2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Reaktionsgruppen** und dann auf **Warteschleife** .

4.  Führen Sie auf der Seite **Warteschleife** einen der folgenden Schritte aus:
    
      - Klicken Sie zum Erstellen einer neuen Warteschleife auf **Neu** . Geben Sie in **Dienst auswählen** den Namen des **ApplicationServer** -Diensts, zu dem Sie die Warteschleife hinzufügen möchten, vollständig oder teilweise in das Suchfeld ein. Klicken Sie in der Dienstliste auf den gewünschten Dienst, und klicken Sie dann auf **OK** .
    
      - Geben Sie den Warteschleifennamen vollständig oder teilweise in das Suchfeld ein, um eine vorhandene Warteschleife zu ändern. Klicken Sie in der Warteschleifenliste auf die gewünschte Warteschleife, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen** .

5.  Geben Sie bei **Name** einen Namen ein, mit dem die Warteschleife bestimmt wird.

6.  Geben Sie in **Beschreibung** eine Beschreibung für die Warteschleife ein.

7.  Geben Sie in **Gruppen** die Gruppen an, die Sie der Warteschleife zuweisen möchten. Führen Sie einen der folgenden Schritte aus:
    
      - Klicken Sie auf **Auswählen** , um eine Gruppe zu der Warteschleife hinzuzufügen. Geben Sie im Suchfeld **Gruppen auswählen** den Namen der Agentgruppe, die Sie der Warteschleife zuweisen möchten, teilweise oder vollständig ein, klicken Sie auf die gewünschte Agentgruppe, und klicken Sie dann auf **OK** .
    
      - Um eine Gruppe aus der Warteschleife zu entfernen, klicken Sie in der Liste der Agentgruppen auf die Gruppe, die Sie entfernen möchten, und klicken Sie dann auf **Entfernen** .
    
      - Um die Reihenfolge zu ändern, in der Agents durchsucht werden, klicken Sie in der Liste der Agentgruppen auf eine Gruppe und klicken Sie dann auf den Pfeil nach oben oder nach unten.
        

        > [!NOTE]
        > Bei der Suche des Servers nach einem verfügbaren Agent werden Gruppen in der vorhandenen Reihenfolge durchlaufen. Die erste Gruppe in der Liste wird also zuerst durchsucht, dann die zweite Gruppe in der Liste usw.



8.  Wenn Sie eine Höchstdauer für die Wartezeit eines Anrufers festlegen möchten, bevor ein Agent den Anruf entgegennimmt, aktivieren Sie das Kontrollkästchen **Timeout für Warteschleife aktivieren** , und führen Sie eine der folgenden Aktionen aus:
    
    1.  Geben Sie in **Timeout (Sekunden)** die maximale Anzahl von Sekunden an, die ein Anrufer auf die Entgegennahme des Anrufs durch einen Agent wartet.
    
    2.  Wählen Sie in **Anrufaktion** die Aktion aus, die bei einem Timeout für einen Anruf durchgeführt wird:
    
    <!-- end list -->
    
      - Klicken Sie auf **Trennen** , um die Verbindung nach Ablauf der angegebenen Zeitdauer zu trennen.
    
      - Klicken Sie auf **An Voicemail weiterleiten** , und geben Sie anschließend im Feld **SIP-Adresse** eine Voicemailadresse im Format "sip: *\<Benutzername\>* @ *\<Domänenname\>* " ein, um den Anruf an eine Voicemail weiterzuleiten (Beispiel: "sip:bob@contoso.com").
    
      - Klicken Sie auf **An Telefonnummer weiterleiten** , und geben Sie anschließend im Feld **SIP-Adresse** die Telefonnummer im Format "sip: *\<Nummer\>* @ *\<Domänenname\>* " ein, um den Anruf an eine Telefonnummer weiterzuleiten (Beispiel: "sip:+14255550121@contoso.com").
    
      - Klicken Sie auf **An SIP-Adresse weiterleiten** , und geben Sie im Feld **SIP-Adresse** den URI für den Benutzer im Format "sip: *\<Benutzername\>* @ *\<Domänenname\>* " ein, um den Anruf an einen anderen Benutzer weiterzuleiten.
    
      - Klicken Sie auf **An andere Warteschleife weiterleiten** , und suchen Sie dann die gewünschte Warteschleife, um den Anruf an eine andere Warteschleife weiterzuleiten.

9.  Um eine maximale Anzahl der Anrufe anzugeben, die in der Warteschleife enthalten sein können, aktivieren Sie das Kontrollkästchen **Warteschleifenüberlauf aktivieren** , und führen Sie dann die folgenden Schritte aus:
    
    1.  Wählen Sie im Feld **Maximale Anzahl von Anrufen** die maximale Anzahl von Anrufen aus, die die Warteschleife enthalten soll.
    
    2.  Wählen Sie in **Anruf weiterleiten** aus, welcher Anruf weitergeleitet werden soll, wenn die Warteschleife voll ist: **Neuester Anruf** oder **Ältester Anruf** .
    
    3.  Wählen Sie in **Anrufaktion** die Aktion aus, die bei Erreichen des Schwellenwerts für den Überlauf durchgeführt wird:
    
    <!-- end list -->
    
      - Klicken Sie auf **Trennen** , um die Verbindung nach Ablauf der angegebenen Zeitdauer zu trennen.
    
      - Klicken Sie auf **An Voicemail weiterleiten** , und geben Sie anschließend im Feld **SIP-Adresse** eine Voicemailadresse im Format "sip: *\<Benutzername\>* @ *\<Domänenname\>* " ein, um den Anruf an eine Voicemail weiterzuleiten (Beispiel: "sip:bob@contoso.com").
    
      - Klicken Sie auf **An Telefonnummer weiterleiten** , und geben Sie anschließend im Feld **SIP-Adresse** die Telefonnummer im Format "sip: *\<Nummer\>* @ *\<Domänenname\>* " ein, um den Anruf an eine Telefonnummer weiterzuleiten (Beispiel: "sip:+14255550121@contoso.com").
    
      - Klicken Sie auf **An SIP-Adresse weiterleiten** , und geben Sie im Feld **SIP-Adresse** den URI für den Benutzer im Format "sip: *\<Benutzername\>* @ *\<Domänenname\>* " ein, um den Anruf an einen anderen Benutzer weiterzuleiten.
    
      - Klicken Sie auf **An andere Warteschleife weiterleiten** , und suchen Sie dann die gewünschte Warteschleife, um den Anruf an eine andere Warteschleife weiterzuleiten.

10. Klicken Sie auf **Commit** .

## So verwenden Sie Windows PowerShell zum Erstellen oder Ändern einer Warteschleife

1.  Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.
    

    > [!NOTE]
    > Wenn Sie einer der delegierten Reaktionsgruppen-Manager für einen verwalteten Workflow sind, können Sie Agentgruppen und Warteschleifen erstellen und Warteschleifen Agentgruppen zuweisen.



2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Erstellen Sie die Ansage, die abgespielt werden soll, wenn der Schwellenwert für den Warteschleifen-Timeout erreicht wurde, und speichern Sie diesen in einer Variable. Führen Sie an der Eingabeaufforderung Folgendes aus:
    
        $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    Beispiel:
    
        "All agents are currently busy. Please call back later."
    

    > [!NOTE]
    > Verwenden Sie das <STRONG>Import-CsRgsAudioFile</STRONG>-Cmdlet, um eine Audiodatei als Ansage zu verwenden. Ausführliche Informationen finden Sie unter <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.



4.  Legen Sie die auszuführende Aktion fest, wenn der Schwellenwert für den Warteschleifen-Timeout erreicht wurde, und speichern Sie diesen in einer Variable. Führen Sie an der Eingabeaufforderung Folgendes aus:
    
        $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
    

    > [!NOTE]
    > Ausführliche Informationen zu möglichen Aktionen und deren Syntax finden Sie unter <A href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>.

    
    Beispiel:
    
        $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate

5.  Erstellen Sie die Ansage, die abgespielt werden soll, wenn der Schwellenwert für den Warteschleifen-Überlauf erreicht wurde, und speichern Sie diesen in einer Variable. Führen Sie an der Eingabeaufforderung Folgendes aus:
    
        $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    Beispiel:
    
        $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
    

    > [!NOTE]
    > Verwenden Sie das <STRONG>Import-CsRgsAudioFile</STRONG>-Cmdlet, um eine Audiodatei als Ansage zu verwenden. Ausführliche Informationen finden Sie unter <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.



6.  Legen Sie die auszuführende Aktion fest, wenn der Schwellenwert für den Warteschleifen-Überlauf erreicht wurde, und speichern Sie diesen in einer Variable. Führen Sie an der Eingabeaufforderung Folgendes aus:
    
        $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
    

    > [!NOTE]
    > Ausführliche Informationen zu möglichen Aktionen und deren Syntax finden Sie unter <A href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>.

    
    Beispiel:
    
        $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate

7.  Rufen Sie den Dienstnamen für den Reaktionsgruppendienst ab, und weisen Sie ihn einer Variablen zu. Führen Sie an der Eingabeaufforderung folgenden Befehl aus:
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;

8.  Identität einer Agentgruppe abrufen, die der Warteschleife zugeordnet werden soll. Führen Sie an der Eingabeaufforderung Folgendes aus:
    
        $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
    

    > [!NOTE]
    > Ausführliche Hinweise zum Erstellen der Agentgruppe finden Sie unter <A href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsAgentGroup">New-CsRgsAgentGroup</A>



9.  Die Warteschleife erstellen. Führen Sie an der Eingabeaufforderung Folgendes aus:
    
        $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
    
    Beispiel:
    
        $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;

10. Bestätigen dass die Warteschleife erstellt wurde. Führen Sie folgenden Befehl aus:
    
        Get-CsRgsQueue -Name "Help Desk"

## Siehe auch

#### Weitere Ressourcen

[New-CsRgsQueue](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsQueue)  
[Set-CsRgsQueue](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsRgsQueue)  
[New-CsRgsPrompt](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsPrompt)  
[New-CsRgsCallAction](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsCallAction)  
[Get-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsQueue)  
[Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile)  
[Remove-CsRgsQueue](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsRgsQueue)

