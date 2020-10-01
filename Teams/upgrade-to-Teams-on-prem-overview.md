---
title: Upgrade auf Teams über eine lokale Skype for Business-Bereitstellung – Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/20
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Upgrade von Skype for Business auf Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8030f1504e56fb6bd9aee528e7969c9d66bf8c96
ms.sourcegitcommit: 739ffd5893abf6d181877d1110f9dc8230b3bfd2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328234"
---
# <a name="upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a>Upgrade von Skype for Business auf Teams &mdash; für IT-Administratoren

## <a name="overview"></a>Übersicht

Bei der Aktualisierung von Skype for Business auf Teams benötigen einige Organisationen einen progressiven Rollout, der von den IT-Abteilungen geplant und verwaltet wird. Die Artikel in diesem Abschnitt gelten in erster Linie für IT-Administratoren in Großunternehmen. Diese Organisationen sind in der Regel lokal, können aber auch große Skype for Business Online-Organisationen sein. Bevor Sie diese Artikel lesen, lesen Sie [Erste Schritte mit Ihrem Team-Upgrade](upgrade-start-here.md) und [das Upgrade-Framework](upgrade-framework.md).


In den folgenden Artikeln wird der Upgradeprozess für Ihre Organisation erläutert: 

- [Upgrade-Methoden](upgrade-to-teams-on-prem-upgrade-methods.md)
- [Tools zum Verwalten des Upgrades](upgrade-to-teams-on-prem-tools.md)
- [Weitere Überlegungen für Organisationen mit Skype for Business lokal](upgrade-to-teams-on-prem-considerations.md)
- [Implementieren des Upgrades](upgrade-to-teams-on-prem-implement.md)
- [Überlegungen zum Public Switched Telephone Network (PSTN)](upgrade-to-teams-on-prem-pstn-considerations.md)

Darüber hinaus werden in den folgenden Artikeln wichtige Upgrade-Konzepte und Koexistenz-Verhaltensweisen beschrieben:

- [Koexistenz von Teams und Skype for Business](upgrade-to-teams-on-prem-coexistence.md)
- [Koexistenzmodus – Referenz](migration-interop-guidance-for-teams-with-skype.md)
- [Führt Kundenerfahrung und Konformität mit Koexistenzmodi zusammen](teams-client-experience-and-conformance-to-coexistence-modes.md)

>[!NOTE]
>In diesen Artikeln werden die Begriffe Skype for Business Online, Skype for Business Server lokal und Skype for Business verwendet. Der letzte Ausdruck bezieht sich auf sowohl online als auch lokale Versionen.

Bevor Sie beginnen, sollten Sie beachten, dass ein Benutzer, der in Teams migriert wurde, keinen Skype for Business-Client mehr verwendet, außer an einer in Skype for Business gehosteten Besprechung teilzunehmen.  Alle eingehenden Chats und Anrufe landen im Team-Client des Benutzers, unabhängig davon, ob der Absender Teams oder Skype for Business verwendet. Alle neuen Besprechungen, die vom migrierten Benutzer organisiert werden, werden als Teams-Besprechungen geplant. Wenn der Benutzer versucht, den Skype for Business-Client zu verwenden, wird das Initiieren von Chats und anrufen blockiert.  Allerdings kann der Benutzer den Skype for Business-Client weiterhin verwenden, um an Skype for Business-Besprechungen teilzunehmen, zu denen er eingeladen wurde. (Ältere Skype for Business-Clients, die vor 2017 ausgeliefert wurden, Ehren TeamsUpgradePolicy nicht. Stellen Sie sicher, dass Sie den neuesten Skype for Business-Client verwenden.)
 
Sie verwalten den Übergang des Benutzers zu Teams mithilfe des Konzepts des [Modus](migration-interop-guidance-for-teams-with-skype.md), bei dem es sich um eine Eigenschaft von [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)handelt. Ein Benutzer, der wie oben beschrieben zu Teams migriert wurde, befindet sich im Modus "TeamsOnly".  Für eine Organisation, die zu Teams migriert, besteht das ultimative Ziel darin, alle Benutzer in den TeamsOnly-Modus zu verschieben.

>[!NOTE]
>Benutzer, die über ein lokales Skype for Business-Konto verfügen, können nicht TeamsOnly werden. Obwohl diese Benutzer [Teams im Modus "Inseln" verwenden](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)können, bietet dies nicht den vollständigen Satz der Teamfunktionen, die im TeamsOnly-Modus zur Verfügung stehen. Damit diese Benutzer TeamsOnly werden, müssen Sie `Move-CsUser` in den lokalen Skype for Business Server-Tools in die Cloud verschoben werden.

Okay. Fangen wir an.  Der erste Schritt besteht darin [, die für Sie verfügbaren Aktualisierungsmethoden zu](upgrade-to-teams-on-prem-upgrade-methods.md)verstehen.







   

## <a name="related-links"></a>Verwandte Links

[Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](migration-interop-guidance-for-teams-with-skype.md) 

[Konfigurieren der Hybrid Konnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Verschieben von Benutzern zwischen lokalen Bereitstellungen und der Cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Festlegen Ihrer Einstellungen für Koexistenz und Upgrades](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Verwenden des Besprechungs Migrations Diensts (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

