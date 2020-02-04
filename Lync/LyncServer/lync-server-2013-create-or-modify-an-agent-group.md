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
ms.openlocfilehash: 99fed5bf80979ef807f45ce7e5ecdc8e8a16329b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739555"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-an-agent-group-in-lync-server-2013"></a>Erstellen oder Ändern einer Agentengruppe in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-02-07_

Verwenden Sie eines der folgenden Verfahren, um eine Agentgruppe zu erstellen oder zu ändern.

<div>


> [!NOTE]  
> Ein Administrator – beispielsweise CsVoiceAdministrator – muss Benutzer für Enterprise-VoIP und lync Server aktivieren, bevor die Benutzeragenten Gruppen zugewiesen werden können. Wenn Sie einer der Delegierten Antwortgruppen-Manager für einen verwalteten Workflow sind, können Sie Agentengruppen erstellen und die Agentengruppen in den von Ihnen verwalteten Workflows verwenden.



</div>

<div>


> [!IMPORTANT]  
> Wenn Sie Benutzer als Reaktionsgruppenagents zuweisen, weisen Sie diese darauf hin, dass sie bei aktiviertem Datenschutzmodus nach „RGS-Anwesenheitsmonitor“-Kontakten suchen und sie ihrer Kontaktliste hinzufügen müssen. Agents, deren Datenschutzmodus aktiviert ist, die jedoch „RGS-Anwesenheitsmonitor“ nicht in ihre Kontaktliste aufgenommen haben, können keine Anrufe bei der Reaktionsgruppe annehmen. Agents, deren Datenschutzmodus nicht aktiviert ist, sind davon nicht betroffen.



</div>

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-an-agent-group"></a>So verwenden Sie die lync Server-Systemsteuerung zum Erstellen oder Ändern einer Agentengruppe

1.  Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie einer der delegierten Reaktionsgruppenleiter für einen verwalteten Workflow sind, können Sie Gruppen erstellen und in den von Ihnen verwalteten Workflows verwenden.

    
    </div>

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **Reaktionsgruppen** und dann auf **Gruppe**.

4.  Führen Sie auf der Seite **Gruppe** einen der folgenden Schritte aus:
    
      - Zum Erstellen einer neuen Agentgruppe klicken Sie auf **Neu**. Geben Sie im Suchfeld **Dienst auswählen** den Namen des **ApplicationServer**-Diensts, dem Sie die Gruppe hinzufügen möchten, ganz oder teilweise ein. Klicken Sie in der nun angezeigten Liste der Dienst auf den gewünschten Dienst und klicken Sie dann auf **OK**.
    
      - Wenn Sie eine vorhandene Agentgruppe ändern möchten, geben Sie im Suchfeld den Namen der Agentgruppe ganz oder teilweise ein. Klicken Sie in der nun angezeigten Liste auf die gewünschte Gruppe, dann auf **Bearbeiten** und anschließend auf **Details anzeigen**.

5.  Geben Sie im Feld **Name** einen aussagekräftigen Namen für die Agentgruppe ein.

6.  Geben Sie in **Beschreibung** eine Beschreibung für die Gruppe ein.

7.  Wählen Sie unter **Beteiligungsrichtlinie** eine der folgenden Einstellungen aus, um das Anmeldeverhalten für die Gruppe einzurichten:
    
      - Wählen Sie **Informell**, um anzugeben, dass Agents in der Gruppe sich bei der Gruppe weder an- noch abmelden müssen. Agents werden bei der Anmeldung bei lync Server 2013 automatisch bei der Gruppe angemeldet.
    
      - Klicken Sie auf **Formell**, um festzulegen, dass sich die Agents der Gruppe bei der Gruppe an- oder abmelden müssen. Wenn Sie diese Option auswählen, klicken Sie in lync auf ein Menüelement, um Internet Explorer zu öffnen und eine Webseite-Konsole zum ein-und Ausloggen der Gruppe anzuzeigen.

8.  Geben Sie im Feld **Agentwarnungszeit (Sekunden)** an, wie lange das Telefon eines Agents klingelt, bevor der Anruf an den nächsten verfügbaren Agent übergeben wird (die Standardeinstellung ist 20 Sekunden).
    
    <div>
    

    > [!IMPORTANT]  
    > Die Einstellung für die Agentwarnungszeit darf 180 Sekunden nicht überschreiten. Andernfalls weist die Clientanwendung den Anruf zurück, weil der Zeitgeber für die SIP-Transaktion die maximale Wartezeit erreicht.

    
    </div>

9.  Wählen Sie unter **Routingmethode** aus, wie Anrufe an die Agents in der Gruppe weitergeleitet werden:
    
      - Wenn Sie einen neuen Anruf zuerst an den Agenten anbieten möchten, der am längsten inaktiv war (in lync Server am längsten **vorhanden** oder **inaktiv** war), klicken Sie auf am längsten **Leerlauf**.
    
      - Klicken Sie auf **Parallel**, um einen neuen Anruf simultan allen verfügbaren Agents anzubieten. Der Anruf wird an den ersten Agent übergeben, der diesen annimmt.
    
      - Wenn Sie einen neuen Anruf den einzelnen Agents nacheinander anbieten möchten, klicken Sie auf **Roundrobin**.
    
      - Wenn Sie einen neuen Anruf den Agents immer in der Reihenfolge anbieten möchten, in der sie auf der Registerkarte **Agent** aufgeführt sind, klicken Sie auf **Seriell**.
    
      - Wenn Sie allen Agents einen neuen Anruf anbieten möchten, die bei lync Server 2013 und der reaktionsgruppenanwendung gleichzeitig angemeldet sind, klicken Sie unabhängig von Ihrem aktuellen Anwesenheitsstatus auf **Attendant**. Benutzer von lync 2010 Attendant, die als Agents konfiguriert sind, können alle Anrufe sehen, die warten, und wartende Anrufe in beliebiger Reihenfolge beantworten. Der Anruf wird an den ersten Agenten gesendet, der ihn annimmt, nach dem die anderen lync 2010 Attendant-Benutzer den Anruf nicht mehr sehen.

10. Geben Sie auf der Registerkarte **Agents** an, wie Sie Ihre Agentliste erstellen möchten:
    
      - Um eine benutzerdefinierte Liste von Agents zu verwenden, klicken Sie auf **Eine benutzerdefinierte Gruppe von Agents definieren**. Führen Sie anschließend einen der folgenden Schritte aus:
        
          - Zum Hinzufügen eines Benutzers zur Agentgruppe klicken Sie auf **Agents Auswählen** und geben Sie dann im Suchfeld **Agents auswählen** einen Teil oder den vollständigen Namen des Benutzers ein, der zu dieser Gruppe hinzugefügt werden soll. Klicken Sie anschließend auf **Suchen**. Klicken Sie in der Ergebnisliste auf den betreffenden Benutzer und dann auf **OK**.
        
          - Zum Entfernen eines Benutzers aus der Agentgruppe klicken Sie in der Liste der Agents auf den Benutzer, der entfernt werden soll und anschließend auf **Entfernen**.
        
          - Zum Ändern der Reihenfolge, in der Agents Anrufe in Gruppen angeboten werden, die entweder Roundrobinrouting oder serielles Routing verwenden, klicken Sie in der Liste der Agents auf einen Benutzer und dann auf den Pfeil nach oben oder den Pfeil nach unten.
    
      - Zum Verwenden einer Microsoft Exchange Server-Verteilerliste als Agentgruppe klicken Sie auf **Eine vorhandene E-Mail-Verteilerliste verwenden** und geben Sie dann in **Adresse der Verteilerliste** die E-Mail-Adresse der Verteilerliste an (z. B. NetzwerkSupport@contoso.com).
        
        Wenn Sie eine E-Mail-Verteilerliste verwenden, gelten die folgenden Einschränkungen:
        
          - Sie können für die Agentgruppe nicht mehrere Verteilerlisten auswählen. Jede Gruppe unterstützt nur eine Verteilerliste.
        
          - Falls die Verteilerliste eine oder mehrere Verteilerlisten enthält, werden die Mitglieder der verschachtelten Verteilerlisten nicht der Agentliste hinzugefügt.
        
          - Wenn serielles Routing oder Roundrobinrouting ausgewählt ist, leitet der Server einen eingehenden Anruf gemäß Routingmethode und Reihenfolge, in der Agents auf der Verteilerliste angegeben sind, an den geeigneten Agent weiter.
        
          - Wenn die Verteilerliste Benutzer enthält, für die Lync Server 2010 aktiviert, aber Enterprise Voice nicht aktiviert ist, werden diese der Agentgruppe als dysfunktionelle Agents hinzugefügt. Stellen Sie sicher, dass für alle Mitglieder in der Verteilerliste Enterprise Voice für die Benutzerkonten aktiviert ist.
        
        <div>
        

        > [!IMPORTANT]  
        > Wenn Sie eine e-Mail-Verteilerliste verwenden, werden ausgeblendete Mitgliedschaften oder ausgeblendete Listen möglicherweise für den Administrator der Reaktionsgruppe oder für Benutzer sichtbar.

        
        </div>
        
        Verborgene Mitgliedschaften oder Listen werden unter den folgenden Umständen sichtbar:
        
          - Wenn eine Verteilerliste so konfiguriert wurde, dass die Mitgliedschaft ausgeblendet ist und der Antwortgruppen Administrator die Verteilerliste der Agentenliste zuordnet, können Benutzer die Gruppe anrufen, um herauszufinden, wer die Mitglieder sind.
        
          - Wenn eine Verteilerliste so konfiguriert wurde, dass Sie in der globalen Exchange-Adressliste ausgeblendet ist, kann der Antwortgruppen Administrator möglicherweise die Verteilerliste sehen und der Agentenliste zuweisen, wenn der Prozess der Reaktionsgruppe die entsprechenden Benutzerrechte aufweist und Berechtigungen, auch wenn der Administrator nicht über die entsprechenden Benutzerrechte und Berechtigungen verfügt.

11. Klicken Sie auf **Commit ausführen**.

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-an-agent-group"></a>So verwenden Sie Windows PowerShell zum Erstellen oder Ändern einer Agentengruppe

1.  Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Verwenden Sie **New-CsRgsAgentGroup**, um eine neue Agentgruppe zu erstellen. Zum Ändern einer vorhandenen Agentgruppe verwenden Sie **Set-CsRgsAgentGroup**. Führen Sie an der Eingabeaufforderung folgenden Befehl aus:
    
        New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
    
    Beispiel:
    
        New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
    
    <div>
    

    > [!IMPORTANT]  
    > Die Einstellung für die Agentwarnungszeit darf 180 Sekunden nicht überschreiten. Andernfalls weist die Clientanwendung den Anruf zurück, weil der Zeitgeber für die SIP-Transaktion die maximale Wartezeit erreicht.

    
    </div>

4.  Vergewissern Sie sich, dass die Agentgruppe erstellt worden ist. Führen Sie folgenden Befehl aus:
    
        Get-CsRgsAgentGroup -Name "Help Desk"

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Löschen einer Agentengruppe in lync Server 2013](lync-server-2013-delete-an-agent-group.md)  


[Verwalten von Reaktionsgruppen-Agentgruppen in lync Server 2013](lync-server-2013-managing-response-group-agent-groups.md)  
[Get-CsService](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[Neu – CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup)  
[Satz-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsAgentGroup)  
[Get-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsAgentGroup)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

