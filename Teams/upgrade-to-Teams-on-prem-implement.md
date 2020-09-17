---
title: Upgrade auf Teams über eine lokale Skype for Business-Bereitstellung – Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/22/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Upgrade von Skype for Business auf Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 887ab004ae913ee2171f1894bd5fc4a44845881f
ms.sourcegitcommit: b07938c0b6edafacaeaaef205a1be00c4c1693ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/16/2020
ms.locfileid: "47940725"
---
# <a name="implement-your-upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a>Implementieren Ihres Upgrades von Skype for Business in Teams &mdash; für IT-Administratoren

In diesem Artikel wird beschrieben, wie Sie Ihr Upgrade implementieren. Dieser Artikel ist der fünfte von mehreren, die Upgrade-Konzepte und Implementierung für IT-Administratoren beschreiben.  

- [Übersicht](upgrade-to-teams-on-prem-overview.md)
- [Upgrade-Methoden](upgrade-to-teams-on-prem-upgrade-methods.md)
- [Tools zum Verwalten des Upgrades](upgrade-to-teams-on-prem-tools.md)
- [Weitere Überlegungen für Organisationen mit Skype for Business lokal](upgrade-to-teams-on-prem-considerations.md)
- **Implementieren des Upgrades** (dieser Artikel)
- [Überlegungen zum Public Switched Telephone Network (PSTN)](upgrade-to-teams-on-prem-pstn-considerations.md)

Darüber hinaus werden in den folgenden Artikeln wichtige Upgrade-Konzepte und Koexistenz-Verhaltensweisen beschrieben:

- [Koexistenz von Teams und Skype for Business](upgrade-to-teams-on-prem-coexistence.md)
- [Koexistenzmodus – Referenz](migration-interop-guidance-for-teams-with-skype.md)
- [Führt Kundenerfahrung und Konformität mit Koexistenzmodi zusammen](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="upgrade-options"></a>Aktualisierungsoptionen

In diesem Abschnitt wird beschrieben, wie Sie das Upgrade mithilfe einer der folgenden Aktualisierungsoptionen implementieren:

- [Überlappende Funktionen Upgrade (im Modus "Inseln")](#overlapping-capabilities-upgrade-using-islands-mode)
- [Ein Upgrade der Auswahlfunktionen für eine Organisation, die noch nicht mit der Verwendung von Teams begonnen hat](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)
- [Ein Upgrade der Auswahlfunktionen für eine Organisation, die bereits Teams im Inseln-Modus verwendet](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

Wenn Sie weitere Informationen zu den Optionen benötigen, stellen Sie sicher, dass Sie die [Upgrade-Methoden](upgrade-to-teams-on-prem-upgrade-methods.md)bereits gelesen haben.

## <a name="overlapping-capabilities-upgrade-using-islands-mode"></a>Überlappende Funktionen Upgrade (im Modus "Inseln")

Für die Option zum überlappenden Funktions Upgrade:

- Bedenken Sie diese Option, wenn Sie ein schnelles Upgrade für Ihre gesamte Organisation durchführen können.  Da es potenzielle Verwirrungs Risiken für Endbenutzer mit der Ausführung beider Clients gibt, ist es am besten, wenn Sie den Zeitraum minimieren können, in dem Benutzer beide Clients ausführen müssen. Sie sollten sicherstellen, dass Ihre Benutzer wissen, dass beide Clients ausgeführt werden.

- Bei dieser Option handelt es sich um das Out-of-the-Box-Modell, das keine Administratoraktion erfordert, um mit Teams zu beginnen, es sei denn, Sie weisen die Microsoft 365-oder Office 365-Lizenz zu. Wenn Ihre Benutzer bereits über Skype for Business Online verfügen, sind Sie möglicherweise bereits in diesem Modell.

- Es kann schwierig sein, den überlappenden Funktionsmodus zu verlassen und zu TeamsOnly zu wechseln. Da aktualisierte Benutzer nur über Teams kommunizieren, müssen alle anderen Benutzer in der Organisation, die mit diesem Benutzer kommunizieren, Teams verwenden.  Wenn Sie über Benutzer verfügen, die nicht mit der Verwendung von Teams begonnen haben, werden Sie fehlenden Nachrichten ausgesetzt. Darüber hinaus werden die TeamsOnly-Benutzer in Skype for Business nicht online angezeigt. Einige Organisationen entscheiden sich für ein mandantenweites Upgrade mit der globalen Mandanten-Richtlinie, um dies zu vermeiden, was jedoch eine Vorausplanung erfordert und wartet, bis alle Benutzer zum Upgrade bereit sind.


## <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a>Ein Upgrade der Auswahlfunktionen für eine Organisation, die noch nicht mit der Verwendung von Teams begonnen hat

Wenn in Ihrer Organisation noch keine aktiven Benutzer in Teams vorhanden sind, besteht der erste Schritt darin, die standardmäßige Mandantenweite Richtlinie für TeamsUpgradePolicy auf einen der Skype for Business-Modi zu setzen, beispielsweise SfbWithTeamsCollab.  Benutzer, die noch nicht mit der Verwendung von Teams begonnen haben, bemerken keinen Unterschied im Verhalten. Durch das Festlegen dieser Richtlinie auf Mandantenebene ist es jedoch möglich, Benutzer auf den TeamsOnly-Modus zu aktualisieren und sicherzustellen, dass die aktualisierten Benutzer weiterhin mit nicht aktualisierten Benutzern kommunizieren können.  Nachdem Sie Ihre Pilotbenutzer identifiziert haben, können Sie Sie auf TeamsOnly aktualisieren.  Wenn Sie lokal sind, verwenden Sie Move-CsUser. Wenn Sie online sind, weisen Sie Ihnen einfach den TeamsOnly-Modus mithilfe von Grant-CsTeamsUpgradePolicy zu. Standardmäßig werden alle von diesen Benutzern geplanten Skype for Business-Besprechungen in Teams migriert.

Im folgenden finden Sie die wichtigsten Befehle:

1. Setzen Sie die Mandantenweite Standardeinstellung auf Mode SfbWithTeamsCollab wie folgt:

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. Aktualisieren Sie die Pilotbenutzer auf TeamsOnly wie folgt:

   - Für einen Benutzer, der Online ist:

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username 
     ```

   - Für einen lokalen Benutzer:

     ```PowerShell
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
     ```

Hinweise
 
- Anstatt die Mandantenweite Richtlinie auf "SfbWithTeamsCollab" festzulegen, können Sie Sie auf "SfbWithTeamsCollabAndMeetings" festlegen. Dies bewirkt, dass alle Benutzer alle neuen Besprechungen in Teams planen.
- `Move-CsUser` ist ein Cmdlet in den lokalen Tools. Für den `MoveToTeams` Switch ist Skype for Business Server 2019 oder Skype for Business Server 2015 mit CU8 oder höher erforderlich. Wenn Sie eine frühere Version verwenden, können Sie den Benutzer zunächst in Skype for Business Online verschieben und dann dem Benutzer den TeamsOnly-Modus erteilen.
- Standardmäßig werden Skype for Business-Besprechungen in Teams migriert, wenn Sie auf den TeamsOnly-Modus aktualisieren oder den SfbWithTeamsCollabAndMeetings-Modus zuweisen.  

Das folgende Diagramm zeigt die konzeptionellen Phasen des Upgrades von SELECT-Funktionen für eine Organisation ohne vorherige Verwendung von Teams. Die Höhe der Balken steht für die Anzahl der Benutzer. In jeder Phase des Upgrades können alle Benutzer miteinander kommunizieren.  Skype for Business-Benutzer kommunizieren mit TeamsOnly-Benutzern über Interop und umgekehrt. Benutzer im Inseln-Modus müssen sicherstellen, dass beide Clients ausgeführt werden.

![Diagramm mit Auswahlmöglichkeiten für Upgrades ohne vorherige Verwendung von Teams](media/teams-upgrade-1.png)


## <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a>Ein Upgrade der Auswahlfunktionen für eine Organisation, die bereits Teams im Inseln-Modus verwendet

Wenn einige Benutzer in Ihrer Organisation Teams im Modus "Inseln" aktiv verwenden, möchten Sie möglicherweise die Funktionalität von vorhandenen Benutzern nicht entfernen. Daher ist ein zusätzlicher Schritt erforderlich, bevor die Mandantenweite Richtlinie geändert wird. Die Lösung besteht darin, diese vorhandenen aktiven Teams-Benutzer in den Modus "Inseln" zu übersetzen, bevor Sie die Mandantenweite Richtlinie auf "SfbWithTeamsCollab" festlegen.  Nachdem Sie dies abgeschlossen haben, können Sie die Bereitstellung wie oben beschrieben fortsetzen, jedoch haben Sie zwei Gruppen von Benutzern, die zu TeamsOnly wechseln: die Benutzer, die in Teams aktiv waren, befinden sich im Modus "Inseln", und die restlichen Benutzer befinden sich im SfbWithTeamsCollab-Modus. Sie können diese Benutzer schrittweise in den TeamsOnly-Modus verschieben.

1. Suchen Sie nach Benutzern, die in Teams wie folgt aktiv sind:

   1. Wechseln Sie im Microsoft 365 Admin Center in der Navigationsleiste auf der linken Seite zu Berichte, und verwenden Sie dann die Verwendung. 
   2. Wählen Sie im Dropdownmenü "Bericht auswählen" den Eintrag Microsoft Teams und dann Benutzeraktivität aus. Dadurch wird eine exportierbare Tabelle mit Benutzern bereitgestellt, die in Teams aktiv waren. 
   3. Klicken Sie auf exportieren, öffnen Sie Excel, und Filtern Sie, um nur die Benutzer anzuzeigen, die in Teams aktiv sind.

2. Weisen Sie für jeden in Schritt 1 gefundenen aktiven Teams-Benutzer den Modus "Inseln" in der Remote-PowerShell zu. So können Sie mit dem nächsten Schritt fortfahren und sicherstellen, dass Sie die Benutzeroberfläche nicht ändern.  

   ```PowerShell
   $users=get-content “C:\MyPath\users.txt” 
    foreach ($user in $users){ 
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands} 
   ```

3. Setzen Sie die Mandantenweite Richtlinie auf SfbWithTeamsCollab:

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab 
   ```

4. Ausgewählte Benutzer auf den TeamsOnly-Modus aktualisieren. Sie können entweder Benutzer im Inseln-Modus oder im SfbWithTeamsCollab-Modus aktualisieren, obwohl Sie möglicherweise zuerst die Aktualisierung der Benutzer im Modus "Inseln" priorisieren möchten, um die Verwirrung zu minimieren, die entstehen kann, wenn sich Benutzer im Inseln-Modus befinden.   

   Für Benutzer, die in Skype for Business Online verwaltet werden:  

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams 
   ```

   Für Benutzer, die in Skype for Business Server lokal verwaltet werden:  

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
   ```

Das folgende Diagramm zeigt die konzeptionellen Phasen eines Auswahl Funktions Übergangs, in dem am Anfang aktive Inseln-Benutzer vorhanden sind. Die Höhe der Balken steht für die Anzahl der Benutzer. In jeder Phase des Upgrades können alle Benutzer miteinander kommunizieren.  Skype for Business-Benutzer kommunizieren mit TeamsOnly-Benutzern über Interop und umgekehrt. 


![Diagramm mit Auswahlmöglichkeiten für das Upgrade für aktive Benutzer im Modus "Inseln"](media/teams-upgrade-2.png)

   



## <a name="related-links"></a>Verwandte Links

[Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](migration-interop-guidance-for-teams-with-skype.md) 

[Konfigurieren der Hybrid Konnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Verschieben von Benutzern zwischen lokalen Bereitstellungen und der Cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Festlegen Ihrer Einstellungen für Koexistenz und Upgrades](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Verwenden des Besprechungs Migrations Diensts (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

