---
title: Aktualisieren von Skype für Unternehmen, die Microsoft-Teams Online | Bereitstellen
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Überlegungen für das Upgrade auf Teams von Skype für Business Online
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6748397c354f9238282f9646388993fc0e9f7b88
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33902720"
---
![Phasen der Upgrade Reise, wobei der Schwerpunkt auf der Bereitstellung und Implementierungsphase] (media/upgrade-banner-deployment.png "Phasen der Upgrade Reise, wobei der Schwerpunkt auf der Bereitstellung und Implementierungsphase")

Dieser Artikel ist Teil der Bereitstellung und Implementierung Stufe der Ihrem Upgrade Weg. Bevor Sie fortfahren, vergewissern Sie sich, dass Sie die folgenden Aktivitäten ausgeführt haben:

- [Ihre Projektbeteiligten eingetragen](upgrade-enlist-stakeholders.md)
- [Definiert die Projektumfang](https://aka.ms/SkypetoTeams-Scope)
- [Skype-Interoperabilität und Koexistenz für Unternehmen und Teams verstanden](https://aka.ms/SkypeToTeams-Coexist)
- [Ihre Reise Upgrade ausgewählt](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Die Umgebung vorbereitet](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [Ihre Organisation vorbereitet](https://aka.ms/SkypeToTeams-UserReadiness)
- [Ein Pilotprojekt durchgeführt.](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-skype-for-business-online-to-teams"></a>Upgrade von Skype for Business Online auf Microsoft Teams

Führen Sie die Anweisungen in diesem Artikel, wenn Sie vollständig Skype für Business Online bereitgestellt haben und Ihre Benutzer von Skype für Unternehmen, die Teams aktualisieren möchten. Sie können Benutzer selektiv aktualisieren oder-Ansatz repräsentieren, basierend auf das Upgrade journey, die Ihrer Organisation ausgewählt hat, durch Ihre Benutzer die entsprechenden Koexistenz und Aktualisierungsmodus zuweisen.

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="assign-the-coexistence-and-upgrade-mode"></a>Weisen Sie den Modus für Upgrade und Koexistenz

Sie können Ihre Benutzer in den Modus TeamsOnly aktualisieren, durch Zuweisen der UpgradeToTeams Instanz des TeamsUpgradePolicy, die über das Microsoft-Teams, Administrationscenter oder einen Skype für Business remote Windows Powershell-Sitzung durchgeführt werden kann. Sie können für jeden Benutzer einzeln oder für einzelne Mandanten geltende vorgehen, wenn Sie den gesamten Mandanten in einem Schritt Ugprade möchten. 

Weitere Informationen finden Sie unter [Festlegen der Koexistenz und Durchführen eines Upgrades Einstellungen](https://aka.ms/SkypeToTeams-SetCoexistence) und [TeamsUpgradePolicy: Verwalten von Migration und Koexistenz](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).

## <a name="upgrade-all-users-to-teams-at-one-time"></a>Aktualisieren Sie alle Benutzer gleichzeitig auf Teams

Befolgen Sie diese Schritte, um alle Benutzer gleichzeitig auf Teams aktualisieren.

### <a name="step-1-notify-the-users-of-the-change-optional"></a>Schritt 1: Fordern Sie die Benutzer der Änderung (optional)

1. Wählen Sie in der Verwaltungskonsole von Microsoft-Teams, **Org geltende Einstellungen** > **Teams zu aktualisieren**.
2. Ändern Sie die Option **Benachrichtigen Skype für Unternehmensbenutzer, dass ein Upgrade auf Teams verfügbar ist** unter **Koexistenzmodus**auf **aktiviert**.

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a>Schritt 2: Legen Sie den Koexistenzmodus auf TeamsOnly für die Organisation

1. Wählen Sie in der Verwaltungskonsole von Microsoft-Teams, **Org geltende Einstellungen**aus.
2. Wählen Sie aus der Dropdownliste **Koexistenzmodus** **Teams** nur Kopfzeilen herunterladen aus.

## <a name="upgrade-users-in-stages"></a>Aktualisieren Sie die Benutzer in Phasen

Gehen Sie folgendermaßen vor, wenn Ihre Benutzer auf TeamsOnly schrittweise aktualisiert werden soll.

### <a name="step-1-identify-groups-of-users-for-upgrade"></a>Schritt 1: Identifizieren der Gruppen von Benutzern für das upgrade

Häufig Organisationen möglicherweise entscheiden sich für Organisationen in Erfolg hochrangige von Benutzern zu aktualisieren.  Sie sollten diese Benutzer zuerst zu identifizieren, damit Sie auf einfache Weise in der Verwaltungskonsole von Microsoft-Teams suchen können. Alternativ können Sie PowerShell effizienter dazu verwenden möchten. Nachdem Sie die Gruppe von Benutzern für eine bestimmte Upgrade Welle identifiziert haben, fahren Sie mit der restlichen Schritte.

### <a name="step-2-set-notification-for-the-users-in-the-current-ugprade-wave-optional"></a>Schritt 2: Einrichten der Benachrichtigung für die Benutzer in der aktuellen Ugprade Welle (optional)

Wenn Sie das Microsoft-Teams, Administrationscenter verwenden, können Sie gleichzeitig TeamsUpgradePolicy für bis zu 20 Benutzer konfigurieren:
1. Kontrollkästchen Sie in der Verwaltungskonsole von Microsoft-Teams **Benutzer**, und suchen und mit mehreren auswählen das für bis zu 20 Benutzer, die aktualisiert werden soll. 
2. Wählen Sie in der oberen linken Ecke des Listview **Einstellungen bearbeiten** . 
3. Ändern Sie im Bereich **Einstellungen bearbeiten** auf der rechten Seite unter **Aktualisieren von Teams** **Benachrichtigen der Skype für Geschäftsbenutzer** Switch auf **aktiviert**. Hinweis: Wenn der Wert der Koexistenzmodus "Einstellungen für Verwendung Org geltende" ist, wird dieser Option nicht angezeigt, müssen Sie zunächst explizit festlegen den Koexistenz-Modus für diese Benutzer auf den Inhalt der Standardwert für die org ist

Alternativ können Sie zum Aktivieren von Benachrichtigungen für Gruppen von Benutzern, die gleichzeitig von PowerShell einfacher. 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a>Schritt 3: Festlegen des Koexistenzmodus für Benutzer nur Teams

Wenn Sie die Benutzer in der aktuellen Welle zum Verwenden von Teams als einzige Programmversionen aktualisieren möchten, legen Sie den Modus Koexistenz für die Benutzer nur Teams.

Wenn Sie das Microsoft-Teams, Administrationscenter verwenden, können Sie gleichzeitig TeamsUpgradePolicy für bis zu 20 Benutzer konfigurieren:
1. Wählen Sie in der Verwaltungskonsole von Microsoft-Teams **Benutzer**aus, und klicken Sie dann das Kontrollkästchen für bis zu 20 Benutzer.
2. Wählen Sie in der oberen linken Ecke des Listview **Einstellungen bearbeiten** .
3. Klicken Sie im Bereich **Einstellungen bearbeiten** auf der rechten Seite unter **Aktualisieren von Teams** Abschnitt legen Sie die Koexistenz auf **Teams nur** in der Dropdown-Liste.

Alternativ können Sie Gruppen von Benutzern, die gleichzeitig von PowerShell aktualisieren einfacher. 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a>Schritt 4: Wiederholen Sie die Schritte 1 bis 3 für aufeinander folgende hochrangige von Benutzern

Beim Überprüfen des Upgrades auf Teams nur Kopfzeilen herunterladen und zum Erweitern bereit sind, wiederholen Sie die vorherigen Schritte, um TeamsOnly auf mehrere Benutzer anwenden.  


## <a name="phone-system-and-teams-upgrade"></a>Upgrade Telefonsystem und Teams

Wenn Ihre Skype für Business Online-Bereitstellung Telefonsystem mit Aufrufen plant umfasst und Microsoft Ihren öffentlichen Telefonnetz Netzwerkanbieter (PSTN) ist, wird Aktualisieren Ihrer Benutzer auf Teams automatisch eingehende PSTN-Aufruf von Teams umzustellen.

Wenn Ihre Skype für Business Online Bereitstellung Telefonsystem mit Cloud Connector Edition umfasst, finden Sie unter die [zusätzliche Überlegungen für das Telefon System direkte Routing](2-envision-make-my-service-decisions-direct-routing.md).
