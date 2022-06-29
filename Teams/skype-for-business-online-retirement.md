---
title: Einstellung von Skype for Business Online
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Erfahren Sie mehr über den Einstellungsplan für Skype for Business Online und wie Microsoft Kunden bei der Migration zu Teams hilft.
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
ms.openlocfilehash: 13d7032c78a7863b46bb186553b0b67e67f8c626
ms.sourcegitcommit: f2253162a23d0683e7424211da1a0a8760c8a91b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2022
ms.locfileid: "66494492"
---
# <a name="skype-for-business-online-retirement"></a>Einstellung von Skype for Business Online

Am 31. Juli 2021 hat Microsoft Skype for Business Online eingestellt. Diese Einstellung wurde im Juli 2019 angekündigt, um Kunden zwei Jahre im Voraus darüber zu informieren, ihre Upgrades auf Microsoft Teams zu planen. Teams ist die Kern-App für Kommunikation und Zusammenarbeit in Microsoft 365. Da Skype for Business Online eingestellt wird, möchte Microsoft sicherstellen, dass Kunden über die erforderlichen Informationen und Ressourcen verfügen, um ein erfolgreiches Upgrade auf Teams zu planen und durchzuführen.  Der Skype-Verbraucherdienst ist von dieser Einstellung nicht betroffen. Hintergrundinformationen dazu, warum Skype for Business Online eingestellt wurde, finden Sie unter [häufig gestellte Fragen (FAQ): Upgrade von Skype for Business auf Microsoft Teams](FAQ-journey.yml).

Microsoft beginnt am oder nach dem 30. Juni 2022 mit der Außerbetriebnahme der Skype for Business Online-Infrastruktur. Dieser Artikel enthält Anleitungen für Organisationen mit TeamsOnly-Benutzern, die von jeder Version von Skype for Business aktualisiert wurden.


## <a name="organizations-with-on-premises-deployments-of-skype-for-business-server"></a>Organisationen mit lokalen Bereitstellungen von Skype for Business Server

Die Einstellung von Skype for Business Online wirkt sich nicht auf die Unterstützung für lokale Bereitstellungen von Skype for Business Server und Lync Server 2013 aus. Hybridkunden mit einer Mischung aus online und lokal verwalteten Benutzern müssen jedoch alle *Onlinebenutzer* aktualisieren. Allen Onlinebenutzern muss der TeamsOnly-Modus mithilfe von TeamsUpgradePolicy zugewiesen werden. Microsoft stellt unterstützte Upgrades bereit, um das Upgrade der verbleibenden Skype for Business Online-Benutzer auf den TeamsOnly-Modus zu automatisieren. Hybridorganisationen müssen ihre *lokalen* Skype for Business Benutzer aufgrund dieser Einstellung nicht in die Cloud verschieben. Microsoft unterstützt hybride Organisationen vollständig mit einer Mischung aus TeamsOnly-Benutzern und lokalen Skype for Business Benutzern. Kunden mit Hybridbereitstellungen von Skype for Business Server oder Lync Server 2013 sollten die [Einstellung von Skype for Business Online](/skypeforbusiness/hybrid/plan-hybrid-connectivity#implications-of-the-upcoming-retirement-of-skype-for-business-online) überprüfen.

Wenn sie neue Benutzer in Ihrer lokales Active Directory-Umgebung erstellen, wenn diese Benutzer mit Azure AD synchronisiert werden und Sie beabsichtigen, sie für Teams zu lizenzieren, müssen Sie *diese Benutzer vor dem Zuweisen der Lizenz* **zuerst in Ihrer lokalen Skype for Business Bereitstellung aktivieren und sicherstellen, dass die Änderung über Azure AD Connect mit der Cloud synchronisiert wurde**.  Sie können überprüfen, ob die Änderung vollständig mit der Cloud synchronisiert wurde, indem Sie Get-CsOnlineUser verwenden. Die Änderung wurde synchronisiert, wenn der HostingProvider des Benutzers " SRV:" ist.  Es sollte nicht "sipfed.online.lync.com" sein.   

## <a name="what-to-expect-post-retirement"></a>Was sie nach der Pensionierung erwarten können

Es ist nicht mehr möglich, benutzern, die in der Cloud verwaltet werden, einen anderen Modus als TeamsOnly zuzuweisen. Dies bedeutet:

 - Bei der Lizenzierung neuer Benutzer, die nicht in lokalen Skype for Business Server verwaltet werden, wird Benutzern automatisch der TeamsOnly-Modus zugewiesen, unabhängig von der globalen Richtlinie des Mandanten von TeamsUpgradePolicy.
 - In Hybridorganisationen wird Benutzern beim Verschieben von benutzern, die lokal verwaltet werden, automatisch der TeamsOnly-Modus zugewiesen, unabhängig davon, ob die `MoveToTeams` Option in `Move-CsUser`angegeben wurde.
 - Benutzern, die in der Cloud verwaltet werden, kann kein anderer Modus als TeamsOnly zugewiesen werden. Online verwaltete Benutzer verwenden *Skype for Business Server nicht* lokal.

Kunden verfügen möglicherweise über verbleibende Benutzer, die im Skype for Business Online verwaltet werden und denen der TeamsOnly-Modus noch nicht zugewiesen ist. Kunden sollten diesen Benutzern so schnell wie möglich den TeamsOnly-Modus zuweisen. Microsoft stellt unterstützte Upgrades für Skype for Business Onlinebenutzer bereit, die sich nicht im TeamsOnly-Modus befinden. Die unterstützte Upgradeerfahrung hängt davon ab, ob Ihre Organisation eine reine Onlineorganisation oder eine Organisation mit lokalen Skype for Business Benutzern ist. Weitere Informationen finden Sie unter ["Unterstützte Upgrades von Skype for Business Online auf Microsoft Teams](upgrade-assisted.md)".

Nach Abschluss des unterstützten Upgrades befinden sich alle *Onlinebenutzer* im TeamsOnly-Modus. Benutzer im TeamsOnly-Modus empfangen eingehende Chats und Anrufe in Teams und planen auch Besprechungen in Teams. Sie können keine Chats oder Anrufe initiieren oder Besprechungen in Skype for Business Online planen.  TeamsOnly-Benutzer können jedoch an Skype for Business Besprechungen teilnehmen, die sie in Zukunft bereits haben oder empfangen. Schließlich *bleiben alle lokal verwalteten Benutzer lokal und werden nicht zu TeamsOnly gemacht*.

## <a name="actions-to-take-before-june-30-2022"></a>Maßnahmen, die vor dem 30. Juni 2022 zu ergreifen sind
Nachdem Skype for Business Online eingestellt wurde, beginnt Microsoft mit der Außerbetriebnahme der unterstützenden Infrastruktur spätestens am 30. Juni 2022.  Für jede Organisation mit TeamsOnly-Benutzern, die von einer beliebigen Version von Skype for Business aktualisiert wurden, müssen Sie Maßnahmen ergreifen, wenn eine dieser Situationen zutrifft:

- Wenn Sie TeamsOnly-Benutzer haben, die vor dem Upgrade Kontakte in Skype for Business hatten *und* die sich seit dem Upgrade noch nicht bei Teams angemeldet haben.
- Wenn Sie TeamsOnly-Benutzer haben, die noch Skype for Business Onlinebesprechungen haben, die sie organisiert haben, bevor sie auf TeamsOnly aktualisiert wurden.

Wenn eine dieser Situationen für Ihre Organisation zutrifft, müssen Sie bis zum 30. Juni 2022 maßnahmen, wie unten beschrieben:

 - **Skype for Business Onlinekontakte:** Nachdem ein Benutzer auf den TeamsOnly-Modus aktualisiert wurde und sich der Benutzer zum ersten Mal bei Teams anmeldet, werden alle vorhandenen Kontakte im Skype for Business Onlinekonto dieses Benutzers zu Teams migriert. Nachdem Microsoft die Skype for Business Online-Infrastruktur entfernt hat, können Sie keine Kontakte *mehr für Benutzer migrieren, die sich noch nicht bei Teams angemeldet haben.* Um Kontakte von Skype for Business zu Teams zu migrieren, empfiehlt Microsoft allen Benutzern, die zuvor mindestens einmal vor dem 30. Juni 2022 Skype for Business, sich bei Teams anzumelden.

 - **Skype for Business Onlinebesprechungen:** Nachdem eine Organisation auf TeamsOnly aktualisiert wurde, erstellen Benutzer alle neuen Besprechungen als Teams-Besprechungen. In einigen Fällen haben TeamsOnly-Benutzer möglicherweise noch Skype for Business Onlinebesprechungen, die sie zuvor organisiert haben. Derzeit können aktualisierte TeamsOnly-Benutzer und alle eingeladenen Teilnehmer mit ihrem Skype for Business-Client an diesen Skype for Business Onlinebesprechungen teilnehmen. Nachdem Microsoft die Skype for Business Online-Infrastruktur für einen bestimmten TeamsOnly-Benutzer entfernt hat, sind jedoch alle verbleibenden Skype for Business Onlinebesprechungen, die von diesem Benutzer organisiert wurden, nicht mehr vorhanden. Der Organisator und alle Teilnehmer können nicht an diesen Besprechungen teilnehmen. Wenn Benutzer in TeamsOnly-Organisationen noch Skype for Business Onlinebesprechungen haben, die sie organisiert haben, empfiehlt Microsoft, diese Besprechungen als Teams-Besprechungen neu zu planen. Alternativ können Administratoren den [Besprechungsmigrationsdienst](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms#trigger-meeting-migration-manually-via-powershell-cmdlet) verwenden, um diese Besprechungen in Teams-Besprechungen zu konvertieren. Führen Sie diese Aktionen in beiden Fällen bis zum 30. Juni 2022 aus.  


## <a name="how-microsoft-is-helping-customers-upgrade-to-teams"></a>Wie Microsoft Kunden beim Upgrade auf Teams hilft

Es wird dringend empfohlen, das Upgrade von Skype for Business Online auf Teams noch heute zu starten. Nutzen Sie die verfügbaren Ressourcen, um Ihre Teams-Bereitstellung und das Upgrade von Skype for Business zu planen:

- [Teams-Bereitstellungs- und Upgradedokumentation](upgrade-start-here.md) – Kostenlose technische Anleitung für IT-Administratoren.

- [Teams-Upgradeplanungsworkshops](./upgrade-workshops-landing-page.yml) – Kostenlose interaktive Upgradeplanungsworkshops, in denen Sie Anleitungen, bewährte Methoden und Ressourcen erhalten, die Ihnen bei der Planung und Implementierung Ihres Upgrades auf Teams helfen sollen.

- [Unterstützte Upgrades von Skype for Business Online auf Microsoft Teams](upgrade-assisted.md) – Automatisiertes Programm, das Sie beim Upgrade Skype for Business Onlinebenutzer auf Teams unterstützt.

- [FastTrack für Microsoft 365](https://www.microsoft.com/fasttrack/microsoft-365) – Teams-Bereitstellungsunterstützung für qualifizierende Pläne verfügbar.

- [Teams-Liveschulung](./instructor-led-training-teams-landing-page.yml) – Kostenlose Onlineschulungskurse, die Entwickelt wurden, um Ihre Organisation mit Teams in Betrieb zu bringen.

- [Teams-Kreidegespräche](./chalk-talks-landing-page.yml) – Kostenlose Online-Workshops für IT-Experten und Entscheidungsträger, in denen bewährte Methoden für wichtige Szenarien in Teams beschrieben werden.

- [Microsoft-Partner](https://www.microsoft.com/solution-providers/home) – Microsoft-Lösungsanbieter können Ihnen dabei helfen, Teams in vollem Umfang zu nutzen.

- [Microsoft Teams-Blog](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog) – Teams-Neuigkeiten zu neuen Features, Einführungs- und Nutzungsressourcen, Teams-Geräten und Integration in andere Geschäftsanwendungen.

Wenn Sie ein aktueller Skype for Business Online-Kunde sind, beginnen Sie noch heute mit der Planung Ihres Upgrades auf Teams. Wir freuen uns, dass Sie seine leistungsstarken Kommunikations- und Zusammenarbeitsfunktionen erleben können, und wir sind bestrebt, ihnen dabei zu helfen.  Weitere Informationen zur Einstellung von Skype for Business Online finden Sie unter [häufig gestellte Fragen –Upgrade von Skype for Business auf Microsoft Teams](FAQ-journey.yml).





