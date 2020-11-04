---
title: Übersicht über Sicherheit und Compliance
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: anwara
audience: admin
description: Eine Übersicht über die Sicherheits-und Compliance-Features von Microsoft Teams, einschließlich Datenschutz und Verschlüsselung, Überwachung und Berichterstellung und vieles mehr.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- remotework
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.securityandcompliance
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 29b01d7418a194233f3205502134645526351dc4
ms.sourcegitcommit: 43dc627e9fef31a2508f54acf741000551ff68b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2020
ms.locfileid: "48878489"
---
# <a name="security-and-compliance-in-microsoft-teams"></a>Sicherheit und Compliance in Microsoft Teams

> [!IMPORTANT]
> Wenn Sie wissen möchten, wie Sie die Sicherheit am besten gewährleisten können, **während alle während des COVID-19-Ausbruchs von zu Hause aus arbeiten** , lesen Sie diese Artikel:
>  - [Die wichtigsten 12 Aufgaben für Sicherheitsteams zur Unterstützung der Arbeit von zu Hause aus](https://docs.microsoft.com/microsoft-365/security/top-security-tasks-for-remote-work)
>  - [Optimieren der Microsoft 365- oder Office 365-Konnektivität für Remotebenutzer mithilfe des geteilten VPN-Tunnels](https://docs.microsoft.com/Office365/Enterprise/office-365-vpn-split-tunnel)
>  - Aktualisiert am 2. April 2020: [Sicherheitsleitfaden für Teams](teams-security-guide.md)


Microsoft Teams basiert auf der Hyper-Scale-Cloud von Microsoft 365 und Office 365, die die fortschrittlichen Sicherheits-und Compliance-Funktionen liefert, die unsere Kunden erwarten. Weitere Informationen zum Planen der Sicherheit in Microsoft 365 oder Office 365, ist [die Sicherheits](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap) Planung ein guter Ausgangspunkt. Weitere Informationen zum Planen der Kompatibilität in Microsoft 365 oder Office 365 finden Sie im Artikel [Plan für Sicherheit und Compliance](https://docs.microsoft.com/microsoft-365/compliance/plan-for-security-and-compliance) .


In diesem Artikel finden Sie weitere Informationen zu Teams-spezifischer Sicherheit und-Compliance. Lassen Sie sich diese Microsoft Mechanics-Videos zur Sicherheit und Compliance nicht entgehen:

- [Microsoft Teams Essentials für IT: Sicherheit und Compliance](https://youtu.be/91lHNKVVvQ4) (12:42 min)
- [Microsoft Teams-Steuerelemente für Sicherheit und Compliance](https://www.youtube.com/watch?v=Km4T4hMM__k) (10:54 min)

> [!IMPORTANT]
> Als Kunde von Microsoft 365 oder Office 365 besitzen und Steuern Sie Ihre Daten. Microsoft verwendet Ihre Daten nicht für etwas anderes als die Bereitstellung des von Ihnen abonnierten Diensts. Als Dienstanbieter scannen wir Ihre e-Mails, Dokumente oder Teams nicht für Werbung oder für Zwecke, die nicht Dienst bezogen sind. Microsoft hat keinen Zugriff auf Hochgeladene Inhalte. Wie OneDrive und SharePoint in Microsoft 365 bleiben Kundendaten im Mandanten. Weitere Informationen zu unseren Vertrauens-und sicherheitsrelevanten Informationen finden Sie im [Microsoft Trust Center](https://microsoft.com/trustcenter). Microsoft Teams folgt den gleichen Leitlinien und Prinzipien wie das Microsoft Trust Center.

## <a name="security"></a>Sicherheit

Teams erzwingt teamübergreifende und organisationsweite zweistufige Authentifizierung, einmaliges Anmelden über Active Directory und Verschlüsselung von Daten in der Übertragung und im Ruhezustand. Dateien werden in SharePoint gespeichert und mit dem entsprechenden SharePoint-Mechanismus verschlüsselt. Notizen werden in OneNote gespeichert und mit dem entsprechenden OneNote-Mechanismus verschlüsselt. Die OneNote-Daten werden auf der SharePoint-Website des Teams gespeichert. Die Registerkarte "wiki" kann auch zum Aufzeichnen von Notizen verwendet werden, und der zugehörige Inhalt wird auch auf der SharePoint-Teamwebsite gespeichert.

Lesen Sie [Identitäts Modelle und Authentifizierung](identify-models-authentication.md) , um mehr Einblicke in Authentifizierung und Teams zu erhalten und zu erfahren, [wie moderne](sign-in-teams.md) Authentifizierungsfunktion insbesondere bei der modernen Authentifizierung hilft.

Da Teams in Partnerschaft mit SharePoint, OneNote, Exchange und mehr arbeiten, sollten Sie die Sicherheit in Microsoft 365 oder Office 365 vollständig verwalten. Weitere Informationen finden Sie unter [Konfigurieren Ihrer Microsoft 365-oder Office 365-Organisation für mehr Sicherheit](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).

> [!NOTE]
> Derzeit unterstützt [privater Kanal](private-channels.md) begrenzte Sicherheits-und Compliance-Funktionen. Die Unterstützung für den vollständigen Satz von Sicherheits-und Compliance-Features in privaten Kanälen wird in Kürze verfügbar sein.

### <a name="advanced-threat-protection-atp"></a>Erweiterter Bedrohungsschutz (ATP)

Advanced Threat Protection (ATP) steht für Microsoft Teams zusammen mit SharePoint und OneDrive, Anwendungen, die in Teams für Content Management integriert sind, zur Verfügung. Mit ATP können Sie feststellen, ob Inhalte in diesen Anwendungen bösartig sind und diesen Inhalt vom Benutzer Zugriff blockieren.

Wie der betroffene Inhalt nach der Erkennung verwaltet wird, entspricht den Einstellungen, die Sie in Microsoft 365 oder Office 365 ausgewählt haben. Wir empfehlen Ihnen dringend, alle Anwendungen in Bezug auf die Konfiguration von ATP zu bedenken, und für die weitere Lektüre finden Sie im Artikel [ATP für SharePoint, OneDrive und Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams) detaillierte Informationen zu den ersten Schritten.

### <a name="safe-links"></a>Sichere Links

Während derzeit in Microsoft Teams keine sicheren Links für Advanced Threat Protection (ATP) verfügbar sind, befinden Sie sich jetzt in der [öffentlichen Vorschau](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links-for-teams?view=o365-worldwide) über unser Technologie Adoptionsprogramm (Tap), und während ein Veröffentlichungsdatum für die allgemeine Verfügbarkeit nicht festgesetzt wird, werden wir diesen Artikel aktualisieren, wenn dieser Zeitpunkt eintrifft. In der Zwischenzeit finden Sie Informationen zu den sicheren Links für Microsoft 365 oder Office 365 über die [ATP-Sicherheits Links](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links#how-to-get-atp-safe-links-protection). ATP-sichere Links sind sowohl in [ATP Plan 1 als auch in ATP Plan 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide)verfügbar.

### <a name="safe-attachments"></a>Sichere Anlagen

Sichere Anlagen ist ein Feature, das zur Verbesserung der Benutzersicherheit dient, indem schädliche Anlagen überprüft und erkannt werden. Global-oder Sicherheitsadministratoren erstellen [Richtlinien](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-atp-safe-attachments-policies?view=o365-worldwide) für die Behandlung dieser mutmaßlichen schädlichen Anlagen, um zu verhindern, dass Sie an Benutzer gesendet, geklickt und gehandelt werden. Der sichere Anlagenschutz steht für SharePoint, OneDrive und Microsoft Teams sowie für Microsoft 365 oder Office 365 [Advanced Threat Protection Plan 1 und 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) zur Verfügung. Lesen Sie mehr über sichere Anlagen und wie Sie [hier](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-attachments?view=o365-worldwide)helfen können, Ihre Organisation zu schützen.

### <a name="how-conditional-access-policies-work-for-teams"></a>Funktionsweise von bedingten Zugriffsrichtlinien für Teams

Microsoft Teams ist in hohem Maße auf Exchange Online, SharePoint und Skype for Business Online für Kern Produktivitätsszenarien wie Besprechungen, Kalender, Interop-Chats und Dateifreigabe angewiesen. Richtlinien für bedingten Zugriff, die für diese Cloud-Apps festgelegt wurden, gelten auch für Microsoft Teams, wenn sich Benutzer direkt bei Microsoft Teams anmelden – unabhängig vom Client.

Microsoft Teams wird separat als Cloud-App in Azure Active Directory-Richtlinien für bedingten Zugriff unterstützt. Richtlinien für bedingten Zugriff, die für die Microsoft Teams-Cloud-App festgelegt wurden, gelten auch für Microsoft Teams, wenn sich Benutzer anmelden. Ohne die richtigen Richtlinien für andere apps wie Exchange Online und SharePoint können Benutzer jedoch weiterhin direkt auf diese Ressourcen zugreifen. Weitere Informationen zum Einrichten einer Richtlinie für den bedingten Zugriff im Azure-Portal finden Sie unter: [Azure Active Directory-Schnellstart](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started).

Microsoft Teams-Desktopclients für Windows und Mac unterstützen moderne Authentifizierung. Moderne Authentifizierung ermöglicht plattformübergreifend die Anmeldung auf der Grundlage von ADAL (Azure Active Directory Authentication Library, Active Directory-Authentifizierungsbibliothek) in Microsoft Office-Clientanwendungen.

Die Microsoft Teams-Desktopanwendung unterstützt AppLocker.  Weitere Informationen zu AppLocker-Voraussetzungen finden Sie unter Voraussetzungen für die Verwendung von [AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/requirements-to-use-applocker).

## <a name="compliance"></a>Compliance

Teams verfügt über eine breite Palette von Informationen, die Ihnen bei Compliance-Bereichen behilflich sein können, einschließlich der Kommunikations Konformität für Kanäle, Chats und Anlagen, Aufbewahrungsrichtlinien, Datenverlust Schutz (DLP), eDiscovery und rechtliche Aufbewahrung für Kanäle, Chats und Dateien, Überwachungsprotokoll Suche sowie Verwaltung mobiler Anwendungen mit Microsoft InTune. Wir haben einige Informationen zu den folgenden Themen bereitgestellt, und Sie können zum [Microsoft 365 Compliance Center](https://compliance.microsoft.com) wechseln, um diese Einstellungen zu verwalten.

### <a name="information-barriers"></a>Informationsbarrieren

Bei Informationsbarrieren handelt es sich um Richtlinien, die von Teams-Administratoren in die Tat umgestellt werden, um Personen oder Gruppen zu unterhalten, miteinander zu kommunizieren (wenn dies für Sie nicht erforderlich ist, oder ein regulatorischer Grund, um Sie davon zu blockieren), und Sie können auch Richtlinien in Bezug auf Suchvorgänge und eDiscovery (nachstehend behandelt) erstellen. Diese Richtlinien können sich auf Benutzer in 1:1-Chats, Gruppen-Chats oder auf Teamebene auswirken.

Weitere Informationen zu diesem Thema finden Sie unter [Informationsbarrieren in Microsoft Teams](information-barriers-in-teams.md).

### <a name="communication-compliance"></a>Kommunikations Konformität

Mit der Kommunikations Kompatibilität in Microsoft 365 können Sie Benutzer zu in-Scope-Richtlinien hinzufügen, die für die Untersuchung von Microsoft Teams-Kommunikationen für anstößige Sprache, vertrauliche Informationen und Informationen im Zusammenhang mit internen und behördlichen Standards konfiguriert werden können. Chat-Kommunikation und zugehörige Anlagen sowohl in öffentlichen als auch privaten Teams-Kanälen, einzelnen Chats und Anlagen können gescannt werden, um Kommunikationsrisiken in Ihrer Organisation zu minimieren. Weitere Informationen dazu, wie Sie Richtlinien für die Erkennung, Erfassung und Ergreifung von Aktionen für unangemessene Teams-Kommunikationen konfigurieren können, finden Sie unter [Kommunikations Kompatibilität in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance).

### <a name="retention-policies"></a>Aufbewahrungsrichtlinien

Mit Aufbewahrungsrichtlinien in Microsoft Teams können Sie sowohl Daten beibehalten, die für Ihre Organisation wichtig sind, als auch aus rechtlichen, rechtlichen, geschäftlichen oder anderen Gründen, sowie Inhalte und Kommunikationen entfernen, die nicht relevant sind, um aufbewahrt zu werden. Sie können Aufbewahrungsrichtlinien auch dazu verwenden, Daten für einen bestimmten Zeitraum zu speichern und dann zu löschen. Weitere Informationen finden Sie im Artikel [Aufbewahrungsrichtlinien in Microsoft Teams](retention-policies.md) .

### <a name="data-loss-prevention-dlp"></a>Verhinderung von Datenverlust (DLP)

Die Verhinderung von Datenverlust (Data Loss Prevention, DLP) in Microsoft Teams sowie die größere DLP-Story für Microsoft 365 oder Office 365 beruht auf Geschäfts Bereitschaft, wenn es um den Schutz vertraulicher Dokumente und Daten geht. Unabhängig davon, ob es sich um vertrauliche Informationen in Nachrichten oder Dokumenten handelt, können DLP-Richtlinien dabei helfen, sicherzustellen, dass Ihre Benutzer diese vertraulichen Daten nicht für die falschen Personen freigeben.

Informationen zur Verhinderung von Datenverlust in Teams finden Sie unter [DLP für Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams). Ein guter Artikel für Office 365 DLP-Bedenken ist eine [Übersicht über die Verhinderung von Datenverlust](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies).

### <a name="ediscovery"></a>eDiscovery

Electronic Discovery (eDiscovery) ist der elektronische Aspekt der Identifizierung, Sammlung und Erstellung von elektronisch gespeicherten Informationen (ESI) als Antwort auf einen Antrag auf Produktion in einer Klage oder Untersuchung. Zu den Funktionen gehören Fallmanagement, Erhaltung, Suche, Analyse und Export von Microsoft Teams-Daten. Dies schließt Zusammenfassungen für Chats, Nachrichten und Dateien sowie Besprechungen und Anrufe ein. Für Microsoft Teams-Besprechungen und -Anrufe wird eine Zusammenfassung der Ereignisse in Besprechungen und Anrufen erstellt und in der eDiscovery verfügbar gemacht.

Weitere Informationen dazu, wie Sie Microsoft 365 oder Office 365 eDiscovery im Security Center und Compliance Center durchführen und Compliance-Inhaltssuche nach Teams-Inhalten ausführen können, finden Sie unter den folgenden Links:

[eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations)

[Inhaltssuche](https://docs.microsoft.com/microsoft-365/compliance/search-for-content)

Wir haben einen Teams-spezifischen Artikel für weitere Informationen, [eDiscovery von Gast-zu-Gast-Chats](eDiscovery-investigation.md).

Kunden können eDiscovery oder [Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/office-365-advanced-ediscovery) pro Ihre Anforderungen nutzen. In der folgenden Tabelle sind die Unterschiede zwischen den beiden Funktionen aufgeführt:

| |eDiscovery  |Advanced eDiscovery  |
|---------|---------|---------|
|Fallmanagement     |X        |X         |
|Access Control  |X         |X         |
|Suche in Inhalten     |X         | X        |
|Speicher   |X         | X        |
|Exportieren     |X         |X         |
|Erkennung von Duplikaten     |-         |X         |
|Relevanzsuche mit maschinellem Lernen    |-         |X         |
|Analyse unstrukturierter Daten      |-         |X         |

### <a name="legal-hold"></a>Gesetzliche Aufbewahrungspflicht

Während eines Rechtsstreits müssen Sie möglicherweise alle Daten, die einem Benutzer (Depotbank) oder einem Team zugeordnet sind, als unveränderlich beibehalten, damit er als Beweis für den Fall verwendet werden kann. Sie können dies tun, indem Sie entweder einen Benutzer (Benutzerpostfach) oder ein Team in rechtlicher Wartestellung setzen. Für eine rechtliche Aufbewahrungspflicht für ein Team kann das Postfach des Teams auf folgende haltebereiche gesetzt werden:

- In-Place halten (eine Teilmenge des Postfachs oder der Websitesammlung durch gezielte Abfragen oder gefilterte Inhalte wird in den Wartebereich gesetzt) oder
- Rechtsstreit halten (das gesamte Postfach oder die gesamte Websitesammlung wird in Wartestellung gesetzt).

In beiden Fällen wird nach der Festlegung des haltebereichs sichergestellt, dass selbst dann, wenn Endbenutzer Kanal Nachrichten löschen oder bearbeiten, die sich im Gruppenpostfach befinden, unveränderliche Kopien dieser Inhalte verwaltet und über die eDiscovery-Suche verfügbar sind. Rechtliche Aufbewahrungen werden im Allgemeinen im Kontext eines eDiscovery-Falls angewendet.

Lesen Sie den Artikel [Übersicht über Aufbewahrungsrichtlinien](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) , um mehr über die Aufbewahrung und Aufbewahrung im Microsoft 365 Compliance Center zu erfahren. Wenn Sie weitere Teams-spezifische Informationen zur rechtlichen Aufbewahrung benötigen, haben wir auch [einen Microsoft Teams-Benutzer oder ein Team für legalen Aufbewahrungs Artikel eingerichtet](legal-hold.md) , in dem Sie weitere Informationen finden.

### <a name="compliance-content-search"></a>Compliancesuche in Inhalten

Die Inhaltssuche kann verwendet werden, um über umfangreiche Filterfunktionen nach allen Teams-Daten zu suchen. Die resultierenden Daten können für Compliance-und Litigation-Unterstützung in einen bestimmten Container exportiert werden. Dies kann mit oder ohne eDiscovery-Fall geschehen. Auf diese Weise können Complianceadministratoren Microsoft Teams-Daten für alle Benutzer sammeln, überprüfen und zur weiteren Verarbeitung exportieren. Weitere Informationen zum Durchführen einer Kompatibilitäts [Inhaltssuche für](https://docs.microsoft.com/microsoft-365/compliance/content-search) Microsoft Teams und andere Microsoft 365-oder Office 365-Inhalte finden Sie im Microsoft 365 Compliance Center.

> [!TIP]
> Mithilfe der Inhaltssuche können Sie nach Bedarf nach nur Microsoft Teams-Inhalten wie Chats und Kanal Nachrichten, Besprechungen und anrufen filtern.

Wenn Sie weitere Teams-spezifische Informationen zum Konfigurieren der Inhaltssuche wünschen, lesen Sie den Artikel [Inhaltssuche in Microsoft Teams](content-search.md) .

### <a name="auditing-and-reporting"></a>Überwachung und Berichterstellung

Die Überwachungsprotokoll Suche wird direkt in das Microsoft 365 Compliance Center übermittelt und bietet Ihnen die Möglichkeit, Benachrichtigungen sowie Berichte zu Überwachungsereignissen festzulegen, indem Sie den Export von Arbeits Auslastungs spezifischen oder generischen Ereignis Sätzen für die Verwendung durch Administratoren und die Untersuchung in einer unbegrenzten Überwachungs Zeitachse zulassen. Sie können Benachrichtigungen für alle Überwachungsprotokolldaten im Microsoft 365 Compliance Center einrichten und diese Daten zur weiteren Analyse Filtern und exportieren. Weitere Informationen zum Durchführen einer Überwachungsprotokoll Suche für Microsoft 365 oder Office 365 finden Sie im Artikel [Durchsuchen des Überwachungsprotokolls](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) . Wenn Sie mehr über das Suchen nach Microsoft Teams-Ereignissen im Microsoft 365 Compliance Center erfahren möchten, haben wir auch den Artikel [Auditing in Teams](audit-log-events.md) für Sie zu überprüfen.

## <a name="privacy"></a>Datenschutz

Bei Microsoft steht der Schutz Ihrer Daten an oberster Stelle. Weitere Informationen zu unseren Datenschutzmethoden finden Sie unter:  

- [Datenschutz bei Microsoft](https://www.microsoft.com/trust-center/privacy)
- [Unser Bekenntnis zu Datenschutz und Sicherheit in Microsoft Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/04/06/microsofts-commitment-privacy-security-microsoft-teams/)
- [Für IT-Experten: Datenschutz und Sicherheit in Microsoft Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/04/06/it-professionals-privacy-security-microsoft-teams/#:~:text=We%20safeguard%20your%20privacy%20by,and%20distribution%20of%20your%20data.)

## <a name="information-protection-architecture"></a>Architektur des Informationsschutzes

Die folgende Abbildung zeigt den Ablauf der Erfassung von Microsoft Teams-Daten (Microsoft Teams-Dateien und -Nachrichten) in Exchange und SharePoint.

![Diagramm des Workflows von Microsoft Teams-Daten zu Exchange und SharePoint](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)

Die folgende Abbildung zeigt den Ablauf der Erfassung von Daten aus Microsoft Teams-Besprechungen und -Anrufen in Exchange.

![Diagramm des Workflows von Daten aus Microsoft Teams-Besprechungen und -Anrufen zu Exchange](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1a.png)

> [!IMPORTANT]
> Beim Ermitteln von Microsoft Teams-Inhalten ist eine Verzögerung von bis zu 24 Stunden möglich.

## <a name="licensing"></a>Lizenzierung

In Bezug auf Informationsschutzfunktionen bestimmen Microsoft 365-Abonnements, Office 365-Abonnements und die zugehörigen eigenständigen Lizenzen den verfügbaren Funktionsumfang.

Informationen zum Ermitteln des Lizenzierungs Bedarfs zur Implementierung von Features für Sicherheit und Compliance finden Sie unter [Lizenzierung für Office 365 oder Microsoft 365](https://download.microsoft.com/download/8/7/7/877B1713-671E-43AA-BB79-AF8478C64AFF/Licensing-Microsoft-365.pdf).

> [!NOTE]
> Die Inhaltssuche und eDiscovery müssen im Security & Compliance Center nicht aktiviert sein, damit Sie funktionieren.

## <a name="location-of-data-in-teams"></a>Speicherort von Daten in Microsoft Teams

Daten in Teams befinden sich in der geografischen Region, die Ihrer Microsoft 365- oder Office 365-Organisation zugeordnet ist. Wenn Sie sehen möchten, welche Regionen zurzeit unterstützt werden, überprüfen Sie den [Speicherort der Daten in Microsoft Teams](location-of-data-in-teams.md).

Wenn Sie sehen möchten, in welcher Region die Daten für Ihren Mandanten angezeigt werden, wechseln Sie zum [Microsoft 365 Admin Center](https://portal.office.com/adminportal/home)  >  **Settings**  >  **Organization Profile**. Scrollen Sie nach unten zu **Data location** (Datenspeicherort).

![Screenshot der Tabelle „Data location“ (Datenspeicherort) einschließlich Microsoft Teams im Admin Center](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="compliance-standards"></a>Compliance-Standards

Teams verwendet die folgenden Standards: [ISO 27001](https://docs.microsoft.com/microsoft-365/compliance/offering-iso-27001), [ISO 27018](https://docs.microsoft.com/microsoft-365/compliance/offering-iso-27018), [SSAE18 SOC 1-und SOC 2](https://docs.microsoft.com/microsoft-365/compliance/offering-soc)-, [HIPAA](https://docs.microsoft.com/microsoft-365/compliance/offering-hipaa-hitech)-und [EU-Modellklauseln (EUMC)](https://docs.microsoft.com/microsoft-365/compliance/offering-eu-model-clauses). Innerhalb des Microsoft Compliance-Rahmens stuft Microsoft Microsoft 365-und Office 365-Anwendungen und-Dienste in vier Kategorien ein. Jede Kategorie wird durch spezifische Compliance-Zusagen definiert, die für einen Microsoft 365-oder Office 365-Dienst oder einen zugehörigen Microsoft-Dienst erfüllt sein müssen, um in dieser Kategorie aufgeführt zu werden.

Details finden Sie in den [datenschutzressourcen](https://servicetrust.microsoft.com/ViewPage/TrustDocumentsV3?command=Download&downloadType=Document&downloadId=b7d05b86-c69b-41ba-8245-21161b9febf9&tab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913&docTab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913_Compliance_Guides). Teams unterstützt auch die Cloud Security Alliance-Compliance.

## <a name="related-topics"></a>Verwandte Themen

[Microsoft 365-Sicherheit](https://docs.microsoft.com/microsoft-365/security/)

[Microsoft 365-Compliance](https://docs.microsoft.com/microsoft-365/compliance/)

[Microsoft-Compliance-Angebote](https://docs.microsoft.com/microsoft-365/compliance/offering-home)
