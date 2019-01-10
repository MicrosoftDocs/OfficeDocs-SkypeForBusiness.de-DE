---
title: Aktualisieren von Skype für Unternehmen Online auf Teams - Microsoft-Teams
author: arachmanGitHub
ms.author: arachman
manager: serdars
ms.date: 12/26/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Überlegungen für das Upgrade auf Teams von Skype für Business Online
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Teams_ITAdmin_JourneyFromSfB
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4f454b3c6e7ae41e87c9d44c02cd76b995313fc7
ms.sourcegitcommit: 0458232441d3aed8dd578f41a13078aa379c9b00
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/10/2019
ms.locfileid: "27789331"
---
![Phasen der Upgrade Reise, wobei der Schwerpunkt auf der Bereitstellung und Implementierungsphase] (media/upgrade-banner-deployment.png "Phasen der Upgrade Reise, wobei der Schwerpunkt auf der Bereitstellung und Implementierungsphase")

Dieser Artikel ist Teil der Bereitstellung und Implementierung Stufe der Ihrem Upgrade Weg. Bevor Sie fortfahren, vergewissern Sie sich, dass Sie die folgenden Aktivitäten ausgeführt haben:

-   [Ihre Projektbeteiligten eingetragen](upgrade-enlist-stakeholders.md)
-   [Definiert die Projektumfang](https://aka.ms/SkypetoTeams-Scope)
-   [Skype-Interoperabilität und Koexistenz für Unternehmen und Teams verstanden](https://aka.ms/SkypeToTeams-Coexist)
-   [Ihre Reise Upgrade ausgewählt](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [Die Umgebung vorbereitet](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [Ihre Organisation vorbereitet](https://aka.ms/SkypeToTeams-UserReadiness)
-   [Ein Pilotprojekt durchgeführt.](https://aka.ms/SkypeToTeams-Pilot)


# <a name="upgrade-from-skype-for-business-online-to-teams"></a>Aktualisieren von Skype für Unternehmen Online auf Teams

Führen Sie die Anweisungen in diesem Artikel, wenn Sie vollständig Skype für Business Online bereitgestellt haben und Ihre Benutzer von Skype für Unternehmen, die Teams aktualisieren möchten. Sie können Benutzer selektiv aktualisieren oder-Ansatz repräsentieren, basierend auf das Upgrade journey, die Ihrer Organisation ausgewählt hat, durch Ihre Benutzer die entsprechenden Koexistenz und Aktualisierungsmodus zuweisen.

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="assign-the-coexistence-and-upgrade-mode"></a>Weisen Sie den Modus für Upgrade und Koexistenz

Sie können die Benutzer von Teams, die durch Zuweisen von den TeamsOnly Modus der TeamsUpgradePolicy, die ausgeführt werden kann, unter Verwendung der Microsoft-Teams & Skype für Business Admin Center oder einen Skype für Business remote Windows Powershell-Sitzung aktualisieren.

Weitere Informationen finden Sie unter [Festlegen der Koexistenz und Durchführen eines Upgrades Einstellungen](https://aka.ms/SkypeToTeams-SetCoexistence) und [TeamsUpgradePolicy: Verwalten von Migration und Koexistenz](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).

## <a name="upgrade-all-users-to-teams-at-one-time"></a>Aktualisieren Sie alle Benutzer gleichzeitig auf Teams

Befolgen Sie diese Schritte, um alle Benutzer gleichzeitig auf Teams aktualisieren.

### <a name="step-1-notify-the-users-of-the-change"></a>Schritt 1: Fordern Sie die Benutzer der Änderung 

1. Wählen Sie in der Microsoft-Teams & Skype für Business Admin Center **Org geltende Einstellungen** > **Teams zu aktualisieren**. 
2. Ändern Sie die Option **Benachrichtigen Skype für Unternehmensbenutzer, dass ein Upgrade auf Teams verfügbar ist** unter **Koexistenzmodus**auf **aktiviert**.

### <a name="step-2-set-the-coexistence-mode-for-the-users"></a>Schritt 2: Festlegen des Koexistenzmodus für die Benutzer 

1. Wählen Sie in der Microsoft-Teams & Skype für Business Admin Center **Org geltende Einstellungen**aus. 
2. Wählen Sie aus der Dropdownliste **Koexistenzmodus** **Teams** nur Kopfzeilen herunterladen aus.
 
## <a name="upgrade-users-in-stages"></a>Aktualisieren Sie die Benutzer in Phasen

Gehen Sie folgendermaßen vor, wenn Sie Ihren Benutzern, Teams schrittweise aktualisieren möchten.

### <a name="step-1-create-your-user-cohorts-for-the-upgrade"></a>Schritt 1: Erstellen Sie Ihrer Benutzer Kohorten für das upgrade 

Benutzer Kohorten sind Gruppen von Benutzern, die gleichzeitig in Teams nur Kopfzeilen herunterladen verschoben werden sollen.  

Erstellen Sie Ihre Benutzer Kohorten (Add Link zur Seite zur Auswahl)
 
### <a name="step-2-set-the-user-mode-to-islands"></a>Schritt 2: Festlegen des Benutzermodus Inseln 

1. Wählen Sie in der Microsoft-Teams & Skype für Business Admin Center **Benutzer**aus, und wählen Sie dann einen Benutzer Kohorte.
2. Neben der **Aktualisierung von Teams**wählen Sie **Bearbeiten**aus.
3. Wählen Sie im Bereich **Teams zu aktualisieren** , klicken Sie unter **Koexistenzmodus** **Inseln** aus der Dropdown-Liste. 

### <a name="step-3-set-notification-for-the-user-optional"></a>Schritt 3: Einrichten der Benachrichtigung für den Benutzer (optional) 

1. Klicken Sie im Microsoft-Teams & Skype für Business Admin Center wählen Sie **Benutzer**aus, und wählen Sie einen Benutzer Kohorte.
2. Neben der **Aktualisierung von Teams**wählen Sie **Bearbeiten**aus.
3. Ändern Sie im Bereich **Teams Upgrade** unter **Koexistenzmodus** **Benachrichtigen der Skype für Geschäftsbenutzer** Switch auf **aktiviert**.

### <a name="step-4-set-the-user-mode-to-teams-only"></a>Schritt 4: Festlegen des Benutzermodus nur Teams 

Wenn Sie die Benutzer zum Verwenden von Teams als einzige Programmversionen aktualisieren möchten, legen Sie den Modus der Koexistenz für den Benutzer nur Teams.  

1. Wählen Sie in der Microsoft-Teams & Skype für Business Admin Center **Benutzer**aus, und wählen Sie dann einen Benutzer Kohorte.
2. Neben der **Aktualisierung von Teams**wählen Sie **Bearbeiten**aus.
3. Wählen Sie das **Aktualisieren von Teams** unter **Koexistenzmodus**im Bereich **Teams nur** aus der Dropdown-Liste. 

## <a name="phone-system-and-teams-upgrade"></a>Upgrade Telefonsystem und Teams

Wenn Ihre Skype für Business Online-Bereitstellung Telefonsystem mit Aufrufen plant umfasst und Microsoft Ihren öffentlichen Telefonnetz Netzwerkanbieter (PSTN) ist, wird Aktualisieren Ihrer Benutzer auf Teams automatisch eingehende PSTN-Aufruf von Teams umzustellen.

Wenn Ihre Skype für Business Online Bereitstellung Telefonsystem mit Cloud Connector Edition umfasst, finden Sie unter die [zusätzliche Überlegungen für das Telefon System direkte Routing](2-envision-make-my-service-decisions-direct-routing.md).