---
title: Erstellen oder Ändern einer Warteschleife in Skype für Unternehmen
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b9d6366a-839f-4651-a01d-9254546cadeb
description: Erstellen Sie oder ändern Sie einer Warteschleife für Reaktionsgruppen in Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: 10396e7d9e672999e72a8fe83c7bdffbd80b7f4b
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20991404"
---
# <a name="create-or-modify-a-queue-in-skype-for-business"></a>Erstellen oder Ändern einer Warteschleife in Skype für Unternehmen
 
Erstellen Sie oder ändern Sie einer Warteschleife für Reaktionsgruppen in Skype für Business Server Enterprise-VoIP.
  
Anrufer verbleiben in Warteschlangen, bis ein Agent den Anruf annimmt. Wenn die Anwendung "Reaktionsgruppe" nach einem verfügbaren Agent sucht, sucht es Agentengruppen in der Reihenfolge, dass Sie diese auflisten. Sie können die agentgruppen auswählen, die an die Warteschlange zugewiesen sind, und geben Sie Warteschlange Verhalten, beispielsweise Beschränken der Anzahl der Anrufe, die die Warteschleife aufnehmen kann und die Zeitspanne, ein Anruf, bis ein Agent den Anruf annimmt den Anruf wartet.
  
Verwenden Sie eines der folgenden Verfahren, um eine Warteschleife zu erstellen oder zu ändern.
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-queue"></a>Verwenden Sie zum Erstellen oder Ändern einer Warteschleife Skype Business Server-Systemsteuerung

1. Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.
    
    > [!NOTE]
    > Wenn Sie einer der delegierten Reaktionsgruppen-Manager für einen verwalteten Workflow sind, können Sie Reaktionsgruppen-Warteschleifen erstellen und ändern und diese den von Ihnen verwalteten Workflows zuweisen. 
  
2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.  
    
3. Klicken Sie in der linken Navigationsleiste auf **Reaktionsgruppen** und dann auf **Warteschleife**.
    
4. Führen Sie auf der Seite **Warteschleife** einen der folgenden Schritte aus:
    
   - Klicken Sie zum Erstellen einer neuen Warteschleife auf **Neu**. Fügen in **Wählen Sie einen Dienst**Typ Teil oder den vollständigen Namen des **ApplicationServer** -Diensts, in dem Sie möchten, die Warteschlange in das Suchfeld ein. Klicken Sie in der Dienstliste auf den gewünschten Dienst und klicken Sie dann auf **OK**.
    
   - Geben Sie den Warteschleifennamen vollständig oder teilweise in das Suchfeld ein, um eine vorhandene Warteschleife zu ändern. Klicken Sie in der Warteschleifenliste auf die gewünschte Warteschleife, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.
    
5. Geben Sie bei **Name** einen Namen ein, mit dem die Warteschleife bestimmt wird.
    
6. Geben Sie in **Beschreibung** eine Beschreibung für die Warteschleife ein.
    
7. Geben Sie in **Gruppen** die Gruppen an, die Sie der Warteschleife zuweisen möchten. Führen Sie einen der folgenden Schritte aus: 
    
   - Klicken Sie auf **Auswählen**, um eine Gruppe zu der Warteschleife hinzuzufügen. Geben Sie im Suchfeld **Gruppen auswählen** den Namen der Agentgruppe, die Sie der Warteschleife zuweisen möchten, teilweise oder vollständig ein, klicken Sie auf die gewünschte Agentgruppe und klicken Sie dann auf **OK**.
    
   - Um eine Gruppe aus der Warteschleife zu entfernen, klicken Sie in der Liste der Agentgruppen auf die Gruppe, die Sie entfernen möchten und klicken Sie dann auf **Entfernen**.
    
   - Um die Reihenfolge zu ändern, in der Agents durchsucht werden, klicken Sie in der Liste der Agentgruppen auf eine Gruppe und klicken Sie dann auf den Pfeil nach oben oder nach unten.
    
    > [!NOTE]
    > Bei der Suche des Servers nach einem verfügbaren Agent werden Gruppen in der vorhandenen Reihenfolge durchlaufen. Die erste Gruppe in der Liste wird also zuerst durchsucht, dann die zweite Gruppe in der Liste usw. 
  
8. Wenn Sie eine Höchstdauer für die Wartezeit eines Anrufers festlegen möchten, bevor ein Agent den Anruf entgegennimmt, aktivieren Sie das Kontrollkästchen **Timeout für Warteschleife aktivieren** und führen Sie eine der folgenden Aktionen aus:
    
    a. Geben Sie in **Timeout (Sekunden)** die maximale Anzahl von Sekunden an, die ein Anrufer auf die Entgegennahme des Anrufs durch einen Agent wartet.
    
    b. Wählen Sie in **Anrufaktion** die Aktion aus, die bei einem Timeout für einen Anruf durchgeführt wird:
    
     - Klicken Sie auf **Trennen**, um die Verbindung nach Ablauf der angegebenen Zeitdauer zu trennen.
    
     - So leiten Sie den Anruf an Voicemail, klicken Sie auf **an Voicemail weiterleiten**, und geben Sie im Feld **SIP-Adresse** eine Voicemail-Adresse im Format Sip weiter: _ \<Username\>_@ _\<Domainname\> _ (für Beispiel, sip:bob@contoso.com).
    
     - Um den Anruf an eine andere Telefonnummer weiterzuleiten, klicken Sie auf **an Telefonnummer weiterleiten**, und geben Sie im Feld **SIP-Adresse** die Telefonnummer im Format Sip: _ \<Anzahl\>_@ _\<Domainname\>_ (beispielsweise sip:+14255550121@contoso.com).
    
     - Um den Anruf an einen anderen Benutzer weiterzuleiten, klicken Sie auf **an SIP-Adresse weiterleiten**, und geben Sie im Feld **SIP-Adresse** den URI für den Benutzer im Format Sip: _ \<Username\>_@ _\<Domainname\>_.
    
     - Klicken Sie auf **An andere Warteschleife weiterleiten** und suchen Sie dann die gewünschte Warteschleife, um den Anruf an eine andere Warteschleife weiterzuleiten.
    
9. Um eine maximale Anzahl der Anrufe anzugeben, die in der Warteschleife enthalten sein können, aktivieren Sie das Kontrollkästchen **Warteschleifenüberlauf aktivieren** und führen Sie dann die folgenden Schritte aus:
    
    a. Wählen Sie im Feld **Maximale Anzahl von Anrufen** die maximale Anzahl von Anrufen aus, die die Warteschleife enthalten soll. 
    
    b. Wählen Sie in **Anruf weiterleiten** aus, welcher Anruf weitergeleitet werden soll, wenn die Warteschleife voll ist: **Neuester Anruf** oder **Ältester Anruf**.
    
    c. Wählen Sie in **Anrufaktion** die Aktion aus, die bei Erreichen des Schwellenwerts für den Überlauf durchgeführt wird:
    
     - Klicken Sie auf **Trennen**, um die Verbindung nach Ablauf der angegebenen Zeitdauer zu trennen.
    
     - So leiten Sie den Anruf an Voicemail, klicken Sie auf **an Voicemail weiterleiten**, und geben Sie im Feld **SIP-Adresse** eine Voicemail-Adresse im Format Sip weiter: _ \<Username\>_@ _\<Domainname\> _ (für Beispiel, sip:bob@contoso.com).
    
     - Um den Anruf an eine andere Telefonnummer weiterzuleiten, klicken Sie auf **an Telefonnummer weiterleiten**, und geben Sie im Feld **SIP-Adresse** die Telefonnummer im Format Sip: _ \<Anzahl\>_@ _\<Domainname\>_ (beispielsweise sip:+14255550121@contoso.com).
    
     - Um den Anruf an einen anderen Benutzer weiterzuleiten, klicken Sie auf **an SIP-Adresse weiterleiten**, und geben Sie im Feld **SIP-Adresse** den URI für den Benutzer im Format Sip: _ \<Username\>_@ _\<Domainname\>_.
    
     - Klicken Sie auf **An andere Warteschleife weiterleiten** und suchen Sie dann die gewünschte Warteschleife, um den Anruf an eine andere Warteschleife weiterzuleiten.
    
10. Klicken Sie auf **Commit ausführen**.
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-queue"></a>Verwenden Sie zum Erstellen oder Ändern einer Warteschleife Skype für Business Server-Verwaltungsshell

1. Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.
    
    > [!NOTE]
    > Wenn Sie einer der delegierten Reaktionsgruppen-Manager für einen verwalteten Workflow sind, können Sie Agentgruppen und Warteschleifen erstellen und Warteschleifen Agentgruppen zuweisen. 
  
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
3. Erstellen Sie die Ansage, die abgespielt werden soll, wenn der Schwellenwert für den Warteschleifen-Timeout erreicht wurde und speichern Sie diesen in einer Variable. Führen Sie an der Eingabeaufforderung Folgendes aus:
    
   ```
   $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   Beispiel:
    
   ```
   "All agents are currently busy. Please call back later."
   ```

   > [!NOTE]
   > Um eine Audiodatei für die Aufforderung zur verwenden möchten, verwenden Sie das Cmdlet **Import-CsRgsAudioFile** . Weitere Informationen hierzu finden Sie unter [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps). 
  
4. Legen Sie die auszuführende Aktion fest, wenn der Schwellenwert für den Warteschleifen-Timeout erreicht wurde und speichern Sie diesen in einer Variable. Führen Sie an der Eingabeaufforderung Folgendes aus:
    
   ```
   $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

   > [!NOTE]
   > Ausführliche Informationen zu möglichen Aktionen und deren Syntax finden Sie unter [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps). 
  
    Beispiel:
    
   ```
   $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate
   ```

5. Erstellen Sie die Ansage, die abgespielt werden soll, wenn der Schwellenwert für den Warteschleifen-Überlauf erreicht wurde und speichern Sie diesen in einer Variable. Führen Sie an der Eingabeaufforderung Folgendes aus:
    
  ```
  $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
  ```

   Beispiel:
    
  ```
  $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
  ```

      > [!NOTE]
      > Um eine Audiodatei für die Aufforderung zur verwenden möchten, verwenden Sie das Cmdlet **Import-CsRgsAudioFile** . Weitere Informationen hierzu finden Sie unter [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps). 
  
6. Legen Sie die auszuführende Aktion fest, wenn der Schwellenwert für den Warteschleifen-Überlauf erreicht wurde und speichern Sie diesen in einer Variable. Führen Sie an der Eingabeaufforderung Folgendes aus:
    
  ```
  $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
  ```

    > [!NOTE]
    > Ausführliche Informationen zu möglichen Aktionen und deren Syntax finden Sie unter [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps). 
  
    Beispiel:
    
   ```
   $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate
   ```

7. Rufen Sie den Dienstnamen für den Reaktionsgruppendienst ab und weisen Sie ihn einer Variablen zu. Führen Sie an der Eingabeaufforderung folgenden Befehl aus:
    
   ```
   $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;
   ```

8. Identität einer Agentgruppe abrufen, die der Warteschleife zugeordnet werden soll. Führen Sie an der Eingabeaufforderung Folgendes aus:
    
   ```
   $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
   ```

    > [!NOTE]
    > Ausführliche Informationen zum Erstellen der agentgruppe finden Sie unter [New-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)
  
9. Die Warteschleife erstellen. Führen Sie an der Eingabeaufforderung Folgendes aus:
    
   ```
   $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
   ```

   Beispiel:
    
   ```
   $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;
   ```

10. Bestätigen Sie, dass die Warteschleife erstellt wurde. Führen Sie folgenden Befehl aus:
    
   ```
   Get-CsRgsQueue -Name "Help Desk"
   ```

## <a name="see-also"></a>Siehe auch

[Mit New-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/new-csrgsqueue?view=skype-ps)
  
[Set-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/set-csrgsqueue?view=skype-ps)
  
[Neue CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps)
  
[Mit New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)
  
[Get-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/get-csrgsqueue?view=skype-ps)
  
[Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)
  
[Remove-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/remove-csrgsqueue?view=skype-ps)