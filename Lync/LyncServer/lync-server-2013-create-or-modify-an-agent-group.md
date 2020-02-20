---
title: 'Lync Server 2013: Erstellen oder Ändern einer Agentengruppe'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify an agent group
ms:assetid: f1461fff-51c1-4f4b-9311-8cba02c333fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205370(v=OCS.15)
ms:contentKeyID: 48185784
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8dd855edfcef9d9503d433426492f0cc1517b61
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151787"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-an-agent-group-in-lync-server-2013"></a>Erstellen oder Ändern einer Agentengruppe in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-02-07_

Verwenden Sie eines der folgenden Verfahren, um eine Agentengruppe zu erstellen oder zu ändern.

<div>


> [!NOTE]  
> Ein Administrator (beispielsweise CsVoiceAdministrator) muss Benutzer für Enterprise-VoIP und-lync Server aktivieren, bevor die Benutzeragenten Gruppen zugewiesen werden können. Wenn Sie einer der Delegierten Reaktionsgruppen-Manager für einen verwalteten Workflow sind, können Sie Agentgruppen erstellen und die Agentengruppen in den von Ihnen verwalteten Workflows verwenden.



</div>

<div>


> [!IMPORTANT]  
> Wenn Sie Benutzer als Reaktionsgruppenagents zuweisen, weisen Sie diese darauf hin, dass sie bei aktiviertem Datenschutzmodus nach "RGS-Anwesenheitsmonitor"-Kontakten suchen und sie ihrer Kontaktliste hinzufügen müssen. Agents, deren Datenschutzmodus aktiviert ist, die jedoch "RGS-Anwesenheitsmonitor" nicht in ihre Kontaktliste aufgenommen haben, können keine Anrufe bei der Reaktionsgruppe annehmen. Agents, deren Datenschutzmodus nicht aktiviert ist, sind davon nicht betroffen.



</div>

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-an-agent-group"></a>So verwenden Sie lync Server-Systemsteuerung zum Erstellen oder Ändern einer Agentgruppe

1.  Melden Sie sich als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie einer der Delegierten Reaktionsgruppen-Manager für einen verwalteten Workflow sind, können Sie Gruppen erstellen und in den von Ihnen verwalteten Workflows verwenden.

    
    </div>

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Reaktionsgruppen** und dann auf **Gruppe**.

4.  Führen Sie auf der Seite **Gruppe** einen der folgenden Schritte aus:
    
      - Klicken Sie auf **neu**, um eine neue Agentengruppe zu erstellen. Geben Sie in das Suchfeld **Dienst auswählen** den vollständigen oder Teil des Namens des **ApplicationServer** -Diensts ein, dem Sie die Gruppe hinzufügen möchten. Klicken Sie in der Dienstliste auf den gewünschten Dienst, und klicken Sie dann auf **OK**.
    
      - Zum Ändern einer vorhandenen Agentgruppe geben Sie den Namen der Agentgruppe ganz oder teilweise in das Suchfeld ein. Klicken Sie in der resultierenden Liste auf die gewünschte Gruppe, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.

5.  Geben Sie unter **Name**einen identifizierenden Namen für die Agentengruppe ein.

6.  Geben Sie in **Beschreibung** eine Beschreibung für die Gruppe ein.

7.  Wählen Sie unter **Beteiligungsrichtlinie** eine der folgenden Einstellungen aus, um das Anmeldeverhalten für die Gruppe einzurichten:
    
      - Wählen Sie **Informell**, um anzugeben, dass Agents in der Gruppe sich bei der Gruppe weder an- noch abmelden müssen. Agents werden bei der Anmeldung bei lync Server 2013 automatisch bei der Gruppe angemeldet.
    
      - klicken Sie auf **Formell**, um festzulegen, dass sich die Agents der Gruppe bei der Gruppe an- oder abmelden müssen. Wenn Sie diese Option auswählen, klicken Agents auf ein Menüelement in lync, um Internet Explorer zu öffnen und eine Webseiten Konsole zum ein-und Ausloggen der Gruppe anzuzeigen.

8.  Geben Sie im Feld **Agentwarnungszeit (Sekunden)** an, wie lange das Telefon eines Agents klingelt, bevor der Anruf an den nächsten verfügbaren Agent übergeben wird (die Standardeinstellung ist 20 Sekunden).
    
    <div>
    

    > [!IMPORTANT]  
    > Die Einstellung für die Agent-Warnungszeit darf 180 Sekunden nicht überschreiten. Wenn die Agent-Warnungszeit 180 Sekunden überschreitet, lehnt die Clientanwendung den Anruf ab, da der SIP-Transaktionszeitgeber seine maximale Wartezeit erreicht.

    
    </div>

9.  Wählen Sie unter **Routingmethode** aus, wie Anrufe an die Agents in der Gruppe weitergeleitet werden:
    
      - Klicken Sie auf **Längster Leerlauf**, um einen neuen Anruf zuerst dem Agent anzubieten, der am längsten im Leerlauf war ( **verfügbar** oder **inaktiv** in lync Server der längste).
    
      - Klicken Sie auf **Parallel**, um einen neuen Anruf simultan allen verfügbaren Agents anzubieten. Der Anruf wird an den ersten Agent übergeben, der diesen annimmt.
    
      - Wenn Sie einen neuen Anruf den einzelnen Agents nacheinander anbieten möchten, klicken Sie auf **Roundrobin**.
    
      - Wenn Sie einen neuen Anruf den Agents immer in der Reihenfolge anbieten möchten, in der sie auf der Registerkarte **Agent** aufgeführt sind, klicken Sie auf **Seriell**.
    
      - Wenn Sie einen neuen Anruf für alle Agents anbieten möchten, die sich unabhängig von Ihrer aktuellen Anwesenheit bei lync Server 2013 und dem Reaktionsgruppenanwendung angemeldet haben, klicken Sie auf **Attendant**. Lync 2010 Attendant Benutzer, die als Agents konfiguriert sind, können alle Anrufe sehen, die warten, und wartende Anrufe in beliebiger Reihenfolge beantworten. Der Anruf wird an den ersten Agent gesendet, der ihn akzeptiert, nach dem die anderen lync 2010 Attendant Benutzer den Anruf nicht mehr sehen.

10. Geben Sie auf der Registerkarte **Agents** an, wie Sie Ihre Agentliste erstellen möchten:
    
      - Um eine benutzerdefinierte Liste von Agents zu verwenden, klicken Sie auf **benutzerdefinierte Gruppe von Agents definieren**, und führen Sie einen der folgenden Schritte aus:
        
          - Klicken Sie zum Hinzufügen eines Benutzers zur Gruppe Agent auf **auswählen**, und geben Sie dann im Suchfeld **Agents auswählen** den vollständigen oder Teil des Namens des Benutzers ein, den Sie dieser Gruppe hinzufügen möchten, und klicken Sie dann auf **Suchen**. Klicken Sie in der resultierenden Liste der Agents auf den Benutzer, und klicken Sie dann auf **OK**.
        
          - Wenn Sie einen Benutzer aus der Gruppe Agent entfernen möchten, klicken Sie in der Liste der Agents auf den Benutzer, den Sie entfernen möchten, und klicken Sie dann auf **Entfernen**.
        
          - Um die Reihenfolge zu ändern, in der Agents in Gruppen angeboten werden, die entweder Round Robin-Routing oder serielles Routing verwenden, klicken Sie in der Liste der Agents auf einen Benutzer, und klicken Sie dann auf den nach-oben-oder nach-unten-Pfeil.
    
      - Wenn Sie eine Exchange Server Verteilerliste als Agentgruppe verwenden möchten, klicken Sie auf **vorhandene e-Mail-Verteilerliste verwenden**, und geben Sie dann in **Verteilerlisten Adresse**die e-Mail-Adresse der Verteilerliste ein (beispielsweise NetworkSupport@contoso.com).
        
        Wenn Sie eine E-Mail-Verteilerliste verwenden, gelten die folgenden Einschränkungen:
        
          - Sie können für die Agentgruppe nicht mehrere Verteilerlisten auswählen. Jede Gruppe unterstützt nur eine Verteilerliste.
        
          - Falls die Verteilerliste eine oder mehrere Verteilerlisten enthält, werden die Mitglieder der verschachtelten Verteilerlisten nicht der Agentliste hinzugefügt.
        
          - Wenn Serial oder Round Robin Routing ausgewählt ist, bietet der Server einen eingehenden Anruf an den entsprechenden Agent entsprechend der Routingmethode und entsprechend der Reihenfolge, in der Agents in der Verteilerliste aufgeführt sind.
        
          - Wenn die Verteilerliste Benutzer enthält, für die lync Server 2010 aktiviert ist, Enterprise-VoIP jedoch nicht aktiviert ist, werden Sie als dysfunktionale Agents der Gruppe Agent hinzugefügt. Stellen Sie sicher, dass für alle Mitglieder der Verteilerliste Enterprise-VoIP für ihre Benutzerkonten aktiviert ist.
        
        <div>
        

        > [!IMPORTANT]  
        > Wenn Sie eine e-Mail-Verteilerliste verwenden, werden ausgeblendete Mitgliedschaften oder ausgeblendete Listen möglicherweise für den Administrator oder die Benutzer der Reaktionsgruppe angezeigt.

        
        </div>
        
        Verborgene Mitgliedschaften oder Listen werden unter den folgenden Umständen sichtbar:
        
          - Wenn eine Verteilerliste so konfiguriert wurde, dass die Mitgliedschaft ausgeblendet ist und der Reaktionsgruppen Administrator die Verteilerliste der Agentliste zuordnet, können Benutzer die Gruppe aufrufen, um herauszufinden, wer die Mitglieder sind.
        
          - Wenn eine Verteilerliste so konfiguriert wurde, dass Sie in der globalen Exchange-Adressliste ausgeblendet ist, kann der Reaktionsgruppen Administrator möglicherweise die Verteilerliste anzeigen und Sie der Liste Agent zuweisen, wenn der Reaktionsgruppen Prozess über die entsprechenden Benutzerrechte verfügt und Berechtigungen, auch wenn der Administrator nicht über die entsprechenden Benutzerrechte und-Berechtigungen verfügt.

11. Klicken Sie auf **Commit ausführen**.

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-an-agent-group"></a>So verwenden Sie Windows PowerShell zum Erstellen oder Ändern einer Agentgruppe

1.  Melden Sie sich als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Verwenden Sie **New-CsRgsAgentGroup** , um eine neue Agentengruppe zu erstellen. Verwenden Sie zum Ändern einer vorhandenen Agentgruppe die Datei " **CsRgsAgentGroup** ". Führen Sie an der Eingabeaufforderung Folgendes aus:
    
        New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
    
    Beispiel:
    
        New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
    
    <div>
    

    > [!IMPORTANT]  
    > Die Einstellung für die Agent-Warnungszeit darf 180 Sekunden nicht überschreiten. Wenn die Agent-Warnungszeit größer als 180 Sekunden ist, lehnt die Clientanwendung den Anruf ab, da der SIP-Transaktionszeitgeber seine maximale Wartezeit erreicht.

    
    </div>

4.  Vergewissern Sie sich, dass die Agentgruppe erstellt wurde. Ausführen
    
        Get-CsRgsAgentGroup -Name "Help Desk"

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Löschen einer Agentengruppe in lync Server 2013](lync-server-2013-delete-an-agent-group.md)  


[Verwalten von Reaktionsgruppen-Agentgruppen in lync Server 2013](lync-server-2013-managing-response-group-agent-groups.md)  
[Get-CsService](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[New-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup)  
[Gruppe-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsAgentGroup)  
[Get-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsAgentGroup)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

