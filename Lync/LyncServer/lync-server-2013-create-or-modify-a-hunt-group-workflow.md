---
title: 'Lync Server 2013: Erstellen oder Ändern eines Workflows für Sammelanschlüsse'
TOCTitle: Erstellen oder Ändern eines Workflows für Sammelanschlüsse
ms:assetid: dcb9effb-5d12-4dee-80fc-ab9654222d5a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205321(v=OCS.15)
ms:contentKeyID: 49295625
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen oder Ändern eines Workflows für Sammelanschlüsse in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-09-11_

Verwenden Sie eines der folgenden Verfahren, um einen Workflow für Sammelanschlüsse zu erstellen oder zu ändern.


> [!NOTE]
> Mit der Lync Server-Verwaltungsshell oder dem Konfigurationstool für Reaktionsgruppen können Sie Workflows für Sammelanschlüsse erstellen und ändern. Auf das Konfigurationstool für Reaktionsgruppen können Sie über die Lync Server-Systemsteuerung zugreifen, oder indem Sie die Webseite direkt in einem Webbrowser durch Eingabe der folgenden URL öffnen: <STRONG>https://</STRONG> <EM>&lt;Webpool-FQDN&gt;</EM> <STRONG>/RgsConfig</STRONG> .



## So erstellen oder ändern Sie mithilfe der Konfigurationstool für Reaktionsgruppen einen Workflow für Sammelanschlüsse

1.  Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Reaktionsgruppen** und dann auf **Workflow** .

4.  Klicken Sie auf der Seite **Workflow** auf **Workflow erstellen oder bearbeiten** .

5.  Geben Sie im Suchfeld **Dienst auswählen** einen Teil oder den vollständigen Namen des **ApplicationServer** -Diensts ein, von dem der Workflow gehostet wird, den Sie erstellen oder ändern möchten. Klicken Sie dann in der Liste mit den Diensten auf den gewünschten Dienst, und klicken Sie auf **OK** .
    

    > [!NOTE]
    > Das Konfigurationstool für Reaktionsgruppen wird geöffnet. Sie können das Konfigurationstool für Reaktionsgruppen auch direkt in einem Webbrowser öffnen, indem Sie die folgende URL eingeben: <STRONG>https://</STRONG> <EM>&lt;Webpool-FQDN&gt;</EM> <STRONG>/RgsConfig</STRONG> .



6.  Führen Sie einen der folgenden Schritte aus:
    
      - Klicken Sie unter **Neuen Workflow erstellen** neben **Sammelanschluss** auf Erstellen .
    
      - Suchen Sie unter **Vorhandenen Workflow verwalten** nach dem Workflow, den Sie ändern möchten, und klicken Sie anschließend unter **Aktion** auf **Bearbeiten** .

7.  Falls Benutzer den Workflow bereits verwenden können, aktivieren Sie das Kontrollkästchen **Workflow aktivieren** .
    

    > [!NOTE]
    > Wenn Sie einen verwalteten Workflow erstellen, müssen Sie <STRONG>Workflow aktivieren</STRONG> auswählen. Nachdem Sie den aktiven, verwalteten Workflow gespeichert haben, können Sie ihn ändern und deaktivieren.



8.  Aktivieren Sie das Kontrollkästchen **Für Partnerverbund aktivieren** , um Partnerbenutzern Anrufe bei der Gruppe zu ermöglichen. Sie müssen auch eine Richtlinie für den externen Zugriff konfiguriert haben, die der für den Verbund konfigurierten Reaktionsgruppenanwendung zugewiesen wurde.
    

    > [!NOTE]
    > Die globale Richtlinie für den externen Zugriff gilt für die Reaktionsgruppenanwendung. Sie können die globale Richtlinie für den Reaktionsgruppenverbund mithilfe der Lync Server-Systemsteuerung oder mithilfe des <STRONG>Set-CsExternalAccessPolicy</STRONG> -Cmdlets konfigurieren, um den EnableOutsideAccess -Parameter auf True festzulegen. Bedenken Sie, dass globale Richtlinieneinstellungen für alle Benutzer gelten, es sei denn, sie sind einer standort- oder benutzerspezifischen Richtlinie zugeordnet. Stellen Sie daher vor dem Ändern dieser Einstellung für Reaktionsgruppen sicher, dass die Partnerverbundeinstellung die Anforderungen Ihrer Organisation erfüllt. Nähere Informationen dazu, wie sich Richtlinien auf Benutzer auswirken, finden Sie unter <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Verwalten von Richtlinien für den externen Zugriff für Ihre Organisation in Lync Server 2013</A>. Nähere Informationen zur Partnerverbundeinstellung finden Sie unter <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsExternalAccessPolicy">Set-CsExternalAccessPolicy</A>.

    

    > [!NOTE]
    > Benutzer, die in Lync Online gehostet werden, können keine Anrufe mit Reaktionsgruppen führen, die in einer lokalen Bereitstellung gehostet werden. Dies gilt sowohl für Hybridbereitstellungen als auch für Fälle, in denen eine lokale Bereitstellung mit einer Lync Online-Bereitstellung verbunden ist.



9.  Aktivieren Sie das Kontrollkästchen **Agentanonymität aktivieren** , um bei Anrufen die Identität der Agents zu verbergen.
    

    > [!NOTE]
    > Anonyme Anrufe können nicht mit Chats oder Video gestartet werden. Agent oder Anrufer können jedoch im Verlauf des Anrufs Chats und Video aktivieren. Ein anonymer Agent kann Anrufe halten, weiterleiten (sowohl blind als auch nach Rücksprache) sowie Anrufe parken und fortsetzen. Anonyme Anrufe bieten keine Unterstützung für Konferenzen, Anwendungs- und Desktopfreigabe, Dateiübertragung, Whiteboardverwendung und Datenzusammenarbeit sowie Anrufaufzeichnung. Agents, die das Lync VDI-Plugin verwenden, können eingehende Anrufe anonym empfangen, jedoch keine ausgehenden anonymen Anrufe tätigen.



10. Geben Sie im Feld **Geben Sie die Adresse der Gruppe ein, die die Anrufe entgegennimmt** den primären SIP-URI (Uniform Resource Identifier) der Gruppe ein, die die Anrufe beim Workflow erhalten soll.
    

    > [!NOTE]
    > Über den primären URI für einen Workflow wird der Workflow identifiziert. Der SIP-URI, den Sie eingeben, wird als Kontaktobjekt in Active Directory-Domänendienste erstellt. Beim Erstellen des URI muss das Objekt in Active Directory eindeutig sein.



11. Geben Sie im Feld **Anzeigename** den Namen ein, der für den Workflow angezeigt werden soll (z. B. "Vertrieb- Reaktionsgruppe").
    

    > [!NOTE]
    > Verwenden Sie im Anzeigenamen nicht die Zeichen "&lt;" oder "&gt;". Die folgenden Anzeigenamen sind reserviert und dürfen nicht verwendet werden: <STRONG>RGS-Anwesenheitsmonitor</STRONG> oder <STRONG>Ankündigungsdienst</STRONG> .



12. Geben Sie unter **Telefonnummer** den Anschluss-URI für die Reaktionsgruppe ein (z. B. +14255550165).

13. Geben Sie in **Anzeigenummer** die Nummer ein, wie sie für die Reaktionsgruppe angezeigt werden soll (z. B. +1 (425) 555-0165).

14. (Optional) Geben Sie im Feld **Beschreibung** eine Beschreibung für den Workflow ein, die auf der Visitenkarte im Lync-Client angezeigt werden soll.

15. Wählen Sie unter **Workflowtyp** die Option **Verwaltet** aus, falls dieser Workflow von einem Reaktionsgruppenmanager verwaltet wird. Führen Sie die folgenden Schritte aus, um dem Workflow Reaktionsgruppenmanager zuzuweisen:
    
    1.  Geben Sie den SIP-URI eines Managers für diesen Workflow ein, und klicken Sie auf **Hinzufügen** .
    
    2.  Geben Sie den SIP-URI zusätzlicher Manager für den Workflow ein, und klicken Sie auf **Hinzufügen** .
    

    > [!IMPORTANT]
    > Jedem Benutzer, der als Manager einer Reaktionsgruppe bestimmt wurde, muss die Rolle CsResponseGroupManager zugewiesen sein. Falls Benutzern diese Rolle nicht zugewiesen ist, können sie keine Reaktionsgruppen verwalten.



16. Klicken Sie unter **Schritt 2: Sprache auswählen** auf die Sprache, die für die Spracherkennung und Text-zu-Sprache verwendet werden soll.

17. Aktivieren Sie zum Konfigurieren einer Willkommensnachricht unter **Schritt 3: Willkommensnachricht konfigurieren** das Kontrollkästchen **Willkommensnachricht wiedergeben** , und führen Sie eine der folgenden Aktionen aus:
    
      - Um die Willkommensnachricht als Text einzugeben, die für Anrufer in Sprache umgewandelt wird, klicken Sie auf **Text-zu-Sprache verwenden** und geben die Willkommensnachricht in das Textfeld ein.
        

        > [!NOTE]
        > Verwenden Sie im eingegebenen Text keine HTML-Tags. Andernfalls wird eine Fehlermeldung angezeigt.

    
      - Um eine aufgezeichnete WAV- (Wave) oder WMA-Datei (Windows Media Audio) für die Willkommensnachricht zu verwenden, klicken Sie auf **Auswählen einer Aufzeichnung** . Klicken Sie auf den Link **Aufzeichnung** , um eine neue Audiodatei hochzuladen. Klicken Sie im neuen Browserfenster auf **Durchsuchen** , markieren Sie die gewünschte Audiodatei, und klicken Sie dann auf **Öffnen** . Klicken Sie auf **Hochladen** , um die Datei zu laden.
        

        > [!NOTE]
        > Alle von Benutzern bereitgestellten Audiodateien müssen bestimmte Anforderungen erfüllen. Ausführliche Informationen zu den unterstützten Dateiformaten finden Sie unter <A href="lync-server-2013-technical-requirements-for-response-group.md">Technische Anforderungen für Reaktionsgruppen in Lync Server 2013</A>.



18. Klicken Sie unter **Schritt 4: Geschäftszeiten angeben** im Feld **Ihre Zeitzone** auf die Zeitzone des Workflows.
    

    > [!NOTE]
    > Dies ist die Zeitzone, in der sich die Anrufer und Agents des Workflows befinden. Die Angabe wird verwendet, um die Öffnungszeiten zu berechnen. Wenn der Workflow z.&nbsp;B. für die mitteleuropäische Zeit konfiguriert wurde und der Workflow um 7:00&nbsp;Uhr öffnen und um 23:00&nbsp;Uhr schließen soll, werden die Zeiten 7:00&nbsp;Uhr MEZ und 23:00&nbsp;Uhr MEZ verwendet. (Die Zeiten müssen im 24-Stunden-Format eingegeben werden.)



19. Sie haben folgende Möglichkeiten, um die gewünschten Geschäftszeiten anzugeben:
    
      - Wenn Sie einen vordefinierten Zeitplan für die Geschäftszeiten verwenden möchten, klicken Sie auf **Vordefinierten Zeitplan verwenden** , und wählen Sie den gewünschten Zeitplan in der Dropdownliste aus.
        

        > [!NOTE]
        > Sie müssen mindestens einen vordefinierten Zeitplan erstellt haben, um diese Option auswählen zu können. Sie erstellen vordefinierte Zeitpläne mit dem <STRONG>New-CSRgsHoursOfBusiness</STRONG>-Cmdlet. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-optional-define-response-group-business-hours.md">(Optional) Definieren von Geschäftszeiten für Reaktionsgruppen in Lync Server 2013</A>.

        

        > [!NOTE]
        > Wenn Sie einen vordefinierten Zeitplan verwenden, werden die Werte für <STRONG>Tag</STRONG> , <STRONG>Öffnen</STRONG> und <STRONG>Schließen</STRONG> , an denen die Reaktionsgruppe verfügbar ist, automatisch eingetragen.

    
      - Klicken Sie auf **Benutzerdefinierten Zeitplan verwenden** , um einen benutzerdefinierten Zeitplan zu erstellen, der nur für diesen Workflow gilt.

20. Wenn Sie einen benutzerdefinierten Zeitplan für diesen Workflow erstellen, aktivieren Sie die Kontrollkästchen für die Wochentage, an denen die Reaktionsgruppe verfügbar ist.

21. Beim Erstellen eines benutzerdefinierten Zeitplans geben Sie über die Werte für **Öffnen** und **Schließen** den Zeitraum für jeden Wochentag ein, in dem die Reaktionsgruppe verfügbar ist.
    

    > [!NOTE]
    > Die Werte für <STRONG>Öffnen</STRONG> und <STRONG>Schließen</STRONG> müssen im 24-Stunden-Format angegeben werden. Wenn Ihr Büro z.&nbsp;B. von 9 Uhr bis 17 Uhr geöffnet und mittags geschlossen ist, können Sie die Geschäftszeiten als <STRONG>Öffnen</STRONG> 9:00, <STRONG>Schließen</STRONG> 12:00, <STRONG>Öffnen</STRONG> 13:00 und <STRONG>Schließen</STRONG> 17:00 angeben.



22. Wenn Sie eine Nachricht wiedergeben möchten, wenn das Büro geschlossen ist, aktivieren Sie das Kontrollkästchen **Nachricht wiedergeben, wenn die Reaktionsgruppe nicht geöffnet ist** , und geben Sie die Nachricht ein, indem Sie eine der folgenden Aktionen ausführen:
    
      - Um die Nachricht als Text einzugeben, die für Anrufer in Sprache umgewandelt wird, klicken Sie auf **Text-zu-Sprache verwenden** und geben die Nachricht in das Textfeld ein.
        

        > [!NOTE]
        > Verwenden Sie im eingegebenen Text keine HTML-Tags. Andernfalls wird eine Fehlermeldung angezeigt.

    
      - Um eine aufgezeichnete Audiodatei als Nachricht zu verwenden, klicken Sie auf **Auswählen einer Aufzeichnung** . Klicken Sie auf den Link **Aufzeichnung** , um eine neue Audiodatei hochzuladen. Klicken Sie im neuen Browserfenster auf **Durchsuchen** , markieren Sie die gewünschte Datei, und klicken Sie auf **Öffnen** . Klicken Sie auf **Hochladen** , um die Datei zu laden.
        

        > [!NOTE]
        > Alle von Benutzern bereitgestellten Audiodateien müssen bestimmte Anforderungen erfüllen. Ausführliche Informationen zu den unterstützten Audiodateiformaten finden Sie unter <A href="lync-server-2013-technical-requirements-for-response-group.md">Technische Anforderungen für Reaktionsgruppen in Lync Server 2013</A>.



23. Geben Sie an, wie nach Wiedergabe der Nachricht verfahren werden soll (sofern eine Nachricht konfiguriert wurde):
    
      - Klicken Sie auf **Verbindung trennen** , um die Verbindung zu trennen.
    
      - Um den Anruf an ein Voicemailsystem weiterzuleiten, klicken Sie auf **An Voicemail weiterleiten** und geben die Voicemailadresse ein. Das Format der Voicemailadresse lautet " *\<Benutzername\>* @ *\<Domänenname\>* " (z. B. bob@contoso.com ).
    
      - Um den Anruf an einen anderen Benutzer weiterzuleiten, klicken Sie auf **An SIP-URI weiterleiten** und geben die Adresse eines Benutzers ein. Das Format der Benutzeradresse lautet " *\<Benutzername\>* @ *\<Domänenname\>* ".
    
      - Um den Anruf an eine andere Telefonnummer weiterzuleiten, klicken Sie auf **An Telefonnummer weiterleiten** und geben die Telefonnummer ein. Das Format der Telefonnummer lautet " *\<Nummer\>* @ *\<Domänenname\>* " (z. B. +14255550121@contoso.com ). Der Domänenname wird verwendet, um den Anrufer an das richtige Ziel weiterzuleiten.

24. Aktivieren Sie unter **Schritt 5: Feiertage angeben** die Kontrollkästchen für einen oder mehrere Feiertagssätze, mit denen die Tage definiert werden, an denen die Reaktionsgruppe aufgrund eines Feiertags nicht verfügbar ist.
    

    > [!NOTE]
    > Sie müssen Feiertage und Feiertagssätze definieren, bevor Sie den Workflow konfigurieren. Verwenden Sie zum Definieren von Feiertagen und Feiertagssätzen die Cmdlets <STRONG>New-CsRgsHoliday</STRONG> und <STRONG>New-CsRgsHolidaySet</STRONG>. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Optional) Definieren von Feiertagsschemas für Reaktionsgruppen in Lync Server 2013</A>.



25. Wenn Sie an Feiertagen eine Nachricht wiedergeben möchten, aktivieren Sie das Kontrollkästchen **An Feiertagen wird eine Nachricht wiedergegeben** , und geben Sie die Nachricht an, indem Sie eine der folgenden Aktionen ausführen:
    
      - Um die Nachricht als Text einzugeben, die für Anrufer in Sprache umgewandelt wird, klicken Sie auf **Text-zu-Sprache verwenden** und geben die Nachricht in das Textfeld ein.
        

        > [!NOTE]
        > Verwenden Sie im eingegebenen Text keine HTML-Tags. Andernfalls wird eine Fehlermeldung angezeigt.

    
      - Um eine aufgezeichnete Audiodatei als Nachricht zu verwenden, klicken Sie auf **Auswählen einer Aufzeichnung** . Klicken Sie auf den Link **Aufzeichnung** , um eine neue Audiodatei hochzuladen. Klicken Sie im neuen Browserfenster auf **Durchsuchen** , markieren Sie die gewünschte Datei, und klicken Sie auf **Öffnen** . Klicken Sie auf **Hochladen** , um die Datei zu laden.
        

        > [!NOTE]
        > Alle von Benutzern bereitgestellten Audiodateien müssen bestimmte Anforderungen erfüllen. Ausführliche Informationen zu den unterstützten Audiodateiformaten finden Sie unter <A href="lync-server-2013-technical-requirements-for-response-group.md">Technische Anforderungen für Reaktionsgruppen in Lync Server 2013</A>.



26. Geben Sie an, wie nach Wiedergabe der Nachricht verfahren werden soll (sofern eine Nachricht konfiguriert wurde):
    
      - Klicken Sie auf **Verbindung trennen** , um die Verbindung zu trennen.
    
      - Um den Anruf an ein Voicemailsystem weiterzuleiten, klicken Sie auf **An Voicemail weiterleiten** und geben die Voicemailadresse ein. Das Format der Voicemailadresse lautet " *\<Benutzername\>* @ *\<Domänenname\>* " (z. B. bob@contoso.com ).
    
      - Um den Anruf an einen anderen Benutzer weiterzuleiten, klicken Sie auf **An SIP-URI weiterleiten** und geben die Adresse eines Benutzers ein. Das Format der Benutzeradresse lautet " *\<Benutzername\>* @ *\<Domänenname\>* ".
    
      - Um den Anruf an eine andere Telefonnummer weiterzuleiten, klicken Sie auf **An Telefonnummer weiterleiten** und geben die Telefonnummer ein. Das Format der Telefonnummer lautet " *\<Nummer\>* @ *\<Domänenname\>* " (z. B. +14255550121@contoso.com ). Der Domänenname wird verwendet, um den Anrufer an das richtige Ziel weiterzuleiten.

27. Wählen Sie unter **Schritt 6: Warteschleife konfigurieren** im Feld **Wählen Sie die Warteschleife aus, an die die Anrufe weitergeleitet werden** die Warteschleife aus, in der die Anrufer gehalten werden, bis ein Agent verfügbar wird.

28. Wählen Sie unter **Schritt 7: Wartemusik konfigurieren** aus, welche Musik Anrufer beim Warten auf einen Agent hören sollen, indem Sie einen der folgenden Schritte ausführen:
    
      - Klicken Sie auf **Standard verwenden** , um die Standardwartemusik zu verwenden.
    
      - Klicken Sie auf **Auswählen einer Musikdatei** , um eine aufgezeichnete Audiodatei als Wartemusik zu verwenden. Klicken Sie auf den Link **Musikdatei** , um eine neue Audiodatei hochzuladen. Klicken Sie im neuen Browserfenster auf **Durchsuchen** , markieren Sie die gewünschte Datei, und klicken Sie auf **Öffnen** . Klicken Sie auf **Hochladen** , um die Datei zu laden.
        

        > [!NOTE]
        > Alle von Benutzern bereitgestellten Audiodateien müssen bestimmte Anforderungen erfüllen. Ausführliche Informationen zu den unterstützten Audiodateiformaten finden Sie unter <A href="lync-server-2013-technical-requirements-for-response-group.md">Technische Anforderungen für Reaktionsgruppen in Lync Server 2013</A>.



29. Klicken Sie auf **Bereitstellen** .

## So erstellen oder ändern Sie mithilfe der Windows PowerShell einen Workflow für Sammelanschlüsse

1.  Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Erstellen Sie die Ansage, die als Willkommensnachricht abgespielt werden soll, und speichern Sie sie in einer Variablen. Führen Sie an der Befehlszeile folgenden Befehl aus:
    
        $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    Beispiel:
    
        $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "Welcome to Contoso. Please wait for an available agent."
    

    > [!NOTE]
    > Verwenden Sie das <STRONG>Import-CsRgsAudioFile</STRONG>-Cmdlet, um eine Audiodatei als Ansage zu verwenden. Ausführliche Informationen finden Sie unter <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.



4.  Rufen Sie die Identität der Warteschleife oder Frage ab, an die die Anrufe weitergeleitet werden. Führen Sie an der Befehlszeile folgenden Befehl aus:
    
        $qid = (Get-CsRgsQueue -Name "Help Desk").Identity
    
    Ausführliche Informationen zum Erstellen der Warteschleife finden Sie unter [New-CsRgsQueue](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsQueue).

5.  Definieren Sie die durchzuführende Standardaktion, wenn ein Workflow während der Geschäftszeiten geöffnet wird, und speichern Sie sie in einer Variablen. Führen Sie an der Befehlszeile folgenden Befehl aus:
    
        $actionWM = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken> -QueueID $qid
    

    > [!NOTE]
    > Für Workflows für Sammelanschlüsse muss der Anruf mit der Standardaktion an eine Warteschleife weitergeleitet werden. Dieser Parameter ist für aktive Workflows erforderlich, für inaktive Workflows dagegen nicht.

    
    Beispiel:
    
        $actionWM = New-CsRgsCallAction -Prompt $promptWM -Action TransferToQueue -QueueID $qid.Identity

6.  Wenn Sie Geschäftszeiten und Feiertage definieren möchten, müssen Sie diese erstellen, bevor Sie den Workflow erstellen oder ändern. Ausführliche Informationen finden Sie unter [(Optional) Definieren von Geschäftszeiten für Reaktionsgruppen in Lync Server 2013](lync-server-2013-optional-define-response-group-business-hours.md) und [(Optional) Definieren von Feiertagsschemas für Reaktionsgruppen in Lync Server 2013](lync-server-2013-optional-define-response-group-holiday-sets.md).

7.  Wenn Sie Ansagen für Anrufe wünschen, die außerhalb der Geschäftszeiten oder an Feiertagen empfangen werden, definieren Sie die Ansage mithilfe des **New-CsRgsPrompt**-Cmdlets, und definieren Sie mithilfe des **New-CsRgsCallAction**-Cmdlets die Aktion, die im Anschluss an die Ansage ausgeführt werden soll. Ausführliche Informationen finden Sie unter [New-CsRgsPrompt](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsPrompt) und [New-CsRgsCallAction](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsCallAction).

8.  Rufen Sie den Dienstnamen für den Lync Server-Reaktionsgruppendienst ab, und weisen Sie ihn einer Variablen zu. Führen Sie an der Befehlszeile folgenden Befehl aus:
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}).ServiceId;

9.  Erstellen oder ändern Sie den Workflow. Verwenden Sie das **New-CsRgsWorkflow**-Cmdlet zum Erstellen eines Workflows. Verwenden Sie das **Set-CsRgsWorkflow**-Cmdlet zum Ändern eines Workflows. Geben Sie an der Befehlszeile Folgendes ein:
    
        $workflowHG = New-CsRgsWorkflow -Parent <service ID for the Response Group service> -Name "<hunt group name>" [-Description "<hunt group description>"] -PrimaryUri "<SIP address for the workflow>" [-LineUri "<Phone number for the workflow>"] [-DisplayNumber "<Phone number displayed in Lync>"] [-Active <$true | $false>] [-Anonymous <$true | $false>] [-DefaultAction <variable from preceding step>] [-EnabledForFederation <$true | $false>] [-Managed <$true | $false>] [-MangersByUri <SIP addresses for Response Group Managers who can manage the workflow>]
    
    Beispiel:
    
        $workflowHG = New-CsRgsWorkflow -Parent $serviceID -Name "Human Resources" -Description "Human Resources workflow" -PrimaryUri "sip:humanresources@contoso.com" -LineUri "TEL:+14255551219" -DisplayNumber "555-1219" -Active $true -Anonymous $true -DefaultAction $actionWM -EnabledForFederation $false -Managed $true -ManagersByUri "sip:bob@contoso.com", "mindy@contoso.com"
    

    > [!IMPORTANT]
    > Allen Benutzer, die designierte Workflowmanager sind, muss die Rolle CsResponseGroupManager zugewiesen werden.

    

    > [!NOTE]
    > Ausführliche Informationen zu zusätzlichen optionalen Parametern finden Sie unter <A href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsWorkflow">New-CsRgsWorkflow</A> oder <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsRgsWorkflow">Set-CsRgsWorkflow</A>



## Siehe auch

#### Aufgaben

[(Optional) Definieren von Feiertagsschemas für Reaktionsgruppen in Lync Server 2013](lync-server-2013-optional-define-response-group-holiday-sets.md)  

#### Konzepte

[(Optional) Definieren von Geschäftszeiten für Reaktionsgruppen in Lync Server 2013](lync-server-2013-optional-define-response-group-business-hours.md)  

#### Weitere Ressourcen

[New-CsRgsWorkflow](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsWorkflow)  
[Set-CsRgsWorkflow](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsRgsWorkflow)  
[New-CsRgsPrompt](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsPrompt)  
[New-CsRgsCallAction](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsCallAction)

