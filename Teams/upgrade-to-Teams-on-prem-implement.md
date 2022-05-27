---
title: Upgradestrategien für IT-Administratoren
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Der Artikel richtet sich an IT-Administratoren und beschreibt Strategien für die Implementierung ihres Upgrades von Skype for Business auf Teams.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f403b12ffc8cabbfebe8a30268eb3e6dad468f32
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681736"
---
# <a name="upgrade-strategies-for-it-administrators"></a>Upgradestrategien für IT-Administratoren

![Phasen der Upgradephase, mit Schwerpunkt auf der Bereitstellungs- und Implementierungsphase.](media/upgrade-banner-deployment.png "Phasen der Upgradephase mit Schwerpunkt auf der Bereitstellungs- und Implementierungsphase")

Dieser Artikel richtet sich an IT-Administratoren, die ihr Upgrade auf Teams von Skype for Business implementieren möchten.

Vor der Implementierung ihres Upgrades empfehlen wir die folgenden Artikel, in denen wichtige Upgradekonzepte und Koexistenzverhalten beschrieben werden:

- [Grundlegendes zu Microsoft Teams und Skype for Business Koexistenz und Interoperabilität](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Koexistenzmodi – Referenz](migration-interop-guidance-for-teams-with-skype.md)
- [Führt Kundenerfahrung und Konformität mit Koexistenzmodi zusammen](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="upgrade-options"></a>Upgradeoptionen

In diesem Abschnitt wird beschrieben, wie Sie Ihr Upgrade mithilfe einer der folgenden Upgradeoptionen implementieren:

- [Upgrade überlappender Funktionen (mithilfe des Inselmodus)](#overlapping-capabilities-upgrade-using-islands-mode)
- [Ein Upgrade auf ausgewählte Funktionen für eine Organisation, die noch nicht mit der Verwendung von Teams](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)
- [Ein Upgrade der Auswahlfunktionen für eine Organisation, die bereits Teams im Inselmodus verwendet](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

Wenn Sie weitere Informationen zu den Optionen benötigen, stellen Sie sicher, dass Sie bereits "[Upgrade auswählen" von Skype for Business zu Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md) gelesen haben.

## <a name="overlapping-capabilities-upgrade-using-islands-mode"></a>Upgrade überlappender Funktionen (mithilfe des Inselmodus)

Für die Upgradeoption für überlappende Funktionen:

- Erwägen Sie diese Option, wenn Sie ein schnelles Upgrade für Ihre gesamte Organisation durchführen können.  Da das Risiko einer Verwirrung für Endbenutzer bei der Ausführung beider Clients besteht, empfiehlt es sich, den Zeitraum zu minimieren, in dem Benutzer beide Clients ausführen müssen. Sie sollten sicherstellen, dass Ihre Benutzer wissen, dass beide Clients ausgeführt werden.

- Diese Option ist das out-of-the-box-Modell und erfordert keine Administratoraktion, um mit Teams zu beginnen, außer die Microsoft 365 oder Office 365 Lizenz zuzuweisen. Wenn Ihre Benutzer bereits über Skype for Business Online verfügen, befinden Sie sich möglicherweise bereits in diesem Modell.

- Es kann schwierig sein, aus dem überlappenden Funktionsmodus herauszukommen und zu TeamsOnly zu wechseln. Da aktualisierte Benutzer nur über Teams kommunizieren, muss jeder andere Benutzer in der Organisation, der mit diesem Benutzer kommuniziert, Teams verwenden.  Wenn Sie Benutzer haben, die noch nicht mit der Verwendung von Teams begonnen haben, werden diese für fehlende Nachrichten verfügbar gemacht. Darüber hinaus werden die TeamsOnly-Benutzer in Skype for Business nicht online angezeigt. Einige Organisationen entscheiden sich für ein mandantenweites Upgrade mithilfe der globalen Mandantenrichtlinie, um dies zu vermeiden. Dies erfordert jedoch eine Vorabplanung und wartet, bis alle Benutzer für das Upgrade bereit sind.

## <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a>Ein Upgrade auf ausgewählte Funktionen für eine Organisation, die noch nicht mit der Verwendung von Teams

Wenn ihre Organisation noch keine aktiven Benutzer in Teams hat, besteht der erste Schritt darin, die mandantenweite Standardrichtlinie für TeamsUpgradePolicy auf einen der Skype for Business Modi festzulegen, z. B. SfbWithTeamsCollab.  Benutzer, die noch nicht mit der Verwendung von Teams begonnen haben, werden keine Verhaltensunterschiede feststellen. Das Festlegen dieser Richtlinie auf Mandantenebene ermöglicht jedoch das Upgrade von Benutzern auf den TeamsOnly-Modus und stellt sicher, dass die aktualisierten Benutzer weiterhin mit nicht aktualisierten Benutzern kommunizieren können.  Nachdem Sie Ihre Pilotbenutzer identifiziert haben, können Sie sie auf TeamsOnly aktualisieren.  Wenn sie lokal sind, verwenden Sie Move-CsUser. Wenn sie online sind, weisen Sie ihnen einfach den TeamsOnly-Modus mithilfe von Grant-CsTeamsUpgradePolicy zu. Standardmäßig werden alle von diesen Benutzern geplanten Skype for Business Besprechungen zu Teams migriert.

Im Folgenden sind die Tastenbefehle aufgeführt:

1. Legen Sie den mandantenweiten Standard auf den Modus "SfbWithTeamsCollab" wie folgt fest:

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. Führen Sie wie folgt ein Upgrade der Pilotbenutzer auf TeamsOnly durch:

   - Für einen Benutzer, der online ist:

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username
     ```

   - Für einen lokalen Benutzer:

     ```PowerShell
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
     ```

**Hinweise**:

- Anstatt die mandantenweite Richtlinie auf SfbWithTeamsCollab festzulegen, könnten Sie sie auf SfbWithTeamsCollabAndMeetings festlegen. Dies bewirkt, dass alle Benutzer alle neuen Besprechungen in Teams planen.
- Standardmäßig werden Skype for Business Besprechungen beim Upgrade auf den TeamsOnly-Modus oder beim Zuweisen des SfbWithTeamsCollabAndMeetings-Modus zu Teams migriert.

> [!NOTE]
> In Vorbereitung auf die bevorstehende Einstellung von Skype for Business Online hat Microsoft die Umstellung von Organisationen auf Teams vereinfacht. Es ist nicht mehr erforderlich, den `-MoveToTeams` Wechsel `Move-CsUser` anzugeben, um Benutzer direkt von der lokalen Umgebung direkt zu TeamsOnly zu verschieben. Wenn diese Option nicht angegeben wurde, haben Benutzer zuvor von Skype for Business Server lokal zu Skype for Business Online gewechselt, und ihr Modus blieb unverändert. Beim Verschieben eines Benutzers aus der lokalen Umgebung in die Cloud mit `Move-CsUser`werden Benutzern automatisch der TeamsOnly-Modus zugewiesen, und ihre Besprechungen von der lokalen Bereitstellung werden automatisch in Teams Besprechungen konvertiert, so als ob die `-MoveToTeams switch had been specified`Besprechung tatsächlich angegeben ist. Dieses Verhalten ist für alle Versionen von Skype For Business Server und Lync Server 2013 (die nie Unterstützung für `-MoveToTeams`) verfügbar.

Das folgende Diagramm zeigt die konzeptionellen Phasen des Upgrades von Auswahlfunktionen für eine Organisation ohne vorherige Verwendung von Teams. Die Höhe der Balken stellt die Anzahl der Benutzer dar. In jeder Phase des Upgrades können alle Benutzer miteinander kommunizieren.  Skype for Business Benutzer kommunizieren mit TeamsOnly-Benutzern über Interop und umgekehrt. Benutzer im Inselmodus müssen unbedingt beide Clients ausführen.

![Diagramm, das das Upgrade der ausgewählten Funktionen ohne vorherige Verwendung von Teams zeigt.](media/teams-upgrade-1.png)

## <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a>Ein Upgrade der Auswahlfunktionen für eine Organisation, die bereits Teams im Inselmodus verwendet

Wenn einige Benutzer in Ihrer Organisation Teams aktiv im Inselmodus verwenden, möchten Sie wahrscheinlich keine Funktionen von vorhandenen Benutzern entfernen. Daher ist vor dem Ändern der mandantenweiten Richtlinie ein zusätzlicher Schritt erforderlich. Die Lösung besteht darin, diese vorhandenen aktiven Teams Benutzer in den Inselmodus zu "überschreiben", bevor die mandantenweite Richtlinie auf SfbWithTeamsCollab festgelegt wird.  Sobald Sie dies getan haben, können Sie die Bereitstellung wie oben beschrieben fortsetzen. Sie haben jedoch zwei Benutzergruppen, die zu TeamsOnly wechseln: Die Benutzer, die im Teams aktiv waren, befinden sich im Inselmodus, und die übrigen Benutzer befinden sich im SfbWithTeamsCollab-Modus. Sie können diese Benutzer schrittweise in den TeamsOnly-Modus verschieben.

1. Suchen Sie Benutzer, die in Teams aktiv sind, wie folgt:

   1. Wechseln Sie im Microsoft 365 Admin Center im linken Navigationsbereich zu "Berichte" und dann "Verwendung".
   2. Wählen Sie in der Dropdownliste "Bericht auswählen" Microsoft Teams und dann "Benutzeraktivität" aus. Dadurch wird eine exportierbare Tabelle mit Benutzern bereitgestellt, die in Teams aktiv waren.
   3. Klicken Sie auf "Exportieren", öffnen Sie Excel, und filtern Sie, um nur die Benutzer anzuzeigen, die in Teams aktiv sind.

2. Weisen Sie ihnen für jeden aktiven Teams Benutzer, der in Schritt 1 gefunden wurde, den Inselmodus in Remote-PowerShell zu. Auf diese Weise können Sie mit dem nächsten Schritt fortfahren und sicherstellen, dass Sie die Benutzerfreundlichkeit nicht ändern.

   ```PowerShell
   $users=get-content "C:\MyPath\users.txt"
    foreach ($user in $users){
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands}
   ```

3. Legen Sie die mandantenweite Richtlinie auf SfbWithTeamsCollab fest:

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab
   ```

4. Aktualisieren Sie ausgewählte Benutzer in den TeamsOnly-Modus. Sie können entweder Benutzer im Inselmodus oder sfbWithTeamsCollab-Modus aktualisieren, obwohl Sie möglicherweise zuerst das Upgrade der Benutzer im Inselmodus priorisieren möchten, um das Risiko von Verwirrung zu minimieren, die auftreten kann, wenn sich Benutzer im Inselmodus befinden.

   Für Benutzer, die in Skype for Business Online verwaltet werden:

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams
   ```

   Für Benutzer, die in Skype for Business Server lokal verwaltet werden:

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
   ```

Das folgende Diagramm zeigt die konzeptionellen Phasen eines Übergangs zu ausgewählten Funktionen, in denen aktive Islands-Benutzer am Anfang sind. Die Höhe der Balken stellt die Anzahl der Benutzer dar. In jeder Phase des Upgrades können alle Benutzer miteinander kommunizieren.  Skype for Business Benutzer kommunizieren mit TeamsOnly-Benutzern über Interoperabilität und umgekehrt.

![Diagramm, das das Upgrade der ausgewählten Funktionen mit aktiven Benutzern im Inselmodus zeigt.](media/teams-upgrade-2.png)

## <a name="related-links"></a>Verwandte Links

[Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](migration-interop-guidance-for-teams-with-skype.md)

[Konfigurieren der Hybridverbindung zwischen Skype for Business Server und Microsoft 365 oder Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Verschieben von Benutzern zwischen lokalen Bereitstellungen und der Cloud](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Festlegen Ihrer Einstellungen für Koexistenz und Upgrades](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy)

[Verwenden des Meeting Migration Service (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
