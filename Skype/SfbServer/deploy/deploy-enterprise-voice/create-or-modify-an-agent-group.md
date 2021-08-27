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
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f1461fff-51c1-4f4b-9311-8cba02c333fc
description: Erstellen oder ändern Sie eine Agentgruppe in der Reaktionsgruppe in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: 367e8e752042d7b8585fdae918f747aa77085223
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58589017"
---
# <a name="create-or-modify-an-agent-group-in-skype-for-business"></a>Erstellen oder Ändern einer Agentgruppe in Skype for Business
 
Erstellen oder ändern Sie eine Agentgruppe in der Reaktionsgruppe in Skype for Business Server Enterprise-VoIP.
  
Beim Erstellen einer Agentgruppe wählen Sie die Agents aus, die der Gruppe zugewiesen werden. Außerdem geben Sie zusätzliche Gruppeneinstellungen (beispielsweise die Routingmethode) an und legen fest, ob sich ein Agent bei der Gruppe an- und abmelden muss. 
  
Ein Agent, der sich bei der Gruppe anmelden muss, was sich von der Anmeldung oder Abmeldung von Skype for Business unterscheidet, wird als formeller Agent bezeichnet. Formelle Agents müssen sich bei der Gruppe anmelden, um an die Gruppe weitergeleitete Anrufe empfangen zu können. Dies kann für Agents nützlich sein, die Anrufe der Gruppe nur zeitweise annehmen. Formale Agents melden sich bei ihren Gruppen an, indem sie auf ein Menüelement in Skype for Business klicken, um den Windows Internet Explorer-Internetbrowser zu öffnen und eine Webseitenkonsole anzuzeigen.
  
Ein Agent, der sich nicht bei der Gruppe anmeldet oder sich nicht abmeldet, wird als informeller Agent bezeichnet. Informelle Agents werden automatisch bei der Gruppe angemeldet, wenn sie sich bei Skype for Business anmelden, und sie können sich nicht von der Gruppe abmelden.
  
Nur lokale Benutzer können Agents sein. Wenn ein Agent von einer lokalen zu einer Onlinebereitstellung verschoben wird, werden Reaktionsgruppenanrufe nicht an diesen Agent weitergeleitet.
  
Verwenden Sie eines der folgenden Verfahren, um eine Agentgruppe zu erstellen oder zu ändern.
  
> [!IMPORTANT]
> Wenn Sie Benutzer als Reaktionsgruppenagents zuweisen, weisen Sie diese darauf hin, dass sie bei aktiviertem Datenschutzmodus nach "RGS-Anwesenheitsmonitor"-Kontakten suchen und sie ihrer Kontaktliste hinzufügen müssen. Agents, deren Datenschutzmodus aktiviert ist, die jedoch "RGS-Anwesenheitsmonitor" nicht in ihre Kontaktliste aufgenommen haben, können keine Anrufe bei der Reaktionsgruppe annehmen. Agents, deren Datenschutzmodus nicht aktiviert ist, sind davon nicht betroffen. 
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-an-agent-group"></a>So verwenden Sie Skype for Business Server Systemsteuerung zum Erstellen oder Ändern einer Agentgruppe

1. Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.
    
    > [!NOTE]
    > Wenn Sie einer der delegierten Reaktionsgruppenmanager für einen verwalteten Workflow sind, können Sie Gruppen erstellen und in den von Ihnen verwalteten Workflows verwenden. 
  
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen.  
    
3. Klicken Sie in der linken Navigationsleiste auf **Reaktionsgruppen** und dann auf **Gruppe**.
    
4. Führen Sie auf der Seite **"Gruppe"** eine der folgenden Aktionen aus:
    
   - Klicken Sie auf **"Neu",** um eine neue Agentgruppe zu erstellen. Geben Sie im Suchfeld **"Dienst auswählen"** den Namen des **ApplicationServer-Diensts,** dem Sie die Gruppe hinzufügen möchten, ganz oder teilweise ein. Klicken Sie in der Dienstliste auf den gewünschten Dienst, und klicken Sie dann auf **OK**.
    
   - Um eine vorhandene Agentgruppe zu ändern, geben Sie den Namen der Agentgruppe ganz oder teilweise in das Suchfeld ein. Klicken Sie in der resultierenden Liste auf die gewünschte Gruppe, klicken Sie auf **"Bearbeiten"** und dann auf **"Details anzeigen".**
    
5. Geben Sie in **"Name"** einen identifizierenden Namen für die Agentgruppe ein.
    
6. Geben Sie in **Beschreibung** eine Beschreibung für die Gruppe ein.
    
7. Wählen Sie unter **Beteiligungsrichtlinie** eine der folgenden Einstellungen aus, um das Anmeldeverhalten für die Gruppe einzurichten:
    
   - Wählen Sie **Informell**, um anzugeben, dass Agents in der Gruppe sich bei der Gruppe weder an- noch abmelden müssen. Agents werden automatisch bei der Gruppe angemeldet, wenn sie sich bei Skype for Business anmelden.
    
   - klicken Sie auf **Formell**, um festzulegen, dass sich die Agents der Gruppe bei der Gruppe an- oder abmelden müssen. Wenn Sie diese Option auswählen, klicken Agents in Skype for Business auf ein Menüelement, um Internet Explorer zu öffnen und eine Webseitenkonsole für die Anmeldung an und aus der Gruppe anzuzeigen.
    
8. Geben Sie im Feld **Agentwarnungszeit (Sekunden)** an, wie lange das Telefon eines Agents klingelt, bevor der Anruf an den nächsten verfügbaren Agent übergeben wird (die Standardeinstellung ist 20 Sekunden).
    
    > [!IMPORTANT]
    > Die Einstellung für die Agent-Warnungszeit darf 180 Sekunden nicht überschreiten. Wenn die Agent-Warnungszeit 180 Sekunden überschreitet, lehnt die Clientanwendung den Anruf ab, da der Timer der SIP-Transaktion die maximale Wartezeit erreicht. 
  
9. Wählen Sie unter **Routingmethode** aus, wie Anrufe an die Agents in der Gruppe weitergeleitet werden:
    
   - Klicken Sie auf **"Längster Leerlauf",** um einen neuen Anruf zuerst dem Agent anzubieten, der sich am längsten im Leerlauf befand (in Skype for Business am längsten war, ob **"Verfügbar"** oder **"Inaktiv"** vorhanden war). 
    
   - Klicken Sie auf **Parallel**, um einen neuen Anruf simultan allen verfügbaren Agents anzubieten. Der Anruf wird an den ersten Agent übergeben, der diesen annimmt.
    
   - Wenn Sie einen neuen Anruf den einzelnen Agents nacheinander anbieten möchten, klicken Sie auf **Roundrobin**. 
    
   - Wenn Sie einen neuen Anruf den Agents immer in der Reihenfolge anbieten möchten, in der sie auf der Registerkarte **Agent** aufgeführt sind, klicken Sie auf **Seriell**. 
    
   - Klicken Sie auf **"Telefonzentrale",** um allen Agents, die gleichzeitig bei Skype for Business und der Reaktionsgruppenanwendung angemeldet sind, unabhängig von ihrer aktuellen Anwesenheit einen neuen Anruf anzubieten. Benutzer, die als Agents konfiguriert sind, können alle Warte- und Antwortanrufe in beliebiger Reihenfolge sehen. Der Anruf wird an den ersten Agent gesendet, der ihn annimmt, nach dem den anderen Agents der Anruf nicht mehr angezeigt wird.
    
10. Geben Sie auf der Registerkarte **Agents** an, wie Sie Ihre Agentliste erstellen möchten:
    
    - Klicken Sie zum Verwenden einer benutzerdefinierten Liste von Agents auf **"Benutzerdefinierte Gruppe von Agents definieren",** und führen Sie eine der folgenden Aktionen aus:
    
    - Klicken Sie zum Hinzufügen eines Benutzers zur Agentgruppe auf **"Auswählen",** und geben Sie dann im Suchfeld **"Agents auswählen"** den Namen des Benutzers, den Sie dieser Gruppe hinzufügen möchten, ganz oder teilweise ein, und klicken Sie dann auf **"Suchen".** Klicken Sie in der resultierenden Liste der Agents auf den Benutzer, und klicken Sie dann auf **OK.**
    
    - Um einen Benutzer aus der Agentgruppe zu entfernen, klicken Sie in der Liste der Agents auf den Benutzer, den Sie entfernen möchten, und klicken Sie dann auf **"Entfernen".**
    
    - Um die Reihenfolge zu ändern, in der Agents Anrufe in Gruppen angeboten werden, die entweder Roundrobinrouting oder serielles Routing verwenden, klicken Sie in der Liste der Agents auf einen Benutzer, und klicken Sie dann auf den Pfeil nach oben oder nach unten. 
    
    - Um eine Microsoft Exchange Server Verteilerliste als Agentgruppe zu verwenden, klicken Sie auf **Vorhandene E-Mail-Verteilerliste verwenden,** und geben Sie dann in der **Verteilerlistenadresse** die E-Mail-Adresse der Verteilerliste ein (z. B. NetworkSupport@contoso.com).
    
      Wenn Sie eine E-Mail-Verteilerliste verwenden, gelten die folgenden Einschränkungen:
    
      - Sie können für die Agentgruppe nicht mehrere Verteilerlisten auswählen. Jede Gruppe unterstützt nur eine Verteilerliste.
    
      - Falls die Verteilerliste eine oder mehrere Verteilerlisten enthält, werden die Mitglieder der verschachtelten Verteilerlisten nicht der Agentliste hinzugefügt.
    
      - Wenn serielles Routing oder Roundrobinrouting ausgewählt ist, bietet der Server einen eingehenden Anruf an den entsprechenden Agent gemäß der Routingmethode und gemäß der Reihenfolge, in der Agents in der Verteilerliste aufgeführt sind.
    
      - Wenn die Verteilerliste Benutzer enthält, für die Lync Server 2010 aktiviert ist, Enterprise-VoIP jedoch nicht aktiviert ist, werden sie der Agentgruppe als nicht funktionierende Agents hinzugefügt. Stellen Sie sicher, dass für alle Mitglieder der Verteilerliste Enterprise-VoIP für ihre Benutzerkonten aktiviert sind.
    
    > [!IMPORTANT]
    > Wenn Sie eine E-Mail-Verteilerliste verwenden, werden ausgeblendete Mitgliedschaften oder ausgeblendete Listen möglicherweise für den Reaktionsgruppenadministrator oder die Benutzer sichtbar. 
  
    Verborgene Mitgliedschaften oder Listen werden unter den folgenden Umständen sichtbar:
    
     - Wenn eine Verteilerliste so konfiguriert wurde, dass die Mitgliedschaft ausgeblendet ist und der Reaktionsgruppenadministrator die Verteilerliste der Agentliste zuweist, können Benutzer die Gruppe aufrufen, um herauszufinden, wer die Mitglieder sind. 
    
     - Wenn eine Verteilerliste so konfiguriert wurde, dass sie in der globalen Adressliste Exchange ausgeblendet ist, kann der Reaktionsgruppenadministrator die Verteilerliste anzeigen und der Agentliste zuweisen, wenn der Reaktionsgruppenprozess über die entsprechenden Benutzerrechte und Berechtigungen verfügt, auch wenn der Administrator nicht über die entsprechenden Benutzerrechte und Berechtigungen verfügt.
    
11. Klicken Sie auf **Commit ausführen**.
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-an-agent-group"></a>So verwenden Sie Skype for Business Server Verwaltungsshell zum Erstellen oder Ändern einer Agentgruppe

1. Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.
    
2. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start",** auf **"Alle Programme",** auf **Skype for Business 2015** und dann auf **Skype for Business Server Verwaltungsshell.**
    
3. Verwenden Sie **New-CsRgsAgentGroup,** um eine neue Agentgruppe zu erstellen. Verwenden Sie **"Set-CsRgsAgentGroup",** um eine vorhandene Agentgruppe zu ändern. Führen Sie an der Eingabeaufforderung Folgendes aus:
    
   ```powershell
   New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
   ```

    Beispiel:
    
   ```powershell
   New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
   ```

    > [!IMPORTANT]
    > Die Einstellung für die Agent-Warnungszeit darf 180 Sekunden nicht überschreiten. Wenn die Agent-Warnungszeit größer als 180 Sekunden ist, lehnt die Clientanwendung den Anruf ab, da der Timer der SIP-Transaktion die maximale Wartezeit erreicht. 
  
4. Vergewissern Sie sich, dass die Agentgruppe erstellt wurde. Führen Sie  aus.
    
   ```powershell
   Get-CsRgsAgentGroup -Name "Help Desk"
   ```

## <a name="see-also"></a>Siehe auch

[Get-CsService](/powershell/module/skype/get-csservice?view=skype-ps)
  
[New-CsRgsAgentGroup](/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)
  
[Set-CsRgsAgentGroup](/powershell/module/skype/set-csrgsagentgroup?view=skype-ps)
  
[Get-CsRgsAgentGroup](/powershell/module/skype/get-csrgsagentgroup?view=skype-ps)