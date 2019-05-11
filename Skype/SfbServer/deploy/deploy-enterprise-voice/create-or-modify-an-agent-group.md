---
title: Erstellen oder Ändern einer agentgruppe in Skype für Unternehmen
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
ms.assetid: f1461fff-51c1-4f4b-9311-8cba02c333fc
description: Erstellen oder Ändern einer agentgruppe in Reaktionsgruppe in Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: 43d4abba518b99a52b67a1c3bfe22abdea28d679
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892902"
---
# <a name="create-or-modify-an-agent-group-in-skype-for-business"></a>Erstellen oder Ändern einer agentgruppe in Skype für Unternehmen
 
Erstellen oder Ändern einer agentgruppe in Reaktionsgruppe in Skype für Business Server Enterprise-VoIP.
  
Beim Erstellen einer Agentgruppe wählen Sie die Agents aus, die der Gruppe zugewiesen werden. Außerdem geben Sie zusätzliche Gruppeneinstellungen (beispielsweise die Routingmethode) an und legen fest, ob sich ein Agent bei der Gruppe an- und abmelden muss. 
  
Ein Agent, der bei der Gruppe an-oder vom an-und Abmelden Skype für Unternehmen unterscheidet abmelden muss, wird einen formellen Vertreter aufgerufen. Formelle Agents müssen sich bei der Gruppe anmelden, um an die Gruppe weitergeleitete Anrufe empfangen zu können. Dies kann für Agents nützlich sein, die Anrufe der Gruppe nur zeitweise annehmen. Formelle Agents melden sich bei ihren Gruppen an-oder durch Klicken auf ein Menüelement in Skype für Unternehmen Windows Internet Explorer als Browser öffnen und Anzeigen einer Webseite-Konsole.
  
Ein Agent, der nicht an- und Abmelden der Gruppe angemeldet ist, wird als informeller Agent bezeichnet. Informelle Agents werden automatisch der Gruppe angemeldet, bei der Anmeldung zu Skype für Unternehmen und Anmeldung kann nicht aus der Gruppe.
  
Nur lokale Benutzer können Agents sein. Wenn ein Agent lokal zu online verschoben wurde, werden nicht reaktionsgruppenanrufe, Vertreter weitergeleitet.
  
Verwenden Sie eines der folgenden Verfahren, um eine Agentgruppe zu erstellen oder zu ändern.
  
> [!IMPORTANT]
> Wenn Sie Benutzer als Reaktionsgruppenagents zuweisen, weisen Sie diese darauf hin, dass sie bei aktiviertem Datenschutzmodus nach „RGS-Anwesenheitsmonitor“-Kontakten suchen und sie ihrer Kontaktliste hinzufügen müssen. Agents, deren Datenschutzmodus aktiviert ist, die jedoch „RGS-Anwesenheitsmonitor“ nicht in ihre Kontaktliste aufgenommen haben, können keine Anrufe bei der Reaktionsgruppe annehmen. Agents, deren Datenschutzmodus nicht aktiviert ist, sind davon nicht betroffen. 
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-an-agent-group"></a>Verwenden Sie zum Erstellen oder Ändern einer agentgruppe Skype Business Server-Systemsteuerung

1. Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.
    
    > [!NOTE]
    > Wenn Sie einer der delegierten Reaktionsgruppenleiter für einen verwalteten Workflow sind, können Sie Gruppen erstellen und in den von Ihnen verwalteten Workflows verwenden. 
  
2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.  
    
3. Klicken Sie auf der linken Navigationsleiste auf **Reaktionsgruppen** und dann auf **Gruppe**.
    
4. Führen Sie auf der Seite **Gruppe** einen der folgenden Schritte aus:
    
   - Zum Erstellen einer neuen Agentgruppe klicken Sie auf **Neu**. Geben Sie im Suchfeld **Dienst auswählen** den Namen des **ApplicationServer**-Diensts, dem Sie die Gruppe hinzufügen möchten, ganz oder teilweise ein. Klicken Sie in der nun angezeigten Liste der Dienst auf den gewünschten Dienst und klicken Sie dann auf **OK**.
    
   - Wenn Sie eine vorhandene Agentgruppe ändern möchten, geben Sie im Suchfeld den Namen der Agentgruppe ganz oder teilweise ein. Klicken Sie in der nun angezeigten Liste auf die gewünschte Gruppe, dann auf **Bearbeiten** und anschließend auf **Details anzeigen**.
    
5. Geben Sie im Feld **Name** einen aussagekräftigen Namen für die Agentgruppe ein.
    
6. Geben Sie in **Beschreibung** eine Beschreibung für die Gruppe ein.
    
7. Wählen Sie unter **Beteiligungsrichtlinie** eine der folgenden Einstellungen aus, um das Anmeldeverhalten für die Gruppe einzurichten:
    
   - Wählen Sie **Informell**, um anzugeben, dass Agents in der Gruppe sich bei der Gruppe weder an- noch abmelden müssen. Agents werden automatisch der Gruppe angemeldet beim Anmelden bei Skype für Unternehmen.
    
   - Klicken Sie auf **Formell**, um festzulegen, dass sich die Agents der Gruppe bei der Gruppe an- oder abmelden müssen. Wenn Sie diese Option auswählen, klicken Sie auf Agents ein Menüelement in Skype für Unternehmen, öffnen Sie Internet Explorer und Anzeigen einer Webseite-Konsole für die Anmeldung bei der Gruppe an-oder.
    
8. Geben Sie im Feld **Agentwarnungszeit (Sekunden)** an, wie lange das Telefon eines Agents klingelt, bevor der Anruf an den nächsten verfügbaren Agent übergeben wird (die Standardeinstellung ist 20 Sekunden).
    
    > [!IMPORTANT]
    > Die Einstellung für die Agentwarnungszeit darf 180 Sekunden nicht überschreiten. Andernfalls weist die Clientanwendung den Anruf zurück, weil der Zeitgeber für die SIP-Transaktion die maximale Wartezeit erreicht. 
  
9. Wählen Sie unter **Routingmethode** aus, wie Anrufe an die Agents in der Gruppe weitergeleitet werden:
    
   - Um einen neuen Anruf zuerst dem Agent anbieten möchten, der die längste Zeit untätig war, Leerlaufzeit (Anwesenheitsstatus **verfügbar** oder **inaktiv** in Skype für Unternehmen, das sich am längsten), klicken Sie auf **Längster Leerlauf**. 
    
   - Klicken Sie auf **Parallel**, um einen neuen Anruf simultan allen verfügbaren Agents anzubieten. Der Anruf wird an den ersten Agent übergeben, der diesen annimmt.
    
   - Wenn Sie einen neuen Anruf den einzelnen Agents nacheinander anbieten möchten, klicken Sie auf **Roundrobin**. 
    
   - Wenn Sie einen neuen Anruf den Agents immer in der Reihenfolge anbieten möchten, in der sie auf der Registerkarte **Agent** aufgeführt sind, klicken Sie auf **Seriell**. 
    
   - Klicken Sie auf **automatische Telefonzentrale**, wenn Sie einen neuen Anruf allen Agents anbieten möchten, die in Skype für Unternehmen und die Anwendung "Reaktionsgruppe" zur selben Zeit, unabhängig von ihrer aktuellen Anwesenheit, angemeldet sind. Benutzer, die als Agents konfiguriert sind, können alle wartenden Anrufe sehen und in beliebiger Reihenfolge annehmen. Der Anruf wird an den ersten Agent übergeben, der den Anruf annimmt, woraufhin er den weiteren Agents nicht mehr angezeigt wird.
    
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
    
    > [!IMPORTANT]
    > Wenn Sie eine e-Mail-Verteilerliste verwenden, können verborgene Mitgliedschaften oder Listen für die Reaktionsgruppe Administrator oder Benutzer sichtbar werden. 
  
    Verborgene Mitgliedschaften oder Listen werden unter den folgenden Umständen sichtbar:
    
     - Wenn eine Verteilerliste, damit die Mitgliedschaft ist ausgeblendet, und der Reaktionsgruppe Administrator der Verteilerliste zu der vertreterliste weist konfiguriert wurde, können Benutzer die Gruppe, um zu ermitteln, wer die Member sind aufrufen. 
    
     - Eine Verteilerliste wurde so konfiguriert, dass er in der globalen Adressliste von Exchange ausgeblendet ist, der Reaktionsgruppe-Administrator möglicherweise finden Sie unter der Verteilung auflisten und der vertreterliste zuweisen, wenn der Reaktionsgruppe Prozess der ausreichenden Benutzerrechte verfügt und Berechtigungen, auch wenn der Administrator nicht über die entsprechenden Benutzerrechte und-Berechtigungen verfügt.
    
11. Klicken Sie auf **Commit ausführen**.
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-an-agent-group"></a>Verwenden von Skype für Business Server-Verwaltungsshell zum Erstellen oder Ändern einer agentgruppe

1. Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.
    
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
3. Verwenden Sie **New-CsRgsAgentGroup**, um eine neue Agentgruppe zu erstellen. Zum Ändern einer vorhandenen Agentgruppe verwenden Sie **Set-CsRgsAgentGroup**. Führen Sie an der Eingabeaufforderung folgenden Befehl aus:
    
   ```
   New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
   ```

    Beispiel:
    
   ```
   New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
   ```

    > [!IMPORTANT]
    > Die Einstellung für die Agentwarnungszeit darf 180 Sekunden nicht überschreiten. Andernfalls weist die Clientanwendung den Anruf zurück, weil der Zeitgeber für die SIP-Transaktion die maximale Wartezeit erreicht. 
  
4. Vergewissern Sie sich, dass die Agentgruppe erstellt worden ist. Führen Sie folgenden Befehl aus:
    
   ```
   Get-CsRgsAgentGroup -Name "Help Desk"
   ```

## <a name="see-also"></a>Siehe auch

[Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)
  
[Mit New-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)
  
[Set-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/set-csrgsagentgroup?view=skype-ps)
  
[Get-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/get-csrgsagentgroup?view=skype-ps)
