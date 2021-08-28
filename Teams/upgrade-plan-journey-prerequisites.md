---
title: Voraussetzungen und Umgebungsabhängigkeiten für ein Upgrade auf Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Verwenden Sie diese Anleitungen, um mehr über die Voraussetzungen und die Umweltabhängigkeiten für die Bereitstellung von Teams in Ihrer Organisation zu erfahren.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3ade37518da516d219c3c54fd0ce4a280720c373
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58631149"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a>Voraussetzungen und Umgebungsabhängigkeiten für Teams

![Diagramm Upgrade-Strategie, mit Betonung der Phase „Technische Bereitschaft“](media/upgrade-banner-tech-readiness.png "Etappen der Upgrade-Tour mit Schwerpunkt auf der Phase „Technische Bereitschaft“")

Dieser Artikel ist Bestandteil der Phase „Technische Bereitschaft“ Ihrer Upgrade-Strategie, einer Aktivität, die Sie parallel zur Phase „Benutzerbereitschaft“ durchführen. Vergewissern Sie sich zunächst, dass diese Aktivitäten aus den vorherigen Phasen abgeschlossen sind:

- [Ernennen der Projektbeteiligten](upgrade-enlist-stakeholders.md)
- [Definieren des Projektumfangs](./upgrade-define-project-scope.md)
- [Vertrautmachen mit der Koexistenz und Interoperabilität von Skype for Business und Microsoft Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Auswählen der Upgrade-Strategie](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

Teams kombiniert mehrere Microsoft 365- und Office 365-Dienste und hängt daher von der richtigen Implementierung und dem korrekten Betrieb dieser Dienste ab. Diese Dienste umfassen online SharePoint, Exchange Online und OneDrive for Business.

Obwohl nicht alle Dienste erforderlich sind, wird dringend empfohlen, dass Sie alle implementieren. Wenn Sie sich entscheiden, bestimmte Dienste nicht zu implementieren, wirkt sich dies auf die Funktionen aus, Teams Ihre Organisation anbieten können. Wenn Sie beispielsweise SharePoint Online nicht implementieren müssen, ist Teams für bestimmte Funktionen wie die Dateifreigabe in Gruppenunterhaltungen auf SharePoint Teams Online angewiesen, sodass die Funktionalität, die über den Client geboten wird, dadurch reduziert wird, wenn Sie diesen Dienst nicht implementieren.

In den folgenden Artikeln finden Sie Informationen zu den Voraussetzungen und zur Teams Interaktion mit anderen Technologien:

- Wenn Ihre Organisation keine Arbeitslasten oder Arbeitslasten bereitgestellt Microsoft 365 Arbeitslasten Office 365, lesen Sie [Erste Schritte.](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)

- Wenn Ihre Organisation keine überprüfte Domäne für benutzer- oder Microsoft 365 Domäne Office 365, lesen Sie Häufig gestellte Fragen zu [Domänen.](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590)

- Wenn Ihre Organisation keine Identitäten mit anderen Azure Active Directory, lesen Sie Identitätsmodelle und [Authentifizierung in Microsoft Teams.](identify-models-authentication.md)

- Wenn Ihre Organisation Exchange Online nicht implementiert hat, finden Sie weitere Informationen unter [Verstehen, wie Exchange und Microsoft Teams interagieren](Exchange-Teams-interact.md).

- Wenn Ihre Organisation SharePoint Online nicht implementiert hat, finden Sie weitere Informationen unter [Verstehen, wie SharePoint Online und OneDrive for Business mit Microsoft Teams interagieren](SharePoint-OneDrive-interact.md).

- Erfahren Sie, [wie Microsoft 365 gruppen und Microsoft Teams interagieren.](Office-365-groups.md)

- Wenn Ihre Organisation eine Bildungseinrichtung ist und Sie ein Student Information System verwenden, lesen Sie Willkommen bei [Microsoft School Data Sync](/schooldatasync) vor der Bereitstellung Microsoft Teams.

- Wenn Ihre Organisation PstN-Anrufoptionen (Public Switched Telephone Network) in Betracht ziehen, lesen Sie Sprach - Telefonsystem- und [PSTN-Anbindung](cloud-voice-landing-page.md) [,](calling-plan-landing-page.md)Welcher Anrufplan ist für Sie am richtigen , und [Telefonsystem Direct Routing](direct-routing-landing-page.md).

- Informationen, wie Sie sicherstellen können, dass alle Netzwerkanforderungen erfüllt wurden, bevor sie Teams, finden Sie unter Vorbereiten des [Unternehmensnetzwerks für Microsoft Teams.](prepare-network.md)

- Wenn Sie derzeit Skype for Business Online Connector zum Verwalten Ihrer Dienste verwenden, müssen Sie zum Teams PowerShell-Modul wechseln und die vorhandenen PowerShell-Skripts aktualisieren. Weitere Informationen finden Sie Skype for Business Wechseln vom [Onlineconnector zum Teams PowerShell-Modul.](teams-powershell-move-from-sfbo.md)

Nachdem Sie überprüft haben, dass Ihre Umgebung alle zutreffenden Voraussetzungen erfüllt, überprüfen Sie Ihre [aktuelle Umgebung für Teams.](upgrade-plan-journey-evaluate-environment.md)