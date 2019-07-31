---
title: Upgrade auf Microsoft Teams von einer Hybrid-Bereitstellung oder einer lokalen Bereitstellung von Skype for Business – Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 01/09/2019
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Überlegungen zum Upgrade auf Teams von einer Skype for Business-Hybrid-oder lokalen Bereitstellung.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 731a6b30fe2476d180198e88f83e80f24c8e8227
ms.sourcegitcommit: 195a4e1bbab46034408a22d636874c10f797945a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "35934518"
---
![Diagramm zum Upgrade von Fahrten mit Hervorhebung der Bereitstellung und Implementierung] (media/upgrade-banner-deployment.png "Phasen der Upgrade-Reise, wobei der Schwerpunkt auf der Bereitstellungs-und Implementierungsphase liegt")

Dieser Artikel ist Teil der Bereitstellungs-und Implementierungsphase Ihrer Upgrade-Reise. Bevor Sie fortfahren, bestätigen Sie, dass Sie die folgenden Aktivitäten abgeschlossen haben:

-   [Ihre Projekt Beteiligten wurden eingetragen](upgrade-enlist-stakeholders.md)
-   [Definieren des Projektumfangs](https://aka.ms/SkypetoTeams-Scope)
-   [Verständliche Koexistenz und Interoperabilität von Skype for Business und Teams](https://aka.ms/SkypeToTeams-Coexist)
-   [Ihre Upgrade-Reise gewählt](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [Ihre Umgebung vorbereitet](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [Vorbereiten Ihrer Organisation](https://aka.ms/SkypeToTeams-UserReadiness)
-   [Durchgeführt eines Pilotprojekts](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-to-teams-from-a-skype-for-business-hybrid-or-on-premises-deployment"></a>Upgrade auf Teams von einer Skype for Business-Hybrid-oder lokalen Bereitstellung

Befolgen Sie die Anleitungen in diesem Artikel, wenn Sie Skype for Business oder Microsoft lync lokal bereitgestellt haben und Ihre Organisation ein Upgrade auf Teams entweder selektiv – mithilfe mehrerer Koexistenzmodus – oder All-in durchführen möchte. Der erste Schritt besteht darin, eine hybridverbindung mit Ihrem Office 365-Mandanten einzurichten und dann Ihre Benutzer in Skype for Business Online zu verschieben und Ihnen den entsprechenden Koexistenz-und Aktualisierungsmodus zuzuweisen. 

> [!IMPORTANT]
> Skype for Business Online wird am 31. Juli 2021 eingestellt, danach wird es nicht mehr barrierefrei oder unterstützt. Um die Leistung zu maximieren und sicherzustellen, dass Ihre Organisation die richtige Zeit für die Implementierung Ihres Upgrades hat, empfehlen wir Ihnen, Ihre Reise zu Microsoft Teams heute zu beginnen. Beachten Sie, dass ein erfolgreiches Upgrade die technische und Benutzer Bereitschaft ausrichtet, damit Sie die hierin beschriebenen Anleitungen für die Navigation in Ihrer Reise zu Microsoft Teams nutzen können.

## <a name="step-1-deploy-hybrid-connectivity"></a>Schritt 1: Bereitstellen von Hybrid Konnektivität 

Die wichtigste Voraussetzung für das Upgrade Ihrer Benutzer auf Teams ist die Bereitstellung von Hybrid Konnektivität. Hierbei kann es sich um die Bereitstellungneuer externer Verbindungen für Ihre vorhandene Skype for Business-oder lync-Bereitstellung oder einfach um das Konfigurieren einer Hybrid Beziehung mit Ihrem Office 365-Mandanten handelt. 

Weitere Informationen finden Sie unter [Bereitstellen von Hybrid Konnektivität zwischen Skype for Business Server und Skype for Business Online](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity).

## <a name="step-2-move-users-to-skype-for-business-online"></a>Schritt 2: Verschieben von Benutzern in Skype for Business Online 

Nachdem Sie Ihre Hybrid Einrichtung abgeschlossen haben, verschieben Sie die Benutzer in Skype for Business Online. 

Weitere Informationen finden Sie unter [Verschieben von Benutzern von lokal in Skype for Business Online](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online). 

## <a name="step-3-assign-a-coexistence-and-upgrade-mode"></a>Schritt 3: Zuweisen einer Koexistenz und eines Aktualisierungsmodus

Nachdem Sie Ihre Benutzer in Skype for Business Online verschoben haben, können Sie Ihnen den passenden Koexistenzmodus zuweisen, der auf der von Ihrer Organisation ausgewählten Upgrade-Reise basiert. Weitere Informationen finden Sie unter [Festlegen von Koexistenz-und Upgradeeinstellungen](https://aka.ms/SkypeToTeams-SetCoexistence) und [TeamsUpgradePolicy: Verwalten von Migration und Koexistenz](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).

> [!NOTE]
> Mit Skype for Business Server 2019 und einem zukünftigen kumulativen Update von Skype for Business Server 2015 können Sie Schritt 2 (Verschieben von Benutzern in Skype for Business Online) und Schritt 3 (Benutzer auf Teams aktualisieren) in einem einzigen Schritt ausführen. Weitere Informationen werden nach der Veröffentlichung von Skype for Business Server 2019 bereitgestellt.

## <a name="phone-system-and-teams-upgrade"></a>Upgrade für Telefonsysteme und Teams

Wenn Sie Ihre Skype for Business-hybridbereitstellung in das Telefon System mit Anrufplänen umstellen und Microsoft Ihr öffentlich geschaltetes Telefonnetz (PSTN)-Anbieter ist – und davon ausgehend, dass Sie die Portierung von Telefonnummern abgeschlossen haben – aktualisieren Sie Ihre Benutzer auf Teams über gehen automatisch eingehende PSTN-Anrufe an Teams.

Wenn keine Anrufpläne verfügbar sind, müssen Sie Ihre Enterprise-VoIP-Bereitstellung auf das direkte Routing von Microsoft Phone System umstellen. Wenn Sie Ihre Benutzer auf Teams aktualisieren möchten, lesen Sie die [zusätzlichen Überlegungen für das direkte Routing von Telefonsystemen](2-envision-make-my-service-decisions-direct-routing.md).
