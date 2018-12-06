---
title: 'Lync Server 2013: Erstellen oder Ändern einer Agent-Gruppe'
TOCTitle: Erstellen oder Ändern einer Agent-Gruppe
ms:assetid: f1461fff-51c1-4f4b-9311-8cba02c333fc
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205370(v=OCS.15)
ms:contentKeyID: 49295862
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen oder Ändern einer Agent-Gruppe in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2014-02-07_

Verwenden Sie eines der folgenden Verfahren, um eine Agentgruppe zu erstellen oder zu ändern.


> [!NOTE]
> Ein Administrator \endash z.&nbsp;B. <STRONG>CsVoiceAdministrator</STRONG> \endash muss Benutzer für Enterprise-VoIP und Lync Server aktivieren, bevor die Benutzer Agentgruppen zugewiesen werden können. Wenn Sie einer der delegierten Reaktionsgruppenleiter für einen verwalteten Workflow sind, können Sie Agentgruppen erstellen und in den von Ihnen verwalteten Workflows verwenden.




> [!IMPORTANT]
> Wenn Sie Benutzer als Reaktionsgruppenagents zuweisen, weisen Sie diese darauf hin, dass sie bei aktiviertem Datenschutzmodus nach "RGS-Anwesenheitsmonitor"-Kontakten suchen und sie ihrer Kontaktliste hinzufügen müssen. Agents, deren Datenschutzmodus aktiviert ist, die jedoch "RGS-Anwesenheitsmonitor" nicht in ihre Kontaktliste aufgenommen haben, können keine Anrufe bei der Reaktionsgruppe annehmen. Agents, deren Datenschutzmodus nicht aktiviert ist, sind davon nicht betroffen.



## So verwenden Sie die Lync Server-Systemsteuerung zum Erstellen oder Ändern einer Agent-Gruppe

1.  Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.
    

    > [!NOTE]
    > Wenn Sie einer der delegierten Reaktionsgruppenleiter für einen verwalteten Workflow sind, können Sie Gruppen erstellen und in den von Ihnen verwalteten Workflows verwenden.



2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **Reaktionsgruppen** und dann auf **Gruppe** .

4.  Führen Sie auf der Seite **Gruppe** einen der folgenden Schritte aus:
    
      - Zum Erstellen einer neuen Agentgruppe klicken Sie auf **Neu** . Geben Sie im Suchfeld **Dienst auswählen** den Namen des **ApplicationServer** -Diensts, dem Sie die Gruppe hinzufügen möchten, ganz oder teilweise ein. Klicken Sie in der nun angezeigten Liste der Dienst auf den gewünschen Dienst, und klicken Sie dann auf **OK** .
    
      - Wenn Sie einen vorhandenen Agentgruppe ändern möchten, geben Sie im Suchfeld den Namen der Agentgruppe ganz oder teilweise ein. Klicken Sie in der nun angezeigten Liste auf die gewünschte Gruppe, dann auf **Bearbeiten** und anschließend auf **Details anzeigen** .

5.  Geben Sie im Feld **Name** einen aussagekräftigen Namen für die Agentgruppe ein.

6.  Geben Sie in **Beschreibung** eine Beschreibung für die Gruppe ein.

7.  Wählen Sie unter **Beteiligungsrichtlinie** eine der folgenden Einstellungen aus, um das Anmeldeverhalten für die Gruppe einzurichten:
    
      - Wählen Sie **Informell** , um anzugeben, dass Agents in der Gruppe sich bei der Gruppe weder an- noch abmelden müssen. Die Agents werden bei der Anmeldung an Lync Server 2013 automatisch bei der Gruppe angemeldet.
    
      - klicken Sie auf **Formell** , um festzulegen, dass sich die Agents der Gruppe bei der Gruppe an- oder abmelden müssen. Wenn Sie diese Option aktivieren, klicken Agents auf eine Menüoption in Lync, um Internet Explorer zu öffnen und eine Webseitenkonsole zur An- und Abmeldung bei der Gruppe anzuzeigen.

8.  Geben Sie im Feld **Agentwarnungszeit (Sekunden)** an, wie lange das Telefon eines Agents klingelt, bevor der Anruf an den nächsten verfügbaren Agent übergeben wird (die Standardeinstellung ist 20 Sekunden).
    

    > [!IMPORTANT]
    > Die Einstellung für die Agentwarnungszeit darf 180&nbsp;Sekunden nicht überschreiten. Andernfalls weist die Clientanwendung den Anruf zurück, weil der Zeitgeber für die SIP-Transaktion die maximale Wartezeit erreicht.



9.  Wählen Sie unter **Routingmethode** aus, wie Anrufe an die Agents in der Gruppe weitergeleitet werden:
    
      - Aktivieren Sie die Option **Längster Leerlauf** , um einen neuen Anruf demjenigen Agent mit der längsten Leerlaufzeit (Anwesenheitsstatus **Verfügbar** oder **Inaktiv** in Lync Server) anzubieten.
    
      - Klicken Sie auf **Parallel** , um einen neuen Anruf simultan allen verfügbaren Agents anzubieten. Der Anruf wird an den ersten Agent übergeben, der diesen annimmt.
    
      - Wenn Sie einen neuen Anruf den einzelnen Agents nacheinander anbieten möchten, klicken Sie auf **Roundrobin** .
    
      - Wenn Sie einen neuen Anruf den Agents immer in der Reihenfolge anbieten möchten, in der sie auf der Registerkarte **Agent** aufgeführt sind, klicken Sie auf **Seriell** .
    
      - Wenn neue Anrufe allen Agents (unabhängig von ihrem aktuellen Anwesenheitsstatus) angeboten werden sollen, die sowohl an Lync Server 2013 als auch an der Reaktionsgruppenanwendung angemeldet sind, klicken Sie auf **Attendant** . Lync 2010-Vermittlung-Benutzer, die als Agents konfiguriert sind, können alle wartenden Anrufe sehen und in beliebiger Reihenfolge annehmen. Der Anruf wird an den ersten Agent übergeben, der den Anruf annimmt, woraufhin er den weiteren Lync 2010-Vermittlung-Benutzern nicht mehr angezeigt wird.

10. Geben Sie auf der Registerkarte **Agents** an, wie Sie Ihre Agentliste erstellen möchten:
    
      - Um eine benutzerdefinierte Liste von Agents zu verwenden, klicken Sie auf **Eine benutzerdefinierte Gruppe von Agents definieren** . Führen Sie anschließend einen der folgenden Schritte aus:
        
          - Zum Hinzufügen eines Benutzers zur Agentgruppe klicken Sie auf **Auswählen** , und geben Sie dann im Suchfeld **Agents auswählen** einen Teil oder den vollständigen Namen des Benutzers ein, der zu dieser Gruppe hinzugefügt werden soll. Klicken Sie anschließend auf **Suchen** . Klicken Sie in der Ergebnisliste auf den betreffenden Benutzer und dann auf **OK** .
        
          - Zum Entfernen eines Benutzers aus der Agentgruppe klicken Sie in der Liste der Agents auf den Benutzer, der entfernt werden soll, und anschließend auf **Entfernen** .
        
          - Zum Ändern der Reihenfolge, in der Agents Anrufe in Gruppen angeboten werden, die entweder Roundrobinrouting oder serielles Routing verwenden, klicken Sie in der Liste der Agents auf einen Benutzer und dann auf den Pfeil nach oben oder den Pfeil nach unten.
    
      - Zum Verwenden einer Microsoft Exchange Server-Verteilerliste als Agentgruppe klicken Sie auf **Eine vorhandene E-Mail-Verteilerliste verwenden** , und geben Sie dann in **Adresse der Verteilerliste** die E-Mail-Adresse der Verteilerliste an (z. B. NetzwerkSupport@contoso.com).
        
        Wenn Sie eine E-Mail-Verteilerliste verwenden, gelten die folgenden Einschränkungen:
        
          - Sie können für die Agentgruppe nicht mehrere Verteilerlisten auswählen. Jede Gruppe unterstützt nur eine Verteilerliste.
        
          - Falls die Verteilerliste eine oder mehrere Verteilerlisten enthält, werden die Mitglieder der verschachtelten Verteilerlisten nicht der Agentliste hinzugefügt.
        
          - Wenn serielles Routing oder Roundrobinrouting ausgewählt ist, leitet der Server einen eingehenden Anruf gemäß Routingmethode und Reihenfolge, in der Agents auf der Verteilerliste angegeben sind, an den geeigneten Agent weiter.
        
          - Wenn die Verteilerliste Benutzer enthält, für die Lync Server 2010 aktiviert, aber Enterprise Voice nicht aktiviert ist, werden diese der Agent-Gruppe als dysfunktionelle Agents hinzugefügt. Stellen Sie sicher, dass für alle Mitglieder in der Verteilerliste Enterprise Voice für die Benutzerkonten aktiviert ist.
        

        > [!IMPORTANT]
        > Wenn Sie eine E-Mail-Verteilerliste verwenden, können verborgene Mitgliedschaften oder verborgene Listen für den Administrator oder die Benutzer der Reaktionsgruppe sichtbar werden.

        
        Verborgene Mitgliedschaften oder Listen werden unter den folgenden Umständen sichtbar:
        
          - Wenn eine Verteilerliste so konfiguriert wurde, dass die Mitgliedschaft verborgen ist und der Reaktionsgruppen-Administrator die Verteilerliste der Agentliste zuweist, können Benutzer die Gruppe aufrufen, um herauszufinden, wer die Mitglieder sind.
        
          - Wenn eine Verteilerliste so konfiguriert wurde, dass sie in der globalen Adressliste von Exchange verborgen ist, könnte der Reaktionsgruppen-Administrator die Verteilerliste sehen und der Agentliste zuweisen, wenn der Reaktionsgruppenprozess über die geeigneten Benutzerrechte und -berechtigungen verfügt, selbst dann, wenn der Administrator nicht die erforderlichen Benutzerrechte und -berechtigungen hat.

11. Klicken Sie auf **Commit** .

## So verwenden Sie die Windows PowerShell zum Erstellen oder Ändern einer Agent-Gruppe

1.  Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Verwenden Sie **New-CsRgsAgentGroup**, um eine neue Agentgruppe zu erstellen. Zum Ändern einer vorhandenen Agentgruppe verwenden Sie **Set-CsRgsAgentGroup**. Führen Sie an der Eingabeaufforderung folgenden Befehl aus:
    
        New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
    
    Beispiel:
    
        New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
    

    > [!IMPORTANT]
    > Die Einstellung für die Agentwarnungszeit darf 180&nbsp;Sekunden nicht überschreiten. Andernfalls weist die Clientanwendung den Anruf zurück, weil der Zeitgeber für die SIP-Transaktion die maximale Wartezeit erreicht.



4.  Vergewissern Sie sich, dass die Agentgruppe erstellt worden ist. Führen Sie folgenden Befehl aus:
    
        Get-CsRgsAgentGroup -Name "Help Desk"

## Siehe auch

#### Aufgaben

[Löschen einer Agentgruppe](lync-server-2013-delete-an-agent-group.md)  

#### Weitere Ressourcen

[Verwalten von Agentgruppen für Reaktionsgruppen](lync-server-2013-managing-response-group-agent-groups.md)  
[Get-CsService](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsService)  
[New-CsRgsAgentGroup](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsAgentGroup)  
[Set-CsRgsAgentGroup](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsRgsAgentGroup)  
[Get-CsRgsAgentGroup](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsRgsAgentGroup)

