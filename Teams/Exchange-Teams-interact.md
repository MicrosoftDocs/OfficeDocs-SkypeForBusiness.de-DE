---
title: Interaktion von Exchange und Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: crowe
description: Lernen Sie die Funktionen kennen, die in Microsoft Teams und den zahlreichen Exchange-Setups gemeinsam verwendet werden, wie zum Beispiel das Erstellen von und die Teilnahme an Teams, das Erstellen von Kanälen usw.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 020204700101e086691004cb90b5e5f7eabdbe5a
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/07/2019
ms.locfileid: "30462188"
---
<a name="how-exchange-and-microsoft-teams-interact"></a>Interaktion von Exchange und Microsoft Teams 
=========================================

> [!Tip]
> Sehen Sie sich die folgenden Sitzung um zu erfahren, wie Teams interagiert mit Azure Active Directory (AAD), Gruppen von Office 365, Exchange, SharePoint und OneDrive für Unternehmen: [Grundlagen der Microsoft-Teams](https://aka.ms/teams-foundations)

Um den vollen Funktionsumfang von Microsoft Teams zu nutzen, sollten alle Benutzer für Exchange Online, SharePoint Online und das Erstellen einer Office 365-Gruppe aktiviert sein.

Die Exchange-Postfächer der Benutzer können online oder lokal gehostet werden. In Exchange Online oder Exchange Dedicated vNext gehostete Benutzer können alle Funktionen von Microsoft Teams verwenden. Sie können Teams und Kanäle erstellen und diesen beitreten, Besprechungen erstellen und anzeigen, anrufen und chatten, Benutzerprofilbilder ändern sowie Connectors, Registerkarten und Bots hinzufügen und konfigurieren.

In Exchange Online Dedicated – Legacy oder Exchange lokal gehostete Benutzer müssen mit Azure Active Directory für Office 365 synchronisiert werden. Sie können Teams und Kanäle erstellen oder an diesen teilnehmen, Registerkarten und Bots hinzufügen und konfigurieren sowie chatten und anrufen. Sie können jedoch keine Benutzerprofilbilder ändern oder Connectors hinzufügen und konfigurieren. Sie können Nachrichten von Connectors empfangen, die von anderen Benutzern konfiguriert wurden. Die Möglichkeiten zum Erstellen und Anzeigen von Besprechungen hängen von der Version ab: Das Erstellen und Anzeigen von Besprechungen wird für das kumulative Update 3 (CU3) von Exchange 2016 und höher unterstützt, aber nicht für niedrigere Versionen.

Die folgende Tabelle enthält Informationen für Benutzer, für die Exchange Online in verschiedenen Umgebungen gehostet ist.

**Unterstützte Aktionen:** 

| Benutzerpostfach ist gehostet in: | eDiscovery| Rechtliche&nbsp;halten | Speicherung| Teams und der DDE-Kanal-mgmt |Besprechungen erstellen und anzeigen| Benutzerprofilbild bearbeiten | Die Anrufliste... | Verwalten von Kontakten | Zugriff auf Outlook-Kontakte | Voicemail |Connectors hinzufügen und konfigurieren|Registerkarten hinzufügen und konfigurieren|Bots hinzufügen und konfigurieren| 
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
|**Exchange Online**|Ja, <sup>2</sup>|Ja, <sup>2</sup>|Ja |Ja|Ja|Ja|Ja|Ja|Ja|Ja|Ja|Ja |Ja|
|**Exchange Online Dedicated vNext**|Ja, <sup>2</sup>|Ja, <sup>2</sup>|Ja |Ja |Ja|Ja|Ja |Ja|Ja|Ja|Ja |Ja |Ja |
|**Exchange Online Dedicated – Vorgängerversion** (Synchronisierung in Azure AD erforderlich)|Ja, <sup>2</sup>|Ja, <sup>2, 3</sup>|Ja <sup>4|Festlegen einer internationalen Nummer als Standardeinwahlnummer (die in der Besprechungseinladung angegeben ist) für einen Benutzer|Ja|Nein|Ja|Ja |Ja|Ja <sup>5|Ja |Ja |Ja|
|**Exchange lokal** (Synchronisierung in Azure AD erforderlich)|Ja, <sup>2</sup>| Ja, <sup>2, 3</sup> |Ja <sup>4|Ja|Ja (Exchange 2016 CU3 oder höher)|Ja (Exchange 2016 CU3 oder höher)|Ja |Ja |Ja|Ja <sup>5|Ja |Ja |Ja |

<sup>1</sup> exchange 2016 CU3 und oben unterstützt  
eDiscovery- <sup>2</sup> und rechtlichen Aufbewahrungspflicht für Konformität auf Channel Nachrichten wird für alle Hostingoptionen unterstützt.  
<sup>3</sup> private Chatnachrichten Teams sind noch nicht für die rechtlichen Aufbewahrungspflicht für diese Hostingoption unterstützt.

<sup>4</sup> Aufbewahrung ein Postfachs Schatten für den online-Benutzer verwendet, um Nachrichten speichern. [Microsoft unterstützt die Teams eDiscovery für Teams Benutzer in einer hybriden Exchange-Umgebung](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-supports-eDiscovery-for-Teams-users-in-a/ba-p/200009).

<sup>5</sup> Teams Benutzer mit Exchange-Postfach verwenden Sie Voicemail mit Teams und Voicemail-Nachrichten in Outlook, aber Voicemail-Nachrichten empfangen kann lokal werden nicht zum Anzeigen oder wiedergegeben werden sollen, innerhalb des Teams-Clients verfügbar.

Weitere Informationen:

-   Microsoft Teams unterstützt keine lokalen SharePoint-Instanzen.

-   SharePoint Online ist erforderlich, um Dateien in Teamunterhaltungen freizugeben und zu speichern.

-   OneDrive for Business ist erforderlich, um Dateien in privaten Chats freizugeben und zu speichern.

-   Wenn Benutzern keine SharePoint Online-Lizenzen zugewiesen sind, verfügen Sie über keinen OneDrive for Business-Speicher in Office 365. Die Dateifreigabe funktioniert weiterhin in Kanälen, die Benutzer können jedoch ohne OneDrive for Business-Speicher in Office 365 keine Dateien in Chats freigeben.

-   Benutzer müssen für die Erstellung von Office 365-Gruppen in Microsoft Teams aktiviert sein.

-   In Microsoft Teams funktionieren Sicherheits- und Compliance-Funktionen wie eDiscovery, Inhaltssuche, Archivierung und gesetzliche Aufbewahrungspflicht am besten in Exchange Online- und SharePoint Online-Umgebungen. Für Kanalunterhalten werden Nachrichten im Gruppenpostfach in Exchange Online als Journal erfasst und stehen für eDiscovery zur Verfügung. Bei Aktivierung von SharePoint Online und OneDrive for Business (mit Geschäfts- oder Schulkonto) für Benutzer in der gesamten Organisation stehen diese Compliance-Funktionen auch für alle Dateien innerhalb von Teams zur Verfügung.

-   Für Exchange lokal müssen Sie das neue Exchange-OAuth-Authentifizierungsprotokoll konfigurieren, wie unter [Konfigurieren der OAuth-Authentifizierung zwischen Exchange- und Exchange Online-Organisationen](https://technet.microsoft.com/en-us/library/dn594521(v=exchg.150).aspx). 

> [!NOTE]
> Wenn Ihre Organisation Compliance-Anforderungen erfüllen muss, um sicherzustellen, dass alle Besprechungsdiskussionen gefunden werden können, sollten Sie private Besprechungen deaktivieren, wenn der Organisator über ein lokales Exchange-Postfach verfügt.
> 
> [!IMPORTANT]
> In einer Exchange-hybridbereitstellung kann Inhalt von Chatnachrichten durchsucht werden, unabhängig davon, ob Chat Teilnehmer einem cloudbasierten Postfach oder ein lokales Postfach verfügen. Weitere Informationen finden lesen Sie [Searching cloudbasierten Postfächer für lokale Benutzer in Office 365](https://docs.microsoft.com/en-us/office365/securitycompliance/search-cloud-based-mailboxes-for-on-premises-users). Informationen zum Suchen nach Inhalten in Teams, lesen Sie [Inhalte Suche in der Office 365-Sicherheit & Compliance Center](https://docs.microsoft.com/en-us/Office365/SecurityCompliance/content-search#searching-microsoft-teams-and-office-365-groups).
> 
> [!TIP]
> Informationen zur Verwendung von Azure Active Directory verbinden mit Azure Active Directory synchronisiert finden Sie unter [Integration von Ihrer lokalen Identitäten mit Azure Active Directory](https://go.microsoft.com/fwlink/?linkid=854600).
