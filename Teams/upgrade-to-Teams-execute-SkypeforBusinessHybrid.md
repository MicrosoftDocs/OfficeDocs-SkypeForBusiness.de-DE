---
title: Upgrade der Skype for Business-Hybridbereitstellung auf Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Erfahren Sie, wie Sie Ihr Unternehmen über eine Skype for Business-Hybridbereitstellung auf Microsoft Teams aktualisieren.
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
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a>Upgrade von einer Skype for Business-Hybridbereitstellung auf Teams

![Phasen des Upgradewegs mit Schwerpunkt auf der Bereitstellungs- und Implementierungsphase](media/upgrade-banner-deployment.png "Phasen des Upgradewegs mit Schwerpunkt auf der Bereitstellungs- und Implementierungsphase")

Dieser Artikel ist Teil der Bereitstellungs- und Implementierungsphase Ihres Upgradewegs. Bevor Sie fortfahren, vergewissern Sie sich, dass Sie die folgenden Aktivitäten abgeschlossen haben:

- [Ernennen der Projektbeteiligten](upgrade-enlist-stakeholders.md)
- [Definieren des Projektumfangs](./upgrade-define-project-scope.md)
- [Vertrautmachen mit der Koexistenz und Interoperabilität von Skype for Business und Microsoft Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Auswählen der Upgrade-Strategie](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Vorbereiten Ihrer Umgebung](./upgrade-prepare-environment.md)
- [Vorbereiten Ihrer Organisation](./upgrade-prepare-organization.md)
- [Pilot durchgeführt](./pilot-essentials.md)

Befolgen Sie die Anleitungen in diesem Artikel, wenn Sie Skype for Business oder Microsoft Lync lokal bereitgestellt und in einer Hybridbereitstellung mit Ihrer Microsoft 365- oder Office 365-Organisation konfiguriert haben und Ihre Organisation entweder selektiv – mithilfe mehrerer Koexistenzmodi – oder all-in ein Upgrade auf Teams durchführen möchte. Für eine upgrade-Reise müssen Sie Ihre Benutzer nach Skype for Business Online verschieben (wenn sie noch nicht online sind) und ihnen dann die entsprechende Koexistenz- und Upgrademodus zuweisen.

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a>Schritt 1: Verschieben von Benutzern nach Skype for Business Online

Dieser Schritt gilt für Benutzer, die derzeit lokal zu Hause sind. Weitere Informationen zum Verschieben dieser Benutzer zu Skype for Business Online finden Sie unter Verschieben von Benutzern von lokal [zu Skype for Business Online.](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a>Schritt 2: Zuweisen eines Koexistenz- und Upgrademodus

Nachdem Sie Ihre Benutzer nach Skype for Business Online verschoben haben, können Sie ihnen den geeigneten Koexistenzmodus zuweisen, der auf der von Ihrer Organisation ausgewählten Upgradereise basiert. Weitere Informationen finden Sie unter [Festlegen der Einstellungen für Koexistenz](./setting-your-coexistence-and-upgrade-settings.md) und Upgrade und [TeamsUpgradePolicy: Verwalten von Migration und Koexistenz](upgrade-to-teams-on-prem-tools.md).

> [!NOTE]
> Mit Skype for Business Server 2019 und einem zukünftigen kumulativen Update von Skype for Business Server 2015 können Sie Schritt 1 (Verschieben von Benutzern zu Skype for Business Online) und Schritt 2 (Upgrade von Benutzern auf Teams) in einem einzigen Schritt ausführen. Nach der Version von Skype for Business Server 2019 werden weitere Informationen bereitgestellt.

## <a name="phone-system-and-teams-upgrade"></a>Upgrade von Telefonsystem und Teams

Wenn Sie Ihre Skype for Business-Hybridbereitstellung auf Telefonsystem mit Anrufplänen umgestellt haben und Microsoft Ihr Anbieter für öffentliches Telefonnetz (PSTN) ist – und vorausgesetzt, Sie haben die Rufnummernportierung abgeschlossen –, wird ein Upgrade Ihrer Benutzer auf Teams automatisch eingehende PSTN-Anrufe an Teams umschalten.

Wenn Anrufpläne nicht verfügbar sind oder Sie Beabsichtigen haben, Ihren vorhandenen PSTN-Konnektivitätsanbieter zu verwenden, müssen Sie Ihre Enterprise-Sprachbereitstellung – oder hybride Sprachbereitstellung, die Ihre vorhandene lokale Bereitstellung oder Cloud Connector Edition verwendet – auf Microsoft Phone System Direct Routing umstiegen. Informationen zum Upgrade Ihrer Benutzer auf Teams finden Sie in den [zusätzlichen Überlegungen zu Telefonsystem-Direct-Routing.](./direct-routing-landing-page.md)