---
title: Upgrade der Skype for Business-Hybridbereitstellung auf Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Erfahren Sie, wie Sie ein Upgrade Ihrer Organisation aus einer Skype for Business-Hybridbereitstellung auf Microsoft Teams durchführen.
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
ms.openlocfilehash: 67bb6c10bb8cc5f37d332459d8e147f4f626497d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802345"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a>Upgrade von einer Skype for Business-Hybridbereitstellung auf Teams

![Phasen des Upgradewegs, mit Betonung auf der Bereitstellungs- und Implementierungsphase](media/upgrade-banner-deployment.png "Phasen des Upgradewegs, mit Betonung auf der Bereitstellungs- und Implementierungsphase")

Dieser Artikel ist Teil der Bereitstellungs- und Implementierungsphase Ihres Upgradewegs. Bevor Sie fortfahren, vergewissern Sie sich, dass Sie die folgenden Aktivitäten abgeschlossen haben:

- [Ernennen der Projektbeteiligten](upgrade-enlist-stakeholders.md)
- [Definieren des Projektumfangs](https://aka.ms/SkypetoTeams-Scope)
- [Vertrautmachen mit der Koexistenz und Interoperabilität von Skype for Business und Microsoft Teams](https://aka.ms/SkypeToTeams-Coexist)
- [Auswählen der Upgrade-Strategie](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Vorbereitung Ihrer Umgebung](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [Vorbereitung Ihrer Organisation](https://aka.ms/SkypeToTeams-UserReadiness)
- [Pilot durchgeführt](https://aka.ms/SkypeToTeams-Pilot)

Folgen Sie den Anweisungen in diesem Artikel, wenn Sie Skype for Business oder Microsoft Lync lokal bereitgestellt und in einer Hybridbereitstellung mit Ihrer Microsoft 365- oder Office 365-Organisation konfiguriert haben und Ihre Organisation entweder selektiv – mithilfe mehrerer Koexistenzmodi – oder ein All-In-Upgrade auf Teams durchführen möchte. Für beide Upgradeprozesse müssen Sie Ihre Benutzer zu Skype for Business Online verschieben (sofern sie noch nicht online vorhanden sind) und ihnen dann die geeignete Koexistenz- und Upgrademodus zuweisen.

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a>Schritt 1: Verschieben von Benutzern nach Skype for Business Online

Dieser Schritt gilt für Benutzer, die derzeit lokal behaust sind. Weitere Informationen zum Verschieben dieser Benutzer nach Skype for Business Online finden Sie unter "Verschieben von Benutzern von lokal zu [Skype for Business Online".](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a>Schritt 2: Zuweisen eines Koexistenz- und Upgrademodus

Nachdem Sie Ihre Benutzer nach Skype for Business Online verschoben haben, können Sie ihnen den geeigneten Koexistenzmodus zuweisen, basierend auf dem upgrade-Weg, den Ihre Organisation gewählt hat. Weitere Informationen finden Sie unter ["Festlegen der Koexistenz-](https://aka.ms/SkypeToTeams-SetCoexistence) und Upgradeeinstellungen und [TeamsUpgradePolicy": Verwalten von Migration und Koexistenz.](upgrade-to-teams-on-prem-tools.md)

> [!NOTE]
> Mit Skype for Business Server 2019 und einem zukünftigen kumulativen Update von Skype for Business Server 2015 können Sie Schritt 1 (Verschieben von Benutzern nach Skype for Business Online) und Schritt 2 (Aktualisieren von Benutzern auf Teams) in einem einzigen Schritt ausführen. Weitere Informationen werden nach der 3019-Entkung von Skype for Business Server 2019 bereitgestellt.

## <a name="phone-system-and-teams-upgrade"></a>Upgrade auf Telefonsystem und Teams

Wenn Sie Ihre Skype for Business-Hybridbereitstellung auf das Telefonsystem mit Anrufplänen umgestellt haben und Microsoft Ihr Anbieter des öffentlichen Telefonnetzwerks (PSTN) ist – und vorausgesetzt, Sie haben die Portierung von Telefonnummern abgeschlossen –, erfolgt beim Upgrade Ihrer Benutzer auf Teams automatisch der Übergang eingehender Anrufe über das Festnetz an Teams.

Wenn Anrufpläne nicht verfügbar sind oder Sie Beabsichtigen haben, Ihren vorhandenen PstN-Konnektivitätsanbieter zu verwenden, müssen Sie Ihre Enterprise-Sprachbereitstellung – oder Hybrid-Voice-Bereitstellung, die Ihre vorhandene lokale Bereitstellung oder Cloud Connector Edition verwendet – auf Microsoft Phone System Direct Routing umstiegen. Informationen zum Upgrade Ihrer Benutzer auf Teams finden Sie unter den zusätzlichen Überlegungen zum [direkten Routing des Telefonsystems.](2-envision-make-my-service-decisions-direct-routing.md)
