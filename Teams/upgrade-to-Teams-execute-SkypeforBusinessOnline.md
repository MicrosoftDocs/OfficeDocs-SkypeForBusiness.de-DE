---
title: Aktualisieren von Skype für Unternehmen Online auf Teams - Microsoft-Teams
author: arachmanGitHub
ms.author: arachman
manager: serdars
ms.date: 07/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Überlegungen für das Upgrade auf Teams von Skype für Business Online
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 50c595643e9c6a1805c44676cfa38fd04beb11bb
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883007"
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

Durchführen eines Upgrades auf Teams erfolgt durch Zuweisen von den TeamsOnly Modus der TeamsUpgradePolicy, die mithilfe von Microsoft-Teams & Skype für Business Admin Center oder einen Skype für Business remote Windows Powershell-Sitzung durchgeführt werden kann.

Weitere Informationen finden Sie unter [Festlegen der Koexistenz und Durchführen eines Upgrades Einstellungen](https://aka.ms/SkypeToTeams-SetCoexistence) und [TeamsUpgradePolicy: Verwalten von Migration und Koexistenz](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).

## <a name="phone-system-and-teams-upgrade"></a>Upgrade Telefonsystem und Teams

Wenn Ihre Skype für Business Online-Bereitstellung Telefonsystem mit Aufrufen plant umfasst und Microsoft Ihren öffentlichen Telefonnetz Netzwerkanbieter (PSTN) ist, wird Aktualisieren Ihrer Benutzer auf Teams automatisch eingehende PSTN-Aufruf von Teams umzustellen.

Wenn Ihre Skype für Business Online Bereitstellung Telefonsystem mit Cloud Connector Edition umfasst, finden Sie unter die [zusätzliche Überlegungen für das Telefon System direkte Routing](2-envision-make-my-service-decisions-direct-routing.md).