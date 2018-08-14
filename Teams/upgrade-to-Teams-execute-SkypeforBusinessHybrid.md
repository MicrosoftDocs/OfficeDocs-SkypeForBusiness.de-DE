---
title: Upgrade von einer Skype für Business hybridbereitstellung auf Teams - Microsoft-Teams
author: arachmanGitHub
ms.author: arachman
manager: serdars
ms.date: 07/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Überlegungen zum Upgrade von Teams aus einer Skype für Business hybridbereitstellung.
localization_priority: Priority
ms.custom: Teams-upgrade-guidance
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 314a7f1ef6a74734d99839ea2aab4c23fcd58057
ms.sourcegitcommit: b45077dd1b5d366fa9a30698aa66ed4b13264eee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/25/2018
ms.locfileid: "21148338"
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

# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a>Upgrade von einer Skype für Business hybridbereitstellung auf Teams

Befolgen Sie die Anweisungen in diesem Artikel, wenn Sie Skype für Unternehmen bereitgestellt haben oder Microsoft Lync lokal und in einer hybridbereitstellung mit Ihrem Office 365-Mandanten konfiguriert und möchte, dass Ihre Organisation auf Teams entweder selektiv aktualisieren – durch die Verwendung mehrerer Koexistenz Modi – oder-Ansatz repräsentieren. Für ein Upgrade Weg müssen Sie Ihre Benutzer (Wenn sie bereits online verwaltet werden nicht) zu Skype für Business Online verschieben, und weisen Sie diese der entsprechenden Koexistenz und Upgrade-Modus.

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a>Schritt 1: Migrieren von Benutzern zu Skype für Business Online

Dieser Schritt gilt für Benutzer, die derzeit lokal sind. Weitere Informationen zum Verschieben von Benutzern zu Skype für Business Online finden Sie unter [Verschieben von Benutzern aus lokal - auf Skype für Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a>Schritt 2: Zuweisen einer Koexistenz und Aktualisierungsmodus

Nachdem Sie Ihre Benutzer in Skype für Business Online verschoben haben, können Sie diese Zuordnen des entsprechenden Koexistenzmodus basierend auf der Upgrade Weg, die Ihre Organisation ausgewählt hat. Weitere Informationen finden Sie unter [Festlegen der Koexistenz und Durchführen eines Upgrades Einstellungen](https://aka.ms/SkypeToTeams-SetCoexistence) und [TeamsUpgradePolicy: Verwalten von Migration und Koexistenz](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).

> [!NOTE]
> Mit Skype für Business Server 2019 und einem zukünftigen kumulativen Update von Skype für Business Server 2015 können Sie Schritt 1 (Migrieren von Benutzern zu Skype für Business Online) und Schritt2 (Upgrade Benutzer Teams) in einem einzigen Schritt ausführen können. Weitere Informationen werden nach der Veröffentlichung von Skype für Business Server 2019 bereitgestellt.

## <a name="phone-system-and-teams-upgrade"></a>Upgrade Telefonsystem und Teams

Wenn Sie Ihre Skype für Business hybridbereitstellung zu Telefonsystem mit Aufrufen plant übergebenden und Microsoft Ihren öffentlichen Telefonnetz Netzwerkanbieter (PSTN) – und unter der Annahme, dass Sie das Telefon Nummer Portieren abgeschlossen haben – aktualisieren die Benutzer Teams werden automatisch eingehende PSTN-Aufruf von Teams umzustellen.

Wenn plant aufrufen, ist nicht verfügbar, oder Sie Ihre vorhandenen PSTN-Konnektivität-Dienstanbieter verwenden möchten, müssen Sie für den Übergang Ihrer Enterprise-VoIP-bereitstellungs – oder Hybrid-VoIP-Bereitstellung, die Ihre vorhandenen verwendet lokale Bereitstellung oder Cloud Connector Edition – an Microsoft Telefonsystem direktes Routing. Wenn Ihre Benutzer auf Teams aktualisieren, finden Sie unter die [zusätzliche Überlegungen für das Telefon System direkte Routing](2-envision-make-my-service-decisions-direct-routing.md).
