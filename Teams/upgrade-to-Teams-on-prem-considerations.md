---
title: Upgrade auf Teams über eine lokale Skype for Business-Bereitstellung – Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/2020
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
ms.openlocfilehash: cf034969c2b6ca030eede72ff358a517fafe501f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533592"
---
# <a name="upgrade-considerations-for-organizations-with-skype-for-business-server-on-premises-mdash-for-it-administrators"></a>Upgrade-Überlegungen für Organisationen mit Skype for Business Server lokal &mdash; für IT-Administratoren

In diesem Artikel werden weitere Überlegungen für Organisationen beschrieben, die Skype for Business Server lokal nutzen. Dieser Artikel ist der vierte von mehreren, die Upgrade-Konzepte und Implementierung für IT-Administratoren beschreiben.  

- [Übersicht](upgrade-to-teams-on-prem-overview.md)
- [Upgrade-Methoden](upgrade-to-teams-on-prem-upgrade-methods.md)
- [Tools zum Verwalten des Upgrades](upgrade-to-teams-on-prem-tools.md)
- **Weitere Überlegungen für Organisationen mit Skype for Business lokal** (dieser Artikel)
- [Implementieren des Upgrades](upgrade-to-teams-on-prem-implement.md)
- [Überlegungen zum Public Switched Telephone Network (PSTN)](upgrade-to-teams-on-prem-pstn-considerations.md)

Darüber hinaus werden in den folgenden Artikeln wichtige Upgrade-Konzepte und Koexistenz-Verhaltensweisen beschrieben:

- [Koexistenz von Teams und Skype for Business](upgrade-to-teams-on-prem-coexistence.md)
- [Koexistenzmodus – Referenz](migration-interop-guidance-for-teams-with-skype.md)
- [Führt Kundenerfahrung und Konformität mit Koexistenzmodi zusammen](teams-client-experience-and-conformance-to-coexistence-modes.md)



## <a name="considerations-for-organizations-with-skype-for-business-server-on-premises"></a>Überlegungen für Organisationen mit Skype for Business Server lokal

- Das Einrichten von Skype for Business-Hybriden ist eine Voraussetzung für die Migration in den TeamsOnly-Modus. Obwohl es möglich ist, Teams im Modus "Inseln" ohne Hybrid zu verwenden, kann der Übergang in den TeamsOnly-Modus erst dann erfolgen, wenn der Benutzer von Skype for Business lokal zu Skype for Business Online (mit [Move-CsUser](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)) verschoben wird. Weitere Informationen finden Sie unter [Konfigurieren der Hybrid Konnektivität](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity).

- Wenn Ihre Organisation über Skype for Business Server verfügt und Sie keine Hybrid Konnektivität konfiguriert haben, aber weiterhin Teams verwenden möchten, müssen Sie ein Administratorkonto verwenden, das über eine onmicrosoft.com-Domäne verfügt. 

- Benutzer von Teams, die ein Skype for Business-Konto lokal haben (das heißt, dass Sie mit Move-CsUser noch nicht in die Cloud verschoben wurden), können nicht mit Skype for Business-Benutzern zusammenarbeiten und können auch nicht mit externen Benutzern zusammenarbeiten. Diese Funktion steht nur zur Verfügung, wenn die Benutzer in die Cloud verschoben werden (entweder im Modus "Inseln" oder als TeamsOnly-Benutzer). 

- Wenn Sie über Benutzer mit Skype for Business-Konten lokal verfügen, können Sie den TeamsOnly-Modus auf Mandantenebene nicht zuweisen. Sie müssen zunächst alle Benutzer mit lokalen Skype for Business-Konten in die Cloud verschieben, indem Sie die `Move-CsUser` [Migration in die Cloud](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)mithilfe und dann deaktivieren.  `Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams` funktioniert nicht auf Mandantenebene, wenn ein lyncdiscover-DNS-Eintrag erkannt wird, der auf einen anderen Speicherort als Office 365 verweist.

- Sie müssen sicherstellen, dass Ihre Benutzer mit den korrekten Skype for Business-Attributen richtig in Azure AD synchronisiert sind. Diese Attribute sind alle Präfixe mit "Attribut msRTCSIP-". Wenn Benutzer nicht ordnungsgemäß mit Azure AD synchronisiert werden, können die Verwaltungstools in Microsoft Teams diese Benutzer nicht verwalten. (Sie können beispielsweise keine Teamrichtlinien für lokale Benutzer zuweisen, es sei denn, Sie synchronisieren diese Attribute ordnungsgemäß.) Weitere Informationen finden Sie unter [Konfigurieren von Azure AD Connect für Teams und Skype for Business](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect).

- Wenn Sie einen neuen TeamsOnly-oder Skype for Business Online-Benutzer in einer Hybrid Organisation erstellen möchten, *müssen Sie zunächst den Benutzer in Skype for Business Server lokal aktivieren*und den Benutzer dann mithilfe von Move-CsUser von lokal in die Cloud verschieben.  Durch das Erstellen des Benutzers im lokalen Bereich wird zunächst sichergestellt, dass andere verbleibende lokale Skype for Business-Benutzer an den neu erstellten Benutzer weiterleiten können. Nachdem alle Benutzer online verschoben wurden, ist es nicht mehr notwendig, Benutzer zunächst lokal zu aktivieren.

- Wenn ein Benutzer von lokal in die Cloud verschoben wird, werden Besprechungen, die von diesem Benutzer organisiert werden, entweder in Skype for Business Online oder in Teams migriert – je nachdem, ob der-MoveToTeams-Schalter angegeben ist.

- Wenn Sie Benachrichtigungen im Skype for Business-Client für lokale Benutzer anzeigen möchten, müssen Sie im lokalen Toolset TeamsUpgradePolicy verwenden. Nur der NotifySfbUsers-Parameter ist für lokale Benutzer relevant.  Lokale Benutzer erhalten Ihren Modus aus den Online Instanzen von TeamsUpgradePolicy. Sehen Sie sich die Notizen in [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps). 

>[!NOTE]
> Alle neuen Mandanten, die nach dem 3. September erstellt wurden, werden als TeamsOnly-Mandanten erstellt, es sei denn 2019, die Organisation verfügt bereits über eine lokale Bereitstellung von Skype for Business Server. Microsoft verwendet DNS-Einträge, um lokale Skype for Business Server-Organisationen zu identifizieren. Wenn Ihre Organisation über lokale Skype for Business-Server ohne öffentliche DNS-Einträge verfügt, müssen Sie den Microsoft-Support anrufen, damit Ihr neuer Mandant heruntergestuft wird. 













## <a name="related-links"></a>Verwandte Links

[Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](migration-interop-guidance-for-teams-with-skype.md) 

[Konfigurieren der Hybrid Konnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Verschieben von Benutzern zwischen lokalen Bereitstellungen und der Cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Festlegen Ihrer Einstellungen für Koexistenz und Upgrades](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Verwenden des Besprechungs Migrations Diensts (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

