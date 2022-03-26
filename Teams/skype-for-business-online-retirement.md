---
title: Einstellung von Skype for Business Online
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Erfahren Sie mehr über den Ruhestandsplan für Skype for Business Online und wie Microsoft Kunden beim Migrieren zu Teams.
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dcd2148a3f939bd8799b7b3f8b86118359936b7c
ms.sourcegitcommit: d3d3d5a70a69359fc71f072ad6c651556f4eda00
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2022
ms.locfileid: "63783904"
---
# <a name="skype-for-business-online-retirement"></a>Einstellung von Skype for Business Online

Am 31. Juli 2021 wurde Microsoft Skype for Business Online eingestellt. Diese Kündigung wurde im Juli 2019 angekündigt, um Kunden zwei Jahre im Voraus zu informieren, dass sie ihre Upgrades auf Microsoft Teams. Teams ist die zentrale App für Kommunikation und Zusammenarbeit in Microsoft 365. Da Skype for Business Online eingestellt wird, möchte Microsoft sicherstellen, dass Kunden über die erforderlichen Informationen und Ressourcen zum Planen und Ausführen eines erfolgreichen Upgrades für ihre Teams.  Der Skype Verbraucherdienst ist von dieser Rente nicht betroffen. Hintergrundinformationen dazu, warum Skype for Business Online eingestellt wurde, finden Sie unter Häufig gestellte Fragen – Upgrade [von Skype for Business auf Microsoft Teams](FAQ-journey.yml).

Microsoft beginnt mit der außerbetriebnahme Skype for Business Online-Infrastruktur am oder nach dem 30. Juni 2022. Dieser Artikel enthält Anleitungen für Organisationen mit TeamsOnly-Benutzern, die ein Upgrade von einer beliebigen Version von Skype for Business.


## <a name="organizations-with-on-premises-deployments-of-skype-for-business-server"></a>Organisationen mit lokalen Bereitstellungen von Skype for Business Server

Das Ende von Skype for Business Online wirkt sich nicht auf die Unterstützung für lokale Bereitstellungen von Skype for Business Server und Lync Server 2013 aus. Hybridkunden mit einer Mischung aus online und lokal behausten Benutzern müssen jedoch ein Upgrade aller *Onlinebenutzer* durchführen. Allen Onlinebenutzern muss mithilfe von TeamsUpgradePolicy der TeamsOnly-Modus zugewiesen werden. Microsoft stellt Unterstützte Upgrades zur Automatisierung des Upgrades der verbleibenden Skype for Business Online-Benutzer in den TeamsOnly-Modus zur Verfügung. Hybridorganisationen müssen *ihre lokalen Benutzer* Skype for Business diese Rente nicht in die Cloud verschieben. Microsoft unterstützt Hybridorganisationen vollständig mit einer Kombination aus TeamsOnly-Benutzern und lokalen Skype for Business Benutzern. Kunden mit Hybridbereitstellungen von Skype for Business Server oder Lync Server 2013 sollten die Rente [von Skype for Business Online lesen](/skypeforbusiness/hybrid/plan-hybrid-connectivity#implications-of-the-upcoming-retirement-of-skype-for-business-online).

## <a name="what-to-expect-post-retirement"></a>Was Sie nach der Rente erwarten können

Benutzern, die in der Cloud leben, ist es nicht mehr möglich, einen anderen Modus als TeamsOnly zu verwenden. Dies bedeutet:

 - Bei der Lizenzierung neuer Benutzer, die nicht im lokalen Skype for Business Server gespeichert sind, wird Benutzern unabhängig von der globalen Richtlinie des Mandanten von TeamsUpgradePolicy automatisch der TeamsOnly-Modus zugewiesen.
 - In Hybridorganisationen werden Benutzern beim Verschieben von lokal in die Cloud gespeicherten Benutzern automatisch TeamsOnly-Modus `MoveToTeams` zugewiesen, unabhängig davon, ob die Umstellung in angegeben wurde `Move-CsUser`.
 - Benutzern, die in der Cloud gespeichert sind, kann kein anderer Modus als TeamsOnly zugewiesen werden. Online gespeicherte Benutzer *verwenden nicht Skype for Business* lokalen Server.

Kunden haben möglicherweise verbleibende Benutzer, die in Skype for Business Online zu Hause sind und denen der TeamsOnly-Modus noch nicht zugewiesen ist. Kunden sollten diesen Benutzern so schnell wie möglich den TeamsOnly-Modus zuweisen. Microsoft stellt Supportupgrades für Skype for Business Online-Benutzer zur Verfügung, die sich nicht im TeamsOnly-Modus befinden. Die Upgrade-Unterstützung hängt davon ab, ob Es sich bei Ihrer Organisation um eine reine Onlineorganisation oder eine Organisation mit lokalen Benutzern Skype for Business handelt. Weitere Informationen finden Sie unter [Unterstützte Upgrades von Skype for Business Online zu Microsoft Teams](upgrade-assisted.md).

Nach Abschluss des unterstützten Upgrades befinden sich alle *Onlinebenutzer* im "TeamsOnly"-Modus. Benutzer im TeamsOnly-Modus empfangen eingehende Chats und Anrufe in Teams und planen außerdem Besprechungen in Teams. Sie können keine Chats oder Anrufe initiieren oder Besprechungen in Skype for Business Online planen.  TeamsOnly-Benutzer können jedoch an Skype for Business besprechungen teilnehmen, die sie bereits haben oder zukünftig erhalten. Schließlich bleiben alle lokal benutzerdefinierten Benutzer lokal und *werden nicht zu "TeamsOnly" gemacht*.

## <a name="actions-to-take-before-june-30-2022"></a>Maßnahmen vor dem 30. Juni 2022
Nachdem Skype for Business Online eingestellt wurde, beginnt Microsoft mit der Außerbetriebnahme der unterstützenden Infrastruktur nicht vor dem 30. Juni 2022.  Für jede Organisation mit TeamsOnly-Benutzern, die von einer beliebigen Skype for Business-Version aktualisiert wurden, müssen Sie in einer der folgenden Situationen Maßnahmen ergreifen:

- Wenn Sie TeamsOnly-Benutzer haben, die bereits Kontakte in Skype for Business hatten und sich seit dem Upgrade noch  nicht bei Teams angemeldet haben.
- Wenn Sie TeamsOnly-Benutzer haben, die noch über Skype for Business Onlinebesprechungen verfügen, die sie vor dem Upgrade auf TeamsOnly organisiert haben.

Wenn eine dieser Situationen für Ihre Organisation zu gelten hat, müssen Sie bis zum 30. Juni 2022 maßnahmen ergreifen, wie nachstehend beschrieben:

 - **Skype for Business Onlinekontakte:** Nachdem ein Benutzer in den TeamsOnly-Modus aktualisiert wurde und sich der Benutzer zum ersten Mal bei Teams anmeldet, werden alle vorhandenen Kontakte im Skype for Business Online-Konto dieses Benutzers zu Teams. Nachdem Microsoft die Skype for Business Online-Infrastruktur entfernt hat, können Sie kontakte für Benutzer, die sich noch nicht bei ihrem Computer angemeldet haben, nicht *mehr Teams.* Zum Migrieren von Kontakten von Skype for Business zu Teams empfiehlt Microsoft, dass sich alle Benutzer, die zuvor Skype for Business hatten, mindestens einmal vor dem 30. Juni 2022 bei Teams anmelden.

 - **Skype for Business Onlinebesprechungen:** Nach dem Upgrade einer Organisation auf TeamsOnly erstellen Benutzer alle neuen Besprechungen Teams Besprechungen. In einigen Fällen haben TeamsOnly-Benutzer möglicherweise weiterhin Skype for Business Onlinebesprechungen, die sie zuvor organisiert haben. Aktuell können aktualisierte TeamsOnly-Benutzer und alle eingeladenen Teilnehmer über ihren Skype for Business an Skype for Business Onlinebesprechungen teilnehmen. Nachdem Microsoft die Skype for Business Online-Infrastruktur für einen bestimmten TeamsOnly-Benutzer entfernt hat, sind jedoch alle übrigen Skype for Business Online-Besprechungen, die von diesem Benutzer organisiert werden, nicht mehr vorhanden. Der Organisator und alle Teilnehmer können nicht an diesen Besprechungen teilnehmen. Wenn Benutzer in TeamsOnly-Organisationen über verbleibende Skype for Business Onlinebesprechungen verfügen, die sie organisiert haben, empfiehlt Microsoft, dass sie diese Besprechungen als Teams neu anplanen. Alternativ können Administratoren den [Meeting Migration Service](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms#trigger-meeting-migration-manually-via-powershell-cmdlet) verwenden, um diese Besprechungen in Besprechungen Teams konvertieren. Führen Sie in beiden Fällen diese Aktionen bis zum 30. Juni 2022 aus.  


## <a name="how-microsoft-is-helping-customers-upgrade-to-teams"></a>Wie Microsoft Kunden beim Upgrade auf Teams

Wir empfehlen dringend, noch heute mit dem Upgrade von Skype for Business Online auf Teams zu beginnen. Nutzen Sie die verfügbaren Ressourcen, um ihre Bereitstellung Teams und das Upgrade der Ressourcen zu Skype for Business:

- [Teams Dokumentation zu Bereitstellung und Upgrade](upgrade-start-here.md) – Kostenloser technischer Leitfaden für IT-Administratoren.

- [Teams Workshops](./upgrade-workshops-landing-page.yml) für die Upgradeplanung – Kostenlose interaktive Upgradeplanungsworkshops, in denen Sie Anleitungen, bewährte Methoden und Ressourcen erhalten, die Ihnen beim Planen und Implementieren Ihres Upgrades auf ihre Teams.

- [Unterstützte Upgrades von Skype for Business Online auf Microsoft Teams](upgrade-assisted.md) – Automatisiertes Programm, das Sie beim Upgrade von Skype for Business Online-Benutzern auf Teams.

- [FastTrack for Microsoft 365](https://www.microsoft.com/fasttrack/microsoft-365) – Teams Bereitstellungsunterstützung für qualifizierende Pläne verfügbar.

- [Teams Liveschulung](./instructor-led-training-teams-landing-page.yml) – Kostenlose Onlineschulungen, die dafür entwickelt wurden, Ihre Organisation mit Ihren Teams.

- [Teams Kreidegespräche](./chalk-talks-landing-page.yml) – Kostenlose Onlineworkshops für IT-Profis und Entscheidungsträger, die bewährte Methoden für wichtige Szenarien in Teams.

- [Microsoft-Partner](https://www.microsoft.com/solution-providers/home) – Microsoft-Lösungsanbieter können Ihnen dabei helfen, die Vorteile Ihres Teams.

- [Microsoft Teams Blog](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog) – finden Teams Informationen zu neuen Features, Ressourcen zur Einführung und Nutzung, Teams geräte und zur Integration in andere Geschäftsanwendungen.

Wenn Sie ein aktueller Online-Kunde Skype for Business, beginnen Sie mit der Planung Ihres Upgrades auf Teams heute. Wir freuen uns, dass Sie die leistungsfähigen Funktionen für Kommunikation und Zusammenarbeit nutzen können, und wir sind bestrebt, Ihnen beim Weg zu helfen.  Weitere Informationen zur Online-Skype for Business finden Sie unter Häufig gestellte Fragen – Upgrade [von Skype for Business auf Microsoft Teams](FAQ-journey.yml).





