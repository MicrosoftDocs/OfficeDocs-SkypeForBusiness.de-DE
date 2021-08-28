---
title: Upgradestrategien für IT-Administratoren
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Dieser Artikel ist für IT-Administratoren vorgesehen und beschreibt Strategien für die Implementierung des Upgrades von Skype for Business auf Teams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6c44d988bdcfbd08f462a99c76b4095bb01ac60c
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58619341"
---
# <a name="upgrade-strategies-for-it-administrators"></a>Upgradestrategien für IT-Administratoren

![Phasen des Upgradewegs, mit Betonung auf der Bereitstellungs- und Implementierungsphase](media/upgrade-banner-deployment.png "Phasen des Upgradewegs, mit Betonung auf der Bereitstellungs- und Implementierungsphase")

Dieser Artikel ist für IT-Administratoren vorgesehen, die ihr Upgrade auf die Teams Von Skype for Business.

Vor der Implementierung des Upgrades empfehlen wir die folgenden Artikel, in denen wichtige Upgradekonzepte und Koexistenzverhalten beschrieben werden:

- [Verständnis Microsoft Teams und Skype for Business Koexistenz und Interoperabilität](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Koexistenzmodi – Referenz](migration-interop-guidance-for-teams-with-skype.md)
- [Führt Kundenerfahrung und Konformität mit Koexistenzmodi zusammen](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="upgrade-options"></a>Upgradeoptionen

In diesem Abschnitt wird beschrieben, wie Sie Ihr Upgrade mithilfe einer der folgenden Upgradeoptionen implementieren:

- [Upgrade überlappender Funktionen (mithilfe des Islands-Modus)](#overlapping-capabilities-upgrade-using-islands-mode)
- [Ein Upgrade der Auswahlfunktionen für eine Organisation, die noch nicht mit der Verwendung von Teams](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)
- [Upgrade der Auswahlfunktionen für eine Organisation, die bereits Teams im Islands-Modus verwendet](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

Wenn Sie weitere Informationen zu den Optionen benötigen, vergewissern Sie sich, dass Sie bereits den Artikel Upgrade auswählen von Skype for Business [zu Teams.](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

## <a name="overlapping-capabilities-upgrade-using-islands-mode"></a>Upgrade überlappender Funktionen (mithilfe des Islands-Modus)

Upgradeoption für überlappende Funktionen:

- Erwägen Sie diese Option, wenn Sie ein schnelles Upgrade für Ihre gesamte Organisation durchführen können.  Da das Risiko von Verwirrung für Endbenutzer mit beiden Clients besteht, ist es am besten, wenn Sie den Zeitraum minimieren können, in dem Benutzer beide Clients ausführen müssen. Sie sollten sicherstellen, dass Ihre Benutzer wissen, dass sie beide Clients ausführen.

- Bei dieser Option handelt es sich um ein bereits verfügbares Modell, bei dem für die ersten Schritte mit Teams keine Administratoraktion erforderlich, es sei denn, Sie weisen die Microsoft 365 oder Office 365 zu. Wenn Ihre Benutzer bereits über Skype for Business Online verfügen, sind Sie möglicherweise bereits in diesem Modell.

- Es kann schwierig sein, den Modus für sich überlappende Funktionen zu nutzen und zu TeamsOnly zu wechseln. Da Benutzer, für die ein Upgrade durchgeführt wurde, nur über Teams kommunizieren, müssen alle anderen Benutzer in der Organisation, die mit diesem Benutzer kommunizieren, über Teams.  Wenn Sie Benutzer haben, die ihre Verwendung noch nicht Teams, werden sie fehlenden Nachrichten ausgesetzt. Außerdem werden die TeamsOnly-Benutzer in Ihrer Skype for Business. Einige Organisationen entscheiden sich für ein mandantenweites Upgrade mit der globalen Mandantenrichtlinie, um dies zu vermeiden. Dies erfordert jedoch eine Vorabplanung und das Warten, bis das Upgrade für alle Benutzer bereit ist.


## <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a>Ein Upgrade der Auswahlfunktionen für eine Organisation, die noch nicht mit der Verwendung von Teams

Wenn Ihre Organisation noch keine aktiven Benutzer in Teams hat, besteht der erste Schritt im Festlegen der mandantenweiten Standardrichtlinie für TeamsUpgradePolicy auf einen der Skype for Business-Modi, z. B. SfbWithTeamsCollab.  Benutzer, die die Verwendung von Teams noch nicht begonnen haben, werden keinen Verhaltensunterschied feststellen. Wenn Sie diese Richtlinie jedoch auf Mandantenebene festlegen, können Sie mit dem Upgrade von Benutzern auf den TeamsOnly-Modus beginnen und sicherstellen, dass die aktualisierten Benutzer weiterhin mit Benutzern ohne Upgrade kommunizieren können.  Nachdem Sie Ihre Pilotbenutzer identifiziert haben, können Sie sie auf TeamsOnly aktualisieren.  Wenn sie lokal sind, verwenden Sie Move-CsUser. Wenn sie online sind, weisen Sie ihnen einfach den TeamsOnly-Modus mithilfe von Grant-CsTeamsUpgradePolicy zu. Standardmäßig werden alle Skype for Business, die von diesen Benutzern geplant werden, zu Teams.

Im Folgenden finden Sie die wichtigsten Befehle:

1. Legen Sie den mandantenweiten Standardmodus SfbWithTeamsCollab wie folgt auf:

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. Aktualisieren Sie die Pilotbenutzer wie folgt auf TeamsOnly:

   - Für einen Benutzer, der online ist:

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username 
     ```

   - Für einen benutzer, der lokal ist:

     ```PowerShell
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
     ```

Hinweise
 
- Statt die mandantenweite Richtlinie auf SfbWithTeamsCollab zu setzen, können Sie sie auf SfbWithTeamsCollabAndMeetings festlegen. Dadurch planen alle Benutzer alle neuen Besprechungen in Teams.
- Standardmäßig werden Skype for Business Besprechungen nach Teams, wenn ein Upgrade auf den TeamsOnly-Modus oder die Zuweisung des SfbWithTeamsCollabAndMeetings-Modus ausgeführt wird.  

> [!NOTE]
> Zur Vorbereitung auf die bevorstehende Skype for Business von Skype for Business Online hat Microsoft den Umzug von Organisationen auf den Teams. Es ist nicht mehr erforderlich, den Wechsel in anzugeben, um Benutzer direkt aus der lokalen Lokalen direkt nach `-MoveToTeams` `Move-CsUser` TeamsOnly zu verschieben. Wenn dieser Schalter nicht angegeben wurde, wurden Benutzer bisher von der lokalen Skype for Business Server-Home zu Skype for Business Online umgeschaltet, und ihr Modus bleibt unverändert. Wenn Sie einen Benutzer jetzt mit aus der lokalen Cloud in die Cloud verschieben, wird den Benutzern automatisch der TeamsOnly-Modus zugewiesen, und ihre Besprechungen aus dem lokalen Modus werden automatisch in Teams-Besprechungen konvertiert, genauso, als ob der tatsächlich angegeben `Move-CsUser` `-MoveToTeams switch had been specified` wurde. Dieses Verhalten ist für alle Versionen von Skype For Business Server und Lync Server 2013 verfügbar (die keine Unterstützung für `-MoveToTeams` hatten).

Das folgende Diagramm zeigt die konzeptuellen Phasen des Upgrades von Auswahlfunktionen für eine Organisation ohne vorherige Verwendung Teams. Die Höhe der Balken stellt die Anzahl der Benutzer dar. Während jeder Phase des Upgrades können alle Benutzer miteinander kommunizieren.  Skype for Business Benutzer kommunizieren mit TeamsOnly-Benutzer über Inop und umgekehrt. Benutzer im Islands-Modus müssen sicherstellen, dass beide Clients ausgeführt werden.

![Diagramm, das das Upgrade der Auswahlfunktionen ohne vorherige Verwendung des Teams](media/teams-upgrade-1.png)


## <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a>Upgrade der Auswahlfunktionen für eine Organisation, die bereits Teams im Islands-Modus verwendet

Wenn einige Benutzer in Ihrer Organisation das Teams im Islands-Modus verwenden, möchten Sie wahrscheinlich die Funktionalität von vorhandenen Benutzern nicht entfernen. Daher ist ein zusätzlicher Schritt erforderlich, bevor Sie die mandantenweite Richtlinie ändern. Die Lösung besteht in der "Bereitstellung" dieser vorhandenen aktiven Teams in den Islands-Modus, bevor sie die mandantenweite Richtlinie auf "SfbWithTeamsCollab" festlegen.  Sobald Sie damit fertig sind, können Sie mit der Bereitstellung wie oben fortfahren, es gibt jedoch zwei Gruppen von Benutzern, die zu TeamsOnly wechseln: Die Benutzer, die in Teams aktiv waren, befinden sich im Islands-Modus, und die übrigen Benutzer befinden sich im SfbWithTeamsCollab-Modus. Sie können diese Benutzer nach und nach in den TeamsOnly-Modus verschieben.

1. Suchen Sie benutzer, die in der Teams wie folgt:

   1. Navigieren Sie Microsoft 365 Admin Center der linken Navigationsleiste zu Berichte und dann zu Verwendung. 
   2. Wählen Sie in der Dropdownliste "Bericht auswählen" die Option Microsoft Teams und dann Benutzeraktivität aus. Dadurch wird eine exportierbare Tabelle mit Benutzern angezeigt, die in der Teams. 
   3. Klicken Sie auf Exportieren, öffnen Excel und filtern Sie, um nur die Benutzer in der Liste Teams.

2. Weisen Sie jedem aktiven Teams in Schritt 1 gefundenen Benutzer den Islands-Modus in der Remote-PowerShell zu. Dadurch können Sie mit dem nächsten Schritt wechseln und sicherstellen, dass die Benutzerfreundlichkeit nicht geändert wird.  

   ```PowerShell
   $users=get-content “C:\MyPath\users.txt” 
    foreach ($user in $users){ 
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands} 
   ```

3. Legen Sie die mandantenweite Richtlinie auf SfbWithTeamsCollab

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab 
   ```

4. Aktualisieren Sie ausgewählte Benutzer in den TeamsOnly-Modus. Sie können entweder ein Upgrade für Benutzer im Islands-Modus oder im SfbWithTeamsCollab-Modus durchführen, obwohl Sie das Upgrade der Benutzer im Islands-Modus zunächst priorisieren möchten, um das Risiko von Verwirrung zu minimieren, die entstehen kann, wenn sich Benutzer im Islands-Modus befinden.   

   Für In Skype for Business Online Skype for Business:  

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams 
   ```

   Für benutzer, die in Skype for Business Server lokal homed sind:  

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
   ```

Das folgende Diagramm zeigt die konzeptuellen Phasen eines Übergangs zur Auswahl von Funktionen, in denen aktive Islands-Benutzer am Anfang stehen. Die Höhe der Balken entspricht der Anzahl der Benutzer. Während jeder Phase des Upgrades können alle Benutzer miteinander kommunizieren.  Skype for Business Benutzer kommunizieren mit TeamsOnly-Benutzern über Inop und umgekehrt. 


![Diagramm, das das Upgrade der Auswahlfunktionen mit aktiven Benutzern im Islands-Modus zeigt](media/teams-upgrade-2.png)

   



## <a name="related-links"></a>Links zu verwandten Themen

[Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](migration-interop-guidance-for-teams-with-skype.md) 

[Konfigurieren der Hybridkonnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Verschieben von Benutzern zwischen lokalen Bereitstellungen und der Cloud](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Festlegen Ihrer Einstellungen für Koexistenz und Upgrades](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Verwenden des Meeting Migration Service (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
