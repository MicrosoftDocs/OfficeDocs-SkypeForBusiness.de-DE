---
title: Upgrade Skype for Business hybride Bereitstellung auf Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Erfahren Sie, wie Sie Ein Upgrade Ihrer Organisation Microsoft Teams einer Skype for Business Hybridbereitstellung durchführen.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 97725e7a9790f47f9789366567981f0167fdd806
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104021"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a>Upgrade von einer Skype for Business Hybridbereitstellung auf Teams

![Phasen des Upgradewegs, mit Betonung auf der Bereitstellungs- und Implementierungsphase](media/upgrade-banner-deployment.png "Phasen des Upgradewegs, mit Betonung auf der Bereitstellungs- und Implementierungsphase")

Dieser Artikel ist Teil der Phase Bereitstellung und Implementierung Ihres Upgrades. Bevor Sie fortfahren, vergewissern Sie sich, dass Sie die folgenden Aktivitäten abgeschlossen haben:

- [Ernennen der Projektbeteiligten](upgrade-enlist-stakeholders.md)
- [Definieren des Projektumfangs](./upgrade-define-project-scope.md)
- [Vertrautmachen mit der Koexistenz und Interoperabilität von Skype for Business und Microsoft Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Auswählen der Upgrade-Strategie](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Vorbereitet auf Ihre Umgebung](./upgrade-prepare-environment.md)
- [Vorbereitung Ihrer Organisation](./upgrade-prepare-organization.md)
- [Durchgeführtes Pilotprojekt](./pilot-essentials.md)

Folgen Sie den Anweisungen in diesem Artikel, wenn Sie Skype for Business oder Microsoft Lync lokal bereitgestellt und in einer Hybridbereitstellung mit Ihrer Microsoft 365- oder Office 365-Organisation konfiguriert haben und Ihre Organisation entweder selektiv ein Upgrade auf Teams mithilfe mehrerer Koexistenzmodi oder all-in durchführen möchte. Bei beiden Upgraden müssen Sie Ihre Benutzer nach Skype for Business Online verschieben (wenn sie noch nicht online besend sind), und ihnen dann die geeignete Koexistenz und den geeigneten Upgrademodus zuweisen.

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a>Schritt 1: Verschieben von Benutzern auf Skype for Business Online

Dieser Schritt gilt für Benutzer, die derzeit lokal besend sind. Weitere Informationen zum Verschieben dieser Benutzer nach Skype for Business Online finden Sie unter Verschieben von Benutzern von lokal [auf Skype for Business Online.](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a>Schritt 2: Zuweisen eines Koexistenz- und Upgrademodus

Nachdem Sie die Benutzer nach Skype for Business Online verschoben haben, können Sie ihnen basierend auf dem von Ihrer Organisation ausgewählten Upgradeweg den geeigneten Koexistenzmodus zuweisen. Weitere Informationen finden Sie unter Festlegen der Einstellungen für [Koexistenz](./setting-your-coexistence-and-upgrade-settings.md) und Upgrade und [TeamsUpgradePolicy: Verwalten von Migration und Koexistenz.](upgrade-to-teams-on-prem-tools.md)

> [!NOTE]
> Mit Skype for Business Server 2019 und einem zukünftigen kumulativen Update von Skype for Business Server 2015 können Sie Schritt 1 (Verschieben von Benutzern nach Skype for Business Online) und Schritt 2 (Aktualisieren von Benutzern auf Teams) in einem einzigen Schritt ausführen. Weitere Informationen werden nach Skype for Business Server 2019 bereitgestellt.

## <a name="phone-system-and-teams-upgrade"></a>Telefonsystem und Teams Upgrade

Wenn Sie Ihre Skype for Business-Hybridbereitstellung auf Telefonsystem mit Anrufplänen umgestellt haben und Microsoft Ihr Anbieter für öffentliches Telefonnetz (PSTN) ist – und wenn Sie die Portierung von Telefonnummern abgeschlossen haben –, werden Ihre Benutzer bei einem Upgrade auf Teams automatisch eingehende PSTN-Anrufe an Teams umgestellt.

Wenn Anrufpläne nicht verfügbar sind oder Sie Ihren vorhandenen PSTN-Konnektivitätsanbieter verwenden möchten, müssen Sie Ihre Enterprise-Sprachbereitstellung – oder Hybrid-Sprachbereitstellung, die Ihre vorhandene lokale Bereitstellung oder Cloud Connector Edition verwendet – auf Microsoft-Telefon System Direct Routing um stellen. Informationen zum Upgrade Ihrer Benutzer auf Teams Finden Sie unter den zusätzlichen Überlegungen Telefonsystem [Direct-Routing.](./direct-routing-landing-page.md)