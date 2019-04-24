---
title: Microsoft-Teams, erforderliche Komponenten | Abhängigkeiten Annahme des Upgrades
author: turgayo
ms.author: turgayo
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: turgayo
description: Verwenden Sie diese Anleitung über die erforderlichen Komponenten und der Umwelt Abhängigkeiten Teams in Ihrer Organisation bereitstellen
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 39483e7b3c8e511f2081f907b187d97dbbaf526f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32203342"
---
![Phasen der Upgrade Reise, mit Schwerpunkt auf die Phase technische Bereitschaft] (media/upgrade-banner-tech-readiness.png "Phasen der Upgrade Reise, mit Schwerpunkt auf die Phase technische Bereitschaft")

Dieser Artikel ist Teil technische Bereitschaft Stufe des Ihrem Upgrade Weg, eine Aktivität, die gleichzeitig mit der User Readiness Phase ausgeführt werden. Bevor Sie fortfahren, vergewissern Sie sich, dass Sie diese Aktivitäten aus vorherigen Phasen abgeschlossen haben:

- [Ihre Projektbeteiligten eingetragen](upgrade-enlist-stakeholders.md)
- [Definiert die Projektumfang](https://aka.ms/SkypetoTeams-Scope)
- [Skype-Interoperabilität und Koexistenz für Unternehmen und Teams verstanden](https://aka.ms/SkypeToTeams-Coexist)
- [Ihre Reise Upgrade ausgewählt](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

# <a name="prerequisites-and-environmental-dependencies-for-teams"></a>Erforderliche Komponenten und Umwelt Abhängigkeiten für Teams

Teams kombiniert mehrere Office 365-Dienste und ist daher die richtige Implementierung und Betrieb dieser Dienste abhängig. Zu diesen Diensten gehören, aber nicht beschränkt auf – SharePoint Online, Exchange Online und OneDrive für Unternehmen.

Obwohl nicht alle Dienste erforderlich sind, empfohlen dringend, dass Sie alle implementieren. Wenn Sie nicht bestimmte Dienste zu implementieren, wirkt die Funktionalität sich, dass Teams Ihrem Unternehmen bieten können. Angenommen, obwohl Sie SharePoint Online implementiert haben, Teams beruht auf SharePoint Online für bestimmte Funktionen wie Dateifreigabe in Gruppe Unterhaltungen, damit dieser Dienst nicht implementieren reduziert, die über die Funktionalität der Kunde.

Finden Sie die folgenden Artikel enthalten Informationen zu Voraussetzungen und Interaktion mit anderen Technologien von Teams aus:

- Wenn Ihre Organisation eine beliebige Office 365-Arbeitslasten bereitgestellt noch nicht, finden Sie unter [Erste Schritte mit Office 365 für Unternehmen](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).

- Wenn Ihre Organisation noch nicht hinzugefügt oder konfiguriert eine überprüfte Domäne für Office 365, finden Sie unter [Überprüfen der Office 365-Domäne](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).

- Wenn Ihre Organisation Identitäten für Azure Active Directory synchronisiert noch nicht, finden Sie unter [Modelle Identität und Authentifizierung in Microsoft-Teams](identify-models-authentication.md).

- Wenn Ihre Organisation doesn¹t Exchange Online haben, finden Sie unter [machen Sie sich mit Interaktion von Exchange und Microsoft-Teams](Exchange-Teams-interact.md).

- Wenn Ihre Organisation SharePoint Online vorhanden ist, finden Sie unter [machen Sie sich mit Interaktion von SharePoint Online und OneDrive für Unternehmen mit Microsoft-Teams](SharePoint-OneDrive-interact.md).

- Hier erfahren Sie, wie [Office 365-Gruppen und Microsoft-Teams interagieren](Office-365-groups.md).

- Wenn Ihre Organisation eine Bildungseinrichtung ist, und Sie eine Student Information System verwenden vor der Bereitstellung von Microsoft-Teams [Schule Daten Sync bereitstellen](https://docs.microsoft.com/schooldatasync) .

Nachdem Sie haben überprüft, ob die Umgebung alle erforderlichen Komponenten zutreffende, [Bewerten der aktuellen Umgebung für Teams](upgrade-plan-journey-evaluate-environment.md)erfüllt.