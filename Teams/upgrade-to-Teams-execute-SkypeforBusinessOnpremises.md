---
title: Upgrade von Skype for Business lokal auf Microsoft Teams | Bereitstellen | Lync
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Überlegungen zum Upgrade auf Teams über eine lokale Skype for Business-Bereitstellung.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1b41de8f54eb0e2a09e7e3700b25cba1e5564f0a
ms.sourcegitcommit: a47f0841b9a14ede65171a817ecb7ebc72f209e5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2019
ms.locfileid: "34288188"
---
![Phasen der Upgrade-Reise, wobei der Schwerpunkt auf der Bereitstellungs-und Implementierungsphase liegt] (media/upgrade-banner-deployment.png "Phasen der Upgrade-Reise, wobei der Schwerpunkt auf der Bereitstellungs-und Implementierungsphase liegt")

Dieser Artikel ist Teil der Bereitstellungs-und Implementierungsphase Ihrer Upgrade-Reise. Bevor Sie fortfahren, bestätigen Sie, dass Sie die folgenden Aktivitäten abgeschlossen haben:

- [Ihre Projekt Beteiligten wurden eingetragen](upgrade-enlist-stakeholders.md)
- [Definieren des Projektumfangs](https://aka.ms/SkypetoTeams-Scope)
- [Verständliche Koexistenz und Interoperabilität von Skype for Business und Teams](https://aka.ms/SkypeToTeams-Coexist)
- [Ihre Upgrade-Reise gewählt](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Ihre Umgebung vorbereitet](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [Vorbereiten Ihrer Organisation](https://aka.ms/SkypeToTeams-UserReadiness)
- [Durchgeführt eines Pilotprojekts](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a>Upgrade von einer lokalen Bereitstellung von Skype for Business in Teams

Befolgen Sie die Anleitungen in diesem Artikel, wenn Sie Skype for Business oder Microsoft lync lokal bereitgestellt haben und Ihre Organisation ein Upgrade auf Microsoft Teams entweder selektiv – mithilfe mehrerer Koexistenzmodus – oder All-in durchführen möchte. 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a>Schritt 1: Bereitstellen von Hybrid Konnektivität

Die wichtigste Voraussetzung für das Upgrade Ihrer Benutzer auf Teams ist die Bereitstellung von Hybrid Konnektivität.

Weitere Informationen finden Sie unter [Bereitstellen von Hybrid Konnektivität zwischen Skype for Business Server und Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity) .

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a>Schritt 2: Implementieren der ausgewählten Upgrade-Reise für Ihre Organisation

Nachdem Sie Ihre Hybrid Einrichtung abgeschlossen haben, können Sie planen, Ihre Benutzer nach Office 365 zu verschieben.

Weitere Informationen finden Sie unter:

- [TeamsUpgradePolicy: Verwalten von Migration und Koexistenz](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)

- [Verschieben von Benutzern von lokal in Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)

## <a name="phone-system-and-teams-upgrade"></a>Upgrade für Telefonsysteme und Teams

Wenn Sie von lokalen Telefonsystemen zu Teams wechseln, können Sie die Vorteile des direkten Routings für das Telefon System ("Direktes Routing") oder der von Microsoft bereitgestellten Anrufpläne für Office 365 nutzen.

Wenn Sie in Office 365 keine Anrufpläne verwenden, müssen Sie Ihre Enterprise-VoIP-Bereitstellung als Teil des Upgrades für Teams in das Telefon System Direct Routing umstellen.

Weitere Informationen finden Sie unter [Weitere Überlegungen zum direkten Routing von Telefonsystemen](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing). Wenn Sie beabsichtigen, Anrufpläne in Office 365 zu verwenden, lesen Sie bitte unsere Anleitungen für die über [Tragung ihrer Telefonnummern nach Office 365](https://docs.microsoft.com/microsoftteams/transfer-phone-numbers-to-office-365).