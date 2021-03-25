---
title: Erstellen oder Ändern einer Agentgruppe in Skype for Business
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
ms.assetid: f1461fff-51c1-4f4b-9311-8cba02c333fc
description: Erstellen oder Ändern einer Agentgruppe in reaktionsgruppe, in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: 0c0e7d54008ba6affa2bae5bd3228c93e430a114
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51105811"
---
# <a name="create-or-modify-an-agent-group-in-skype-for-business"></a>Erstellen oder Ändern einer Agentgruppe in Skype for Business
 
Erstellen oder Ändern einer Agentgruppe in reaktionsgruppe, in Skype for Business Server Enterprise-VoIP.
  
Beim Erstellen einer Agentgruppe wählen Sie die Agents aus, die der Gruppe zugewiesen werden. Außerdem geben Sie zusätzliche Gruppeneinstellungen (beispielsweise die Routingmethode) an und legen fest, ob sich ein Agent bei der Gruppe an- und abmelden muss. 
  
Ein Agent, der sich bei der Gruppe anmelden und abmelden muss, was sich von der Anmeldung oder Abmelden von Skype for Business abhing, wird als formaler Agent bezeichnet. Formelle Agents müssen sich bei der Gruppe anmelden, um an die Gruppe weitergeleitete Anrufe empfangen zu können. Dies kann für Agents nützlich sein, die Anrufe der Gruppe nur zeitweise annehmen. Formale Agents melden sich an und aus ihren Gruppen, indem sie in Skype for Business auf ein Menüelement klicken, um den Windows Internet Explorer-Internetbrowser zu öffnen und eine Webseitenkonsole anzuzeigen.
  
Ein Agent, der sich nicht oder nicht aus der Gruppe anmeldet, wird als informeller Agent bezeichnet. Informelle Agents werden automatisch bei der Gruppe angemeldet, wenn sie sich bei Skype for Business anmelden, und sie können sich nicht aus der Gruppe abmelden.
  
Nur lokale Benutzer können Agents sein. Wenn ein Agent von einer lokalen zu einer Onlinebereitstellung verschoben wird, werden Reaktionsgruppenanrufe nicht an diesen Agent weitergeleitet.
  
Verwenden Sie eines der folgenden Verfahren, um eine Agentgruppe zu erstellen oder zu ändern.
  
> [!IMPORTANT]
> Wenn Sie Benutzer als Reaktionsgruppenagents zuweisen, weisen Sie diese darauf hin, dass sie bei aktiviertem Datenschutzmodus nach "RGS-Anwesenheitsmonitor"-Kontakten suchen und sie ihrer Kontaktliste hinzufügen müssen. Agents, deren Datenschutzmodus aktiviert ist, die jedoch "RGS-Anwesenheitsmonitor" nicht in ihre Kontaktliste aufgenommen haben, können keine Anrufe bei der Reaktionsgruppe annehmen. Agents, deren Datenschutzmodus nicht aktiviert ist, sind davon nicht betroffen. 
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-an-agent-group"></a>So verwenden Sie die Skype for Business Server-Systemsteuerung zum Erstellen oder Ändern einer Agentgruppe

1. Melden Sie sich als Mitglied der Gruppe RTCUniversalServerAdmins oder als Mitglied einer der vordefinierten Administrativen Rollen an, die die Reaktionsgruppe unterstützen.
    
    > [!NOTE]
    > Wenn Sie einer der delegierten Reaktionsgruppenmanager für einen verwalteten Workflow sind, können Sie Gruppen erstellen und in den von Ihnen verwalteten Workflows verwenden. 
  
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen.  
    
3. Klicken Sie in der linken Navigationsleiste auf **Reaktionsgruppen** und dann auf **Gruppe**.
    
4. Gehen Sie **auf** der Seite Gruppe wie folgt vor:
    
   - Klicken Sie auf Neu, um eine neue Agentgruppe **zu erstellen.** Geben Sie **im Suchfeld** Dienst auswählen den Namen des **ApplicationServer-Diensts** ganz oder teilweise ein, in den Sie die Gruppe hinzufügen möchten. Klicken Sie in der Dienstliste auf den gewünschten Dienst, und klicken Sie dann auf **OK**.
    
   - Geben Sie zum Ändern einer vorhandenen Agentgruppe den Namen der Agentgruppe ganz oder teilweise in das Suchfeld ein. Klicken Sie in der resultierenden Liste auf die gruppe, die Sie möchten, klicken Sie auf **Bearbeiten** und dann **auf Details anzeigen**.
    
5. Geben **Sie unter Name** einen identifizierenden Namen für die Agentgruppe ein.
    
6. Geben Sie in **Beschreibung** eine Beschreibung für die Gruppe ein.
    
7. Wählen Sie unter **Beteiligungsrichtlinie** eine der folgenden Einstellungen aus, um das Anmeldeverhalten für die Gruppe einzurichten:
    
   - Wählen Sie **Informell**, um anzugeben, dass Agents in der Gruppe sich bei der Gruppe weder an- noch abmelden müssen. Agents werden automatisch bei der Gruppe angemeldet, wenn sie sich bei Skype for Business anmelden.
    
   - klicken Sie auf **Formell**, um festzulegen, dass sich die Agents der Gruppe bei der Gruppe an- oder abmelden müssen. Wenn Sie diese Option auswählen, klicken Agents in Skype for Business auf ein Menüelement, um Internet Explorer zu öffnen und eine Webseitenkonsole zum Anmelden und Abstellen der Gruppe anzuzeigen.
    
8. Geben Sie im Feld **Agentwarnungszeit (Sekunden)** an, wie lange das Telefon eines Agents klingelt, bevor der Anruf an den nächsten verfügbaren Agent übergeben wird (die Standardeinstellung ist 20 Sekunden).
    
    > [!IMPORTANT]
    > Die Einstellung für die Agentbenachrichtigungszeit darf 180 Sekunden nicht überschreiten. Wenn die Agentbenachrichtigungszeit 180 Sekunden überschreitet, lehnt die Clientanwendung den Aufruf ab, da der SIP-Transaktionstimer die maximale Wartezeit erreicht. 
  
9. Wählen Sie unter **Routingmethode** aus, wie Anrufe an die Agents in der Gruppe weitergeleitet werden:
    
   - Klicken Sie auf Längster Leerlauf, um dem Agent, der  am längsten im Leerlauf war (war in Skype for Business am längsten verfügbar oder **inaktiv)** einen neuen Anruf zu **bieten.** 
    
   - Klicken Sie auf **Parallel**, um einen neuen Anruf simultan allen verfügbaren Agents anzubieten. Der Anruf wird an den ersten Agent übergeben, der diesen annimmt.
    
   - Wenn Sie einen neuen Anruf den einzelnen Agents nacheinander anbieten möchten, klicken Sie auf **Roundrobin**. 
    
   - Wenn Sie einen neuen Anruf den Agents immer in der Reihenfolge anbieten möchten, in der sie auf der Registerkarte **Agent** aufgeführt sind, klicken Sie auf **Seriell**. 
    
   - Klicken Sie auf **Telefonkonferenz,** um allen Agents, die bei Skype for Business und der Reaktionsgruppe-Anwendung gleichzeitig angemeldet sind, unabhängig von ihrer aktuellen Anwesenheit einen neuen Anruf zu bieten. Benutzer, die als Agents konfiguriert sind, können alle Warte- und Antwortanrufe in beliebiger Reihenfolge sehen. Der Anruf wird an den ersten Agent gesendet, der ihn annimmt, nach dem die anderen Agents den Anruf nicht mehr sehen.
    
10. Geben Sie auf der Registerkarte **Agents** an, wie Sie Ihre Agentliste erstellen möchten:
    
    - Klicken Sie zum Verwenden einer benutzerdefinierten Liste von Agents auf Benutzerdefinierte Gruppe von Agents **definieren,** und gehen Sie wie folgt vor:
    
    - Klicken Sie zum Hinzufügen eines Benutzers zur Agentgruppe  auf Auswählen **,** und geben Sie dann im Suchfeld Agents auswählen den Namen des Benutzers, den Sie dieser Gruppe hinzufügen möchten, ganz oder teilweise ein, und klicken Sie dann auf **Suchen**. Klicken Sie in der resultierenden Liste der Agents auf den Benutzer, und klicken Sie dann auf **OK**.
    
    - Um einen Benutzer aus der Agentgruppe zu entfernen, klicken Sie in der Liste der Agents auf den Benutzer, den Sie entfernen möchten, und klicken Sie dann auf **Entfernen**.
    
    - Um die Reihenfolge zu ändern, in der Agents Anrufe in Gruppen angeboten werden, die entweder Roundrobinrouting oder serielles Routing verwenden, klicken Sie in der Liste der Agents auf einen Benutzer, und klicken Sie dann auf den Pfeil nach oben oder nach unten. 
    
    - Um eine Microsoft Exchange Server Verteilerliste als Agentgruppe zu verwenden, klicken Sie auf Vorhandene E-Mail-Verteilerliste **verwenden,** und geben Sie dann unter Verteilerlistenadresse die E-Mail-Adresse der Verteilerliste ein (z. B. NetworkSupport@contoso.com).
    
      Wenn Sie eine E-Mail-Verteilerliste verwenden, gelten die folgenden Einschränkungen:
    
      - Sie können für die Agentgruppe nicht mehrere Verteilerlisten auswählen. Jede Gruppe unterstützt nur eine Verteilerliste.
    
      - Falls die Verteilerliste eine oder mehrere Verteilerlisten enthält, werden die Mitglieder der verschachtelten Verteilerlisten nicht der Agentliste hinzugefügt.
    
      - Wenn serielles Routing oder Roundrobinrouting ausgewählt ist, bietet der Server einen eingehenden Anruf an den entsprechenden Agent gemäß der Routingmethode und entsprechend der Reihenfolge, in der Agents in der Verteilerliste aufgeführt sind.
    
      - Wenn die Verteilerliste Benutzer enthält, für die Lync Server 2010 aktiviert ist, Enterprise-VoIP nicht aktiviert ist, werden sie der Agentgruppe als dysfunktionale Agents hinzugefügt. Stellen Sie sicher, dass alle Mitglieder der Verteilerliste Enterprise-VoIP für ihre Benutzerkonten aktiviert sind.
    
    > [!IMPORTANT]
    > Wenn Sie eine E-Mail-Verteilerliste verwenden, werden ausgeblendete Mitgliedschaften oder ausgeblendete Listen möglicherweise für den Administrator oder die Benutzer der Reaktionsgruppe sichtbar. 
  
    Verborgene Mitgliedschaften oder Listen werden unter den folgenden Umständen sichtbar:
    
     - Wenn eine Verteilerliste so konfiguriert wurde, dass die Mitgliedschaft ausgeblendet ist und der Administrator der Reaktionsgruppe die Verteilerliste der Agentliste zurkennt, können Benutzer die Gruppe aufrufen, um herauszufinden, wer die Mitglieder sind. 
    
     - Wenn eine Verteilerliste so konfiguriert wurde, dass sie in der globalen Adressliste von Exchange ausgeblendet ist, kann der Administrator der Reaktionsgruppe die Verteilerliste möglicherweise sehen und der Agentliste zuweisen, wenn der Reaktionsgruppesprozess über die entsprechenden Benutzerrechte und -berechtigungen verfügt, auch wenn der Administrator nicht über die entsprechenden Benutzerrechte und -berechtigungen verfügt.
    
11. Klicken Sie auf **Commit ausführen**.
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-an-agent-group"></a>So verwenden Sie die Skype for Business Server-Verwaltungsshell zum Erstellen oder Ändern einer Agentgruppe

1. Melden Sie sich als Mitglied der Gruppe RTCUniversalServerAdmins oder als Mitglied einer der vordefinierten Administrativen Rollen an, die die Reaktionsgruppe unterstützen.
    
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start,** klicken Sie auf **Alle Programme,** **klicken Sie auf Skype for Business 2015,** und klicken Sie dann auf **Skype for Business Server Management Shell**.
    
3. Verwenden **Sie New-CsRgsAgentGroup,** um eine neue Agentgruppe zu erstellen. Verwenden **Sie Set-CsRgsAgentGroup,** um eine vorhandene Agentgruppe zu ändern. Führen Sie an der Eingabeaufforderung Folgendes aus:
    
   ```powershell
   New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
   ```

    Beispiel:
    
   ```powershell
   New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
   ```

    > [!IMPORTANT]
    > Die Einstellung für die Agentbenachrichtigungszeit darf 180 Sekunden nicht überschreiten. Wenn die Agentbenachrichtigungszeit größer als 180 Sekunden ist, lehnt die Clientanwendung den Aufruf ab, da der SIP-Transaktionstimer seine maximale Wartezeit erreicht. 
  
4. Vergewissern Sie sich, dass die Agentgruppe erstellt wurde. Führen Sie  aus.
    
   ```powershell
   Get-CsRgsAgentGroup -Name "Help Desk"
   ```

## <a name="see-also"></a>Siehe auch

[Get-CsService](/powershell/module/skype/get-csservice?view=skype-ps)
  
[New-CsRgsAgentGroup](/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)
  
[Set-CsRgsAgentGroup](/powershell/module/skype/set-csrgsagentgroup?view=skype-ps)
  
[Get-CsRgsAgentGroup](/powershell/module/skype/get-csrgsagentgroup?view=skype-ps)