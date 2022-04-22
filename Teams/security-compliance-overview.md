---
title: Übersicht über Sicherheit und Compliance
author: MSFTTracyP
ms.author: tracyp
manager: laurawi
ms.date: 04/12/2022
ms.topic: conceptual
ms.service: msteams
ms.reviewer: anwara
audience: admin
description: Eine Übersicht über Microsoft Teams Sicherheits- und Compliancefeatures, einschließlich Datenschutz und Verschlüsselung, Überwachung und Berichterstellung und vieles mehr.
ms.localizationpriority: medium
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
ms.openlocfilehash: 1c41ac53e95c179fc62b5e2e469bb614cbdcd516
ms.sourcegitcommit: 7d5266ae7e4a440ee45ab1873a30f4056bdcca1f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2022
ms.locfileid: "65031900"
---
# <a name="security-and-compliance-in-microsoft-teams"></a>Sicherheit und Compliance in Microsoft Teams

> [!IMPORTANT]
> Um zu erfahren, wie Sie **während des COVID-19-Ausbruchs die Sicherheit am besten gewährleisten können, während alle zu Hause arbeiten**, lesen Sie diese Artikel:
>  - [Die wichtigsten 12 Aufgaben für Sicherheitsteams zur Unterstützung der Arbeit von zu Hause aus](/microsoft-365/security/top-security-tasks-for-remote-work)
>  - [Optimieren der Microsoft 365- oder Office 365-Konnektivität für Remotebenutzer mithilfe des geteilten VPN-Tunnels](/Office365/Enterprise/office-365-vpn-split-tunnel)
>  - Aktualisiert am 2. April 2020: [Teams Sicherheitshandbuch](teams-security-guide.md)


Microsoft Teams basiert auf der Microsoft 365 und Office 365 Cloud auf Unternehmensniveau, die die erweiterten Sicherheits- und Compliancefunktionen bietet, die unsere Kunden erwarten. Weitere Informationen zur Planung der Sicherheit in Microsoft 365 oder Office 365 finden Sie in [der Sicherheits-Roadmap](/microsoft-365/security/office-365-security/security-roadmap). Weitere Informationen zur Planung der Compliance in Microsoft 365 oder Office 365 erhalten Sie, wenn Sie mit ["Planen der Sicherheit & Compliance](/microsoft-365/compliance/plan-for-security-and-compliance)" beginnen.


Dieser Artikel enthält weitere Informationen zu Teams-spezifischen Sicherheit und Compliance. Verpassen Sie nicht diese Microsoft Mechanics-Videos zu Sicherheit und Compliance:

- [Microsoft Teams Essentials für IT: Sicherheit und Compliance](https://youtu.be/91lHNKVVvQ4) (12:42 Min.)
- [Microsoft Teams-Steuerelemente für Sicherheit und Compliance](https://www.youtube.com/watch?v=Km4T4hMM__k) (10:54 Min.)

> [!IMPORTANT]
> Als Kunde von Microsoft 365 oder Office 365 besitzen und steuern Sie Ihre Daten. Microsoft verwendet Ihre Daten nur für den Dienst, den Sie abonniert haben. Als Dienstanbieter scannen wir Ihre E-Mails, Dokumente oder Teams nicht für Werbung oder für Zwecke, die nicht dienstbezogen sind. Microsoft hat keinen Zugriff auf hochgeladene Inhalte. Wie OneDrive und SharePoint in Microsoft 365 bleiben Kundendaten im Mandanten. Weitere Informationen zu vertrauens- und sicherheitsrelevanten Informationen finden Sie im [Microsoft Trust Center](https://microsoft.com/trustcenter). Microsoft Teams folgt den gleichen Leitlinien und Prinzipien wie das Microsoft Trust Center.

## <a name="security"></a>Sicherheit

Teams erzwingt teamweite und organisationsweite zweistufige Authentifizierung, einmaliges Anmelden über Active Directory und Verschlüsselung von Daten während der Übertragung und ruhenden Daten. Dateien werden in SharePoint gespeichert und mit dem entsprechenden SharePoint-Mechanismus verschlüsselt. Notizen werden in OneNote gespeichert und mit dem entsprechenden OneNote-Mechanismus verschlüsselt. Die OneNote-Daten werden auf der SharePoint-Website des Teams gespeichert. Die Wiki-Registerkarte kann auch zum Erstellen von Notizen verwendet werden, und ihre Inhalte werden auch innerhalb des Teams SharePoint Website gespeichert.

Lesen Sie [Identitätsmodelle und Authentifizierung](identify-models-authentication.md), um mehr Einblicke in die Authentifizierung und Teams zu erhalten, und [wie die moderne Authentifizierung funktioniert](sign-in-teams.md), hilft insbesondere bei der modernen Authentifizierung.

Da Teams in Zusammenarbeit mit SharePoint, OneNote, Exchange und mehr arbeitet, sollten Sie mit der Verwaltung von Sicherheit in Microsoft 365 oder Office 365 all-up vertraut sein. Weitere Informationen finden Sie unter [Konfigurieren Ihrer Microsoft 365 oder Office 365 Organisation für erhöhte Sicherheit](/office365/securitycompliance/tenant-wide-setup-for-increased-security).

> [!NOTE]
> Derzeit unterstützen [private Kanäle](private-channels.md) eingeschränkte Sicherheits- und Compliancefunktionen. Unterstützung für den vollständigen Satz von Sicherheits- und Compliancefunktionen in privaten Kanälen wird in Kürze verfügbar sein.

### <a name="microsoft-defender-for-office-365"></a>Microsoft Defender für Office 365

Microsoft Defender für Office 365 ist für Microsoft Teams sowie für SharePoint- und OneDrive-Anwendungen verfügbar, die in Teams für die Inhaltsverwaltung integriert sind. Defender für Office 365 können Sie ermitteln, ob Inhalte in diesen Anwendungen bösartig sind, und diese Inhalte am Benutzerzugriff hindern.

Wie der betroffene Inhalt nach der Erkennung verwaltet wird, hängt von den Einstellungen ab, die Sie in Microsoft 365 oder Office 365 ausgewählt haben. Es wird dringend empfohlen, alle Anwendungen beim Konfigurieren von Defender für Office 365 in Betracht zu ziehen. Für weitere Informationen finden Sie [hier eine Übersicht über die Funktionsweise sicherer Links und schritte zum Einrichten](/microsoft-365/security/office-365-security/safe-links?view=o365-worldwide). Hier finden Sie ausführliche Informationen zu den ersten Schritten.

### <a name="safe-links-in-microsoft-teams"></a>links in Microsoft Teams Tresor

Defender für Office 365 sichere Links sind in Microsoft Teams verfügbar. Weitere Informationen dazu, was sichere Links sind und was mit diesem Feature zu tun ist, finden Sie in den [Einstellungen für sichere Links für Teams](/microsoft-365/security/office-365-security/safe-links?view=o365-worldwide). Tresor Links sind sowohl in [Defender für Office 365 Plan 1](/microsoft-365/security/office-365-security/overview?view=o365-worldwide) als auch in Plan 2 verfügbar.

### <a name="safe-attachments"></a>Tresor Anlagen

Tresor Anlagen ist ein Feature zur Verbesserung der Benutzersicherheit, indem bösartige Anlagen gesucht und erkannt werden. Globale oder Sicherheitsadministratoren [aktivieren das Feature](/microsoft-365/security/office-365-security/turn-on-mdo-for-spo-odb-and-teams?view=o365-worldwide) und [erstellen Richtlinien](/microsoft-365/security/office-365-security/set-up-safe-attachments-policies?view=o365-worldwide) für die Behandlung dieser verdächtigen bösartigen Anlagen, um zu verhindern, dass sie an Benutzer gesendet, angeklickt und darauf reagiert werden.

Tresor Anlagenschutz ist für SharePoint, OneDrive und Microsoft Teams sowie für Microsoft 365 oder Office 365 in [ Microsoft Defender für Office 365 Plan 1 und Plan 2](/microsoft-365/security/office-365-security/overview?view=o365-worldwide). Lesen Sie in [diesem Artikel](/microsoft-365/security/office-365-security/set-up-safe-attachments-policies?view=o365-worldwide) mehr über Tresor Anlagen und wie sie Zum Schutz Ihrer Organisation beitragen können.

### <a name="secure-score"></a>Sicherheitsbewertung

Die Microsoft-Sicherheitsbewertung ist eine Messung des Sicherheitsstatus einer Organisation, wobei eine höhere Zahl auf mehr ergriffene Verbesserungsmaßnahmen hinweist. Sie befindet sich im [Microsoft 365 Security Center](https://security.microsoft.com/securescore). Das Folgen der Empfehlungen für die Sicherheitsbewertung kann Ihre Organisation vor Bedrohungen schützen. Über ein zentrales Dashboard in der Microsoft 365 Security Center können Organisationen die Sicherheit ihrer Microsoft 365 Identitäten, Apps und Geräte überwachen und daran arbeiten. Microsoft Teams hat jetzt Empfehlungen zur Sicherheitsbewertung, und Administratoren werden aufgefordert, ihre Sicherheitsposition auf der Plattform zu überwachen.

Die Sicherheitsbewertung hilft Organisationen:
- Bericht über den aktuellen Status des Sicherheitsstatus der Organisation.
- Verbessern Sie ihren Sicherheitsstatus, indem Sie Auffindbarkeit, Sichtbarkeit, Anleitung und Kontrolle bereitstellen.
- Vergleichen Sie mit Benchmarks, und legen Sie Key Performance Indicators (KPIs) fest.

### <a name="how-conditional-access-policies-work-for-teams"></a>Funktionsweise von Richtlinien für bedingten Zugriff für Teams

Microsoft Teams basiert stark auf Exchange Online, SharePoint und Skype for Business Online für wichtige Produktivitätsszenarien wie Besprechungen, Kalender, Interop-Chats und Dateifreigaben. Richtlinien für bedingten Zugriff, die für diese Cloud-Apps festgelegt wurden, gelten auch für Microsoft Teams, wenn sich Benutzer direkt bei Microsoft Teams anmelden – unabhängig vom Client.

Microsoft Teams wird separat als Cloud-App in Azure Active Directory-Richtlinien für bedingten Zugriff unterstützt. Richtlinien für bedingten Zugriff, die für die Microsoft Teams-Cloud-App festgelegt wurden, gelten auch für Microsoft Teams, wenn sich Benutzer anmelden. Ohne die richtigen Richtlinien für andere Apps wie Exchange Online und SharePoint können Benutzer jedoch möglicherweise weiterhin direkt auf diese Ressourcen zugreifen. Weitere Informationen zum Einrichten einer Richtlinie für bedingten Zugriff im Azure-Portal finden Sie [unter Azure Active Directory Schnellstart](/azure/active-directory/active-directory-conditional-access-azure-portal-get-started).

Microsoft Teams-Desktopclients für Windows und Mac unterstützen moderne Authentifizierung. Moderne Authentifizierung ermöglicht plattformübergreifend die Anmeldung auf der Grundlage von ADAL (Azure Active Directory Authentication Library, Active Directory-Authentifizierungsbibliothek) in Microsoft Office-Clientanwendungen.

Die Microsoft Teams-Desktopanwendung unterstützt AppLocker.  Weitere Informationen zu den Voraussetzungen für AppLocker finden Sie unter: Anforderungen für die Verwendung von [AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/requirements-to-use-applocker).

## <a name="compliance"></a>Compliance

Teams verfügt über eine breite Palette von Informationen, die Sie bei compliance-Bereichen unterstützen, einschließlich Kommunikationscompliance für Kanäle, Chats und Anlagen, Aufbewahrungsrichtlinien, Verhinderung von Datenverlust (Data Loss Prevention, DLP), eDiscovery und gesetzliche Aufbewahrung für Kanäle, Chats und Dateien, Überwachungsprotokollsuche sowie verwaltung mobiler Anwendungen mit Microsoft Intune. Wir haben unten einige Informationen zu all diesen Themen bereitgestellt, und Sie können zum [Microsoft 365 Compliance Center](https://compliance.microsoft.com) wechseln, um diese Einstellungen zu verwalten.

### <a name="information-barriers"></a>Informationsbarrieren

Microsoft Purview Information Barriers sind Richtlinien, die von Teams Administratoren eingerichtet wurden, um z. B. Personen oder Gruppen daran zu hindern, miteinander zu kommunizieren (wenn sie dazu keine geschäftliche Notwendigkeit haben oder einen regulatorischen Grund dafür haben), und es ermöglicht Ihnen auch, Richtlinien in Bezug auf Dinge wie Nachschlagevorgänge und eDiscovery festzulegen (siehe unten). Diese Richtlinien können sich auf Benutzer in 1:1-Chats, Gruppenchats oder auf Teamebene auswirken. Das Feature "Informationsbarriere" ist in der öffentlichen Cloud verfügbar und wurde ab Januar 2021 für die GCC Cloud eingeführt.

Weitere Informationen zu diesem Thema finden Sie [unter Informationsbarrieren in Microsoft Teams](information-barriers-in-teams.md).

### <a name="communication-compliance"></a>Kommunikationscompliance

Microsoft Purview Communication Compliance ermöglicht es Ihnen, Benutzer zu in-Scope-Richtlinien hinzuzufügen, die so konfiguriert werden können, dass Microsoft Teams Kommunikation auf anstößige Sprache, vertrauliche Informationen und Informationen im Zusammenhang mit internen und regulatorischen Standards untersucht wird. Chatkommunikation und zugehörige Anlagen in öffentlichen und privaten Teams Kanälen, einzelnen Chats und Anlagen können gescannt werden, um Kommunikationsrisiken in Ihrer Organisation zu minimieren. Weitere Informationen dazu, wie Sie Richtlinien konfigurieren können, damit Sie unangemessene Teams Kommunikation erkennen, erfassen und Maßnahmen ergreifen können, finden [Sie unter "Informationen zur Kommunikationscompliance"](/microsoft-365/compliance/communication-compliance).

### <a name="sensitivity-labels"></a>Vertraulichkeitsbezeichnungen

Wenden Sie [Vertraulichkeitsbezeichnungen](/microsoft-365/compliance/sensitivity-labels) an, um den Zugriff auf vertrauliche Organisationsinhalte zu schützen und zu regulieren, die während der Zusammenarbeit innerhalb von Teams erstellt wurden. Wenden Sie z. B. Bezeichnungen an, die den Datenschutz (öffentlich oder privat) von Teams konfigurieren, den Gastzugriff und die externe Freigabe steuern und den Zugriff von nicht verwalteten Geräten aus verwalten. Weitere Informationen hierzu unter [Vertraulichkeitsbezeichnungen in Microsoft Teams](sensitivity-labels.md).

### <a name="microsoft-purview-data-loss-prevention-dlp"></a>Microsoft Purview Data Loss Prevention (DLP)

Die Verhinderung von Datenverlust (Data Loss Prevention, DLP) in Microsoft Teams sowie die größere DLP-Story für Microsoft Purview dreht sich um die Geschäftsbereitschaft beim Schutz vertraulicher Dokumente und Daten. Unabhängig davon, ob Sie Bedenken hinsichtlich vertraulicher Informationen in Nachrichten oder Dokumenten haben, können DLP-Richtlinien sicherstellen, dass Ihre Benutzer diese vertraulichen Daten nicht für die falschen Personen freigeben.

Informationen zur Verhinderung von Datenverlust in Teams finden Sie in [DLP für Microsoft Teams](/microsoft-365/compliance/dlp-microsoft-teams). Ein guter Artikel für DLP-Bedenken ist [Informationen zur Verhinderung von Datenverlust](/microsoft-365/compliance/dlp-learn-about-dlp).

### <a name="customer-key"></a>Kundenschlüssel

Microsoft 365 bietet eine zusätzliche Verschlüsselungsschicht zusätzlich zur Dienstverschlüsselung für Ihre Inhalte. Mithilfe von von Ihnen bereitgestellten Schlüsseln verschlüsselt Customer Key verschiedene Arten von Daten in Microsoft Teams. Mithilfe von Customer Key auf Anwendungsebene verschlüsselt Customer Key Teams Dateien, die in SharePoint Online gespeichert sind. Weitere Informationen finden Sie unter [Dienstverschlüsselung mit Microsoft Purview Customer Key](/microsoft-365/compliance/customer-key-overview).

Mithilfe von Customer Key auf Mandantenebene verschlüsselt Customer Key Folgendes:
- Teams Chatnachrichten (1:1-Chats, Gruppenchats, Besprechungschats und Kanalunterhaltungen)
- Teams Mediennachrichten (Bilder, Codeausschnitte, Videos und Wiki-Bilder)
- Teams Anruf- und Besprechungsaufzeichnungen, die im Speicher Teams gespeichert sind
- Teams Chatbenachrichtigungen
- Teams von Chatvorschlägen nach Cortana
- statusmeldungen Teams

Weitere Informationen finden Sie unter [Übersicht über Customer Key auf Mandantenebene](/microsoft-365/compliance/customer-key-tenant-level) und lesen Sie den Microsoft Teams Blog, in dem der [Customer Key-Support für Microsoft Teams jetzt in der öffentlichen Vorschau](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/customer-key-support-for-microsoft-teams-now-in-public-preview/ba-p/1999893) behandelt wird. Informationen zu der Microsoft Information Protection-Version, die Customer Key auf Mandantenebene enthielt, finden Sie unter [Ankündigung neuer Microsoft Information Protection Funktionen, um Ihre vertraulichen Daten zu kennen und zu schützen](https://techcommunity.microsoft.com/t5/microsoft-security-and/announcing-new-microsoft-information-protection-capabilities-to/ba-p/1999692).

### <a name="retention-policies"></a>Aufbewahrungsrichtlinien

Aufbewahrungsrichtlinien in Microsoft Teams ermöglichen es Ihnen, sowohl Daten aufzubewahren, die für Ihre Organisation wichtig sind, aus behördlichen, rechtlichen, geschäftlichen oder anderen Gründen, als auch Inhalte und Kommunikationen zu entfernen, die nicht relevant sind, um aufbewahrt zu werden. Sie können Aufbewahrungsrichtlinien auch verwenden, um Daten für einen bestimmten Zeitraum zu speichern und dann zu löschen. Weitere Informationen hierzu erfahren Sie [in den Aufbewahrungsrichtlinien in Microsoft Teams](retention-policies.md).

### <a name="ediscovery"></a>eDiscovery

Elektronische Ermittlung oder eDiscovery ist der elektronische Aspekt der Identifizierung, Erfassung und Erstellung elektronisch gespeicherter Informationen (ELECTRONIC Stored Information, ESI) als Reaktion auf einen Antrag auf Produktion in einer Klage oder Untersuchung. Zu den Funktionen gehören Fallmanagement, Erhaltung, Suche, Analyse und Export von Microsoft Teams-Daten. Dies schließt Zusammenfassungen für Chats, Nachrichten und Dateien sowie Besprechungen und Anrufe ein. Für Microsoft Teams-Besprechungen und -Anrufe wird eine Zusammenfassung der Ereignisse in Besprechungen und Anrufen erstellt und in der eDiscovery verfügbar gemacht.

Weitere Informationen zur Verwendung von eDiscovery-Tools im Microsoft Purview Compliance-Portal, um nach Teams Inhalten zu suchen, finden Sie unter den folgenden Links:

- [eDiscovery](/microsoft-365/compliance/manage-legal-investigations)

- [Inhaltssuche](/microsoft-365/compliance/search-for-content)

Wir haben einen Teams-spezifischen Artikel für weitere Informationen unter [Durchführung einer eDiscovery-Untersuchung von Inhalten in Microsoft Teams](eDiscovery-investigation.md).

Kunden können eDiscovery oder [eDiscovery (Premium)](/microsoft-365/compliance/office-365-advanced-ediscovery) gemäß ihren Anforderungen nutzen. In der folgenden Tabelle sind die Unterschiede zwischen den beiden Funktionen aufgeführt:

|&nbsp; |eDiscovery  |eDiscovery (Premium)  |
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

Bei Rechtsstreitigkeiten müssen möglicherweise alle Daten, die einem Benutzer (Verwahrer) oder einem Team zugeordnet sind, unveränderlich aufbewahrt werden, damit sie als Beweis für den Fall verwendet werden können. Dazu können Sie entweder einen Benutzer (Benutzerpostfach) oder ein Team in die gesetzliche Aufbewahrungspflicht setzen. Für eine teamrechtliche Aufbewahrung kann das Postfach des Teams in den folgenden Haltebereichen abgelegt werden:

- In-Place Haltebereich (eine Teilmenge des Postfachs oder der Websitesammlung durch gezielte Abfragen oder gefilterte Inhalte wird in den Haltebereich gesetzt) oder
- Beweissicherungsverfahren (das gesamte Postfach oder die gesamte Websitesammlung wird in den Haltebereich gesetzt).

In beiden Fällen wird nach dem Festlegen des Haltebereichs sichergestellt, dass, auch wenn Endbenutzer Kanalnachrichten löschen oder bearbeiten, die sich im Gruppenpostfach befinden, unveränderliche Kopien dieses Inhalts beibehalten werden und über die eDiscovery-Suche verfügbar sind. Gesetzliche Aufbewahrungspflichten werden im Allgemeinen im Rahmen eines eDiscovery-Falls angewendet.

Weitere Informationen zu Erhaltung und Haltebereichen finden Sie im Microsoft Purview Compliance-Portal im [Überblick über Aufbewahrungsrichtlinien](/microsoft-365/compliance/retention-policies) . Für weitere Teams spezifische Informationen zur aufbewahrungspflichtigen Aufbewahrung haben wir auch [einen Microsoft Teams Benutzer oder ein Team in die gesetzliche Aufbewahrungspflicht](legal-hold.md), damit Sie mehr erfahren können.

### <a name="content-search"></a>Inhaltssuche

Die Inhaltssuche kann verwendet werden, um mithilfe umfangreicher Filterfunktionen nach allen Teams Daten zu suchen. Die resultierenden Daten können zur Unterstützung von Compliance und Rechtsstreitigkeiten in einen bestimmten Container exportiert werden. Dies kann mit oder ohne eDiscovery-Fall geschehen. Auf diese Weise können Complianceadministratoren Microsoft Teams-Daten für alle Benutzer sammeln, überprüfen und zur weiteren Verarbeitung exportieren. Weitere Informationen zum Durchführen einer Compliance-Inhaltssuche nach Microsoft Teams und anderen Microsoft 365 oder Office 365 Inhalten im Microsoft Purview Compliance-Portal finden Sie in der [Inhaltssuche](/microsoft-365/compliance/content-search).

> [!TIP]
> Mithilfe der Inhaltssuche können Sie nach Microsoft Teams nur Inhalt filtern, z. B. Chat- und Kanalnachrichten, Besprechungen und Anrufe, falls erforderlich.

Wenn Sie weitere Teams-spezifische Informationen zum Konfigurieren der Inhaltssuche wünschen, überprüfen Sie [die Inhaltssuche in Microsoft Teams](content-search.md).

### <a name="auditing"></a>Überwachung

Die Überwachungsprotokollsuche wird direkt in das Microsoft Purview Compliance-Portal eingebunden und bietet Ihnen die Möglichkeit, Warnungen festzulegen und über Überwachungsereignisse zu berichten, indem Sie den Export von workloadspezifischen oder generischen Ereignissätzen für die Verwendung und Untersuchung durch Administratoren über eine unbegrenzte Überwachungszeitachse hinweg zulassen. Sie können Benachrichtigungen für alle Überwachungsprotokolldaten im Microsoft Purview Compliance-Portal einrichten und diese Daten filtern und exportieren, um weitere Analysen durchzuführen. Weitere Informationen zum Suchen nach Microsoft Teams Ereignissen im Microsoft Purview Compliance-Portal finden [Sie unter Durchsuchen des Überwachungsprotokolls nach Ereignissen in Microsoft Teams](audit-log-events.md).

## <a name="privacy"></a>Datenschutz

Bei Microsoft hat der Schutz Ihrer Daten höchste Priorität. Weitere Informationen zu unseren Datenschutzpraktiken finden Sie unter:  

- [Datenschutz bei Microsoft](https://www.microsoft.com/trust-center/privacy)
- [Unser Engagement für Datenschutz und Sicherheit in Microsoft Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/04/06/microsofts-commitment-privacy-security-microsoft-teams/)
- [Für IT-Experten: Datenschutz und Sicherheit in Microsoft Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/04/06/it-professionals-privacy-security-microsoft-teams/#:~:text=We%20safeguard%20your%20privacy%20by,and%20distribution%20of%20your%20data.)

## <a name="information-protection-architecture"></a>Information Protection Architektur

Die folgende Abbildung zeigt den Ablauf der Erfassung von Microsoft Teams-Daten (Microsoft Teams-Dateien und -Nachrichten) in Exchange und SharePoint.

> [!div class="mx-imgBorder"]
> ![Diagramm des Workflows von Teams Daten zum Exchange und SharePoint.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)

Die folgende Abbildung zeigt den Ablauf der Erfassung von Daten aus Microsoft Teams-Besprechungen und -Anrufen in Exchange.

> [!div class="mx-imgBorder"]
> ![Diagramm des Workflows von Teams Besprechungen und Anrufdaten für Exchange.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1a.png)

> [!IMPORTANT]
> Beim Ermitteln von Microsoft Teams-Inhalten ist eine Verzögerung von bis zu 24 Stunden möglich.

## <a name="licensing"></a>Lizenzierung

Wenn es um Informationsschutzfunktionen geht, bestimmen Microsoft 365 Abonnements, Office 365 Abonnements und die zugehörigen eigenständigen Lizenzen den verfügbaren Featuresatz.

Informationen zum Ermitteln der Lizenzierungsanforderungen zur Implementierung von Features für Sicherheit und Compliance finden Sie in den [Lizenzierungsanforderungen](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance) für Sicherheits- und Compliancefeatures.

> [!NOTE]
> Inhaltssuche, eDiscovery (Standard) und eDiscovery (Premium) müssen nicht im Microsoft Purview-Complianceportal aktiviert sein, damit sie funktionieren. Weitere Informationen finden Sie [unter Microsoft 365 eDiscovery-Lösungen](/microsoft-365/compliance/ediscovery).

## <a name="location-of-data-in-teams"></a>Speicherort von Daten in Microsoft Teams

Daten in Teams befinden sich in der geografischen Region, die Ihrer Microsoft 365- oder Office 365-Organisation zugeordnet ist. Um zu sehen, welche Regionen derzeit unterstützt werden, lesen Sie bitte den [Speicherort der Daten in Microsoft Teams](location-of-data-in-teams.md).

Wenn Sie sehen müssen, in welcher Region Daten für Ihren Mandanten enthalten sind, wechseln Sie zum [Profil Microsoft 365 Admin Center](https://portal.office.com/adminportal/home) >  **Einstellungen** >  **Organization**. Blättern Sie nach unten zu **Datenspeicherort**.

> [!div class="mx-imgBorder"]
> ![Screenshot der Datenspeicherorttabelle einschließlich Teams im Admin Center.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="compliance-standards"></a>Compliancestandards

Teams verwendet die folgenden Standards: [ISO 27001](/microsoft-365/compliance/offering-iso-27001), [ISO 27018](/microsoft-365/compliance/offering-iso-27018), [SSAE18 SOC 1 und SOC 2](/microsoft-365/compliance/offering-soc), [HIPAA](/microsoft-365/compliance/offering-hipaa-hitech) und [EU Model Clauses (EUMC)](/microsoft-365/compliance/offering-eu-model-clauses). Im Microsoft Compliance Framework klassifiziert Microsoft Microsoft 365 und Office 365 Anwendungen und Dienste in vier Kategorien. Jede Kategorie wird durch bestimmte Complianceverpflichtungen definiert, die erfüllt werden müssen, damit ein Microsoft 365- oder Office 365-Dienst oder ein zugehöriger Microsoft-Dienst in dieser Kategorie aufgeführt wird.

Details finden Sie in den [Datenschutzressourcen](https://servicetrust.microsoft.com/ViewPage/TrustDocumentsV3?command=Download&downloadType=Document&downloadId=b7d05b86-c69b-41ba-8245-21161b9febf9&tab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913&docTab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913_Compliance_Guides). Teams unterstützt auch die Compliance der Cloud Security Alliance.

## <a name="related-topics"></a>Verwandte Themen

[Microsoft 365 Sicherheit](/microsoft-365/security/)

[Microsoft 365 Compliance](/microsoft-365/compliance/)

[Microsoft Compliance-Angebote](/microsoft-365/compliance/offering-home)
