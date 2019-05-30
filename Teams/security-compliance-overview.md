---
title: Übersicht über Sicherheit und Compliance in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: anach
description: Eine Übersicht über die Sicherheits-und Kompatibilitätsfeatures von Microsoft Teams, einschließlich Überwachung und Berichterstellung, Konformitäts Inhaltssuche, eDiscovery und mehr.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6aa87b4cb600e38f7d3d0ea5944166d92793dad2
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548000"
---
<a name="overview-of-security-and-compliance-in-microsoft-teams"></a>Übersicht über Sicherheit und Compliance in Microsoft Teams
======================================================

Microsoft Teams basiert auf der Office 365-Cloud auf Unternehmensniveau mit Hyperskalierung und bietet die erweiterten Sicherheits- und Compliance-Funktionen, die unsere Kunden erwarten.

Teams ist Stufe D-kompatibel. Dies umfasst die folgenden Standards: ISO 27001, ISO 27018, SSAE16 SOC 1-und SOC 2-, HIPAA-und EU-Modellklauseln (EUMC). Innerhalb des Microsoft Compliance-Rahmens stuft Microsoft Office 365-Anwendungen und-Dienste in vier Kategorien um. Jede Kategorie wird durch spezifische Compliance-Zusagen definiert, die bei einem Office 365-Dienst oder einem zugehörigen Microsoft-Dienst erfüllt sein müssen, um in dieser Kategorie aufgeführt zu werden.

Dienste in den Compliance-Kategorien C und D, für die branchenführende Compliance-Verpflichtungen gelten, sind standardmäßig aktiviert. Dienste der Kategorien A und B verfügen über Steuermöglichkeiten, mit denen diese Dienste organisationsweit aktiviert oder deaktiviert werden können. Details hierzu finden Sie im Dokument zum [Compliance-Framework für Branchenstandards und -bestimmungen](https://go.microsoft.com/fwlink/?linkid=855777). Microsoft Teams unterstützt außerdem Cloud Security Alliance-Compliance.

Teams erzwingt auch teamübergreifende und organisationsweite zweistufige Authentifizierung, einmaliges Anmelden über Active Directory und Verschlüsselung von Daten in der Übertragung und im Ruhezustand. Dateien werden in SharePoint gespeichert und durch die SharePoint-Verschlüsselung gesichert. Notizen werden in OneNote gespeichert und durch die OneNote-Verschlüsselung gesichert. Die OneNote-Daten werden auf der SharePoint-Teamwebsite gespeichert. Die Registerkarte "wiki" kann auch zum Aufzeichnen von Notizen verwendet werden, und der Inhalt wird auch auf der SharePoint-Teamwebsite gespeichert.

Außerdem haben wir Unterstützung für Überwachungsprotokollsuche, eDiscovery und gesetzliche Aufbewahrungspflicht für Kanäle, Chats und Dateien sowie mobile Anwendungsverwaltung mit Microsoft Intune hinzugefügt. Wechseln Sie zum Office 365 Security & Compliance Center, um diese Einstellungen zu verwalten. 

Weitere Informationen zur Compliance von Office 365 Security & finden Sie unter [Konfigurieren Ihres Office 365-Mandanten für erhöhte Sicherheit](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)

## <a name="auditing-and-reporting"></a>Überwachung und Berichterstellung

Überwachungsprotokoll Suche-Plugs direkt in das Office 365 Security & Compliance Center und macht Fähigkeiten verfügbar, um Benachrichtigungen und/oder Berichte über Überwachungsereignisse festzulegen, indem Sie für die Verwendung und Untersuchung von Arbeitslasten spezifische oder generische Ereignis Sätze für die Verwendung durch Administratoren bereitstellen unbegrenzte Überwachungs Zeitachse. Alle Überwachungsprotokolldaten stehen zum Einrichten von Benachrichtigungen im Office 365 Security & Compliance Center sowie zum Filtern und exportieren zur weiteren Analyse zur Verfügung. Weitere Informationen zum durch [](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c) führen einer Überwachungsprotokoll Suche nach Microsoft Teams-Ereignissen finden Sie im Office 365 Security & Compliance Center. 

## <a name="compliance-content-search"></a>Compliancesuche in Inhalten

Mit der Inhaltssuche können Sie über Rich-Filterfunktionen nach allen Teams-Daten suchen und in einen bestimmten Container exportieren, um Compliance-und Litigation-Unterstützung zu erhalten. Dies kann mit oder ohne eDiscovery-Fall erfolgen. Dies ermöglicht es Compliance-Administratoren, Team Daten für alle Benutzer zu sammeln, zu überprüfen und zur weiteren Verarbeitung zu exportieren. Weitere Informationen zum durch [](https://support.office.com/article/content-search-in-office-365-53390468-eec6-45cb-b6cd-7511f9c909e4) führen einer Compliance-Inhaltssuche nach Microsoft Teams-Inhalten finden Sie im Office 365 Security & Compliance Center. 

Tipp: die Art Microsoft Teams kann verwendet werden, um nach Microsoft Teams nur Inhalte zu filtern, also Chats und Kanal Nachrichten, Besprechungen und Anrufe. 

## <a name="ediscovery"></a>eDiscovery

Bei eDiscovery handelt es sich um den elektronischen Aspekt beim Identifizieren, Sammeln und Erzeugen von elektronisch gespeicherten Informationen (ESI) als Reaktion auf die Aufforderung zur Vorlage dieser Informationen in einem Rechtsstreit oder einer Untersuchung. Zu den Funktionen gehören Fallverwaltung, Aufbewahrung, Suche, Analyse und Export von Teams-Daten. Dazu gehören Chats, Nachrichten und Dateien, Besprechungen und Anruf Zusammenfassungen. Für Teams-Besprechungen und-Anrufe werden eine Zusammenfassung der Ereignisse erstellt, die in der Besprechung und dem Anruf durchgeführt wurden und in eDiscovery zur Verfügung gestellt werden. 

Weitere Informationen dazu, wie Sie eDiscovery im Security & Compliance Center durchführen und Compliance-Inhaltssuche nach Teams-Inhalten ausführen, finden Sie unter den folgenden Links: 

[eDiscovery](https://support.office.com/article/manage-legal-investigations-in-office-365-2e5fbe9f-ee4d-4178-8ff8-4356bc1b168e) 

[Inhaltssuche](https://support.office.com/article/search-for-content-in-office-365-df2d1e0f-b476-42c9-aade-4a260b24f193)

Kunden können in-Place-eDiscovery oder [Advanced eDiscovery] je nach Ihren Anforderungenhttps://support.office.com/article/Office-365-Advanced-eDiscovery-fd53438a-a760-45f6-9df4-861b50161ae4)nutzen (. In der folgenden Tabelle sind die Unterschiede zwischen den beiden Funktionen aufgeführt:


| |In-Situ-eDiscovery  |Advanced eDiscovery  |
|---------|---------|---------|
|Fallmanagement     |X        |X         |
|Zugriffssteuerung  |X         |X         |
|Suche in Inhalten     |X         | X        |
|Speicher   |X         | X        |
|Export     |X         |X         |
|Erkennung von Duplikaten     |-         |X         |
|Relevanzsuche mit maschinellem Lernen    |-         |X         |
|Analyse unstrukturierter Daten      |-         |X         |


## <a name="legal-hold"></a>Gesetzliche Aufbewahrungspflicht

Während eines Rechtsstreits ist es häufig erforderlich, dass alle Daten, die einem Benutzer (Depotbank) oder einem Team zugeordnet sind, unveränderlich bleiben, damit er als Beweis für den Fall verwendet werden kann. Dies wird erreicht, indem entweder ein Benutzer (Benutzerpostfach) oder ein Team in rechtlicher Wartestellung platziert wird. Wenn ein Team innerhalb von Teams in-situ-Speicher (Teilmenge des Postfachs oder der Websitesammlung durch gezielte Abfragen oder gefilterte Inhalte) oder in einem Rechtsstreit (gesamtes Postfach oder Websitesammlung) platziert wird, wird der Haltebereich auf das Postfach "Gruppen" gesetzt. Dadurch wird sichergestellt, dass selbst dann, wenn Endbenutzer Kanal Nachrichten löschen oder bearbeiten, die in das Gruppenpostfach aufgenommen werden, unveränderliche Kopien dieser Inhalte verwaltet werden und in der eDiscovery-Suche verfügbar sind. Gesetzliche Aufbewahrungspflicht wird im Allgemeinen im Kontext eines eDiscovery-Falls angewendet. In [diesem](https://support.office.com/article/overview-of-preservation-policies-9c3b1d52-40ce-4ba3-a520-9ae0be15538a) Hilfeartikel finden Sie weitere Informationen zur Aufbewahrung und Aufbewahrung im Office 365 Security & Compliance Center. 

## <a name="information-protection-architecture-for-microsoft-teams"></a>Informationsschutz Architektur für Microsoft Teams. 

Die folgende Abbildung zeigt den Einnahme Fluss von Teams-Daten sowohl in Exchange als auch in SharePoint für Teams-Dateien und-Nachrichten. 

![Diagramm des Workflows von Teams-Daten zu Exchange und SharePoint](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)

Die folgende Abbildung zeigt den Einnahme Fluss von Teams-Besprechungen und das Aufrufen von Daten an Exchange.

![Diagramm des Workflows von Teams-Besprechungen und Anrufen von Daten an Exchange](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1a.png)

> [!IMPORTANT]
> Es kann bis zu 24 Stunden dauern, bis Sie die Inhalte von Teams entdecken können.

<a name="licensing"></a>Lizenzierung
---------------

Die Funktionen für den Schutz von Informationen hängen von den Office 365-Abonnements und den zugehörigen eigenständigen Lizenzen ab.


| Funktion für den Schutz von Informationen | Office 365 Business Essentials | Office 365 Business Premium | Office 365 Enterprise E1 | Office 365 Enterprise E3/E4 | Office 365 Enterprise E5 |
|-----------------------------------|--------------------------------|-----------------------------|--------------------------|-----------------------------|--------------------------|
|              Archiv              |               -                |              -              |            -             |             Ja             |           Ja            |
|        In-Situ-eDiscovery        |               -                |              -              |            -             |             Ja             |           Ja            |
|        Advanced eDiscovery        |               -                |              -              |            -             |              -              |           Ja            |
|            Gesetzliche Aufbewahrungspflicht             |               -                |              -              |            -             |             Ja             |           Ja            |
|     Compliancesuche in Inhalten     |               -                |             Ja             |           Ja            |             Ja             |           Ja            |
|      Überwachung und Berichterstellung       |              Ja               |             Ja             |           Ja            |             Ja             |           Ja            |
|       Bedingter Zugriff\*        |              Ja               |             Ja             |           Ja            |             Ja             |           Ja            |

> [!NOTE]
> \*Für bedingten Zugriff sind zusätzliche Lizenzen erforderlich.


| |  |  |
|---------|---------|---------|
|![Ein Symbol, das einen Entscheidungspunkt darstellt](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |Entscheidungspunkt         |Verfügt Ihre Organisation über die erforderlichen Lizenzen, um die geschäftlichen Compliance- und Sicherheitsanforderungen zu erfüllen?         |
|![Ein Symbol, das die nächsten Schritte darstellt](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)    |Nächste Schritte         |Überprüfen Sie die aktuelle Lizenzierung Ihrer Organisation, und bestätigen Sie, dass Sie alle geschäftlichen Anforderungen hinsichtlich Compliance und Sicherheit erfüllt.         |

Bevor Sie eine dieser Funktionen aktivieren, stellen Sie sicher, dass Sie im Microsoft 365 Admin Center auf das Security & Compliance Center zugreifen können. Mandantenadministratoren verfügen standardmäßig über Zugriff.

Die Inhaltssuche und eDiscovery erfordern keine Aktivierung im Security & Compliance Center.

<a name="location-of-data-in-teams"></a>Speicherort von Daten in Microsoft Teams
-------------------------

Die Microsoft Teams-Daten befinden sich in der geografischen Region, die Ihrem Office 365-Mandanten zugeordnet ist. Derzeit unterstützt Microsoft Teams die Regionen Australien, Kanada, Indien, Japan, Großbritannien, Amerika, APAC und EMEA. 

> [!IMPORTANT]
> Teams bietet derzeit nur für neue Mandantendaten in Australien, Kanada, Indien, Japan und Großbritannien an. Ein neuer Mandant wird definiert als ein Mandant, über den sich noch kein einziger Benutzer bei Microsoft Teams angemeldet hat. Bestehende Mandanten aus Australien, Indien und Japan werden Ihre Teams-Daten weiterhin in der Region APAC speichern. Für vorhandene Mandanten in Kanada und Großbritannien werden Ihre Daten in der Region Americas und EMEA gespeichert.

Weitere Informationen zur Einführung der Datenspeicherung für Microsoft Teams in Indien und im Vereinigten Königreich finden Sie in Ansuman Acharyas Blogbeitrag zur [Einführung der Datenspeicherung für Microsoft Teams in Indien und zu geplanten weiteren geografischen Regionen](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Australia-and-Japan-Data-Residency/ba-p/237827). 

Weitere Informationen zu Kanada Data Residency für Teams finden Sie im Blogbeitrag von Varun Sagar, [Microsoft Teams startet Kanada Data Residency, Australien und Japan in Kürze](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Canada-Data-Residency-Australia-and/ba-p/227178). 

Wenn Sie mehr über die Einführung von Australien und Japan Data Residency für Teams erfahren möchten, lesen Sie den Blogbeitrag von Varun Sagar, [Microsoft Teams startet den Daten Wohnsitz in Australien und Japan ](https://go.microsoft.com/fwlink/?linkid=867773). 

Wenn Sie sehen möchten, in welcher Region Daten für Ihren Mandanten angezeigt werden, wechseln Sie zum [Microsoft 365 Admin Center](https://portal.office.com/adminportal/home) > **Settings** > **Organization Profile**. Scrollen Sie nach unten zu **Data location** (Datenspeicherort). 

![Screenshot der Tabelle "Datenspeicherort" mit Teams im Admin Center](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

<a name="how-do-conditional-access-policies-work-for-teams"></a>Wie funktionieren bedingte Zugriffsrichtlinien für Teams?
-------------------------

Microsoft Teams ist in hohem Maße auf Exchange Online, SharePoint Online und Skype for Business Online für Kern Produktivitätsszenarien wie Besprechungen, Kalender, Interop-Chats und Dateifreigabe angewiesen. Für diese Cloud-apps festgelegte Richtlinien für den bedingten Zugriff gelten für Microsoft Teams, wenn sich ein Benutzer direkt bei Microsoft Teams anmeldet – auf einem beliebigen Client. 

Microsoft Teams wird in Azure Active Directory-Richtlinien für den bedingten Zugriff separat als Cloud-App unterstützt. Für die Microsoft Teams Cloud-App festgelegte Richtlinien für den Zugriffs Zugriff gelten für Microsoft Teams, wenn sich ein Benutzer anmeldet. Ohne die richtigen Richtlinien für andere apps wie Exchange Online und SharePoint Online können Benutzer jedoch weiterhin direkt auf diese Ressourcen zugreifen. Weitere Informationen zum Einrichten einer Richtlinie für den bedingten Zugriff im Azure-Portal finden Sie unter: (https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started) 

Microsoft Teams-Desktop Clients für Windows und Mac unterstützen die moderne Authentifizierung. Bei der modernen Authentifizierung wird die Anmeldung basierend auf der Azure Active Directory Authentication Library (Adal) für Microsoft Office-Clientanwendungen plattformübergreifend durchführt.

Die Microsoft Teams-Desktopanwendung unterstützt AppLocker.  Weitere Informationen zu AppLocker-Voraussetzungen finden Sie unter: Voraussetzungen für die Verwendung von AppLocker (https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/requirements-to-use-applocker).

<a name="privacy-in-teams"></a>Datenschutz in Microsoft Teams
--------------------------

Als Kunde von Office 365 sind Sie der Besitzer der Daten und verfügen auch über die vollständige Kontrolle. Microsoft verwendet Ihre Daten ausschließlich für die Bereitstellung des Diensts, den Sie abonniert haben. Als Dienstanbieter scannen wir nicht Ihre E-Mails, Dokumente oder Teams zu Werbezwecken oder nicht dienstbezogenen Zwecken. Microsoft hat keinen Zugriff auf hochgeladene Inhalte. Genau wie bei OneDrive for Business und SharePoint Online bleiben die Kundendaten im Mandanten.

Weitere Informationen zu unseren Vertrauens-und sicherheitsrelevanten Informationen finden Sie im [Microsoft Trust Center](https://microsoft.com/trustcenter). Teams befolgt die gleichen Richtlinien und Grundsätze wie das Microsoft Trust Center.

<a name="related-topics"></a>Verwandte Themen
----------------------
[Sichere Office 365 ATP-Links](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links#how-to-get-atp-safe-links-protection)
