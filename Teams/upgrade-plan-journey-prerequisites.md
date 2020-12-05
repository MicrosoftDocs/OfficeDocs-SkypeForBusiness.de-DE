---
title: Voraussetzungen und Umgebungs Abhängigkeiten für das Upgrade auf Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Verwenden Sie diese Anleitung, um sich über die Voraussetzungen und die Umgebungs Abhängigkeiten für die Bereitstellung von Teams in Ihrer Organisation zu informieren.
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
ms.openlocfilehash: bcd3de45954ea500a6be0d325370ab0660604a65
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578278"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a>Voraussetzungen und Umgebungs Abhängigkeiten für Teams

![Diagramm Upgrade-Strategie, mit Betonung der Phase „Technische Bereitschaft“](media/upgrade-banner-tech-readiness.png "Etappen der Upgrade-Tour mit Schwerpunkt auf der Phase „Technische Bereitschaft“")

Dieser Artikel ist Bestandteil der Phase „Technische Bereitschaft“ Ihrer Upgrade-Strategie, einer Aktivität, die Sie parallel zur Phase „Benutzerbereitschaft“ durchführen. Vergewissern Sie sich zunächst, dass diese Aktivitäten aus den vorherigen Phasen abgeschlossen sind:

- [Ernennen der Projektbeteiligten](upgrade-enlist-stakeholders.md)
- [Definieren des Projektumfangs](https://aka.ms/SkypetoTeams-Scope)
- [Vertrautmachen mit der Koexistenz und Interoperabilität von Skype for Business und Microsoft Teams](https://aka.ms/SkypeToTeams-Coexist)
- [Auswählen der Upgrade-Strategie](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

Teams kombiniert mehrere Microsoft 365-und Office 365-Dienste und ist daher von der korrekten Implementierung und dem Betrieb dieser Dienste abhängig. Zu diesen Diensten gehören – aber nicht ausschließlich – SharePoint Online, Exchange Online und OneDrive for Business.

Obwohl nicht alle Dienste erforderlich sind, wird dringend empfohlen, alle Dienste zu implementieren. Wenn Sie bestimmte Dienste nicht implementieren möchten, wirkt sich dies auf die Funktionalität aus, die Teams Ihrer Organisation anbieten können. Wenn Sie beispielsweise SharePoint Online nicht implementieren müssen, ist es für Teams auf SharePoint Online für bestimmte Funktionen wie Dateifreigabe in Gruppenunterhaltungen angewiesen, sodass die Funktionalität, die der Client bietet, nicht durch die Implementierung dieses Diensts verringert wird.

In den folgenden Artikeln finden Sie Informationen zu den Voraussetzungen und dazu, wie Teams mit anderen Technologien interagieren:

- Wenn Ihre Organisation keine Microsoft 365-oder Office 365-Arbeitslasten bereitgestellt hat, lesen Sie [Erste Schritte](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).

- Wenn Ihre Organisation keine verifizierte Domäne für Microsoft 365 oder Office 365 hinzugefügt oder konfiguriert hat, lesen Sie [häufig gestellte Fragen zu Domains](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).

- Wenn Ihre Organisation keine Identitäten mit Azure Active Directory synchronisiert hat, lesen Sie [Identitäts Modelle und Authentifizierung in Microsoft Teams](identify-models-authentication.md).

- Wenn Ihre Organisation nicht über Exchange Online verfügt, lesen Sie [verstehen, wie Exchange und Microsoft Teams interagieren](Exchange-Teams-interact.md).

- Wenn Ihre Organisation nicht über SharePoint Online verfügt, lesen Sie Grund [Legendes zur Interaktion von SharePoint Online und OneDrive for Business mit Microsoft Teams](SharePoint-OneDrive-interact.md).

- So erfahren Sie, wie [Microsoft 365-Gruppen und Microsoft Teams interagieren](Office-365-groups.md).

- Wenn es sich bei Ihrer Organisation um eine Bildungseinrichtung handelt und Sie ein Kursteilnehmer-Informations System verwenden, lesen Sie [Willkommen bei Microsoft School Data Sync](https://docs.microsoft.com/schooldatasync) , bevor Sie Microsoft Teams bereitstellen.

- Wenn Ihre Organisation über PSTN-Anrufoptionen (Public Switched Telephone Network) nachdenkt, lesen Sie [sprach-und PSTN-Konnektivität](cloud-voice-landing-page.md), [welcher Anrufplan für Sie die richtige ist](calling-plan-landing-page.md), und [Direktes Routing für Telefonsysteme](direct-routing-landing-page.md).

- Wenn Sie sicherstellen möchten, dass alle Netzwerkanforderungen erfüllt sind, bevor Sie Teams bereitstellen, lesen Sie [Vorbereiten des Netzwerks Ihrer Organisation für Microsoft Teams](prepare-network.md).

Nachdem Sie überprüft haben, dass Ihre Umgebung alle anwendbaren Voraussetzungen erfüllt, [evaluieren Sie Ihre aktuelle Umgebung für Teams](upgrade-plan-journey-evaluate-environment.md).
