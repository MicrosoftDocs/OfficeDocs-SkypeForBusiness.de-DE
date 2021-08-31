---
title: Upgrade von Skype for Business (lokal) auf Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Erfahren Sie, wie Sie ihre Organisation so Microsoft Teams, dass Skype for Business lokalen Bereitstellung nicht mehr funktioniert.
ms.localizationpriority: medium
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
ms.openlocfilehash: e8d8b104354e442116dd908b686bc5e1d18f22d2
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731154"
---
# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a>Upgrade von einer Skype for Business lokalen Bereitstellung auf Teams

![Phasen des Upgradewegs, mit Betonung auf der Bereitstellungs- und Implementierungsphase.](media/upgrade-banner-deployment.png "Phasen des Upgradewegs, mit Betonung auf der Bereitstellungs- und Implementierungsphase")

Dieser Artikel ist Teil der Phase Bereitstellung und Implementierung Ihres Upgrades. Bevor Sie fortfahren, vergewissern Sie sich, dass Sie die folgenden Aktivitäten abgeschlossen haben:

- [Ernennen der Projektbeteiligten](upgrade-enlist-stakeholders.md)
- [Definieren des Projektumfangs](./upgrade-define-project-scope.md)
- [Vertrautmachen mit der Koexistenz und Interoperabilität von Skype for Business und Microsoft Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Auswählen der Upgrade-Strategie](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Vorbereitet auf Ihre Umgebung](./upgrade-prepare-environment.md)
- [Vorbereitung Ihrer Organisation](./upgrade-prepare-organization.md)
- [Durchgeführtes Pilotprojekt](./pilot-essentials.md)

Folgen Sie den Anleitungen in diesem Artikel, wenn Sie Skype for Business oder Microsoft Lync lokal bereitgestellt haben und Ihre Organisation entweder selektiv – mithilfe mehrerer Koexistenzmodi – ein Upgrade auf Microsoft Teams durchführen möchte. 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a>Schritt 1: Bereitstellen der Hybridkonnektivität

Die wichtigste Voraussetzung für ein Upgrade Ihrer Benutzer auf Teams Bereitstellung von Hybridkonnektivität.

Weitere Informationen finden Sie unter Bereitstellen einer Hybridkonnektivität zwischen [Skype for Business Server und Skype for Business Online.](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a>Schritt 2: Implementieren des ausgewählten Upgradewegs für Ihre Organisation

Nachdem Sie das Hybrid-Setup abgeschlossen haben, können Sie planen, Ihre Benutzer zu einem anderen Microsoft 365 oder Office 365.

Weitere Informationen finden Sie unter:

- [TeamsUpgradePolicy: Verwalten von Migration und Koexistenz.](upgrade-to-teams-on-prem-tools.md)

- [Verschieben sie Benutzer von lokal auf Skype for Business Online.](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)

## <a name="phone-system-and-teams-upgrade"></a>Telefonsystem und Teams Upgrade

Wenn Sie von lokalen Telefonsystemen auf Teams umstiegen, können Sie Telefonsystem Direct Routing ("Direct Routing") oder die von Microsoft bereitgestellten Anrufpläne für Microsoft 365 oder Office 365.

Wenn Sie keine Anrufpläne verwenden, müssen Sie Ihre Enterprise-Sprachbereitstellung im Rahmen Ihres Upgrades auf Telefonsystem Direct-Routing um Teams.

Weitere Informationen finden Sie unter [zusätzliche Überlegungen zur Telefonsystem Direct-Routing.](./direct-routing-landing-page.md) Wenn Sie Anrufpläne verwenden möchten, lesen Sie bitte unseren Leitfaden für die Übertragung Ihrer [Telefonnummern an Teams.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)