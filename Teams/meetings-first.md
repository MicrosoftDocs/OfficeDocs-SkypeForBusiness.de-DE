---
title: Erste Besprechung – Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: francoid
description: Informieren Sie sich zuerst über Besprechungen, in denen Benutzer Ihre Besprechung in Teams erstellen können, während Sie weiterhin Skype for Business für Chats, Anrufe und Anwesenheitsinformationen verwenden.
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
ms.openlocfilehash: d8c88ba4ddb8b2e9af83e227388232e243dcabe1
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/03/2020
ms.locfileid: "43140294"
---
# <a name="meetings-first"></a>Besprechungen zuerst

"Meetings First" richtet sich an und optimiert für Skype for Business Server-Organisationen mit Enterprise-VoIP auf Räumlichkeiten, die so schnell wie möglich mit der Verwendung von Teams-Besprechungen beginnen möchten. Für diese Organisationen ist "Besprechungen" zunächst eine Alternative zur Verwendung des **Inseln** -Modus, der die Teambesprechungen priorisiert.

## <a name="what-is-meetings-first"></a>Was sind Besprechungen zuerst?

Besprechungen basieren zunächst auf dem **SfBWithTeamsCollabAndMeetings** -Koexistenzmodus. Besprechungen sind zunächst kein Produkt oder Feature – Es handelt sich um eine Konfiguration, die Funktionen und Funktionen von Teams und Skype for Business nutzt, um eine einzigartig maßgeschneiderte Koexistenz-Erfahrung bereitzustellen.

In Besprechungen erstellen Benutzer zunächst Ihre Besprechung in Teams, während Sie weiterhin Skype for Business für Chats, Anrufe und Anwesenheitsinformationen verwenden. Es gibt keine Überlappung der Modalitäten zwischen Teams und Skype for Business. Chats, Anrufe und Anwesenheitsinformationen sind in Skype for Business und offline in Teams aktiviert. Dies ermöglicht einzigartige "bessere Zusammenarbeit"-Szenarien zwischen Skype for Business und Teams, die die Benutzererfahrung während der Koexistenz verbessern, sowie Interoperabilitätsszenarien mit **nur Teams** -Benutzern.

![Screenshot des Szenarios "besser zusammen" mit Teams und Skype for Business](media/meetings-first-meeting-in-meeting.png)

> [!Important]
> Besprechungen sind eine bessere Abstimmung für Organisationen, die keine oder nur wenige aktive Team-Chat-Benutzer haben. Aktive Teams Chat-Nutzer sollten nicht auf den ersten Modus von Besprechungen umgestellt werden, da Sie die Möglichkeit verlieren, in Teams zu chatten und auf Ihr Chat-Protokoll zuzugreifen. Diese Benutzer sollten stattdessen im Modus " **Inseln** " untergebracht sein, und Besprechungen werden zunächst nur den Benutzern gewährt, die noch nicht im Chat in Teams aktiv sind.

## <a name="who-should-consider-meetings-first"></a>Wer sollte Besprechungen zuerst berücksichtigen?

Besprechungen wurden zunächst für Organisationen entwickelt, die Skype for Business Server mit Enterprise-VoIP verwenden, die ihren Wechsel zu Teams-Besprechungen beschleunigen möchten, insbesondere für Personen mit starker IT-Disziplin, die einen verwalteten, deterministischen Upgrade-Pfad für Teams wünschen.

Für komplexe oder große Organisationen werden sprach Migrationen in der Regel auf der Grundlage von Websites durchgeführt, die möglicherweise lange dauern, potenziell mehrere Jahre, was zu erweiterten Koexistenz-Szenarien führt. Wenn sich die Koexistenz im Modus " **Inseln** " befindet, haben Benutzer immer die Wahl zwischen zwei Besprechungs Lösungen (Skype for Business und Teams), die zu verwirrenden oder suboptimalen Situationen führen können. Im Gegensatz zu sprach Migrationen können Besprechungs Migrationen im Allgemeinen innerhalb kürzester Zeit im gesamten Unternehmen durchgeführt werden. Organisationen, die so schnell wie möglich zu Teams-Besprechungen wechseln möchten (und ohne darauf zu warten, dass die Sprach Migration abgeschlossen ist), sollten zuerst Besprechungen in Frage stellen.

Besprechungen sind für Organisationen, die keine Enterprise-VoIP-Benutzer haben, zunächst möglicherweise nicht hilfreich. Diese Organisationen sollten in der Lage sein, **nur auf Teams** zu aktualisieren, sobald Sie in der Lage sind, Teambesprechungen zu übernehmen. Sie sollten zuerst Besprechungen überspringen.

Darüber hinaus sind Besprechungen zunächst hilfreich für Organisationen, deren Umfang eine reine Besprechungs Lösung ist, beispielsweise, wenn eine Ausschreibung "nur für Besprechungen" ausgestellt wird.

## <a name="capabilities-in-meetings-first"></a>Funktionen in Besprechungen zuerst

In der Besprechung werden zunächst die folgenden Funktionen zusammengeführt:

- [Bereitstellen eines Skype for Business Server-Benutzers (lokal)](https://docs.microsoft.com/microsoftteams/tutorial-audio-conferencing?tutorial-step=3) mit [Teams-Audiokonferenzen](tutorial-audio-conferencing.yml).
- [Migrationsdienst für Besprechungen](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms): die vom Benutzer organisierten Besprechungen werden in die Cloud migriert und in Teams-Besprechungen konvertiert, während der Benutzer zuerst zu Besprechungen heraufgestuft wird (erfordert Exchange Online).
- Optimierte Benutzererfahrung in Teams, zentriert auf Teams-Besprechungen und Teams und Kanäle (die optional mithilfe der [App-Berechtigungsrichtlinie](teams-app-permission-policies.md)ausgeblendet werden können) [Private Chats, Anrufe und selbst Anwesenheit von Teams](teams-client-experience-and-conformance-to-coexistence-modes.md) werden in Besprechungen nicht zuerst verfügbar gemacht, wodurch sich die Bereitstellung und Einführung in vollem Umfang auf Besprechungen konzentrieren kann.
- Überlegene [Teams-Besprechungs Erfahrung](tutorial-meetings-in-teams.yml).
- "Besser zusammen" zwischen Teams und Skype for Business: 
  - Automatischer Halt: Wenn Sie in einer Besprechung in Teams in einem Anruf in Skype for Business sind, wird die Teams-Besprechung in Wartestellung gesetzt, und umgekehrt. Dadurch wird verhindert, dass Benutzer private Anrufe von den Besprechungsteilnehmern über hören.
    ![Screenshot des Szenarios "besser zusammen" mit Teams und Skype for Business](media/meetings-first-better-together-hold.png)
  - Anwesenheits Abstimmung: die Aktivität in Teams spiegelt sich in der Anwesenheit des Benutzers wider, also bei der Anwesenheit von Skype for Business, da sich Chats und Anrufe in Skype for Business befinden. Insbesondere werden die Anwesenheitsinformationen für Besprechungen, in denen sich die ersten Benutzer in einer Teams-Besprechung befinden, entsprechend aktualisiert. Wenn der Bildschirm angezeigt wird, wird sein Anwesenheitsstatus auf "nicht stören" (basierend auf den Einstellungen in Skype for Business) aktualisiert.
  - Überprüfung des HID-Steuerelements für USB-Geräte (auch auf dem Mac verfügbar): die HID-Steuerelemente werden von Teams in Teams-Besprechungen und von Skype for Business unter allen anderen Umständen berücksichtigt.
  - Sofern nicht anders angegeben, erfordern die Funktionen für eine bessere Zusammenarbeit aktuelle Windows-Desktop Clients zu diesem Zeitpunkt.

## <a name="prerequisites-for-meetings-first"></a>Voraussetzungen für Besprechungen zuerst

Die einzigen harten Anforderungen für Besprechungen sind die gleichen wie die Anforderungen für Teams mit lokalem Active Directory und einer lokalen Bereitstellung von Skype for Business:

- [Allgemeine Voraussetzungen für Teams](upgrade-plan-journey-prerequisites.md), einschließlich
- [Identität und Authentifizierung in Teams](identify-models-authentication.md) und
- [Konfigurieren Sie Azure Active Directory für Teams und Skype for Business](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-azure-ad-connect).

Eine [Skype for Business-Hybrid Topologie](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-federation-with-skype-for-business-online) ist nicht erforderlich, wird jedoch empfohlen. Einige Funktionen wie der Migrationsdienst für Besprechungen und die Interoperabilität beruhen auf dieser Topologie.

Besprechungen werden zunächst mit einer beliebigen Version des Skype for Business-Servers unterstützt (und bekanntermaßen mit dem nicht mehr unterstützten lync-Server zusammenarbeiten). Es wird mit jedem unterstützten Skype for Business-Client unterstützt, doch für eine bessere Zusammenarbeit ist ein neuer Client erforderlich.

Sobald diese Anforderungen erfüllt sind (und nicht vor), können die Benutzer [für Office 365 und Teams lizenziert](https://docs.microsoft.com/office365/enterprise/assign-licenses-to-user-accounts)werden.

Für die ersten Erfahrungen mit den besten Besprechungen sollten Benutzer für [Exchange Online](exchange-teams-interact.md), [SharePoint Online und OneDrive for Business](sharepoint-onedrive-interact.md)sowie für die Erstellung von Office 365-Gruppen aktiviert sein. Besprechungen werden zunächst für Benutzer unterstützt, deren Postfach sich lokal in Exchange befindet oder für die keine SharePoint Online-oder OneDrive for Business-oder Office 365-Gruppenerstellung vorhanden ist. Ihre Erfahrung wird jedoch nicht so vollständig sein. Insbesondere für Organisationen, die Exchange Server lokal verwenden, gibt es möglicherweise (abhängig von der Version von Exchange Server) einige Einschränkungen beim Erstellen und Anzeigen von Besprechungen vom Team-Client sowie hinsichtlich der Compliance-Funktionen.

Benutzer müssen mindestens [für Teams lizenziert](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)sein. Darüber hinaus können Sie bei Bedarf für [Audiokonferenzen](set-up-audio-conferencing-in-teams.md)lizenziert werden.

Wir empfehlen, [den **SfBOnly** -oder **SfBWithTeamsCollab** ](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps) -Modus als Mandanten Standard zu dem Zeitpunkt zu gewähren, zu dem Sie die Benutzer lizenzieren. Auf diese Weise wird sichergestellt, dass Benutzer keine eigenen Teams im Standardmodus für **Inseln** verwenden, bevor Sie mit der ersten Besprechung beginnen.

Besprechungen werden zuerst auf vollständigen Desktop Clients (Windows und Mac), auf Browserclients und auf mobilen Clients unterstützt. Sie ist auch mit [Microsoft Teams-Räumen](https://docs.microsoft.com/microsoftteams/room-systems/)kompatibel. Für eine bessere Zusammenarbeit ist der vollständige Desktop Client erforderlich.

## <a name="prepare-for-teams-meetings-in-meetings-first"></a>Vorbereiten von Teambesprechungen in Besprechungen zuerst

Damit Ihre Benutzer die bestmögliche Erfahrung in Teambesprechungen haben, sollten Sie Folgendes tun:

- Führen Sie die Schritte in [Besprechungen und Konferenzen für Microsoft Teams](deploy-meetings-microsoft-teams-landing-page.md)aus, insbesondere.
- [Bewerten Sie Ihre Umgebung](3-envision-evaluate-my-environment.md).
- [Bereiten Sie das Netzwerk Ihrer Organisation für Microsoft Teams](prepare-network.md)vor.
- Aktualisieren Sie Ihre Besprechungsräume mit teamfähigen [Besprechungsraum Geräten und-Lösungen](https://docs.microsoft.com/skypeforbusiness/certification/devices-meeting-rooms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json), oder verwenden Sie [Cloud-Video-Interop für Microsoft Teams](cloud-video-interop.md) , damit Ihre vorhandenen Drittanbieter Räume und-Geräte an Teams-Besprechungen teilnehmen können.
- Rüsten Sie Ihre Benutzer mit [zertifizierten USB-Audio-und-Videogeräten](https://docs.microsoft.com/skypeforbusiness/certification/devices-usb-devices?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)aus.
- Vorbereiten der [Sensibilisierung und Akzeptanz für Teams-Besprechungen](adopt-microsoft-teams-landing-page.md)
- [Planen Sie Ihr Dienstmanagement](4-envision-plan-my-service-management.md).
- Machen Sie sich mit den reichen anrufanalyse Berichten vertraut, um eine [schlechte Anrufqualität zu beheben](use-call-analytics-to-troubleshoot-poor-call-quality.md).

In diesem Schritt sollten Sie in der Lage sein, ein Pilotprojekt mit mittlerer Serienreife zu führen.

## <a name="configure-users-for-meetings-first"></a>Benutzer für Besprechungen zuerst konfigurieren

Nachdem Sie Ihre Benutzer lizenziert und Ihre Organisation für Teams-Besprechungen vorbereitet haben, ist es an der Zeit, Ihre Benutzer zuerst für Besprechungen zu aktivieren. Wir haben es ganz einfach gemacht: eine einzige Einstellung bietet alles!

Alle Funktionen und Benutzeroberflächen in Besprechungen, einschließlich der Clientkonfiguration für Teams und der [automatischen Konformität](teams-client-experience-and-conformance-to-coexistence-modes.md) der Benutzeroberfläche, des Migrations Diensts für Besprechungen und besserer Zusammenarbeit, werden konfiguriert, indem der Benutzer (oder die Gruppe von Benutzern oder Mandanten Standard) der [SfBWithTeamsCollabAndMeetings-Koexistenzmodus](setting-your-coexistence-and-upgrade-settings.md) entweder im [Microsoft Teams Admin Center](manage-teams-in-modern-portal.md) oder mithilfe von [PowerShell](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)gewährt wird.

![Screenshot der Administratoreinstellungen, um zuerst Besprechungen zu aktivieren](media/teams-meeting-admin-settings.png)

Wenn Sie die Anwendung Teams und Kanäle aus der linken Navigationsleiste des Benutzer Teams-Clients ausblenden möchten, um Ihre Erfahrungen auf Besprechungen weiter zu konzentrieren, kann dies optional mit der APP- [Berechtigungsrichtlinie](teams-app-permission-policies.md)erreicht werden.

## <a name="reporting-and-call-analytics"></a>Berichterstellung und anrufanalyse

Berichterstellung und anrufanalyse für Teams-Besprechungen in Besprechungen werden in den anderen Modi nicht geändert.

## <a name="related-links"></a>Verwandte Links

Nachdem Sie diesen Artikel überprüft haben, möchten Sie möglicherweise weitere Informationen über [Ihre Upgrade-Reise](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md), [Migrations-und Interoperabilitäts Anleitungen](migration-interop-guidance-for-teams-with-skype.md)sowie die [Koexistenz mit Skype for Business](coexistence-chat-calls-presence.md) auswählen.


