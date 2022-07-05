---
title: Upgrade Skype for Business Hybridbereitstellung auf Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Erfahren Sie, wie Sie Ihr Unternehmen von einer Skype for Business Hybridbereitstellung auf Microsoft Teams aktualisieren.
ms.localizationpriority: medium
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
ms.openlocfilehash: 4ea8db9f53b891002cf7fbe1f5282051e7aca7ea
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615601"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a>Upgrade von einer Skype for Business Hybridbereitstellung auf Teams

![Phasen der Upgradephase, mit Schwerpunkt auf der Bereitstellungs- und Implementierungsphase.](media/upgrade-banner-deployment.png "Phasen der Upgradephase mit Schwerpunkt auf der Bereitstellungs- und Implementierungsphase")

Dieser Artikel ist Teil der Bereitstellungs- und Implementierungsphase Ihrer Upgrade-Reise. Bevor Sie fortfahren, vergewissern Sie sich, dass Sie die folgenden Aktivitäten abgeschlossen haben:

- [Ernennen der Projektbeteiligten](upgrade-enlist-stakeholders.md)
- [Definieren des Projektumfangs](./upgrade-define-project-scope.md)
- [Vertrautmachen mit der Koexistenz und Interoperabilität von Skype for Business und Microsoft Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Auswählen der Upgrade-Strategie](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Vorbereiten Ihrer Umgebung](./upgrade-prepare-environment.md)
- [Ihre Organisation vorbereitet](./upgrade-prepare-organization.md)
- [Durchführen eines Pilotprojekts](./pilot-essentials.md)

Befolgen Sie die Anleitungen in diesem Artikel, wenn Sie Skype for Business oder Microsoft Lync lokal bereitgestellt und in einer Hybridbereitstellung mit Ihrer Microsoft 365- oder Office 365-Organisation konfiguriert haben und Ihre Organisation entweder selektiv mithilfe mehrerer Koexistenzmodi oder all-in auf Teams upgraden möchte. Bei beiden Upgrades müssen Sie Ihre Benutzer in Skype for Business Online verschieben (sofern sie noch nicht online verwaltet werden) und ihnen dann den entsprechenden Koexistenz- und Upgrademodus zuweisen.

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a>Schritt 1: Verschieben von Benutzern zu Skype for Business Online

Dieser Schritt gilt für Benutzer, die derzeit lokal verwaltet werden. Weitere Informationen zum Verschieben dieser Benutzer nach Skype for Business Online finden [Sie unter "Verschieben von Benutzern von lokal nach Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)".

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a>Schritt 2: Zuweisen eines Koexistenz- und Upgrademodus

Nachdem Sie Ihre Benutzer zu Skype for Business Online verschoben haben, können Sie ihnen basierend auf der von Ihrer Organisation ausgewählten Upgrade-Reise den entsprechenden Koexistenzmodus zuweisen. Weitere Informationen finden Sie unter [Festlegen ihrer Koexistenz- und Upgradeeinstellungen](./setting-your-coexistence-and-upgrade-settings.md) und [TeamsUpgradePolicy: Verwalten von Migration und Koexistenz](upgrade-to-teams-on-prem-tools.md).

> [!NOTE]
> Mit Skype for Business Server 2019 und einem zukünftigen kumulativen Update von Skype for Business Server 2015 können Sie Schritt 1 (Verschieben von Benutzern zu Skype for Business Online) und Schritt 2 (Upgrade von Benutzern auf Teams) in einem einzigen Schritt ausführen. Weitere Informationen werden nach der Veröffentlichung Skype for Business Server 2019 bereitgestellt.

## <a name="phone-system-and-teams-upgrade"></a>Upgrade von Telefonsystem und Teams

Wenn Sie Ihre Skype for Business Hybridbereitstellung auf das Telefonsystem mit Anrufplänen umstellen und Microsoft Ihr PSTN-Anbieter (Public Switched Telephone Network) ist – und davon ausgegangen wird, dass Sie die Portierung der Telefonnummer abgeschlossen haben –, wird durch das Upgrade Ihrer Benutzer auf Teams automatisch eingehende PSTN-Anrufe zu Teams übertragen.

Wenn Anrufpläne nicht verfügbar sind oder Sie Ihren vorhandenen PSTN-Konnektivitätsanbieter verwenden möchten, müssen Sie Ihre Enterprise-VoIP-Bereitstellung oder hybride VoIP-Bereitstellung, die Ihre vorhandene lokale Bereitstellung oder Cloud Connector Edition verwendet, auf Microsoft Phone System Direct Routing umstellen. Informationen zum Upgrade Ihrer Benutzer auf Teams finden Sie [in den zusätzlichen Überlegungen zum Direct Routing des Telefonsystems](./direct-routing-landing-page.md).