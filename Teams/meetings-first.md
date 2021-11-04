---
title: Besprechung zuerst – Microsoft Teams
author: cichur
ms.author: v-mahoffman
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: lsomi
description: Erfahren Sie zuerst mehr über Besprechungen, in dem Benutzer ihre Besprechung in Teams erstellen und Skype for Business für Chat, Anrufe und Anwesenheit verwenden können.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2aafa115d6da600df17ac18e4b1af66358efb16b
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60741641"
---
# <a name="meetings-first"></a>Besprechungen zuerst

"Meetings First" ist für Skype for Business Server Organisationen mit lokalen Enterprise-VoIP ausgerichtet und optimiert, die so schnell wie möglich Teams-Besprechungen verwenden möchten. Für diese Organisationen ist "Meetings  First" eine Alternative zum Islands-Modus, der die Besprechungserfahrung Teams priorisiert.

## <a name="what-is-meetings-first"></a>Was ist Besprechungen zuerst?

Meetings First basiert auf dem **Koexistenzmodus SfBWithTeamsCollabAndMeetings.** Besprechungen Zuerst ist kein Produkt oder Feature – es ist eine Konfiguration, die Funktionen und Features von Teams und Skype for Business verwendet, um eine speziell maßgeschneiderte Koexistenzerfahrung zu bieten.

In "Besprechungen zuerst" erstellen benutzer ihre Besprechung in Teams, während sie weiterhin Skype for Business für Chat, Anrufe und Anwesenheit verwenden. Es gibt keine Überschneidung von Modalitäten zwischen Teams und Skype for Business. Chats, Anrufe und Anwesenheitsschalten sind in der Skype for Business und in der Teams. Dies ermöglicht eindeutige "gemeinsame" Szenarien zwischen Skype for Business und Teams, die die Benutzerfreundlichkeit während der Koexistenz verbessern, sowie Interoperabilitätsszenarien mit Teams **Nur** Benutzern.

![Screenshot des Szenarios "Zusammen besser" mit Teams und Skype for Business.](media/meetings-first-meeting-in-meeting.png)

> [!Important]
> Besprechungen Zuerst ist eine bessere Übereinstimmung für Organisationen, die über keine oder Teams Chatbenutzer verfügen. Aktive Teams-Chatbenutzer sollten nicht in den Ersten Modus für Besprechungen wechseln, da sie die Möglichkeit zum Chatten in Teams und zum Zugriff auf ihren Chatverlauf verlieren würden. Diese Benutzer sollten stattdessen  im Islands-Modus und "Meetings First" nur Benutzern gewährt werden, die noch nicht in einem Chat in Teams.

## <a name="who-should-consider-meetings-first"></a>Wer sollten Besprechungen zuerst in Betracht ziehen?

Meetings First wurde für Organisationen entwickelt, die Skype for Business Server mit Enterprise-VoIP verwenden, die ihren Wechsel zu Teams-Besprechungen beschleunigen möchten, insbesondere für Organisationen mit einer starken IT-Disziplin, die einen verwalteten, deterministischen Upgradepfad zu Teams.

Bei komplexen oder großen Organisationen erfolgen Sprachmigrationen in der Regel websiteintern und können sehr lange, potenziell mehrere Jahre dauern, was zu erweiterten Koexistenzszenarien führt. Wenn diese Koexistenz im Islands-Modus ausgeführt wird, haben Benutzer immer die Wahl zwischen zwei Besprechungslösungen (Skype for Business und Teams), die zu verwirrenden oder suboptimalen Situationen führen können.  Im Gegensatz zu Sprachmigrationen können Besprechungsmigrationen im Allgemeinen innerhalb kurzer Zeit im gesamten Unternehmen abgeschlossen werden. Organisationen, die so schnell wie möglich Teams besprechungen wechseln möchten (und ohne auf den Abschluss ihrer Sprachmigration warten zu müssen), sollten Besprechungen zuerst in Betracht ziehen.

Besprechungen Zuerst ist möglicherweise nicht hilfreich für Organisationen, die nicht über Enterprise-VoIP verfügen. Diese Organisationen sollten in der Lage sein, ein Upgrade auf **Teams,** sobald sie in der Lage sind, Besprechungen Teams durchführen. Sie sollten Besprechungen zuerst überspringen.

Darüber hinaus ist "Besprechungs zuerst" für Organisationen nützlich, deren Bereich eine reine Besprechungslösung ist, z. B. wenn eine "nur für Besprechungen" bestimmte Angebotsmappe veröffentlicht wird.

## <a name="capabilities-in-meetings-first"></a>Funktionen in Besprechungen zuerst

Meeting First bringt die folgenden Funktionen zusammen:

- [Bereitstellen Skype for Business Server (lokalen)](./tutorial-audio-conferencing.yml?tutorial-step=3) Benutzer mit [Teams Audiokonferenz.](tutorial-audio-conferencing.yml)
- [Migrationsdienst für Besprechungen:](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)Vom Benutzer organisierte Besprechungen werden in die Cloud migriert und in Teams-Besprechungen konvertiert, wenn der Benutzer zu "Besprechungs zuerst" heraufgestuft wird (erfordert Exchange Online).
- Optimierte Benutzeroberfläche in Teams, zentriert auf Teams Besprechungen und Teams und Kanälen (die optional mithilfe der Richtlinie für [App-Berechtigungen ausgeblendet werden können).](teams-app-permission-policies.md) [Teams private Chats,](teams-client-experience-and-conformance-to-coexistence-modes.md) Anrufe und Selbstanrufe werden in Besprechungen zuerst nicht verfügbar gemacht, sodass der Bereitstellungs- und Einführungsaufwand vollständig auf Besprechungen konzentriert werden kann.
- Superior [Teams Besprechungserfahrung](tutorial-meetings-in-teams.yml).
- "Besser zusammen" zwischen Teams und Skype for Business: 
  - Automatisches Halten: Wenn Sie sich in Teams einer Besprechung in Skype for Business halten, wird die Teams-Besprechung in den Halteraum gestellt und umgekehrt. Dadurch wird verhindert, dass Benutzer ihre privaten Anrufe von den Besprechungsteilnehmern überhören.
    ![Screenshot des Szenarios "Zusammen besser" mit Teams und Skype for Business.](media/meetings-first-better-together-hold.png)
  - Anwesenheitsabgleich: Die Aktivität in Teams wird in der Anwesenheit des Benutzers widerspiegelt. Dies ist die Skype for Business Anwesenheit, da Chats und Anrufe Skype for Business. Insbesondere bei Besprechungen, in denen sich die ersten Benutzer in einer Besprechung Teams, werden ihre Anwesenheits anwesenheitsbesprechungen aktualisiert, um dies zu zeigen. Wenn sie ihren Bildschirm präsentieren, werden ihre Anwesenheitseinstellungen aktualisiert, um "Nicht stören" anzuzeigen (basierend auf ihren Einstellungen in Skype for Business).
  - Abstimmung des HID-Steuerelements auf dem USB-Gerät (auch auf dem Mac verfügbar): Die HID-Steuerelemente werden von Teams in Teams-Besprechungen und unter allen anderen Umständen von Skype for Business berücksichtigt.
  - Sofern nicht anders angegeben, erfordern die Funktionen für "Besseres Windows" derzeit eine aktuelle Version Windows Desktopclients.

## <a name="prerequisites-for-meetings-first"></a>Voraussetzungen für Besprechungen zuerst

Die einzigen schwierigen Anforderungen an Besprechungen Sind die gleichen wie für Teams lokales Active Directory und eine lokale Skype for Business Bereitstellung:

- [Allgemeine Voraussetzungen für Teams](upgrade-plan-journey-prerequisites.md), einschließlich
- [Identität und Authentifizierung in Teams](identify-models-authentication.md) und
- [Konfigurieren Azure Active Directory für Teams und Skype for Business.](/skypeforbusiness/hybrid/configure-azure-ad-connect)

Eine [Skype for Business Hybridtopologie](/skypeforbusiness/hybrid/configure-federation-with-skype-for-business-online) ist nicht erforderlich, wird jedoch empfohlen. Einige Funktionen wie Meetings Migration Service und Interoperabilität sind von dieser Topologie angewiesen.

"Besprechungen zuerst" wird von jeder Version des Skype for Business Server unterstützt (und bekannt dafür, mit dem nicht mehr unterstützten Lync Server zu arbeiten). Es wird von jedem unterstützten Skype for Business-Client unterstützt, für better Together-Funktionen ist jedoch ein neuer Client erforderlich.

Sobald diese Anforderungen erfüllt sind (und nicht in früheren Jahren), können die Benutzer für Microsoft 365 Oder Office 365 [und Teams.](/office365/enterprise/assign-licenses-to-user-accounts)

Für eine optimale Erste Besprechungserfahrung sollten die Benutzer für Exchange Online [,](exchange-teams-interact.md)SharePoint [Online und](sharepoint-onedrive-interact.md)OneDrive for Business und Microsoft 365 aktiviert sein. Besprechungen Zuerst wird für Benutzer unterstützt, deren Postfach Exchange lokal ist oder die nicht über SharePoint Online oder OneDrive For Business oder die Erstellung einer Microsoft 365-Gruppe verfügen. Die Benutzererfahrung ist jedoch weniger vollständig. Insbesondere bei Organisationen, die Exchange Server lokal verwenden, können (je nach Version von Exchange Server) einige Einschränkungen beim Erstellen und Anzeigen von Besprechungen über den Teams-Client sowie im Hinblick auf Compliancefunktionen gelten.

Benutzer müssen mindestens über [eine Lizenz für Teams.](/microsoft-365/admin/manage/assign-licenses-to-users) Darüber hinaus können sie bei Bedarf für [Audiokonferenzen](set-up-audio-conferencing-in-teams.md)lizenziert werden.

Es wird empfohlen, [ **den SfBOnly-** oder **SfBWithTeamsCollab-Modus**](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps) zum Zeitpunkt der Lizenz für die Benutzer als Mandanten standard zu gewähren. Dadurch wird sichergestellt, dass Benutzer die Besprechungen Teams im Standardmodus **"Islands"** nicht allein verwenden, bevor Sie zum Starten von "Besprechungen zuerst" bereit sind.

Meetings First wird auf vollständigen Desktopclients (Windows und Mac), auf Browserclients und auf mobilen Clients unterstützt. Sie ist auch kompatibel mit [Microsoft Teams-Räume.](/microsoftteams/room-systems/) "Better Together" erfordert den vollständigen Desktopclient.

## <a name="prepare-for-teams-meetings-in-meetings-first"></a>Vorbereiten auf Teams Besprechungen in Besprechungen

Damit Ihre Benutzer in Besprechungen und Besprechungen die Teams können, sollten Sie:

- Führen Sie insbesondere die Schritte in [Besprechungen](deploy-meetings-microsoft-teams-landing-page.md)und Microsoft Teams Für Besprechungen aus.
- [Bewerten Sie Ihre Umgebung.](3-envision-evaluate-my-environment.md)
- [Bereiten Sie das Netzwerk Ihrer Organisation für die Microsoft Teams](prepare-network.md)vor.
- Aktualisieren Sie Ihre Besprechungsräume [](/skypeforbusiness/certification/devices-meeting-rooms?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json)mit Teams-fähigen Besprechungsraumgeräten und -lösungen, oder verwenden Sie [Cloud Video Interop für Microsoft Teams,](cloud-video-interop.md) um Ihren vorhandenen Räumen und Geräten von Drittanbietern die Teilnahme an Besprechungen Teams ermöglichen.
- Stellen Sie Ihren Benutzern zertifizierte [USB-Audio- und Videogeräte zur Verfügung.](/skypeforbusiness/certification/devices-usb-devices?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json)
- Bereiten Sie sich darauf vor, das Bewusstsein für und Teams für [Besprechungen zu fördern.](adopt-microsoft-teams-landing-page.md)
- [Planen Sie die Dienstverwaltung.](4-envision-plan-my-service-management.md)
- Machen Sie sich mit den reichhaltigen Anrufanalyseberichten vertraut, [um Probleme mit schlechter Anrufqualität zu beheben.](use-call-analytics-to-troubleshoot-poor-call-quality.md)

Sie können in dieser Phase ein mäßiges produktionsfertiges Pilotprojekt in Betracht ziehen.

## <a name="configure-users-for-meetings-first"></a>Konfigurieren von Benutzern für Besprechungen zuerst

Nachdem Sie ihre Benutzer lizenziert und Ihre Organisation für Teams Besprechungen vorbereitet haben, ist es an der Zeit, Ihre Benutzer zuerst für Besprechungen zu aktivieren. Wir haben es einfach gemacht: Eine einzige Einstellung macht alles.

Alle Funktionen und Benutzererfahrungen in Besprechungen Zuerst, einschließlich der [Teams-Clientkonfiguration](teams-client-experience-and-conformance-to-coexistence-modes.md) und der automatischen Konformität der Benutzeroberfläche, des Meetings Migration Service und der Better Together-Funktionen, werden konfiguriert, indem dem Benutzer (oder einer Benutzergruppe oder Mandanten standard) der Koexistenzmodus [SfBWithTeamsCollabAndMeetings](setting-your-coexistence-and-upgrade-settings.md) entweder im [Microsoft Teams](manage-teams-in-modern-portal.md) Admin Center oder mithilfe von [PowerShel gewährt wird. l](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).

![Screenshot der Administratoreinstellungen zum Aktivieren von "Besprechungen zuerst".](media/teams-meeting-admin-settings.png)

Optional sollten Sie die Anwendung Teams und Kanäle aus der linken Navigationsleiste des Teams-Clients Ihrer Benutzer ausblenden, um die Benutzererfahrung stärker auf Besprechungen zu konzentrieren, die mithilfe der App-Setup-Richtlinie erreicht werden [können.](teams-app-setup-policies.md)

## <a name="reporting-and-call-analytics"></a>Berichterstellung und Anrufanalyse

Die Berichterstellung und die Anrufanalyse für Teams Besprechungen in Besprechungen sind gegenüber dem, was sie in anderen Modi sind, unverändert.

## <a name="related-links"></a>Links zu verwandten Themen

Nachdem Sie diesen Artikel überprüft haben, sollten Sie [](migration-interop-guidance-for-teams-with-skype.md)weitere Informationen unter Auswählen Ihres Upgradewegs, [](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)Anleitungen für Migration und Interoperabilität und [Koexistenz Skype for Business](coexistence-chat-calls-presence.md) Mit Skype for Business lesen.
