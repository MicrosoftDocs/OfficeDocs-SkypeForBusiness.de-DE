---
title: Upgrade von Skype for Business Online auf Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Erfahren Sie, wie Sie Ihr Unternehmen über eine Skype for Business Online-Bereitstellung auf Microsoft Teams aktualisieren.
localization_priority: Normal
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
ms.openlocfilehash: 65b00f8e56792164ed2aa0b8240d0d131a7bdbcd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104011"
---
# <a name="upgrade-from-skype-for-business-online-to-teams"></a>Upgrade von Skype for Business Online auf Microsoft Teams

![Upgrade-Reisediagramm mit Betonung auf Bereitstellung und Implementierung](media/upgrade-banner-deployment.png "Phasen des Upgradewegs mit Schwerpunkt auf der Bereitstellungs- und Implementierungsphase")

Dieser Artikel ist Teil der Bereitstellungs- und Implementierungsphase Ihres Upgradewegs. Bevor Sie fortfahren, vergewissern Sie sich, dass Sie die folgenden Aktivitäten abgeschlossen haben:

- [Ernennen der Projektbeteiligten](upgrade-enlist-stakeholders.md)
- [Definieren des Projektumfangs](./upgrade-define-project-scope.md)
- [Vertrautmachen mit der Koexistenz und Interoperabilität von Skype for Business und Microsoft Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Auswählen der Upgrade-Strategie](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Vorbereiten Ihrer Umgebung](./upgrade-prepare-environment.md)
- [Vorbereiten Ihrer Organisation](./upgrade-prepare-organization.md)
- [Pilot durchgeführt](./pilot-essentials.md)

Befolgen Sie die Anleitungen in diesem Artikel, wenn Sie Skype for Business Online vollständig bereitgestellt haben und Ihre Benutzer von Skype for Business auf Teams aktualisieren möchten. Sie können Die Benutzer selektiv oder alle Ein-/Aus-Ressourcen basierend auf dem von Ihrer Organisation ausgewählten Upgradeweg aktualisieren, indem Sie den Benutzern die entsprechende Koexistenz- und Upgrademodus zuweisen.

> [!IMPORTANT]
> Skype for Business Online wird am 31. Juli 2021 eingestellt. Ab diesem Zeitpunkt kann nicht mehr darauf zugegriffen werden, und es wird nicht mehr unterstützt. Um den maximalen Nutzen zu erzielen und sicherzustellen, dass Ihre Organisation genügend Zeit hat, Ihr Upgrade durchzuführen, empfehlen wir Ihnen, den Wechsel zu Microsoft Teams bereits heute zu planen. Denken Sie daran, dass ein erfolgreiches Upgrade die technische Bereitschaft und Benutzerbereitschaft an sich richtet. Verwenden Sie daher unbedingt die hierin enthaltenen Anleitungen, während Sie auf Ihrem Weg zu Microsoft Teams navigieren.

## <a name="assign-the-coexistence-and-upgrade-mode"></a>Zuweisen des Koexistenz- und Upgrademodus

Sie können Ein Upgrade Ihrer Benutzer auf den TeamsOnly-Modus durchführen, indem Sie die UpgradeToTeams-Instanz von TeamsUpgradePolicy zuweisen, die mithilfe des Microsoft Teams Admin Centers oder einer Skype for Business-Remote-Windows PowerShell ausgeführt werden kann. Sie können dies entweder auf Benutzerbasis oder mandantenweit ausführen, wenn Sie den gesamten Mandanten in einem Schritt aktualisieren möchten. 

Weitere Informationen finden Sie unter [Festlegen der Einstellungen für Koexistenz](./setting-your-coexistence-and-upgrade-settings.md) und Upgrade und [TeamsUpgradePolicy: Verwalten von Migration und Koexistenz](upgrade-to-teams-on-prem-tools.md).

## <a name="upgrade-all-users-to-teams-at-one-time"></a>Gleichzeitiges Upgrade aller Benutzer auf Teams

Führen Sie die folgenden Schritte aus, um alle Benutzer gleichzeitig auf Teams zu aktualisieren.

### <a name="step-1-notify-the-users-of-the-change-optional"></a>Schritt 1: Benachrichtigen der Benutzer über die Änderung (optional)

1. Wählen Sie im Microsoft Teams Admin Center die Option **Organisationsweite Einstellungen**  >  **Teams upgrade aus.**
2. Ändern **Sie unter Koexistenzmodus** den Schalter Skype **for Business-Benutzer** benachrichtigen, dass ein Upgrade auf Teams verfügbar ist, auf **Ein.**

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a>Schritt 2: Festlegen des Koexistenzmodus auf TeamsOnly für die Organisation

1. Wählen Sie im Microsoft Teams Admin Center **organisationsweite Einstellungen aus.**
2. Wählen **Sie in der** Dropdownliste **Koexistenzmodus den** Modus Teams only aus.

## <a name="upgrade-users-in-stages"></a>Stufenweises Upgrade von Benutzern

Führen Sie diese Schritte aus, wenn Sie Ihre Benutzer schrittweise auf TeamsOnly aktualisieren möchten.

### <a name="step-1-identify-groups-of-users-for-upgrade"></a>Schritt 1: Identifizieren von Benutzergruppen für ein Upgrade

Häufig entscheiden sich Organisationen für ein Upgrade ihrer Organisationen in Erfolgs welle von Benutzern.  Sie sollten diese Benutzer zuerst identifizieren, damit Sie im Microsoft Teams Admin Center ganz einfach nach ihnen suchen können. Alternativ können Sie PowerShell verwenden, um dies effizienter zu machen. Nachdem Sie die Benutzer für eine bestimmte Upgradewelle identifiziert haben, fahren Sie mit den verbleibenden Schritten fort.

### <a name="step-2-set-notification-for-the-users-in-the-current-upgrade-wave-optional"></a>Schritt 2: Festlegen der Benachrichtigung für die Benutzer in der aktuellen Upgradewelle (optional)

Wenn Sie das Microsoft Teams Admin Center verwenden, können Sie TeamsUpgradePolicy für bis zu 20 Benutzer gleichzeitig konfigurieren:
1. Wählen Sie im Microsoft Teams Admin Center Benutzer **aus,** und aktivieren Sie das Kontrollkästchen für bis zu 20 Benutzer, für die ein Upgrade durchgeführt werden soll. 
2. Wählen **Sie einstellungen** bearbeiten in der oberen linken Ecke der Listenansicht aus. 
3. Ändern Sie **im Bereich** Einstellungen bearbeiten auf der rechten Seite unter **Teams-Upgrade** die Option Skype **for Business-Benutzer** benachrichtigen auf **Ein.** Hinweis: Wenn der Wert des Koexistenzmodus "Organisationsweite Einstellungen verwenden" ist, wird dieser Schalter nicht angezeigt, daher müssen Sie zuerst den Koexistenzmodus für diese Benutzer explizit auf den Standardwert für die Organisation festlegen.

Alternativ kann es einfacher sein, Benachrichtigungen für Benutzergruppen gleichzeitig mit PowerShell zu aktivieren. 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a>Schritt 3: Festlegen des Koexistenzmodus für Benutzer auf Nur Teams

Wenn Sie bereit sind, ein Upgrade der Benutzer in der aktuellen Welle durchführen zu können, um Teams als einzige Anwendung zu verwenden, legen Sie den Koexistenzmodus für die Benutzer auf Teams Only (Nur Teams) festgelegt.

Wenn Sie das Microsoft Teams Admin Center verwenden, können Sie TeamsUpgradePolicy für bis zu 20 Benutzer gleichzeitig konfigurieren:
1. Wählen Sie im Microsoft Teams Admin Center **Benutzer** und dann das Kontrollkästchen für bis zu 20 Benutzer aus.
2. Wählen **Sie einstellungen** bearbeiten in der oberen linken Ecke der Listenansicht aus.
3. Legen Sie **im Bereich** Einstellungen bearbeiten auf der rechten Seite unter **Abschnitt "Teams-Upgrade"** den Koexistenzmodus in der Dropdownliste auf **"Teams Only"** ein.

Alternativ können Sie es einfacher finden, Benutzergruppen mit PowerShell gleichzeitig zu aktualisieren. 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a>Schritt 4: Wiederholen der Schritte 1 bis 3 für aufeinander folgende Wellen von Benutzern

Wiederholen Sie die vorherigen Schritte zum Anwenden von TeamsOnly auf mehr Benutzer, während Sie Ihr Upgrade auf den Modus "Nur Teams" überprüfen und zum Erweitern bereit sind.  


## <a name="phone-system-and-pstn-connectivity-options"></a>Optionen für Telefonsystem- und PSTN-Konnektivität

Telefonsystem mit Teams wird unterstützt, nachdem sich der Benutzer im TeamsOnly-Modus befindet. (Wenn sich der Benutzer im Inselmodus befindet, wird Telefonsystem nur mit Skype for Business unterstützt.)  

### <a name="pstn-connectivity-options"></a>PstN-Konnektivitätsoptionen

Bei der Berücksichtigung der Konnektivitätsoptionen für das öffentliche Telefonnetz (PSTN) gibt es zwei mögliche Szenarien beim Wechsel von Skype for Business Online in den TeamsOnly-Modus:

- Ein Benutzer in Skype for Business Online mit einem Microsoft-Anrufplan. Nach dem Upgrade hat dieser Benutzer weiterhin einen Microsoft Calling-Plan. Dies ist das einfachste Szenario, das nur einige Schritte erfordert. Weitere Informationen finden Sie unter [Von Skype for Business Online mit Microsoft-Anrufplänen](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans).

- Ein Benutzer in Skype for Business Online mit lokalen Sprachfunktionen über Skype for Business lokal oder Cloud Connector Edition. Das Upgrade des Benutzers auf Teams muss mit der Migration des Benutzers zu Direct Routing koordiniert werden, um sicherzustellen, dass der TeamsOnly-Benutzer über PSTN-Funktionen verfügt.  Weitere Informationen finden Sie unter [From Skype for Business Online with on-premises voice](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice).