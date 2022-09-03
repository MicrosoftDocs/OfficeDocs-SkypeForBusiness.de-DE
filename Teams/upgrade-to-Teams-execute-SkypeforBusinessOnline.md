---
title: Upgrade von Skype for Business Online auf Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Erfahren Sie, wie Sie Ihre Organisation von einer Skype for Business Onlinebereitstellung auf Microsoft Teams aktualisieren.
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
ms.openlocfilehash: 5da45fcc5a9459b909e03f0d4e904b57d9a3f0fa
ms.sourcegitcommit: 9a9168d5c40bbb0cceaf3ffd11eb104c137f26b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2022
ms.locfileid: "67590212"
---
# <a name="upgrade-from-skype-for-business-online-to-teams"></a>Upgrade von Skype for Business Online auf Microsoft Teams

![Upgrade-Journey-Diagramm mit Betonung der Bereitstellung und Implementierung.](media/upgrade-banner-deployment.png "Phasen der Upgradephase mit Schwerpunkt auf der Bereitstellungs- und Implementierungsphase")

Dieser Artikel ist Teil der Bereitstellungs- und Implementierungsphase Ihrer Upgrade-Reise. Bevor Sie fortfahren, vergewissern Sie sich, dass Sie die folgenden Aktivitäten abgeschlossen haben:

- [Ernennen der Projektbeteiligten](upgrade-enlist-stakeholders.md)
- [Definieren des Projektumfangs](./upgrade-define-project-scope.md)
- [Vertrautmachen mit der Koexistenz und Interoperabilität von Skype for Business und Microsoft Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Auswählen der Upgrade-Strategie](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Vorbereiten Ihrer Umgebung](./upgrade-prepare-environment.md)
- [Ihre Organisation vorbereitet](./upgrade-prepare-organization.md)
- [Durchführen eines Pilotprojekts](./pilot-essentials.md)

Befolgen Sie die Anleitungen in diesem Artikel, wenn Sie Skype for Business Online vollständig bereitgestellt haben und Ihre Benutzer von Skype for Business auf Teams aktualisieren möchten. Sie können Benutzer basierend auf der von Ihrer Organisation ausgewählten Upgrade-Reise selektiv oder vollständig aktualisieren, indem Sie Den Benutzern den entsprechenden Koexistenz- und Upgrademodus zuweisen.

> [!IMPORTANT]
> Skype for Business Online wurde am 31. Juli 2021 eingestellt. Um den maximalen Nutzen zu erzielen und sicherzustellen, dass Ihre Organisation genügend Zeit hat, Ihr Upgrade durchzuführen, empfehlen wir Ihnen, den Wechsel zu Microsoft Teams bereits heute zu planen. Denken Sie daran, dass ein erfolgreiches Upgrade die technische und benutzertechnische Bereitschaft anordnen kann. Nutzen Sie daher unbedingt die hier aufgeführten Anleitungen, während Sie auf Ihrem Weg zu Microsoft Teams navigieren.

## <a name="assign-the-coexistence-and-upgrade-mode"></a>Zuweisen des Koexistenz- und Upgrademodus

Sie können Ihre Benutzer in den TeamsOnly-Modus aktualisieren, indem Sie die UpgradeToTeams-Instanz von TeamsUpgradePolicy zuweisen, die mithilfe des Microsoft Teams Admin Centers oder einer Skype for Business Remote-Windows PowerShell-Sitzung ausgeführt werden kann. Sie können dies entweder pro Benutzer oder mandantenweit tun, wenn Sie den gesamten Mandanten in einem Schritt aktualisieren möchten. 

Weitere Informationen finden Sie unter [Festlegen ihrer Koexistenz- und Upgradeeinstellungen](./setting-your-coexistence-and-upgrade-settings.md) und [TeamsUpgradePolicy: Verwalten von Migration und Koexistenz](upgrade-to-teams-on-prem-tools.md).

## <a name="upgrade-all-users-to-teams-at-one-time"></a>Gleichzeitiges Upgrade aller Benutzer auf Teams

Führen Sie die folgenden Schritte aus, um alle Ihre Benutzer gleichzeitig auf Teams zu aktualisieren.

### <a name="step-1-notify-the-users-of-the-change-optional"></a>Schritt 1: Benachrichtigen der Benutzer über die Änderung (optional)

1. Wählen Sie im Microsoft Teams Admin Center die **Upgradeeinstellungen** für **Teams** >  Teams aus.
2. Ändern Sie im **Koexistenzmodus** die Option **"Benutzer benachrichtigen Skype for Business, dass ein Upgrade auf Teams verfügbar ist**, auf **"Ein**".

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a>Schritt 2: Festlegen des Koexistenzmodus auf TeamsOnly für die Organisation

1. Wählen Sie im Microsoft Teams Admin Center die **Upgradeeinstellungen** für **Teams** >  Teams aus.
2. Wählen Sie in der Dropdownliste "**Koexistenzmodus**" den Modus "**Nur Teams**" aus.

## <a name="upgrade-users-in-stages"></a>Stufenweises Upgrade von Benutzern

Führen Sie die folgenden Schritte aus, wenn Sie Ihre Benutzer schrittweise auf TeamsOnly aktualisieren möchten.

### <a name="step-1-identify-groups-of-users-for-upgrade"></a>Schritt 1: Identifizieren von Benutzergruppen für das Upgrade

Häufig können Sich Organisationen entscheiden, ihre Organisationen in Erfolgswellen von Benutzern zu aktualisieren.  Sie sollten diese Benutzer zuerst identifizieren, damit Sie im Microsoft Teams Admin Center problemlos danach suchen können. Alternativ können Sie PowerShell verwenden, um dies effizienter zu machen. Nachdem Sie die Gruppe von Benutzern für eine bestimmte Upgradewelle identifiziert haben, fahren Sie mit den verbleibenden Schritten fort.

### <a name="step-2-set-notification-for-the-users-in-the-current-upgrade-wave-optional"></a>Schritt 2: Festlegen der Benachrichtigung für die Benutzer in der aktuellen Upgradewelle (optional)

Wenn Sie das Microsoft Teams Admin Center verwenden, können Sie TeamsUpgradePolicy für bis zu 20 Benutzer gleichzeitig konfigurieren:
1. Wählen Sie im Microsoft Teams Admin Center **"Benutzer**" aus, und suchen und aktivieren Sie das Kontrollkästchen für bis zu 20 Benutzer, die aktualisiert werden sollen. 
2. Wählen Sie " **Einstellungen bearbeiten"** in der oberen linken Ecke der Listenansicht aus. 
3. Ändern Sie im Bereich **"Einstellungen bearbeiten**" auf der rechten Seite unter "**Teams-Upgrade**" **den Schalter "Skype for Business Benutzer** benachrichtigen" auf **"Ein**". Hinweis: Wenn der Wert des Koexistenzmodus "Organisationsweite Einstellungen verwenden" lautet, wird dieser Schalter nicht angezeigt, daher müssen Sie zuerst explizit den Koexistenzmodus für diese Benutzer auf den Standardwert für die Organisation festlegen.

Alternativ können Sie es einfacher finden, Benachrichtigungen für Benutzergruppen gleichzeitig mithilfe von PowerShell zu aktivieren. Weitere Informationen finden Sie [unter Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy).

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a>Schritt 3: Festlegen des Koexistenzmodus für Benutzer auf "Nur Teams"

Wenn Sie bereit sind, die Benutzer in der aktuellen Welle so zu aktualisieren, dass sie Teams als einzige Anwendung verwenden, legen Sie den Koexistenzmodus für die Benutzer auf "Nur Teams" fest.

Wenn Sie das Microsoft Teams Admin Center verwenden, können Sie TeamsUpgradePolicy für bis zu 20 Benutzer gleichzeitig konfigurieren:
1. Wählen Sie im Microsoft Teams Admin Center **"Benutzer**" und dann das Kontrollkästchen für bis zu 20 Benutzer aus.
2. Wählen Sie " **Einstellungen bearbeiten"** in der oberen linken Ecke der Listenansicht aus.
3. Legen Sie im Bereich **"Einstellungen bearbeiten** " auf der rechten Seite unter dem Abschnitt " **Teams-Upgrade** " den Koexistenzmodus in der Dropdownliste auf **"Nur Teams** " fest.

Alternativ können Sie es einfacher finden, Gruppen von Benutzern gleichzeitig mithilfe von PowerShell zu aktualisieren. Weitere Informationen finden Sie [unter Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy).

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a>Schritt 4: Wiederholen der Schritte 1 bis 3 für aufeinander folgende Benutzerwellen

Wenn Sie Ihr Upgrade auf den Modus "Nur Teams" überprüfen und erweitern möchten, wiederholen Sie die vorherigen Schritte, um TeamsOnly auf weitere Benutzer anzuwenden.  


## <a name="phone-system-and-pstn-connectivity-options"></a>Optionen für Telefonsystem und Festnetzanbindung

Das Telefonsystem mit Teams wird unterstützt, nachdem sich der Benutzer im TeamsOnly-Modus befindet. (Wenn sich der Benutzer im Inselmodus befindet, wird das Telefonsystem nur mit Skype for Business unterstützt.)  

### <a name="pstn-connectivity-options"></a>PSTN-Konnektivitätsoptionen

Bei der Betrachtung von PSTN-Konnektivitätsoptionen (Public Switched Telephone Network, PSTN) gibt es zwei mögliche Szenarien beim Wechsel von Skype for Business Online in den TeamsOnly-Modus:

- Ein Benutzer in Skype for Business Online mit einem Microsoft-Anrufplan: Nach dem Upgrade verfügt dieser Benutzer weiterhin über einen Microsoft-Anrufplan. Dies ist das einfachste Szenario, in dem nur einige Schritte erforderlich sind. Weitere Informationen finden Sie [unter From Skype for Business Online with Microsoft Calling Plans](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans).

- Ein Benutzer in Skype for Business Online mit lokalen Anruffunktionen über lokales Skype for Business oder Cloud Connector Edition: Das Upgrade des Benutzers auf Microsoft Teams muss mit seinem Wechsel zu Direct Routing koordiniert werden, um sicherzustellen, dass dem TeamsOnly-Benutzer Festnetzfunktionen zur Verfügung stehen.  Weitere Informationen finden Sie unter [From Skype for Business Online mit lokaler Sprachausgabe](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice).
