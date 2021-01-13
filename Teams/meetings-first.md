---
title: Besprechung zuerst – Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: francoid
description: Erfahren Sie zuerst mehr über Besprechungen, in denen Benutzer ihre Besprechung in Teams erstellen und Skype for Business weiterhin für Chat, Anrufe und Anwesenheit verwenden können.
localization_priority: Normal
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
ms.openlocfilehash: 34b32a1d421941e4e9c3bd743c5db1026d88a2ac
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809505"
---
# <a name="meetings-first"></a>Besprechungen zuerst

"Meetings First" ist für Skype for Business Server-Organisationen mit Enterprise-VoIP lokal ausgerichtet und optimiert, die mit der Nutzung von Teambesprechungen so schnell wie möglich beginnen möchten. Für diese Organisationen ist "Meetings First" eine Alternative zum **Islands-Modus,** der die Besprechungserfahrung in Teams priorisiert.

## <a name="what-is-meetings-first"></a>Was ist Besprechungen zuerst?

"Meetings First" basiert auf dem **Koexistenzmodus "SfBWithTeamsCollabAndMeetings".** Besprechungen sind weder ein Produkt noch ein Feature – es handelt sich um eine Konfiguration, bei der die Funktionen und Funktionen von Teams und Skype for Business genutzt werden, um eine einzigartige Koexistenzerfahrung zu bieten.

In "Besprechungen zuerst" erstellen Benutzer ihre Besprechung in Teams, während sie Skype for Business weiterhin für Chat, Anrufe und Anwesenheit verwenden. Es gibt keine Überlappung der Modalitäten zwischen Teams und Skype for Business. Chat, Anrufe und Anwesenheit sind in Skype for Business und in Teams deaktiviert. Dies ermöglicht eindeutige Szenarien für eine "bessere Zusammenarbeit" zwischen Skype for Business und Teams, die die Benutzerfreundlichkeit während der Koexistenz verbessern, sowie Interoperabilitätsszenarien mit **Teams Only-Benutzern.**

![Screenshot des Szenarios "Zusammen besser zusammen" mit Teams und Skype for Business](media/meetings-first-meeting-in-meeting.png)

> [!Important]
> "Besprechungen zuerst" ist eine bessere Übereinstimmung für Organisationen, die nur über wenige aktive Teams-Chatbenutzer verfügen. Aktive Chatbenutzer von Teams sollten nicht in den Besprechungsmodus "First" umgestellt werden, da sie die Möglichkeit zum Chatten in Teams und zum Zugriff auf ihren Chatverlauf verlieren würden. Diese Benutzer sollten stattdessen  im Islands-Modus angezeigt werden, und Besprechungen werden zuerst nur den Benutzern gewährt, die noch nicht in Einem Chat in Teams aktiv sind.

## <a name="who-should-consider-meetings-first"></a>Wer sollte Besprechungen zuerst in Erwägung ziehen?

Meetings First wurde für Organisationen entwickelt, die Skype for Business Server mit Enterprise-VoIP verwenden, die ihren Wechsel zu Teambesprechungen beschleunigen möchten, insbesondere für Organisationen mit starkem IT-Disziplin, die einen verwalteten, deterministischen Upgradepfad zu Teams wünschen.

Bei komplexen oder großen Organisationen erfolgen Sprachmigrationen in der Regel websiteintern und können sehr lange, potenziell mehrere Jahre dauern, was zu erweiterten Koexistenzszenarien führt. Wenn diese Koexistenz im Modus "Inseln" ausgeführt wird, haben Benutzer immer die Wahl zwischen zwei Besprechungslösungen (Skype for Business und Teams), was zu einer verwirrenden oder suboptimalen Situation führen kann.  Im Gegensatz zu Sprachmigrationen können Besprechungsmigrationen im Allgemeinen innerhalb kurzer Zeit im gesamten Unternehmen abgeschlossen werden. Organisationen, die so schnell wie möglich vollständig zu Teambesprechungen wechseln möchten (und ohne auf den Abschluss ihrer Sprachmigration warten zu müssen), sollten Besprechungen zuerst in Betracht ziehen.

Besprechungen zuerst sind für Organisationen, die keine Benutzer haben, möglicherweise Enterprise-VoIP nützlich. Diese Organisationen sollten nur in der Lage sein, ein Upgrade auf **Teams** zu durchführen, sobald sie in der Lage sind, Teambesprechungen zu übernehmen. Sie sollten überlegen, Besprechungen zuerst zu überspringen.

Darüber hinaus ist "Besprechungen zuerst" nützlich für Organisationen, deren Bereich eine rein spielbare Besprechungslösung ist, z. B. wenn eine "nur für Besprechungen" bestimmte Angebotsanforderung ausgegeben wird.

## <a name="capabilities-in-meetings-first"></a>Funktionen in Besprechungen zuerst

Meeting First bringt die folgenden Funktionen zusammen:

- [Bereitstellen eines (lokalen) Skype for Business Server-Benutzers](https://docs.microsoft.com/microsoftteams/tutorial-audio-conferencing?tutorial-step=3) mit [Teams-Audiokonferenzen.](tutorial-audio-conferencing.yml)
- [Migrationsdienst](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)für Besprechungen: Vom Benutzer organisierte Besprechungen werden in die Cloud migriert und in Teambesprechungen konvertiert, wenn der Benutzer zuerst zu "Besprechungen" heraufgestuft wird (erfordert Exchange Online).
- Optimierte Benutzeroberfläche in Teams, zentriert auf Teambesprechungen sowie Teams und Kanälen (die optional mithilfe der Richtlinie für [App-Berechtigungen ausgeblendet werden können);](teams-app-permission-policies.md) [Private Chats, Anrufe und Selbstanrufe](teams-client-experience-and-conformance-to-coexistence-modes.md) in Teams werden in Besprechungen zuerst nicht verfügbar gemacht, was es den Bereitstellungs- und Einführungsaufwand ermöglicht, sich vollständig auf Besprechungen zu konzentrieren.
- [Besprechungserfahrung in Superior Teams.](tutorial-meetings-in-teams.yml)
- "Better Together" zwischen Teams und Skype for Business: 
  - Automatisches Halten: Wenn Sie in einer Besprechung in Teams einen Anruf in Skype for Business führen, wird die Besprechung in der Warteschleife halten und umgekehrt. Dadurch wird verhindert, dass Benutzer ihre privaten Anrufe von den Besprechungsteilnehmern überhören.
    ![Screenshot des Szenarios "Zusammen besser zusammen" mit Teams und Skype for Business](media/meetings-first-better-together-hold.png)
  - Abstimmung über die Anwesenheit: Aktivitäten in Teams werden in den Anwesenheitsinformationen des Benutzers widersspiegelt, bei denen es sich um die Anwesenheitsinformationen von Skype for Business handelt, da sich Chats und Anrufe in Skype for Business befinden. Insbesondere, wenn sich "Meetings First"-Benutzer in einer Teambesprechung befinden, werden deren Anwesenheit aktualisiert, um dies widerspiegeln zu können. Wenn sie ihren Bildschirm präsentieren, wird ihr Anwesenheitsmodus aktualisiert, um "Nicht stören" anzuzeigen (basierend auf ihren Einstellungen in Skype for Business).
  - Abstimmung über das USB-Gerät-HID-Steuerelement (auch auf dem Mac verfügbar): Die Steuerelemente werden von Teams in Teambesprechungen und unter allen anderen Umständen von Skype for Business berücksichtigt.
  - Sofern nicht anders angegeben, sind für Better Together-Funktionen aktuelle Windows-Desktopclients zu diesem Zeitpunkt erforderlich.

## <a name="prerequisites-for-meetings-first"></a>Voraussetzungen für Besprechungen zuerst

Die einzigen schwierigen Anforderungen für "Besprechungen zuerst" sind dieselben wie die Anforderungen für Teams mit lokalem Active Directory und einer lokalen Skype for Business-Bereitstellung:

- [Allgemeine Voraussetzungen für Teams,](upgrade-plan-journey-prerequisites.md)einschließlich
- [Identität und Authentifizierung in Teams und](identify-models-authentication.md)
- [Konfigurieren Sie Azure Active Directory für Teams und Skype for Business.](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-azure-ad-connect)

Eine [Skype for Business-Hybridtopologie](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-federation-with-skype-for-business-online) ist nicht erforderlich, wird jedoch empfohlen. Einige Funktionen wie Meetings Migration Service und Interoperabilität sind von dieser Topologie angewiesen.

"Besprechungen zuerst" wird von jeder Version von Skype for Business Server unterstützt (und bekannt dafür, mit dem nicht mehr unterstützten Lync Server zu arbeiten). Es wird von jedem unterstützten Skype for Business-Client unterstützt, für die Better Together-Funktionen ist jedoch ein neuer Client erforderlich.

Sobald diese Anforderungen erfüllt sind (und nicht früher), können die Benutzer für [Microsoft 365 oder Office 365 und Teams lizenziert werden.](https://docs.microsoft.com/office365/enterprise/assign-licenses-to-user-accounts)

Für eine optimale Benutzererfahrung bei Besprechungen sollten die Benutzer für [Exchange Online,](exchange-teams-interact.md) [SharePoint Online und OneDrive for Business](sharepoint-onedrive-interact.md)sowie für die Erstellung von Microsoft 365-Gruppen aktiviert sein. "Besprechungen zuerst" wird für Benutzer unterstützt, deren Postfach sich auf einem lokalen #A0 befindet oder die nicht über SharePoint Online, OneDrive for Business oder die Erstellung von Microsoft 365-Gruppen verfügen. Allerdings ist deren Erfahrung weniger vollständig. Insbesondere bei Organisationen, die Exchange Server lokal verwenden, können (je nach Version von Exchange Server) einige Einschränkungen beim Erstellen und Anzeigen von Besprechungen im Teamclient sowie im Hinblick auf Compliancefunktionen gelten.

Benutzer müssen mindestens für [Teams lizenziert sein.](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users) Darüber hinaus können sie bei Bedarf für [Audiokonferenzen](set-up-audio-conferencing-in-teams.md)lizenziert werden.

Es wird empfohlen, [ **den Modus SfBOnly** oder **SfBWithTeamsCollab**](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps) zum Zeitpunkt der Lizenz für die Benutzer als Mandanten standard zu gewähren. Dadurch wird sichergestellt, dass Benutzer Teams nicht  allein im Standardmodus "Islands" verwenden, bevor Sie bereit sind, zuerst Besprechungen zu starten.

"Besprechungen zuerst" wird auf vollständigen Desktopclients (Windows und Mac), auf Browserclients und auf mobilen Clients unterstützt. Sie ist auch mit [Microsoft Teams Rooms kompatibel.](https://docs.microsoft.com/microsoftteams/room-systems/) Better Together erfordert den vollständigen Desktopclient.

## <a name="prepare-for-teams-meetings-in-meetings-first"></a>Vorbereiten von Teambesprechungen in Besprechungen zuerst

Damit Ihre Benutzer in Teambesprechungen die bestmögliche Erfahrung haben, sollten Sie:

- Führen Sie insbesondere die Schritte in [Besprechungen und](deploy-meetings-microsoft-teams-landing-page.md)Konferenzen für Microsoft Teams aus.
- [Bewerten Sie Ihre Umgebung.](3-envision-evaluate-my-environment.md)
- [Bereiten Sie das Netzwerk Ihrer Organisation für Microsoft Teams vor.](prepare-network.md)
- Aktualisieren Sie Ihre Besprechungsräume mit Teams-fähigen Besprechungsraumgeräten und [-lösungen,](https://docs.microsoft.com/skypeforbusiness/certification/devices-meeting-rooms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)oder verwenden Sie Cloud Video Interop für Microsoft [Teams,](cloud-video-interop.md) um Ihren vorhandenen Räumen und Geräten von Drittanbietern die Teilnahme an Teambesprechungen zu ermöglichen.
- Bestatten Sie Ihre Benutzer [mit zertifizierten USB-Audio- und -Videogeräten.](https://docs.microsoft.com/skypeforbusiness/certification/devices-usb-devices?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- Bereiten Sie sich darauf [vor, das Bewusstsein für Teambesprechungen zu fördern und die Einführung zu fördern.](adopt-microsoft-teams-landing-page.md)
- [Planen Sie die Dienstverwaltung.](4-envision-plan-my-service-management.md)
- Machen Sie sich mit den reichhaltigen Anrufanalyseberichten vertraut, um [Probleme mit einer schlechten Anrufqualität zu beheben.](use-call-analytics-to-troubleshoot-poor-call-quality.md)

Sie können in dieser Phase ein Pilotprojekt mit mittlerem Produktionsmaßstab in Betracht ziehen.

## <a name="configure-users-for-meetings-first"></a>Konfigurieren von Benutzern für Besprechungen zuerst

Nachdem Sie Ihre Benutzer lizenziert und Ihre Organisation für Teambesprechungen vorbereitet haben, ist es an der Zeit, Ihre Benutzer zuerst für Besprechungen zu aktivieren. Wir haben es ihnen leicht gemacht: Mit einer einzigen Einstellung ist alles möglich!

Alle Funktionen und Benutzeroberflächen in "Meetings First", einschließlich der [Teams-Clientkonfiguration](teams-client-experience-and-conformance-to-coexistence-modes.md) und der automatischen Konformität der Funktionen "Benutzererfahrung", "Meetings Migration Service" und "Better Together", werden konfiguriert, indem dem Benutzer (oder der Benutzergruppe oder dem Mandanten standard) der Koexistenzmodus ["SfBWithTeamsCollabAndMeetings"](setting-your-coexistence-and-upgrade-settings.md) entweder im [Microsoft Teams Admin](manage-teams-in-modern-portal.md) Center oder mithilfe von [PowerShell](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)gewährt wird.

![Screenshot der Administratoreinstellungen zum aktivieren von "Besprechungen zuerst"](media/teams-meeting-admin-settings.png)

Optional sollten Sie die Anwendung "Teams und Kanäle" in der linken Navigationsleiste des Teams-Clients Ihrer Benutzer ausblenden, um ihre Erfahrung auf Besprechungen zu konzentrieren, die mithilfe der Richtlinie für Die Berechtigung der App [erreicht werden können.](teams-app-permission-policies.md)

## <a name="reporting-and-call-analytics"></a>Berichterstellung und Anrufanalyse

Reporting and Call Analytics for Teams meetings in Meetings First are unchanged from what they are in other modes.

## <a name="related-links"></a>Links zu verwandten Themen

Nachdem Sie sich diesen Artikel durchschaut haben, sollten Sie weitere Einzelheiten unter "Upgradeweg [auswählen",](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)Anleitungen zu Migration und [Interoperabilität](migration-interop-guidance-for-teams-with-skype.md)sowie zur Koexistenz mit Skype for [Business](coexistence-chat-calls-presence.md) lesen.


