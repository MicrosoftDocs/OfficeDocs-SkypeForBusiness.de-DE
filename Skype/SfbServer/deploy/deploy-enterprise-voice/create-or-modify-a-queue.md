---
title: Erstellen oder Ändern einer Warteschlange in Skype for Business
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
ms.assetid: b9d6366a-839f-4651-a01d-9254546cadeb
description: Erstellen oder ändern Sie eine Reaktiongruppenwarteschlange in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: 9ab714b974601599f591880886a2cf64e35262ba
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808675"
---
# <a name="create-or-modify-a-queue-in-skype-for-business"></a>Erstellen oder Ändern einer Warteschlange in Skype for Business
 
Erstellen oder ändern Sie eine Reaktiongruppenwarteschlange in Skype for Business Server Enterprise-VoIP.
  
Warteschleifen halten Anrufer, bis ein Agent den Anruf beantwortet. Wenn die Reaktionsgruppenanwendung nach einem verfügbaren Agent sucht, durchsucht sie Agentgruppen in der Reihenfolge, in der Sie sie auflisten. Sie können die Agentgruppen auswählen, die der Warteschleife zugewiesen sind, und das Warteschleifenverhalten angeben, z. B. die Anzahl der Anrufe begrenzen, die die Warteschleife halten kann, und den Zeitraum, in dem ein Anruf wartet, bis ein Agent den Anruf beantwortet.
  
Verwenden Sie eines der folgenden Verfahren, um eine Warteschleife zu erstellen oder zu ändern.
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-queue"></a>So verwenden Sie die Skype for Business Server-Systemsteuerung zum Erstellen oder Ändern einer Warteschlange

1. Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppe unterstützen.
    
    > [!NOTE]
    > Wenn Sie einer der delegierten Reaktionsgruppen-Manager für einen verwalteten Workflow sind, können Sie Reaktionsgruppen-Warteschleifen erstellen und ändern und diese den von Ihnen verwalteten Workflows zuweisen. 
  
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen.  
    
3. Klicken Sie in der linken Navigationsleiste auf **Reaktionsgruppen** und dann auf **Warteschleife**.
    
4. Führen Sie auf der Seite **Warteschleife** einen der folgenden Schritte aus:
    
   - Klicken Sie zum Erstellen einer neuen Warteschleife auf **Neu**. Geben Sie in **Dienst auswählen** den Namen des **ApplicationServer**-Diensts, zu dem Sie die Warteschleife hinzufügen möchten, vollständig oder teilweise in das Suchfeld ein. Klicken Sie in der Dienstliste auf den gewünschten Dienst, und klicken Sie dann auf **OK**.
    
   - Geben Sie den Warteschleifennamen vollständig oder teilweise in das Suchfeld ein, um eine vorhandene Warteschleife zu ändern. Klicken Sie in der Warteschleifenliste auf die gewünschte Warteschleife, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.
    
5. Geben Sie bei **Name** einen Namen ein, mit dem die Warteschleife bestimmt wird.
    
6. Geben Sie in **Beschreibung** eine Beschreibung für die Warteschleife ein.
    
7. Geben Sie in **Gruppen** die Gruppen an, die Sie der Warteschleife zuweisen möchten. Führen Sie einen der folgenden Schritte aus: 
    
   - Klicken Sie auf **Auswählen**, um eine Gruppe zu der Warteschleife hinzuzufügen. Geben Sie im Suchfeld **Gruppen auswählen** den Namen der Agentgruppe, die Sie der Warteschleife zuweisen möchten, teilweise oder vollständig ein, klicken Sie auf die gewünschte Agentgruppe, und klicken Sie dann auf **OK**.
    
   - Um eine Gruppe aus der Warteschleife zu entfernen, klicken Sie in der Liste der Agentgruppen auf die Gruppe, die Sie entfernen möchten, und klicken Sie dann auf **Entfernen**.
    
   - Um die Reihenfolge zu ändern, in der Agents durchsucht werden, klicken Sie in der Liste der Agentgruppen auf eine Gruppe und klicken Sie dann auf den Pfeil nach oben oder nach unten.
    
     > [!NOTE]
     > Bei der Suche des Servers nach einem verfügbaren Agent werden Gruppen in der vorhandenen Reihenfolge durchlaufen. Die erste Gruppe in der Liste wird also zuerst durchsucht, dann die zweite Gruppe in der Liste usw. 
  
8. Wenn Sie eine Höchstdauer für die Wartezeit eines Anrufers festlegen möchten, bevor ein Agent den Anruf entgegennimmt, aktivieren Sie das Kontrollkästchen **Timeout für Warteschleife aktivieren**, und führen Sie eine der folgenden Aktionen aus:
    
    a. Geben Sie in **Timeout (Sekunden)** die maximale Anzahl von Sekunden an, die ein Anrufer auf die Entgegennahme des Anrufs durch einen Agent wartet.
    
    b. Wählen Sie in **Anrufaktion** die Aktion aus, die bei einem Timeout für einen Anruf durchgeführt wird:
    
   - Klicken Sie auf **Trennen**, um die Verbindung nach Ablauf der angegebenen Zeitdauer zu trennen.
    
   - Klicken Sie zum Weiterleiten des Anrufs an Voicemail auf "An Voicemail weiterleiten", und geben Sie dann im Feld **"SIP-Adresse"** eine Voicemailadresse im Format "sip:" ein (z. B. *\<username\>* @  *\<domainname\>* sip:bob@contoso.com).
    
   - Wenn Sie den Anruf an eine andere Telefonnummer weiterleiten möchten, klicken Sie auf "An Telefonnummer weiterleiten", und geben Sie dann im Feld **"SIP-Adresse"** die Telefonnummer im Format "sip:" ein (z. B. *\<number\>* @  *\<domainname\>* sip:+14255550121@contoso.com).
    
   - Zum Weiterleiten des Anrufs an einen anderen Benutzer klicken Sie auf "An SIP-Adresse weiterleiten", und geben Sie dann im Feld **"SIP-Adresse"** den URI für den Benutzer im Format "sip: " _\<username\>_ @  _\<domainname\>_ ein.
    
   - Klicken Sie auf **An andere Warteschleife weiterleiten**, und suchen Sie dann die gewünschte Warteschleife, um den Anruf an eine andere Warteschleife weiterzuleiten.
    
9. Um eine maximale Anzahl der Anrufe anzugeben, die in der Warteschleife enthalten sein können, aktivieren Sie das Kontrollkästchen **Warteschleifenüberlauf aktivieren**, und führen Sie dann die folgenden Schritte aus:
    
    a. Wählen Sie im Feld **Maximale Anzahl von Anrufen** die maximale Anzahl von Anrufen aus, die die Warteschleife enthalten soll. 
    
    b. Wählen Sie in **Anruf weiterleiten** aus, welcher Anruf weitergeleitet werden soll, wenn die Warteschleife voll ist: **Neuester Anruf** oder **Ältester Anruf**.
    
    c. Wählen Sie in **Anrufaktion** die Aktion aus, die bei Erreichen des Schwellenwerts für den Überlauf durchgeführt wird:
    
   - Klicken Sie auf **Trennen**, um die Verbindung nach Ablauf der angegebenen Zeitdauer zu trennen.
    
   - Klicken Sie zum Weiterleiten des Anrufs an Voicemail auf "An Voicemail weiterleiten", und geben Sie dann im Feld **"SIP-Adresse"** eine Voicemailadresse im Format "sip:" ein (z. B. *\<username\>* @  *\<domainname\>* sip:bob@contoso.com).
    
   - Wenn Sie den Anruf an eine andere Telefonnummer weiterleiten möchten, klicken Sie auf "An Telefonnummer weiterleiten", und geben Sie dann im Feld **"SIP-Adresse"** die Telefonnummer im Format "sip:" ein (z. B. *\<number\>* @  *\<domainname\>* sip:+14255550121@contoso.com).
    
   - Zum Weiterleiten des Anrufs an einen anderen Benutzer klicken Sie auf "An SIP-Adresse weiterleiten", und geben Sie dann im Feld **"SIP-Adresse"** den URI für den Benutzer im Format "sip: " _\<username\>_ @  _\<domainname\>_ ein.
    
   - Klicken Sie auf **An andere Warteschleife weiterleiten**, und suchen Sie dann die gewünschte Warteschleife, um den Anruf an eine andere Warteschleife weiterzuleiten.
    
10. Klicken Sie auf **Commit**.
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-queue"></a>So verwenden Sie die Skype for Business Server-Verwaltungsshell zum Erstellen oder Ändern einer Warteschlange

1. Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppe unterstützen.
    
    > [!NOTE]
    > Wenn Sie einer der delegierten Reaktionsgruppen-Manager für einen verwalteten Workflow sind, können Sie Agentgruppen und Warteschleifen erstellen und Warteschleifen Agentgruppen zuweisen. 
  
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **"Start",**"Alle **Programme",** **"Skype for Business 2015"** und dann auf **"Skype for Business Server-Verwaltungsshell".**
    
3. Erstellen Sie die Ansage, die abgespielt werden soll, wenn der Schwellenwert für den Warteschleifen-Timeout erreicht wurde, und speichern Sie diesen in einer Variable. Führen Sie an der Eingabeaufforderung Folgendes aus:
    
   ```powershell
   $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   Zum Beispiel:
    
   ```console
   "All agents are currently busy. Please call back later."
   ```

   > [!NOTE]
   > Verwenden Sie das Cmdlet **Import-CsRgsAudioFile**, um eine Audiodatei für die Ansage zu verwenden. Weitere Informationen finden Sie unter [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps). 
  
4. Legen Sie die auszuführende Aktion fest, wenn der Schwellenwert für den Warteschleifen-Timeout erreicht wurde, und speichern Sie diesen in einer Variable. Führen Sie an der Eingabeaufforderung Folgendes aus:
    
   ```powershell
   $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

   > [!NOTE]
   > Weitere Informationen zu möglichen Aktionen und deren Syntax finden Sie unter [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps). 
  
    Zum Beispiel:
    
   ```powershell
   $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate
   ```

5. Erstellen Sie die Ansage, die abgespielt werden soll, wenn der Schwellenwert für den Warteschleifen-Überlauf erreicht wurde, und speichern Sie diesen in einer Variable. Führen Sie an der Eingabeaufforderung Folgendes aus:
    
   ```powershell
   $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   Zum Beispiel:
    
   ```powershell
   $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
   ```

      > [!NOTE]
      > Verwenden Sie das Cmdlet **Import-CsRgsAudioFile**, um eine Audiodatei für die Ansage zu verwenden. Weitere Informationen finden Sie unter [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps). 
  
6. Legen Sie die auszuführende Aktion fest, wenn der Schwellenwert für den Warteschleifen-Überlauf erreicht wurde, und speichern Sie diesen in einer Variable. Führen Sie an der Eingabeaufforderung Folgendes aus:
    
   ```powershell
   $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

    > [!NOTE]
    > Weitere Informationen zu möglichen Aktionen und deren Syntax finden Sie unter [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps). 
  
    Zum Beispiel:
    
   ```powershell
   $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate
   ```

7. Dienstnamen für den Reaktionsgruppendienst abrufen und diesen einer Variable zuweisen. Führen Sie an der Eingabeaufforderung Folgendes aus:
    
   ```powershell
   $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;
   ```

8. Identität einer Agentgruppe abrufen, die der Warteschleife zugeordnet werden soll. Führen Sie an der Eingabeaufforderung Folgendes aus:
    
   ```powershell
   $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
   ```

    > [!NOTE]
    > Weitere Informationen zum Erstellen der Agentgruppe finden Sie unter ["New-CsRgsAgentGroup".](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)
  
9. Die Warteschleife erstellen. Führen Sie an der Eingabeaufforderung Folgendes aus:
    
   ```powershell
   $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
   ```

   Zum Beispiel:
    
   ```powershell
   $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;
   ```

10. Bestätigen dass die Warteschleife erstellt wurde. Führen Sie folgenden Befehl aus:
    
    ```powershell
    Get-CsRgsQueue -Name "Help Desk"
    ```

## <a name="see-also"></a>Siehe auch

[New-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/new-csrgsqueue?view=skype-ps)
  
[Set-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/set-csrgsqueue?view=skype-ps)
  
[New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps)
  
[New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)
  
[Get-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/get-csrgsqueue?view=skype-ps)
  
[Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)
  
[Remove-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/remove-csrgsqueue?view=skype-ps)
