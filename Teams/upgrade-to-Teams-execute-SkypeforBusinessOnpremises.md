---
title: Upgrade von Skype for Business (lokal) auf Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Erfahren Sie, wie Sie Ihre Organisation von einer Skype for Business lokalen Bereitstellung auf Microsoft Teams umsteigen.
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
ms.openlocfilehash: 7b06134a0fe0f72e8dc9c01b4faa85c67a6063f3
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615441"
---
# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a>Upgrade von einer Skype for Business lokalen Bereitstellung auf Teams

![Phasen der Upgradephase, mit Schwerpunkt auf der Bereitstellungs- und Implementierungsphase.](media/upgrade-banner-deployment.png "Phasen der Upgradephase mit Schwerpunkt auf der Bereitstellungs- und Implementierungsphase")

Dieser Artikel ist Teil der Bereitstellungs- und Implementierungsphase Ihrer Upgrade-Reise. Bevor Sie fortfahren, vergewissern Sie sich, dass Sie die folgenden Aktivitäten abgeschlossen haben:

- [Ernennen der Projektbeteiligten](upgrade-enlist-stakeholders.md)
- [Definieren des Projektumfangs](./upgrade-define-project-scope.md)
- [Vertrautmachen mit der Koexistenz und Interoperabilität von Skype for Business und Microsoft Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Auswählen der Upgrade-Strategie](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Vorbereiten Ihrer Umgebung](./upgrade-prepare-environment.md)
- [Ihre Organisation vorbereitet](./upgrade-prepare-organization.md)
- [Durchführen eines Pilotprojekts](./pilot-essentials.md)

Befolgen Sie die Anleitungen in diesem Artikel, wenn Sie Skype for Business oder Microsoft Lync lokal bereitgestellt haben und Ihre Organisation entweder selektiv – mithilfe mehrerer Koexistenzmodi – oder all-in auf Microsoft Teams upgraden möchte. 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a>Schritt 1: Bereitstellen der Hybridkonnektivität

Die wichtigste Voraussetzung für das Upgrade Ihrer Benutzer auf Teams ist die Bereitstellung der Hybridkonnektivität.

Weitere Informationen finden [Sie unter Bereitstellen der Hybridkonnektivität zwischen Skype for Business Server und Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a>Schritt 2: Implementieren der ausgewählten Upgrade-Reise für Ihre Organisation

Nachdem Sie Ihre Hybrideinrichtung abgeschlossen haben, können Sie planen, Ihre Benutzer nach Microsoft 365 oder Office 365 zu verschieben.

Weitere Informationen finden Sie unter:

- [TeamsUpgradePolicy: Verwalten von Migration und Koexistenz](upgrade-to-teams-on-prem-tools.md).

- [Verschieben von Benutzern aus der lokalen Umgebung in Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).

## <a name="phone-system-and-teams-upgrade"></a>Upgrade von Telefonsystem und Teams

Wenn Sie von lokalen Telefonsystemen zu Teams wechseln, können Sie die Vorteile von Direct Routing für Telefonsysteme ("Direct Routing") oder der von Microsoft bereitgestellten Anrufpläne für Microsoft 365 oder Office 365 nutzen.

Wenn Sie keine Anrufpläne verwenden, müssen Sie Ihre Enterprise-VoIP-Bereitstellung im Rahmen Ihres Upgrades auf Teams auf Direct Routing für Telefonsysteme umstellen.

Weitere Informationen finden Sie [unter zusätzlichen Überlegungen zum Direct Routing des Telefonsystems](./direct-routing-landing-page.md). Wenn Sie beabsichtigen, Anrufpläne zu verwenden, lesen Sie bitte unsere Anleitung für die [Übertragung Ihrer Telefonnummern nach Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).