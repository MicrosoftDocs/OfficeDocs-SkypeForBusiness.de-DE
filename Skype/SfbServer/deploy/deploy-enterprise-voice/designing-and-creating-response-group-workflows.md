---
title: Entwerfen und Erstellen von Antwort Gruppe Workflows in Skype für Unternehmen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: dcb9effb-5d12-4dee-80fc-ab9654222d5a
description: Entwerfen und Erstellen von Workflows für Reaktionsgruppen in Skype für Business Server Enterprise-VoIP. Es werden sowohl Workflows für Sammelanschlüsse als auch interaktive Workflows abgedeckt.
ms.openlocfilehash: 9ae4a229c0b7ece3e9dbb858bc0491fea123e479
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892571"
---
# <a name="designing-and-creating-response-group-workflows-in-skype-for-business"></a>Entwerfen und Erstellen von Antwort Gruppe Workflows in Skype für Unternehmen

Entwerfen und Erstellen von Workflows für Reaktionsgruppen in Skype für Business Server Enterprise-VoIP. Es werden sowohl Workflows für Sammelanschlüsse als auch interaktive Workflows abgedeckt.

Ein Workflow definiert, wie mit einem Anruf ab dem Läuten des Telefons bis zur Annahme des Anrufs verfahren wird. Der Workflow gibt die Warteschleife zum Halten des Anrufs an und legt die Routingmethode für die Workflows für Sammelanschlüsse oder die Fragen und Antworten für die Workflows für interaktive-Reaktionsgruppen fest.

Ein Workflow definiert außerdem Einstellungen wie die Willkommensnachricht, Wartemusik, Geschäftszeiten und Feiertage.

> [!NOTE]
> Vor dem Erstellen eines Workflows müssen Sie zuerst Agent-Gruppen und Warteschleifen erstellen, die vom Workflow verwendet werden sollen.

## <a name="creating-or-modifying-a-hunt-group-workflow"></a>Erstellen oder ändern einen Workflow für Sammelanschlüsse

### <a name="to-use-response-group-configuration-tool-to-create-or-modify-a-hunt-group-workflow"></a>Verwenden des Konfigurationstools für Reaktionsgruppen erstellen oder ändern einen Workflow für Sammelanschlüsse

1. Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.

2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.

3. Klicken Sie in der linken Navigationsleiste auf **Reaktionsgruppen** und dann auf **Workflow**.

4. Klicken Sie auf der Seite **Workflow** auf **Workflow erstellen oder bearbeiten**.

5. Geben Sie im Suchfeld **Dienst auswählen** einen Teil oder den vollständigen Namen des **ApplicationServer**-Diensts ein, von dem der Workflow gehostet wird, den Sie erstellen oder ändern möchten. Klicken Sie in der nun angezeigten Liste der Dienst auf den gewünschten Dienst und klicken Sie dann auf **OK**.

    > [!NOTE]
    > Das Konfigurationstool für Reaktionsgruppen wird geöffnet. Sie können auch das Konfigurationstool für Reaktionsgruppen direkt über einen Webbrowser öffnen, indem Sie die folgende URL eingeben: https://\<WebPoolFqdn\>/RgsConfig.

6. Führen Sie einen der folgenden Schritte aus:

   - Klicken Sie unter **neuen Workflow erstellen**neben **Sammelanschluss**auf **Erstellen**.

   - Suchen Sie unter **Vorhandenen Workflow verwalten** nach dem Workflow, den Sie ändern möchten, und klicken Sie anschließend unter **Aktion** auf **Bearbeiten**.

7. Falls Benutzer den Workflow bereits verwenden können, aktivieren Sie das Kontrollkästchen **Workflow aktivieren**.

    > [!NOTE]
    >  Wenn Sie einen verwalteten Workflow erstellen, müssen Sie **den Workflow aktivieren**auswählen. Nachdem Sie den aktiven, verwalteten Workflow gespeichert haben, können Sie ihn ändern und deaktivieren.

8. Aktivieren Sie das Kontrollkästchen **Für Partnerverbund aktivieren**, um Partnerbenutzern Anrufe bei der Gruppe zu ermöglichen. Sie benötigen auch eine externe Zugriffsrichtlinie, die für die Anwendung "Reaktionsgruppe" für den Verbund konfiguriert gilt.

    > [!NOTE]
    > Die globale externe Zugriffsrichtlinie gilt für die Anwendung "Reaktionsgruppe". Sie können die globale Richtlinie für den Verbund Antwort-Gruppe konfigurieren, mithilfe von Skype Business Server-Systemsteuerung oder mit dem **Set-CsExternalAccessPolicy** -Cmdlet den EnableOutsideAccess-Parameter auf True festgelegt. Bedenken Sie, dass globale Richtlinieneinstellungen für alle Benutzer gelten, es sei denn, sie sind einer standort- oder benutzerspezifischen Richtlinie zugeordnet. Stellen Sie daher vor dem Ändern dieser Einstellung für Reaktionsgruppen sicher, dass die Partnerverbundeinstellung die Anforderungen Ihrer Organisation erfüllt. Nähere Informationen dazu, wie sich Richtlinien auf Benutzer auswirken, finden Sie unter [Manage External Access Policy for Your Organization](https://technet.microsoft.com/library/5571811e-34c8-443a-b94c-1ab5d4275581.aspx). Ausführliche Informationen zu den partnerverbundeinstellung finden Sie unter [Set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/set-csexternalaccesspolicy?view=skype-ps).

    > [!NOTE]
    > Benutzer, die in Skype für Business Online gehostet werden können nicht tätigen von Anrufen zu Response Groups, die gehostet werden in einer lokalen Bereitstellung. Dies gilt in beiden hybridbereitstellungen und in Fällen, in dem eine lokale Bereitstellung mit einem Skype für Business Online-Bereitstellung im Verbund befindet.

9. Aktivieren Sie das Kontrollkästchen **Agentanonymität aktivieren**, um bei Anrufen die Identität der Agents zu verbergen.

    > [!NOTE]
    > Anonyme Anrufe können nicht mit Chats oder Video gestartet werden. Agent oder Anrufer können jedoch im Verlauf des Anrufs Chats und Video aktivieren. Ein anonymer Agent kann Anrufe halten, weiterleiten (sowohl blind als auch nach Rücksprache) sowie Anrufe parken und fortsetzen. Anonyme Anrufe bieten keine Unterstützung für Konferenzen, Anwendungs- und Desktopfreigabe, Dateiübertragung, Whiteboardverwendung und Datenzusammenarbeit sowie Anrufaufzeichnung. Agents, die das Lync VDI-Plugin verwenden, können eingehende Anrufe anonym empfangen, jedoch keine ausgehenden anonymen Anrufe tätigen.

10. Geben Sie im Feld **Adresse der Gruppe eingeben, die die Anrufe entgegennimmt** den primären SIP-URI (Uniform Resource Identifier) der Gruppe ein, die die Anrufe beim Workflow erhalten soll.

    > [!NOTE]
    > Über den primären URI für einen Workflow wird der Workflow identifiziert und auf ihn verwiesen. Der SIP-URI, den Sie eingeben, wird als ein Kontaktobjekt in Active Directory Domain Services erstellt. Um den URI zu erstellen, muss das Objekt in Active Directory eindeutig sein.

11. Geben Sie im **Anzeigename**der Name, den Sie für den Workflow (beispielsweise Sales Reaktionsgruppe) anzeigen möchten.

    > [!NOTE]
    > Verwenden Sie im Anzeigenamen nicht die Zeichen „<“ oder „>“. Die folgenden Anzeigenamen sind reserviert und dürfen nicht verwendet werden: **RGS-Anwesenheitsmonitor** oder **Ankündigungsdienst**.

12. Geben Sie unter **Telefonnummer** den Anschluss-URI für die Reaktionsgruppe ein (z. B. +14255550165).

13. Geben Sie im Feld **Anzeigenummer** die Nummer ein, wie sie für die Reaktionsgruppe angezeigt werden soll (z. B. +1 (425) 555-0165).

14. (Optional) Geben Sie im Feld **Beschreibung**eine Beschreibung für den Workflow, wie Sie auf der Visitenkarte in Skype für Unternehmen angezeigt werden soll.

15. Wählen Sie unter **Workflowtyp** die Option **Verwaltet** aus, wenn dieser Workflow von einem Reaktionsgruppenmanager verwaltet wird. Gehen Sie Reaktionsgruppen-Manager, um den Workflow zuzuweisen:

    a. Geben Sie den SIP-URI eines Managers für diesen Workflow ein und klicken Sie auf **Hinzufügen**.

    b. Geben Sie den SIP-URI zusätzlicher Manager für den Workflow ein und klicken Sie auf **Hinzufügen**.

    > [!IMPORTANT]
    > Jedem Benutzer, der als Manager einer Reaktionsgruppe bestimmt wurde, muss die Rolle „CsResponseGroupManager“ zugewiesen sein. Falls Benutzern diese Rolle nicht zugewiesen ist, können sie keine Reaktionsgruppen verwalten.

16. Klicken Sie unter **Schritt 2: Sprache auswählen** auf die Sprache, die für die Spracherkennung und Text-zu-Sprache verwendet werden soll.

17. Aktivieren Sie zum Konfigurieren einer Willkommensnachricht unter **Schritt 3: Willkommensnachricht konfigurieren** das Kontrollkästchen **Willkommensnachricht wiedergeben** und führen Sie eine der folgenden Aktionen aus:

    - Um die Willkommensnachricht als Text einzugeben, die für Anrufer in Sprache umgewandelt wird, klicken Sie auf **Text-zu-Sprache verwenden** und geben Sie die Willkommensnachricht in das Textfeld ein.

    > [!NOTE]
    > Verwenden Sie im eingegebenen Text keine HTML-Tags. Andernfalls wird eine Fehlermeldung angezeigt.

    - Um eine aufgezeichnete WAV- (Wave) oder WMA-Datei (Windows Media Audio) für die Willkommensnachricht zu verwenden, klicken Sie auf **Aufzeichnung auswählen**. Klicken Sie auf den Link **Aufzeichnung**, um eine neue Audiodatei hochzuladen. Klicken Sie im neuen Browserfenster auf **Durchsuchen**, markieren Sie die gewünschte Audiodatei und klicken Sie dann auf **Öffnen**. Klicken Sie auf **Hochladen**, um die Datei zu laden.

    > [!NOTE]
    > Alle von Benutzern bereitgestellten Audiodateien müssen bestimmte Anforderungen erfüllen. Ausführliche Informationen zu den unterstützten Dateiformaten finden Sie unter [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).

18. Klicken Sie unter **Schritt 4: Geschäftszeiten angeben** im Feld **Ihre Zeitzone** auf die Zeitzone des Workflows.

    > [!NOTE]
    > Dies ist die Zeitzone, in der sich die Anrufer und Agents des Workflows befinden. Die Angabe wird verwendet, um die Öffnungszeiten zu berechnen. Wenn der Workflow z. B. für die mitteleuropäische Zeit konfiguriert wurde und der Workflow um 7:00 Uhr öffnen und um 23:00 Uhr schließen soll, werden die Zeiten 7:00 Uhr MEZ und 23:00 Uhr MEZ verwendet. (Die Zeiten müssen im 24-Stunden-Format eingegeben werden.)

19. Sie haben folgende Möglichkeiten, um die gewünschten Geschäftszeiten anzugeben:

    - Wenn Sie einen vordefinierten Zeitplan für die Geschäftszeiten verwenden möchten, klicken Sie auf **Vordefinierten Zeitplan verwenden** und wählen Sie den gewünschten Zeitplan in der Dropdownliste aus.

      > [!NOTE]
      > Sie müssen mindestens einen vordefinierten Zeitplan erstellt haben, um diese Option auswählen zu können. Sie erstellen vordefinierte Zeitpläne mit dem **New-CSRgsHoursOfBusiness**-Cmdlet. Weitere Informationen hierzu finden Sie unter [Reaktionsgruppe (Optional) Definieren von Geschäftszeiten in Skype für Unternehmen](optional-define-response-group-business-hours.md).

      > [!NOTE]
      > Wenn Sie einen vordefinierten Zeitplan verwenden, werden die Werte für **Tag**, **Öffnen** und **Schließen**, automatisch mit den Tagen und Stunden ausgefüllt, an denen die Reaktionsgruppe verfügbar ist.

    - Klicken Sie auf **Benutzerdefinierten Zeitplan verwenden**, um einen benutzerdefinierten Zeitplan zu erstellen, der nur für diesen Workflow gilt.

20. Wenn Sie einen benutzerdefinierten Zeitplan für diesen Workflow erstellen, aktivieren Sie die Kontrollkästchen für die Wochentage, an denen die Reaktionsgruppe verfügbar ist.

21. Wenn Sie einen benutzerdefinierten Zeitplan erstellen, geben Sie die **öffnenden** und **schließenden** Stunden für jeden Tag der Woche, die die reaktionsgruppe verfügbar ist.

    > [!NOTE]
    > Die Werte für **Öffnen** und **Schließen** müssen im 24-Stunden-Format angegeben werden. Wenn Ihr Büro z. B. von 9 Uhr bis 17 Uhr geöffnet und mittags geschlossen ist, können Sie die Geschäftszeiten als **Öffnen** 9:00, **Schließen** 12:00, **Öffnen** 13:00 und **Schließen** 17:00 angeben.

22. Wenn Sie eine Nachricht wiedergeben möchten, wenn das Büro geschlossen ist, aktivieren Sie das Kontrollkästchen **Nachricht wiedergeben, wenn die Reaktionsgruppe nicht geöffnet ist** und geben Sie die Nachricht ein, indem Sie eine der folgenden Aktionen ausführen:

    - Um die Nachricht als Text einzugeben, die für Anrufer in Sprache umgewandelt wird, klicken Sie auf **Text-zu-Sprache verwenden** und geben Sie die Nachricht in das Textfeld ein.

      > [!NOTE]
      > Verwenden Sie im eingegebenen Text keine HTML-Tags. Andernfalls wird eine Fehlermeldung angezeigt.

    - Um eine aufgezeichnete Audiodatei als Nachricht zu verwenden, klicken Sie auf **Aufzeichnung auswählen**. Klicken Sie auf den Link **Aufzeichnung**, um eine neue Audiodatei hochzuladen. Klicken Sie im neuen Browserfenster auf **Durchsuchen**, markieren Sie die gewünschte Datei und klicken Sie auf **Öffnen**. Klicken Sie auf **Hochladen**, um die Datei zu laden.

      > [!NOTE]
      > Alle von Benutzern bereitgestellten Audiodateien müssen bestimmte Anforderungen erfüllen. Ausführliche Informationen zu den unterstützten Audiodateiformaten finden Sie unter [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).

23. Geben Sie an, wie nach Wiedergabe der Nachricht verfahren werden soll (sofern eine Nachricht konfiguriert wurde):

    - Klicken Sie auf **Verbindung trennen**, um die Verbindung zu trennen.

    - Um den Anruf an ein Voicemailsystem weiterzuleiten, klicken Sie auf **An Voicemail weiterleiten** und geben Sie die Voicemailadresse ein. Das Format für Voicemail-Adresse ist * \<Username\>*@*\<DomainName\> * (beispielsweise bob@contoso.com).

    - Um den Anruf an einen anderen Benutzer weiterzuleiten, klicken Sie auf **An SIP-URI weiterleiten** und geben Sie die Adresse eines Benutzers ein. Das Format der Benutzeradresse lautet _ \<Username\>_@_\<DomainName\>_.

    - Um den Anruf an eine andere Telefonnummer weiterzuleiten, klicken Sie auf **An Telefonnummer weiterleiten** und geben Sie die Telefonnummer ein. Das Format für die Telefonnummer ist * \<Anzahl\>*@*\<DomainName\> * (beispielsweise +14255550121@contoso.com). Der Domänenname wird verwendet, um den Anrufer an das richtige Ziel weiterzuleiten.

24. Aktivieren Sie unter **Schritt 5: Feiertage angeben** die Kontrollkästchen für einen oder mehrere Feiertagssätze, mit denen die Tage definiert werden, an denen die Reaktionsgruppe aufgrund eines Feiertags nicht verfügbar ist.

    > [!NOTE]
    > Sie müssen Feiertage und Feiertagssätze definieren, bevor Sie den Workflow konfigurieren. Verwenden Sie zum Definieren von Feiertagen und Feiertagssätzen die Cmdlets **New-CsRgsHoliday** und **New-CsRgsHolidaySet**. Weitere Informationen hierzu finden Sie unter [feiertagssätze in Skype für Unternehmen (Optional) definieren Response Group](optional-define-response-group-holiday-sets.md).

25. Wenn Sie an Feiertagen eine Nachricht wiedergeben möchten, aktivieren Sie das Kontrollkästchen **An Feiertagen eine Nachricht wiedergegeben** und geben Sie die Nachricht ein, indem Sie eine der folgenden Aktionen ausführen:

    - Um die Nachricht als Text einzugeben, die für Anrufer in Sprache umgewandelt wird, klicken Sie auf **Text-zu-Sprache verwenden** und geben Sie die Nachricht in das Textfeld ein.

    > [!NOTE]
    > Verwenden Sie im eingegebenen Text keine HTML-Tags. Andernfalls wird eine Fehlermeldung angezeigt.

    - Um eine aufgezeichnete Audiodatei als Nachricht zu verwenden, klicken Sie auf **Aufzeichnung auswählen**. Klicken Sie auf den Link **Aufzeichnung**, um eine neue Audiodatei hochzuladen. Klicken Sie im neuen Browserfenster auf **Durchsuchen**, markieren Sie die gewünschte Datei und klicken Sie auf **Öffnen**. Klicken Sie auf **Hochladen**, um die Datei zu laden.

      > [!NOTE]
      > Alle von Benutzern bereitgestellten Audiodateien müssen bestimmte Anforderungen erfüllen. Ausführliche Informationen zu den unterstützten Audiodateiformaten finden Sie unter [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).

26. Geben Sie an, wie nach Wiedergabe der Nachricht verfahren werden soll (sofern eine Nachricht konfiguriert wurde):

    - Klicken Sie auf **Verbindung trennen**, um die Verbindung zu trennen.

    - Um den Anruf an ein Voicemailsystem weiterzuleiten, klicken Sie auf **An Voicemail weiterleiten** und geben Sie die Voicemailadresse ein. Das Format für Voicemail-Adresse ist * \<Username\>*@*\<DomainName\> * (beispielsweise bob@contoso.com).

    - Um den Anruf an einen anderen Benutzer weiterzuleiten, klicken Sie auf **An SIP-URI weiterleiten** und geben Sie die Adresse eines Benutzers ein. Das Format der Benutzeradresse lautet _ \<Username\>_@_\<DomainName\>_.

    - Um den Anruf an eine andere Telefonnummer weiterzuleiten, klicken Sie auf **An Telefonnummer weiterleiten** und geben Sie die Telefonnummer ein. Das Format für die Telefonnummer ist * \<Anzahl\>*@*\<DomainName\> * (beispielsweise +14255550121@contoso.com). Der Domänenname wird verwendet, um den Anrufer an das richtige Ziel weiterzuleiten.

27. Wählen Sie unter **Schritt 6: Warteschleife konfigurieren** im Feld **Warteschleife auswählen, an die die Anrufe weitergeleitet werden** die Warteschleife aus, in der die Anrufer gehalten werden, bis ein Agent verfügbar wird.

28. Wählen Sie unter **Schritt 7: Wartemusik konfigurieren** aus, welche Musik Anrufer beim Warten auf einen Agent hören sollen, indem Sie einen der folgenden Schritte ausführen:

    - Klicken Sie auf **Standard verwenden**, um die Standardwartemusik zu verwenden.

    - Klicken Sie auf **Musikdatei auswählen**, um eine aufgezeichnete Audiodatei als Wartemusik zu verwenden. Klicken Sie auf den Link **Musikdatei**, um eine neue Audiodatei hochzuladen. Klicken Sie im neuen Browserfenster auf **Durchsuchen**, markieren Sie die gewünschte Datei und klicken Sie auf **Öffnen**. Klicken Sie auf **Hochladen**, um die Datei zu laden.

      > [!NOTE]
      > Alle von Benutzern bereitgestellten Audiodateien müssen bestimmte Anforderungen erfüllen. Ausführliche Informationen zu den unterstützten Audiodateiformaten finden Sie unter [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).

29. Klicken Sie auf **Bereitstellen**.

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-hunt-group-workflow"></a>Verwenden Sie zum Erstellen oder ändern einen Workflow für Sammelanschlüsse Skype für Business Server-Verwaltungsshell

1. Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.

2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.

3. Erstellen Sie die Eingabeaufforderung, die als Willkommensnachricht abgespielt werden soll und speichern Sie sie in einer Variablen. Führen Sie an der Befehlszeile folgenden Befehl aus:

   ```
   $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

    Beispiel:

   ```
   $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "Welcome to Contoso. Please wait for an available agent."
   ```

     > [!NOTE]
     > Verwenden Sie das **Import-CsRgsAudioFile**-Cmdlet, um eine Audiodatei als Ansage zu verwenden. Weitere Informationen hierzu finden Sie unter [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).

4. Rufen Sie die Identität der Warteschleife oder Frage ab, an die die Anrufe weitergeleitet werden. Führen Sie an der Befehlszeile folgenden Befehl aus:

   ```
   $qid = (Get-CsRgsQueue -Name "Help Desk").Identity
   ```

    Ausführliche Informationen zum Erstellen der Warteschlange finden Sie unter [New-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/new-csrgsqueue?view=skype-ps).

5. Definieren Sie die durchzuführende Standardaktion, wenn ein Workflow während der Geschäftszeiten geöffnet wird, und speichern Sie sie in einer Variablen. Führen Sie in der Befehlszeile folgenden Befehl aus:

   ```
   $actionWM = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken> -QueueID $qid
   ```

    > [!NOTE]
    > Workflows für Sammelanschlüsse Gruppe muss die Standardaktion des Anrufs an eine Warteschleife direktes. Dieser Parameter ist erforderlich für aktive Workflows. Es ist nicht erforderlich für inaktive Workflows.

    Beispiel:

   ```
   $actionWM = New-CsRgsCallAction -Prompt $promptWM -Action TransferToQueue -QueueID $qid.Identity
   ```

6. Wenn Sie Geschäftszeiten und Feiertage definieren möchten, müssen Sie diese erstellen, bevor Sie den Workflow erstellen oder ändern. Weitere Informationen hierzu finden Sie unter [Reaktionsgruppe (Optional) Definieren von Geschäftszeiten in Skype für Unternehmen](optional-define-response-group-business-hours.md) und [(Optional) definieren Response Group feiertagssätze in Skype für Unternehmen](optional-define-response-group-holiday-sets.md).

7. Wenn eingabeaufforderungen für Anrufe werden soll, die außerhalb der Geschäftszeiten oder an Feiertagen empfangen werden, verwenden Sie das Cmdlet " **New-CsRgsPrompt** " So definieren Sie die Aufforderung, und verwenden Sie das **New-CsRgsCallAction** so definieren Sie die Aktion nach der Aufforderung erfolgen soll. Weitere Informationen hierzu finden Sie unter [New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps) und [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps).

8. Der Dienstname für Lync Server-reaktionsgruppendienst abgerufen und einer Variablen zuweisen. Führen Sie an der Befehlszeile folgenden Befehl aus:

   ```
   $serviceId = "service:" + (Get-CsService | ?{$_.Applications -like "*RGS*"}).ServiceId;
   ```

9. Erstellen oder ändern Sie den Workflow. Verwenden Sie **New-CsRgsWorkflow** zum Erstellen eines Workflows. Verwenden Sie **Set-CsRgsWorkflow** zum Ändern eines Workflows. Geben Sie in der Befehlszeile Folgendes ein:

   ```
   $workflowHG = New-CsRgsWorkflow -Parent <service ID for the Response Group service> -Name "<hunt group name>" [-Description "<hunt group description>"] -PrimaryUri "<SIP address for the workflow>" [-LineUri "<Phone number for the workflow>"] [-DisplayNumber "<Phone number displayed in Lync>"] [-Active <$true | $false>] [-Anonymous <$true | $false>] [-DefaultAction <variable from preceding step>] [-EnabledForFederation <$true | $false>] [-Managed <$true | $false>] [-ManagersByUri <SIP addresses for Response Group Managers who can manage the workflow>]
   ```

    Beispiel:

   ```
   $workflowHG = New-CsRgsWorkflow -Parent $serviceID -Name "Human Resources" -Description "Human Resources workflow" -PrimaryUri "sip:humanresources@contoso.com" -LineUri "TEL:+14255551219" -DisplayNumber "555-1219" -Active $true -Anonymous $true -DefaultAction $actionWM -EnabledForFederation $false -Managed $true -ManagersByUri "sip:bob@contoso.com", "mindy@contoso.com"
   ```

     > [!IMPORTANT]
     > Allen Benutzern, die designierte Workflowmanager sind, muss die Rolle „CsResponseGroupManager“ zugewiesen werden.

     > [!NOTE]
     > Ausführliche Informationen zu zusätzlichen optionalen Parametern finden Sie unter [New-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/new-csrgsworkflow?view=skype-ps) oder [Set-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/set-csrgsworkflow?view=skype-ps)

## <a name="designing-an-interactive-workflow"></a>Entwerfen eines interaktiven Workflows

Sie können die interaktive Sprachantwort (Interactive Voice Response, IVR) verwenden, um Informationen bei Anrufern abzufragen und den Anruf an die richtige Warteschleife zu leiten. Frage/Antwort-Paare bestimmten, welche Warteschleife verwendet wird. Je nach Antwort des Anrufers Anrufer entweder hört eine weitere Frage oder wird an die entsprechende Warteschlange weitergeleitet. Die IVR-Fragen und Antworten des Anrufers werden dem zuständigen Agent bereitgestellt, die den Anruf annimmt nützliche Informationen an den Agenten bereitstellen.

### <a name="overview-of-ivr-features"></a>Übersicht über die Funktionen der interaktiven Sprachantwort (IVR)

Die Anwendung "Reaktionsgruppe" bietet Spracherkennung und Text-Sprach-Funktionen in 26 Sprachen. Sie können mit Sprachausgabe oder eine WAV- oder Windows Media Audio (WMA)-Datei IVR-Fragen eingeben. Anrufer können Antworten mithilfe von VoIP oder Dual-Tone Multifrequency (DTMF) Antworten.

Interaktive Workflows unterstützt bis zu zwei Stufen von Fragen, mit dem jede Frage, dass bis zu vier mögliche Antworten. Die IVR stellt dem Anrufer eine Frage, und leitet je nach Antwort des Anrufers, den Anrufer an eine Warteschleife oder stellt eine zweite Frage. Die zweite Frage kann ebenfalls vier mögliche Antworten haben. Abhängig von der Antwort auf die Frage der zweiten Ebene wird der Anrufer an die geeignete Warteschleife weitergeleitet.

> [!NOTE]
> Beim Entwerfen von anrufflüssen mithilfe von Skype für Business Server-Verwaltungsshell können Sie eine beliebige Anzahl von Ebenen der IVR-Fragen und eine beliebige Anzahl von Antworten definieren. Aus Gründen der Benutzerfreundlichkeit wird jedoch empfohlen, nicht mehr als drei Frageebenen und pro Ebene nicht mehr als fünf Antworten zu definieren. Wenn Sie eine Anruffluss, die mehr als zwei Stufen von Fragen mit mehr als vier Antworten hat entwerfen, können nicht Sie mithilfe von Skype Business Server-Systemsteuerung darüber hinaus den Anruffluss bearbeiten.

Die IVR-Fragen und Antworten des Anrufers werden dem zuständigen Agent angezeigt, die den Anruf annimmt.

### <a name="working-with-speech-technologies"></a>Arbeiten mit Sprachtechnologien

Sprachtechnologien, wie beispielsweise Spracherkennung und Text-zu-Sprache (Sprachsynthese), können die Benutzerfreundlichkeit verbessern und Benutzern einen intuitiveren und einfacheren Zugriff auf Informationen bieten. Es kann jedoch vorkommen, dass der angegebene Text oder die Sprachantwort des Benutzers vom Sprachmodul nicht richtig erkannt wird. Das Symbol „#“ wird vom Text-zu-Sprache-Modul z. B. als das Wort „Nummer“ übersetzt. Diesem Problem kann wie folgt entgegengewirkt werden:

- Das Sprachmodul gibt dem Anrufer fünf Versuche, die Frage zu beantworten. Wenn der Anrufer die Frage falsch beantwortet (die Antwort also keiner der angegebenen Antworten entspricht) oder keine Antwort gibt, erhält er eine weitere Möglichkeit, die Frage zu beantworten. Der Anrufer hat fünf Versuche, die Frage zu beantworten, bevor die Verbindung getrennt wird. Sie können das interaktive Sprachantwortsystem so konfigurieren, dass nach einem Anruferfehler eine benutzerdefinierte Nachricht wiedergegeben wird. Die Frage wird jedes Mal wiederholt.

- Um zu vermeiden, dass Hintergrundgeräusche vom Sprachmodul als Antwort erkannt werden, sollten Sie längere Antworten verwenden. Antworten sollten beispielsweise mehr als eine Silbe umfassen und sich deutlich voneinander unterscheiden.

- Wenn für Fragen sowohl eine Antwort per Spracheingabe als auch per Tastendruck (MFV) möglich ist, konfigurieren Sie die Sprachantworten mit Wörtern, die das Konzept widerspiegeln, statt auf die Taste zu verweisen. Verwenden Sie beispielsweise anstelle von „Drücken oder sagen Sie 1“ die Eingabeaufforderung „Drücken Sie die 1 oder sagen Sie Rechnung“.

- Rufen Sie den Workflow nach dem Entwerfen der interaktiven Sprachantwort an, hören Sie sich die Eingabeaufforderungen an, reagieren Sie auf alle Eingabeaufforderungen per Spracheingabe und überprüfen Sie, ob die interaktive Sprachantwort (IVR) sich wie gewünscht anhört und verhält. Anschließend können Sie den Workflow bearbeiten, um etwaige Interpretationsfehler zu beheben. Wenn Sie wie im vorgenannten Beispiel auf die Taste „#“ verweisen müssen, können Sie die IVR-Eingabeaufforderung so umschreiben, dass der Name der Taste und nicht das Symbol „#“ verwendet wird. Beispiel: „Wenn Sie mit unserem Vertrieb verbunden werden möchten, drücken Sie die Rautetaste.“

### <a name="ivr-design-examples"></a>IVR-Entwurfsbeispiele

Die folgenden Abschnitte zeigen Beispiele für unterschiedliche IVR-Szenarien und Frage/Antwort-Paare.

#### <a name="ivr-with-one-level-of-questions"></a>IVR mit einer Frageebene

Das folgende Beispiel zeigt einen IVR-Entwurf mit einer Frageebene. Die Spracherkennung verwendet, um die Antwort des Anrufers zu erkennen.

 **Frage:** „Willkommen bei der Personalabteilung. Falls Sie mit der Lohnbuchhaltung sprechen möchten, sagen Sie ‚Lohnbuchhaltung‘ Sagen Sie andernfalls ‚Personalabteilung‘.“

- **Option 1 wurde gewählt:** Der Anrufer wird an das Team der Lohnbuchhaltung weitergeleitet.

- **Option 2 wurde gewählt:** Der Anrufer wird an das Team der Personalabteilung weitergeleitet.

In der folgenden Abbildung ist der Anruffluss dargestellt.

 **Interaktiver Anruffluss mit einer Ebene**

![Entwerfen von Anrufflüssen mithilfe von Anrufflüssen für interaktive](../../media/Ops_OCS_RGS_IVRLevel1.jpg)

#### <a name="ivr-with-two-levels-of-questions"></a>IVR mit zwei Frageebenen

Das folgende Beispiel zeigt einen IVR-Entwurf mit zwei Frageebenen. Dabei können Anrufer entweder per Spracheingabe oder per Tastendruck (MFV) antworten.

 **Frage:** „Willkommen beim IT-Helpdesk. Wenn Sie ein Problem mit dem Netzwerkzugriff haben, drücken Sie die 1 oder sagen Sie ‚Netzwerk‘. Wenn Sie ein Softwareproblem haben, drücken Sie die 2 oder sagen Sie ‚Software‘. Wenn Sie ein Hardwareproblem haben, drücken Sie die 3 oder sagen Sie ‚Hardware‘.“

- **Option 1 wurde gewählt:** Der Anrufer wird an das Team für den Netzwerksupport weitergeleitet.

- **Option 2 wurde gewählt:** Dem Anrufer wird eine weitere Frage gestellt.

    **Frage:** „Wenn Sie ein Problem mit dem Betriebssystem haben, drücken Sie die 1 oder sagen Sie ‚Betriebssystem‘. Wenn Sie ein Problem mit einer internen Anwendung haben, drücken Sie die 2 oder sagen Sie ‚interne Anwendung‘. Andernfalls drücken Sie die 3 oder sagen Sie ‚Sonstiges‘.“

  - **Option 1 wurde gewählt:** Der Anrufer wird an das Team für den Betriebssystemsupport weitergeleitet.

  - **Option 2 wurde gewählt:** Der Anrufer wird an das Supportteam für interne Anwendungen weitergeleitet.

  - **Option 3 wurde gewählt:** Der Anrufer wird an das Team für den Softwaresupport weitergeleitet.

- **Option 3 wurde gewählt:** Dem Anrufer wird eine weitere Frage gestellt.

    **Frage:** „Wenn Sie ein Problem mit dem Drucker haben, drücken Sie die 1. Andernfalls drücken Sie die 2.“

  - **Option 1 wurde gewählt:** Der Anrufer wird an das Team für den Druckersupport weitergeleitet.

  - **Option 2 wurde gewählt:** Der Anrufer wird an das Team für den Hardwaresupport weitergeleitet.

In der folgenden Abbildung ist der Anruffluss dargestellt.

 **Interaktiver Anruffluss mit zwei Ebenen**

![Entwerfen von Anrufflüssen mithilfe von Anrufflüssen für interaktive](../../media/Ops_OCS_RGS_IVRLevel2.jpg)

### <a name="best-practices"></a>Bewährte Methoden

In der folgenden Liste werden einige bewährte Methoden für das Entwerfen der interaktiven Sprachantwort beschrieben:

- Leiten Sie den Anrufer schnell an die gewünschte Kontaktperson weiter. Vermeiden Sie interaktive Sprachantworten mit zu vielen Informationen und langen Marketingbotschaften.

- Wenn Sie eine lange Nachricht verwenden möchten, hängen Sie diese eher an die erste Frage statt an die Willkommensnachricht an. Anrufer können die Nachricht durch Beantwortung der Frage umgehen, wenn sie Teil der ersten Frage ist. Eine Umgehung der Willkommensnachricht ist jedoch nicht möglich.

- Sprechen Sie die Sprache des Anrufers. Vermeiden Sie eine gestelzte Ausdrucksweise. Sprechen Sie natürlich.

- Formulieren Sie effiziente und effektive Anweisungen. Entfernen Sie unnötige Optionen. Strukturieren der Informationen an, sodass erwartete Antwort des Anrufers am Ende des Satzes befindet. Beispielsweise "Wenn an das Team der Vertriebsmitarbeiter sprechen möchten, drücken Sie die 1".

- Gestalten Sie Sprachantworten benutzerfreundlich. Wenn beispielsweise sowohl eine Antwort per Spracheingabe als auch eine Antwort per Tastendruck (MFV) zulässig ist, verwenden Sie eine Formulierung wie diese: „Wenn Sie mit unserem Vertrieb verbunden werden möchten, drücken Sie die 1 oder sagen Sie ‚Vertrieb‘.“

- Testen Sie den IVR-Workflow in einer Gruppe von Benutzern, bevor Sie ihn in Ihrer Organisation bereitstellen.

## <a name="creating-or-modifying-an-interactive-workflow"></a>Erstellen oder Ändern eines interaktiven Workflows

### <a name="to-use-response-group-configuration-tool-to-create-or-modify-an-interactive-workflow"></a>Verwenden des Konfigurationstools für Reaktionsgruppen erstellen oder Ändern eines interaktiven Workflows

1. Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.

2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.

3. Klicken Sie in der linken Navigationsleiste auf **Reaktionsgruppen** und dann auf **Workflow**.

4. Klicken Sie auf der Seite **Workflow** auf **Workflow erstellen oder bearbeiten**.

5. Geben Sie im Suchfeld **Dienst auswählen** einen Teil oder den vollständigen Namen des **ApplicationServer**-Diensts ein, von dem der Workflow gehostet wird, den Sie erstellen oder ändern möchten. Klicken Sie in der nun angezeigten Liste der Dienst auf den gewünschten Dienst und klicken Sie dann auf **OK**.

    > [!NOTE]
    > Das Konfigurationstool für Reaktionsgruppen wird geöffnet. Sie können auch das Konfigurationstool für Reaktionsgruppen direkt über einen Webbrowser öffnen, indem Sie die folgende URL eingeben: https://\<WebPoolFqdn\>/RgsConfig.

6. Führen Sie einen der folgenden Schritte aus:

   - Klicken Sie unterhalb von **Neuen Workflow erstellen** neben **Interaktiv** auf **Erstellen**.

   - Suchen Sie unter **Vorhandenen Workflow verwalten** nach dem Workflow, den Sie ändern möchten, und klicken Sie anschließend unter **Aktion** auf **Bearbeiten**.

7. Falls Benutzer den Workflow noch nicht aufrufen sollen, müssen Sie das Kontrollkästchen **Workflow aktivieren** deaktivieren.

    > [!NOTE]
    >  Wenn Sie einen verwalteten Workflow erstellen, müssen Sie **den Workflow aktivieren**auswählen. Nachdem Sie den aktiven, verwalteten Workflow gespeichert haben, können Sie ihn ändern und deaktivieren.

8. Aktivieren Sie das Kontrollkästchen **Für Partnerverbund aktivieren**, um Partnerbenutzern Anrufe bei der Gruppe zu ermöglichen. Sie benötigen auch eine externe Zugriffsrichtlinie, die für die Anwendung "Reaktionsgruppe" für den Verbund konfiguriert gilt.

    > [!NOTE]
    > Die globale externe Zugriffsrichtlinie gilt für die Anwendung "Reaktionsgruppe". Sie können die globale Richtlinie für den Verbund Antwort-Gruppe konfigurieren, mithilfe von Skype Business Server-Systemsteuerung oder mit dem **Set-CsExternalAccessPolicy** -Cmdlet den EnableOutsideAccess-Parameter auf True festgelegt. Bedenken Sie, dass globale Richtlinieneinstellungen für alle Benutzer gelten, es sei denn, sie sind einer standort- oder benutzerspezifischen Richtlinie zugeordnet. Stellen Sie daher vor dem Ändern dieser Einstellung für Reaktionsgruppen sicher, dass die Partnerverbundeinstellung die Anforderungen Ihrer Organisation erfüllt. Nähere Informationen dazu, wie sich Richtlinien auf Benutzer auswirken, finden Sie unter [Manage External Access Policy for Your Organization](https://technet.microsoft.com/library/5571811e-34c8-443a-b94c-1ab5d4275581.aspx). Ausführliche Informationen zu den partnerverbundeinstellung finden Sie unter **Set-CsExternalAccessPolicy** in der Dokumentation.

    > [!NOTE]
    > Benutzer, die in Skype für Business Online gehostet werden können nicht tätigen von Anrufen zu Response Groups, die gehostet werden in einer lokalen Bereitstellung. Dies gilt in beiden hybridbereitstellungen und in Fällen, in dem eine lokale Bereitstellung mit einem Skype für Business Online-Bereitstellung im Verbund befindet.

9. Aktivieren Sie das Kontrollkästchen **Agentanonymität aktivieren**, um bei Anrufen die Identität der Agents zu verbergen.

    > [!NOTE]
    > Anonyme Anrufe können nicht mit Chats oder Video gestartet werden. Agent oder Anrufer können jedoch im Verlauf des Anrufs Chats und Video aktivieren. Ein anonymer Agent kann Anrufe halten, weiterleiten (sowohl blind als auch nach Rücksprache) sowie Anrufe parken und fortsetzen. Anonyme Anrufe bieten keine Unterstützung für Konferenzen, Anwendungs- und Desktopfreigabe, Dateiübertragung, Whiteboardverwendung und Datenzusammenarbeit sowie Anrufaufzeichnung. Agents, die das Lync VDI-Plugin verwenden, können eingehende Anrufe anonym empfangen, jedoch keine ausgehenden anonymen Anrufe tätigen.

10. Geben Sie im Feld **Adresse der Gruppe eingeben, die die Anrufe entgegennimmt** den primären SIP-URI (Uniform Resource Identifier) der Gruppe ein, die die Anrufe beim Workflow erhalten soll.

11. Geben Sie im Feld **Anzeigename** den Namen ein, der für den Workflow angezeigt werden soll (z. B. „Vertrieb-IVR-Reaktionsgruppe“).

    > [!NOTE]
    > Schließen Sie nicht die "\<"oder"\>" Zeichen in den Anzeigenamen. Die folgenden Anzeigenamen sind reserviert und dürfen nicht verwendet werden: **RGS-Anwesenheitsmonitor** oder **Ankündigungsdienst**.

12. Geben Sie unter **Telefonnummer** den Anschluss-URI für die Reaktionsgruppe ein (z. B. +14255550165).

13. Geben Sie im Feld **Anzeigenummer** die Nummer ein, wie sie für die Reaktionsgruppe angezeigt werden soll (z. B. +1 (425) 555-0165).

14. (Optional) Geben Sie im Feld **Beschreibung**eine Beschreibung für den Workflow, den auf der Visitenkarte in Skype für Unternehmen angezeigt werden soll.

15. Wählen Sie unter **Workflowtyp** die Option **Verwaltet** aus, wenn dieser Workflow von einem Reaktionsgruppenmanager verwaltet wird. Gehen Sie Reaktionsgruppen-Manager, um den Workflow zuzuweisen:

    a. Geben Sie den SIP-URI eines Managers für diesen Workflow ein und klicken Sie auf **Hinzufügen**.

    b. Geben Sie den SIP-URI zusätzlicher Manager für den Workflow ein und klicken Sie auf **Hinzufügen**.

    > [!IMPORTANT]
    > Jedem Benutzer, der als Manager einer Reaktionsgruppe bestimmt wurde, muss die Rolle „CsResponseGroupManager“ zugewiesen sein. Falls Benutzern diese Rolle nicht zugewiesen ist, können sie keine Reaktionsgruppen verwalten.

16. Klicken Sie unter **Schritt 2: Sprache auswählen** auf die Sprache, die für die Spracherkennung und die Text-zu-Sprache-Funktion verwendet werden soll.

17. Aktivieren Sie zum Konfigurieren einer Willkommensnachricht unter **Schritt 3: Willkommensnachricht konfigurieren** das Kontrollkästchen **Willkommensnachricht wiedergeben** und führen Sie eine der folgenden Aktionen aus:

    - Um die Willkommensnachricht als Text einzugeben, die für Anrufer in Sprache umgewandelt wird, klicken Sie auf **Text-zu-Sprache verwenden** und geben Sie die Willkommensnachricht in das Textfeld ein.

    > [!NOTE]
    > Verwenden Sie im eingegebenen Text keine HTML-Tags. Andernfalls wird eine Fehlermeldung angezeigt.

    - Um eine aufgezeichnete WAV- oder WMA-Datei für die Willkommensnachricht zu verwenden, klicken Sie auf **Aufzeichnung auswählen**. Klicken Sie auf den Link **Aufzeichnung**, um eine neue Audiodatei hochzuladen. Klicken Sie im neuen Browserfenster auf **Durchsuchen**, markieren Sie die gewünschte Audiodatei und klicken Sie dann auf **Öffnen**. Klicken Sie auf **Hochladen**, um die Datei zu laden.

    > [!NOTE]
    > Alle von Benutzern bereitgestellten Audiodateien müssen bestimmte Anforderungen erfüllen. Ausführliche Informationen zu den unterstützten Dateiformaten finden Sie unter [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).

18. Klicken Sie unter **Schritt 4: Geschäftszeiten angeben** im Feld **Ihre Zeitzone** auf die Zeitzone des Workflows.

    > [!NOTE]
    > Dies ist die Zeitzone, in der sich die Anrufer und Agents des Workflows befinden. Die Angabe wird verwendet, um die Öffnungszeiten zu berechnen. Wenn der Workflow z. B. für die mitteleuropäische Zeit konfiguriert wurde und der Workflow um 7:00 Uhr öffnen und um 11:00 Uhr schließen soll, werden die Zeiten 7:00 Uhr MEZ und 23:00 Uhr MEZ verwendet. (Die Zeiten müssen im 24-Stunden-Format eingegeben werden.)

19. Sie haben folgende Möglichkeiten, um die gewünschten Geschäftszeiten anzugeben:

    - Wenn Sie einen vordefinierten Zeitplan für die Geschäftszeiten verwenden möchten, klicken Sie auf **Vordefinierten Zeitplan verwenden** und wählen Sie den gewünschten Zeitplan in der Dropdownliste aus.

      > [!NOTE]
      > Sie müssen mindestens einen vordefinierten Zeitplan erstellt haben, um diese Option auswählen zu können. Definieren Sie vorgegebenen Zeitpläne mit dem Cmdlet **New-CsRgsHoursOfBusiness** . Weitere Informationen hierzu finden Sie unter [Reaktionsgruppe (Optional) Definieren von Geschäftszeiten in Skype für Unternehmen](optional-define-response-group-business-hours.md). Wenn Sie einen vordefinierten Zeitplan verwenden, werden die Werte für **Tag**, **Öffnen** und **Schließen**, automatisch mit den Tagen und Stunden ausgefüllt, an denen die Reaktionsgruppe verfügbar ist.

    - Klicken Sie auf **Benutzerdefinierten Zeitplan verwenden**, um einen benutzerdefinierten Zeitplan zu erstellen, der nur für diesen Workflow gilt.

20. Wenn Sie einen benutzerdefinierten Zeitplan für diesen Workflow erstellen, aktivieren Sie die Kontrollkästchen für die Wochentage, an denen die Reaktionsgruppe verfügbar ist.

21. Wenn Sie einen benutzerdefinierten Zeitplan erstellen, geben Sie die **öffnenden** und **schließenden** Stunden, wenn die reaktionsgruppe verfügbar ist.

     > [!NOTE]
     > Die Werte für **Öffnen** und **Schließen** müssen im 24-Stunden-Format angegeben werden. Wenn Ihr Büro z. B. von 9 Uhr bis 17 Uhr geöffnet und mittags geschlossen ist, können Sie die Geschäftszeiten als **Öffnen** 9:00, **Schließen** 12:00, **Öffnen** 13:00 und **Schließen** 17:00 angeben.

22. Wenn Sie eine Nachricht wiedergeben möchten, wenn das Büro geschlossen ist, aktivieren Sie das Kontrollkästchen **Nachricht wiedergeben, wenn die Reaktionsgruppe nicht geöffnet ist** und geben Sie die Nachricht ein, indem Sie eine der folgenden Aktionen ausführen:

    - Um die Nachricht als Text einzugeben, die für Anrufer in Sprache umgewandelt wird, klicken Sie auf **Text-zu-Sprache verwenden** und geben Sie die Nachricht in das Textfeld ein.

      > [!NOTE]
      > Verwenden Sie im eingegebenen Text keine HTML-Tags. Andernfalls wird eine Fehlermeldung angezeigt.

    - Um eine aufgezeichnete Audiodatei als Nachricht zu verwenden, klicken Sie auf **Aufzeichnung auswählen**. Klicken Sie auf den Link **Aufzeichnung**, um eine neue Audiodatei hochzuladen. Klicken Sie im neuen Browserfenster auf **Durchsuchen**, markieren Sie die gewünschte Datei und klicken Sie auf **Öffnen**. Klicken Sie auf **Hochladen**, um die Datei zu laden.

    > [!NOTE]
    > Alle von Benutzern bereitgestellten Audiodateien müssen bestimmte Anforderungen erfüllen. Ausführliche Informationen zu den unterstützten Dateiformaten finden Sie unter [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).

23. Geben Sie an, wie nach Wiedergabe der Nachricht verfahren werden soll (sofern eine Nachricht konfiguriert wurde):

    - Klicken Sie auf **Verbindung trennen**, um die Verbindung zu trennen.

    - Um den Anruf an ein Voicemailsystem weiterzuleiten, klicken Sie auf **An Voicemail weiterleiten** und geben Sie die Voicemailadresse ein. Das Format für Voicemail-Adresse ist * \<Username\>*@*\<Domainname\> * (beispielsweise bob@contoso.com).

    - Um den Anruf an einen anderen Benutzer weiterzuleiten, klicken Sie auf **An SIP-URI weiterleiten** und geben Sie die Adresse eines Benutzers ein. Das Format der Benutzeradresse lautet _ \<Username\>_@_\<Domainname\>_.

    - Um den Anruf an eine andere Telefonnummer weiterzuleiten, klicken Sie auf **An Telefonnummer weiterleiten** und geben Sie die Telefonnummer ein. Das Format für die Telefonnummer ist * \<Anzahl\>*@*\<Domainname\> * (beispielsweise +14255550121@contoso.com). Der Domänenname wird verwendet, um den Anrufer an das richtige Ziel weiterzuleiten.

24. Aktivieren Sie unter **Schritt 5: Feiertage angeben** die Kontrollkästchen für einen oder mehrere Feiertagssätze, mit denen die Tage definiert werden, an denen die Reaktionsgruppe aufgrund eines Feiertags nicht verfügbar ist.

    > [!NOTE]
    > Sie müssen Feiertage und Feiertagssätze definieren, bevor Sie den Workflow konfigurieren. Verwenden Sie zum Definieren von Feiertagen und Feiertagssätzen die Cmdlets **New-CsRgsHoliday** und **New-CsRgsHolidaySet**. Weitere Informationen hierzu finden Sie unter [feiertagssätze in Skype für Unternehmen (Optional) definieren Response Group](optional-define-response-group-holiday-sets.md).

25. Wenn Sie an Feiertagen eine Nachricht wiedergeben möchten, aktivieren Sie das Kontrollkästchen **An Feiertagen eine Nachricht wiedergegeben** und geben Sie die Nachricht ein, indem Sie eine der folgenden Aktionen ausführen:

    - Um die Nachricht als Text einzugeben, die für Anrufer in Sprache umgewandelt wird, klicken Sie auf **Text-zu-Sprache verwenden** und geben Sie die Nachricht in das Textfeld ein.

      > [!NOTE]
      > Verwenden Sie im eingegebenen Text keine HTML-Tags. Andernfalls wird eine Fehlermeldung angezeigt.

    - Um eine aufgezeichnete Audiodatei als Nachricht zu verwenden, klicken Sie auf **Aufzeichnung auswählen**. Klicken Sie auf den Link **Aufzeichnung**, um eine neue Audiodatei hochzuladen. Klicken Sie im neuen Browserfenster auf **Durchsuchen**, markieren Sie die gewünschte Datei und klicken Sie auf **Öffnen**. Klicken Sie auf **Hochladen**, um die Datei zu laden.

      > [!NOTE]
      > Alle von Benutzern bereitgestellten Audiodateien müssen bestimmte Anforderungen erfüllen. Ausführliche Informationen zu den unterstützten Audiodateiformaten finden Sie unter [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).

26. Geben Sie an, wie nach Wiedergabe der Nachricht verfahren werden soll (sofern eine Nachricht konfiguriert wurde):

    - Klicken Sie auf **Verbindung trennen**, um die Verbindung zu trennen.

    - Um den Anruf an ein Voicemailsystem weiterzuleiten, klicken Sie auf **An Voicemail weiterleiten** und geben Sie die Voicemailadresse ein. Das Format für Voicemail-Adresse ist * \<Username\>*@*\<Domainname\> * (beispielsweise bob@contoso.com).

    - Um den Anruf an einen anderen Benutzer weiterzuleiten, klicken Sie auf **An SIP-URI weiterleiten** und geben Sie die Adresse eines Benutzers ein. Das Format der Benutzeradresse lautet _ \<Username\>_@_\<Domainname\>_.

    - Um den Anruf an eine andere Telefonnummer weiterzuleiten, klicken Sie auf **An Telefonnummer weiterleiten** und geben Sie die Telefonnummer ein. Das Format für die Telefonnummer ist * \<Anzahl\>*@*\<Domainname\> * (beispielsweise +14255550121@contoso.com). Der Domänenname wird verwendet, um den Anrufer an das richtige Ziel weiterzuleiten.

27. Wählen Sie unter **Schritt 6: Wartemusik konfigurieren** aus, was Anrufer beim Warten auf einen Agent hören sollen, indem Sie einen der folgenden Schritte ausführen:

    - Klicken Sie auf **Standard verwenden**, um die Standardwartemusik zu verwenden.

    - Klicken Sie auf **Musikdatei auswählen**, um eine aufgezeichnete Audiodatei als Wartemusik zu verwenden. Klicken Sie auf den Link **Musikdatei**, um eine neue Audiodatei hochzuladen. Klicken Sie im neuen Browserfenster auf **Durchsuchen**, markieren Sie die gewünschte Datei und klicken Sie auf **Öffnen**. Klicken Sie auf **Hochladen**, um die Datei zu laden.

    > [!NOTE]
    > Alle von Benutzern bereitgestellten Audiodateien müssen bestimmte Anforderungen erfüllen. Ausführliche Informationen zu den unterstützten Dateiformaten finden Sie unter [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).

28. Geben Sie in **Schritt 7: Interaktive Sprachantwort (IVR) konfigurieren** unter **Der Benutzer hört den folgenden Text bzw. die folgende aufgezeichnete Nachricht** die Frage ein, die dem Anrufer gestellt wird. Führen Sie hierzu die folgenden Aktionen aus:

    - Um die Frage im Textformat einzugeben, klicken Sie auf **Text-zu-Sprache verwenden** und geben Sie die Frage in das Textfeld ein.

    > [!NOTE]
    > Verwenden Sie im eingegebenen Text keine HTML-Tags. Andernfalls wird eine Fehlermeldung angezeigt.

    > [!NOTE]
    > Das Symbol „#“ wird vom Text-zu-Sprache-Modul als das Wort „Nummer“ übersetzt. Wenn Sie auf die Taste # verweisen möchten, sollten Sie bei der Eingabe anstelle des Symbols den Tastennamen verwenden. Beispiel: „Wenn Sie mit unserem Vertrieb verbunden werden möchten, drücken Sie die Rautetaste.“

    - Um eine aufgezeichnete Audiodatei mit der Frage zu verwenden, klicken Sie auf **Aufzeichnung auswählen** und dann auf den Link **Aufzeichnung**, um die Datei hochzuladen. Klicken Sie im neuen Browserfenster auf **Durchsuchen**, markieren Sie die gewünschte Audiodatei und klicken Sie auf **Öffnen**. Klicken Sie auf **Hochladen** , um die Datei zu laden, und geben Sie dann optional Sie können die Frage in das Textfeld (auf diese Weise können die Frage und Antwort des Anrufers an den zuständigen Agent weitergeleitet werden).

      > [!NOTE]
      > Alle von Benutzern bereitgestellten Audiodateien müssen bestimmte Anforderungen erfüllen. Ausführliche Informationen zu den unterstützten Dateiformaten finden Sie unter [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).

29. Geben Sie unter **Antwort 1** wie folgt die erste mögliche Antwort auf die Frage ein:

    > [!IMPORTANT]
    > Verwenden Sie in Sprachantworten keine Anführungszeichen („“). Bei Verwendung von Anführungszeichen funktioniert die interaktive Sprachantwort nicht ordnungsgemäß.

    > [!NOTE]
    > Sie können auswählen, ob Anrufer per Sprache, Tasteneingabe oder beidem antworten können.

    - Wenn Sie zulassen möchten, dass Anrufer per Sprache antworten, geben Sie die Antwort in das Feld **Sprachantwort eingeben** ein.

    - Wenn Sie zulassen möchten, dass Anrufer per Tasteneingabe antworten, klicken Sie im Feld **Ziffer** auf die entsprechende Ziffer.

30. Geben Sie wie folgt an, ob der Anrufer an eine Warteschleife weitergeleitet wird oder ob eine weitere Frage gestellt werden soll:

    - Um den Anrufer an eine Warteschleife weiterzuleiten, klicken Sie auf **An eine Warteschleife senden** und klicken Sie unter **Warteschleife auswählen** auf die Warteschleife, die Sie verwenden möchten.

    - Wenn eine weitere Frage gestellt werden soll, klicken Sie auf **Eine weitere Frage stellen**, klicken Sie dann auf **Text-zu-Sprache verwenden** und geben Sie die Frage ein oder klicken Sie auf **Aufzeichnung auswählen**. Verwenden Sie die Einstellungen in diesem Abschnitt, um bis zu vier mögliche Antworten auf die zusätzliche Frage sowie die Warteschleife für jede Antwort anzugeben. Um eine dritte oder vierte mögliche Antwort anzugeben, aktivieren Sie das Kontrollkästchen **Antwort 3** oder das Kontrollkästchen **Antwort 4**.

31. Geben Sie bis zu drei weitere mögliche Antworten auf die ursprüngliche Frage ein, indem Sie die Schritte 28 und 29 wiederholen, um mögliche Antworten und die Aktion für jede Antwort anzugeben. Um eine dritte oder vierte mögliche Antwort anzugeben, aktivieren Sie das Kontrollkästchen **Antwort 3** oder das Kontrollkästchen **Antwort 4**.

32. Klicken Sie auf **Bereitstellen**.

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-an-interactive-workflow"></a>Verwenden von Skype für Business Server-Verwaltungsshell zum Erstellen oder Ändern eines interaktiven Workflows

1.  Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.

2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.

3. Rufen Sie den Dienstnamen für den Reaktionsgruppendienst ab und weisen Sie ihn einer Variablen zu. Führen Sie an der Eingabeaufforderung folgenden Befehl aus:

   ```
   $serviceId = "service:" + (Get-CsService | ?{$_.Applications -like "*RGS*"}).ServiceId;
   ```

4. Ein interaktiver Workflow erfordert mindestens zwei Warteschlangen und mindestens zwei Agentgruppen. Erstellen Sie zunächst die Agentgruppen. Führen Sie folgenden Befehl aus:

   ```
   $AGSupport = New-CsRgsAgentGroup -Parent $serviceId -Name "Technical Support" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:agent1@contoso.com", "sip:agent2@contoso.com")]
   $AGSales = New-CsRgsAgentGroup -Parent $serviceId -Name "Sales Team" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:bob@contoso.com", "sip:alice@contoso.com")]
   ```

5. Erstellen Sie die Warteschlangen. Führen Sie folgenden Befehl aus:

   ```
   $QSupport = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Support" -AgentGroupIDList($AG-Support.Identity)
   $QSales = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Sales" -AgentGroupIDList($AG-Sales.Identity)
   ```

6. Erstellen Sie die erste Reaktionsgruppen-Eingabeaufforderung. Führen Sie folgenden Befehl aus:

   ```
   $SupportPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please be patient while we connect you with Contoso Technical Support."
   ```

7. Erstellen Sie anschließend die Aktion, die nach der Eingabeaufforderung ausgeführt werden soll. Führen Sie folgenden Befehl aus:

   ```
   $SupportAction = New-CsRgsCallAction -Prompt $SupportPrompt -Action TransferToQueue -QueueID $QSupport.Identity
   ```

8. Erstellen Sie die erste Reaktionsgruppenantwort. Führen Sie folgenden Befehl aus:

   ```
   $SupportAnswer = New-CsRgsAnswer -Action $SupportAction [-DtmfResponse 1]
   ```

9. Erstellen Sie nun die zweite Eingabeaufforderung, die zweite Anrufaktion und die zweite Antwort. Erstellen Sie zunächst die Eingabeaufforderung. Führen Sie folgenden Befehl aus:

   ```
   $SalesPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please hold while we connect you with Contoso Sales."
   ```

10. Erstellen Sie die zweite Anrufaktion. Führen Sie folgenden Befehl aus:

    ```
    $SalesAction = New-CsRgsCallAction -Prompt $SalesPrompt -Action TransferToQueue -QueueID $QSales.Identity
    ```

11. Erstellen Sie die zweite Reaktionsgruppenantwort. Führen Sie folgenden Befehl aus:

    ```
    $SalesAnswer = New-CsRgsAnswer -Action $SalesAction [-DtmfResponse 2]
    ```

12. Erstellen Sie die Eingabeaufforderung der obersten Ebene. Führen Sie folgenden Befehl aus:

    ```
    $TopLevelPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Thank you for calling Contoso. For Technical Support, press 1. For a Sales Representative, press 2."
    ```

13. Erstellen Sie die Frage der obersten Ebene. Führen Sie folgenden Befehl aus:

    ```
    $TopLevelQuestion = New-CsRgsQuestion -Prompt $TopLevelPrompt [-AnswerList ($SupportAnswer, $SalesAnswer)]
    ```

14. Erstellen Sie nun den Workflow. Führen Sie folgenden Befehl aus:

    ```
    $IVRAction = New-CsRgsCallAction -Action TransferToQuestion [-Question $Question]
    $IVRWorkflow = New-CsRgsWorkflow -Parent $ServiceId -Name "Contoso Helpdesk" [-Description "The Contoso Helpdesk line."] -PrimaryUri "sip:helpdesk@contoso.com" [-LineUri tel:+14255554321] [-DisplayNumber "+1 (425) 555-4321"] [-Active $true] [-Anonymous $true] [-DefaultAction $IVRAction] [-Managed $true] [-ManagersByURI ("sip:mindy@contoso.com", "sip:bob@contoso.com")]
    ```

     > [!NOTE]
     > Alle Benutzer, die als Manager Mitglied einer reaktionsgruppe festgelegt wurde, müssen die Rolle CsResponseGroupManager zugewiesen werden. Falls Benutzern diese Rolle nicht zugewiesen ist, können sie keine Reaktionsgruppen verwalten.

## <a name="see-also"></a>Siehe auch

[(Optional) Definieren von Reaktionsgruppe feiertagssätze in Skype für Unternehmen](optional-define-response-group-holiday-sets.md)

[(Optional) Reaktionsgruppe Definieren von Geschäftszeiten in Skype für Unternehmen](optional-define-response-group-business-hours.md)

[Mit New-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/new-csrgsworkflow?view=skype-ps)

[Set-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/set-csrgsworkflow?view=skype-ps)

[New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps)

[Mit New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)

