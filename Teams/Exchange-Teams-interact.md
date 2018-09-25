---
title: Interaktion von Exchange und Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: crowe
description: Lernen Sie die Funktionen kennen, die in Microsoft Teams und den zahlreichen Exchange-Setups gemeinsam verwendet werden, wie zum Beispiel das Erstellen von und die Teilnahme an Teams, das Erstellen von Kanälen usw.
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 40ed3d2cef71077dcc098ab42c5ecf3518d3c5fc
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "25015821"
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

| Benutzerpostfach ist gehostet in: | eDiscovery| Gesetzliche Aufbewahrungspflicht | Aufbewahrung| Teams und der DDE-Kanal-mgmt |Besprechungen erstellen und anzeigen| Benutzerprofilbild bearbeiten | Die Anrufliste... | Verwalten von Kontakten | Zugriff auf Outlook-Kontakte | Voicemail |Connectors hinzufügen und konfigurieren|Registerkarten hinzufügen und konfigurieren|Bots hinzufügen und konfigurieren| 
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
|**Exchange Online**|Ja,<sup>2</sup>|Ja,<sup>2</sup>|Ja|Ja|Ja|Ja|Ja|Ja|Ja|Ja|Ja|Ja|Ja|
|**Exchange Online Dedicated vNext**|Ja,<sup>2</sup>|Ja,<sup>2</sup>|Ja|Ja|Ja|Ja|Ja|Ja|Ja|Ja|Ja|Ja|Ja|
|**Exchange Online Dedicated – Vorgängerversion** (Synchronisierung in Azure AD erforderlich)|Ja ([Liste der zugelassenen](https://support.office.com/en-us/article/searching-cloud-based-mailboxes-for-on-premises-users-in-office-365-3f7dde1a-a8ea-4366-86da-8ee6777f357c?ui=en-US&rs=en-US&ad=US))<sup>2</sup>|Ja,<sup>2, 3</sup>|Nein|Ja|Nein|Nein|Ja|Ja|Nein|Nein|Nein|Ja|Ja|
|**Exchange lokal** (Synchronisierung in Azure AD erforderlich)|Ja ([Liste der zugelassenen](https://support.office.com/en-us/article/searching-cloud-based-mailboxes-for-on-premises-users-in-office-365-3f7dde1a-a8ea-4366-86da-8ee6777f357c?ui=en-US&rs=en-US&ad=US))<sup>2</sup>|Ja,<sup>2, 3</sup>|Nein|Ja|Ja (Exchange 2016 CU3 oder höher)|Nein|Ja|Ja|Nein|Nein|Nein|Nein|Ja|
                                                            
<sup>1</sup> exchange 2016 CU3 und oben unterstützt  
eDiscovery- <sup>2</sup> und rechtlichen Aufbewahrungspflicht für Konformität auf Channel Nachrichten wird für alle Hostingoptionen unterstützt.  
<sup>3</sup> private Chatnachrichten Teams sind noch nicht für die rechtlichen Aufbewahrungspflicht für diese Hostingoption unterstützt.

Weitere Informationen:

-   Microsoft Teams unterstützt keine lokalen SharePoint-Instanzen.

-   SharePoint Online ist erforderlich, um Dateien in Teamunterhaltungen freizugeben und zu speichern.

-   OneDrive for Business ist erforderlich, um Dateien in privaten Chats freizugeben und zu speichern.

-   Wenn Benutzern keine SharePoint Online-Lizenzen zugewiesen sind, verfügen Sie über keinen OneDrive for Business-Speicher in Office 365. Die Dateifreigabe funktioniert weiterhin in Kanälen, die Benutzer können jedoch ohne OneDrive for Business-Speicher in Office 365 keine Dateien in Chats freigeben.

-   Benutzer müssen für die Erstellung von Office 365-Gruppen in Microsoft Teams aktiviert sein.

-   In Microsoft Teams funktionieren Sicherheits- und Compliance-Funktionen wie eDiscovery, Inhaltssuche, Archivierung und gesetzliche Aufbewahrungspflicht am besten in Exchange Online- und SharePoint Online-Umgebungen. Für Kanalunterhalten werden Nachrichten im Gruppenpostfach in Exchange Online als Journal erfasst und stehen für eDiscovery zur Verfügung. Bei Aktivierung von SharePoint Online und OneDrive for Business (mit Geschäfts- oder Schulkonto) für Benutzer in der gesamten Organisation stehen diese Compliance-Funktionen auch für alle Dateien innerhalb von Teams zur Verfügung.

-   Für Exchange lokal (hybridbereitstellung) müssen Sie OAuth konfigurieren, wie unter [Konfigurieren der OAuth-Authentifizierung zwischen Exchange- und Exchange Online-Organisationen](https://technet.microsoft.com/en-us/library/dn594521(v=exchg.150).aspx)beschrieben. 

> [!NOTE]
> Wenn Ihre Organisation Compliance-Anforderungen erfüllen muss, um sicherzustellen, dass alle Besprechungsdiskussionen gefunden werden können, sollten Sie private Besprechungen deaktivieren, wenn der Organisator über ein lokales Exchange-Postfach verfügt.

> [!IMPORTANT]
  Benutzer, die Unterhaltungen teilnehmen, die Teil der Liste der Chat in Microsoft-Teams sind benötigen ein Exchange Online (Cloud-basierten) Postfach für ein Administrator Chat Unterhaltungen suchen. Dies liegt daran Unterhaltungen, die Teil der Liste der Chat sind in der Cloud-basierten Postfächern Chat Teilnehmer gespeichert sind. Wenn ein Teilnehmer Chat ein Exchange Online-Postfach besitzt, werden nicht der Administrator suchen oder einen Haltestatus auf Chat Unterhaltungen setzen. Beispielsweise können in einer Exchange-hybridbereitstellung Benutzer mit lokalen Postfächern möglicherweise zur Teilnahme an Unterhaltungen, die Teil der Liste der Chat in Microsoft-Teams sind. Jedoch in diesem Fall Inhalte aus dieser Unterhaltungen nicht durchsuchbaren und kann nicht in der Warteschleife platziert werden, da der Benutzer nicht über cloudbasierten Postfächer verfügen. Weitere Informationen zu Content-Suche und Microsoft-Teams finden Sie unter [Ausführen einer Inhaltssuche im Compliance Center & Sicherheit in Office 365](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a).

> [!TIP]
  Informationen zur Verwendung von Azure Active Directory verbinden mit Azure Active Directory synchronisiert finden Sie unter [*Integration von Ihrer lokalen Identitäten mit Azure Active Directory*](https://go.microsoft.com/fwlink/?linkid=854600).
