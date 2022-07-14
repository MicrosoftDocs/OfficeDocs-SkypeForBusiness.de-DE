---
title: Erste Besprechung – Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: lsomi
description: Erfahren Sie zuerst mehr über Besprechungen, bei denen Benutzer ihre Besprechung in Teams erstellen und gleichzeitig Skype for Business für Chat, Anrufe und Anwesenheit verwenden können.
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
ms.openlocfilehash: 149a5a3e22a633ec4c889b68a91ac9c6db8e9f4b
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789780"
---
# <a name="meetings-first"></a>Besprechungen zuerst

"Meetings First" richtet sich an und ist für Skype for Business Server Organisationen mit Enterprise-VoIP vor Ort optimiert, die so schnell wie möglich mit der Nutzung von Teams-Besprechungen beginnen möchten. Für diese Organisationen ist "Meetings First" eine Alternative zur Verwendung des **Inselmodus** , der die Teams-Besprechungserfahrung priorisiert.

## <a name="what-is-meetings-first"></a>Was ist "Besprechungen zuerst"?

"Meetings First" basiert auf dem Koexistenzmodus **"SfBWithTeamsCollabAndMeetings** ". Besprechungen zuerst ist kein Produkt oder Feature – es ist eine Konfiguration, die Funktionen und Features von Teams und Skype for Business verwendet, um eine individuell angepasste Koexistenzerfahrung bereitzustellen.

In Besprechungen erstellen Benutzer zuerst ihre Besprechung in Teams, während sie weiterhin Skype for Business für Chat, Anrufe und Anwesenheit verwenden. Es gibt keine Überlappung der Modalitäten zwischen Teams und Skype for Business. Chat, Anrufe und Anwesenheit sind in Skype for Business und deaktiviert in Teams. Dies ermöglicht einzigartige "better together"-Szenarien zwischen Skype for Business und Teams, die die Benutzererfahrung während der Koexistenz verbessern, sowie Interoperabilitätsszenarien mit **Nur Teams-Benutzern**.

![Screenshot des Szenarios "Bessere Zusammenarbeit" mit Teams und Skype for Business.](media/meetings-first-meeting-in-meeting.png)

> [!Important]
> "Besprechungen zuerst" ist eine bessere Übereinstimmung für Organisationen, die keine oder nur wenige aktive Teams-Chatbenutzer haben. Aktive Teams-Chatbenutzer sollten nicht in den Modus "Erste Besprechungen" umgestellt werden, da sie die Möglichkeit verlieren würden, in Teams zu chatten und auf ihren Chatverlauf zuzugreifen. Diese Benutzer sollten stattdessen im **Inselmodus** behandelt werden, und Besprechungen sollten zuerst nur den Benutzern gewährt werden, die noch nicht im Chat in Teams aktiv sind.

## <a name="who-should-consider-meetings-first"></a>Wer sollte Besprechungen zuerst in Betracht ziehen?

Meetings First wurde für Organisationen entwickelt, die Skype for Business Server mit Enterprise-VoIP verwenden, die ihren Wechsel zu Teams-Besprechungen beschleunigen möchten, insbesondere für Personen mit starker IT-Disziplin, die einen verwalteten, deterministischen Upgradepfad zu Teams wünschen.

Bei komplexen oder großen Organisationen werden VoIP-Migrationen in der Regel von Standort zu Standort durchgeführt und können lange dauern, möglicherweise mehrere Jahre, was zu erweiterten Koexistenzszenarien führt. Wenn sich diese Koexistenz im **Inselmodus** befindet, haben Benutzer immer die Wahl zwischen zwei Besprechungslösungen (Skype for Business und Teams), die zu verwirrenden oder suboptimalen Situationen führen können. Im Gegensatz zu VoIP-Migrationen können Besprechungsmigrationen in der Regel innerhalb kurzer Zeit im gesamten Unternehmen durchgeführt werden. Organisationen, die so schnell wie möglich vollständig zu Teams-Besprechungen wechseln möchten (und ohne darauf zu warten, dass ihre VoIP-Migration abgeschlossen ist), sollten zuerst Besprechungen in Betracht ziehen.

Besprechungen zuerst sind für Organisationen, die keine Enterprise-VoIP Benutzer haben, möglicherweise nicht nützlich. Diese Organisationen sollten in der Lage sein, **nur auf Teams** zu aktualisieren, sobald sie in der Lage sind, Teams-Besprechungen anzunehmen. Sie sollten erwägen, zuerst Besprechungen zu überspringen.

Darüber hinaus ist "Meetings First" für Organisationen nützlich, deren Bereich eine rein wiedergegebene Besprechungslösung ist, z. B. wenn eine "nur Besprechungsanfrage" ausgegeben wird.

## <a name="capabilities-in-meetings-first"></a>Funktionen in Besprechungen zuerst

Meeting First bringt die folgenden Funktionen zusammen:

- [Bereitstellen eines Skype for Business Server (lokalen) Benutzers](./tutorial-audio-conferencing.yml?tutorial-step=3) mit [Teams-Audiokonferenzen](tutorial-audio-conferencing.yml).
- [Migrationsdienst für Besprechungen](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms): Vom Benutzer organisierte Besprechungen werden in die Cloud migriert und in Teams-Besprechungen konvertiert, wenn der Benutzer zuerst zu Besprechungen heraufgestuft wird (erfordert Exchange Online).
- Optimierte Benutzererfahrung in Teams, zentriert auf Teams-Besprechungen und Teams und -Kanälen (die optional mithilfe der [App-Berechtigungsrichtlinie](teams-app-permission-policies.md) ausgeblendet werden können); [Private Chat-, Anruf- und Selbstpräsenz in Teams](teams-client-experience-and-conformance-to-coexistence-modes.md) werden in Besprechungen zuerst nicht verfügbar gemacht, sodass sich die Bereitstellungs- und Einführungsbemühungen vollständig auf Besprechungen konzentrieren können.
- Überlegene [Teams-Besprechungserfahrung](tutorial-meetings-in-teams.yml).
- "Better Together" zwischen Teams und Skype for Business: 
  - Automatische Aufbewahrung: Wenn Sie in einer Besprechung in Teams einen Anruf in Skype for Business erhalten, wird die Teams-Besprechung gehalten und umgekehrt. Dadurch wird verhindert, dass Benutzer ihre privaten Anrufe von den Besprechungsteilnehmern überhören.
    ![Screenshot des Szenarios "Bessere Zusammenarbeit" mit Teams und Skype for Business.](media/meetings-first-better-together-hold.png)
  - Anwesenheits abstimmung: Aktivitäten in Teams spiegeln sich in der Anwesenheit des Benutzers wider. Dies ist die Skype for Business Anwesenheit, da Chat und Anrufe in Skype for Business sind. Insbesondere wenn sich die ersten Benutzer von Besprechungen in einer Teams-Besprechung befinden, wird ihre Anwesenheit entsprechend aktualisiert. Wenn sie ihren Bildschirm präsentieren, wird ihre Anwesenheit aktualisiert, um "Nicht stören" anzuzeigen (basierend auf ihren Einstellungen in Skype for Business).
  - HID-Steuerelement-Abstimmung für USB-Geräte (auch für Mac verfügbar): Die HID-Steuerelemente werden von Teams in Teams-Besprechungen und von Skype for Business unter allen anderen Umständen berücksichtigt.
  - Sofern nicht anders erwähnt, erfordern Better Together-Funktionen zurzeit aktuelle Windows-Desktopclients.

## <a name="prerequisites-for-meetings-first"></a>Voraussetzungen für Besprechungen zuerst

Die einzigen schwierigen Anforderungen für "Besprechungen zuerst" sind die gleichen wie die Anforderungen für Teams mit lokales Active Directory und einer Skype for Business lokalen Bereitstellung:

- [Allgemeine Voraussetzungen für Teams](upgrade-plan-journey-prerequisites.md), einschließlich
- [Identität und Authentifizierung in Teams](identify-models-authentication.md) und
- [Konfigurieren Sie Azure Active Directory für Teams und Skype for Business](/skypeforbusiness/hybrid/configure-azure-ad-connect).

Eine [Skype for Business Hybridtopologie](/skypeforbusiness/hybrid/configure-federation-with-skype-for-business-online) ist nicht erforderlich, wird jedoch empfohlen. Einige Funktionen wie der Besprechungsmigrationsdienst und die Interoperabilität basieren auf dieser Topologie.

"Besprechungen zuerst" wird mit jeder Version der Skype for Business Server unterstützt (und ist bekannt für die Arbeit mit dem nicht mehr unterstützten Lync-Server). Es wird mit allen unterstützten Skype for Business-Clients unterstützt, jedoch erfordern Better Together-Funktionen einen aktuellen Client.

Sobald diese Anforderungen erfüllt sind (und nicht zuvor), können die Benutzer [für Microsoft 365 oder Office 365 und Teams lizenziert](/office365/enterprise/assign-licenses-to-user-accounts) werden.

Für eine optimale Besprechungserfahrung sollten Benutzer für [Exchange Online](exchange-teams-interact.md), [SharePoint Online und OneDrive for Business](sharepoint-onedrive-interact.md) sowie die Erstellung von Microsoft 365-Gruppen aktiviert werden. "Besprechungen zuerst" wird für Benutzer unterstützt, deren Postfach sich lokal in Exchange befindet oder die nicht über SharePoint Online oder OneDrive for Business oder die Erstellung von Microsoft 365-Gruppen verfügen. Ihre Erfahrung wird jedoch weniger vollständig sein. Insbesondere für Organisationen, die Exchange Server lokal verwenden, kann es (je nach Version von Exchange Server) einige Einschränkungen beim Erstellen und Anzeigen von Besprechungen über den Teams-Client sowie hinsichtlich der Compliancefunktionen geben.

Mindestens müssen Benutzer [für Teams lizenziert](/microsoft-365/admin/manage/assign-licenses-to-users) sein. Darüber hinaus können sie bei Bedarf für [Audiokonferenzen](set-up-audio-conferencing-in-teams.md) lizenziert werden.

Es wird empfohlen [, den **SfBOnly** - oder **SfBWithTeamsCollab-Modus**](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps) zum Zeitpunkt der Lizenzierung der Benutzer als Mandantenstandard zu gewähren. Dadurch wird sichergestellt, dass Benutzer teams nicht allein im Standardmodus **"Inseln** " verwenden, bevor Sie bereit sind, zuerst Besprechungen zu starten.

Meetings First wird auf vollständigen Desktopclients (Windows und Mac), auf Browserclients und auf mobilen Clients unterstützt. Es ist auch mit [Microsoft Teams-Räume](/microsoftteams/room-systems/) kompatibel. Better Together erfordert den vollständigen Desktopclient.

## <a name="prepare-for-teams-meetings-in-meetings-first"></a>Vorbereiten auf Teams-Besprechungen in Besprechungen zuerst

Damit Ihre Benutzer die bestmögliche Erfahrung in Teams-Besprechungen haben, sollten Sie Folgendes tun:

- Führen Sie insbesondere die Schritte in [Besprechungen und Konferenzen für Microsoft Teams aus](deploy-meetings-microsoft-teams-landing-page.md).
- [Bewerten Sie Ihre Umgebung](3-envision-evaluate-my-environment.md).
- [Bereiten Sie das Netzwerk Ihrer Organisation auf Microsoft Teams vor](prepare-network.md).
- Aktualisieren Sie Ihre Besprechungsräume mit Teams-fähigen [Besprechungsraumgeräten und -lösungen](/skypeforbusiness/certification/devices-meeting-rooms?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json), oder verwenden Sie [Cloud Video Interop für Microsoft Teams](cloud-video-interop.md) , um Ihren vorhandenen Räumen und Geräten von Drittanbietern die Teilnahme an Teams-Besprechungen zu ermöglichen.
- Statten Sie Ihre Benutzer mit [zertifizierten USB-Audio- und Videogeräten aus](/skypeforbusiness/certification/devices-usb-devices?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json).
- Bereiten Sie sich darauf vor, [das Bewusstsein und die Akzeptanz für Teams-Besprechungen zu fördern](adopt-microsoft-teams-landing-page.md).
- [Planen Sie Ihre Dienstverwaltung](4-envision-plan-my-service-management.md).
- Machen Sie sich mit den umfangreichen Anrufanalyseberichten vertraut, um [probleme mit schlechter Anrufqualität zu beheben](use-call-analytics-to-troubleshoot-poor-call-quality.md).

Möglicherweise sollten Sie in dieser Phase ein produktionsbereites Pilotprojekt im mittleren Maßstab ausführen.

## <a name="configure-users-for-meetings-first"></a>Konfigurieren von Benutzern für Besprechungen zuerst

Nachdem Sie Ihre Benutzer lizenziert und Ihre Organisation auf Teams-Besprechungen vorbereitet haben, ist es an der Zeit, Ihre Benutzer zuerst für Besprechungen zu aktivieren. Wir haben es einfach gemacht: Eine einzige Einstellung wird alles erledigen!

Alle Funktionen und Benutzeroberflächen in "Besprechungen zuerst", einschließlich der [Teams-Clientkonfiguration und der automatischen Konformität](teams-client-experience-and-conformance-to-coexistence-modes.md) der Benutzeroberfläche, des Migrationsdiensts für Besprechungen und der Funktionen "Bessere Zusammen", werden konfiguriert, indem dem Benutzer (oder einer Gruppe von Benutzern oder der Mandantenstandard) der [SfBWithTeamsCollabAndMeetings-Koexistenzmodus](setting-your-coexistence-and-upgrade-settings.md) entweder im [Microsoft Teams Admin Center](manage-teams-in-modern-portal.md) oder mithilfe von [PowerShell](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps) gewährt wird.

![Screenshot der Administratoreinstellungen zum Aktivieren von "Besprechungen zuerst".](media/teams-meeting-admin-settings.png)

Optional sollten Sie die Teams- und Kanäle-Anwendung aus der linken Navigation des Teams-Clients Ihrer Benutzer ausblenden, um ihre Erfahrung weiter auf Besprechungen zu konzentrieren, die mithilfe der [App-Setup-Richtlinie](teams-app-setup-policies.md) erreicht werden können.

## <a name="reporting-and-call-analytics"></a>Berichterstellung und Anrufanalyse

Berichterstellung und Anrufanalyse für Teams-Besprechungen in Besprechungen zuerst sind unverändert, als sie sich in anderen Modi befinden.

## <a name="related-links"></a>Verwandte Links

Nachdem Sie diesen Artikel durchgesehen haben, sollten Sie sich für weitere Details den [Leitfaden "Upgradereise auswählen](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)", ["Migration und Interoperabilität](migration-interop-guidance-for-teams-with-skype.md)" und ["Koexistenz mit Skype for Business](coexistence-chat-calls-presence.md)" ansehen.
