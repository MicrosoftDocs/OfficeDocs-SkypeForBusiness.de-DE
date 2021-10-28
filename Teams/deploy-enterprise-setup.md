---
title: Einrichten von Microsoft Teams in Ihrem Unternehmen
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: Richten Sie Teams in Ihrem Unternehmen ein, damit Ihre Benutzer per Chat und Dateifreigabe zusammenarbeiten, kleine und große Besprechungen einrichten und daran teilnehmen sowie per Video und Sprache kommunizieren können.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: f05616de4f315cee115ee9767a52eea09297dfcf
ms.sourcegitcommit: 3a8bec0445cee5cd776fb1991f093a0ec4351852
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2021
ms.locfileid: "60605821"
---
# <a name="set-up-microsoft-teams-in-your-enterprise"></a>Einrichten von Microsoft Teams in Ihrem Unternehmen

Verwenden Sie die Informationen in diesem Artikel als Leitfaden, um Sie durch die Bereitstellung von Teams in Ihrer Organisation zu führen.

> [!NOTE]
> Wenn dies noch nicht geschehen ist, wird dringend empfohlen, die Bereitstellung von Teams mit einem Pilotprojekt zu beginnen. Ein Pilotprojekt ermöglicht es Ihnen und einigen Early Adoptern, sich vor der Planung und dem möglichen Rollout mit Teams und dessen Funktionen vertraut zu machen. Weitere Informationen zum Starten Ihres Pilotprojekts finden Sie unter [Erste Schritte mit Microsoft Teams](get-started-with-teams-quick-start.md).

Stellen Sie vor dem allgemeinen Rollout von Teams sicher, dass Ihre Organisation bereit ist, indem Sie die Punkte unter [Stellen Sie sicher, dass Sie bereit sind](get-started-with-teams-quick-start.md#make-sure-youre-ready) überprüfen.

## <a name="plan-your-deployment"></a>Planen Ihrer Bereitstellung

Bevor Sie mit der Bereitstellung von Teams beginnen, stellen Sie sicher, dass Sie den Planungsprozess abgeschlossen haben. Ihr Planungsprozess sollte Folgendes umfassen:

- Verstehen der Teams-Architektur
- Überprüfen und Verstehen von Teams-Workloads und ihrer Zusammenarbeit mit Microsoft 365
- Berechnete Netzwerkanforderungen und Sicherstellen, dass Ihr Netzwerk und die Internetverbindung über die erforderliche Hardware und Kapazität verfügen, um kritische Anforderungen, wie die Kommunikation in Echtzeit, zu erfüllen
- Verstehen der behördlichen und Compliance-Anforderungen für Informationen, die in Teams und anderen Microsoft 365-Diensten gespeichert sind
- Erstellen eines Einführungsplans, damit die Benutzer die Vorteile der Verwendung von Teams besser verstehen

Es wird dringend empfohlen, den [Advisor für Teams](https://admin.teams.microsoft.com/teams-deployment) zu verwenden, der Sie bei der Bereitstellung unterstützt. Details zur Funktionsweise des Advisor für Teams finden Sie unter [Verwenden von Advisor für Teams als Hilfe beim Rollout von Microsoft Teams](use-advisor-teams-roll-out.md).

> [!TIP]
> Erfahren Sie, wie Sie den Advisor für Teams verwenden können, um Sie bei der Planung Ihrer Teams-Bereitstellung zu unterstützen, indem Sie das Modul [Rollout mithilfe des Advisors für Teams](/learn/modules/m365-teams-rollout-using-advisor/) in Microsoft Learn abschließen.

Informationen zur Planung für Teams finden Sie unter [Teams – Übersicht über die Unternehmensbereitstellung](deploy-enterprise-overview.md).

## <a name="workloads"></a>Workloads

Es gibt viele Möglichkeiten zum Anpassen von Teams. In den folgenden Abschnitten wird gezeigt, wie Sie die einzelnen Teams-Arbeitslasten einrichten: **Chats, Teams und Kanäle**; **Besprechungen und Konferenzen**; und **Telefonanlage**. Die Reihenfolge, in der Sie die einzelnen Arbeitslasten einrichten, liegt bei Ihnen. Zwar empfehlen wir ihnen, zuerst die Chats, Teams und Kanäle für die Arbeitsauslastung eingerichtet zu haben, sie können aber mit Besprechungen und Konferenzen oder sogar mit dem Telefonsystem beginnen.

#### <a name="chat-teams-and-channels"></a>[Chat, Teams und Kanäle](#tab/ChatTeamsChannels)

Chats, Teams und Kanäle sind die Säulen von Teams. Der **Chat** ermöglicht es einem oder mehreren Benutzern, sich zu unterhalten, Dateien zu teilen und sich privat zu treffen. Mit **Teams**, das für alle Personen in Ihrer Organisation oder nur für die Teammitglieder sichtbar sein kann, können die richtigen Personen unabhängig von der Aufgabe oder dem Anlass zusammenarbeiten, ganz gleich, ob es um ein langes Projekt oder die Planung einer Geburtstagsfeier geht. **Kanäle** innerhalb von Teams können Themen, Projekte, Abteilungen oder alles andere segmentieren, was für Ihr Team sinnvoll ist. Details zu Chats, Teams und Kanälen finden Sie unter [Übersicht über Teams und Kanäle](teams-channels-overview.md).

> [!TIP]
> Schauen Sie sich an, wie Sie Teamrollen, Zugriff und Messagingrichtlinien verwalten können, indem Sie das Modul [Verwalten von Microsoft Teams](/learn/modules/m365-teams-collab-manage-teams/) in Microsoft Learn abschließen.

### <a name="administration-and-team-ownership"></a>Verwaltung und Besitzrechte im Team

| Entscheidung | Beschreibung |
|--|--|
| Wer sollte Teams-Administrator sein? | Administratorrollen können verwendet werden, um Personen, die Teams verwalten möchten, bestimmte Berechtigungen zu erteilen. Kleine Unternehmen benötigen diese zusätzlichen Rollen möglicherweise nicht, da dieselbe Person möglicherweise für alle Aspekte von Teams verantwortlich ist. Sie können Mitglieder später jederzeit hinzufügen oder entfernen.<p>[Verwenden von Teams-Administratorrollen zum Verwalten von Microsoft Teams](using-admin-roles.md) |
| Wer sollte Team-Besitzer und -mitglieder sein? | Teambesitzer steuern, wer auf ein Team und dessen Kanäle zugreifen kann. Sie können entscheiden, ob ein Team oder Kanal öffentlich (für die Organisation) oder privat ist, und Richtlinien einrichten, z. B. ob ein Kanal moderiert werden soll. Mitglieder können auf das Team und dessen Kanäle zugreifen (sofern kein Kanal auf "Privat" festgelegt ist und sie kein Mitglied dieses Kanals sind) und können als Moderatoren festgelegt werden.<p>[Zuweisen von Teambesitzern und -mitgliedern in Microsoft Teams](assign-roles-permissions.md) |

### <a name="default-settings-and-lifecycle-policies"></a>Standardeinstellungen und Lebenszyklusrichtlinien

| Entscheidung | Beschreibung |
|--|--|
| Welche Messagingrichtlinien sollten angewendet werden? | Messagingrichtlinien steuern, welche Features für Chat- und Kanalnachrichten (z. B. wer den Chat verwenden kann, wer gesendete Nachrichten bearbeiten und löschen kann und so weiter) für Benutzer in Teams zur Verfügung stehen. Teams hat eine globale Richtlinie, die für jeden gilt. Alle Features der globalen Richtlinie sind standardmäßig auf **An** festgelegt.<p>Wenn für alle dieselbe Richtlinie gelten soll, müssen Sie nur Änderungen an dieser globalen Richtlinie vornehmen (z. B. Deaktivieren der Unterstützung von Memes in Unterhaltungen).<p>Wenn Sie unterschiedliche Richtlinien für unterschiedliche Personengruppen (z. B. eine Richtlinie für Büroarbeiter und eine weitere für Fabrikarbeiter) wünschen, können Sie Richtlinien erstellen und zuweisen. Wenn Sie einem Benutzer eine Richtlinie zuweisen, gilt die globale Richtlinie nicht mehr für diesen Benutzer.<p>[Verwalten von Messaging-Richtlinien in Teams](messaging-policies-in-teams.md) |
| Welche Teameinstellungen sollen angewendet werden? | Mithilfe der Teams-Einstellungen können Sie für Ihre Teams Funktionen wie E-Mail-Integration, Cloud-Speicheroptionen, die Organisationsregisterkarte, das Einrichten von Geräten in Besprechungsräumen und den Suchbereich einrichten. Wenn Sie Änderungen an diesen Einstellungen vornehmen, betreffen sie alle Teams in Ihrer Organisation.<p>[Teams-Einstellungen](enable-features-office-365.md#teams-settings)  |

### <a name="external-and-guest-access"></a>Externer und Gastzugriff

| Entscheidung | Beschreibung |
|--|--|
| Sollte der externe Zugriff aktiviert sein? | Über den externen Zugriff kann jeder in einer anderen Organisation mit Personen in Ihrer Organisation sprechen. Dies ist nützlich, wenn Sie in enger Beziehung zu einer anderen Organisation, z. B. einem Lieferanten, stehen und es den Personen in einer Organisation ermöglichen möchten, miteinander zu chatten, Besprechungen zu halten und so weiter.<p>Der externe Zugriff ist anders als der Gastzugriff. Über den externen Zugriff erhält jeder in einer Organisation Zugriff auf die Interaktion mit Personen in Ihrer Organisation. Beim Gastzugriff werden bestimmte Personen zur Interaktion mit Personen in Ihrer Organisation eingeladen.<p>Der externe Zugriff ist standardmäßig **Aus**.<p>[Verwaltung des externen Zugriffs in Microsoft Teams](manage-external-access.md)  |
| Sollte der Gastzugriff aktiviert sein? |Mithilfe eines Gastzugriffs können Personen in Ihrer Organisation Personen außerhalb Ihrer Organisation dazu einladen, auf Ihr Teams und Ihre Kanäle zuzugreifen. Der Gastzugriff wird häufig verwendet, um mit Personen außerhalb Ihrer Organisation zusammenzuarbeiten, die keine formelle Beziehung mit Ihrer Organisation haben. So könnten Sie beispielsweise einen Projektplaner vorübergehend zur Arbeit an einem Projekt einladen.<p>Der Gastzugriff ist anders als der externe Zugriff. Beim Gastzugriff werden bestimmte Personen zur Interaktion mit Personen in Ihrer Organisation eingeladen. Über den externen Zugriff erhält jeder in einer anderen Organisation Zugriff auf die Interaktion mit Personen in Ihrer Organisation. <p>Der Gastzugriff ist standardmäßig **Aus**. <p>[Aktivieren oder Deaktivieren des Gastzugriffs auf Microsoft Teams](set-up-guests.md)  |

#### <a name="meetings-and-audio-conferencing"></a>[Besprechungen und Audiokonferenzen](#tab/MeetingsAudioConferencing)

Besprechungen und Konferenzen ermöglichen es Personen in Ihrer Organisation, sich untereinander und mit Personen außerhalb Ihrer Organisation zu treffen. Jede Person mit einem Teams- oder Skype for Business-Client kann an **Besprechungen** teilnehmen, zu denen sie eingeladen wurde. Mithilfe des Mikrofons, der Kamera und des Bildschirms ihres Geräts können die Teilnehmer an der Unterhaltung teilnehmen, ohne ein Telefon zu benötigen. Teilnehmer können chatten, Sprachanrufe tätigen und Video und Apps mit anderen Teilnehmern über einen PC oder ein mobiles Gerät teilen.

**Audiokonferenzen** ermöglicht es Teilnehmern, über ein normales Telefon an Besprechungen teilzunehmen, indem sie eine Konferenztelefonnummer anrufen und eine Besprechungs-ID eingeben. Audiokonferenzen sind nützlich, wenn ein Teilnehmer nicht über eine gute Internetverbindung verfügt, die Besprechung nur per Sprache stattfindet oder er wegen einem anderen Umstand nicht über den Teams-Client teilnehmen kann.

> [!TIP]
> Machen Sie sich mit Besprechungen und Ereignissen vertraut, indem Sie das Modul [Besprechungen, Konferenzen und Ereignisse mit Microsoft Teams verwalten](/learn/modules/m365-teams-collab-manage-meetings) in Microsoft Learn abschließen.

### <a name="meetings"></a>Besprechungen

| Entscheidung | Beschreibung |
|--|--|
| Welche organisationsweiten Besprechungseinstellungen angewendet werden sollen| Besprechungsrichtlinien steuern, welche Besprechungsfeatures für Besprechungsorganisatoren und -teilnehmer zur Verfügung stehen. Sie können steuern, ob anonyme Teilnehmer an Besprechungen teilnehmen, Besprechungseinladungen anpassen, die Handhabung von Medien in Echtzeit steuern und mehr können. Wenn Sie Änderungen an diesen Einstellungen vornehmen, betreffen sie alle Besprechungen in Ihrer Organisation. <p>[Verwalten von Besprechungseinstellungen in Microsoft Teams](meeting-settings-in-teams.md)|
| Welche Besprechungsrichtlinien sollten angewendet werden? | Besprechungsrichtlinien werden verwendet, um die Features zu steuern, die Besprechungsteilnehmern für Besprechungen, die von Benutzern in Ihrer Organisation geplant werden, zur Verfügung stehen. Sie können steuern, ob Benutzer private Besprechungen planen, die Option "Jetzt besprechungen" aktivieren, das Aufzeichnen von Besprechungen zulassen und so weiter. Teams hat eine globale Richtlinie, die für jeden gilt.<p> Wenn für alle dieselbe Richtlinie gelten soll, müssen Sie nur Änderungen an dieser globalen Richtlinie vornehmen (z. B. Deaktivieren der Aufzeichnung von Besprechungen). <p>Wenn Sie unterschiedliche Richtlinien für unterschiedliche Personengruppen (z. B. eine Richtlinie für Büroarbeiter und eine weitere für leitende Angestellte) wünschen, können Sie Richtlinien erstellen und zuweisen. Wenn Sie einem Benutzer eine Richtlinie zuweisen, gilt die globale Richtlinie nicht mehr für diesen Benutzer.<p> [Verwalten von Besprechungsrichtlinien in Teams](meeting-policies-overview.md)|
| Möchten Sie die Aufzeichnung und Archivierung von Besprechungen zulassen?| Besprechungsorganisatoren können Besprechungen in der Cloud aufzeichnen und archivieren. Sie können Besprechungsaufzeichnung und -archivierung mithilfe von Besprechungsrichtlinien aktivieren oder deaktivieren.<p> [Aufzeichnung einer Teams-Cloudbesprechung](cloud-recording.md) |

### <a name="audio-conferencing"></a>Audiokonferenz

| Entscheidung | Beschreibung |
|--|--|
| Möchten Sie Videointeroperabilität mit Lösungen von Drittanbietern einrichten?| Durch die Interoperabilität mit Cloudvideos können Drittanbieter-Telepresence- und private Videogeräte an Teams-Besprechungen teilnehmen. Wenn Sie bereits in Videokonferenzen und private Videogeräte investiert haben, können Sie die Videointeroperabilität verwenden, um diese Geräte in Teams zu integrieren.<p> [Cloud-Video-Interoperabilität für Microsoft Teams](cloud-video-interop.md)|
| Welche organisationsweiten Audiokonferenzeinstellungen sollten angewendet werden?| Mit den Einstellungen für Audiokonferenzen können Sie steuern, wie sich Teilnehmer per Telefon in Besprechungen einrufen. Sie können die Länge der zum Teilnehmen an Besprechungen erforderlichen PINs festlegen, Konferenz-IDs zurücksetzen, das Senden von Audiokonferenzinformationen an Teilnehmer aktivieren oder deaktivieren und so weiter. Änderungen an den Einstellungen für Audiokonferenzen gelten für alle Benutzer in Ihrer Organisation.<p>[Verwalten der Audiokonferenz-Einstellungen für Ihre Organisation in Microsoft Teams](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md). |
| Müssen Besprechungsorganisatoren ein Ziel anwählen?| Kommunikationsgutschriften werden verwendet, wenn Sie von einer Audiokonferenzkonferenz Telefonnummern außerhalb Ihrer Organisation anrufen. Sie müssen genügend Kommunikationsgutschriften erwerben, um sicherzustellen, dass sie ihnen während der Audiokonferenzanrufe nicht ausgehen.<p>Einige Audiokonferenzabonnements umfassen möglicherweise ausgehende Anrufe. Die Details hierzu finden Sie in Ihren Abonnementinformationen.<p> [Einrichten von Guthaben für Kommunikationen für Ihre Organisation](set-up-communications-credits-for-your-organization.md)|
| Welche Einschränkungen für ausgehende Anrufe sollten angewendet werden?| Sie können die Steuerelemente für ausgehende Anrufe verwenden, um den Typ der Audiokonferenzanrufe einzuschränken, die von Benutzern in Ihrer Organisation gemacht werden können. Beispielsweise können Sie steuern, ob Besprechungen internationale Telefonnummern anrufen, ausgehende Anrufe überhaupt tätigen, nur in bestimmte Länder oder Regionen anrufen können und so weiter.<p>[Einschränkungsrichtlinien für ausgehende Anrufe für Audiokonferenzen und PSTN-Anrufe](outbound-calling-restriction-policies.md) |
| Möchten Sie ändern, wie gewählte Telefonnummern von Teams interpretiert werden? | Mithilfe von Einwahlplänen können Sie steuern, wie Telefonnummern interpretiert werden. So können Sie beispielsweise festlegen, welche Nummer zu wählen ist, um eine externe Rufnummer zu erreichen, die Handhabung von Telefonerweiterungen steuern, ein Präfix festlegen, damit eine Durchwahl in eine vollständige Telefonnummer übersetzt wird und so weiter.<p> [Erstellen und Verwalten von Wählplänen](create-and-manage-dial-plans.md) |
| Möchten Sie Liveereignisse aktivieren? | Liveereignisse können Video- und Besprechungsinhalte an große Zielgruppen übertragen. Wenn Sie Liveereignisse aktivieren, können Sie Richtlinien für diese Ereignisse festlegen, um deren Verwendung zu steuern. Sie können z. B. die URL-Teilnehmer konfigurieren, die für den Support verwendet werden sollen, einen Videoverteilungsanbieter (sofern sie über einen Drittanbieter verfügen) und so weiter. Teams hat eine globale Richtlinie, die für jeden gilt.<p>Wenn für alle dieselbe Richtlinie gelten soll, müssen Sie nur Änderungen an dieser globalen Richtlinie vornehmen. <p>Wenn Sie unterschiedliche Richtlinien für unterschiedliche Personengruppen (z. B. eine Richtlinie für Büroarbeiter und eine weitere für leitende Angestellte) wünschen, können Sie Richtlinien erstellen und zuweisen. Wenn Sie einem Benutzer eine Richtlinie zuweisen, gilt die globale Richtlinie nicht mehr für diesen Benutzer.<p> [Einrichten von Live-Ereignissen in Microsoft Teams](teams-live-events/set-up-for-teams-live-events.md) |

#### <a name="phone-system-and-pstn-connectivity"></a>[Telefonsystem und PSTN-Konnektivität](#tab/PhoneSystem)

Mit dem Telefonsystem können Sie Ihr vorhandenes lokales Telefonsystem durch eine Reihe von Funktionen ersetzen, die über Microsoft 365 bereitgestellt werden und die eng in Ihre Cloudlösung integriert sind.

| Entscheidung | Beschreibung |
|--|--|
| Möchten Sie Ihre lokale Telefonanlage ersetzen? | Telefonsystem einrichten, automatische Telefonanrufe konfigurieren, Anrufpläne, Anrufwarteschlangen und so weiter. <p> [Einrichten des Telefonsystems in Ihrer Organisation](setting-up-your-phone-system.md)|
| Möchten Sie Richtlinien für Cloud-Voicemail festlegen?| Sie können steuern, welche Cloud-Voicemailfeatures Ihren Benutzern zur Verfügung stehen und wie sie funktionieren. Sie können beispielsweise die Voicemailabschrift für Ihre gesamte Organisation aktivieren oder deaktivieren, die Profanitätsmaske für bestimmte Benutzer aktivieren oder deaktivieren und so weiter.<p> [Einrichten von Cloudvoicemail](set-up-phone-system-voicemail.md) |
| Möchten Sie dynamische Notrufe aktivieren?| Sie können Netzwerkeinstellungen konfigurieren, Notrufadressen an Standorte zuweisen und so weiter. Mit dynamischen Notfallanrufen können Sie eine Standortkarte basierend auf Netzwerkeinstellungen und anderen Metadaten konfigurieren, um festzulegen, wohin Notfallmitarbeiter für den Fall gesendet werden, dass ein Benutzer einen Notruf abgibt.<p>[Planen und Konfigurieren dynamischer Notrufe](configure-dynamic-emergency-calling.md) |
| Möchten Sie das Verhalten der Anrufer-ID anpassen? | Standardmäßig ist die Telefonnummer, die bei einem Anruf eines Teams-Benutzers angezeigt wird, die Telefonnummer des Benutzers. Sie können dies in die Hauptnummer des Unternehmens ändern, die Telefonnummer blockieren, die Nummer anonymisieren oder in eine andere Dienstnummer ändern. Teams hat eine globale Richtlinie, die für jeden gilt.<p>Wenn für alle dieselbe Richtlinie gelten soll, müssen Sie nur Änderungen an dieser globalen Richtlinie vornehmen. <p>Wenn Sie unterschiedliche Richtlinien für unterschiedliche Personengruppen (z. B. eine Richtlinie für Büroarbeiter und eine weitere für leitende Angestellte) wünschen, können Sie Richtlinien erstellen und zuweisen. Wenn Sie einem Benutzer eine Richtlinie zuweisen, gilt die globale Richtlinie nicht mehr für diesen Benutzer.<p> [Verwalten von Anrufer-ID-Richtlinien in Microsoft Teams](caller-id-policies.md). |

---

## <a name="security"></a>Sicherheit

Teams wurde in Übereinstimmung mit dem [Microsoft Security Development Lifecycle (SDL)](https://www.microsoft.com/sdl/default.aspx) konzipiert und entwickelt. Um die Konformität mit dem SDL zu gewährleisten, integriert Teams Sicherheitstechnologien nach Industriestandard als grundlegenden Teil seiner Architektur, darunter:

- Entwerfen von Bedrohungsmodellen, deren Features dann in Bezug auf Folgendes getestet werden:
- Einbindung sicherheitsrelevanter Verbesserungen in den Kodierungsprozess und -praktiken
- Erstellung von Build-Time-Tools zur Erkennung von Pufferüberläufen und anderen potenziellen Sicherheitsbedrohungen, bevor Code in das Produkt eingecheckt werden kann

Obwohl Teams eine "Trustworthy by Design"-Methodik verfolgt, ist es unmöglich, gegen alle unbekannten Sicherheitsbedrohungen zu entwickeln. Aus diesem Grund ist es wichtig zu verstehen, wie Teams arbeitet und mit anderen Systemen interagiert. Darüber hinaus ist es wichtig zu verstehen, wie häufig verwendete Bedrohungen wie IP-Adressen-Spoofing, Denial-of-Service-Angriffe, Man-in-the-Middle-Angriffe usw. funktionieren, damit Sie Ihr Netzwerk und die Konfiguration Ihres Teams so gestalten können, dass die Wahrscheinlichkeit dieser Angriffe verringert wird.

Um zu verstehen, wie Teams die Grundlagen der Sicherheit in den Entwurf integriert, und um sich über weitere häufige Bedrohungen zu informen, lesen Sie [Security und Microsoft Teams](teams-security-guide.md).

## <a name="compliance"></a>Compliance

Teams und Microsoft 365 stellen zahlreiche Tools zur Verfügung, mit deren Hilfe Sie die gesetzlichen Vorschriften ihres Unternehmens und Ihrer Benutzer erfüllen können. In den folgenden Artikeln finden Sie Informationen zum Konfigurieren der einzelnen Compliancefeatures in Teams:

| Feature | Beschreibung|
|-|-|
| [Informationsbarrieren](information-barriers-in-teams.md)| Verhindert, dass Einzelpersonen oder Gruppen miteinander kommunizieren oder sich in der Benutzerauswahl suchen können.|
| [Aufbewahrungsrichtlinien](retention-policies.md)| Mit dieser Option können Sie steuern, wie lange Daten in Teams aufbewahrt werden sollen oder ob Daten nach einem bestimmten Zeitraum entfernt werden müssen.|
| [Kommunikationscompliance](communication-compliance.md)| Hilft bei der Reduzierung von Kommunikationsrisiken, indem es beleidigende, profane und belästigende Sprache, rassistische und blutige Bilder für Erwachsene und die Weitergabe sensibler Informationen identifiziert und Maßnahmen dagegen ergreift. |
| [Richtlinienbasierte Aufzeichnung für Anrufe & Besprechungen](teams-recording-policy.md)| Hiermit können Sie steuern, wann oder ob Anrufe und Besprechungen automatisch aufgezeichnet und für spätere Verarbeitung, Aufbewahrung oder Analyse gespeichert werden sollen.|
| [Vertraulichkeitsbezeichnungen](sensitivity-labels.md)| Hilft Ihnen dabei, den Zugriff auf vertrauliche Informationen zu schützen und zu regulieren, indem Sie Bezeichnungen erstellen, mit denen ausgewählte Datenschutzoptionen erzwungen werden.|
| [Verhinderung von Datenverlust](/microsoft-365/compliance/dlp-microsoft-teams?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json)| Ermöglicht es Ihnen, Regeln zu erstellen, mit denen festgelegt wird, wie bestimmte Informationen wie Sozialversicherungsnummern, Kreditkartennummern und so weiter verarbeitet werden sollen. Sie können das Senden bestimmter Informationen verhindern, verhindern, dass diese Ihre Organisation verlassen, und so weiter.|
| [eDiscovery](eDiscovery-investigation.md)| Hilft Ihnen bei der Suche nach und dem Abrufen von Inhalten in Ihrem Unternehmen, wenn Ihr Unternehmen Discovery-Anforderungen in Gerichtsverfahren erhält. |
| [Gesetzliche Aufbewahrungspflicht](legal-hold.md)| Hilft Ihnen bei der Aufbewahrung von Informationen in Ihrer Organisation, auch wenn sie von einem Benutzer gelöscht werden, wenn dies während rechtlicher Verfahren erforderlich ist, damit sie während eDiscovery-Untersuchungen gefunden werden können. |
| [Inhaltssuche](content-search.md)| Bietet einen Weg, um Microsoft Teams-Informationen abzurufen. Die Abfragen schließen Exchange, SharePoint Online und OneDrive for Business ebenfalls ein.|
| [Auditing](audit-log-events.md)| Hiermit können Sie Informationen zu einer bestimmten Aktion anzeigen, einschließlich der Angaben, wer die Aktion ausgeführt hat, wann die Aktion ausgeführt wurde, welche IP-Adresse verwendet wurde, und so weiter. Zu den Aktionen gehören das Erstellen oder Löschen von Teams, die Erstellung von Kanälen, geänderte Einstellungen in Teams und so weiter.|
| [Kundenschlüssel](/microsoft-365/compliance/customer-key-tenant-level?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json)| Ermöglicht ihnen das Erstellen einer Datenverschlüsselungsrichtlinie mithilfe von Verschlüsselungsschlüsseln, die Sie bereitstellen.|

## <a name="clients"></a>Clients

Wenn Sie bereit sind, Teams für Ihre Benutzer zu verwenden, können sie den Teams-Client auf ihrem Windows-, Mac- oder Linux-PC oder aber auf ihrem Android- oder iOS-Gerät installieren. Benutzer können den Teams-Client direkt von <https://teams.microsoft.com/downloads> herunterladen.

Stellen Sie sicher, dass jeder, der Teams verwenden wird, über eine Teams-Lizenz verfügt. Weitere Informationen zum Zuweisen einer Teams-Lizenz finden Sie unter [Verwalten des Benutzerzugriffs auf Teams](user-access.md#using-the-microsoft-365-admin-center).

> [!TIP]
> Erhalten Sie Empfehlungen zur Planung der Bereitstellung Ihrer Teams-Clientbereitstellung, indem Sie das Modul [Bereitstellen von Microsoft Teams-Clients](/learn/modules/m365-teams-collab-deploy-clients/) Microsoft Learn abschließen.

Wenn Ihre Organisation Microsoft Endpoint Configuration Manager, Gruppenrichtlinien oder einen Verteilungsmechanismus eines Drittanbieters verwendet, finden Sie Informationen zum Bereitstellen von Software auf den Computern ihrer Benutzer unter [Installieren von Microsoft Teams mithilfe von Microsoft Endpoint Configuration Manager](msi-deployment.md).

Detaillierte Informationen zum Bereitstellen von Teams-Clients finden Sie unter [Erhalten von Clients für Microsoft Teams](get-clients.md).

## <a name="training"></a>Schulung

Informationen dazu, wie Sie Ihre Benutzer und Administratoren in der Nutzung von Teams schulen, finden Sie unter [Microsoft Teams-Schulung](training-microsoft-teams-landing-page.md).