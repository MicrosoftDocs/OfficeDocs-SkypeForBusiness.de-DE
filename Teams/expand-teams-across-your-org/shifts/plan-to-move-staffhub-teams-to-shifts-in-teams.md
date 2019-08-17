---
title: Planen, ihre StaffHub-Teams in Microsoft Teams zu verschieben
author: LanaChin
ms.author: v-lanac
ms.reviewer: gumariam,aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Hier erfahren Sie, wie Sie Ihre StaffHub-Teams auf Schichten in Microsoft Teams verschieben können.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0804b3fb0783a588fdd79dfec1a8dd39e4d92f34
ms.sourcegitcommit: a0df7479662b3bea488c19722ad588981f58a5e4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/16/2019
ms.locfileid: "36447966"
---
# <a name="plan-to-move-your-staffhub-teams-to-shifts-in-microsoft-teams"></a>Planen, ihre StaffHub-Teams in Microsoft Teams zu verschieben

> [!IMPORTANT]
> Ab dem 1. Oktober 2019 wird Microsoft StaffHub eingestellt. Wir erstellen StaffHub-Funktionen in Microsoft Teams. Heute umfasst Teams die Schicht-App für die Terminplanung, und zusätzliche Funktionen werden im Laufe der Zeit bereitgestellt. StaffHub wird für alle Benutzer am 1. Oktober 2019 nicht mehr funktionieren. Jede Person, die versucht, StaffHub zu öffnen, wird eine Meldung angezeigt, die Sie zum Herunterladen von Teams anweist. Weitere Informationen finden Sie unter [Microsoft StaffHub](microsoft-staffhub-to-be-retired.md). 

Der Übergang von StaffHub zu Teams beginnt, wenn Sie mit der Planung der Änderung beginnen. Um sicherzustellen, dass Ihr Umzug in Teams erfolgreich ist, haben wir eine Beispiel Zeitachse erstellt, die einen typischen Übergangsplan veranschaulicht. In der Beispiel Zeitachse werden Planungsaktivitäten zur Vorbereitung des Umzugs beschrieben, und Sie gelangen durch das Verschieben der StaffHub-Teams Ihrer Organisation in Teams.

Verwenden Sie die Zeitachse als Leitfaden für die Planung Ihres Umstiegs von StaffHub in Teams, und passen Sie Sie entsprechend den Anforderungen Ihrer Organisation an. Überprüfen Sie unbedingt die Ressourcen, die mit den Schritten in der Zeitachse verknüpft sind.

## <a name="prepare-to-move-your-staffhub-teams-to-teams"></a>Vorbereiten des Verschiebens ihrer StaffHub-Teams in Teams

|Schritt |Anleitung  |Ressourcen |
|---------|---------|---------|
|1    |Vorbereiten und Identifizieren von Stakeholdern         |         |
|2     |Überprüfen der Dokumentation zum Übergang von StaffHub zu Teams und Teams Onboarding         |[StaffHub wird zurückgezogen](microsoft-staffhub-to-be-retired.md)<br><br>[Verschieben Ihrer StaffHub-Teams in die Schichten in Teams](move-staffhub-teams-to-shifts-in-teams.md)<br><br>[Erste Schritte mit Microsoft Teams](../../get-started-with-teams-quick-start.md)         |
|3    |Aktivieren von Office 365-Gruppen für Ihre Organisation        |[Office 365-Gruppen und-Teams](../../Office-365-groups.md)      |
|4    |Sicherstellen, dass die Voraussetzungen erfüllt sind         |[Überprüfen, ob Voraussetzungen erfüllt sind](move-staffhub-teams-to-shifts-in-teams.md#check-that-prerequisites-are-met)       |
|5   |Zuweisen von Teams-Lizenzen zu StaffHub-Benutzern in Ihrer Organisation|[Zuweisen von Teams-Lizenzen](move-staffhub-teams-to-shifts-in-teams.md#assign-teams-licenses)<br><br>[Verwalten des Benutzerzugriffs auf Teams](../../user-access.md)      |
|6    |Installieren des StaffHub PowerShell-Moduls        |[Installieren des StaffHub PowerShell-Moduls](install-the-staffhub-powershell-module.md)        |
|7     |Bestimmen der Zeitachse und Identifizieren von StaffHub-Benutzern für den Wechsel zu Teams       |[Ausführen eines Berichts zur Anzeige der aktiven StaffHub-Verwendung](run-report-to-show-staffhub-usage.md) |
|8     |Identifizieren von StaffHub-Benutzern, die nicht über ein Azure AD-Konto verfügen (wird in StaffHub als "inaktiv" angezeigt), und Verknüpfen eines Kontos für Sie     |[Verknüpfen eines Azure AD-Kontos für StaffHub-Teammitglieder, die nicht über ein Konto verfügen](move-staffhub-teams-to-shifts-in-teams.md#link-an-azure-ad-account-for-staffhub-team-members-who-dont-have-one)        |
|9    |Erstellen von Schulungsinhalten für Benutzer, die für Ihre Organisation zugeschnitten sind         |[Vorbereiten eines Benutzer Bereitschaftsplans für Teams](../../upgrade-user-readiness.md)     |
|10    |Kommunizieren von StaffHub-Benutzern über den Übergang zu Schichten in Teams         |         |
|11     |Installieren von Teams-Clients         |[Beziehen von Clients für Teams](../../get-clients.md) |
|12    |Zuweisen der FirstLineWorker-App-Setup Richtlinie zu Benutzern (oder erstellen und Zuweisen einer benutzerdefinierten App-Setup Richtlinie), um die Schicht-APP an Teams-Clients zu anheften  |[Zuweisen der FirstlineWorker-App-Setup Richtlinie zu Benutzern](move-staffhub-teams-to-shifts-in-teams.md#assign-the-firstlineworker-app-setup-policy-to-users)         |
|13     |Schulen von Benutzern beim Verwenden von Schichten und Teams         |[Onboard-Benutzer für Teams](move-staffhub-teams-to-shifts-in-teams.md#onboard-users-to-teams)<br><br>[Hilfedokumentation zu Schichten](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)<br><br>[Teams-Hilfedokumentation](https://support.office.com/teams)<br><br>[Teams-Schulungsvideos](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)       |
|14     |Überprüfen Sie Ihre Liste der StaffHub-Teams, um sicherzustellen, dass alle Benutzer in diesen Teams in Teams verschoben werden. Entfernen Sie Benutzer, die nicht im Zeitplan sein sollten. |         |

## <a name="move-your-organizations-staffhub-teams-to-teams"></a>Verschieben der StaffHub-Teams Ihrer Organisation in Teams

|Schritt |Anleitung |Ressourcen  |
|---------|---------|---------|
|1  |Identifizieren eines Pilot Teams und Verschieben eines Teams          |[Verschieben eines StaffHub-Teams](move-staffhub-teams-to-shifts-in-teams.md#move-a-staffhub-team)          |
|2    |Überprüfen Sie das Pilot Team, und ermitteln Sie etwaige Verschiebungs Probleme. Aktualisieren Sie die Schulungsdokumentation nach Bedarf.         |         |
|3     |Ermitteln weiterer Pilot Teams und Verschieben von fünf bis zehn Teams         |[Verschieben Ihrer StaffHub-Teams](move-staffhub-teams-to-shifts-in-teams.md#go-beyond-your-pilot-and-move-all-staffhub-teams)         |
|4     |Ermitteln der verbleibenden StaffHub-Teams und Verschieben dieser in einem Phasen orientierten Ansatz         |[Verschieben Ihrer StaffHub-Teams](move-staffhub-teams-to-shifts-in-teams.md#go-beyond-your-pilot-and-move-all-staffhub-teams)         |
|5     |Weitere Unterstützung für Schichten und Teams         |         |
|6     |Wenn die Self-Service-Kennwortzurücksetzung aktiviert ist, führen Sie einen Bericht zur Unterstützung von Anmeldeproblemen in Microsoft Teams aus.       |[Ausführen eines Berichts zur Self-Service-Kenn Wort Zurücksetzungs Einrichtung](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-reporting)        |
