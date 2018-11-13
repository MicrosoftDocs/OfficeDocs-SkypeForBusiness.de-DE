---
title: Übersicht über Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: Hier erhalten Sie Informationen zu Microsoft Teams, zur Infrastruktur und zur Verwendung von Teams mit Office 365.
localization_priority: Normal
search.appverid: MET150
ms.custom:
- NewAdminCenter_Update
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4fb74faf3acb0b3df7960ba4429c88e1383204f8
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295205"
---
<a name="overview-of-microsoft-teams"></a>Übersicht über Microsoft Teams
===========================

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=ccf507a4-4ec4-4d61-9fb0-c86b5f1fc2a6&AutoPlayVideo=false] 


Microsoft Teams vereint den vollen Funktionsumfang von Office 365 in einem wirklich chatbasierten Hub für Teamarbeit und gibt Kunden die Gelegenheit, eine offenere, flüssigere und digitale Umgebung zu schaffen. Microsoft Teams basiert auf vorhandenen Microsoft-Technologien, die durch Office 365-Gruppen verknüpft werden. 

Teams nutzt standardmäßig die in Azure Active Directory (Azure AD) gespeicherten Identitäten und wird in die anderen Dienste in Office 365 integriert, um für jedes erstellte Team eine SharePoint Online-Website und ein Exchange Online-Gruppenpostfach zu erstellen.

Jeder Benutzer mit einer Business "oder" Consumer e-Mail-Konto, wie Outlook, Google Mail oder andere, kann als Gast in Teams teilnehmen. Alle Gäste in Teams unterliegen den gleichen Einhaltung von Vorschriften und Überwachung Schutz als den Rest von Office 365 und Gäste in Azure AD sicher verwaltet werden können. Administratoren können zentral verwalten wie Gäste innerhalb ihrer Office 365-Umgebung teilnehmen und auf einfache Weise anzeigen, hinzufügen oder widerrufen des Gastsystem Zugriff auf den Host-Mandanten.

Microsoft Teams bietet Funktionen für beständigen Chat, Anrufe und Besprechungen, einfachen Zugriff auf andere Komponenten von Office 365 sowie robuste Erweiterungsmöglichkeiten.  Dadurch entsteht ein Hub für Teamarbeit, der sich für die verschiedensten Organisationsgrößen eignet – von Großunternehmen bis hin zu kleinen Organisationen.  

Zum Erweitern der Funktionen von Teams stehen Connectors, Registerkarten und Bots als [Apps](https://go.microsoft.com/fwlink/?linkid=854629) zur Verfügung, mit denen externe Informationen, Inhalte und Interaktionen mit intelligenten Bots in Teams integriert werden können.  

<a name="microsoft-teams-infrastructure"></a>Infrastruktur von Microsoft Teams
------------------------------

Teams basiert auf vorhandenen Microsoft-Technologien, die durch Office 365-Gruppen verknüpft werden. Unterstützt von der Cloud von Microsoft können Organisationen exzellente Leistung und Zuverlässigkeit erwarten, wenn sie Teams als Bestandteil ihrer Zusammenarbeitslösung nutzen.

Standardmäßig wird für ein in Teams erstelltes Team jeweils eine Office 365-Gruppe mit der zugehörigen SharePoint Online-Website erstellt – einschließlich einer Dokumentbibliothek und eines Exchange Online-Gruppenpostfachs, das von Teams zum Speichern von Informationen wie zum Beispiel Besprechungseinladungen verwendet wird. Ein Team kann mithilfe vorhandener Office 365-Gruppen erstellt werden, sodass vorhandene Gruppenmitgliedschaften und Inhalte, die in SharePoint Online und Exchange Online gespeichert sind, nach Teams portiert werden können.

Um die Fähigkeit von Teams zu ergänzen, wie ein, in dem informelle, Real-Time Unterhaltungen stattfinden, persistent Chat Board auch Teams bietet eine Anruf- und meeting Erfahrung basieren auf der nächsten Generation cloudbasierten-Infrastruktur, die auch von Skype und Skype für verwendet wird Business. Zu diesen Technologieinvestitionen gehören Azure-basierte Clouddienste für Medienverarbeitung und Signalisierung, der Videocodec H.264, die Audiocodecs SILK und Opus, Netzwerkresilienz, Telemetrie und Qualitätsdiagnose.

Office 365-Gruppen nutzen in Azure Active Directory (Azure AD) gespeicherte Identitäten. Damit sind alle Authentifizierungs- und Autorisierungsfunktionen in Azure AD wie Unterstützung für mehrstufige Authentifizierung (Multi-Factor Authentication, MFA) direkt zur Verwendung durch Teams verfügbar.

> [!NOTE]
> Basierend auf Feedback von Kunden, neue Office 365 Gruppen infolge einer erstellen ein Team in Microsoft-Teams, nicht mehr in Outlook standardmäßig angezeigt. Für Kunden, die das vorhandene Verhalten der mit diesen Gruppen in Outlook fortsetzen möchten, wird die Gruppe die für die benutzerfreundlichkeit von Outlook ermöglichen können ein Exchange Online PowerShell-Cmdlet bereitgestellt werden. Gruppen über Outlook erstellt und dann später für Teams aktiviert werden weiterhin in Outlook und Teams angezeigt. Dieses Update wird schrittweise Roll out über Outlook und Teams in den nächsten Monaten.


<a name="microsoft-teams-and-office-365"></a>Microsoft Teams und Office 365
------------------------------

Verschiedene Gruppen haben unterschiedliche Anforderungen, die auf ihrer jeweiligen funktionalen Rolle und Arbeitsweise basieren. Office 365 ist für die individuelle Arbeitsweise jeder Gruppe konzipiert und umfasst speziell entwickelte integrierte Anwendungen wie zum Beispiel:

-   Outlook für E-Mail auf Unternehmensniveau, jetzt mit Gruppenfunktionen

-   SharePoint für Websites und Portale, intelligente Inhaltsdienste, Automatisierung von Geschäftsprozessen und Unternehmenssuche

-   Yammer zum Knüpfen firmenweiter Verbindungen

-   Skype for Business als Backbone für Enterprise-VoIP und Video

-   Und jetzt auch Microsoft Teams, den neuen chatbasierten Arbeitsbereich in Office 365

Hier sind gängige Anwendungsfälle für die einzelnen Anwendungen in Office 365. Einen detaillierten Leitfaden zur Verwendung finden Sie unter [FastTrack Productivity Library](https://go.microsoft.com/fwlink/?linkid=854630).

![Microsoft Teams-Symbol](media/Overview_of_Microsoft_Teams_image1.png)

-   Wird von Benutzern und Teams genutzt, die in Echtzeit mit dem gleichen Personenkreis zusammenarbeiten möchten.

-   Hilft Teams, die ein Projekt schnell durchlaufen und dabei Dateien freigeben und zusammen an freigegebenen Projektdokumenten arbeiten möchten.

-   Ermöglicht Benutzern die Verbindung eine Vielzahl von Tools in den Arbeitsbereich (beispielsweise Planner, Power BI, GitHub usw.).

![Microsoft Outlook-Symbol](media/Overview_of_Microsoft_Teams_image2.png)

-   Wird von Benutzern genutzt, die es vorziehen, in der vertrauten Umgebung mit E-Mail und/oder formeller und strukturierter zu arbeiten.

-   Bietet spezifische Geschäftsprozesse, die die Verwendung von E-Mail zum Übertragen von Dokumenten und Informationen innerhalb und außerhalb der Unternehmensgrenzen erfordern.

-   Kommuniziert und unterhält Verbindungen mit Benutzern außerhalb unmittelbarer Arbeitsgruppen oder Organisationen.

![Yammer-Symbol](media/Overview_of_Microsoft_Teams_image3.png)

-   Wird genutzt, um Benutzer aus der gesamten Organisation miteinander zu verbinden, praxisbezogene Communitys zu bilden und bewährte Methoden auszutauschen.

-   Verbessert funktionsübergreifende Workflows durch eine offene und transparente feedbasierte Plattform.

-   Fördert den Austausch zwischen Führungskräften und Mitarbeitern durch bidirektionale Unterhaltungen zwischen der Führung und der breiteren Mitarbeiterbasis.

-   Regt Ihre an vorderster Front stehenden Mitarbeiter dazu an, Wissen und Fachkenntnisse weiterzugeben und zu erwerben.

![Skype for Business-Symbol](media/Overview_of_Microsoft_Teams_image4.png)

-   Wird für Echtzeitkommunikation und Zusammenarbeit, intern und extern mit Kunden bzw. Partnern, genutzt.

-   Ermöglicht Besprechungen mit Audio, Video und Inhalten in kleinen oder großen Teams (einschließlich Mitarbeiterversammlungen mit bis zu 10.000 Teilnehmern).

-   Bietet Telefoniefunktionen für Unternehmen.


![Microsoft SharePoint-Symbol](media/Overview_of_Microsoft_Teams_image5.png)

-   Wird für Websites und Portale genutzt (zum Beispiel Firmennachrichten und -ankündigungen, Suche und Zusammenarbeit an Dokumenten).

-   Implementiert Automatisierung von Geschäftsprozessen in Dokumentbibliotheken und Informationslisten durch Integration von Microsoft Flow und PowerApps.

-   Eine SharePoint-Teamwebsite mit vollem Funktionsumfang für Dateispeicherung, Teamnachrichten, Seiten, Listen und vieles mehr wird automatisch für jedes Team in Microsoft Teams bereitgestellt.

-   Weitere Informationen finden Sie unter [Interaktion von SharePoint Online und OneDrive for Business mit Teams](SharePoint-OneDrive-interact.md)

## <a name="teams-known-issuesknown-issuesmd"></a>[Bekannte Probleme für Microsoft Teams](Known-issues.md)

## <a name="teams-client-release-noteshttpssupportofficecomarticlerelease-notes-for-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de"></a>[Anmerkungen zu dieser Version des Microsoft Teams-Clients](https://support.office.com/article/Release-notes-for-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)


