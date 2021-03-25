---
title: Entwerfen und Erstellen von Reaktionsgruppeworkflows in Skype for Business
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
ms.assetid: dcb9effb-5d12-4dee-80fc-ab9654222d5a
description: Entwerfen und Erstellen von Reaktionsgruppeworkflows in Skype for Business Server Enterprise-VoIP. Sowohl Sammelgruppenworkflows als auch interaktive Workflows werden behandelt.
ms.openlocfilehash: 678dcb25f5f802f101016a2a289015a60e48ba88
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51105781"
---
# <a name="designing-and-creating-response-group-workflows-in-skype-for-business"></a>Entwerfen und Erstellen von Reaktionsgruppeworkflows in Skype for Business

Entwerfen und Erstellen von Reaktionsgruppeworkflows in Skype for Business Server Enterprise-VoIP. Sowohl Sammelgruppenworkflows als auch interaktive Workflows werden behandelt.

Ein Workflow definiert, wie mit einem Anruf ab dem Läuten des Telefons bis zur Annahme des Anrufs verfahren wird. Der Workflow gibt die Warteschlange an, die zum Halten des Anrufs verwendet werden soll, und gibt die Routingmethode an, die für Sammelgruppenworkflows verwendet werden soll, oder die Fragen und Antworten, die für interaktive Reaktionsgruppeworkflows verwendet werden.

Ein Workflow definiert außerdem Einstellungen wie die Willkommensnachricht, Wartemusik, Geschäftszeiten und Feiertage.

> [!NOTE]
> Vor dem Erstellen eines Workflows müssen Sie zuerst Agentgruppen und Warteschleifen erstellen, die vom Workflow verwendet werden sollen.

## <a name="creating-or-modifying-a-hunt-group-workflow"></a>Erstellen oder Ändern eines Sammelaktionsworkflows

### <a name="to-use-response-group-configuration-tool-to-create-or-modify-a-hunt-group-workflow"></a>So verwenden Sie das Reaktionsgruppe-Konfigurationstool zum Erstellen oder Ändern eines Sammelgruppenworkflows

1. Melden Sie sich als Mitglied der Gruppe RTCUniversalServerAdmins oder als Mitglied einer der vordefinierten Administrativen Rollen an, die die Reaktionsgruppe unterstützen.

2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen.

3. Klicken Sie in der linken Navigationsleiste auf **Reaktionsgruppen** und dann auf **Workflow**.

4. Klicken Sie auf der Seite **Workflow** auf **Workflow erstellen oder bearbeiten**.

5. Geben Sie im Suchfeld **Dienst auswählen** einen Teil oder den vollständigen Namen des **ApplicationServer**-Diensts ein, von dem der Workflow gehostet wird, den Sie erstellen oder ändern möchten. Klicken Sie in der Dienstliste auf den gewünschten Dienst, und klicken Sie dann auf **OK**.

    > [!NOTE]
    > Das Reaktionsgruppe-Konfigurationstool wird geöffnet. Sie können das Reaktionsgruppeskonfigurationstool auch direkt über einen Webbrowser öffnen, indem Sie die folgende URL eingeben: https:// \<webPoolFqdn\> /RgsConfig.

6. Führen Sie einen der folgenden Schritte aus:

   - Klicken Sie unterhalb von **Neuen Workflow erstellen** neben **Sammelanschluss** auf **Erstellen**.

   - Suchen Sie unter **Vorhandenen Workflow verwalten** nach dem Workflow, den Sie ändern möchten, und klicken Sie anschließend unter **Aktion** auf **Bearbeiten**.

7. Falls Benutzer den Workflow bereits verwenden können, aktivieren Sie das Kontrollkästchen **Workflow aktivieren**.

    > [!NOTE]
    >  Wenn Sie einen verwalteten Workflow erstellen, müssen Sie den **Workflow aktivieren auswählen.** Nachdem Sie den aktiven, verwalteten Workflow gespeichert haben, können Sie ihn ändern und deaktivieren.

8. Aktivieren Sie das Kontrollkästchen **Für Partnerverbund aktivieren**, um Partnerbenutzern Anrufe bei der Gruppe zu ermöglichen. Sie müssen auch über eine Richtlinie für den externen Zugriff verfügen, die für die Reaktionsgruppeanwendung gilt, die für den Verbund konfiguriert ist.

    > [!NOTE]
    > Die globale Richtlinie für den externen Zugriff gilt für die Reaktionsgruppeanwendung. Sie können die globale Richtlinie für den Verbund von Reaktionsgruppen mithilfe der Skype for Business Server-Systemsteuerung oder mithilfe des **Cmdlets Set-CsExternalAccessPolicy** konfigurieren, um den Parameter EnableOutsideAccess auf True zu setzen. Bedenken Sie, dass globale Richtlinieneinstellungen für alle Benutzer gelten, es sei denn, sie sind einer standort- oder benutzerspezifischen Richtlinie zugeordnet. Stellen Sie daher vor dem Ändern dieser Einstellung für Reaktionsgruppen sicher, dass die Verbundeinstellung die Anforderungen Ihrer Organisation erfüllt. Ausführliche Informationen dazu, wie Richtlinien auf Benutzer angewendet werden, finden Sie unter [Manage External Access Policy for Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-manage-external-access-policy-for-your-organization). Weitere Informationen zur Verbundeinstellung finden Sie unter [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy?view=skype-ps).

    > [!NOTE]
    > Benutzer, die in Skype for Business Online gehostet werden, können keine Anrufe an Reaktionsgruppen führen, die in einer lokalen Bereitstellung gehostet werden. Dies gilt sowohl für Hybridbereitstellungen als auch für Fälle, in denen eine lokale Bereitstellung mit einer Skype for Business Online-Bereitstellung in Verbindung steht.

9. Aktivieren Sie das Kontrollkästchen **Anonymität für Agents aktivieren**, um bei Anrufen die Identität der Agents zu verbergen.

    > [!NOTE]
    > Anonyme Anrufe können nicht mit Chat oder Video beginnen, obwohl der Agent oder der Anrufer Chatnachrichten und Video hinzufügen kann, nachdem der Anruf eingerichtet wurde. Ein anonymer Agent kann anrufe auch zurückhalten, Anrufe übertragen (blinde und konsultative Übertragungen) und Anrufe parken und abrufen. Anonyme Anrufe unterstützen keine Konferenzen, Anwendungsfreigabe und Desktopfreigabe, Dateiübertragung, Whiteboarding und Datenzusammenarbeit sowie Anrufaufzeichnungen. Agents, die das Lync VDI-Plug-In verwenden, können eingehende Anrufe anonym empfangen, aber sie können keine ausgehenden Anrufe anonym entgegen nehmen.

10. Geben Sie im Feld **Geben Sie die Adresse der Gruppe ein, die die Anrufe entgegennimmt** den primären SIP-URI (Uniform Resource Identifier) der Gruppe ein, die die Anrufe beim Workflow erhalten soll.

    > [!NOTE]
    > Über den primären URI für einen Workflow wird der Workflow identifiziert. Der von Ihnen eingebende SIP-URI wird als Kontaktobjekt in Active Directory Domain Services erstellt. Zum Erstellen des URI muss das Objekt in Active Directory eindeutig sein.

11. Geben **Sie unter** Anzeigename den Namen ein, den Sie für den Workflow anzeigen möchten (z. B. Sales Response Group).

    > [!NOTE]
    > Verwenden Sie im Anzeigenamen nicht die Zeichen "<" oder ">". Die folgenden Anzeigenamen sind reserviert und dürfen nicht verwendet werden: **RGS-Anwesenheitsmonitor** oder **Ankündigungsdienst**.

12. Geben Sie unter **Telefonnummer** den Anschluss-URI für die Reaktionsgruppe ein (z. B. +14255550165).

13. Geben Sie in **Anzeigenummer** die Nummer ein, wie sie für die Reaktionsgruppe angezeigt werden soll (z. B. +1 (425) 555-0165).

14. (Optional) Geben **Sie** unter Beschreibung eine Beschreibung für den Workflow ein, wie er auf der Visitenkarte in Skype for Business angezeigt werden soll.

15. Wählen Sie unter **Workflowtyp** die Option **Verwaltet** aus, falls dieser Workflow von einem Reaktionsgruppenmanager verwaltet wird. Gehen Sie wie folgt vor, um dem Workflow Reaktionsgruppenmanager zuzuordnen:

    a. Geben Sie den SIP-URI eines Managers für diesen Workflow ein, und klicken Sie auf **Hinzufügen**.

    b. Geben Sie den SIP-URI zusätzlicher Manager für den Workflow ein, und klicken Sie auf **Hinzufügen**.

    > [!IMPORTANT]
    > Jedem Benutzer, der als Manager einer Reaktionsgruppe bestimmt wurde, muss die Rolle CsResponseGroupManager zugewiesen sein. Falls Benutzern diese Rolle nicht zugewiesen ist, können sie keine Reaktionsgruppen verwalten.

16. Klicken Sie unter **Schritt 2: Sprache auswählen** auf die Sprache, die für die Spracherkennung und Text-zu-Sprache verwendet werden soll.

17. Aktivieren Sie zum Konfigurieren einer Willkommensnachricht unter **Schritt 3: Willkommensnachricht konfigurieren** das Kontrollkästchen **Willkommensnachricht wiedergeben**, und führen Sie eine der folgenden Aktionen aus:

    - Um die Willkommensnachricht als Text einzugeben, die für Anrufer in Sprache umgewandelt wird, klicken Sie auf **Text-zu-Sprache verwenden** und geben die Willkommensnachricht in das Textfeld ein.

    > [!NOTE]
    > Verwenden Sie im eingegebenen Text keine HTML-Tags. Andernfalls wird eine Fehlermeldung angezeigt.

    - Um eine aufgezeichnete WAV- (Wave) oder WMA-Datei (Windows Media Audio) für die Willkommensnachricht zu verwenden, klicken Sie auf **Auswählen einer Aufzeichnung**. Klicken Sie auf den Link **Aufzeichnung**, um eine neue Audiodatei hochzuladen. Klicken Sie im neuen Browserfenster auf **Durchsuchen**, markieren Sie die gewünschte Audiodatei, und klicken Sie dann auf **Öffnen**. Klicken Sie auf **Hochladen**, um die Datei zu laden.

    > [!NOTE]
    > Alle von Benutzern bereitgestellten Audiodateien müssen bestimmte Anforderungen erfüllen. Ausführliche Informationen zu den unterstützten Dateiformaten finden Sie unter [Technical Requirements for Response Groups](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group).

18. Klicken Sie unter **Schritt 4: Geschäftszeiten angeben** im Feld **Ihre Zeitzone** auf die Zeitzone des Workflows.

    > [!NOTE]
    > Dies ist die Zeitzone, in der sich die Anrufer und Agents des Workflows befinden. Die Angabe wird verwendet, um die Öffnungszeiten zu berechnen. Wenn der Workflow z. B. für die mitteleuropäische Zeit konfiguriert wurde und der Workflow um 7:00 Uhr öffnen und um 23:00 Uhr schließen soll, werden die Zeiten 7:00 Uhr MEZ und 23:00 Uhr MEZ verwendet. (Die Zeiten müssen im 24-Stunden-Format eingegeben werden.)

19. Sie haben folgende Möglichkeiten, um die gewünschten Geschäftszeiten anzugeben:

    - Wenn Sie einen vordefinierten Zeitplan für die Geschäftszeiten verwenden möchten, klicken Sie auf **Verwenden eines vordefinierten Zeitplans**, und wählen Sie den gewünschten Zeitplan in der Dropdownliste aus.

      > [!NOTE]
      > Sie müssen mindestens einen vordefinierten Zeitplan erstellt haben, um diese Option auswählen zu können. Sie erstellen vordefinierte Zeitpläne mit dem Cmdlet **New-CSRgsHoursOfBusiness**. Weitere Informationen finden Sie unter [(Optional) Define Response Group business hours in Skype for Business](optional-define-response-group-business-hours.md).

      > [!NOTE]
      > Wenn Sie einen vordefinierten Zeitplan verwenden, werden die Werte für **Tag**, **Öffnen** und **Schließen**, an denen die Reaktionsgruppe verfügbar ist, automatisch eingetragen.

    - Klicken Sie auf **Verwenden eines benutzerdefinierten Zeitplans**, um einen benutzerdefinierten Zeitplan zu erstellen, der nur für diesen Workflow gilt.

20. Wenn Sie einen benutzerdefinierten Zeitplan für diesen Workflow erstellen, aktivieren Sie die Kontrollkästchen für die Wochentage, an denen die Reaktionsgruppe verfügbar ist.

21. Wenn Sie einen benutzerdefinierten Zeitplan  erstellen, geben Sie die Stunden **"Öffnen"** und "Schließen" für jeden Wochentag ein, an dem die Reaktionsgruppe verfügbar ist.

    > [!NOTE]
    > Die Werte für **Öffnen** und **Schließen** müssen im 24-Stunden-Format angegeben werden. Wenn Ihr Büro z. B. von 9 Uhr bis 17 Uhr geöffnet und mittags geschlossen ist, können Sie die Geschäftszeiten als **Öffnen** 9:00, **Schließen** 12:00, **Öffnen** 13:00 und **Schließen** 17:00 angeben.

22. Wenn Sie eine Nachricht wiedergeben möchten, wenn das Büro geschlossen ist, aktivieren Sie das Kontrollkästchen **Wiedergabe einer Nachricht, wenn sich die Reaktionsgruppe außerhalb der Geschäftszeiten befindet**, und geben Sie die Nachricht ein, indem Sie eine der folgenden Aktionen ausführen:

    - Um die Nachricht als Text einzugeben, die für Anrufer in Sprache umgewandelt wird, klicken Sie auf **Text-zu-Sprache verwenden** und geben die Nachricht in das Textfeld ein.

      > [!NOTE]
      > Verwenden Sie im eingegebenen Text keine HTML-Tags. Andernfalls wird eine Fehlermeldung angezeigt.

    - Um eine aufgezeichnete Audiodatei als Nachricht zu verwenden, klicken Sie auf **Auswählen einer Aufzeichnung**. Klicken Sie auf den Link **Aufzeichnung**, um eine neue Audiodatei hochzuladen. Klicken Sie im neuen Browserfenster auf **Durchsuchen**, markieren Sie die gewünschte Datei, und klicken Sie auf **Öffnen**. Klicken Sie auf **Hochladen**, um die Datei zu laden.

      > [!NOTE]
      > Alle von Benutzern bereitgestellten Audiodateien müssen bestimmte Anforderungen erfüllen. Ausführliche Informationen zu den unterstützten Audiodateiformaten finden Sie unter [Technical Requirements for Response Groups](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group).

23. Geben Sie an, wie nach Wiedergabe der Nachricht verfahren werden soll (sofern eine Nachricht konfiguriert wurde):

    - Klicken Sie auf **Verbindung trennen**, um die Verbindung zu trennen.

    - Um den Anruf an ein Voicemailsystem weiterzuleiten, klicken Sie auf **An Voicemail weiterleiten** und geben die Voicemailadresse ein. Das Format für die Voicemailadresse ist *\<username\>* @ *\<domainName\>* (z. B. bob@contoso.com).

    - Um den Anruf an einen anderen Benutzer weiterzuleiten, klicken Sie auf **An SIP-URI weiterleiten** und geben die Adresse eines Benutzers ein. Das Format für die Benutzeradresse ist _\<username\>_ @ _\<domainName\>_ .

    - Um den Anruf an eine andere Telefonnummer weiterzuleiten, klicken Sie auf **An Telefonnummer weiterleiten** und geben die Telefonnummer ein. Das Format für die Telefonnummer ist *\<number\>* @ *\<domainName\>* (z. B. +14255550121@contoso.com). Der Domänenname wird verwendet, um den Anrufer an das richtige Ziel weiterzuleiten.

24. Aktivieren Sie unter **Schritt 5: Feiertage angeben** die Kontrollkästchen für einen oder mehrere Feiertagssätze, mit denen die Tage definiert werden, an denen die Reaktionsgruppe aufgrund eines Feiertags nicht verfügbar ist.

    > [!NOTE]
    > Sie müssen die für Sie geltenden Feiertage und Feiertagssätze definieren, bevor Sie den Workflow konfigurieren. Verwenden Sie zum Definieren von Feiertagen und Feiertagssätzen die Cmdlets **New-CsRgsHoliday** und **New-CsRgsHolidaySet**. Weitere Informationen finden Sie unter [(Optional) Define Response Group holiday sets in Skype for Business](optional-define-response-group-holiday-sets.md).

25. Wenn Sie an Feiertagen eine Nachricht wiedergeben möchten, aktivieren Sie das Kontrollkästchen **Wiedergabe einer Nachricht an Feiertagen**, und geben Sie die Nachricht an, indem Sie eine der folgenden Aktionen ausführen:

    - Um die Nachricht als Text einzugeben, die für Anrufer in Sprache umgewandelt wird, klicken Sie auf **Text-zu-Sprache verwenden** und geben die Nachricht in das Textfeld ein.

    > [!NOTE]
    > Verwenden Sie im eingegebenen Text keine HTML-Tags. Andernfalls wird eine Fehlermeldung angezeigt.

    - Um eine aufgezeichnete Audiodatei als Nachricht zu verwenden, klicken Sie auf **Auswählen einer Aufzeichnung**. Klicken Sie auf den Link **Aufzeichnung**, um eine neue Audiodatei hochzuladen. Klicken Sie im neuen Browserfenster auf **Durchsuchen**, markieren Sie die gewünschte Datei, und klicken Sie auf **Öffnen**. Klicken Sie auf **Hochladen**, um die Datei zu laden.

      > [!NOTE]
      > Alle von Benutzern bereitgestellten Audiodateien müssen bestimmte Anforderungen erfüllen. Ausführliche Informationen zu den unterstützten Audiodateiformaten finden Sie unter [Technical Requirements for Response Groups](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group).

26. Geben Sie an, wie nach Wiedergabe der Nachricht verfahren werden soll (sofern eine Nachricht konfiguriert wurde):

    - Klicken Sie auf **Verbindung trennen**, um die Verbindung zu trennen.

    - Um den Anruf an ein Voicemailsystem weiterzuleiten, klicken Sie auf **An Voicemail weiterleiten** und geben die Voicemailadresse ein. Das Format für die Voicemailadresse ist *\<username\>* @ *\<domainName\>* (z. B. bob@contoso.com).

    - Um den Anruf an einen anderen Benutzer weiterzuleiten, klicken Sie auf **An SIP-URI weiterleiten** und geben die Adresse eines Benutzers ein. Das Format für die Benutzeradresse ist _\<username\>_ @ _\<domainName\>_ .

    - Um den Anruf an eine andere Telefonnummer weiterzuleiten, klicken Sie auf **An Telefonnummer weiterleiten** und geben die Telefonnummer ein. Das Format für die Telefonnummer ist *\<number\>* @ *\<domainName\>* (z. B. +14255550121@contoso.com). Der Domänenname wird verwendet, um den Anrufer an das richtige Ziel weiterzuleiten.

27. Wählen Sie unter **Schritt 6: Warteschleife konfigurieren** im Feld **Warteschleife für Anrufe auswählen** die Warteschleife aus, in der die Anrufer gehalten werden, bis ein Agent verfügbar wird.

28. Wählen Sie unter **Schritt 7: Wartemusik konfigurieren** aus, welche Musik Anrufer beim Warten auf einen Agent hören sollen, indem Sie einen der folgenden Schritte ausführen:

    - Klicken Sie auf **Standard verwenden**, um die Standardwartemusik zu verwenden.

    - Klicken Sie auf **Auswählen einer Musikdatei**, um eine aufgezeichnete Audiodatei als Wartemusik zu verwenden. Klicken Sie auf den Link **Musikdatei**, um eine neue Audiodatei hochzuladen. Klicken Sie im neuen Browserfenster auf **Durchsuchen**, markieren Sie die gewünschte Datei, und klicken Sie auf **Öffnen**. Klicken Sie auf **Hochladen**, um die Datei zu laden.

      > [!NOTE]
      > Alle von Benutzern bereitgestellten Audiodateien müssen bestimmte Anforderungen erfüllen. Ausführliche Informationen zu den unterstützten Audiodateiformaten finden Sie unter [Technical Requirements for Response Groups](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group).

29. Klicken Sie auf **Bereitstellen**.

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-hunt-group-workflow"></a>So verwenden Sie die Skype for Business Server-Verwaltungsshell zum Erstellen oder Ändern eines Sammelsuchenworkflows

1. Melden Sie sich als Mitglied der Gruppe RTCUniversalServerAdmins oder als Mitglied einer der vordefinierten Administrativen Rollen an, die die Reaktionsgruppe unterstützen.

2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start,** klicken Sie auf **Alle Programme,** **klicken Sie auf Skype for Business 2015,** und klicken Sie dann auf **Skype for Business Server Management Shell**.

3. Erstellen Sie die Ansage, die als Willkommensnachricht abgespielt werden soll, und speichern Sie sie in einer Variablen. Führen Sie an der Befehlszeile folgenden Befehl aus:

   ```powershell
   $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

    Beispiel:

   ```powershell
   $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "Welcome to Contoso. Please wait for an available agent."
   ```

     > [!NOTE]
     > Verwenden Sie das Cmdlet **Import-CsRgsAudioFile**, um eine Audiodatei für die Ansage zu verwenden. Weitere Informationen finden Sie unter [Import-CsRgsAudioFile](/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).

4. Rufen Sie die Identität der Warteschleife oder Frage ab, an die die Anrufe weitergeleitet werden. Führen Sie an der Befehlszeile folgenden Befehl aus:

   ```powershell
   $qid = (Get-CsRgsQueue -Name "Help Desk").Identity
   ```

    Weitere Informationen zum Erstellen der Warteschlange finden Sie unter [New-CsRgsQueue](/powershell/module/skype/new-csrgsqueue?view=skype-ps).

5. Definieren Sie die durchzuführende Standardaktion, wenn ein Workflow während der Geschäftszeiten geöffnet wird, und speichern Sie sie in einer Variablen. Führen Sie an der Befehlszeile folgenden Befehl aus:

   ```powershell
   $actionWM = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken> -QueueID $qid
   ```

    > [!NOTE]
    > Bei Sammelaufrufworkflows muss die Standardaktion den Aufruf an eine Warteschlange weiterveranten. Dieser Parameter ist für aktive Workflows erforderlich. Sie ist für inaktive Workflows nicht erforderlich.

    Beispiel:

   ```powershell
   $actionWM = New-CsRgsCallAction -Prompt $promptWM -Action TransferToQueue -QueueID $qid.Identity
   ```

6. Wenn Sie Geschäftszeiten und Feiertage definieren möchten, müssen Sie diese erstellen, bevor Sie den Workflow erstellen oder ändern. Weitere Informationen finden Sie unter [(Optional) Definieren](optional-define-response-group-business-hours.md) von Geschäftszeiten der Reaktionsgruppe in Skype for Business und [(Optional) Definieren](optional-define-response-group-holiday-sets.md)von Feiertagssätzen für Reaktionsgruppe in Skype for Business .

7. Wenn Sie Ansagen für Anrufe wünschen, die außerhalb der Geschäftszeiten oder an Feiertagen empfangen werden, definieren Sie die Ansage mithilfe des **New-CsRgsPrompt**-Cmdlets, und definieren Sie mithilfe des **New-CsRgsCallAction**-Cmdlets die Aktion, die im Anschluss an die Ansage ausgeführt werden soll. Weitere Informationen finden Sie unter [New-CsRgsPrompt](/powershell/module/skype/new-csrgsprompt?view=skype-ps) und [New-CsRgsCallAction](/powershell/module/skype/new-csrgscallaction?view=skype-ps).

8. Rufen Sie den Dienstnamen für den Lync Server-Reaktionsgruppesdienst ab, und weisen Sie ihn einer Variablen zu. Führen Sie an der Befehlszeile folgenden Befehl aus:

   ```powershell
   $serviceId = "service:" + (Get-CsService | ?{$_.Applications -like "*RGS*"}).ServiceId;
   ```

9. Erstellen oder ändern Sie den Workflow. Verwenden Sie das **New-CsRgsWorkflow**-Cmdlet zum Erstellen eines Workflows. Verwenden Sie das **Set-CsRgsWorkflow**-Cmdlet zum Ändern eines Workflows. Geben Sie in die Befehlszeile Folgendes ein:

   ```powershell
   $workflowHG = New-CsRgsWorkflow -Parent <service ID for the Response Group service> -Name "<hunt group name>" [-Description "<hunt group description>"] -PrimaryUri "<SIP address for the workflow>" [-LineUri "<Phone number for the workflow>"] [-DisplayNumber "<Phone number displayed in Lync>"] [-Active <$true | $false>] [-Anonymous <$true | $false>] [-DefaultAction <variable from preceding step>] [-EnabledForFederation <$true | $false>] [-Managed <$true | $false>] [-ManagersByUri <SIP addresses for Response Group Managers who can manage the workflow>]
   ```

    Beispiel:

   ```powershell
   $workflowHG = New-CsRgsWorkflow -Parent $serviceID -Name "Human Resources" -Description "Human Resources workflow" -PrimaryUri "sip:humanresources@contoso.com" -LineUri "TEL:+14255551219" -DisplayNumber "555-1219" -Active $true -Anonymous $true -DefaultAction $actionWM -EnabledForFederation $false -Managed $true -ManagersByUri "sip:bob@contoso.com", "mindy@contoso.com"
   ```

     > [!IMPORTANT]
     > Allen Benutzer, die designierte Workflowmanager sind, muss die Rolle CsResponseGroupManager zugewiesen werden.

     > [!NOTE]
     > Weitere Informationen zu zusätzlichen optionalen Parametern finden Sie unter [New-CsRgsWorkflow](/powershell/module/skype/new-csrgsworkflow?view=skype-ps) oder [Set-CsRgsWorkflow.](/powershell/module/skype/set-csrgsworkflow?view=skype-ps)

## <a name="designing-an-interactive-workflow"></a>Entwerfen eines interaktiven Workflows

Sie können die interaktive Sprachantwort (Interactive Voice Response, IVR) verwenden, um Informationen von Anrufern zu erhalten und den Anruf an die entsprechende Warteschlange weiter zu senden. Frage-Antwort-Paare bestimmen, welche Warteschlange verwendet werden soll. Je nach Antwort des Anrufers hört der Anrufer entweder eine Folgefrage oder wird an die entsprechende Warteschlange geroutet. Die IVR-Fragen und die Antworten des Anrufers werden dem antwortenden Agent zur Verfügung gestellt, der den Anruf annimmt und dem Agent wertvolle Informationen zur Verfügung stellt.

### <a name="overview-of-ivr-features"></a>Übersicht über IVR-Features

Die Reaktionsgruppe bietet Spracherkennung und Text-zu-Sprache-Funktionen in 26 Sprachen. Sie können IVR-Fragen mithilfe von Text-zu-Sprache oder einer Welle (WAV) oder Windows Media-Audiodatei (WMA) eingeben. Anrufer können mit Sprach- oder DTMF-Antworten (Dual-Tone MultiFrequency) antworten.

Interaktive Workflows unterstützen bis zu zwei Ebenen von Fragen, bei der jede Frage bis zu vier mögliche Antworten hat. Die IVR stellt dem Anrufer eine Frage und leitet den Anrufer je nach Antwort des Anrufers an eine Warteschleife weiter oder stellt eine zweite Frage. Die zweite Frage kann auch vier mögliche Antworten haben. Abhängig von der Antwort auf die Frage der zweiten Ebene wird der Anrufer an die entsprechende Warteschlange geroutet.

> [!NOTE]
> Wenn Sie Anrufflüsse mithilfe der Skype for Business Server-Verwaltungsshell entwerfen, können Sie eine beliebige Anzahl von Ebenen von IVR-Fragen und eine beliebige Anzahl von Antworten definieren. Für die Benutzerfreundlichkeit von Anrufern wird jedoch empfohlen, nicht mehr als drei Fragenebenen mit jeweils nicht mehr als fünf Antworten zu verwenden. Wenn Sie darüber hinaus einen Anruffluss mit mehr als zwei Fragenebenen mit jeweils mehr als vier Antworten entwerfen, können Sie den Anruffluss nicht mithilfe der Skype for Business Server-Systemsteuerung bearbeiten.

Die IVR-Fragen und die Antworten des Anrufers werden dem antwortenden Agent bereitgestellt, der den Anruf annimmt.

### <a name="working-with-speech-technologies"></a>Arbeiten mit Sprachtechnologien

Sprachtechnologien, z. B. Spracherkennung und Text-zu-Sprache, können die Benutzererfahrung verbessern und den Zugriff auf Informationen natürlicher und effektiver ermöglichen. Es kann jedoch Fälle geben, in denen der angegebene Text oder die Benutzerstimmenantwort vom Sprachmodul nicht richtig erkannt wird. Das Symbol "#" wird beispielsweise vom Text-zu-Sprache-Modul als Wort "Zahl" übersetzt. Dieses Problem kann wie folgt behoben werden:

- Das Sprachmodul gibt dem Anrufer fünf Versuche, die Frage zu beantworten. Wenn der Anrufer die Frage falsch beantwortet (d. h., die Antwort ist keine der angegebenen Antworten) oder überhaupt keine Antwort gibt, erhält der Anrufer eine weitere Möglichkeit, die Frage zu beantworten. Der Anrufer hat fünf Versuche, die Frage zu beantworten, bevor er getrennt wird. Sie können die IVR so konfigurieren, dass nach jedem Aufruferfehler eine angepasste Nachricht wieder angezeigt wird. Die Frage wird jedes Mal wiederholt.

- Verwenden Sie längere Antworten, um das Risiko zu minimieren, dass Umgebungsgeräusche vom Sprachmodul als Antwort interpretiert werden. Beispielsweise sollten Antworten mehr als eine Silbe haben und sich deutlich voneinander unterscheiden.

- Wenn Ihre Fragen sowohl Sprach- als auch DTMF-Antworten haben, konfigurieren Sie die Sprachantworten mit Wörtern, die das Konzept und nicht die DTMF-Antwort darstellen. Verwenden Sie z. B. anstelle von "Drücken oder Sagen" "1 drücken oder Abrechnung sagen".

- Rufen Sie nach dem Entwerfen der IVR den Workflow auf, lauschen Sie den Eingabeaufforderungen, beantworten Sie die einzelnen Eingabeaufforderungen mithilfe von Voice, und überprüfen Sie, ob die IVR wie erwartet klingt und verhält. Anschließend können Sie die IVR ändern, um alle Interpretationsprobleme zu beheben. Wenn Sie im vorherigen Beispiel auf die #-Taste verweisen müssen, können Sie Ihre #A0 umschreiben, um den Schlüsselnamen anstelle des #-Symbols zu verwenden. Beispiel: "Drücken Sie zum Sprechen mit dem Vertrieb die Taste für das Pfund."

### <a name="ivr-design-examples"></a>IVR-Entwurfsbeispiele

Die folgenden Abschnitte enthalten Beispiele für verschiedene IVR-Szenarien und Frage-und-Antwort-Paare.

#### <a name="ivr-with-one-level-of-questions"></a>IVR mit einer Ebene von Fragen

Das folgende Beispiel zeigt eine IVR, die eine Frageebene verwendet. Die Spracherkennung wird verwendet, um die Antwort des Anrufers zu erkennen.

 **Frage:** "Vielen Dank für den Aufruf von Personal. Wenn Sie mit der Gehaltsabrechnung sprechen möchten, sagen Sie Gehaltsabrechnung. Sagen Sie andernfalls HR."

- **Option 1 ist ausgewählt:** Der Anrufer wird an das Gehaltsabrechnungsteam geroutet.

- **Option 2 ist ausgewählt:** Der Anrufer wird an das Personalteam geroutet.

Die folgende Abbildung zeigt den Anruffluss.

 **Interaktiver Anruffluss auf einer Ebene**

![Entwerfen von Anrufflüssen mithilfe von Interactive Voice Respo](../../media/Ops_OCS_RGS_IVRLevel1.jpg)

#### <a name="ivr-with-two-levels-of-questions"></a>IVR mit zwei Ebenen von Fragen

Das folgende Beispiel zeigt eine IVR, die zwei Ebenen von Fragen verwendet. Es ermöglicht Anrufern, entweder über sprach- oder DTMF-Tastatureingaben zu antworten.

 **Frage:** "Vielen Dank, dass Sie den IT-Helpdesk anrufen. Wenn Sie ein Netzwerkzugriffsproblem haben, drücken Sie 1, oder sagen Sie Netzwerk. Wenn Sie ein Softwareproblem haben, drücken Sie 2 oder sagen Sie Software. Wenn Sie ein Hardwareproblem haben, drücken Sie 3, oder sagen Sie Hardware."

- **Option 1 ist ausgewählt:** Der Anrufer wird an das Netzwerksupportteam geroutet.

- **Option 2 ist ausgewählt:** Dem Anrufer wird eine Follow-up-Frage gestellt:

    **Frage:** "Wenn es sich um ein Betriebssystemproblem handelt, drücken Sie 1, oder sagen Sie Betriebssystem. Wenn dies ein Problem mit einer internen Anwendung ist, drücken Sie 2, oder sagen Sie interne Anwendung. Drücken Sie andernfalls 3, oder sagen Sie eine andere."

  - **Option 1 ist ausgewählt:** Der Anrufer wird an das Betriebssystemunterstützungsteam geroutet.

  - **Option 2 ist ausgewählt:** Der Anrufer wird an das Supportteam für interne Anwendungen geroutet.

  - **Option 3 ist ausgewählt:** Der Anrufer wird an das Softwaresupportteam geroutet.

- **Option 3 ist ausgewählt:** Dem Anrufer wird eine Follow-up-Frage gestellt:

    **Frage:** "Wenn es sich um ein Druckerproblem handelt, drücken Sie 1. Drücken Sie andernfalls 2."

  - **Option 1 ist ausgewählt:** Der Anrufer wird an das Druckerunterstützungsteam geroutet.

  - **Option 2 ist ausgewählt:** Der Anrufer wird an das Hardwaresupportteam geroutet.

Die folgende Abbildung zeigt den Anruffluss.

 **Interaktiver Anruffluss auf zwei Ebenen**

![Entwerfen von Anrufflüssen mithilfe von Interactive Voice Respo](../../media/Ops_OCS_RGS_IVRLevel2.jpg)

### <a name="best-practices"></a>Bewährte Methoden

In der folgenden Liste werden einige bewährte Methoden für das Entwerfen ihrer IVR beschrieben:

- Lassen Sie den Anrufer schnell zur Aufgabe kommen. Vermeiden Sie zu viele Informationen oder langwierige Marketingnachrichten in Ihrer IVR.

- Wenn Sie eine lange Nachricht hinzufügen möchten, sollten Sie sie an die erste Frage anstatt an die Willkommensnachricht anhängen. Anrufer können die Nachricht umgehen, wenn sie Teil der ersten Frage ist, indem sie die Frage beantworten, aber sie können die Willkommensnachricht nicht umgehen.

- Sprechen Sie in der Sprache des Anrufers. Vermeiden Sie stilierte Sprache. Sprechen Sie natürlich.

- Effiziente und effektive Eingabeaufforderungen schreiben. Entfernen Sie alle unnötigen Optionen. Strukturieren Sie die Informationen so, dass die erwartete Antwort des Anrufers am Ende des Satzes liegt. Beispiel: "Drücken Sie 1, um mit dem Vertriebsteam zu sprechen."

- Gestalten Sie Sprachantworten benutzerfreundlich. Wenn Sie z. B. DTMF- und Sprachantworten angeben, verwenden Sie etwa: "Wenn Sie mit dem Vertriebsteam sprechen möchten, drücken Sie 1, oder sagen Sie".

- Testen Sie die IVR für eine Gruppe von Benutzern, bevor Sie sie in Ihrer Organisation bereitstellen.

## <a name="creating-or-modifying-an-interactive-workflow"></a>Erstellen oder Ändern eines interaktiven Workflows

### <a name="to-use-response-group-configuration-tool-to-create-or-modify-an-interactive-workflow"></a>So verwenden Sie das Reaktionsgruppe-Konfigurationstool zum Erstellen oder Ändern eines interaktiven Workflows

1. Melden Sie sich als Mitglied der Gruppe RTCUniversalServerAdmins oder als Mitglied einer der vordefinierten Administrativen Rollen an, die die Reaktionsgruppe unterstützen.

2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen.

3. Klicken Sie in der linken Navigationsleiste auf **Reaktionsgruppen** und dann auf **Workflow**.

4. Klicken Sie auf der Seite **Workflow** auf **Workflow erstellen oder bearbeiten**.

5. Geben Sie **im Suchfeld** Dienst auswählen den Namen des **ApplicationServer-Diensts** ganz oder teilweise ein, der den Workflow hostet, den Sie erstellen oder ändern möchten. Klicken Sie in der Dienstliste auf den gewünschten Dienst, und klicken Sie dann auf **OK**.

    > [!NOTE]
    > Das Reaktionsgruppe-Konfigurationstool wird geöffnet. Sie können das Reaktionsgruppeskonfigurationstool auch direkt über einen Webbrowser öffnen, indem Sie die folgende URL eingeben: https:// \<webPoolFqdn\> /RgsConfig.

6. Führen Sie einen der folgenden Schritte aus:

   - Klicken **Sie unter Erstellen eines neuen Workflows** neben **Interaktiv** auf **Erstellen**.

   - Suchen Sie unter **Vorhandenen Workflow verwalten** nach dem Workflow, den Sie ändern möchten, und klicken Sie anschließend unter **Aktion** auf **Bearbeiten**.

7. Falls Benutzer den Workflow noch nicht aufrufen sollen, müssen Sie das Kontrollkästchen **Workflow aktivieren** deaktivieren.

    > [!NOTE]
    >  Wenn Sie einen verwalteten Workflow erstellen, müssen Sie den **Workflow aktivieren auswählen.** Nachdem Sie den aktiven, verwalteten Workflow gespeichert haben, können Sie ihn ändern und deaktivieren.

8. Aktivieren Sie das Kontrollkästchen **Für Partnerverbund aktivieren**, um Partnerbenutzern Anrufe bei der Gruppe zu ermöglichen. Sie müssen auch über eine Richtlinie für den externen Zugriff verfügen, die für die Reaktionsgruppeanwendung gilt, die für den Verbund konfiguriert ist.

    > [!NOTE]
    > Die globale Richtlinie für den externen Zugriff gilt für die Reaktionsgruppeanwendung. Sie können die globale Richtlinie für den Verbund von Reaktionsgruppen mithilfe der Skype for Business Server-Systemsteuerung oder mithilfe des **Cmdlets Set-CsExternalAccessPolicy** konfigurieren, um den Parameter EnableOutsideAccess auf True zu setzen. Bedenken Sie, dass globale Richtlinieneinstellungen für alle Benutzer gelten, es sei denn, sie sind einer standort- oder benutzerspezifischen Richtlinie zugeordnet. Stellen Sie daher vor dem Ändern dieser Einstellung für Reaktionsgruppen sicher, dass die Verbundeinstellung die Anforderungen Ihrer Organisation erfüllt. Ausführliche Informationen dazu, wie Richtlinien auf Benutzer angewendet werden, finden Sie unter [Manage External Access Policy for Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-manage-external-access-policy-for-your-organization). Ausführliche Informationen zur Verbundeinstellung finden Sie unter **Set-CsExternalAccessPolicy** in der Dokumentation.

    > [!NOTE]
    > Benutzer, die in Skype for Business Online gehostet werden, können keine Anrufe an Reaktionsgruppen führen, die in einer lokalen Bereitstellung gehostet werden. Dies gilt sowohl für Hybridbereitstellungen als auch für Fälle, in denen eine lokale Bereitstellung mit einer Skype for Business Online-Bereitstellung in Verbindung steht.

9. Aktivieren Sie das Kontrollkästchen **Anonymität für Agents aktivieren**, um bei Anrufen die Identität der Agents zu verbergen.

    > [!NOTE]
    > Anonyme Anrufe können nicht mit Chat oder Video beginnen, obwohl der Agent oder der Anrufer Chatnachrichten und Video hinzufügen kann, nachdem der Anruf eingerichtet wurde. Ein anonymer Agent kann anrufe auch zurückhalten, Anrufe übertragen (blinde und konsultative Übertragungen) und Anrufe parken und abrufen. Anonyme Anrufe unterstützen keine Konferenzen, Anwendungsfreigabe und Desktopfreigabe, Dateiübertragung, Whiteboarding und Datenzusammenarbeit sowie Anrufaufzeichnungen. Agents, die das Lync VDI-Plug-In verwenden, können eingehende Anrufe anonym empfangen, aber sie können keine ausgehenden Anrufe anonym entgegen nehmen.

10. Geben Sie im Feld **Geben Sie die Adresse der Gruppe ein, die die Anrufe entgegennimmt** den primären SIP-URI (Uniform Resource Identifier) der Gruppe ein, die die Anrufe beim Workflow erhalten soll.

11. Geben **Sie unter** Anzeigename den Namen ein, den Sie für den Workflow anzeigen möchten (z. B. Sales IVR Response Group).

    > [!NOTE]
    > Fügen Sie die Zeichen " \<" or "\> " nicht in den Anzeigenamen ein. Die folgenden Anzeigenamen sind reserviert und dürfen nicht verwendet werden: **RGS-Anwesenheitsmonitor** oder **Ankündigungsdienst**.

12. Geben Sie unter **Telefonnummer** den Anschluss-URI für die Reaktionsgruppe ein (beispielsweise +14255550165).

13. Geben Sie in **Anzeigenummer** die Nummer ein, wie sie für die Reaktionsgruppe angezeigt werden soll (z. B. +1 (425) 555-0165).

14. (Optional) Geben **Sie unter** Beschreibung eine Beschreibung für den Workflow ein, der auf der Visitenkarte in Skype for Business angezeigt werden soll.

15. Wählen Sie unter **Workflowtyp** die Option **Verwaltet** aus, falls dieser Workflow von einem Reaktionsgruppenmanager verwaltet wird. Gehen Sie wie folgt vor, um dem Workflow Reaktionsgruppenmanager zuzuordnen:

    a. Geben Sie den SIP-URI eines Managers für diesen Workflow ein, und klicken Sie auf **Hinzufügen**.

    b. Geben Sie den SIP-URI zusätzlicher Manager für den Workflow ein, und klicken Sie auf **Hinzufügen**.

    > [!IMPORTANT]
    > Jedem Benutzer, der als Manager einer Reaktionsgruppe bestimmt wurde, muss die Rolle CsResponseGroupManager zugewiesen sein. Falls Benutzern diese Rolle nicht zugewiesen ist, können sie keine Reaktionsgruppen verwalten.

16. Klicken Sie unter **Schritt 2: Sprache auswählen** auf die Sprache, die für die Spracherkennung und die Text-zu-Sprache-Funktion verwendet werden soll.

17. Aktivieren Sie zum Konfigurieren einer Willkommensnachricht unter **Schritt 3: Willkommensnachricht konfigurieren** das Kontrollkästchen **Willkommensnachricht wiedergeben**, und führen Sie eine der folgenden Aktionen aus:

    - Um die Willkommensnachricht als Text einzugeben, die für Anrufer in Sprache umgewandelt wird, klicken Sie auf **Text-zu-Sprache verwenden** und geben die Willkommensnachricht in das Textfeld ein.

    > [!NOTE]
    > Verwenden Sie im eingegebenen Text keine HTML-Tags. Andernfalls wird eine Fehlermeldung angezeigt.

    - Um eine aufgezeichnete WAV- oder WMA-Datei für die Willkommensnachricht zu verwenden, klicken Sie auf **Auswählen einer Aufzeichnung**. Klicken Sie auf den Link **Aufzeichnung**, um eine neue Audiodatei hochzuladen. Klicken Sie im neuen Browserfenster auf **Durchsuchen**, markieren Sie die gewünschte Audiodatei, und klicken Sie dann auf **Öffnen**. Klicken Sie auf **Hochladen**, um die Datei zu laden.

    > [!NOTE]
    > Alle von Benutzern bereitgestellten Audiodateien müssen bestimmte Anforderungen erfüllen. Ausführliche Informationen zu den unterstützten Dateiformaten finden Sie unter [Technical Requirements for Response Groups](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group).

18. Klicken Sie unter **Schritt 4: Geschäftszeiten angeben** im Feld **Ihre Zeitzone** auf die Zeitzone des Workflows.

    > [!NOTE]
    > Dies ist die Zeitzone, in der sich die Anrufer und Agents des Workflows befinden. Die Angabe wird verwendet, um die Öffnungszeiten zu berechnen. Wenn der Workflow beispielsweise für die Verwendung der Zeitzone "North American Eastern" konfiguriert ist und der Workflow um 7:00 Uhr geöffnet werden soll. und schließen um 23:00 Uhr, wird davon ausgegangen, dass die Öffnen- und Schlusszeiten 7:00 Uhr Ostzeit bzw. 11:00 Uhr Ostzeit sind. (Die Zeiten müssen im 24-Stunden-Format eingegeben werden.)

19. Sie haben folgende Möglichkeiten, um die gewünschten Geschäftszeiten anzugeben:

    - Wenn Sie einen vordefinierten Zeitplan für die Geschäftszeiten verwenden möchten, klicken Sie auf **Verwenden eines vordefinierten Zeitplans**, und wählen Sie den gewünschten Zeitplan in der Dropdownliste aus.

      > [!NOTE]
      > Sie müssen mindestens einen vordefinierten Zeitplan erstellt haben, um diese Option auswählen zu können. Sie definieren vordefinierte Zeitpläne mithilfe des **Cmdlets New-CsRgsHoursOfBusiness.** Weitere Informationen finden Sie unter [(Optional) Define Response Group business hours in Skype for Business](optional-define-response-group-business-hours.md). Wenn Sie einen vordefinierten Zeitplan verwenden, werden die Werte für **Tag**, **Öffnen** und **Schließen**, an denen die Reaktionsgruppe verfügbar ist, automatisch eingetragen.

    - Klicken Sie auf **Verwenden eines benutzerdefinierten Zeitplans**, um einen benutzerdefinierten Zeitplan zu erstellen, der nur für diesen Workflow gilt.

20. Wenn Sie einen benutzerdefinierten Zeitplan für diesen Workflow erstellen, aktivieren Sie die Kontrollkästchen für die Wochentage, an denen die Reaktionsgruppe verfügbar ist.

21. Wenn Sie einen benutzerdefinierten Zeitplan  erstellen, geben Sie die Stunden **öffnen** und schließen ein, wenn die Reaktionsgruppe verfügbar ist.

     > [!NOTE]
     > Die Werte für **Öffnen** und **Schließen** müssen im 24-Stunden-Format angegeben werden. Wenn Ihr Büro z. B. von 9 Uhr bis 17 Uhr geöffnet und mittags geschlossen ist, können Sie die Geschäftszeiten als **Öffnen** 9:00, **Schließen** 12:00, **Öffnen** 13:00 und **Schließen** 17:00 angeben.

22. Wenn Sie eine Nachricht wiedergeben möchten, wenn das Büro geschlossen ist, aktivieren Sie das Kontrollkästchen **Wiedergabe einer Nachricht, wenn sich die Reaktionsgruppe außerhalb der Geschäftszeiten befindet**, und geben Sie die Nachricht ein, indem Sie eine der folgenden Aktionen ausführen:

    - Um die Nachricht als Text einzugeben, die für Anrufer in Sprache umgewandelt wird, klicken Sie auf **Text-zu-Sprache verwenden** und geben die Nachricht in das Textfeld ein.

      > [!NOTE]
      > Verwenden Sie im eingegebenen Text keine HTML-Tags. Andernfalls wird eine Fehlermeldung angezeigt.

    - Um eine aufgezeichnete Audiodatei als Nachricht zu verwenden, klicken Sie auf **Auswählen einer Aufzeichnung**. Klicken Sie auf den Link **Aufzeichnung**, um eine neue Audiodatei hochzuladen. Klicken Sie im neuen Browserfenster auf **Durchsuchen**, markieren Sie die gewünschte Datei, und klicken Sie auf **Öffnen**. Klicken Sie auf **Hochladen**, um die Datei zu laden.

    > [!NOTE]
    > Alle von Benutzern bereitgestellten Audiodateien müssen bestimmte Anforderungen erfüllen. Ausführliche Informationen zu den unterstützten Dateiformaten finden Sie unter [Technical Requirements for Response Groups](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group).

23. Geben Sie an, wie nach Wiedergabe der Nachricht verfahren werden soll (sofern eine Nachricht konfiguriert wurde):

    - Klicken Sie auf **Verbindung trennen**, um die Verbindung zu trennen.

    - Um den Anruf an ein Voicemailsystem weiterzuleiten, klicken Sie auf **An Voicemail weiterleiten** und geben die Voicemailadresse ein. Das Format für die Voicemailadresse ist *\<username\>* @ *\<domainname\>* (z. B. bob@contoso.com).

    - Um den Anruf an einen anderen Benutzer weiterzuleiten, klicken Sie auf **An SIP-URI weiterleiten** und geben die Adresse eines Benutzers ein. Das Format für die Benutzeradresse ist _\<username\>_ @ _\<domainname\>_ .

    - Um den Anruf an eine andere Telefonnummer weiterzuleiten, klicken Sie auf **An Telefonnummer weiterleiten** und geben die Telefonnummer ein. Das Format für die Telefonnummer ist *\<number\>* @ *\<domainname\>* (z. B. +14255550121@contoso.com). Der Domänenname wird verwendet, um den Anrufer an das richtige Ziel weiterzuleiten.

24. Aktivieren Sie unter **Schritt 5: Feiertage angeben** die Kontrollkästchen für einen oder mehrere Feiertagssätze, mit denen die Tage definiert werden, an denen die Reaktionsgruppe aufgrund eines Feiertags nicht verfügbar ist.

    > [!NOTE]
    > Sie müssen die für Sie geltenden Feiertage und Feiertagssätze definieren, bevor Sie den Workflow konfigurieren. Verwenden Sie zum Definieren von Feiertagen und Feiertagssätzen die Cmdlets **New-CsRgsHoliday** und **New-CsRgsHolidaySet**. Weitere Informationen finden Sie unter [(Optional) Define Response Group holiday sets in Skype for Business](optional-define-response-group-holiday-sets.md).

25. Wenn Sie an Feiertagen eine Nachricht wiedergeben möchten, aktivieren Sie das Kontrollkästchen **Wiedergabe einer Nachricht an Feiertagen**, und geben Sie die Nachricht an, indem Sie eine der folgenden Aktionen ausführen:

    - Um die Nachricht als Text einzugeben, die für Anrufer in Sprache umgewandelt wird, klicken Sie auf **Text-zu-Sprache verwenden** und geben die Nachricht in das Textfeld ein.

      > [!NOTE]
      > Verwenden Sie im eingegebenen Text keine HTML-Tags. Andernfalls wird eine Fehlermeldung angezeigt.

    - Um eine aufgezeichnete Audiodatei als Nachricht zu verwenden, klicken Sie auf **Auswählen einer Aufzeichnung**. Klicken Sie auf den Link **Aufzeichnung**, um eine neue Audiodatei hochzuladen. Klicken Sie im neuen Browserfenster auf **Durchsuchen**, markieren Sie die gewünschte Datei, und klicken Sie auf **Öffnen**. Klicken Sie auf **Hochladen**, um die Datei zu laden.

      > [!NOTE]
      > Alle von Benutzern bereitgestellten Audiodateien müssen bestimmte Anforderungen erfüllen. Ausführliche Informationen zu den unterstützten Audiodateiformaten finden Sie unter [Technical Requirements for Response Groups](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group).

26. Geben Sie an, wie nach Wiedergabe der Nachricht verfahren werden soll (sofern eine Nachricht konfiguriert wurde):

    - Klicken Sie auf **Verbindung trennen**, um die Verbindung zu trennen.

    - Um den Anruf an ein Voicemailsystem weiterzuleiten, klicken Sie auf **An Voicemail weiterleiten** und geben die Voicemailadresse ein. Das Format für die Voicemailadresse ist *\<username\>* @ *\<domainname\>* (z. B. bob@contoso.com).

    - Um den Anruf an einen anderen Benutzer weiterzuleiten, klicken Sie auf **An SIP-URI weiterleiten** und geben die Adresse eines Benutzers ein. Das Format für die Benutzeradresse ist _\<username\>_ @ _\<domainname\>_ .

    - Um den Anruf an eine andere Telefonnummer weiterzuleiten, klicken Sie auf **An Telefonnummer weiterleiten** und geben die Telefonnummer ein. Das Format für die Telefonnummer ist *\<number\>* @ *\<domainname\>* (z. B. +14255550121@contoso.com). Der Domänenname wird verwendet, um den Anrufer an das richtige Ziel weiterzuleiten.

27. Wählen Sie unter **Schritt 6: Wartemusik konfigurieren** aus, was Anrufer beim Warten auf einen Agent hören sollen, indem Sie eine der folgenden Aktionen ausführen:

    - Klicken Sie auf **Standard verwenden**, um die Standardwartemusik zu verwenden.

    - Klicken Sie auf **Auswählen einer Musikdatei**, um eine aufgezeichnete Audiodatei als Wartemusik zu verwenden. Klicken Sie auf den Link **Musikdatei**, um eine neue Audiodatei hochzuladen. Klicken Sie im neuen Browserfenster auf **Durchsuchen**, markieren Sie die gewünschte Datei, und klicken Sie auf **Öffnen**. Klicken Sie auf **Hochladen**, um die Datei zu laden.

    > [!NOTE]
    > Alle von Benutzern bereitgestellten Audiodateien müssen bestimmte Anforderungen erfüllen. Ausführliche Informationen zu den unterstützten Dateiformaten finden Sie unter [Technical Requirements for Response Groups](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group).

28. Geben Sie in **Schritt 7: Interaktive Sprachantwort (IVR) konfigurieren** unter **Der Benutzer hört den folgenden Text bzw. die folgende aufgezeichnete Nachricht** die Frage ein, die dem Anrufer gestellt wird. Führen Sie hierzu die folgenden Aktionen aus:

    - Um die Frage im Textformat einzugeben, klicken Sie auf **Text-zu-Sprache verwenden** und geben die Frage in das Textfeld ein.

    > [!NOTE]
    > Verwenden Sie im eingegebenen Text keine HTML-Tags. Andernfalls wird eine Fehlermeldung angezeigt.

    > [!NOTE]
    > Das Symbol "#" wird vom Text-zu-Sprache-Modul als das Wort "Nummer" übersetzt. Wenn Sie auf die Taste # verweisen möchten, sollten Sie bei der Eingabe anstelle des Symbols den Tastennamen verwenden. Beispiel: "Drücken Sie zum Sprechen mit dem Vertrieb die Taste für das Pfund."

    - Um eine aufgezeichnete Audiodatei mit der Frage zu verwenden, klicken Sie auf **Auswählen einer Aufzeichnung** und dann auf den Link **Aufzeichnung**, um die Datei hochzuladen. Klicken Sie im neuen Browserfenster auf **Durchsuchen**, markieren Sie die gewünschte Audiodatei, und klicken Sie auf **Öffnen**. Klicken **Sie auf Hochladen,** um die Datei zu laden, und sie können dann optional die Frage in das Textfeld eingeben (dadurch können die Frage und die Antwort des Anrufers an den antwortenden Agent weitergeleitet werden).

      > [!NOTE]
      > Alle von Benutzern bereitgestellten Audiodateien müssen bestimmte Anforderungen erfüllen. Ausführliche Informationen zu den unterstützten Dateiformaten finden Sie unter [Technical Requirements for Response Groups](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group).

29. Geben Sie unter **Antwort 1** wie folgt die erste mögliche Antwort auf die Frage ein:

    > [!IMPORTANT]
    > Verwenden Sie in Sprachantworten keine Anführungszeichen ("). Bei Verwendung von Anführungszeichen funktioniert die interaktive Sprachantwort nicht ordnungsgemäß.

    > [!NOTE]
    > Sie können auswählen, ob Anrufer per Sprache, Tasteneingabe oder beidem antworten können.

    - Wenn Sie zulassen möchten, dass Anrufer per Sprache antworten, geben Sie die Antwort in das Feld **Geben Sie eine Sprachantwort ein** ein.

    - Wenn Sie zulassen möchten, dass Anrufer per Tasteneingabe antworten, klicken Sie im Feld **Ziffer** auf die entsprechende Ziffer.

30. Geben Sie wie folgt an, ob der Anrufer an eine Warteschleife weitergeleitet wird, oder ob eine weitere Frage gestellt werden soll:

    - Um den Anrufer an eine Warteschleife weiterzuleiten, klicken Sie auf **An eine Warteschleife senden**, und klicken Sie unter **Warteschleife auswählen** auf die Warteschleife, die Sie verwenden möchten.

    - Wenn eine weitere Frage gestellt werden soll, klicken Sie auf **Eine weitere Frage stellen**, klicken Sie dann auf **Text-zu-Sprache verwenden**, und geben Sie die Frage ein, oder klicken Sie auf **Auswählen einer Aufzeichnung**. Verwenden Sie die Einstellungen in diesem Abschnitt, um bis zu vier mögliche Antworten auf die zusätzliche Frage sowie die Warteschleife für jede Antwort anzugeben. Um eine dritte oder vierte mögliche Antwort anzugeben, aktivieren Sie das Kontrollkästchen **Antwort 3** oder das Kontrollkästchen **Antwort 4**.

31. Geben Sie bis zu drei weitere mögliche Antworten auf die ursprüngliche Frage ein, indem Sie die Schritte 28 und 29 wiederholen, um mögliche Antworten und die Aktion für jede Antwort anzugeben. Klicken Sie zum Angeben einer dritten oder vierten möglichen Antwort auf das **Kontrollkästchen Antwort 3** oder **Antwort 4.**

32. Klicken Sie auf **Bereitstellen**.

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-an-interactive-workflow"></a>So verwenden Sie die Skype for Business Server-Verwaltungsshell zum Erstellen oder Ändern eines interaktiven Workflows

1.  Melden Sie sich als Mitglied der Gruppe RTCUniversalServerAdmins oder als Mitglied einer der vordefinierten Administrativen Rollen an, die die Reaktionsgruppe unterstützen.

2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start,** klicken Sie auf **Alle Programme,** **klicken Sie auf Skype for Business 2015,** und klicken Sie dann auf **Skype for Business Server Management Shell**.

3. Dienstnamen für den Reaktionsgruppendienst abrufen und diesen einer Variable zuweisen. Führen Sie an der Eingabeaufforderung Folgendes aus:

   ```powershell
   $serviceId = "service:" + (Get-CsService | ?{$_.Applications -like "*RGS*"}).ServiceId;
   ```

4. Ein interaktiver Workflow erfordert zwei oder mehr Warteschlangen und zwei oder mehr Agentgruppen. Erstellen Sie zunächst die Agentgruppen. Führen Sie  aus.

   ```powershell
   $AGSupport = New-CsRgsAgentGroup -Parent $serviceId -Name "Technical Support" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:agent1@contoso.com", "sip:agent2@contoso.com")]
   $AGSales = New-CsRgsAgentGroup -Parent $serviceId -Name "Sales Team" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:bob@contoso.com", "sip:alice@contoso.com")]
   ```

5. Erstellen Sie die Warteschlangen. Führen Sie  aus.

   ```powershell
   $QSupport = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Support" -AgentGroupIDList($AG-Support.Identity)
   $QSales = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Sales" -AgentGroupIDList($AG-Sales.Identity)
   ```

6. Erstellen Sie die erste Eingabeaufforderung für Reaktionsgruppe. Führen Sie  aus.

   ```powershell
   $SupportPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please be patient while we connect you with Contoso Technical Support."
   ```

7. Erstellen Sie dann die Aktion, die nach der Eingabeaufforderung ausgeführt werden soll. Führen Sie  aus.

   ```powershell
   $SupportAction = New-CsRgsCallAction -Prompt $SupportPrompt -Action TransferToQueue -QueueID $QSupport.Identity
   ```

8. Erstellen Sie die erste Antwortgruppe. Führen Sie  aus.

   ```powershell
   $SupportAnswer = New-CsRgsAnswer -Action $SupportAction [-DtmfResponse 1]
   ```

9. Erstellen Sie nun die zweite Eingabeaufforderung, die Anrufaktion und die Antwort. Erstellen Sie zuerst die Eingabeaufforderung. Führen Sie  aus.

   ```powershell
   $SalesPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please hold while we connect you with Contoso Sales."
   ```

10. Erstellen Sie die zweite Aufrufaktion. Führen Sie  aus.

    ```powershell
    $SalesAction = New-CsRgsCallAction -Prompt $SalesPrompt -Action TransferToQueue -QueueID $QSales.Identity
    ```

11. Erstellen Sie die zweite Antwortgruppe. Führen Sie  aus.

    ```powershell
    $SalesAnswer = New-CsRgsAnswer -Action $SalesAction [-DtmfResponse 2]
    ```

12. Erstellen Sie die Eingabeaufforderung auf oberster Ebene. Führen Sie  aus.

    ```powershell
    $TopLevelPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Thank you for calling Contoso. For Technical Support, press 1. For a Sales Representative, press 2."
    ```

13. Erstellen Sie die Frage auf oberster Ebene. Führen Sie  aus.

    ```powershell
    $TopLevelQuestion = New-CsRgsQuestion -Prompt $TopLevelPrompt [-AnswerList ($SupportAnswer, $SalesAnswer)]
    ```

14. Erstellen Sie nun den Workflow. Führen Sie  aus.

    ```powershell
    $IVRAction = New-CsRgsCallAction -Action TransferToQuestion [-Question $Question]
    $IVRWorkflow = New-CsRgsWorkflow -Parent $ServiceId -Name "Contoso Helpdesk" [-Description "The Contoso Helpdesk line."] -PrimaryUri "sip:helpdesk@contoso.com" [-LineUri tel:+14255554321] [-DisplayNumber "+1 (425) 555-4321"] [-Active $true] [-Anonymous $true] [-DefaultAction $IVRAction] [-Managed $true] [-ManagersByURI ("sip:mindy@contoso.com", "sip:bob@contoso.com")]
    ```

     > [!NOTE]
     > Allen Benutzern, die als Vorgesetzter einer Reaktionsgruppe festgelegt wurden, muss die Rolle CsResponseGroupManager zugewiesen werden. Falls Benutzern diese Rolle nicht zugewiesen ist, können sie keine Reaktionsgruppen verwalten.

## <a name="see-also"></a>Siehe auch

[(Optional) Definieren von Feiertagssätzen für Reaktionsgruppe in Skype for Business](optional-define-response-group-holiday-sets.md)

[(Optional) Definieren der Geschäftszeiten der Reaktionsgruppe in Skype for Business](optional-define-response-group-business-hours.md)

[New-CsRgsWorkflow](/powershell/module/skype/new-csrgsworkflow?view=skype-ps)

[Set-CsRgsWorkflow](/powershell/module/skype/set-csrgsworkflow?view=skype-ps)

[New-CsRgsPrompt](/powershell/module/skype/new-csrgsprompt?view=skype-ps)

[New-CsRgsCallAction](/powershell/module/skype/new-csrgscallaction?view=skype-ps)