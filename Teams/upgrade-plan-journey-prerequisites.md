---
title: Voraussetzungen für Microsoft Teams | Upgrade der Abhängigkeiten
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
audience: admin
description: Verwenden Sie diese Anleitung, um mehr über die Voraussetzungen und die Umgebungs Abhängigkeiten für die Bereitstellung von Teams in Ihrer Organisation zu erfahren.
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
ms.openlocfilehash: ec634105f87c548ed962bdf9f098298f01f1e93e
ms.sourcegitcommit: 5d64e30a1984a4b1d9ff36e2e1721cb4bbf9e450
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/17/2020
ms.locfileid: "42706865"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a>Voraussetzungen und Umgebungs Abhängigkeiten für Teams

![Diagramm zum Upgrade von Fahrten mit Hervorhebung der technischen Bereitschaftsstufe](media/upgrade-banner-tech-readiness.png "Phasen der Upgrade-Reise, wobei der Schwerpunkt auf der technischen Bereitschaftsstufe liegt")

Dieser Artikel ist Bestandteil der Phase „Technische Bereitschaft“ Ihrer Upgrade-Strategie, einer Aktivität, die Sie parallel zur Phase „Benutzerbereitschaft“ durchführen. Bevor Sie fortfahren, bestätigen Sie, dass Sie diese Aktivitäten aus vorherigen Phasen abgeschlossen haben:

- [Ernennen der Projektbeteiligten](upgrade-enlist-stakeholders.md)
- [Definieren des Projektumfangs](https://aka.ms/SkypetoTeams-Scope)
- [Vertrautmachen mit der Koexistenz und Interoperabilität von Skype for Business und Microsoft Teams](https://aka.ms/SkypeToTeams-Coexist)
- [Auswählen der Upgrade-Strategie](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

Teams kombiniert mehrere Office 365-Dienste und ist daher von der korrekten Implementierung und dem Betrieb dieser Dienste abhängig. Zu diesen Diensten gehören – aber nicht ausschließlich – SharePoint Online, Exchange Online und OneDrive for Business.

Obwohl nicht alle Dienste erforderlich sind, wird dringend empfohlen, alle Dienste zu implementieren. Wenn Sie bestimmte Dienste nicht implementieren möchten, wirkt sich dies auf die Funktionalität aus, die Teams Ihrer Organisation anbieten können. Wenn Sie beispielsweise SharePoint Online nicht implementieren müssen, ist es für Teams auf SharePoint Online für bestimmte Funktionen wie Dateifreigabe in Gruppenunterhaltungen angewiesen, sodass die Implementierung dieses Diensts nicht zu einer Verringerung der Funktionalität führt, die über die Client.

In den folgenden Artikeln finden Sie Informationen zu den Voraussetzungen und dazu, wie Teams mit anderen Technologien interagieren:

- Wenn Ihre Organisation keine Office 365-Arbeitsauslastungen bereitgestellt hat, lesen Sie [Erste Schritte mit Office 365 for Business](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).

- Wenn Ihre Organisation keine überprüfte Domäne für Office 365 hinzugefügt oder konfiguriert hat, lesen Sie [Überprüfen Ihrer Office 365-Domäne](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).

- Wenn Ihre Organisation keine Identitäten mit Azure Active Directory synchronisiert hat, lesen Sie [Identitäts Modelle und Authentifizierung in Microsoft Teams](identify-models-authentication.md).

- Wenn Ihre Organisation nicht<sup>1</sup>über Exchange Online verfügt, lesen Sie [verstehen, wie Exchange und Microsoft Teams interagieren](Exchange-Teams-interact.md).

- Wenn Ihre Organisation nicht über SharePoint Online verfügt, lesen Sie Grund [Legendes zur Interaktion von SharePoint Online und OneDrive for Business mit Microsoft Teams](SharePoint-OneDrive-interact.md).

- Hier erfahren Sie [, wie Office 365-Gruppen und Microsoft Teams interagieren](Office-365-groups.md).

- Wenn es sich bei Ihrer Organisation um eine Bildungseinrichtung handelt und Sie ein Kursteilnehmer-Informations System verwenden, [Stellen Sie School Data Sync bereit](https://docs.microsoft.com/schooldatasync) , bevor Sie Microsoft Teams bereitstellen.

Nachdem Sie überprüft haben, dass Ihre Umgebung alle anwendbaren Voraussetzungen erfüllt, [evaluieren Sie Ihre aktuelle Umgebung für Teams](upgrade-plan-journey-evaluate-environment.md).
