---
title: Upgrade von Skype for Business Online auf Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Erfahren Sie, wie Sie Ihre Organisation für die Microsoft Teams einer Onlinebereitstellung Skype for Business upgraden.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8bb2924dfe6bab5afedda2b02b1027de057c9e86
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "58733934"
---
# <a name="upgrade-from-skype-for-business-online-to-teams"></a>Upgrade von Skype for Business Online auf Microsoft Teams

![Upgrade-Wegdiagramm mit Hervorhebung von Bereitstellung und Implementierung.](media/upgrade-banner-deployment.png "Phasen des Upgradewegs, mit Betonung auf der Bereitstellungs- und Implementierungsphase")

Dieser Artikel ist Teil der Phase Bereitstellung und Implementierung Ihres Upgrades. Bevor Sie fortfahren, vergewissern Sie sich, dass Sie die folgenden Aktivitäten abgeschlossen haben:

- [Ernennen der Projektbeteiligten](upgrade-enlist-stakeholders.md)
- [Definieren des Projektumfangs](./upgrade-define-project-scope.md)
- [Vertrautmachen mit der Koexistenz und Interoperabilität von Skype for Business und Microsoft Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Auswählen der Upgrade-Strategie](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Vorbereitet auf Ihre Umgebung](./upgrade-prepare-environment.md)
- [Vorbereitung Ihrer Organisation](./upgrade-prepare-organization.md)
- [Durchgeführtes Pilotprojekt](./pilot-essentials.md)

Folgen Sie den Anweisungen in diesem Artikel, wenn Sie eine Bereitstellung auf Skype for Business Online bereitgestellt haben und Ihre Benutzer von einem Skype for Business Auf Teams. Sie können Benutzer basierend auf dem von Ihrer Organisation ausgewählten Upgrade weg selektiv oder all-in aktualisieren, indem Sie den Benutzern die entsprechende Koexistenz und den entsprechenden Upgrademodus zuweisen.

> [!IMPORTANT]
> Skype for Business Online wird am 31. Juli 2021 eingestellt. Ab diesem Zeitpunkt kann nicht mehr darauf zugegriffen werden, und es wird nicht mehr unterstützt. Um den maximalen Nutzen zu erzielen und sicherzustellen, dass Ihre Organisation genügend Zeit hat, Ihr Upgrade durchzuführen, empfehlen wir Ihnen, den Wechsel zu Microsoft Teams bereits heute zu planen. Denken Sie daran, dass bei einem erfolgreichen Upgrade die technische und die Benutzerbereitschaft ausgerichtet ist. Daher sollten Sie unbedingt die hier beschriebenen Anleitungen nutzen, während Sie zu Ihrer Microsoft Teams.

## <a name="assign-the-coexistence-and-upgrade-mode"></a>Zuweisen der Koexistenz- und Upgrademodus

Sie können Ihre Benutzer in den TeamsOnly-Modus aktualisieren, indem Sie die UpgradeToTeams-Instanz von TeamsUpgradePolicy zuweisen, die mithilfe des Microsoft Teams Admin Centers oder einer Skype for Business-Remote-Windows PowerShell-Sitzung ausgeführt werden kann. Dies können Sie entweder pro Benutzer oder mandantenweit durchführen, wenn Sie in einem Schritt ein Upgrade für den gesamten Mandanten durchführen möchten. 

Weitere Informationen finden Sie unter Festlegen der Einstellungen für [Koexistenz](./setting-your-coexistence-and-upgrade-settings.md) und Upgrade und [TeamsUpgradePolicy: Verwalten von Migration und Koexistenz.](upgrade-to-teams-on-prem-tools.md)

## <a name="upgrade-all-users-to-teams-at-one-time"></a>Gleichzeitiges Upgrade aller Teams auf "Benutzer"

Führen Sie die folgenden Schritte aus, um alle Ihre Benutzer Teams gleichzeitig zu aktualisieren.

### <a name="step-1-notify-the-users-of-the-change-optional"></a>Schritt 1: Benachrichtigen der Benutzer über die Änderung (optional)

1. Wählen Sie Microsoft Teams Admin Center organisationsweite Einstellungen aus, um  >  **Teams zu aktualisieren.**
2. Ändern **Sie unter Koexistenzmodus** den Schalter Benachrichtigen Skype for Business Benutzer, dass ein Upgrade auf Teams **verfügbar** ist in **Ein.**

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a>Schritt 2: Festlegen des Koexistenzmodus auf TeamsOnly für die Organisation

1. Wählen Sie Microsoft Teams Admin Center **Organisationsweite Einstellungen aus.**
2. Wählen **Teams in der** Dropdownliste **Koexistenzmodus die** Option Nur Modus aus.

## <a name="upgrade-users-in-stages"></a>Stufenweises Upgrade von Benutzern

Führen Sie die folgenden Schritte aus, wenn Sie Ihre Benutzer schrittweise auf TeamsOnly aktualisieren möchten.

### <a name="step-1-identify-groups-of-users-for-upgrade"></a>Schritt 1: Identifizieren von Benutzergruppen für das Upgrade

Organisationen entscheiden sich häufig für ein Upgrade ihrer Organisation in Erfolgs welle von Benutzern.  Sie sollten diese Benutzer zuerst identifizieren, damit Sie sie ganz einfach im admin center Microsoft Teams können. Alternativ können Sie powerShell verwenden, um dies effizienter zu machen. Nachdem Sie die Gruppe der Benutzer für eine bestimmte Upgrade welle identifiziert haben, fahren Sie mit den verbleibenden Schritten fort.

### <a name="step-2-set-notification-for-the-users-in-the-current-upgrade-wave-optional"></a>Schritt 2: Festlegen der Benachrichtigung für die Benutzer in der aktuellen Upgrade welle (optional)

Wenn Sie das Microsoft Teams Admin Center verwenden, können Sie TeamsUpgradePolicy für bis zu 20 Benutzer gleichzeitig konfigurieren:
1. Wählen Sie Microsoft Teams Admin Center Benutzer **aus,** und suchen und aktivieren Sie das Kontrollkästchen für bis zu 20 Benutzer, für die ein Upgrade durchgeführt werden soll. 
2. Wählen **Sie in der** oberen linken Ecke der Listenansicht Einstellungen bearbeiten aus. 
3. Ändern Sie **im Bereich** Einstellungen bearbeiten auf der rechten Seite **unter Teams** die Option Benachrichtigen, Skype for Business **Benutzer** auf Ein **umschalten.** Hinweis: Wenn der Wert für den Koexistenzmodus "Organisationsweite Einstellungen verwenden" ist, wird dieser Schalter nicht angezeigt, daher müssen Sie zuerst den Koexistenzmodus für diese Benutzer explizit auf den Standardwert für die Organisation festlegen.

Alternativ finden Sie es vielleicht einfacher, Benachrichtigungen für Benutzergruppen gleichzeitig mit PowerShell zu aktivieren. 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a>Schritt 3: Festlegen des Koexistenzmodus für Benutzer auf "Teams".

Wenn Sie bereit sind, die Benutzer in der aktuellen Welle für die Verwendung von Teams als einzige Anwendung zu aktualisieren, legen Sie den Koexistenzmodus für die Benutzer auf Nur Teams festgelegt.

Wenn Sie das Microsoft Teams Admin Center verwenden, können Sie TeamsUpgradePolicy für bis zu 20 Benutzer gleichzeitig konfigurieren:
1. Wählen Sie Microsoft Teams Admin Center Benutzer **aus,** und aktivieren Sie dann das Kontrollkästchen für bis zu 20 Benutzer.
2. Wählen **Sie in der** oberen linken Ecke der Listenansicht Einstellungen bearbeiten aus.
3. Legen Sie **im Bereich** Einstellungen bearbeiten auf der rechten Seite **Teams** Abschnitt Upgrade den Koexistenzmodus auf **Teams** In der Dropdownliste auf Nur festgelegt.

Alternativ finden Sie das gleichzeitige Upgrade von Benutzergruppen mithilfe von PowerShell einfacher. 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a>Schritt 4: Wiederholen der Schritte 1 bis 3 für aufeinander folgende Benutzer welle

Wenn Sie Ihr Upgrade auf Teams-Modus überprüfen und zum Erweitern bereit sind, wiederholen Sie die vorherigen Schritte, um TeamsOnly auf mehr Benutzer anzuwenden.  


## <a name="phone-system-and-pstn-connectivity-options"></a>Telefonsystem und PSTN-Konnektivitätsoptionen

Telefonsystem mit Teams wird unterstützt, nachdem sich der Benutzer im TeamsOnly-Modus befindet. (Wenn sich der Benutzer im Islands-Modus befindet, Telefonsystem nur mit der Skype for Business.)  

### <a name="pstn-connectivity-options"></a>PSTN-Konnektivitätsoptionen

Bei der Überlegung nach Optionen für die Konnektivität über das öffentliche Telefonnetz (PSTN) gibt es zwei mögliche Szenarien beim Wechsel von Skype for Business Online in den TeamsOnly-Modus:

- Ein Benutzer in Skype for Business Online mit einem Microsoft-Anrufplan. Bei einem Upgrade verfügen diese Benutzer weiterhin über einen Microsoft-Anrufplan. Dies ist das einfachste Szenario, das nur ein paar Schritte erfordert. Weitere Informationen finden Sie unter [Von Skype for Business Online mit Microsoft-Anrufplänen](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans).

- Ein Benutzer in Skype for Business Online mit lokalen Sprachfunktionen über eine lokale Skype for Business oder Cloud Connector Edition. Das Upgrade des Benutzers auf Teams muss mit der Migration des Benutzers zu Direct-Routing koordiniert werden, um sicherzustellen, dass der TeamsOnly-Benutzer über PSTN-Funktionen verfügt.  Weitere Informationen finden Sie unter [Von Skype for Business online mit lokalem Sprachanruf.](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)