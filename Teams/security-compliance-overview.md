---
title: Übersicht über Sicherheit und Compliance in Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: anach
audience: admin
description: Eine Übersicht über die Sicherheits- und Compliance-Funktionen von Microsoft Teams, einschließlich Überwachung und Berichterstellung, Compliancesuche in Inhalten, eDiscovery und vielem mehr.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.securityandcompliance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 45e4c49824df9a098af5251d13234eae48db5619
ms.sourcegitcommit: 152eb7daacd0a36f42aa441633c12c7037a0969a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2020
ms.locfileid: "42288623"
---
# <a name="security-and-compliance-in-microsoft-teams"></a>Sicherheit und Compliance in Microsoft Teams

> [!IMPORTANT]
> Als Kunde von Office 365 besitzen und Steuern Sie Ihre Daten. Microsoft verwendet Ihre Daten nicht für etwas anderes als die Bereitstellung des von Ihnen abonnierten Diensts. Als Dienstanbieter scannen wir Ihre e-Mails, Dokumente oder Teams nicht für Werbung oder für Zwecke, die nicht Dienst bezogen sind. Microsoft hat keinen Zugriff auf Hochgeladene Inhalte. Wie OneDrive for Business und SharePoint Online bleiben Kundendaten im Mandanten. Weitere Informationen zu unseren Vertrauens-und sicherheitsrelevanten Informationen finden Sie im [Microsoft Trust Center](https://microsoft.com/trustcenter). Microsoft Teams folgt den gleichen Leitlinien und Prinzipien wie das Microsoft Trust Center.

Microsoft Teams basiert auf der Office 365-Cloud auf Unternehmensniveau mit Hyperskalierung und bietet die erweiterten Sicherheits- und Compliance-Funktionen, die unsere Kunden erwarten. Weitere Informationen zum Planen der Sicherheit in Office 365 finden Sie in unseren Office 365-Inhalten. [Der Office 365-Sicherheitsplan](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap) ist ein guter Ausgangspunkt. Weitere Informationen zum Planen der Compliance in Office 365 finden Sie im Artikel [Plan für Sicherheit und Compliance](https://docs.microsoft.com/microsoft-365/compliance/plan-for-security-and-compliance) .

In diesem Artikel finden Sie weitere Informationen zu Teams-spezifischer Sicherheit und-Compliance. Lesen Sie diese Microsoft Mechanics-Videos zur Sicherheit und Compliance:

- [Microsoft Teams Essentials für IT: Sicherheit und Compliance](https://youtu.be/91lHNKVVvQ4) (12:42 min)
- [Microsoft Teams-Steuerelemente für Sicherheit und Compliance](https://www.youtube.com/watch?v=Km4T4hMM__k) (10:54 min)

## <a name="security"></a>Sicherheit

Teams erzwingt teamübergreifende und organisationsweite zweistufige Authentifizierung, einmaliges Anmelden über Active Directory und Verschlüsselung von Daten in der Übertragung und im Ruhezustand. Dateien werden in SharePoint gespeichert und mit dem entsprechenden SharePoint-Mechanismus verschlüsselt. Notizen werden in OneNote gespeichert und mit dem entsprechenden OneNote-Mechanismus verschlüsselt. Die OneNote-Daten werden auf der SharePoint-Website des Teams gespeichert. Die Registerkarte "wiki" kann auch zum Aufzeichnen von Notizen verwendet werden, und der zugehörige Inhalt wird auch auf der SharePoint-Teamwebsite gespeichert.

Lesen Sie [Identitäts Modelle und Authentifizierung](identify-models-authentication.md) , um mehr Einblicke in Authentifizierung und Teams zu erhalten und zu erfahren, [wie moderne](sign-in-teams.md) Authentifizierungsfunktion insbesondere bei der modernen Authentifizierung hilft.

Da Teams in Partnerschaft mit SharePoint, OneNote, Exchange und mehr arbeiten, sollten Sie die Sicherheit in Office 365 vollständig verwalten. Wenn Sie mehr über die Office 365-Sicherheit erfahren möchten, lesen Sie [Konfigurieren Ihres Office 365-Mandanten für erhöhte Sicherheit](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).

> [!NOTE]
> Derzeit unterstützt [privater Kanal](private-channels.md) begrenzte Sicherheits-und Compliance-Funktionen. Die Unterstützung für den vollständigen Satz von Sicherheits-und Compliance-Features in privaten Kanälen wird in Kürze verfügbar sein.

### <a name="advance-threat-protection-atp"></a>Advance Threat Protection (ATP)

Advance Threat Protection (ATP) steht für Microsoft Teams zusammen mit SharePoint und OneDrive for Business zur Verfügung, Anwendungen, die in Teams für Content Management integriert sind. Mit ATP können Sie feststellen, ob Inhalte in diesen Anwendungen bösartig sind und diesen Inhalt vom Benutzer Zugriff blockieren.

Wie der betroffene Inhalt nach der Erkennung verwaltet wird, entspricht den Einstellungen, die Sie in Office 365 ausgewählt haben. Wir empfehlen Ihnen dringend, alle Anwendungen in Bezug auf die Konfiguration von ATP zu bedenken, und für weitere Informationen finden Sie im Artikel [Office 365 ATP für SharePoint, OneDrive und Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams) detaillierte Informationen zu den ersten Schritten.

### <a name="safe-links"></a>Sichere Links

Obwohl ATP-sichere Links in Microsoft Teams zurzeit nicht zur Verfügung stehen, sollten Sie zu einem späteren Zeitpunkt verfügbar sein, und wenn dies der Fall ist, aktualisieren wir diesen Inhalt, um Sie zu informieren. In der Zwischenzeit finden Sie Informationen zu Office 365-sicheren Links unter [Office 365 ATP-sichere Links](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links#how-to-get-atp-safe-links-protection).

### <a name="how-conditional-access-policies-work-for-teams"></a>Funktionsweise von bedingten Zugriffsrichtlinien für Teams

Microsoft Teams nutzt in großem Umfang Exchange Online, SharePoint Online und Skype for Business Online für elementare Produktivitätsszenarien wie Besprechungen, Kalender, Interop-Chats und Dateifreigabe. Richtlinien für bedingten Zugriff, die für diese Cloud-Apps festgelegt wurden, gelten auch für Microsoft Teams, wenn sich Benutzer direkt bei Microsoft Teams anmelden – unabhängig vom Client.

Microsoft Teams wird separat als Cloud-App in Azure Active Directory-Richtlinien für bedingten Zugriff unterstützt. Richtlinien für bedingten Zugriff, die für die Microsoft Teams-Cloud-App festgelegt wurden, gelten auch für Microsoft Teams, wenn sich Benutzer anmelden. Ohne die richtigen Richtlinien für andere Apps wie Exchange Online und SharePoint Online jedoch können Benutzer möglicherweise dennoch direkt auf diese Ressourcen zugreifen. Weitere Informationen zum Einrichten einer Richtlinie für den bedingten Zugriff im Azure-Portal finden Sie unter: [Azure Active Directory-Schnellstart](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started).

Microsoft Teams-Desktopclients für Windows und Mac unterstützen moderne Authentifizierung. Moderne Authentifizierung ermöglicht plattformübergreifend die Anmeldung auf der Grundlage von ADAL (Azure Active Directory Authentication Library, Active Directory-Authentifizierungsbibliothek) in Microsoft Office-Clientanwendungen.

Die Microsoft Teams-Desktopanwendung unterstützt AppLocker.  Weitere Informationen zu AppLocker-Voraussetzungen finden Sie unter Voraussetzungen für die Verwendung von [AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/requirements-to-use-applocker).

## <a name="compliance"></a>Compliance

Teams verfügt über eine breite Palette von Informationen, die Ihnen bei Compliance-Bereichen helfen, darunter Aufbewahrungsrichtlinien, Datenverlust Schutz (DLP), eDiscovery und rechtliche Aufbewahrungsmöglichkeiten für Kanäle, Chats und Dateien, Überwachungsprotokoll Suche sowie Verwaltung mobiler Anwendungen mit Microsoft InTune. Wir haben einige Informationen zu den folgenden Themen bereitgestellt, und Sie können zum Office 365 Security & Compliance Center wechseln, um diese Einstellungen zu verwalten.

### <a name="retention-policies"></a>Aufbewahrungsrichtlinien

Mit Aufbewahrungsrichtlinien in Microsoft Teams können Sie sowohl Daten beibehalten, die für Ihre Organisation wichtig sind, als auch aus rechtlichen, rechtlichen, geschäftlichen oder anderen Gründen, sowie Inhalte und Kommunikationen entfernen, die nicht relevant sind, um aufbewahrt zu werden. Sie können Aufbewahrungsrichtlinien auch dazu verwenden, Daten für einen bestimmten Zeitraum zu speichern und dann zu löschen. Weitere Informationen finden Sie im Artikel [Aufbewahrungsrichtlinien in Microsoft Teams](retention-policies.md) .

### <a name="data-loss-prevention-dlp"></a>Verhinderung von Datenverlust (DLP)

Die Verhinderung von Datenverlust (DLP) in Microsoft Teams sowie die größere DLP-Story für Office 365 dreht sich um die Geschäfts Bereitschaft, wenn es darum geht, vertrauliche Dokumente und Daten in Office 365 zu schützen. Unabhängig davon, ob es sich um vertrauliche Informationen in Nachrichten oder Dokumenten handelt, können DLP-Richtlinien dabei helfen, sicherzustellen, dass Ihre Benutzer diese vertraulichen Daten nicht für die falschen Personen freigeben.

Informationen zur Verhinderung von Datenverlust in Teams finden Sie unter [DLP für Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams). Ein guter Artikel für O36 DLP-Bedenken [https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)ist.

### <a name="ediscovery"></a>eDiscovery

Electronic Discovery (eDiscovery) ist der elektronische Aspekt der Identifizierung, Sammlung und Erstellung von elektronisch gespeicherten Informationen (ESI) als Antwort auf einen Antrag auf Produktion in einer Klage oder Untersuchung. Zu den Funktionen gehören Fallmanagement, Erhaltung, Suche, Analyse und Export von Microsoft Teams-Daten. Dies schließt Zusammenfassungen für Chats, Nachrichten und Dateien sowie Besprechungen und Anrufe ein. Für Microsoft Teams-Besprechungen und -Anrufe wird eine Zusammenfassung der Ereignisse in Besprechungen und Anrufen erstellt und in der eDiscovery verfügbar gemacht.

Weitere Informationen dazu, wie Sie Office 365 eDiscovery im Security & Compliance Center durchführen und Compliance-Inhaltssuche nach Teams-Inhalten ausführen, finden Sie unter den folgenden Links:

[eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations)

[Inhaltssuche](https://docs.microsoft.com/microsoft-365/compliance/search-for-content)

Wir haben einen Teams-spezifischen Artikel für weitere Informationen, [eDiscovery von Gast-zu-Gast-Chats](eDiscovery-investigation.md).

Kunden können in-Place-eDiscovery oder [Advanced eDiscovery] je nach Ihren [Anforderungen](https://docs.microsoft.com/microsoft-365/compliance/office-365-advanced-ediscovery)nutzen. In der folgenden Tabelle sind die Unterschiede zwischen den beiden Funktionen aufgeführt:

| |In-Situ-eDiscovery  |Advanced eDiscovery  |
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

- In-situ-Speicher (eine Teilmenge des Postfachs oder der Websitesammlung durch gezielte Abfragen oder gefilterte Inhalte wird in Wartestellung gesetzt) oder
- Rechtsstreit halten (das gesamte Postfach oder die gesamte Websitesammlung wird in Wartestellung gesetzt).

In beiden Fällen wird nach der Festlegung des haltebereichs sichergestellt, dass selbst dann, wenn Endbenutzer Kanal Nachrichten löschen oder bearbeiten, die sich im Gruppenpostfach befinden, unveränderliche Kopien dieser Inhalte verwaltet und über die eDiscovery-Suche verfügbar sind. Rechtliche Aufbewahrungen werden im Allgemeinen im Kontext eines eDiscovery-Falls angewendet.

Lesen Sie den Artikel [Übersicht über Aufbewahrungsrichtlinien](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) , um mehr über die Aufbewahrung und Aufbewahrung im Office 365 Security & Compliance Center zu erfahren. Wenn Sie weitere Teams-spezifische Informationen zur rechtlichen Aufbewahrung benötigen, haben wir auch [einen Microsoft Teams-Benutzer oder ein Team für legalen Aufbewahrungs Artikel eingerichtet](legal-hold.md) , in dem Sie weitere Informationen finden.

### <a name="compliance-content-search"></a>Compliancesuche in Inhalten

Die Inhaltssuche kann verwendet werden, um über umfangreiche Filterfunktionen nach allen Teams-Daten zu suchen. Die resultierenden Daten können für Compliance-und Litigation-Unterstützung in einen bestimmten Container exportiert werden. Dies kann mit oder ohne eDiscovery-Fall geschehen. Auf diese Weise können Complianceadministratoren Microsoft Teams-Daten für alle Benutzer sammeln, überprüfen und zur weiteren Verarbeitung exportieren. Weitere Informationen zum Durchführen einer Konformitäts Inhaltssuche für Microsoft Teams und andere Office 365-Inhalte finden Sie im Office 365 Security & Compliance Center im Artikel " [Inhaltssuche in Office 365](https://docs.microsoft.com/microsoft-365/compliance/content-search) ".

> [!TIP]
> Mithilfe der Inhaltssuche können Sie nach Bedarf nach nur Microsoft Teams-Inhalten wie Chats und Kanal Nachrichten, Besprechungen und anrufen filtern.

Wenn Sie weitere Teams-spezifische Informationen zum Konfigurieren der Inhaltssuche wünschen, lesen Sie den Artikel [Inhaltssuche in Microsoft Teams](content-search.md) .

### <a name="auditing-and-reporting"></a>Überwachung und Berichterstellung

Die Überwachungsprotokoll Suche wird direkt in das Office 365 Security & Compliance Center integriert und bietet Ihnen die Möglichkeit, Benachrichtigungen sowie Berichte zu Überwachungsereignissen festzulegen, indem Sie den Export von Arbeits Auslastungs spezifischen oder generischen Ereignis Sätzen für die Verwendung durch Administratoren und die Untersuchung in einer unbegrenzten Überwachungs Zeitachse zulassen. Sie können Benachrichtigungen für alle Überwachungsprotokolldaten im Office 365 Security & Compliance Center einrichten und diese Daten zur weiteren Analyse Filtern und exportieren. Weitere Informationen zum Durchführen eines Überwachungsprotokolls für Office 365 finden Sie im Artikel [Durchsuchen des Überwachungsprotokolls](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) . Wenn Sie mehr über das Suchen nach Microsoft Teams-Ereignissen im Office 365 Security & Compliance Center erfahren möchten, haben wir auch den Artikel [Auditing in Teams](audit-log-events.md) für Sie zu überprüfen.

## <a name="information-protection-architecture"></a>Architektur des Informationsschutzes

Die folgende Abbildung zeigt den Ablauf der Erfassung von Microsoft Teams-Daten (Microsoft Teams-Dateien und -Nachrichten) in Exchange und SharePoint.

![Diagramm des Workflows von Microsoft Teams-Daten zu Exchange und SharePoint](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)

Die folgende Abbildung zeigt den Ablauf der Erfassung von Daten aus Microsoft Teams-Besprechungen und -Anrufen in Exchange.

![Diagramm des Workflows von Daten aus Microsoft Teams-Besprechungen und -Anrufen zu Exchange](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1a.png)

> [!IMPORTANT]
> Beim Ermitteln von Microsoft Teams-Inhalten ist eine Verzögerung von bis zu 24 Stunden möglich.

## <a name="licensing"></a>Lizenzierung

In Bezug auf Informationsschutzfunktionen bestimmen Office 365-Abonnements und die zugehörigen eigenständigen Lizenzen den verfügbaren Funktionsumfang.

Informationen zum Ermitteln des Lizenzierungs Bedarfs zur Implementierung von Features für Sicherheit und Compliance finden Sie unter: [Lizenzierung für Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).

> [!NOTE]
> Die Inhaltssuche und eDiscovery müssen im Security & Compliance Center nicht aktiviert sein, damit Sie funktionieren.

## <a name="location-of-data-in-teams"></a>Speicherort von Daten in Microsoft Teams

Die Microsoft Teams-Daten befinden sich in der geografischen Region, die Ihrem Office 365-Mandanten zugeordnet ist. Wenn Sie sehen möchten, welche Regionen zurzeit unterstützt werden, überprüfen Sie den [Speicherort der Daten in Microsoft Teams](location-of-data-in-teams.md).

Wenn Sie sehen möchten, in welcher Region die Daten für Ihren Mandanten angezeigt werden, wechseln Sie zum [Microsoft 365 Admin Center](https://portal.office.com/adminportal/home) > **Settings** > **Organization Profile**. Scrollen Sie nach unten zu **Data location** (Datenspeicherort).

![Screenshot der Tabelle „Data location“ (Datenspeicherort) einschließlich Microsoft Teams im Admin Center](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="compliance-standards"></a>Compliance-Standards

Microsoft Teams ist mit Stufe D konform. Dazu gehören die folgenden Standards: ISO 27001, ISO 27018, SSAE16 SOC 1 und SOC 2, HIPAA und EU-Standardvertragsklauseln (EU Model Clauses, EUMC). Microsoft klassifiziert innerhalb des Microsoft-Compliance-Frameworks Office 365-Anwendungen und -Dienste in vier Kategorien. Jede Kategorie wird durch bestimmte Compliance-Verpflichtungen definiert, die ein Office 365-Dienst oder ein zugehöriger Microsoft-Dienst erfüllen muss, um in dieser Kategorie geführt zu werden.

Dienste in den Compliance-Kategorien C und D, für die branchenführende Compliance-Verpflichtungen gelten, sind standardmäßig aktiviert. Dienste der Kategorien A und B verfügen über Steuermöglichkeiten, mit denen diese Dienste organisationsweit aktiviert oder deaktiviert werden können. Details hierzu finden Sie im Dokument zum [Compliance-Framework für Branchenstandards und -bestimmungen](https://download.microsoft.com/download/1/4/3/1434ABAB-B8E9-412D-8C3A-187B5FCB7A2F/Compliance%20Framework%20document.pdf). Microsoft Teams unterstützt außerdem Cloud Security Alliance-Compliance.

## <a name="related-topics"></a>Verwandte Themen

[M365 Security](https://docs.microsoft.com/microsoft-365/security/)
[M365 Compliance](https://docs.microsoft.com/microsoft-365/compliance/)
