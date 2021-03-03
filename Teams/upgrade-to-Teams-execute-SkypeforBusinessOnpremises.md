---
title: Upgrade von Skype for Business (lokal) auf Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Erfahren Sie, wie Sie von einer lokalen Skype for Business-Bereitstellung auf Microsoft Teams umstiegen.
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
ms.openlocfilehash: 90542f680c1d3992f5f318bfedad8a12470d282b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820945"
---
# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a>Upgrade von einer lokalen Skype for Business-Bereitstellung auf Teams

![Phasen des Upgradewegs, mit Betonung auf der Bereitstellungs- und Implementierungsphase](media/upgrade-banner-deployment.png "Phasen des Upgradewegs, mit Betonung auf der Bereitstellungs- und Implementierungsphase")

Dieser Artikel ist Teil der Bereitstellungs- und Implementierungsphase Ihres Upgradewegs. Bevor Sie fortfahren, vergewissern Sie sich, dass Sie die folgenden Aktivitäten abgeschlossen haben:

- [Ernennen der Projektbeteiligten](upgrade-enlist-stakeholders.md)
- [Definieren des Projektumfangs](https://aka.ms/SkypetoTeams-Scope)
- [Vertrautmachen mit der Koexistenz und Interoperabilität von Skype for Business und Microsoft Teams](https://aka.ms/SkypeToTeams-Coexist)
- [Auswählen der Upgrade-Strategie](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Vorbereitung Ihrer Umgebung](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [Vorbereitung Ihrer Organisation](https://aka.ms/SkypeToTeams-UserReadiness)
- [Pilot durchgeführt](https://aka.ms/SkypeToTeams-Pilot)

Folgen Sie den Anweisungen in diesem Artikel, wenn Sie Skype for Business oder Microsoft Lync lokal bereitgestellt haben und Ihre Organisation entweder selektiv – mithilfe mehrerer Koexistenzmodi – oder als "All-In" auf Microsoft Teams aktualisieren möchte. 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a>Schritt 1: Bereitstellen von Hybridkonnektivität

Die wichtigste Voraussetzung für das Upgrade Ihrer Benutzer auf Teams ist die Bereitstellung von Hybridkonnektivität.

Weitere Informationen finden Sie unter ["Bereitstellen einer Hybridkonnektivität zwischen Skype for Business Server und Skype for Business Online".](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a>Schritt 2: Implementieren des ausgewählten Upgradeschritts für Ihre Organisation

Nachdem Sie die Hybrideinrichtung abgeschlossen haben, können Sie planen, Ihre Benutzer nach Microsoft 365 oder Office 365 zu verschieben.

Weitere Informationen finden Sie unter:

- [TeamsUpgradePolicy: Verwalten von Migration und Koexistenz](upgrade-to-teams-on-prem-tools.md)

- [Verschieben Sie Benutzer von der lokalen Version zu Skype for Business Online.](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)

## <a name="phone-system-and-teams-upgrade"></a>Upgrade auf Telefonsystem und Teams

Durch den Wechsel von lokalen Telefonsystemen zu Teams können Sie das direkte Telefonsystem-Routing ("Direktes Routing") oder die von Microsoft bereitgestellten Anrufpläne für Microsoft 365 oder Office 365 nutzen.

Wenn Sie keine Anrufpläne verwenden, müssen Sie Ihre Enterprise-Sprachbereitstellung im Rahmen Ihres Upgrades auf Teams auf Telefonsystem-Direct-Routing umstiegen.

Weitere Informationen finden Sie unter [zusätzlichen Überlegungen zum direkten Routing des Telefonsystems.](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing) Wenn Sie Anrufpläne verwenden möchten, lesen Sie bitte unsere Anleitung für die Übertragung Ihrer [Telefonnummern zu Teams.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)