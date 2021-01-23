---
title: Übersicht über Sicherheit und Compliance
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: anwara
audience: admin
description: Eine Übersicht über Die Sicherheits- und Compliancefunktionen von Microsoft Teams, einschließlich Datenschutz und Verschlüsselung, Überwachung und Berichterstellung und vieles mehr.
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
ms.openlocfilehash: a9ee7d3d4cd7d877925b649bb3f3b6a8da72ddf0
ms.sourcegitcommit: 5473b9fcd2bfe8adeb05a4a8d23e4350c7970fb6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49937437"
---
# <a name="security-and-compliance-in-microsoft-teams"></a>Sicherheit und Compliance in Microsoft Teams

> [!IMPORTANT]
> Lesen Sie die folgenden Artikel, um zu erfahren, wie Sie die Sicherheit am besten gewährleisten können, während alle von zu Hause aus bei **einem COVID-19-Bruch** arbeiten:
>  - [Die wichtigsten 12 Aufgaben für Sicherheitsteams zur Unterstützung der Arbeit von zu Hause aus](https://docs.microsoft.com/microsoft-365/security/top-security-tasks-for-remote-work)
>  - [Optimieren der Microsoft 365- oder Office 365-Konnektivität für Remotebenutzer mithilfe des geteilten VPN-Tunnels](https://docs.microsoft.com/Office365/Enterprise/office-365-vpn-split-tunnel)
>  - Aktualisiert am 2. April 2020: [Sicherheitshandbuch für Teams](teams-security-guide.md)


Microsoft Teams baut auf der Hyperskalen-Cloud von Microsoft 365 und Office 365 auf Unternehmensklasse auf und bietet die erweiterten Sicherheits- und Compliancefunktionen, die unsere Kunden erwarten. Weitere Informationen zur Planung der Sicherheit in Microsoft 365 [](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap) oder Office 365 finden Sie im Sicherheitsplan. Weitere Informationen zur Planung der Compliance in Microsoft 365 oder Office 365 finden Sie im Artikel "Plan für Sicherheit [und Compliance".](https://docs.microsoft.com/microsoft-365/compliance/plan-for-security-and-compliance)


Dieser Artikel enthält weitere Informationen zu Teams-spezifischer Sicherheit und Compliance. Lassen Sie sich diese Microsoft Mechanics-Videos zu Sicherheit und Compliance nicht entgehen:

- [Microsoft Teams Essentials für IT: Sicherheit und Compliance](https://youtu.be/91lHNKVVvQ4) (12:42 Minuten)
- [Microsoft Teams Controls for Security and Compliance](https://www.youtube.com/watch?v=Km4T4hMM__k) (10:54 Min.)

> [!IMPORTANT]
> Als Kunde von Microsoft 365 oder Office 365 besitzen und steuern Sie Ihre Daten. Microsoft verwendet Ihre Daten nur für die Bereitstellung des Diensts, den Sie abonniert haben. Als Dienstanbieter scannen wir Ihre E-Mails, Dokumente oder Teams nicht zu Werbezwecken oder zu Zwecken, die nicht dienstbezogene sind. Microsoft hat keinen Zugriff auf hochgeladene Inhalte. Wie OneDrive und SharePoint in Microsoft 365 bleiben auch Kundendaten innerhalb des Mandanten. Weitere Informationen zu vertrauens- und sicherheitsbezogenen Informationen finden Sie im [Microsoft Trust Center.](https://microsoft.com/trustcenter) Microsoft Teams folgt den gleichen Leitlinien und Prinzipien wie das Microsoft Trust Center.

## <a name="security"></a>Sicherheit

Teams erzwingt teamweite und organisationsweite zweistufige Authentifizierung, einmaliges Anmelden über Active Directory und Verschlüsselung von Daten bei der Übertragung und ruhenden Daten. Dateien werden in SharePoint gespeichert und mit dem entsprechenden SharePoint-Mechanismus verschlüsselt. Notizen werden in OneNote gespeichert und mit dem entsprechenden OneNote-Mechanismus verschlüsselt. Die OneNote-Daten werden auf der SharePoint-Website des Teams gespeichert. Die Registerkarte "Wiki" kann auch zum Erstellen von Notizen verwendet werden, und der Inhalt wird ebenfalls auf der Team-SharePoint-Website gespeichert.

Lesen [Sie Identitätsmodelle und Authentifizierung,](identify-models-authentication.md) um mehr Einblicke in die Authentifizierung und teams zu erhalten, und wie die moderne [Authentifizierung](sign-in-teams.md) funktioniert, hilft insbesondere bei der modernen Authentifizierung.

Da Teams in Partnerschaft mit SharePoint, OneNote, Exchange und weiteren mehr zusammenarbeiten, sollten Sie mit der Verwaltung der Sicherheit in Microsoft 365 oder Office 365 als All-Up-Konto arbeiten. Weitere Informationen finden Sie unter dem Konfigurieren Ihrer [Microsoft 365- oder Office 365-Organisation für erhöhte Sicherheit.](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)

> [!NOTE]
> Derzeit unterstützen [private Kanäle](private-channels.md) eingeschränkte Sicherheits- und Compliancefeatures. Unterstützung für den vollständigen Satz von Sicherheits- und Compliancefeatures in privaten Kanälen wird in Kürze zur Verfügung stehen.

### <a name="advanced-threat-protection-atp"></a>Advanced Threat Protection (ATP)

Advanced Threat Protection (ATP) ist für Microsoft Teams sowie für SharePoint und OneDrive, Anwendungen, die in Teams für die Inhaltsverwaltung integriert sind, verfügbar. ATP ermöglicht es Ihnen zu bestimmen, ob Inhalte in diesen Anwendungen schädlich sind, und den Benutzerzugriff auf diese Inhalte zu blockieren.

Wie der betroffene Inhalt nach der Erkennung verwaltet wird, liegt in den Einstellungen, die Sie in Microsoft 365 oder Office 365 ausgewählt haben. Es wird dringend empfohlen, alle Anwendungen in Erwägung zu ziehen, wenn es um die Konfiguration von ATP geht. Zur weiteren Lektüre enthält der #A0 für [SharePoint, OneDrive](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams) und Microsoft Teams ausführliche Informationen zu den ersten Schritte.

### <a name="safe-links"></a>Sichere Links

Derzeit sind sichere Advanced Threat Protection (ATP)-Links in Microsoft Teams nicht [](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links-for-teams?view=o365-worldwide) verfügbar, sie werden jetzt über unser Technology Adoption Program (TAP) in der öffentlichen Vorschau angezeigt, und obwohl kein Veröffentlichungsdatum für die allgemeine Verfügbarkeit festgelegt ist, wird dieser Artikel aktualisiert, sobald diese Zeit ankommt. Informationen zu sicheren Links in Microsoft 365 oder Office 365 finden Sie in der Zwischenzeit unter ["Sichere ATP-Links".](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links#how-to-get-atp-safe-links-protection) AtP Safe links is available in [ATP Plan 1 and ATP Plan 2.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide)

### <a name="safe-attachments"></a>Sichere Anlagen

Sichere Anlagen sind ein Feature, das die Sicherheit des Benutzers erhöht, indem auf schädliche Anlagen überprüft und diese erkannt werden. Globale oder Sicherheitsadministratoren erstellen Richtlinien für die Behandlung dieser verdächtigen bösartigen Anlagen, um zu verhindern, dass sie an Benutzer gesendet, geklickt und auf sie reagiert werden. [](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-atp-safe-attachments-policies?view=o365-worldwide) Sicherer Anlagenschutz steht für SharePoint, OneDrive und Microsoft Teams zur Verfügung, und Microsoft 365 oder Office 365 [Advanced Threat Protection Plan 1 und 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) verfügen über diese Funktion. Weitere Informationen zu sicheren Anlagen und dazu, wie sie zum Schutz Ihrer Organisation beitragen können, finden Sie [hier.](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-attachments?view=o365-worldwide)

### <a name="how-conditional-access-policies-work-for-teams"></a>Funktionsweise von Richtlinien für bedingten Zugriff in Teams

Microsoft Teams basiert in den wichtigsten Produktivitätsszenarien wie Besprechungen, Kalendern, Inopchats und Dateifreigaben in hohem Maße auf Exchange Online, SharePoint und Skype for Business Online. Richtlinien für bedingten Zugriff, die für diese Cloud-Apps festgelegt wurden, gelten auch für Microsoft Teams, wenn sich Benutzer direkt bei Microsoft Teams anmelden – unabhängig vom Client.

Microsoft Teams wird separat als Cloud-App in Azure Active Directory-Richtlinien für bedingten Zugriff unterstützt. Richtlinien für bedingten Zugriff, die für die Microsoft Teams-Cloud-App festgelegt wurden, gelten auch für Microsoft Teams, wenn sich Benutzer anmelden. Ohne die richtigen Richtlinien für andere Apps wie Exchange Online und SharePoint können die Benutzer jedoch möglicherweise weiterhin direkt auf diese Ressourcen zugreifen. Weitere Informationen zum Einrichten einer Richtlinie für bedingten Zugriff im Azure-Portal finden Sie unter: [Azure Active Directory – Schnellstart.](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)

Microsoft Teams-Desktopclients für Windows und Mac unterstützen moderne Authentifizierung. Moderne Authentifizierung ermöglicht plattformübergreifend die Anmeldung auf der Grundlage von ADAL (Azure Active Directory Authentication Library, Active Directory-Authentifizierungsbibliothek) in Microsoft Office-Clientanwendungen.

Die Microsoft Teams-Desktopanwendung unterstützt AppLocker.  Weitere Informationen zu den Voraussetzungen für AppLocker finden Sie unter: Anforderungen für die Verwendung von [AppLocker.](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/requirements-to-use-applocker)

## <a name="compliance"></a>Compliance

Teams verfügt über eine breite Palette von Informationen, die Sie in Compliancebereichen unterstützen, darunter Kommunikationskonformität für Kanäle, Chats und Anlagen, Aufbewahrungsrichtlinien, DLP (Data Loss Protection), eDiscovery und gesetzliche Aufbewahrung für Kanäle, Chats und Dateien, Überwachungsprotokollsuche und verwaltung mobiler Anwendungen mit Microsoft Intune. Wir haben einige Informationen zu allen diesen Themen unten bereitgestellt, und Sie können zum [Microsoft 365 Compliance Center](https://compliance.microsoft.com) wechseln, um diese Einstellungen zu verwalten.

### <a name="information-barriers"></a>Informationsbarrieren

Informationsbarrieren sind Richtlinien, die von Teamadministratoren eingerichtet werden, um beispielsweise dafür zu sorgt, dass Personen oder Gruppen nicht miteinander kommunizieren können (wenn dies nicht vom Unternehmen benötigt wird, oder ein gesetzlicher Grund, dies zu blockieren), und es ermöglicht Ihnen außerdem, Richtlinien für Dinge wie Nachschlageaktionen und eDiscovery (siehe unten) zu erstellen. Diese Richtlinien können sich auf Benutzer in 1:1-Chats, Gruppenchats oder auf Teamebene auswirken.

Weitere Informationen zu diesem Thema finden Sie unter ["Informationsbarrieren" in Microsoft Teams.](information-barriers-in-teams.md)

### <a name="communication-compliance"></a>Kommunikationskonformität

Mit Der Kommunikationskonformität in Microsoft 365 können Sie Benutzer zu Richtlinien im Bereich hinzufügen, die so konfiguriert werden können, dass die Kommunikation in Microsoft Teams auf anstößige Sprache, vertrauliche Informationen und Informationen im Zusammenhang mit internen und behördlichen Standards untersucht wird. Chatkommunikation und zugehörige Anlagen in öffentlichen und privaten Teams-Kanälen, einzelnen Chats und Anlagen können gescannt werden, um die Kommunikationsrisiken in Ihrer Organisation zu minimieren. Weitere Informationen dazu, wie Sie Richtlinien konfigurieren können, damit Sie unangemessene Kommunikationen in Microsoft Teams erkennen, erfassen und maßnahmen können, finden Sie unter "Kommunikationskonformität [in Microsoft 365".](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance)

### <a name="retention-policies"></a>Aufbewahrungsrichtlinien

Aufbewahrungsrichtlinien in Microsoft Teams ermöglichen ihnen das Speichern von Daten, die für Ihre Organisation wichtig sind, und zwar sowohl aus gesetzlichen, rechtlichen, geschäftlichen oder anderen Gründen als auch das Entfernen von Inhalten und Kommunikationen, die für die Beibehaltung nicht relevant sind. Mithilfe von Aufbewahrungsrichtlinien können Sie Daten auch für einen bestimmten Zeitraum behalten und dann löschen. Weitere Informationen finden Sie in den [Aufbewahrungsrichtlinien in Microsoft Teams.](retention-policies.md)

## <a name="sensitivity-labels"></a>Vertraulichkeitsbeschriftungen

Wenden [Sie Vertraulichkeitsbezeichnungen](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) an, um den Zugriff auf vertrauliche Organisationsinhalte zu schützen und zu schützen, die während der Zusammenarbeit innerhalb von Teams erstellt wurden. Wenden Sie beispielsweise Bezeichnungen an, die den Datenschutz (öffentlich oder privat) von Teams konfigurieren, den Gastzugriff und die externe Freigabe steuern und den Zugriff von nicht verwalteten Geräten aus verwalten. Weitere Informationen finden Sie in den [Vertraulichkeitsbezeichnungen im Microsoft Teams-Artikel.](sensitivity-labels.md)

### <a name="data-loss-prevention-dlp"></a>Verhinderung von Datenverlust (Data Loss Prevention, DLP)

Die Verhinderung von Datenverlust (Data Loss Prevention, DLP) in Microsoft Teams sowie der größere Artikel zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) für Microsoft 365 oder Office 365 drehen sich um die Geschäftsbereitschaft, wenn es um den Schutz vertraulicher Dokumente und Daten geht. Ganz gleich, ob Sie Bedenken hinsichtlich vertraulicher Informationen in Nachrichten oder Dokumenten haben, mithilfe von DLP-Richtlinien kann sichergestellt werden, dass Ihre Benutzer diese vertraulichen Daten nicht mit den falschen Personen teilen.

Informationen zur Verhinderung von Datenverlust in Teams finden Sie in [DLP für Microsoft Teams.](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams) Ein guter Artikel für Probleme von O365 DLP ist die Übersicht über die Verhinderung [von Datenverlust.](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)

### <a name="ediscovery"></a>eDiscovery

Die elektronische Ermittlung (eDiscovery) ist der elektronische Aspekt der Identifizierung, Erfassung und Herstellung elektronisch gespeicherter Informationen als Reaktion auf eine Produktionsanforderung in einer Rechtsklage oder Untersuchung. Zu den Funktionen gehören Fallmanagement, Erhaltung, Suche, Analyse und Export von Microsoft Teams-Daten. Dies schließt Zusammenfassungen für Chats, Nachrichten und Dateien sowie Besprechungen und Anrufe ein. Für Microsoft Teams-Besprechungen und -Anrufe wird eine Zusammenfassung der Ereignisse in Besprechungen und Anrufen erstellt und in der eDiscovery verfügbar gemacht.

Weitere Details zur Ausführung von Microsoft 365- oder Office 365 eDiscovery im Security Center und Compliance Center und zum Ausführen der Complianceinhaltssuche nach Microsoft Teams-Inhalten finden Sie unter den folgenden Links:

[eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations)

[Inhaltssuche](https://docs.microsoft.com/microsoft-365/compliance/search-for-content)

Wir haben einen Teams-spezifischen Artikel für weitere Informationen, [eDiscovery von Gast-zu-Gast-Chats.](eDiscovery-investigation.md)

Kunden können eDiscovery oder [Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/office-365-advanced-ediscovery) nach ihren Anforderungen nutzen. In der folgenden Tabelle sind die Unterschiede zwischen den beiden Funktionen aufgeführt:

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

Während eines Rechtsstreits müssen möglicherweise alle daten, die einem Benutzer (Bzw. Bzw. Einem Team) zugeordnet sind, als unveränderlich beibehalten werden, damit sie als Beweismaterial für den Fall verwendet werden können. Dazu können Sie entweder einen Benutzer (Benutzerpostfach) oder ein Team in die gesetzliche Schleife setzen. Für einen gesetzlichen In-Halteraum für ein Team kann das Postfach des Teams in die folgenden Halteschleifen verschoben werden:

- In-Place (eine Teilmenge des Postfachs oder der Websitesammlung durch gezielte Abfragen oder gefilterte Inhalte wird im Haltebereich gespeichert) oder
- Halteverfahren für Rechtsstreitigkeiten (das gesamte Postfach oder die gesamte Websitesammlung wird in den Halteraum gesetzt).

In beiden Fällen wird durch festlegen des Haltefelds sichergestellt, dass, selbst wenn Endbenutzer Kanalnachrichten, die sich im Gruppenpostfach befinden, unveränderliche Kopien dieses Inhalts beibehalten und über die eDiscovery-Suche zur Verfügung stehen. Gesetzliche Halte halte ich im Allgemeinen im Kontext eines eDiscovery-Falls.

Lesen Sie bitte den [Artikel zu Aufbewahrungsrichtlinien,](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) um mehr über Erhaltung und Aufbewahrung im Microsoft 365 Compliance Center zu erfahren. Wenn Sie weitere Teams-spezifische Informationen zur gesetzlichen Zurückhalten von Microsoft Teams erhalten möchten, finden Sie in diesem Artikel auch weitere Informationen zu Microsoft [Teams-Benutzern](legal-hold.md) oder -Teams.

### <a name="compliance-content-search"></a>Compliancesuche in Inhalten

Die Inhaltssuche kann verwendet werden, um über umfangreiche Filterfunktionen nach allen Daten in Teams zu suchen. Die resultierenden Daten können zur Unterstützung von Compliance- und Rechtsstreitigkeiten in einen bestimmten Container exportiert werden. Dies kann mit oder ohne eDiscovery-Fall geschehen. Auf diese Weise können Complianceadministratoren Microsoft Teams-Daten für alle Benutzer sammeln, überprüfen und zur weiteren Verarbeitung exportieren. Lesen Sie diesen Artikel für [die](https://docs.microsoft.com/microsoft-365/compliance/content-search) Inhaltssuche, um mehr darüber zu erfahren, wie Sie eine Complianceinhaltssuche für Microsoft Teams und andere Microsoft 365- oder Office 365-Inhalte im Microsoft 365 Compliance Center durchführen.

> [!TIP]
> Mithilfe der Inhaltssuche können Sie bei Bedarf nur nach Inhalten in Microsoft Teams filtern, z. B. Chat- und Kanalnachrichten, Besprechungen und Anrufe.

Wenn Sie weitere Teams-spezifische Informationen zum Konfigurieren der Inhaltssuche erhalten möchten, lesen Sie die [Inhaltssuche im Microsoft](content-search.md) Teams-Artikel.

### <a name="auditing-and-reporting"></a>Überwachung und Berichterstellung

Die Überwachungsprotokollsuche ist direkt in das Microsoft 365 Compliance Center angeschlossen und bietet Ihnen die Möglichkeit, Warnungen zu festlegen sowie Berichte zu Überwachungsereignissen zu erstellen, indem der Export von workloadspezifischen oder generischen Ereignissätzen für die Administratornutzung und -untersuchung über eine unbegrenzte Überwachungszeitachse ermöglicht wird. Sie können Warnungen für alle Überwachungsprotokolldaten im Microsoft 365 Compliance Center einrichten und diese Daten zur weiteren Analyse filtern und exportieren. Weitere Informationen [](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) zum Durchführen einer Überwachungsprotokollsuche für Microsoft 365 oder Office 365 finden Sie im Artikel zum Durchsuchen des Überwachungsprotokolls. Weitere Informationen zur Suche nach Microsoft Teams-Ereignissen im Microsoft 365 Compliance Center finden Sie auch im Artikel "Aktivieren der Überwachung [in Teams",](audit-log-events.md) den Sie überprüfen können.

## <a name="privacy"></a>Datenschutz

Bei Microsoft hat der Schutz Ihrer Daten oberste Priorität. Weitere Informationen zu unseren Datenschutzpraktiken finden Sie unter:  

- [Datenschutz bei Microsoft](https://www.microsoft.com/trust-center/privacy)
- [Unser Engagement für Datenschutz und Sicherheit in Microsoft Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/04/06/microsofts-commitment-privacy-security-microsoft-teams/)
- [Für IT-Experten: Datenschutz und Sicherheit in Microsoft Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/04/06/it-professionals-privacy-security-microsoft-teams/#:~:text=We%20safeguard%20your%20privacy%20by,and%20distribution%20of%20your%20data.)

## <a name="information-protection-architecture"></a>Architektur für Den Schutz von Informationen

Die folgende Abbildung zeigt den Ablauf der Erfassung von Microsoft Teams-Daten (Microsoft Teams-Dateien und -Nachrichten) in Exchange und SharePoint.

![Diagramm des Workflows von Microsoft Teams-Daten zu Exchange und SharePoint](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)

Die folgende Abbildung zeigt den Ablauf der Erfassung von Daten aus Microsoft Teams-Besprechungen und -Anrufen in Exchange.

![Diagramm des Workflows von Daten aus Microsoft Teams-Besprechungen und -Anrufen zu Exchange](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1a.png)

> [!IMPORTANT]
> Beim Ermitteln von Microsoft Teams-Inhalten ist eine Verzögerung von bis zu 24 Stunden möglich.

## <a name="licensing"></a>Lizenzierung

Wenn es um Funktionen zum Schutz von Informationen geht, bestimmen Microsoft 365-Abonnements, Office 365-Abonnements und die zugehörigen eigenständigen Lizenzen die verfügbaren Features.

Informationen zum Ermitteln der Lizenzierungsanforderungen für die Implementierung von Features für Sicherheit und Compliance finden Sie unter den [Lizenzierungsanforderungen](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance) für Sicherheits- und Compliancefunktionen.
> [!NOTE]
> Inhaltssuche und eDiscovery müssen im Security & Compliance Center nicht aktiviert sein, damit sie funktionieren.

## <a name="location-of-data-in-teams"></a>Speicherort von Daten in Microsoft Teams

Daten in Teams befinden sich in der geografischen Region, die Ihrer Microsoft 365- oder Office 365-Organisation zugeordnet ist. Um zu sehen, welche Regionen derzeit unterstützt werden, überprüfen Sie den [Speicherort der Daten in Microsoft Teams.](location-of-data-in-teams.md)

Wenn Sie sehen möchten, in welcher Region Daten für Ihren Mandanten enthalten sind, wechseln Sie zum Profil "Einstellungsorganisation" im [Microsoft 365](https://portal.office.com/adminportal/home)  >  **Admin**  >  **Center.** Scrollen Sie nach unten zu **Data location** (Datenspeicherort).

![Screenshot der Tabelle „Data location“ (Datenspeicherort) einschließlich Microsoft Teams im Admin Center](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="compliance-standards"></a>Compliancestandards

Teams verwendet die folgenden Standards: [ISO 27001,](https://docs.microsoft.com/microsoft-365/compliance/offering-iso-27001) [ISO 27018,](https://docs.microsoft.com/microsoft-365/compliance/offering-iso-27018) [SSAE18 SOC 1 und SOC 2,](https://docs.microsoft.com/microsoft-365/compliance/offering-soc) [HIPAA](https://docs.microsoft.com/microsoft-365/compliance/offering-hipaa-hitech)und [EU Model Clauses (EUMC).](https://docs.microsoft.com/microsoft-365/compliance/offering-eu-model-clauses) Innerhalb des Microsoft-Compliance-Frameworks unterteilt Microsoft 365- und Office 365-Anwendungen und -Dienste in vier Kategorien. Jede Kategorie wird durch bestimmte Complianceverpflichtungen definiert, die erfüllt sein müssen, damit ein Microsoft 365- oder Office 365-Dienst oder ein zugehöriger Microsoft-Dienst in dieser Kategorie aufgeführt wird.

Details finden Sie in den [Datenschutzressourcen.](https://servicetrust.microsoft.com/ViewPage/TrustDocumentsV3?command=Download&downloadType=Document&downloadId=b7d05b86-c69b-41ba-8245-21161b9febf9&tab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913&docTab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913_Compliance_Guides) Teams unterstützt auch Cloud Security Alliance-Compliance.

## <a name="related-topics"></a>Verwandte Themen

[Microsoft 365 Security](https://docs.microsoft.com/microsoft-365/security/)

[Microsoft 365 Compliance](https://docs.microsoft.com/microsoft-365/compliance/)

[Microsoft-Compliance-Angebote](https://docs.microsoft.com/microsoft-365/compliance/offering-home)
