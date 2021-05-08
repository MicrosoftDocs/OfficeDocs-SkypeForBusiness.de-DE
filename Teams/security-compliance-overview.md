---
title: Übersicht über Sicherheit und Compliance
author: laurawi
ms.author: laurawi
manager: laurawi
ms.topic: conceptual
ms.service: msteams
ms.reviewer: anwara
audience: admin
description: Eine Übersicht über Microsoft Teams Sicherheits- und Compliancefunktionen, einschließlich Datenschutz und Verschlüsselung, Überwachung und Berichterstellung und mehr.
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
ms.openlocfilehash: bfa593aaeabe8d7aab9446a1070134b267ea6ef4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51107611"
---
# <a name="security-and-compliance-in-microsoft-teams"></a>Sicherheit und Compliance in Microsoft Teams

> [!IMPORTANT]
> Lesen Sie die folgenden Artikel, um zu erfahren, wie Sie die Sicherheit während des **COVID-19-Virenausbruchs** für alle Zu Hause am besten sicherstellen können:
>  - [Die wichtigsten 12 Aufgaben für Sicherheitsteams zur Unterstützung der Arbeit von zu Hause aus](/microsoft-365/security/top-security-tasks-for-remote-work)
>  - [Optimieren der Microsoft 365- oder Office 365-Konnektivität für Remotebenutzer mithilfe des geteilten VPN-Tunnels](/Office365/Enterprise/office-365-vpn-split-tunnel)
>  - Aktualisiert am 2. April 2020: [Teams Sicherheitshandbuch](teams-security-guide.md)


Microsoft Teams ist auf der Microsoft 365 und Office 365 Hyper-Scale-Cloud auf Unternehmensklasse aufgebaut und bietet so die erweiterten Sicherheits- und Compliancefunktionen, die unsere Kunden erwarten. Wenn Sie weitere Informationen zur Planung der Sicherheit in Microsoft 365 oder [Office 365,](/microsoft-365/security/office-365-security/security-roadmap) ist die Sicherheits roadmap ein guter Einstiegsort. Weitere Informationen zur Planung der Compliance in Microsoft 365 oder Office 365 finden Sie unter Planen von & [Compliance.](/microsoft-365/compliance/plan-for-security-and-compliance)


Dieser Artikel enthält weitere Informationen zu Teams Sicherheits- und Compliance-spezifisch sind. Verpassen Sie nicht diese Microsoft Mechanics-Videos zu Sicherheit und Compliance:

- [Microsoft Teams Essentials für IT: Sicherheit und Compliance](https://youtu.be/91lHNKVVvQ4) (12:42 Min.)
- [Microsoft Teams steuerelemente für Sicherheit und Compliance](https://www.youtube.com/watch?v=Km4T4hMM__k) (10:54 Min.)

> [!IMPORTANT]
> Als Kunde von Microsoft 365 oder Office 365 sie ihre Daten besitzen und steuern. Microsoft verwendet Ihre Daten nur für die Bereitstellung des Diensts, den Sie abonniert haben. Als Dienstanbieter scannen wir nicht Ihre E-Mails, Dokumente oder Teams zu Werbezwecken oder zu Zwecken, die nicht dienstbezogene sind. Microsoft hat keinen Zugriff auf hochgeladene Inhalte. Wie OneDrive und SharePoint in Microsoft 365 bleiben die Kundendaten im Mandanten. Weitere Informationen zu vertrauenswürdigen und sicherheitsrelevanten Informationen finden Sie im [Microsoft Trust Center.](https://microsoft.com/trustcenter) Microsoft Teams folgt den gleichen Leitlinien und Prinzipien wie das Microsoft Trust Center.

## <a name="security"></a>Sicherheit

Teams werden teamweite und organisationsweite zweistufige Authentifizierung, einmaliges Anmelden über Active Directory und Verschlüsselung der übertragenen Daten und der ruhenden Daten erzwungen. Dateien werden in SharePoint gespeichert und mit dem entsprechenden SharePoint-Mechanismus verschlüsselt. Notizen werden in OneNote gespeichert und mit dem entsprechenden OneNote-Mechanismus verschlüsselt. Die OneNote-Daten werden auf der SharePoint-Website des Teams gespeichert. Die Registerkarte Wiki kann auch zum Erstellen von Notizen verwendet werden, und ihr Inhalt wird auch auf der Teamwebsite SharePoint gespeichert.

Lesen [Sie Identitätsmodelle und Authentifizierung,](identify-models-authentication.md) um mehr [](sign-in-teams.md) Einblicke in die Authentifizierung und Teams und die Funktionsweise der modernen Authentifizierung insbesondere bei der modernen Authentifizierung zu erhalten.

Da Teams in Partnerschaft mit SharePoint, OneNote, Exchange und weiteren mehr arbeiten, sollten Sie mit der Verwaltung der Sicherheit in Microsoft 365 oder Office 365 all-up arbeiten. Weitere Informationen finden Sie unter Konfigurieren Ihrer Organisation [Microsoft 365 oder Office 365 für erhöhte Sicherheit.](/office365/securitycompliance/tenant-wide-setup-for-increased-security)

> [!NOTE]
> Derzeit unterstützen [private Kanäle](private-channels.md) eingeschränkte Sicherheits- und Compliancefeatures. Unterstützung für den vollständigen Satz von Sicherheits- und Compliancefeatures in privaten Kanälen wird in Kürze folgen.

### <a name="advanced-threat-protection-atp"></a>ATP (Advanced Threat Protection)

ATP (Advanced Threat Protection) ist für Microsoft Teams sowie für SharePoint- und OneDrive-Anwendungen verfügbar, die in Teams für Inhaltsverwaltung integriert sind. ATP ermöglicht es Ihnen, zu ermitteln, ob Inhalte in diesen Anwendungen schädlich sind, und diesen Inhalt für den Benutzerzugriff zu blockieren.

Wie der betroffene Inhalt nach Erkennung verwaltet wird, ist bis zu den Einstellungen, die Sie in der Microsoft 365 Oder Office 365. Es wird dringend empfohlen, alle Anwendungen in Erwägung zu ziehen, wenn es um die Konfiguration von ATP geht. Zur weiteren Lektüre erhalten ATP für [SharePoint, OneDrive](/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams) und Microsoft Teams detaillierte Informationen zu den ersten Schritte.

### <a name="safe-links"></a>Sichere Links

Derzeit stehen sichere ATP-Links (Advanced Threat Protection) in Microsoft Teams nicht zur Verfügung, sie werden jetzt über unser Technology Adoption Program (TAP) als Public Preview angezeigt, und während ein Veröffentlichungsdatum für die allgemeine Verfügbarkeit nicht festgelegt ist, wird dieser Artikel zu diesem Zeitpunkt aktualisiert. [](/microsoft-365/security/office-365-security/atp-safe-links-for-teams?view=o365-worldwide) Informationen zu sicheren Links Microsoft 365 finden Office 365 in der Zwischenzeit unter [SICHERE ATP-Links.](/office365/securitycompliance/atp-safe-links#how-to-get-atp-safe-links-protection) Sichere ATP-Links sind sowohl in [ATP Plan 1 als auch in ATP Plan 2 verfügbar.](/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide)

### <a name="safe-attachments"></a>Sichere Anlagen

Sichere Anlagen sind ein Feature, mit dem die Sicherheit von Benutzern erhöht werden soll, indem auf schädliche Anlagen überprüft und diese erkannt werden. Globale oder Sicherheitsadministratoren erstellen Richtlinien für die Behandlung dieser verdächtigen bösartigen Anlagen, um zu verhindern, dass sie an Benutzer gesendet, darauf geklickt und auf sie reagiert werden. [](/microsoft-365/security/office-365-security/set-up-atp-safe-attachments-policies?view=o365-worldwide) Sicherer Anlagenschutz ist für SharePoint, OneDrive und Microsoft Teams verfügbar, und Microsoft 365 oder Office 365 Advanced [Threat Protection Plan 1](/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) und 2 verfügen über diese Funktion. Weitere Informationen zu sicheren Anlagen und dazu, wie diese zum Schutz Ihrer Organisation beitragen können, finden Sie unter Sichere Anlagen [in Microsoft Defender für Office 365.](/microsoft-365/security/office-365-security/atp-safe-attachments?view=o365-worldwide)

### <a name="secure-score"></a>Secure Score

Microsoft Secure Score ist eine Messung der Sicherheitshaltung einer Organisation, mit einer höheren Zahl, die mehr Verbesserungsmaßnahmen angibt. Sie finden ihn im Microsoft 365 [Security Center](https://security.microsoft.com/securescore). Wenn Sie den Secure Score-Empfehlungen folgen, können Sie Ihre Organisation vor Bedrohungen schützen. Über ein zentrales Dashboard im Microsoft 365 Security Center können Organisationen die Sicherheit ihrer Microsoft 365-Identitäten, Apps und Geräte überwachen und bearbeiten. Microsoft Teams gibt nun Empfehlungen zu Secure Score, und Administratoren werden empfohlen, ihre Sicherheitsrisiken auf der Plattform zu überwachen.

Secure Score hilft Organisationen bei:
- Berichten Sie über den aktuellen Status der Sicherheitshaltung der Organisation.
- Verbessern Sie ihre Sicherheitshaltung, indem Sie Aufblick, Sichtbarkeit, Anleitungen und Kontrolle bereitstellen.
- Vergleichen Sie sich mit Benchmarks, und richten Sie Key Performance Indicators (KPIs) ein.


### <a name="how-conditional-access-policies-work-for-teams"></a>Funktionsweise von Richtlinien für den bedingten Teams

Microsoft Teams basiert in den wichtigsten Produktivitätsszenarien wie Besprechungen, Kalendern, Inop-Chats und Dateifreigaben in hohem Maße auf Exchange Online, SharePoint und Skype for Business Online. Richtlinien für bedingten Zugriff, die für diese Cloud-Apps festgelegt wurden, gelten auch für Microsoft Teams, wenn sich Benutzer direkt bei Microsoft Teams anmelden – unabhängig vom Client.

Microsoft Teams wird separat als Cloud-App in Azure Active Directory-Richtlinien für bedingten Zugriff unterstützt. Richtlinien für bedingten Zugriff, die für die Microsoft Teams-Cloud-App festgelegt wurden, gelten auch für Microsoft Teams, wenn sich Benutzer anmelden. Allerdings können Benutzer ohne die richtigen Richtlinien für andere Apps wie Exchange Online und SharePoint möglicherweise weiterhin direkt auf diese Ressourcen zugreifen. Weitere Informationen zum Einrichten einer Richtlinie für bedingten Zugriff im Azure-Portal finden Sie unter [Azure Active Directory.](/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)

Microsoft Teams-Desktopclients für Windows und Mac unterstützen moderne Authentifizierung. Moderne Authentifizierung ermöglicht plattformübergreifend die Anmeldung auf der Grundlage von ADAL (Azure Active Directory Authentication Library, Active Directory-Authentifizierungsbibliothek) in Microsoft Office-Clientanwendungen.

Die Microsoft Teams-Desktopanwendung unterstützt AppLocker.  Weitere Informationen zu appLocker-Voraussetzungen finden Sie unter Anforderungen für die Verwendung von [AppLocker.](/windows/security/threat-protection/windows-defender-application-control/applocker/requirements-to-use-applocker)

## <a name="compliance"></a>Compliance

Teams bietet eine breite Palette von Informationen, die Ihnen bei Compliancebereichen helfen, einschließlich Kommunikationskonformität für Kanäle, Chats und Anlagen, Aufbewahrungsrichtlinien, Schutz vor Datenverlust (Data Loss Protection, DLP), eDiscovery und gesetzliche Aufbewahrung für Kanäle, Chats und Dateien, Überwachungsprotokollsuche und Verwaltung mobiler Anwendungen mit Microsoft Intune. Wir haben einige Informationen zu allen diesen Themen weiter unten bereitgestellt, und Sie können zum [Microsoft 365 Compliance Center](https://compliance.microsoft.com) wechseln, um diese Einstellungen zu verwalten.

### <a name="information-barriers"></a>Informationsbarrieren

Informationsbarrieren sind Richtlinien, die von Teams-Administratoren eingerichtet werden, um beispielsweise dafür zu sorgt, dass Personen oder Gruppen nicht miteinander kommunizieren können (wenn dies nicht vom Unternehmen benötigt wird oder wenn dies aus gesetzlichen Gründen nicht möglich ist), und ermöglicht Ihnen außerdem das Festlegen von Richtlinien für Dinge wie Nachschlage- und eDiscovery (siehe unten). Diese Richtlinien können sich auf Benutzer in 1:1-Chats, Gruppenchats oder auf Teamebene auswirken. Das Feature Informationsbarriere ist in der öffentlichen Cloud verfügbar und ab Januar 2021 in der Cloud GCC verfügbar.

Weitere Informationen zu diesem Thema finden Sie unter [Informationsbarrieren in Microsoft Teams.](information-barriers-in-teams.md)

### <a name="communication-compliance"></a>Kommunikationscompliance

Kommunikationskonformität in Microsoft 365 ermöglicht es Ihnen, Benutzer zu Richtlinien für den Bereich hinzuzufügen, die so konfiguriert werden können, dass Microsoft Teams-Kommunikation auf anstößige Sprache, vertrauliche Informationen und Informationen im Zusammenhang mit internen und behördlichen Standards untersucht wird. Chatkommunikationen und zugehörige Anlagen sowohl in öffentlichen als auch in privaten Teams-Kanälen, einzelnen Chats und Anlagen können überprüft werden, um die Kommunikationsrisiken in Ihrer Organisation zu minimieren. Weitere Informationen dazu, wie Sie Richtlinien konfigurieren können, mit deren Hilfe Sie unangemessene Kommunikationen erkennen, erfassen und Maßnahmen ergreifen können, Teams sie unterstützen, finden Sie unter Kommunikationskonformität [in Microsoft 365.](/microsoft-365/compliance/communication-compliance)

### <a name="retention-policies"></a>Aufbewahrungsrichtlinien

Aufbewahrungsrichtlinien in Microsoft Teams ermöglichen ihnen sowohl die Aufbewahrung von Daten, die für Ihre Organisation wichtig sind, aus gesetzlichen, rechtlichen, geschäftlichen oder anderen Gründen als auch das Entfernen von Inhalten und Kommunikationen, die für die Beibehaltung nicht relevant sind. Mithilfe von Aufbewahrungsrichtlinien können Sie Daten auch für einen bestimmten Zeitraum behalten und dann löschen. Weitere Informationen finden Sie unter [Aufbewahrungsrichtlinien in Microsoft Teams.](retention-policies.md)

## <a name="sensitivity-labels"></a>Vertraulichkeitsbezeichnungen

Wenden Sie [Vertraulichkeitsbezeichnungen](/microsoft-365/compliance/sensitivity-labels) an, um den Zugriff auf vertrauliche Organisationsinhalte zu schützen und zu regulieren, die während der Zusammenarbeit innerhalb von Teams erstellt wurden. So können Sie beispielsweise Bezeichnungen anwenden, die den Datenschutz (öffentlich oder privat) von Teams konfigurieren, den Gastzugriff und die externe Freigabe steuern sowie den Zugriff von nicht verwalteten Geräten verwalten. Weitere Informationen finden Sie unter [Vertraulichkeitsbeschriftungen in Microsoft Teams.](sensitivity-labels.md)

### <a name="data-loss-prevention-dlp"></a>Verhinderung von Datenverlust (Data Loss Prevention, DLP)

Die Verhinderung von Datenverlust (Data Loss Prevention, DLP) in Microsoft Teams sowie der größere DLP-Artikel für Microsoft 365 oder Office 365 drehen sich um die Geschäftsbereitschaft, wenn es um den Schutz vertraulicher Dokumente und Daten geht. Ganz gleich, ob Sie Bedenken hinsichtlich vertraulicher Informationen in Nachrichten oder Dokumenten haben, DLP-Richtlinien können sicherstellen, dass Ihre Benutzer diese vertraulichen Daten nicht mit den falschen Personen teilen.

Informationen zur Verhinderung von Datenverlust in Teams finden Sie unter [DLP für Microsoft Teams.](/microsoft-365/compliance/dlp-microsoft-teams) Ein guter Artikel für O365 DLP-Probleme ist [Die Übersicht über die Verhinderung von Datenverlust.](/microsoft-365/compliance/data-loss-prevention-policies)

### <a name="ediscovery"></a>eDiscovery

Electronic Discovery oder eDiscovery ist der elektronische Aspekt der Identifizierung, Erfassung und Erstellung elektronisch gespeicherter Informationen als Reaktion auf eine Produktionsanforderung in einer Rechtsklage oder -untersuchung. Zu den Funktionen gehören Fallmanagement, Erhaltung, Suche, Analyse und Export von Microsoft Teams-Daten. Dies schließt Zusammenfassungen für Chats, Nachrichten und Dateien sowie Besprechungen und Anrufe ein. Für Microsoft Teams-Besprechungen und -Anrufe wird eine Zusammenfassung der Ereignisse in Besprechungen und Anrufen erstellt und in der eDiscovery verfügbar gemacht.

Weitere Details zur Ausführung von Microsoft 365- oder Office 365-eDiscovery im Security Center und Compliance Center und zum Ausführen von Complianceinhaltssuchen nach Teams-Inhalten finden Sie unter den folgenden Links:

 - [eDiscovery](/microsoft-365/compliance/manage-legal-investigations)

 - [Inhaltssuche](/microsoft-365/compliance/search-for-content)

Wir haben einen Teams-spezifischen Artikel für weitere Informationen, [eDiscovery von Gast-zu-Gast-Chats.](eDiscovery-investigation.md)

Kunden können eDiscovery [oder](/microsoft-365/compliance/office-365-advanced-ediscovery) Advanced eDiscovery ihren Anforderungen entsprechen. In der folgenden Tabelle sind die Unterschiede zwischen den beiden Funktionen aufgeführt:

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

Im Rahmen eines Rechtsstreits müssen möglicherweise alle mit einem Benutzer (Bzw. Bzw. einem Team) verbundenen Daten als unveränderlich beibehalten werden, damit sie als Nachweise für den Fall verwendet werden können. Sie können dies tun, indem Sie entweder einen Benutzer (Benutzerpostfach) oder ein Team in einen gesetzlichen Halteraum setzen. Für einen gesetzlichen In-Halteraum für ein Team kann das Postfach des Teams in die folgenden Halteschleifen verschoben werden:

- In-Place (eine Teilmenge des Postfachs oder der Websitesammlung durch gezielte Abfragen oder gefilterte Inhalte wird im Haltebereich archiviert) oder
- Halteverfahren für ein Rechtsstreitigkeiten (das gesamte Postfach oder die gesamte Websitesammlung wird in den Halteraum gesetzt).

In beiden Fällen wird durch Festlegen des Halteraums sichergestellt, dass unveränderliche Kopien dieses Inhalts beibehalten und über die eDiscovery-Suche verfügbar werden, auch wenn Endbenutzer Kanalnachrichten im Gruppenpostfach löschen oder bearbeiten. Gesetzliche Halte halte werden im Allgemeinen im Kontext eines eDiscovery-Falls angewendet.

Unter Übersicht [über Aufbewahrungsrichtlinien finden](/microsoft-365/compliance/retention-policies) Sie weitere Informationen zur Erhaltung und Archivierung im Microsoft 365 Compliance Center. Für weitere Teams im gesetzlichen Halteraum steht [](legal-hold.md) Ihnen auch die gesetzliche In-Hand Microsoft Teams für einen Benutzer oder ein Team zur Verfügung, um weitere Informationen zu erhalten.

### <a name="compliance-content-search"></a>Compliancesuche in Inhalten

Die Inhaltssuche kann verwendet werden, um mithilfe von rich Teams Filterfunktionen nach allen Daten zu suchen. Die resultierenden Daten können zur Unterstützung von Compliance- und Rechtsstreitigkeiten in einen bestimmten Container exportiert werden. Dies kann mit oder ohne eDiscovery-Fall geschehen. Auf diese Weise können Complianceadministratoren Microsoft Teams-Daten für alle Benutzer sammeln, überprüfen und zur weiteren Verarbeitung exportieren. Unter Inhaltssuche finden Sie weitere Informationen zum Durchführen einer Complianceinhaltssuche nach Microsoft Teams- und anderen Microsoft 365- oder Office 365-Inhalten im Microsoft 365 Compliance Center. [](/microsoft-365/compliance/content-search)

> [!TIP]
> Mithilfe der Inhaltssuche können Sie bei Bedarf Microsoft Teams Inhalte wie Chats und Kanalnachrichten, Besprechungen und Anrufe filtern.

Wenn Sie weitere spezielle Teams zum Konfigurieren der Inhaltssuche erhalten möchten, überprüfen Sie die [Inhaltssuche in Microsoft Teams.](content-search.md)

### <a name="auditing-and-reporting"></a>Überwachung und Berichterstellung

Die Überwachungsprotokollsuche ist direkt in das Microsoft 365 Compliance Center angeschlossen und bietet Ihnen die Möglichkeit, Benachrichtigungen zu erstellen sowie Berichte zu Überwachungsereignissen zu erstellen, indem der Export von arbeitsauslastungsspezifischen oder generischen Ereignissätzen für Die Verwendung und Untersuchung durch Administratoren über eine unbegrenzte Überwachungszeitachse ermöglicht wird. Sie können Benachrichtigungen für alle Überwachungsprotokolldaten im Microsoft 365 Compliance Center einrichten und diese Daten zur weiteren Analyse filtern und exportieren. Unter Durchsuchen [des Überwachungsprotokolls finden](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) Sie weitere Informationen zum Durchführen einer Überwachungsprotokollsuche nach Microsoft 365 Überwachungsprotokollen Office 365. Weitere Informationen zum Suchen nach Microsoft Teams Ereignissen im Microsoft 365 Compliance Center finden Sie auch unter Aktivieren der Überwachung [in](audit-log-events.md) Teams die Sie überprüfen können.

## <a name="customer-key"></a>Kundenschlüssel

Microsoft 365 bietet zusätzlich zur Dienstverschlüsselung für Ihre Inhalte eine zusätzliche Verschlüsselungsebene. Mithilfe von Schlüsseln, die Sie bereitstellen, verschlüsselt der Kundenschlüssel verschiedene Arten von Daten in Microsoft Teams. Mithilfe von Kundenschlüssel auf Anwendungsebene verschlüsselt der Kundenschlüssel Teams in ihrer SharePoint Online. Weitere Informationen finden Sie unter [Dienstverschlüsselung mit Dem Kundenschlüssel.](/microsoft-365/compliance/customer-key-overview) 

Mit dem Kundenschlüssel auf Mandantenebene verschlüsselt der Kundenschlüssel:
- Teams (1:1-Chats, Gruppenchats, Besprechungschats und Kanalunterhaltungen)
- Teams (Bilder, Codeausschnitte, Videos und Wiki-Bilder)
- Teams von Anruf- und Besprechungsaufzeichnungen, die im Teams sind
- Teams von Chatbenachrichtigungen
- Teams von Cortana zu Chatvorschlägen
- Teams-Statusmeldungen Weitere Informationen finden Sie unter Übersicht über Den Kundenschlüssel für [Microsoft 365](/microsoft-365/compliance/customer-key-tenant-level) auf Mandantenebene und den Microsoft Teams-Blog, der den Kundenschlüsselsupport für Microsoft Teams jetzt in Public [Preview](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/customer-key-support-for-microsoft-teams-now-in-public-preview/ba-p/1999893)behandelt. Informationen zur Microsoft Information Protection-Version, in der Kundenschlüssel auf Mandantenebene enthalten waren, finden Sie unter Ankündigung der neuen Microsoft Information Protection-Funktionen zum Wissen und Schützen [Ihrer vertraulichen Daten.](https://techcommunity.microsoft.com/t5/microsoft-security-and/announcing-new-microsoft-information-protection-capabilities-to/ba-p/1999692)

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

Wenn es um Informationsschutzfunktionen geht, bestimmen Microsoft 365 Abonnements, Office 365 Abonnements und die zugehörigen eigenständigen Lizenzen die verfügbaren Featuresets.

Informationen zur Ermittlung der Lizenzierungsanforderungen für die Implementierung von Features für Sicherheit und Compliance finden Sie unter den [Lizenzierungsanforderungen](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance) für Sicherheits- und Compliancefunktionen.

> [!NOTE]
> Inhaltssuche und eDiscovery müssen im Security & Compliance Center nicht aktiviert sein, damit sie funktionieren.

## <a name="location-of-data-in-teams"></a>Speicherort von Daten in Microsoft Teams

Daten in Teams befinden sich in der geografischen Region, die Ihrer Microsoft 365- oder Office 365-Organisation zugeordnet ist. Um zu sehen, welche Regionen derzeit unterstützt werden, lesen Sie Speicherort [der Daten in Microsoft Teams.](location-of-data-in-teams.md)

Wenn Sie sehen möchten, welche Gebietshausdaten für Ihren Mandanten verwendet werden, wechseln Sie zum Microsoft 365 [Admin Center](https://portal.office.com/adminportal/home)  >  **Einstellungen**  >  **Organisationsprofil**. Blättern Sie nach unten zu **Datenspeicherort**.

> [!div class="mx-imgBorder"]
> ![Screenshot der Tabelle "Datenspeicherort" Teams im Admin Center](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="compliance-standards"></a>Compliancestandards

Teams verwendet die folgenden Standards: [ISO 27001,](/microsoft-365/compliance/offering-iso-27001) [ISO 27018,](/microsoft-365/compliance/offering-iso-27018) [SSAE18 SOC 1 und SOC 2,](/microsoft-365/compliance/offering-soc) [HIPAA](/microsoft-365/compliance/offering-hipaa-hitech)und [EU-Musterklauseln (EU Model Clauses, EUMC).](/microsoft-365/compliance/offering-eu-model-clauses) Innerhalb des Microsoft Compliance-Frameworks unterteilt Microsoft Microsoft 365 und Office 365 Anwendungen und Dienste in vier Kategorien. Jede Kategorie wird durch bestimmte Compliance-Verpflichtungen definiert, die erfüllt sein müssen, damit ein Microsoft 365- oder Office 365-Dienst oder ein zugehöriger Microsoft-Dienst in dieser Kategorie aufgeführt wird.

Details finden Sie in den [Datenschutzressourcen.](https://servicetrust.microsoft.com/ViewPage/TrustDocumentsV3?command=Download&downloadType=Document&downloadId=b7d05b86-c69b-41ba-8245-21161b9febf9&tab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913&docTab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913_Compliance_Guides) Teams unterstützt außerdem Cloud Security Alliance-Compliance.

## <a name="related-topics"></a>Verwandte Themen

[Microsoft 365 Sicherheit](/microsoft-365/security/)

[Microsoft 365 Compliance](/microsoft-365/compliance/)

[Microsoft Compliance-Angebote](/microsoft-365/compliance/offering-home)