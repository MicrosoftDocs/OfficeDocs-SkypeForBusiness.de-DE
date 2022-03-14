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
ms.openlocfilehash: 6c18871756c8081b7013666d98d1599cfec4117f
ms.sourcegitcommit: b635f3765498ae23f535a33fa9ffea5068eecb14
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2022
ms.locfileid: "63463738"
---
# <a name="skype-for-business-online-retirement"></a>Einstellung von Skype for Business Online

Am 31. Juli 2021 wurde Microsoft Skype for Business Online eingestellt. Diese Kündigung wurde im Juli 2019 angekündigt, um Kunden zwei Jahre im Voraus zu informieren, dass sie ihre Upgrades auf Microsoft Teams. Teams ist die zentrale App für Kommunikation und Zusammenarbeit in Microsoft 365. Da Skype for Business Online eingestellt wird, möchte Microsoft sicherstellen, dass Kunden über die erforderlichen Informationen und Ressourcen zum Planen und Ausführen eines erfolgreichen Upgrades für ihre Teams.  Der Skype Verbraucherdienst ist von dieser Rente nicht betroffen.

## <a name="why-is-skype-for-business-online-retiring"></a>Warum wird Skype for Business Online nicht mehr verfügbar?

Seit seiner Einführung ist Skype for Business Online ein wertvolles Tool für Millionen von Menschen auf der ganzen Welt. Durch die Kombination von Chat, Anrufen und Video hat Skype for Business Online neue Möglichkeiten für die Geschäftskommunikation geschaffen. Teams ist das nächste Kapitel in dieser Vision. 

Die Funktionen von Microsoft Teams gehen über die Funktionen von Skype for Business Online hinaus. Fortlaufende Plattformin innovation und entwicklung bedeutet, Teams Benutzer von einer reichhaltigere Leistung, Funktionalität, Flexibilität und Sicherheit profitieren. Durch die Kombination der folgenden Funktionen in einer einzelnen Bearbeitung ermöglicht Teams neue Arbeitsweise:

- Chat
- Video
- Anrufe
- Zusammenarbeit an Dokumenten
- Anwendungsintegration

Teams ist mehr als ein Upgrade für Skype for Business Online. Es ist ein leistungsfähiges Tool, das es Schulen und Organisationen ermöglicht, agiler zu werden und die Effizienz wichtiger Workflows zu verbessern. Weitere Informationen zu den Vorteilen von Teams finden Sie im Whitepaper Forrester: Die gesamten wirtschaftlichen [Auswirkungen™ Microsoft Teams](https://www.microsoft.com/microsoft-365/blog/wp-content/uploads/sites/2/2019/04/Total-Economic-Impact-Microsoft-Teams.pdf?rtc=1).

Weitere Informationen zur Online-Skype for Business finden Sie unter Häufig gestellte Fragen [– Upgrade von Skype for Business auf Microsoft Teams](FAQ-journey.yml).

## <a name="organizations-with-skype-for-business-online"></a>Organisationen mit Skype for Business Online

Microsoft stellt einen unterstützten Upgradeprozess zur Verfügung, damit Organisationen die verbleibenden Skype for Business Online-Benutzer ausschließlich auf Teams verschieben können. Teams ist in den meisten Microsoft 365 Business- und Enterprise-Plänen verfügbar, und vorhandene Investitionen in die Lizenzierung werden auf Teams. Funktionen, bei denen es sich heute in Skype for Business Online um Premium-Arbeitsauslastungen handelt, gelten auch in Teams als Premium-Arbeitsauslastungen. Wenn Sie beispielsweise audio conferencing standalone oder als Teil von E5 mit Skype for Business erworben haben, werden Audiokonferenzen in Teams.

## <a name="organizations-with-on-premises-deployments-of-skype-for-business-server"></a>Organisationen mit lokalen Bereitstellungen von Skype for Business Server

Das Ende von Skype for Business Online wirkt sich nicht auf die Unterstützung für lokale Bereitstellungen von Skype for Business Server und Lync Server 2013 aus. Hybridkunden mit einer Mischung aus online und lokal behausten Benutzern müssen jedoch ein Upgrade aller *Onlinebenutzer* durchführen. Diesen Onlinebenutzern muss mithilfe von TeamsUpgradePolicy Teams Nur-Modus zugewiesen werden. Microsoft stellt Support-Upgrades zur Verfügung, um das Upgrade der verbleibenden Skype for Business Online-Benutzer auf den Teams zu automatisieren. Hybridorganisationen müssen *ihre lokalen Benutzer* Skype for Business diese Rente nicht in die Cloud verschieben. Microsoft unterstützt Hybridorganisationen vollständig mit einer Kombination aus Teams nur Benutzern und lokalen Skype for Business Benutzern. Kunden mit Hybridbereitstellungen von Skype for Business Server oder Lync Server 2013 sollten die Auswirkungen der bevorstehenden Rente von [Skype for Business Online lesen](/skypeforbusiness/hybrid/plan-hybrid-connectivity#implications-of-the-upcoming-retirement-of-skype-for-business-online).

## <a name="what-to-expect-post-retirement"></a>Was Sie nach der Rente erwarten können

Benutzern, die in der Cloud leben, ist es nicht mehr möglich, einen anderen Modus als TeamsOnly zu verwenden. Dies bedeutet:
 - Bei der Lizenzierung neuer Benutzer (mit Ausnahme von Benutzern, die im lokalen Skype for Business Server gespeichert sind) wird Benutzern automatisch der TeamsOnly-Modus zugewiesen, unabhängig von der globalen Richtlinie des Mandanten von TeamsUpgradePolicy.
 - In Hybridorganisationen wird Benutzern beim Verschieben von lokal in die Cloud gespeicherten Benutzern automatisch der TeamsOnly-Modus zugewiesen ( `MoveToTeams` d. h., ob der Schalter in angegeben wurde `Move-CsUser`).
 - Benutzern, die in der Cloud gespeichert sind (z. B. wenn  Sie Skype for Business Server nicht lokal verwenden), kann kein anderer Modus als nur Teams zugewiesen werden.

Kunden verfügen möglicherweise über verbleibende Teile ihrer Benutzergesamtheit, die in Skype for Business Online leben und denen noch kein Teams zugewiesen ist.  Kunden sollten diesen Teams den Modus "Nur" so schnell wie möglich zuweisen.  Darüber hinaus stellt Microsoft Supportupgrades für Skype for Business Online-Benutzer zur Verfügung, die sich nicht im Teams Befinden.  Die Upgrade-Unterstützung hängt davon ab, ob Es sich bei Ihrer Organisation um eine reine Onlineorganisation oder eine Organisation mit lokalen Benutzern Skype for Business handelt.  Weitere Informationen finden Sie unter [Unterstützte Upgrades von Skype for Business Online zu Microsoft Teams](upgrade-assisted.md).

Nach Abschluss des unterstützten Upgrades befinden sich alle *Onlinebenutzer* im Teams-Modus. Benutzer im Teams Nur-Modus empfangen eingehende Chats und Anrufe in Teams und planen außerdem Besprechungen in Teams. Sie können keine Chats oder Anrufe initiieren oder Besprechungen in Skype for Business Online planen.  Allerdings können Teams nur Benutzer an besprechungen Skype for Business teilnehmen, die sie bereits haben oder zukünftig erhalten. Schließlich bleiben alle lokal benutzerdefinierten Benutzer lokal und *werden nicht nur Teams gemacht*.


## <a name="how-microsoft-is-helping-customers-upgrade-to-teams"></a>Wie Microsoft Kunden beim Upgrade auf Teams

Wir empfehlen dringend, noch heute mit dem Upgrade von Skype for Business Online auf Teams zu beginnen.

Nutzen Sie die verfügbaren Ressourcen, um ihre Bereitstellung Teams und das Upgrade der Ressourcen zu Skype for Business:

- [Teams Dokumentation zu Bereitstellung und Upgrade](upgrade-start-here.md) – Kostenloser technischer Leitfaden für IT-Administratoren.

- [Teams Workshops](./upgrade-workshops-landing-page.yml) für die Upgradeplanung – Kostenlose interaktive Upgradeplanungsworkshops, in denen Sie Anleitungen, bewährte Methoden und Ressourcen erhalten, die Ihnen beim Planen und Implementieren Ihres Upgrades auf ihre Teams.

- [Unterstützte Upgrades von Skype for Business Online auf Microsoft Teams](upgrade-assisted.md) – Automatisiertes Programm, das Sie beim Upgrade von Skype for Business Online-Benutzern auf Teams.

- [FastTrack for Microsoft 365](https://www.microsoft.com/fasttrack/microsoft-365) – Teams Bereitstellungsunterstützung für qualifizierende Pläne verfügbar.

- [Teams Liveschulung](./instructor-led-training-teams-landing-page.yml) – Kostenlose Onlineschulungen, die dafür entwickelt wurden, Ihre Organisation mit Ihren Teams.

- [Teams Kreidegespräche](./chalk-talks-landing-page.yml) – Kostenlose Onlineworkshops für IT-Profis und Entscheidungsträger, die bewährte Methoden für wichtige Szenarien in Teams.

- [Microsoft-Partner](https://www.microsoft.com/solution-providers/home) – Microsoft-Lösungsanbieter können Ihnen dabei helfen, die Vorteile Ihres Teams.

- [Microsoft Teams Blog](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog) – finden Teams Informationen zu neuen Features, Ressourcen zur Einführung und Nutzung, Teams geräte und zur Integration in andere Geschäftsanwendungen.

Wenn Sie ein aktueller Online-Kunde Skype for Business, beginnen Sie mit der Planung Ihres Upgrades auf Teams heute. Wir freuen uns, dass Sie die leistungsfähigen Funktionen für Kommunikation und Zusammenarbeit nutzen können, und wir sind bestrebt, Ihnen beim Weg zu helfen.




