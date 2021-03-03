---
title: Upgradestrategien für IT-Administratoren
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Der Artikel ist für IT-Administratoren und beschreibt Strategien für die Implementierung des Upgrades von Skype for Business auf Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cb884f26862466dcd70c9efe81e5293d277adbde
ms.sourcegitcommit: b0753baa55841a2c6c5dc006dcdd117704af3b42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/02/2021
ms.locfileid: "50401346"
---
# <a name="upgrade-strategies-for-it-administrators"></a>Upgradestrategien für IT-Administratoren

![Phasen des Upgradewegs mit Schwerpunkt auf der Bereitstellungs- und Implementierungsphase](media/upgrade-banner-deployment.png "Phasen des Upgradewegs mit Schwerpunkt auf der Bereitstellungs- und Implementierungsphase")

Dieser Artikel gilt für IT-Administratoren, die ihr Upgrade von Skype for Business auf Teams implementieren möchten.

Vor der Implementierung des Upgrades empfehlen wir die folgenden Artikel, in denen wichtige Upgradekonzepte und Koexistenzverhalten beschrieben werden:

- [Verständnis der Koexistenz und Interoperabilität von Microsoft Teams und Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Koexistenzmodi – Referenz](migration-interop-guidance-for-teams-with-skype.md)
- [Führt Kundenerfahrung und Konformität mit Koexistenzmodi zusammen](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="upgrade-options"></a>Upgradeoptionen

In diesem Abschnitt wird beschrieben, wie Sie Ihr Upgrade mithilfe einer der folgenden Upgradeoptionen implementieren:

- [Upgrade überlappender Funktionen (im Inselmodus)](#overlapping-capabilities-upgrade-using-islands-mode)
- [Upgrade der Auswahlfunktionen für eine Organisation, die noch nicht mit der Verwendung von Teams begonnen hat](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)
- [Upgrade der Auswahlfunktionen für eine Organisation, die Teams bereits im Inselmodus verwendet](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

Wenn Sie weitere Informationen zu den Optionen benötigen, vergewissern Sie sich, dass Sie bereits die Option Upgrade von Skype for Business zu Teams auswählen [gelesen haben.](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

## <a name="overlapping-capabilities-upgrade-using-islands-mode"></a>Upgrade überlappender Funktionen (im Inselmodus)

Für die Upgradeoption für überlappende Funktionen:

- Erwägen Sie diese Option, wenn Sie ein schnelles Upgrade für Ihre gesamte Organisation durchführen können.  Da für Endbenutzer mit der Ausführung beider Clients ein potenzielles Verwirrungsrisiko besteht, ist es am besten, wenn Sie den Zeitraum minimieren können, in dem Benutzer beide Clients ausführen müssen. Sie sollten sicherstellen, dass ihre Benutzer wissen, dass sie beide Clients ausführen.

- Diese Option ist das out-of-box-Modell und erfordert keine Administratoraktion, um mit Teams zu beginnen, außer die Microsoft 365- oder Office 365-Lizenz zu zuweisen. Wenn Ihre Benutzer bereits Über Skype for Business Online verfügen, sind Sie möglicherweise bereits in diesem Modell.

- Es kann schwierig sein, den Modus für überlappende Funktionen zu verlassen und zu TeamsOnly zu wechseln. Da aktualisierte Benutzer nur über Teams kommunizieren, müssen alle anderen Benutzer in der Organisation, die mit diesem Benutzer kommunizieren, Teams verwenden.  Wenn Sie Benutzer haben, die noch nicht mit der Verwendung von Teams begonnen haben, werden diese für fehlende Nachrichten verfügbar gemacht. Darüber hinaus werden die TeamsOnly-Benutzer in Skype for Business nicht online sehen. Einige Organisationen entscheiden sich für ein mandantenweites Upgrade mithilfe der globalen Mandantenrichtlinie, um dies zu vermeiden. Dies erfordert jedoch eine Vorabplanung sowie das Warten, bis alle Benutzer zum Upgrade bereit sind.


## <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a>Upgrade der Auswahlfunktionen für eine Organisation, die noch nicht mit der Verwendung von Teams begonnen hat

Wenn Ihre Organisation noch keine aktiven Benutzer in Teams hat, besteht der erste Schritt im Festlegen der mandantenweiten Standardrichtlinie für TeamsUpgradePolicy auf einen der Skype for Business-Modi, z. B. SfbWithTeamsCollab.  Benutzer, die noch nicht mit der Verwendung von Teams begonnen haben, werden keinen Verhaltensunterschied feststellen. Wenn Sie diese Richtlinie jedoch auf Mandantenebene festlegen, können Sie mit dem Upgrade von Benutzern auf den TeamsOnly-Modus beginnen und sicherstellen, dass die aktualisierten Benutzer weiterhin mit nicht aktualisierten Benutzern kommunizieren können.  Nachdem Sie Ihre Pilotbenutzer identifiziert haben, können Sie sie auf TeamsOnly aktualisieren.  Wenn sie lokal sind, verwenden Sie Move-CsUser. Wenn sie online sind, weisen Sie ihnen einfach den TeamsOnly-Modus zu, indem Sie Grant-CsTeamsUpgradePolicy verwenden. Standardmäßig werden alle von diesen Benutzern geplanten Skype for Business-Besprechungen zu Teams migriert.

Im Folgenden sind die wichtigsten Befehle zu finden:

1. Legen Sie den mandantenweiten Standardwert wie folgt auf den Modus SfbWithTeamsCollab festlegen:

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. Upgraden der Pilotbenutzer auf TeamsOnly wie folgt:

   - Für einen Benutzer, der online ist:

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username 
     ```

   - Für einen benutzer, der lokal ist:

     ```PowerShell
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
     ```

Hinweise
 
- Statt die mandantenweite Richtlinie auf SfbWithTeamsCollab zu setzen, könnten Sie sie auf SfbWithTeamsCollabAndMeetings festlegen. Dies bewirkt, dass alle Benutzer alle neuen Besprechungen in Teams planen.
- `Move-CsUser` ist ein Cmdlet in den lokalen Tools. Für `MoveToTeams` den Schalter ist Skype for Business Server 2019 oder Skype for Business Server 2015 mit CU8 oder höher erforderlich. Wenn Sie eine frühere Version verwenden, können Sie den Benutzer zuerst nach Skype for Business Online verschieben und diesem Benutzer dann den TeamsOnly-Modus gewähren.
- Skype for Business-Besprechungen werden standardmäßig zu Teams migriert, wenn ein Upgrade auf den TeamsOnly-Modus oder beim Zuweisen des SfbWithTeamsCollabAndMeetings-Modus ausgeführt wird.  

Das folgende Diagramm zeigt die konzeptionellen Phasen des Upgrades von Auswahlfunktionen für eine Organisation ohne vorherige Verwendung von Teams. Die Höhe der Balken stellt die Anzahl der Benutzer dar. Während jeder Phase des Upgrades können alle Benutzer miteinander kommunizieren.  Skype for Business-Benutzer kommunizieren mit TeamsOnly-Benutzern, die Interop verwenden, und umgekehrt. Benutzer im Inselmodus müssen sicherstellen, dass beide Clients ausgeführt werden.

![Diagramm mit upgraden von Auswahlfunktionen ohne vorherige Verwendung von Teams](media/teams-upgrade-1.png)


## <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a>Upgrade der Auswahlfunktionen für eine Organisation, die Teams bereits im Inselmodus verwendet

Wenn einige Benutzer in Ihrer Organisation Teams im Inselmodus aktiv verwenden, möchten Sie wahrscheinlich keine Funktionen von vorhandenen Benutzern entfernen. Daher ist ein zusätzlicher Schritt erforderlich, bevor Sie die mandantenweite Richtlinie ändern. Die Lösung besteht in der "Vererbung" dieser vorhandenen aktiven Teams-Benutzer im Inselmodus, bevor sie die mandantenweite Richtlinie auf SfbWithTeamsCollab festlegen.  Nachdem Sie dies getan haben, können Sie mit der Bereitstellung wie oben beschrieben fortfahren. Es gibt jedoch zwei Benutzergruppen, die zu TeamsOnly wechseln: Die Benutzer, die in Teams aktiv waren, befinden sich im Inselmodus, und die übrigen Benutzer befinden sich im SfbWithTeamsCollab-Modus. Sie können diese Benutzer schrittweise in den TeamsOnly-Modus verschieben.

1. Suchen Sie benutzer, die in Teams aktiv sind, wie folgt:

   1. Wechseln Sie im Microsoft 365 Admin Center in der linken Navigation zu Berichte und dann Nutzung. 
   2. Wählen Sie in der Dropdownliste "Bericht auswählen" Microsoft Teams und dann Benutzeraktivität aus. Dies stellt eine exportierbare Tabelle mit Benutzern zur Verfügung, die in Teams aktiv waren. 
   3. Klicken Sie auf Exportieren, öffnen Sie Excel, und filtern Sie, um nur die Benutzer zu sehen, die in Teams aktiv sind.

2. Weisen Sie jedem aktiven Teams-Benutzer, der in Schritt 1 gefunden wurde, den Inselmodus in der Remote-PowerShell zu. Auf diese Weise können Sie zum nächsten Schritt wechseln und sicherstellen, dass Sie die Benutzeroberfläche nicht ändern.  

   ```PowerShell
   $users=get-content “C:\MyPath\users.txt” 
    foreach ($user in $users){ 
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands} 
   ```

3. Legen Sie die mandantenweite Richtlinie auf SfbWithTeamsCollab festlegen:

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab 
   ```

4. Aktualisieren Sie ausgewählte Benutzer auf den TeamsOnly-Modus. Sie können entweder im Islands-Modus oder im SfbWithTeamsCollab-Modus ein Upgrade durchführen, obwohl Sie das Upgrade der Benutzer im Inselmodus priorisieren möchten, um das Potenzielle für Verwirrung zu minimieren, das entstehen kann, wenn sich Benutzer im Inselmodus befinden.   

   Für Benutzer, die in Skype for Business Online zuhause sind:  

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams 
   ```

   Für Benutzer, die sich lokal in Skype for Business Server befinden:  

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
   ```

Das nachstehende Diagramm zeigt die konzeptionellen Phasen eines Übergangs für Auswahlfunktionen, in denen am Anfang aktive Benutzer der Inseln sind. Die Höhe der Balken stellt die Anzahl der Benutzer dar. Während jeder Phase des Upgrades können alle Benutzer miteinander kommunizieren.  Skype for Business-Benutzer kommunizieren mit TeamsOnly-Benutzer, die Inopop verwenden und umgekehrt. 


![Diagramm, das das Upgrade der Auswahlfunktionen mit aktiven Benutzern im Inselmodus zeigt](media/teams-upgrade-2.png)

   



## <a name="related-links"></a>Verwandte Links

[Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](migration-interop-guidance-for-teams-with-skype.md) 

[Konfigurieren der Hybridkonnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Verschieben von Benutzern zwischen lokalen Bereitstellungen und der Cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Festlegen Ihrer Einstellungen für Koexistenz und Upgrades](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Verwenden des Besprechungsmigrationsdiensts (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

