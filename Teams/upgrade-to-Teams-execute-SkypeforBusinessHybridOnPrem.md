---
title: Durchführen eines Upgrades auf Teams aus einer Skype Business Hybrid oder lokale Bereitstellung - Microsoft-Teams
author: arachmanGitHub
ms.author: arachman
manager: serdars
ms.date: 01/09/2019
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Überlegungen zum Upgrade von Teams aus einer Skype Business Hybrid oder lokale Bereitstellung.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Teams_ITAdmin_JourneyFromSfB
appliesto:
- Microsoft Teams
ms.openlocfilehash: 016165ea54b3a87d4a26f5670964794364e78985
ms.sourcegitcommit: 0458232441d3aed8dd578f41a13078aa379c9b00
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/10/2019
ms.locfileid: "27791712"
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

# <a name="upgrade-to-teams-from-a-skype-for-business-hybrid-or-on-premises-deployment"></a>Durchführen eines Upgrades auf Teams aus einer Skype Business Hybrid oder lokale Bereitstellung

Führen Sie die Anweisungen in diesem Artikel, wenn Sie Skype für Unternehmen bereitgestellt haben oder lokalen Microsoft Lync und Ihre Organisation möchte Teams entweder selektiv upgrade – mithilfe von mehreren Koexistenz Modi – oder-Ansatz repräsentieren. Im erste Schritt wird zum Einrichten von hybridkonnektivität mit Ihrem Office 365-Mandanten, und verschieben Sie Ihre Benutzer zu Skype für Business Online und weisen Sie ihnen die entsprechende Koexistenz und Aktualisierungsmodus. 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a>Schritt 1: Bereitstellen von hybridkonnektivität 

Die wichtige Voraussetzung für die Aktualisierung auf Teams ist zum Bereitstellen von hybridkonnektivität. Dies kann neue externe Konnektivität für Ihre vorhandenen Skype für Business oder Lync-Bereitstellung bereitstellen oder einfach mit Ihrem Office 365-Mandanten Konfigurieren einer hybriden Beziehungs umfassen. 

Weitere Informationen finden Sie unter [Deploy hybridkonnektivität zwischen Skype für Business Server und Skype für Business Online](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity).

## <a name="step-2-move-users-to-skype-for-business-online"></a>Schritt 2: Migrieren von Benutzern zu Skype für Business Online 

Nachdem Sie Ihre Hybriden Setup abgeschlossen haben, verschieben Sie Benutzer in Skype für Business Online. 

Weitere Informationen finden Sie unter [Verschieben von Benutzern aus lokal zu Skype für Business Online](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online). 

## <a name="step-3-assign-a-coexistence-and-upgrade-mode"></a>Schritt 3: Zuweisen einer Koexistenz und Aktualisierungsmodus

Nachdem Sie Ihre Benutzer in Skype für Business Online verschoben haben, können Sie diese Zuordnen des entsprechenden Koexistenzmodus basierend auf der Upgrade Weg, die Ihre Organisation ausgewählt hat. Weitere Informationen finden Sie unter [Festlegen der Koexistenz und Durchführen eines Upgrades Einstellungen](https://aka.ms/SkypeToTeams-SetCoexistence) und [TeamsUpgradePolicy: Verwalten von Migration und Koexistenz](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).

> [!NOTE]
> Mit Skype für Business Server 2019 und einem zukünftigen kumulativen Update von Skype für Business Server 2015 benötigen Sie (Migrieren von Benutzern zu Skype für Business Online) Schritt2 und Schritt 3 (Upgrade Benutzer Teams) in einem einzigen Schritt ausführen können. Weitere Informationen werden nach der Veröffentlichung von Skype für Business Server 2019 bereitgestellt.

## <a name="phone-system-and-teams-upgrade"></a>Upgrade Telefonsystem und Teams

Wenn Sie Ihre Skype für Business hybridbereitstellung zu Telefonsystem mit Aufrufen plant übergebenden und Microsoft Ihren öffentlichen Telefonnetz Netzwerkanbieter (PSTN) – und unter der Annahme, dass Sie das Telefon Nummer Portieren abgeschlossen haben – aktualisieren die Benutzer Teams werden automatisch eingehende PSTN-Aufruf von Teams umzustellen.

Wenn aufrufen Pläne nicht verfügbar ist, müssen Sie Ihre Enterprise-VoIP-Bereitstellung Microsoft Phone System direkten Routing Übergang. Wenn Ihre Benutzer auf Teams aktualisieren, finden Sie unter die [zusätzliche Überlegungen für das Telefon System direkte Routing](2-envision-make-my-service-decisions-direct-routing.md).
