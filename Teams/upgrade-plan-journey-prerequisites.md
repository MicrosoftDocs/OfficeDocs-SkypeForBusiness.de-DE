---
title: Voraussetzungen und Umgebungsabhängigkeiten für das Upgrade auf Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Verwenden Sie diese Anleitung, um mehr über die Voraussetzungen und Die Umgebungsabhängigkeiten für die Bereitstellung von Teams in Ihrer Organisation zu erfahren.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b0ad5716dbbe1925a93f4fbfadca7084e39a9599
ms.sourcegitcommit: e72599d5437773322ae6ef985f804a19101ed84f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/26/2021
ms.locfileid: "50347806"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a>Voraussetzungen und Umgebungsabhängigkeiten für Teams

![Diagramm Upgrade-Strategie, mit Betonung der Phase „Technische Bereitschaft“](media/upgrade-banner-tech-readiness.png "Etappen der Upgrade-Tour mit Schwerpunkt auf der Phase „Technische Bereitschaft“")

Dieser Artikel ist Bestandteil der Phase „Technische Bereitschaft“ Ihrer Upgrade-Strategie, einer Aktivität, die Sie parallel zur Phase „Benutzerbereitschaft“ durchführen. Vergewissern Sie sich zunächst, dass diese Aktivitäten aus den vorherigen Phasen abgeschlossen sind:

- [Ernennen der Projektbeteiligten](upgrade-enlist-stakeholders.md)
- [Definieren des Projektumfangs](https://aka.ms/SkypetoTeams-Scope)
- [Vertrautmachen mit der Koexistenz und Interoperabilität von Skype for Business und Microsoft Teams](https://aka.ms/SkypeToTeams-Coexist)
- [Auswählen der Upgrade-Strategie](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

Teams kombiniert mehrere Microsoft 365- und Office 365-Dienste und ist daher von der richtigen Implementierung und dem richtigen Betrieb dieser Dienste abhängig. Diese Dienste umfassen – aber nicht beschränkt auf – SharePoint Online, Exchange Online und OneDrive for Business.

Obwohl nicht alle Dienste erforderlich sind, wird dringend empfohlen, alle Dienste zu implementieren. Wenn Sie bestimmte Dienste nicht implementieren möchten, wirkt sich dies auf die Funktionen aus, die Teams Ihrer Organisation anbieten kann. Obwohl Sie Beispielsweise SharePoint Online nicht implementieren müssen, ist Teams für bestimmte Funktionen wie die Dateifreigabe in Gruppenunterhaltungen auf SharePoint Online angewiesen, sodass die Funktionalität, die über den Client angeboten wird, durch die Implementierung dieses Diensts reduziert wird.

In den folgenden Artikeln finden Sie Informationen zu den Voraussetzungen und zur Interaktion von Teams mit anderen Technologien:

- Wenn Ihre Organisation keine Microsoft 365- oder Office 365-Workloads bereitgestellt hat, lesen Sie [Erste Schritte.](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)

- Wenn Ihre Organisation keine überprüfte Domäne für Microsoft 365 oder Office 365 hinzugefügt oder konfiguriert hat, lesen Sie Häufig gestellte Fragen [zu Domänen](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).

- Wenn Ihre Organisation keine Identitäten mit Azure Active Directory synchronisiert hat, lesen Sie Identitätsmodelle [und Authentifizierung in Microsoft Teams.](identify-models-authentication.md)

- Wenn Ihre Organisation nicht über Exchange Online verfügen, lesen Sie Verstehen der Interaktion [zwischen Exchange und Microsoft Teams.](Exchange-Teams-interact.md)

- Wenn Ihre Organisation nicht über SharePoint Online verfügen, lesen Sie Verstehen, wie SharePoint Online und [OneDrive for Business mit Microsoft Teams interagieren.](SharePoint-OneDrive-interact.md)

- Hier erfahren Sie, [wie Microsoft 365-Gruppen und Microsoft Teams interagieren.](Office-365-groups.md)

- Wenn Ihre Organisation eine Bildungseinrichtung ist und Sie ein Schülerinformationssystem verwenden, lesen Sie Willkommen bei [Microsoft School Data Sync](https://docs.microsoft.com/schooldatasync) vor der Bereitstellung von Microsoft Teams.

- Wenn Ihre Organisation Optionen für Anrufe im öffentlichen Telefonnetz (PstN) erwägt, lesen Sie [Voice – Telefonsystem-](cloud-voice-landing-page.md)und PSTN-Konnektivität [,](calling-plan-landing-page.md)Welcher Anrufplan für Sie richtig ist , und Direktes [Telefonsystem-Routing](direct-routing-landing-page.md).

- Informationen zum Erfüllen aller Netzwerkanforderungen vor dem Roll out von Teams finden Sie unter Vorbereiten des Netzwerks Ihrer Organisation [für Microsoft Teams](prepare-network.md).

- Wenn Sie derzeit Skype for Business Online Connector zum Verwalten Ihrer Dienste verwenden, müssen Sie zum Teams PowerShell-Modul wechseln und Ihre vorhandenen PowerShell-Skripts aktualisieren. Weitere Informationen finden Sie unter Wechseln von [Skype for Business Online Connector zum Teams PowerShell-Modul.](teams-powershell-move-from-sfbo.md)

Nachdem Sie überprüft haben, ob Ihre Umgebung alle anwendbaren Voraussetzungen erfüllt, werten Sie [Ihre aktuelle Umgebung für Teams aus.](upgrade-plan-journey-evaluate-environment.md)
