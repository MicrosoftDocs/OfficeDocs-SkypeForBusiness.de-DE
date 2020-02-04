---
title: 'Lync Server 2013: Erstellen oder Ändern eines Sammel Ansuchen-Workflows'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a hunt group workflow
ms:assetid: dcb9effb-5d12-4dee-80fc-ab9654222d5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205321(v=OCS.15)
ms:contentKeyID: 48185596
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e56a93ae0be1fd6f047dc6cde724afbea7aa4064
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758059"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-hunt-group-workflow-in-lync-server-2013"></a>Erstellen oder Ändern eines Sammel Ansuchen-Workflows in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-09-11_

Führen Sie eines der folgenden Verfahren aus, um einen Sammelvorgangs-Workflow zu erstellen oder zu ändern.

<div>


> [!NOTE]  
> Sie können die lync Server-Verwaltungsshell oder das Reaktionsgruppen-Konfigurations Tool zum Erstellen und Ändern von Sammelanschlüssen verwenden. Sie können über die lync Server-Systemsteuerung auf das Tool für die Reaktionsgruppen Konfiguration zugreifen, oder indem Sie die Webseite direkt in einem Webbrowser öffnen, indem Sie die folgende URL eingeben: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.



</div>

<div>

## <a name="to-use-response-group-configuration-tool-to-create-or-modify-a-hunt-group-workflow"></a>So verwenden Sie das Reaktionsgruppen-Konfigurations Tool zum Erstellen oder Ändern eines Sammel Ansuchen-Workflows

1.  Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Reaktionsgruppen** und dann auf **Workflow**.

4.  Klicken Sie auf der Seite **Workflow** auf **Workflow erstellen oder bearbeiten**.

5.  Geben Sie im Suchfeld **Dienst auswählen** einen Teil oder den vollständigen Namen des **ApplicationServer**-Diensts ein, von dem der Workflow gehostet wird, den Sie erstellen oder ändern möchten. Klicken Sie in der nun angezeigten Liste der Dienst auf den gewünschten Dienst und klicken Sie dann auf **OK**.
    
    <div>
    

    > [!NOTE]  
    > Das Tool für die Reaktionsgruppen Konfiguration wird geöffnet. Sie können das Tool für die Reaktionsgruppen Konfiguration auch direkt in einem Webbrowser öffnen, indem Sie die folgende URL eingeben: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.

    
    </div>

6.  Führen Sie einen der folgenden Schritte aus:
    
      - Klicken Sie unter **Neuen Workflow erstellen** neben **Sammelanschluss** auf „Erstellen“.
    
      - Suchen Sie unter **Vorhandenen Workflow verwalten** nach dem Workflow, den Sie ändern möchten, und klicken Sie anschließend unter **Aktion** auf **Bearbeiten**.

7.  Falls Benutzer den Workflow bereits verwenden können, aktivieren Sie das Kontrollkästchen **Workflow aktivieren**.
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie einen verwalteten Workflow erstellen, müssen Sie <STRONG>Workflow aktivieren</STRONG> auswählen. Nachdem Sie den aktiven, verwalteten Workflow gespeichert haben, können Sie ihn ändern und deaktivieren.

    
    </div>

8.  Aktivieren Sie das Kontrollkästchen **Für Partnerverbund aktivieren**, um Partnerbenutzern Anrufe bei der Gruppe zu ermöglichen. Außerdem müssen Sie über eine Richtlinie für den externen Zugriff verfügen, die für die für den Verbund konfigurierte reaktionsgruppenanwendung gilt.
    
    <div>
    

    > [!NOTE]  
    > Die globale Richtlinie für den externen Zugriff gilt für die Antwortgruppen Anwendung. Sie können die globale Richtlinie für die Antwortgruppen Föderation mithilfe der lync Server-Systemsteuerung oder mithilfe des Cmdlets "CsExternalAccessPolicy" konfigurieren, um den EnableOutsideAccess <STRONG>-</STRONG> Parameter auf "true" festzulegen. Bedenken Sie, dass globale Richtlinieneinstellungen für alle Benutzer gelten, es sei denn, sie sind einer standort- oder benutzerspezifischen Richtlinie zugeordnet. Stellen Sie daher vor dem Ändern dieser Einstellung für Reaktionsgruppen sicher, dass die Partnerverbundeinstellung die Anforderungen Ihrer Organisation erfüllt. Details dazu, wie Richtlinien für Benutzer gelten, finden Sie unter <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Verwalten der Richtlinie für den externen Zugriff in lync Server 2013</A>. Details zur Föderations Einstellung finden Sie unter <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy">Festlegen von CsExternalAccessPolicy</A>.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Benutzer, die in lync online gehostet werden, können keine Anrufe an Reaktionsgruppen tätigen, die in einer lokalen Bereitstellung gehostet werden. Dies gilt sowohl in hybridbereitstellungen als auch in Fällen, in denen eine lokale Bereitstellung mit einer lync Online-Bereitstellung verbunden ist.

    
    </div>

9.  Aktivieren Sie das Kontrollkästchen **Agentanonymität aktivieren**, um bei Anrufen die Identität der Agents zu verbergen.
    
    <div>
    

    > [!NOTE]  
    > Anonyme Anrufe können nicht mit Chats oder Video gestartet werden. Agent oder Anrufer können jedoch im Verlauf des Anrufs Chats und Video aktivieren. Ein anonymer Agent kann Anrufe halten, weiterleiten (sowohl blind als auch nach Rücksprache) sowie Anrufe parken und fortsetzen. Anonyme Anrufe bieten keine Unterstützung für Konferenzen, Anwendungs- und Desktopfreigabe, Dateiübertragung, Whiteboardverwendung und Datenzusammenarbeit sowie Anrufaufzeichnung. Agents, die das Lync VDI-Plugin verwenden, können eingehende Anrufe anonym empfangen, jedoch keine ausgehenden anonymen Anrufe tätigen.

    
    </div>

10. Geben Sie im Feld **Adresse der Gruppe eingeben, die die Anrufe entgegennimmt** den primären SIP-URI (Uniform Resource Identifier) der Gruppe ein, die die Anrufe beim Workflow erhalten soll.
    
    <div>
    

    > [!NOTE]  
    > Über den primären URI für einen Workflow wird der Workflow identifiziert und auf ihn verwiesen. Der von Ihnen eingegebene SIP-URI wird in den Active Directory-Domänendiensten als Kontaktobjekt erstellt. Zum Erstellen des URIs muss das Objekt in Active Directory eindeutig sein.

    
    </div>

11. Geben Sie im Feld **Anzeigename**den Namen ein, der für den Workflow angezeigt werden soll (beispielsweise Sales Response Group).
    
    <div>
    

    > [!NOTE]  
    > Fügen Sie die Zeichen "&lt;" oder "&gt;" nicht in den Anzeigenamen ein. Die folgenden Anzeigenamen sind reserviert und dürfen nicht verwendet werden: <STRONG>RGS-Anwesenheitsmonitor</STRONG> oder <STRONG>Ankündigungsdienst</STRONG>.

    
    </div>

12. Geben Sie unter **Telefonnummer** den Anschluss-URI für die Reaktionsgruppe ein (z. B. +14255550165).

13. Geben Sie im Feld **Anzeigenummer** die Nummer ein, wie sie für die Reaktionsgruppe angezeigt werden soll (z. B. +1 (425) 555-0165).

14. Optional Geben Sie in **Beschreibung**eine Beschreibung für den Workflow ein, wie er auf der Visitenkarte in lync-Client angezeigt werden soll.

15. Wählen Sie unter **Workflowtyp** die Option **Verwaltet** aus, wenn dieser Workflow von einem Reaktionsgruppenmanager verwaltet wird. Gehen Sie wie folgt vor, um dem Workflow Antwortgruppen-Manager zuzuweisen:
    
    1.  Geben Sie den SIP-URI eines Managers für diesen Workflow ein und klicken Sie auf **Hinzufügen**.
    
    2.  Geben Sie den SIP-URI zusätzlicher Manager für den Workflow ein und klicken Sie auf **Hinzufügen**.
    
    <div>
    

    > [!IMPORTANT]  
    > Jedem Benutzer, der als Manager einer Reaktionsgruppe bestimmt wurde, muss die Rolle „CsResponseGroupManager“ zugewiesen sein. Falls Benutzern diese Rolle nicht zugewiesen ist, können sie keine Reaktionsgruppen verwalten.

    
    </div>

16. Klicken Sie unter **Schritt 2: Sprache auswählen** auf die Sprache, die für die Spracherkennung und Text-zu-Sprache verwendet werden soll.

17. Aktivieren Sie zum Konfigurieren einer Willkommensnachricht unter **Schritt 3: Willkommensnachricht konfigurieren** das Kontrollkästchen **Willkommensnachricht wiedergeben** und führen Sie eine der folgenden Aktionen aus:
    
      - Um die Willkommensnachricht als Text einzugeben, die für Anrufer in Sprache umgewandelt wird, klicken Sie auf **Text-zu-Sprache verwenden** und geben Sie die Willkommensnachricht in das Textfeld ein.
        
        <div>
        

        > [!NOTE]  
        > Verwenden Sie im eingegebenen Text keine HTML-Tags. Andernfalls wird eine Fehlermeldung angezeigt.

        
        </div>
    
      - Um eine aufgezeichnete WAV- (Wave) oder WMA-Datei (Windows Media Audio) für die Willkommensnachricht zu verwenden, klicken Sie auf **Aufzeichnung auswählen**. Klicken Sie auf den Link **Aufzeichnung**, um eine neue Audiodatei hochzuladen. Klicken Sie im neuen Browserfenster auf **Durchsuchen**, markieren Sie die gewünschte Audiodatei und klicken Sie dann auf **Öffnen**. Klicken Sie auf **Hochladen**, um die Datei zu laden.
        
        <div>
        

        > [!NOTE]  
        > Alle von Benutzern bereitgestellten Audiodateien müssen bestimmte Anforderungen erfüllen. Ausführliche Informationen zu unterstützten Dateiformaten finden Sie unter <A href="lync-server-2013-technical-requirements-for-response-group.md">Technische Anforderungen für die Reaktionsgruppe in lync Server 2013</A>.

        
        </div>

18. Klicken Sie unter **Schritt 4: Geschäftszeiten angeben** im Feld **Ihre Zeitzone** auf die Zeitzone des Workflows.
    
    <div>
    

    > [!NOTE]  
    > Dies ist die Zeitzone, in der sich die Anrufer und Agents des Workflows befinden. Die Angabe wird verwendet, um die Öffnungszeiten zu berechnen. Wenn der Workflow z. B. für die mitteleuropäische Zeit konfiguriert wurde und der Workflow um 7:00 Uhr öffnen und um 23:00 Uhr schließen soll, werden die Zeiten 7:00 Uhr MEZ und 23:00 Uhr MEZ verwendet. (Die Zeiten müssen im 24-Stunden-Format eingegeben werden.)

    
    </div>

19. Sie haben folgende Möglichkeiten, um die gewünschten Geschäftszeiten anzugeben:
    
      - Wenn Sie einen vordefinierten Zeitplan für die Geschäftszeiten verwenden möchten, klicken Sie auf **Vordefinierten Zeitplan verwenden** und wählen Sie den gewünschten Zeitplan in der Dropdownliste aus.
        
        <div>
        

        > [!NOTE]  
        > Sie müssen mindestens einen vordefinierten Zeitplan erstellt haben, um diese Option auswählen zu können. Sie erstellen vordefinierte Zeitpläne mit dem <STRONG>New-CSRgsHoursOfBusiness</STRONG>-Cmdlet. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-optional-define-response-group-business-hours.md">(optional) definieren von Reaktionsgruppen-Geschäftszeiten in lync Server 2013</A>.

        
        </div>
        
        <div>
        

        > [!NOTE]  
        > Wenn Sie einen vordefinierten Zeitplan verwenden, werden die Werte für <STRONG>Tag</STRONG>, <STRONG>Öffnen</STRONG> und <STRONG>Schließen</STRONG>, automatisch mit den Tagen und Stunden ausgefüllt, an denen die Reaktionsgruppe verfügbar ist.

        
        </div>
    
      - Klicken Sie auf **Benutzerdefinierten Zeitplan verwenden**, um einen benutzerdefinierten Zeitplan zu erstellen, der nur für diesen Workflow gilt.

20. Wenn Sie einen benutzerdefinierten Zeitplan für diesen Workflow erstellen, aktivieren Sie die Kontrollkästchen für die Wochentage, an denen die Reaktionsgruppe verfügbar ist.

21. Beim Erstellen eines benutzerdefinierten Zeitplans geben Sie über die Werte für **Öffnen** und **Schließen** den Zeitraum für jeden Wochentag ein, in dem die Reaktionsgruppe verfügbar ist.
    
    <div>
    

    > [!NOTE]  
    > Die Werte für <STRONG>Öffnen</STRONG> und <STRONG>Schließen</STRONG> müssen im 24-Stunden-Format angegeben werden. Wenn Ihr Büro z. B. von 9 Uhr bis 17 Uhr geöffnet und mittags geschlossen ist, können Sie die Geschäftszeiten als <STRONG>Öffnen</STRONG> 9:00, <STRONG>Schließen</STRONG> 12:00, <STRONG>Öffnen</STRONG> 13:00 und <STRONG>Schließen</STRONG> 17:00 angeben.

    
    </div>

22. Wenn Sie eine Nachricht wiedergeben möchten, wenn das Büro geschlossen ist, aktivieren Sie das Kontrollkästchen **Nachricht wiedergeben, wenn die Reaktionsgruppe nicht geöffnet ist** und geben Sie die Nachricht ein, indem Sie eine der folgenden Aktionen ausführen:
    
      - Um die Nachricht als Text einzugeben, die für Anrufer in Sprache umgewandelt wird, klicken Sie auf **Text-zu-Sprache verwenden** und geben Sie die Nachricht in das Textfeld ein.
        
        <div>
        

        > [!NOTE]  
        > Verwenden Sie im eingegebenen Text keine HTML-Tags. Andernfalls wird eine Fehlermeldung angezeigt.

        
        </div>
    
      - Um eine aufgezeichnete Audiodatei als Nachricht zu verwenden, klicken Sie auf **Aufzeichnung auswählen**. Klicken Sie auf den Link **Aufzeichnung**, um eine neue Audiodatei hochzuladen. Klicken Sie im neuen Browserfenster auf **Durchsuchen**, markieren Sie die gewünschte Datei und klicken Sie auf **Öffnen**. Klicken Sie auf **Hochladen**, um die Datei zu laden.
        
        <div>
        

        > [!NOTE]  
        > Alle von Benutzern bereitgestellten Audiodateien müssen bestimmte Anforderungen erfüllen. Ausführliche Informationen zu unterstützten audiodateidateien finden Sie unter <A href="lync-server-2013-technical-requirements-for-response-group.md">Technische Anforderungen für die Reaktionsgruppe in lync Server 2013</A>.

        
        </div>

23. Geben Sie an, wie nach Wiedergabe der Nachricht verfahren werden soll (sofern eine Nachricht konfiguriert wurde):
    
      - Klicken Sie auf **Verbindung trennen**, um die Verbindung zu trennen.
    
      - Um den Anruf an ein Voicemailsystem weiterzuleiten, klicken Sie auf **An Voicemail weiterleiten** und geben Sie die Voicemailadresse ein. Das Format für die Voicemail-Adresse lautet \<username\>@\<Domain Name\> (beispielsweise Bob@contoso.com).
    
      - Um den Anruf an einen anderen Benutzer weiterzuleiten, klicken Sie auf **An SIP-URI weiterleiten** und geben Sie die Adresse eines Benutzers ein. Das Format für die Benutzeradresse lautet \<username\>@\<Domain Name\>.
    
      - Um den Anruf an eine andere Telefonnummer weiterzuleiten, klicken Sie auf **An Telefonnummer weiterleiten** und geben Sie die Telefonnummer ein. Das Format für die Telefonnummer ist \<Number\>@\<Domain Name\> (beispielsweise + 14255550121@contoso.com). Der Domänenname wird verwendet, um den Anrufer an das richtige Ziel weiterzuleiten.

24. Aktivieren Sie unter **Schritt 5: Feiertage angeben** die Kontrollkästchen für einen oder mehrere Feiertagssätze, mit denen die Tage definiert werden, an denen die Reaktionsgruppe aufgrund eines Feiertags nicht verfügbar ist.
    
    <div>
    

    > [!NOTE]  
    > Sie müssen Feiertage und Feiertagssätze definieren, bevor Sie den Workflow konfigurieren. Verwenden Sie zum Definieren von Feiertagen und Feiertagssätzen die Cmdlets <STRONG>New-CsRgsHoliday</STRONG> und <STRONG>New-CsRgsHolidaySet</STRONG>. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">(optional) definieren von Reaktionsgruppen Feiertagssätzen in lync Server 2013</A>.

    
    </div>

25. Wenn Sie an Feiertagen eine Nachricht wiedergeben möchten, aktivieren Sie das Kontrollkästchen **An Feiertagen eine Nachricht wiedergegeben** und geben Sie die Nachricht ein, indem Sie eine der folgenden Aktionen ausführen:
    
      - Um die Nachricht als Text einzugeben, die für Anrufer in Sprache umgewandelt wird, klicken Sie auf **Text-zu-Sprache verwenden** und geben Sie die Nachricht in das Textfeld ein.
        
        <div>
        

        > [!NOTE]  
        > Verwenden Sie im eingegebenen Text keine HTML-Tags. Andernfalls wird eine Fehlermeldung angezeigt.

        
        </div>
    
      - Um eine aufgezeichnete Audiodatei als Nachricht zu verwenden, klicken Sie auf **Aufzeichnung auswählen**. Klicken Sie auf den Link **Aufzeichnung**, um eine neue Audiodatei hochzuladen. Klicken Sie im neuen Browserfenster auf **Durchsuchen**, markieren Sie die gewünschte Datei und klicken Sie auf **Öffnen**. Klicken Sie auf **Hochladen**, um die Datei zu laden.
        
        <div>
        

        > [!NOTE]  
        > Alle von Benutzern bereitgestellten Audiodateien müssen bestimmte Anforderungen erfüllen. Ausführliche Informationen zu unterstützten audiodateidateien finden Sie unter <A href="lync-server-2013-technical-requirements-for-response-group.md">Technische Anforderungen für die Reaktionsgruppe in lync Server 2013</A>.

        
        </div>

26. Geben Sie an, wie nach Wiedergabe der Nachricht verfahren werden soll (sofern eine Nachricht konfiguriert wurde):
    
      - Klicken Sie auf **Verbindung trennen**, um die Verbindung zu trennen.
    
      - Um den Anruf an ein Voicemailsystem weiterzuleiten, klicken Sie auf **An Voicemail weiterleiten** und geben Sie die Voicemailadresse ein. Das Format für die Voicemail-Adresse lautet \<username\>@\<Domain Name\> (beispielsweise Bob@contoso.com).
    
      - Um den Anruf an einen anderen Benutzer weiterzuleiten, klicken Sie auf **An SIP-URI weiterleiten** und geben Sie die Adresse eines Benutzers ein. Das Format für die Benutzeradresse lautet \<username\>@\<Domain Name\>.
    
      - Um den Anruf an eine andere Telefonnummer weiterzuleiten, klicken Sie auf **An Telefonnummer weiterleiten** und geben Sie die Telefonnummer ein. Das Format für die Telefonnummer ist \<Number\>@\<Domain Name\> (beispielsweise + 14255550121@contoso.com). Der Domänenname wird verwendet, um den Anrufer an das richtige Ziel weiterzuleiten.

27. Wählen Sie unter **Schritt 6: Warteschleife konfigurieren** im Feld **Warteschleife auswählen, an die die Anrufe weitergeleitet werden** die Warteschleife aus, in der die Anrufer gehalten werden, bis ein Agent verfügbar wird.

28. Wählen Sie unter **Schritt 7: Wartemusik konfigurieren** aus, welche Musik Anrufer beim Warten auf einen Agent hören sollen, indem Sie einen der folgenden Schritte ausführen:
    
      - Klicken Sie auf **Standard verwenden**, um die Standardwartemusik zu verwenden.
    
      - Klicken Sie auf **Musikdatei auswählen**, um eine aufgezeichnete Audiodatei als Wartemusik zu verwenden. Klicken Sie auf den Link **Musikdatei**, um eine neue Audiodatei hochzuladen. Klicken Sie im neuen Browserfenster auf **Durchsuchen**, markieren Sie die gewünschte Datei und klicken Sie auf **Öffnen**. Klicken Sie auf **Hochladen**, um die Datei zu laden.
        
        <div>
        

        > [!NOTE]  
        > Alle von Benutzern bereitgestellten Audiodateien müssen bestimmte Anforderungen erfüllen. Ausführliche Informationen zu unterstützten audiodateidateien finden Sie unter <A href="lync-server-2013-technical-requirements-for-response-group.md">Technische Anforderungen für die Reaktionsgruppe in lync Server 2013</A>.

        
        </div>

29. Klicken Sie auf **Bereitstellen**.

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-hunt-group-workflow"></a>So verwenden Sie Windows PowerShell zum Erstellen oder Ändern eines Sammel Ansuchen-Workflows

1.  Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Erstellen Sie die Eingabeaufforderung, die als Willkommensnachricht abgespielt werden soll und speichern Sie sie in einer Variablen. Führen Sie an der Befehlszeile folgenden Befehl aus:
    
        $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    Beispiel:
    
        $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "Welcome to Contoso. Please wait for an available agent."
    
    <div>
    

    > [!NOTE]  
    > Verwenden Sie das <STRONG>Import-CsRgsAudioFile</STRONG>-Cmdlet, um eine Audiodatei als Ansage zu verwenden. Ausführliche Informationen finden Sie unter <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">importieren-CsRgsAudioFile</A>.

    
    </div>

4.  Rufen Sie die Identität der Warteschleife oder Frage ab, an die die Anrufe weitergeleitet werden. Führen Sie an der Befehlszeile folgenden Befehl aus:
    
        $qid = (Get-CsRgsQueue -Name "Help Desk").Identity
    
    Details zum Erstellen der Warteschlange finden Sie unter [New-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue).

5.  Definieren Sie die durchzuführende Standardaktion, wenn ein Workflow während der Geschäftszeiten geöffnet wird, und speichern Sie sie in einer Variablen. Führen Sie in der Befehlszeile folgenden Befehl aus:
    
        $actionWM = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken> -QueueID $qid
    
    <div>
    

    > [!NOTE]  
    > Für Workflows für Sammelanschlüsse muss der Anruf mit der Standardaktion an eine Warteschleife weitergeleitet werden. Dieser Parameter ist für aktive Workflows erforderlich, für inaktive Workflows dagegen nicht.

    
    </div>
    
    Beispiel:
    
        $actionWM = New-CsRgsCallAction -Prompt $promptWM -Action TransferToQueue -QueueID $qid.Identity

6.  Wenn Sie Geschäftszeiten und Feiertage definieren möchten, müssen Sie diese erstellen, bevor Sie den Workflow erstellen oder ändern. Ausführliche Informationen finden Sie unter [(optional) definieren von Reaktionsgruppen-Geschäftszeiten in lync Server 2013](lync-server-2013-optional-define-response-group-business-hours.md) und [(optional) definieren von Reaktionsgruppen Feiertagssätzen in lync Server 2013](lync-server-2013-optional-define-response-group-holiday-sets.md).

7.  Wenn Sie Aufforderungen für Anrufe erhalten möchten, die außerhalb der Geschäftszeiten oder an Feiertagen empfangen werden, verwenden Sie das Cmdlet **New-CsRgsPrompt** , um die Eingabeaufforderung zu definieren, und verwenden Sie die **New-CsRgsCallAction** , um die Aktion zu definieren, die nach der Eingabeaufforderung ausgeführt werden soll. Ausführliche Informationen finden Sie unter [New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt) und [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction).

8.  Rufen Sie den Dienstnamen für den lync Server Response Group-Dienst ab, und weisen Sie ihn einer Variablen zu. Führen Sie an der Befehlszeile folgenden Befehl aus:
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}).ServiceId;

9.  Erstellen oder ändern Sie den Workflow. Verwenden Sie **New-CsRgsWorkflow** zum Erstellen eines Workflows. Verwenden Sie **Set-CsRgsWorkflow** zum Ändern eines Workflows. Geben Sie in der Befehlszeile Folgendes ein:
    
        $workflowHG = New-CsRgsWorkflow -Parent <service ID for the Response Group service> -Name "<hunt group name>" [-Description "<hunt group description>"] -PrimaryUri "<SIP address for the workflow>" [-LineUri "<Phone number for the workflow>"] [-DisplayNumber "<Phone number displayed in Lync>"] [-Active <$true | $false>] [-Anonymous <$true | $false>] [-DefaultAction <variable from preceding step>] [-EnabledForFederation <$true | $false>] [-Managed <$true | $false>] [-MangersByUri <SIP addresses for Response Group Managers who can manage the workflow>]
    
    Beispiel:
    
        $workflowHG = New-CsRgsWorkflow -Parent $serviceID -Name "Human Resources" -Description "Human Resources workflow" -PrimaryUri "sip:humanresources@contoso.com" -LineUri "TEL:+14255551219" -DisplayNumber "555-1219" -Active $true -Anonymous $true -DefaultAction $actionWM -EnabledForFederation $false -Managed $true -ManagersByUri "sip:bob@contoso.com", "mindy@contoso.com"
    
    <div>
    

    > [!IMPORTANT]  
    > Allen Benutzern, die designierte Workflowmanager sind, muss die Rolle „CsResponseGroupManager“ zugewiesen werden.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Details zu zusätzlichen optionalen Parametern finden Sie unter <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow">New-CsRgsWorkflow</A> oder <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow">CsRgsWorkflow</A>

    
    </div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Optional Definieren von Feiertagssätzen für Reaktionsgruppen in lync Server 2013](lync-server-2013-optional-define-response-group-holiday-sets.md)  


[Optional Definieren der Geschäftszeiten der Reaktionsgruppe in lync Server 2013](lync-server-2013-optional-define-response-group-business-hours.md)  


[Neu – CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow)  
[Satz-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow)  
[New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt)  
[Neu – CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

