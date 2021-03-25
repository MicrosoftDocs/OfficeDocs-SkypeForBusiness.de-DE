---
title: Upgrade von Skype for Business (lokal) auf Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Erfahren Sie, wie Sie Ihre Organisation von einer lokalen Skype for Business-Bereitstellung zu Microsoft Teams umstiegen.
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
ms.openlocfilehash: 0585f0ad829f19334d5a970461f1f3248a107e9d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115553"
---
# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a>Upgrade von einer lokalen Skype for Business-Bereitstellung auf Teams

![Phasen des Upgradewegs mit Schwerpunkt auf der Bereitstellungs- und Implementierungsphase](media/upgrade-banner-deployment.png "Phasen des Upgradewegs mit Schwerpunkt auf der Bereitstellungs- und Implementierungsphase")

Dieser Artikel ist Teil der Bereitstellungs- und Implementierungsphase Ihres Upgradewegs. Bevor Sie fortfahren, vergewissern Sie sich, dass Sie die folgenden Aktivitäten abgeschlossen haben:

- [Ernennen der Projektbeteiligten](upgrade-enlist-stakeholders.md)
- [Definieren des Projektumfangs](./upgrade-define-project-scope.md)
- [Vertrautmachen mit der Koexistenz und Interoperabilität von Skype for Business und Microsoft Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Auswählen der Upgrade-Strategie](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Vorbereiten Ihrer Umgebung](./upgrade-prepare-environment.md)
- [Vorbereiten Ihrer Organisation](./upgrade-prepare-organization.md)
- [Pilot durchgeführt](./pilot-essentials.md)

Befolgen Sie die Anleitungen in diesem Artikel, wenn Sie Skype for Business oder Microsoft Lync lokal bereitgestellt haben und Ihre Organisation entweder selektiv – mithilfe mehrerer Koexistenzmodi – oder all-in auf Microsoft Teams aktualisieren möchte. 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a>Schritt 1: Bereitstellen von Hybridkonnektivität

Die wichtigste Voraussetzung für ein Upgrade Ihrer Benutzer auf Teams besteht in der Bereitstellung von Hybridkonnektivität.

Weitere Informationen finden Sie unter [Bereitstellen von Hybridkonnektivität zwischen Skype for Business Server und Skype for Business Online.](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a>Schritt 2: Implementieren des ausgewählten Upgradewegs für Ihre Organisation

Nachdem Sie die Hybrideinrichtung abgeschlossen haben, können Sie planen, Ihre Benutzer nach Microsoft 365 oder Office 365 zu verschieben.

Weitere Informationen finden Sie unter:

- [TeamsUpgradePolicy: Verwalten von Migration und Koexistenz](upgrade-to-teams-on-prem-tools.md).

- [Verschieben sie Benutzer von lokal nach Skype for Business Online.](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)

## <a name="phone-system-and-teams-upgrade"></a>Upgrade von Telefonsystem und Teams

Wenn Sie von lokalen Telefonsystemen zu Teams umstiegen, können Sie das direkte Routing für Telefonsysteme ("Direct Routing") oder die von Microsoft bereitgestellten Anrufpläne für Microsoft 365 oder Office 365 nutzen.

Wenn Sie keine Anrufpläne verwenden, müssen Sie Ihre Enterprise-Sprachbereitstellung im Rahmen Ihres Upgrades auf Teams auf Telefonsystem-Direct-Routing umstiegen.

Weitere Informationen finden Sie unter [zusätzliche Überlegungen zu Telefonsystem-Direct-Routing.](./direct-routing-landing-page.md) Wenn Sie Anrufpläne verwenden möchten, lesen Sie unsere Anleitungen zum Übertragen [Ihrer Telefonnummern an Teams.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)