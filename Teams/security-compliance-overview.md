---
title: Übersicht über Sicherheit und Compliance
author: laurawi
ms.author: laurawi
manager: laurawi
ms.topic: conceptual
ms.service: msteams
ms.reviewer: anwara
audience: admin
description: Eine Übersicht über Die Sicherheits- und Compliancefeatures von Microsoft Teams, einschließlich Datenschutz und Verschlüsselung, Überwachung und Berichterstellung und vieles mehr.
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
ms.openlocfilehash: 36cb67dc73177678206e5d5865ba145414ae37a9
ms.sourcegitcommit: 360c78c66386fe00afe535681f51254eda886edf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/17/2021
ms.locfileid: "50836922"
---
# <a name="security-and-compliance-in-microsoft-teams"></a>Sicherheit und Compliance in Microsoft Teams

> [!IMPORTANT]
> Lesen Sie die folgenden Artikel, um zu erfahren, wie Sie die Sicherheit während des **COVID-19-Ausbruchs** von zu Hause aus optimal gewährleisten können:
>  - [Die wichtigsten 12 Aufgaben für Sicherheitsteams zur Unterstützung der Arbeit von zu Hause aus](https://docs.microsoft.com/microsoft-365/security/top-security-tasks-for-remote-work)
>  - [Optimieren der Microsoft 365- oder Office 365-Konnektivität für Remotebenutzer mithilfe des geteilten VPN-Tunnels](https://docs.microsoft.com/Office365/Enterprise/office-365-vpn-split-tunnel)
>  - Aktualisiert am 2. April 2020: [Sicherheitshandbuch für Teams](teams-security-guide.md)


Microsoft Teams baut auf der Hyper-Scale-Cloud von Microsoft 365 und Office 365 auf Unternehmensklasse auf und bietet die erweiterten Sicherheits- und Compliancefunktionen, die unsere Kunden erwarten. Weitere Informationen zur Planung der Sicherheit in Microsoft 365 [](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap) oder Office 365 finden Sie in der Sicherheitsplanplanung. Weitere Informationen zur Planung von Compliance in Microsoft 365 oder Office 365 finden Sie unter Planen von Sicherheit [und & Compliance.](https://docs.microsoft.com/microsoft-365/compliance/plan-for-security-and-compliance)


Dieser Artikel enthält weitere Informationen zu Teams-spezifischer Sicherheit und Compliance. Verpassen Sie nicht die folgenden Microsoft Mechanics-Videos zu Sicherheit und Compliance:

- [Microsoft Teams Essentials für IT: Sicherheit und Compliance](https://youtu.be/91lHNKVVvQ4) (12:42 Min.)
- [Microsoft Teams-Steuerelemente für Sicherheit und Compliance](https://www.youtube.com/watch?v=Km4T4hMM__k) (10:54 Min.)

> [!IMPORTANT]
> Als Kunde von Microsoft 365 oder Office 365 besitzen und steuern Sie Ihre Daten. Microsoft verwendet Ihre Daten nur für andere Dienste als die Bereitstellung des diensts, den Sie abonniert haben. Als Dienstanbieter scannen wir Ihre E-Mails, Dokumente oder Teams nicht zu Werbezwecken oder zu Zwecken, die nicht dienstlich sind. Microsoft hat keinen Zugriff auf hochgeladene Inhalte. Wie OneDrive und SharePoint in Microsoft 365 bleiben Kundendaten innerhalb des Mandanten. Weitere Informationen zu unseren Informationen zu Vertrauen und Sicherheit finden Sie im [Microsoft Trust Center.](https://microsoft.com/trustcenter) Microsoft Teams folgt den gleichen Leitlinien und Prinzipien wie das Microsoft Trust Center.

## <a name="security"></a>Sicherheit

Teams erzwingt die teamweite und organisationsweite zweistufige Authentifizierung, einmaliges Anmelden über Active Directory und die Verschlüsselung von Daten, die übertragen und in Ruhe sind. Dateien werden in SharePoint gespeichert und mit dem entsprechenden SharePoint-Mechanismus verschlüsselt. Notizen werden in OneNote gespeichert und mit dem entsprechenden OneNote-Mechanismus verschlüsselt. Die OneNote-Daten werden auf der SharePoint-Website des Teams gespeichert. Die Registerkarte Wiki kann auch zum Erstellen von Notizen verwendet werden, und ihr Inhalt wird auch auf der SharePoint-Teamwebsite des Teams gespeichert.

Lesen [Sie Identitätsmodelle und Authentifizierung,](identify-models-authentication.md) um mehr Einblick in Authentifizierung und Teams zu erhalten, und wie moderne [Authentifizierung](sign-in-teams.md) funktioniert, hilft insbesondere bei der modernen Authentifizierung.

Da Teams in Partnerschaft mit SharePoint, OneNote, Exchange und mehr zusammenarbeiten, sollten Sie die Sicherheit in Microsoft 365 oder Office 365 insgesamt komfortabel verwalten. Weitere Informationen finden Sie unter Konfigurieren Ihrer [Microsoft 365- oder Office 365-Organisation](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)für mehr Sicherheit.

> [!NOTE]
> Derzeit unterstützen [private Kanäle](private-channels.md) eingeschränkte Sicherheits- und Compliancefeatures. Unterstützung für den vollständigen Satz von Sicherheits- und Compliancefeatures in privaten Kanälen wird in Kürze zur Verfügung stehen.

### <a name="advanced-threat-protection-atp"></a>Advanced Threat Protection (ATP)

Advanced Threat Protection (ATP) steht zusammen mit SharePoint und OneDrive, Anwendungen, die in Teams für die Inhaltsverwaltung integriert sind, für Microsoft Teams zur Verfügung. MIT ATP können Sie ermitteln, ob Inhalte in diesen Anwendungen böswilliger Natur sind, und diesen Inhalt für den Benutzerzugriff blockieren.

Wie der betroffene Inhalt nach der Erkennung verwaltet wird, liegt in den Einstellungen, die Sie in Microsoft 365 oder Office 365 ausgewählt haben. Es wird dringend empfohlen, dass Sie alle Anwendungen berücksichtigen, wenn es um die Konfiguration von ATP geht, und für weitere Informationen enthält [ATP für SharePoint, OneDrive](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams) und Microsoft Teams detaillierte Informationen zu den ersten Schritte.

### <a name="safe-links"></a>Sichere Links

Obwohl zu diesem Zeitpunkt sichere Advanced Threat Protection (ATP)-Links in Microsoft [](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links-for-teams?view=o365-worldwide) Teams nicht verfügbar sind, werden sie jetzt über unser Technology Adoption Program (TAP) in der öffentlichen Vorschau angezeigt, und obwohl kein Veröffentlichungsdatum für die allgemeine Verfügbarkeit festgelegt ist, werden wir diesen Artikel aktualisieren, sobald diese Zeit eintrifft. Informationen zu sicheren Microsoft 365- oder Office 365-Links finden Sie unter [ATP Safe Links](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links#how-to-get-atp-safe-links-protection). ATP Sichere Links sind sowohl in [ATP Plan 1 als auch in ATP Plan 2 verfügbar.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide)

### <a name="safe-attachments"></a>Sichere Anlagen

Sichere Anlagen ist ein Feature, das die Benutzersicherheit erhöhen soll, indem schädliche Anlagen überprüft und erkannt werden. Globale oder Sicherheitsadministratoren erstellen Richtlinien für die Behandlung dieser mutmaßlichen schädlichen Anlagen, um zu verhindern, dass sie an Benutzer gesendet, geklickt und darauf reagiert werden. [](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-atp-safe-attachments-policies?view=o365-worldwide) Sicherer Anlagenschutz ist für SharePoint, OneDrive und Microsoft Teams verfügbar, und Microsoft 365 oder Office 365 [Advanced Threat Protection Plan 1](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) und 2 verfügen über diese Funktion. Weitere Informationen zu sicheren Anlagen und deren Unterstützung beim Schutz Ihrer Organisation finden Sie unter Sichere Anlagen [in Microsoft Defender für Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-attachments?view=o365-worldwide)

### <a name="secure-score"></a>Secure Score

Microsoft Secure Score ist ein Maß für die Sicherheitshaltung einer Organisation, mit einer höheren Anzahl, die mehr Verbesserungsmaßnahmen angibt. Sie befindet sich im [Microsoft 365 Security Center.](https://security.microsoft.com/securescore) Wenn Sie den Secure Score-Empfehlungen folgen, können Sie Ihre Organisation vor Bedrohungen schützen. Über ein zentrales Dashboard im Microsoft 365 Security Center können Organisationen die Sicherheit ihrer Microsoft 365-Identitäten, -Apps und -Geräte überwachen und bearbeiten. Microsoft Teams enthält jetzt Empfehlungen zu Secure Score, und Administratoren werden aufgefordert, ihre Sicherheitshaltung auf der Plattform zu überwachen.

Secure Score hilft Organisationen:
- Melden Sie den aktuellen Status der Sicherheitshaltung der Organisation.
- Verbessern Sie ihre Sicherheitshaltung, indem Sie Diebigkeit, Sichtbarkeit, Anleitung und Kontrolle bereitstellen.
- Vergleichen Sie mit Benchmarks, und legen Sie KpIs (Key Performance Indicators) fest.


### <a name="how-conditional-access-policies-work-for-teams"></a>Funktionsweise von Richtlinien für bedingten Zugriff für Teams

Microsoft Teams setzt bei grundlegenden Produktivitätsszenarien wie Besprechungen, Kalendern, Inopchats und Dateifreigaben in hohem Maße auf Exchange Online, SharePoint und Skype for Business Online. Richtlinien für bedingten Zugriff, die für diese Cloud-Apps festgelegt wurden, gelten auch für Microsoft Teams, wenn sich Benutzer direkt bei Microsoft Teams anmelden – unabhängig vom Client.

Microsoft Teams wird separat als Cloud-App in Azure Active Directory-Richtlinien für bedingten Zugriff unterstützt. Richtlinien für bedingten Zugriff, die für die Microsoft Teams-Cloud-App festgelegt wurden, gelten auch für Microsoft Teams, wenn sich Benutzer anmelden. Ohne die richtigen Richtlinien für andere Apps wie Exchange Online und SharePoint können Benutzer jedoch möglicherweise weiterhin direkt auf diese Ressourcen zugreifen. Weitere Informationen zum Einrichten einer Richtlinie für bedingten Zugriff im Azure-Portal finden Sie unter [Azure Active Directory Schnellstart](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started).

Microsoft Teams-Desktopclients für Windows und Mac unterstützen moderne Authentifizierung. Moderne Authentifizierung ermöglicht plattformübergreifend die Anmeldung auf der Grundlage von ADAL (Azure Active Directory Authentication Library, Active Directory-Authentifizierungsbibliothek) in Microsoft Office-Clientanwendungen.

Die Microsoft Teams-Desktopanwendung unterstützt AppLocker.  Weitere Informationen zu den Voraussetzungen von AppLocker finden Sie unter: Anforderungen für die Verwendung von [AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/requirements-to-use-applocker).

## <a name="compliance"></a>Compliance

Teams verfügt über eine breite Palette von Informationen, die Ihnen bei Compliancebereichen helfen, einschließlich Kommunikationskonformität für Kanäle, Chats und Anlagen, Aufbewahrungsrichtlinien, Schutz vor Datenverlust (Data Loss Protection, DLP), eDiscovery und rechtlicher Haltebereich für Kanäle, Chats und Dateien, Überwachungsprotokollsuche sowie Verwaltung mobiler Anwendungen mit Microsoft Intune. Wir haben einige Informationen zu all diesen Themen unten bereitgestellt, und Sie können zum [Microsoft 365 Compliance Center](https://compliance.microsoft.com) wechseln, um diese Einstellungen zu verwalten.

### <a name="information-barriers"></a>Informationsbarrieren

Informationsbarrieren sind Richtlinien, die von Teams-Administratoren eingerichtet wurden, um z. B. Personen oder Gruppen an der Kommunikation miteinander zu halten (wenn es keine geschäftliche Notwendigkeit dafür gibt, oder ein gesetzlicher Grund, dies zu blockieren). Außerdem können Sie Richtlinien für Dinge wie Nachschlage- und eDiscovery festlegen (siehe unten). Diese Richtlinien können sich auf Benutzer in 1:1-Chats, Gruppenchats oder auf Teamebene auswirken. Das Feature Informationsbarriere ist in der öffentlichen Cloud verfügbar und wird ab Januar 2021 in der GCC-Cloud angeboten.

Weitere Informationen zu diesem Thema finden Sie unter [Informationsbarrieren in Microsoft Teams.](information-barriers-in-teams.md)

### <a name="communication-compliance"></a>Kommunikationscompliance

Mit der Kommunikationskonformität in Microsoft 365 können Sie Benutzer zu Richtlinien in ihrem Umfang hinzufügen, die konfiguriert werden können, um Microsoft Teams-Kommunikationen auf anstößige Sprache, sensible Informationen und Informationen im Zusammenhang mit internen und gesetzlichen Standards zu untersuchen. Chatkommunikationen und zugehörige Anlagen in öffentlichen und privaten Teams-Kanälen, einzelnen Chats und Anlagen können durchsucht werden, um Kommunikationsrisiken in Ihrer Organisation zu minimieren. Weitere Informationen zum Konfigurieren von Richtlinien zum Erkennen, Erfassen und Ergreifen von Maßnahmen für unangemessene Teams-Kommunikationen finden Sie unter Kommunikationskonformität [in Microsoft 365.](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance)

### <a name="retention-policies"></a>Aufbewahrungsrichtlinien

Aufbewahrungsrichtlinien in Microsoft Teams ermöglichen es Ihnen, sowohl Daten zu speichern, die für Ihre Organisation wichtig sind, aus gesetzlichen, rechtlichen, geschäftlichen oder anderen Gründen zu behalten, als auch Inhalte und Kommunikationen zu entfernen, die für die Aufbewahrung nicht relevant sind. Sie können Aufbewahrungsrichtlinien auch verwenden, um Daten für einen Bestimmten Zeitraum zu behalten und dann zu löschen. Weitere Informationen finden Sie unter [Aufbewahrungsrichtlinien in Microsoft Teams.](retention-policies.md)

## <a name="sensitivity-labels"></a>Vertraulichkeitsbezeichnungen

Wenden [Sie Vertraulichkeitsbeschriftungen](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) an, um den Zugriff auf vertrauliche Organisationsinhalte zu schützen und zu regeln, die während der Zusammenarbeit innerhalb von Teams erstellt wurden. Wenden Sie beispielsweise Bezeichnungen an, die den Datenschutz (öffentlich oder privat) von Teams konfigurieren, den Gastzugriff und die externe Freigabe steuern und den Zugriff von nicht verwalteten Geräten verwalten. Weitere Informationen finden Sie unter [Vertraulichkeitsbeschriftungen in Microsoft Teams.](sensitivity-labels.md)

### <a name="data-loss-prevention-dlp"></a>Verhinderung von Datenverlust (Data Loss Prevention, DLP)

Die Verhinderung von Datenverlust (Data Loss Prevention, DLP) in Microsoft Teams sowie der größere DLP-Story für Microsoft 365 oder Office 365 dreht sich um die Geschäftsbereitschaft, wenn es um den Schutz vertraulicher Dokumente und Daten geht. Ganz gleich, ob Sie Bedenken hinsichtlich vertraulicher Informationen in Nachrichten oder Dokumenten haben, DLP-Richtlinien können sicherstellen, dass Ihre Benutzer diese vertraulichen Daten nicht mit den falschen Personen teilen.

Informationen zur Verhinderung von Datenverlust in Teams finden Sie unter [DLP für Microsoft Teams.](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams) Ein guter Artikel für O365-DLP-Probleme ist [Übersicht über die Verhinderung von Datenverlust.](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)

### <a name="ediscovery"></a>eDiscovery

Die elektronische Ermittlung (eDiscovery) ist der elektronische Aspekt der Identifizierung, Sammlung und Erstellung elektronisch gespeicherter Informationen (ELECTRONIC Stored Information, ESI) als Reaktion auf einen Antrag auf Produktion in einer Klage oder Untersuchung. Zu den Funktionen gehören Fallmanagement, Erhaltung, Suche, Analyse und Export von Microsoft Teams-Daten. Dies schließt Zusammenfassungen für Chats, Nachrichten und Dateien sowie Besprechungen und Anrufe ein. Für Microsoft Teams-Besprechungen und -Anrufe wird eine Zusammenfassung der Ereignisse in Besprechungen und Anrufen erstellt und in der eDiscovery verfügbar gemacht.

Weitere Details zum Ausführen von Microsoft 365- oder Office 365-eDiscovery im Security Center und Compliance Center sowie zum Ausführen der Suche nach Complianceinhalten nach Microsoft 365- oder Office 365-eDiscovery finden Sie unter den folgenden Links:

 - [eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations)

 - [Inhaltssuche](https://docs.microsoft.com/microsoft-365/compliance/search-for-content)

Wir haben einen teamsspezifischen Artikel für weitere Informationen, [eDiscovery von Gast-zu-Gast-Chats.](eDiscovery-investigation.md)

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

Während eines Rechtsstreits müssen möglicherweise alle Daten, die einem Benutzer ( Custodian) oder einem Team zugeordnet sind, als unveränderlich aufbewahrt werden, damit sie als Beweismittel für den Fall verwendet werden können. Dazu können Sie entweder einen Benutzer (Benutzerpostfach) oder ein Team in den rechtlichen Halteraum setzen. Für einen rechtlichen Halteraum eines Teams kann das Postfach des Teams in den folgenden Haltefächern gespeichert werden:

- In-Place (eine Teilmenge des Postfachs oder der Websitesammlung durch gezielte Abfragen oder gefilterte Inhalte wird in den Haltebereich verschoben) oder
- Rechtsstreitigkeiten (das gesamte Postfach oder die gesamte Websitesammlung wird in den Halteraum gesetzt).

In beiden Fällen wird nach dem Festlegen des Haltefelds sichergestellt, dass unveränderliche Kopien dieses Inhalts beibehalten und über die eDiscovery-Suche zur Verfügung stehen, auch wenn Endbenutzer Kanalnachrichten löschen oder bearbeiten, die sich im Gruppenpostfach befinden. Gesetzliche Halte halte werden im Allgemeinen im Kontext eines eDiscovery-Falls angewendet.

Weitere Informationen zur Erhaltung [und](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) Aufbewahrung im Microsoft 365 Compliance Center finden Sie unter Übersicht über Aufbewahrungsrichtlinien. Für weitere teamsspezifische Informationen zum rechtlichen Halteraum haben wir außerdem einen [Microsoft Teams-Benutzer](legal-hold.md) oder ein Microsoft Teams in einen rechtlichen Halteraum, damit Sie mehr erfahren können.

### <a name="compliance-content-search"></a>Compliancesuche in Inhalten

Die Inhaltssuche kann verwendet werden, um über umfangreiche Filterfunktionen nach allen Teams-Daten zu suchen. Die resultierenden Daten können zur Unterstützung von Compliance- und Rechtsstreitigkeiten in einen bestimmten Container exportiert werden. Dies kann mit oder ohne eDiscovery-Fall geschehen. Auf diese Weise können Complianceadministratoren Microsoft Teams-Daten für alle Benutzer sammeln, überprüfen und zur weiteren Verarbeitung exportieren. Weitere Informationen [zum](https://docs.microsoft.com/microsoft-365/compliance/content-search) Durchführen einer Complianceinhaltssuche für Microsoft Teams und andere Microsoft 365- oder Office 365-Inhalte im Microsoft 365 Compliance Center finden Sie unter Inhaltssuche.

> [!TIP]
> Mithilfe der Inhaltssuche können Sie bei Bedarf nur nach Inhalten von Microsoft Teams filtern, z. B. Chat- und Kanalnachrichten, Besprechungen und Anrufe.

Wenn Sie weitere teamsspezifische Informationen zum Konfigurieren der Inhaltssuche erhalten möchten, überprüfen Sie die [Inhaltssuche in Microsoft Teams.](content-search.md)

### <a name="auditing-and-reporting"></a>Überwachung und Berichterstellung

Die Überwachungsprotokollsuche wird direkt in das Microsoft 365 Compliance Center angeschlossen und bietet Ihnen die Möglichkeit, Benachrichtigungen sowie Berichte zu Überwachungsereignissen zu erstellen, indem sie den Export von workloadspezifischen oder generischen Ereignissätzen für die Verwendung und Untersuchung von Administratoren über eine unbegrenzte Zeitachse für die Überwachung ermöglichen. Sie können Benachrichtigungen für alle Überwachungsprotokolldaten im Microsoft 365 Compliance Center einrichten und diese Daten zur weiteren Analyse filtern und exportieren. Weitere Informationen [zum](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) Durchführen einer Überwachungsprotokollsuche für Microsoft 365 oder Office 365 finden Sie unter Durchsuchen des Überwachungsprotokolls. Wenn Sie mehr über die Suche nach Microsoft Teams-Ereignissen im Microsoft 365 Compliance Center erfahren möchten, haben wir auch die Überwachung [in Teams](audit-log-events.md) aktiviert, die Sie überprüfen können.

## <a name="customer-key"></a>Kundenschlüssel

Microsoft 365 bietet zusätzlich zur Dienstverschlüsselung eine zusätzliche Verschlüsselungsebene für Ihre Inhalte. Mithilfe von schlüsseln, die Sie bereitstellen, verschlüsselt Customer Key verschiedene Datentypen in Microsoft Teams. Mithilfe des Kundenschlüssels auf Anwendungsebene verschlüsselt Customer Key in SharePoint Online gespeicherte Teams-Dateien. Informationen finden Sie unter [Dienstverschlüsselung mit Kundenschlüssel](https://docs.microsoft.com/microsoft-365/compliance/customer-key-overview). 

Mithilfe des Kundenschlüssels auf Mandantenebene verschlüsselt Customer Key:
- Teams-Chatnachrichten (1:1-Chats, Gruppenchats, Besprechungschats und Kanalunterhaltungen)
- Mediennachrichten von Teams (Bilder, Codeausschnitte, Videos und Wikibilder)
- Im Speicher von Teams gespeicherte Anruf- und Besprechungsaufzeichnungen von Teams
- Teams-Chatbenachrichtigungen
- Vorschläge für Teamschats von Cortana
- Statusmeldungen zu Teams Weitere Informationen finden Sie unter Übersicht über den Kundenschlüssel für [Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/customer-key-tenant-level) auf Mandantenebene, und lesen Sie den Microsoft Teams-Blog, der den Support für Kundenschlüssel für Microsoft Teams jetzt [in Public Preview behandelt.](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/customer-key-support-for-microsoft-teams-now-in-public-preview/ba-p/1999893) Informationen zur Microsoft Information Protection-Version, die Kundenschlüssel auf Mandantenebene enthält, finden Sie unter Ankündigung neuer Microsoft Information Protection-Funktionen, um Ihre vertraulichen Daten zu kennen und [zu schützen.](https://techcommunity.microsoft.com/t5/microsoft-security-and/announcing-new-microsoft-information-protection-capabilities-to/ba-p/1999692)

## <a name="privacy"></a>Datenschutz

Bei Microsoft hat der Schutz Ihrer Daten oberste Priorität. Weitere Informationen zu unseren Datenschutzpraktiken finden Sie unter:  

- [Datenschutz bei Microsoft](https://www.microsoft.com/trust-center/privacy)
- [Unser Engagement für Datenschutz und Sicherheit in Microsoft Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/04/06/microsofts-commitment-privacy-security-microsoft-teams/)
- [Für IT-Experten: Datenschutz und Sicherheit in Microsoft Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/04/06/it-professionals-privacy-security-microsoft-teams/#:~:text=We%20safeguard%20your%20privacy%20by,and%20distribution%20of%20your%20data.)

## <a name="information-protection-architecture"></a>Architektur für den Informationsschutz

Die folgende Abbildung zeigt den Ablauf der Erfassung von Microsoft Teams-Daten (Microsoft Teams-Dateien und -Nachrichten) in Exchange und SharePoint.

> [!div class="mx-imgBorder"]
> ![Diagramm des Workflows von Microsoft Teams-Daten zu Exchange und SharePoint](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)

Die folgende Abbildung zeigt den Ablauf der Erfassung von Daten aus Microsoft Teams-Besprechungen und -Anrufen in Exchange.

> [!div class="mx-imgBorder"]
> ![Diagramm des Workflows von Daten aus Microsoft Teams-Besprechungen und -Anrufen zu Exchange](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1a.png)

> [!IMPORTANT]
> Beim Ermitteln von Microsoft Teams-Inhalten ist eine Verzögerung von bis zu 24 Stunden möglich.

## <a name="licensing"></a>Lizenzierung

Wenn es um Informationsschutzfunktionen geht, bestimmen Microsoft 365-Abonnements, Office 365-Abonnements und die zugehörigen eigenständigen Lizenzen den verfügbaren Featuresatz.

Informationen zum Ermitteln der Lizenzierungsanforderungen zum Implementieren von Features für Sicherheit und Compliance finden Sie in den Lizenzierungsanforderungen [für](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance) Sicherheits- und Compliancefeatures.

> [!NOTE]
> Inhaltssuche und eDiscovery müssen nicht im Security & Compliance Center aktiviert sein, um funktionieren zu können.

## <a name="location-of-data-in-teams"></a>Speicherort von Daten in Microsoft Teams

Daten in Teams befinden sich in der geografischen Region, die Ihrer Microsoft 365- oder Office 365-Organisation zugeordnet ist. Wenn Sie sehen können, welche Regionen derzeit unterstützt werden, lesen Sie [Standort von Daten in Microsoft Teams.](location-of-data-in-teams.md)

Wenn Sie sehen müssen, in welcher Region Daten für Ihren Mandanten gespeichert sind, wechseln Sie zum [Microsoft 365 Admin Center](https://portal.office.com/adminportal/home)  >  **Settings**  >  **Organization-Profil.** Blättern Sie nach unten zu **Datenspeicherort**.

> [!div class="mx-imgBorder"]
> ![Screenshot der Tabelle "Datenspeicherort" einschließlich Teams im Admin Center](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="compliance-standards"></a>Compliancestandards

Teams verwendet die folgenden Standards: [ISO 27001](https://docs.microsoft.com/microsoft-365/compliance/offering-iso-27001), [ISO 27018](https://docs.microsoft.com/microsoft-365/compliance/offering-iso-27018), [SSAE18 SOC 1 und SOC 2,](https://docs.microsoft.com/microsoft-365/compliance/offering-soc) [HIPAA](https://docs.microsoft.com/microsoft-365/compliance/offering-hipaa-hitech)und [EU Model Clauses (EUMC).](https://docs.microsoft.com/microsoft-365/compliance/offering-eu-model-clauses) Im Microsoft Compliance Framework unterteilt Microsoft Microsoft 365- und Office 365-Anwendungen und -Dienste in vier Kategorien. Jede Kategorie wird durch bestimmte Complianceverpflichtungen definiert, die erfüllt werden müssen, damit ein Microsoft 365- oder Office 365-Dienst oder ein zugehöriger Microsoft-Dienst in dieser Kategorie aufgeführt werden kann.

Details finden Sie in den [Datenschutzressourcen.](https://servicetrust.microsoft.com/ViewPage/TrustDocumentsV3?command=Download&downloadType=Document&downloadId=b7d05b86-c69b-41ba-8245-21161b9febf9&tab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913&docTab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913_Compliance_Guides) Teams unterstützt auch cloud security alliance compliance.

## <a name="related-topics"></a>Verwandte Themen

[Microsoft 365 Security](https://docs.microsoft.com/microsoft-365/security/)

[Microsoft 365 Compliance](https://docs.microsoft.com/microsoft-365/compliance/)

[Microsoft Compliance-Angebote](https://docs.microsoft.com/microsoft-365/compliance/offering-home)
