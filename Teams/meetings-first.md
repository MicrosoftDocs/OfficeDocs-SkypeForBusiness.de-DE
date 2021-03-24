---
title: Besprechung zuerst – Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: lsomi
description: Erfahren Sie mehr über Besprechungen zuerst, in denen Benutzer ihre Besprechung in Teams erstellen können, während Sie Skype for Business weiterhin für Chats, Anrufe und Anwesenheitsgespräche verwenden können.
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
ms.openlocfilehash: b691a9d722a82e68384f8937479c5f71d3f4c11d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096169"
---
# <a name="meetings-first"></a>Besprechungen zuerst

"Besprechungen zuerst" richtet sich an Skype for Business Server-Organisationen mit lokalen Enterprise-VoIP, die so schnell wie möglich mit der Nutzung von Teams-Besprechungen beginnen möchten. Für diese Organisationen ist "Besprechungen  zuerst" eine Alternative zur Verwendung des Modus "Inseln", der die Teambesprechungserfahrung priorisiert.

## <a name="what-is-meetings-first"></a>Was ist "Besprechungen zuerst"?

Meetings First basiert auf dem Koexistenzmodus **SfBWithTeamsCollabAndMeetings.** "Besprechungen zuerst" ist kein Produkt oder Feature– es ist eine Konfiguration, die Funktionen und Features von Teams und Skype for Business verwendet, um eine individuell angepasste Koexistenzerfahrung zu bieten.

In "Besprechungen zuerst" erstellen Benutzer ihre Besprechung in Teams, während Skype for Business weiterhin für Chats, Anrufe und Anwesenheitsgespräche verwendet wird. Es gibt keine Überlappung der Modalitäten zwischen Teams und Skype for Business. Chat, Anrufe und Anwesenheit sind in Skype for Business und in Teams deaktiviert. Dies ermöglicht einzigartige Szenarien für eine bessere Zusammenarbeit zwischen Skype for Business und Teams, die die Benutzerfreundlichkeit während der Koexistenz verbessern, sowie Interoperabilitätsszenarien mit **Teams Only-Benutzern.**

![Screenshot des besseren Gemeinsamen Szenarios mit Teams und Skype for Business](media/meetings-first-meeting-in-meeting.png)

> [!Important]
> "Besprechungen zuerst" ist eine bessere Übereinstimmung für Organisationen, die keine oder nur wenige aktive Teams-Chatbenutzer haben. Aktive Teams-Chatbenutzer sollten nicht in den Modus "Besprechungen zuerst" umgestellt werden, da sie die Möglichkeit verlieren, in Teams zu chatten und auf ihren Chatverlauf zu zugreifen. Diese Benutzer sollten stattdessen  im Inselmodus und Besprechungen zuerst nur benutzern gewährt werden, die noch nicht in Chats in Teams aktiv sind.

## <a name="who-should-consider-meetings-first"></a>Wer sollte zuerst Besprechungen in Erwägung ziehen?

Meetings First wurde für Organisationen entwickelt, die Skype for Business Server mit Enterprise-VoIP verwenden, die ihren Wechsel zu Teams-Besprechungen beschleunigen möchten, insbesondere für Organisationen mit einer starken IT-Disziplin, die einen verwalteten, deterministischen Upgradepfad zu Teams wünschen.

Bei komplexen oder großen Organisationen erfolgen Sprachmigrationen in der Regel auf Websitebasis und können lange, potenziell mehrere Jahre dauern, was zu erweiterten Koexistenzszenarien führt. Wenn sich diese  Koexistenz im Inselmodus befindet, haben Benutzer immer die Wahl zwischen zwei Besprechungslösungen (Skype for Business und Teams), was zu verwirrenden oder suboptimalen Situationen führen kann. Im Gegensatz zu Sprachmigrationen können Besprechungsmigrationen im Allgemeinen innerhalb kurzer Zeit im gesamten Unternehmen abgeschlossen werden. Organisationen, die so schnell wie möglich vollständig zu Teams-Besprechungen wechseln möchten (und ohne auf den Abschluss ihrer Sprachmigration zu warten), sollten zuerst Besprechungen in Erwägung ziehen.

Besprechungen Zuerst ist für Organisationen, die keine Benutzer haben, möglicherweise Enterprise-VoIP nützlich. Diese Organisationen sollten ein Upgrade auf **Teams nur durchführen** können, sobald sie Teams-Besprechungen annehmen können. Sie sollten zuerst Besprechungen überspringen.

Darüber hinaus ist "Besprechungen zuerst" für Organisationen nützlich, deren Umfang eine reine Besprechungslösung ist, z. B. wenn ein RfP nur für Besprechungen ausgegeben wird.

## <a name="capabilities-in-meetings-first"></a>Funktionen in "Besprechungen zuerst"

Meeting First bringt die folgenden Funktionen zusammen:

- [Bereitstellen eines lokalen Skype for Business Server-Benutzers](./tutorial-audio-conferencing.yml?tutorial-step=3) mit [Teams Audio conferencing](tutorial-audio-conferencing.yml).
- [Migrationsdienst für Besprechungen:](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)Vom Benutzer organisierte Besprechungen werden in die Cloud migriert und in Teams-Besprechungen konvertiert, wenn der Benutzer zu "Besprechungen zuerst" heraufgestuft wird (erfordert Exchange Online).
- Optimierte Benutzererfahrung in Teams, zentriert auf Teams-Besprechungen und Teams und Kanälen (die optional mithilfe der App-Berechtigungsrichtlinie ausgeblendet [werden können);](teams-app-permission-policies.md) [Private Chats, Anrufe und](teams-client-experience-and-conformance-to-coexistence-modes.md) Selbstpräsenz von Teams werden in "Besprechungen zuerst" nicht verfügbar gemacht, sodass sich die Bereitstellungs- und Einführungsleistung vollständig auf Besprechungen konzentrieren kann.
- [Besprechungserfahrung von](tutorial-meetings-in-teams.yml)Superior Teams .
- "Besser zusammen" zwischen Teams und Skype for Business: 
  - Automatisches Halten: Wenn Sie in einer Besprechung in Teams einen Anruf in Skype for Business führen, wird die Teams-Besprechung in den Halteraum gestellt und umgekehrt. Dadurch wird verhindert, dass Benutzer ihre privaten Anrufe von den Besprechungsteilnehmern überhören.
    ![Screenshot des besseren Gemeinsamen Szenarios mit Teams und Skype for Business](media/meetings-first-better-together-hold.png)
  - Anwesenheitsabgleich: Aktivitäten in Teams spiegeln sich in der Anwesenheit des Benutzers wider, d. h. in der Skype for Business-Anwesenheit, da Chats und Anrufe in Skype for Business aktiv sind. Insbesondere werden die Anwesenheitsbesprechungen der ersten Benutzer in einer Teams-Besprechung aktualisiert, um dies widerspiegeln zu können. Wenn sie ihren Bildschirm präsentieren, wird ihre Anwesenheit aktualisiert, um "Nicht stören" anzuzeigen (basierend auf ihren Einstellungen in Skype for Business).
  - USB-Gerät HID-Steuerungsabstimmung (auch für Mac verfügbar): Die HID-Steuerelemente werden von Teams in Teams-Besprechungen und von Skype for Business unter allen anderen Umständen berücksichtigt.
  - Sofern nicht anders erwähnt, erfordern better together-Funktionen zurzeit aktuelle Windows-Desktopclients.

## <a name="prerequisites-for-meetings-first"></a>Voraussetzungen für "Besprechungen zuerst"

Die einzigen harten Anforderungen für "Besprechungen zuerst" entsprechen den Anforderungen für Teams mit lokalem Active Directory und einer lokalen Skype for Business-Bereitstellung:

- [Allgemeine Voraussetzungen für Teams,](upgrade-plan-journey-prerequisites.md)einschließlich
- [Identität und Authentifizierung in Teams](identify-models-authentication.md) und
- [Konfigurieren Sie Azure Active Directory für Teams und Skype for Business.](/skypeforbusiness/hybrid/configure-azure-ad-connect)

Eine [Skype for Business-Hybridtopologie](/skypeforbusiness/hybrid/configure-federation-with-skype-for-business-online) ist nicht erforderlich, wird jedoch empfohlen. Einige Funktionen wie der Migrationsdienst für Besprechungen und die Interoperabilität sind auf diese Topologie angewiesen.

Besprechungen Zuerst wird mit jeder Version von Skype for Business Server unterstützt (und bekannt dafür, mit dem nicht mehr unterstützten Lync Server zu arbeiten). Es wird von jedem unterstützten Skype for Business-Client unterstützt, jedoch ist für better together-Funktionen ein neuer Client erforderlich.

Sobald diese Anforderungen erfüllt sind (und nicht zuvor), können die Benutzer für [Microsoft 365 oder Office 365](/office365/enterprise/assign-licenses-to-user-accounts)und Teams lizenziert werden.

Für die beste Erfahrung in Besprechungen Zuerst sollten Benutzer für die Gruppenerstellung [in Exchange Online,](exchange-teams-interact.md) [SharePoint Online und OneDrive for Business](sharepoint-onedrive-interact.md)und Microsoft 365 aktiviert sein. Besprechungen Zuerst wird für Benutzer unterstützt, deren Postfach sich lokal in Exchange befindet oder die nicht über SharePoint Online oder OneDrive For Business oder die Erstellung von Microsoft 365-Gruppen verfügen. Ihre Erfahrung ist jedoch weniger vollständig. Insbesondere für Organisationen, die Exchange Server lokal verwenden, kann es (abhängig von der Version von Exchange Server) einige Einschränkungen beim Erstellen und Anzeigen von Besprechungen im Teams-Client sowie in Bezug auf Compliancefunktionen geben.

Mindestens müssen Die Benutzer für [Teams lizenziert sein.](/microsoft-365/admin/manage/assign-licenses-to-users) Darüber hinaus können sie bei Bedarf für [Audiokonferenzen](set-up-audio-conferencing-in-teams.md)lizenziert werden.

Es wird empfohlen, [ **den SfBOnly-** oder **SfBWithTeamsCollab-Modus**](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps) zum Zeitpunkt der Lizenz für die Benutzer als Mandanteneinstellung zu gewähren. Dadurch wird sichergestellt, dass Benutzer Teams nicht  im Standardmodus "Inseln" allein verwenden, bevor Sie zum Starten von "Besprechungen zuerst" bereit sind.

Meetings First wird auf vollständigen Desktopclients (Windows und Mac), auf Browserclients und auf mobilen Clients unterstützt. Es ist auch mit [Microsoft Teams Rooms kompatibel.](/microsoftteams/room-systems/) Better Together erfordert den vollständigen Desktopclient.

## <a name="prepare-for-teams-meetings-in-meetings-first"></a>Vorbereiten von Teams-Besprechungen in "Besprechungen zuerst"

Damit Ihre Benutzer die bestmögliche Erfahrung in Teams-Besprechungen haben, sollten Sie:

- Führen Sie insbesondere die Schritte in [Besprechungen](deploy-meetings-microsoft-teams-landing-page.md)und Konferenzen für Microsoft Teams aus.
- [Bewerten Sie Ihre Umgebung](3-envision-evaluate-my-environment.md).
- [Bereiten Sie das Netzwerk Ihrer Organisation für Microsoft Teams vor.](prepare-network.md)
- Aktualisieren Sie Ihre Besprechungsräume mit Teams-fähigen Geräten und Lösungen für Besprechungsräume, [](/skypeforbusiness/certification/devices-meeting-rooms?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json)oder verwenden Sie Cloud Video [Interop für Microsoft Teams,](cloud-video-interop.md) um Ihren vorhandenen Räumen und Geräten von Drittanbietern die Teilnahme an Teams-Besprechungen zu ermöglichen.
- Statten Sie Ihre Benutzer mit [zertifizierten USB-Audio- und Videogeräten aus.](/skypeforbusiness/certification/devices-usb-devices?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json)
- Bereiten Sie sich darauf [vor, das Bewusstsein und die Akzeptanz für Teams-Besprechungen zu fördern.](adopt-microsoft-teams-landing-page.md)
- [Planen Der Dienstverwaltung](4-envision-plan-my-service-management.md).
- Machen Sie sich mit den reichen Anrufanalyseberichten vertraut, um [Probleme mit der schlechten Anrufqualität zu beheben.](use-call-analytics-to-troubleshoot-poor-call-quality.md)

Sie können in dieser Phase möglicherweise einen produktionsbereiten Pilot im moderaten Maßstab ausführen.

## <a name="configure-users-for-meetings-first"></a>Konfigurieren von Benutzern für Besprechungen zuerst

Nachdem Sie Ihre Benutzer lizenziert und Ihre Organisation auf Teams-Besprechungen vorbereitet haben, ist es an der Zeit, ihre Benutzer für Besprechungen zuerst zu aktivieren. Wir haben es einfach gemacht: Eine einzige Einstellung macht alles!

Alle Funktionen und Benutzererfahrungen in "Besprechungen zuerst", einschließlich der Microsoft [Teams-Clientkonfiguration](teams-client-experience-and-conformance-to-coexistence-modes.md) und der automatischen Übereinstimmung der Benutzererfahrung, des Migrationsdiensts für Besprechungen und der Funktionen "Besser zusammen", werden konfiguriert, indem dem Benutzer (oder der Benutzergruppe oder der Mandanteneinstellung) der Koexistenzmodus [SfBWithTeamsCollabAndMeetings](setting-your-coexistence-and-upgrade-settings.md) entweder im [Microsoft Teams Admin Center](manage-teams-in-modern-portal.md) oder mithilfe von [PowerShell gewährt wird.](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

![Screenshot der Administratoreinstellungen zum Aktivieren von "Besprechungen zuerst"](media/teams-meeting-admin-settings.png)

Wenn Sie die Anwendung Teams und Kanäle optional aus der linken Navigationsleiste des Teams-Clients Ihrer Benutzer ausblenden möchten, um ihre Benutzererfahrung auf Besprechungen zu konzentrieren, kann dies mithilfe der [App-Berechtigungsrichtlinie erreicht werden.](teams-app-permission-policies.md)

## <a name="reporting-and-call-analytics"></a>Berichterstellung und Anrufanalyse

Reporting and Call Analytics for Teams meetings in Meetings First are unchanged from what they are in other modes.

## <a name="related-links"></a>Verwandte Links

Nachdem Sie diesen Artikel überprüft haben, sollten Sie weitere Informationen finden: Wählen Sie Ihre [Upgradereise,](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)Migrations- und Interoperabilitätsleitfäden und Die Koexistenz mit [Skype for Business](coexistence-chat-calls-presence.md) aus. [](migration-interop-guidance-for-teams-with-skype.md)