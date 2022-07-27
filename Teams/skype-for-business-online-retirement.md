---
title: Einstellung von Skype for Business Online
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Erfahren Sie mehr über den Plan zur Einstellung von Skype for Business Online und darüber, wie Microsoft seinen Kunden bei der Migration zu Microsoft Teams hilft.
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
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2022
ms.locfileid: "66494492"
---
# <a name="skype-for-business-online-retirement"></a>Einstellung von Skype for Business Online

Am 31. Juli 2021 hat Microsoft Skype for Business Online eingestellt. Diese Einstellung wurde im Juli 2019 angekündigt, um Kunden zwei Jahre im Voraus zu informieren und ihnen Zeit zu geben, ihre Upgrades auf Microsoft Teams zu planen. Microsoft Teams ist die Kern-App für Kommunikation und Zusammenarbeit in Microsoft 365. Da Skype for Business Online eingestellt wird, möchte Microsoft sicherstellen, dass Kunden über die erforderlichen Informationen und Ressourcen verfügen, um ein erfolgreiches Upgrade auf Microsoft Teams zu planen und durchzuführen.  Skype für Heimanwender ist von dieser Einstellung nicht betroffen. Hintergrundinformationen dazu, warum Skype for Business Online eingestellt wurde, finden Sie unter [Häufig gestellte Fragen (FAQ): Upgrade von Skype for Business auf Microsoft Teams](FAQ-journey.yml).

Microsoft beginnt am oder nach dem 30. Juni 2022 mit der Außerbetriebnahme der Skype for Business Online-Infrastruktur. Dieser Artikel enthält Anleitungen für Organisationen mit TeamsOnly-Benutzern, die von beliebigen Versionen von Skype for Business aktualisiert wurden.


## <a name="organizations-with-on-premises-deployments-of-skype-for-business-server"></a>Organisationen mit lokalen Bereitstellungen von Skype for Business Server

Die Einstellung von Skype for Business Online wirkt sich nicht auf die Unterstützung für lokale Bereitstellungen von Skype for Business Server und Lync Server 2013 aus. Hybridkunden mit einer Mischung aus online und lokal verwalteten Benutzern müssen jedoch alle *Onlinebenutzer* aktualisieren. Allen Onlinebenutzern muss der TeamsOnly-Modus mithilfe von TeamsUpgradePolicy zugewiesen werden. Microsoft stellt unterstützte Upgrades bereit, um die Automatisierung des Upgrades der verbleibenden Skype for Business Online-Benutzer auf den TeamsOnly-Modus zu unterstützen. Hybridorganisationen brauchen ihre *lokalen* Skype for Business-Benutzer aufgrund dieser Einstellung nicht in die Cloud verschieben. Microsoft bietet hybriden Organisationen mit einer Mischung aus TeamsOnly-Benutzern und lokalen Skype for Business-Benutzern vollständige Unterstützung. Kunden mit Hybridbereitstellungen von Skype for Business Server oder Lync Server 2013 sollten die Informationen zur [Einstellung von Skype for Business Online](/skypeforbusiness/hybrid/plan-hybrid-connectivity#implications-of-the-upcoming-retirement-of-skype-for-business-online) lesen.

Wenn sie neue Benutzer in Ihrer lokales Active Directory-Umgebung erstellen, diese Benutzer mit Azure AD synchronisiert werden und Sie beabsichtigen, sie für Microsoft Teams zu lizenzieren, **müssen Sie diese Benutzer *vor dem Zuweisen der Lizenz* zuerst in Ihrer lokalen Skype for Business-Bereitstellung aktivieren und sicherstellen, dass die Änderung über Azure AD Connect mit der Cloud synchronisiert wurde**.  Mit „Get-CsOnlineUser“ können Sie überprüfen, ob die Änderung vollständig mit der Cloud synchronisiert wurde. Die Änderung wurde synchronisiert, wenn der „HostingProvider“ des Benutzers „SRV:“ ist.  Er sollte nicht „sipfed.online.lync.com“ lauten.   

## <a name="what-to-expect-post-retirement"></a>Was nach der Einstellung zu erwarten ist

Es ist nicht mehr möglich, in der Cloud verwalteten Benutzern einen anderen Modus als „TeamsOnly“ zuzuweisen. Das bedeutet Folgendes:

 - Bei der Lizenzierung neuer Benutzer, die nicht in der lokalen Version von Skype for Business Server verwaltet werden, wird diesen Benutzern automatisch der TeamsOnly-Modus zugewiesen, unabhängig von der globalen Richtlinie des Mandanten von „TeamsUpgradePolicy“.
 - Beim Verschieben von lokal verwalteten Benutzern in Hybridorganisationen in die Cloud wird diesen Benutzern automatisch der TeamsOnly-Modus zugewiesen, unabhängig davon, ob die Option `MoveToTeams` in `Move-CsUser` angegeben wurde.
 - In der Cloud verwalteten Benutzern kann kein anderer Modus als „TeamsOnly“ mehr zugewiesen werden. Online verwaltete Benutzer verwenden Skype for Business Server *nicht* lokal.

Kunden verfügen möglicherweise noch über einzelne Benutzer, die in Skype for Business Online verwaltet werden und denen der TeamsOnly-Modus noch nicht zugewiesen wurde. Kunden sollten diesen Benutzern so schnell wie möglich den TeamsOnly-Modus zuweisen. Microsoft stellt unterstützte Upgrades für Skype for Business Online-Benutzer bereit, die noch nicht den TeamsOnly-Modus verwenden. Die unterstützte Upgradeerfahrung hängt davon ab, ob Ihre Organisation eine reine Onlineorganisation oder eine Organisation mit lokalen Skype for Business-Benutzern ist. Weitere Informationen finden Sie unter [Unterstützte Upgrades von Skype for Business Online auf Microsoft Teams](upgrade-assisted.md).

Nach Abschluss des unterstützten Upgrades befinden sich alle *Onlinebenutzer* im TeamsOnly-Modus. Benutzer im TeamsOnly-Modus empfangen eingehende Chats und Anrufe in Microsoft Teams und planen auch Besprechungen in Microsoft Teams. Sie können keine Chats oder Anrufe in Skype for Business Online starten oder Besprechungen in Skype for Business Online planen.  TeamsOnly-Benutzer können jedoch an Skype for Business- Besprechungen teilnehmen, die bereits stattfinden oder in Zukunft erfolgen. Schließlich *bleiben alle lokal verwalteten Benutzer lokal und werden nicht in den TeamsOnly-Modus gewechselt*.

## <a name="actions-to-take-before-june-30-2022"></a>Maßnahmen, die vor dem 30. Juni 2022 zu ergreifen sind
Nachdem Skype for Business Online nun eingestellt wurde, beginnt Microsoft mit der Außerbetriebnahme der unterstützenden Infrastruktur ab dem 30. Juni 2022.  Alle Organisationen mit TeamsOnly-Benutzern, die von einer beliebigen Version von Skype for Business aktualisiert wurden, müssen Maßnahmen ergreifen, wenn eine der folgenden Situationen zutrifft:

- Sie haben TeamsOnly-Benutzer, die vor dem Upgrade Kontakte in Skype for Business hatten *und* sich seit dem Upgrade noch nicht bei Microsoft Teams angemeldet haben.
- Sie haben TeamsOnly-Benutzer, die noch über Skype for Business Online-Besprechungen verfügen, die vor dem Upgrade auf TeamsOnly organisiert wurden.

Wenn eine dieser Situationen für Ihre Organisation zutrifft, müssen Sie bis zum 30. Juni 2022 die unten beschriebenen Maßnahmen ergreifen:

 - **Skype for Business Online-Kontakte:** Wenn sich ein Benutzer nach dem Upgrade auf den TeamsOnly-Modus zum ersten Mal bei Microsoft Teams anmeldet, werden alle vorhandenen Kontakte im Skype for Business Online-Konto dieses Benutzers zu Microsoft Teams migriert. Nachdem Microsoft die Skype for Business Online-Infrastruktur entfernt hat, können Sie *für Benutzer, die sich noch nicht bei Microsoft Teams angemeldet haben*, keine Kontakte mehr migrieren. Um Kontakte von Skype for Business zu Microsoft Teams zu migrieren, empfiehlt Microsoft allen Benutzern, die zuvor Skype for Business verwendet haben, sich mindestens einmal vor dem 30. Juni 2022 bei Microsoft Teams anzumelden.

 - **Skype for Business Online-Besprechungen:** Nachdem eine Organisation auf TeamsOnly aktualisiert wurde, erstellen Benutzer alle neuen Besprechungen als Microsoft Teams-Besprechungen. In einigen Fällen haben TeamsOnly-Benutzer möglicherweise noch Skype for Business Online-Besprechungen, die sie zuvor organisiert haben. Derzeit können aktualisierte TeamsOnly-Benutzer und alle eingeladenen Teilnehmer mit ihrem Skype for Business-Client an diesen Skype for Business Online-Besprechungen teilnehmen. Sobald die Skype for Business Online-Infrastruktur von Microsoft für einen bestimmten TeamsOnly-Benutzer entfernt wurde, werden jedoch alle von diesem Benutzer organisierten verbleibenden Skype for Business Online-Besprechungen entfernt. An diesen Besprechungen können weder der Organisator noch die Teilnehmer teilnehmen. Wenn Benutzer in TeamsOnly-Organisationen noch über Skype for Business Online-Besprechungen verfügen, die sie organisiert haben, empfiehlt Microsoft, diese Besprechungen als Microsoft Teams-Besprechungen neu zu planen. Alternativ können Administratoren den [Besprechungsmigrationsdienst](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms#trigger-meeting-migration-manually-via-powershell-cmdlet) verwenden, um diese Besprechungen in Microsoft Teams-Besprechungen zu konvertieren. Führen Sie diese Aktionen in beiden Fällen bis zum 30. Juni 2022 aus.  


## <a name="how-microsoft-is-helping-customers-upgrade-to-teams"></a>Wie hilft Microsoft seinen Kunden beim Upgrade auf Microsoft Teams?

Es wird dringend empfohlen, das Upgrade von Skype for Business Online auf Microsoft Teams noch heute zu starten. Nutzen Sie die verfügbaren Ressourcen, um Ihre Microsoft Teams-Bereitstellung und das Upgrade von Skype for Business zu planen:

- [Dokumentation zu Microsoft Teams-Bereitstellung und -Upgrade](upgrade-start-here.md) – Kostenlose technische Anleitungen für IT-Administratoren.

- [Microsoft Teams-Upgradeplanungsworkshops](./upgrade-workshops-landing-page.yml) – Kostenlose interaktive Upgradeplanungsworkshops, in denen Sie Anleitungen, bewährte Methoden und Ressourcen erhalten, die Ihnen bei der Planung und Implementierung Ihres Upgrades auf Microsoft Teams helfen.

- [Unterstützte Upgrades von Skype for Business Online auf Microsoft Teams](upgrade-assisted.md) – Automatisiertes Programm, das Sie beim Upgrade von Skype for Business Online-Benutzern auf Microsoft Teams unterstützt.

- [FastTrack für Microsoft 365](https://www.microsoft.com/fasttrack/microsoft-365) – Microsoft Teams-Bereitstellungsunterstützung für qualifizierende Pläne verfügbar.

- [Microsoft Teams-Liveschulung](./instructor-led-training-teams-landing-page.yml) – Kostenlose Onlineschulungskurse, die entwickelt wurden, um Ihre Organisation auf Microsoft Teams vorzubereiten.

- [Microsoft Teams-Chalk Talks](./chalk-talks-landing-page.yml) – Kostenlose Onlineworkshops für IT-Experten und Entscheidungsträger, in denen bewährte Methoden für wichtige Szenarien in Microsoft Teams beschrieben werden.

- [Microsoft-Partner](https://www.microsoft.com/solution-providers/home) – Microsoft-Lösungsanbieter können Ihnen dabei helfen, Microsoft Teams in vollem Umfang zu nutzen.

- [Microsoft Teams-Blog](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog) – Microsoft Teams-Neuigkeiten zu neuen Features, Einführungs- und Nutzungsressourcen, Microsoft Teams-Geräten und Integration in andere Geschäftsanwendungen.

Wenn Sie ein aktueller Skype for Business Online-Kunde sind, beginnen Sie noch heute mit der Planung Ihres Upgrades auf Microsoft Teams. Wir freuen uns darauf, dass Sie die leistungsstarken Funktionen für Kommunikation und Zusammenarbeit kennen lernen, und wir helfen Ihnen dabei.  Weitere Informationen zur Einstellung von Skype for Business Online finden Sie unter [Häufig gestellte Fragen – Upgrade von Skype for Business auf Microsoft Teams](FAQ-journey.yml).





