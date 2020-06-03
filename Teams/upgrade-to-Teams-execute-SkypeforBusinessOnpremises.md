---
title: Upgrade von Skype for Business (lokal) auf Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Erfahren Sie, wie Sie Ihre Organisation über eine lokale Skype for Business-Bereitstellung zu Microsoft Teams wechseln.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bea614da76bd61cf7c29b0e8f150f1aac85223a7
ms.sourcegitcommit: 6acede580649588334aeb48130ab2a5d73245723
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2020
ms.locfileid: "44523158"
---
# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a>Upgrade von einer lokalen Bereitstellung von Skype for Business in Teams

![Phasen der Upgrade-Reise, wobei der Schwerpunkt auf der Bereitstellungs-und Implementierungsphase liegt](media/upgrade-banner-deployment.png "Phasen der Upgrade-Reise, wobei der Schwerpunkt auf der Bereitstellungs-und Implementierungsphase liegt")

Dieser Artikel ist Teil der Bereitstellungs-und Implementierungsphase Ihrer Upgrade-Reise. Bevor Sie fortfahren, bestätigen Sie, dass Sie die folgenden Aktivitäten abgeschlossen haben:

- [Ernennen der Projektbeteiligten](upgrade-enlist-stakeholders.md)
- [Definieren des Projektumfangs](https://aka.ms/SkypetoTeams-Scope)
- [Vertrautmachen mit der Koexistenz und Interoperabilität von Skype for Business und Microsoft Teams](https://aka.ms/SkypeToTeams-Coexist)
- [Auswählen der Upgrade-Strategie](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Ihre Umgebung vorbereitet](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [Vorbereiten Ihrer Organisation](https://aka.ms/SkypeToTeams-UserReadiness)
- [Durchgeführt eines Pilotprojekts](https://aka.ms/SkypeToTeams-Pilot)

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

Weitere Informationen finden Sie unter [Weitere Überlegungen zum direkten Routing von Telefonsystemen](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing). Wenn Sie beabsichtigen, Anrufpläne in Office 365 zu verwenden, beziehen Sie sich bitte auf unsere Anleitungen für die über [Tragung ihrer Telefonnummern in Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).