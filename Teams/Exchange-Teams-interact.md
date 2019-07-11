---
title: Interaktion von Exchange und Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: dstrome
description: Lernen Sie die Funktionen kennen, die in Microsoft Teams und den zahlreichen Exchange-Setups gemeinsam verwendet werden, wie zum Beispiel das Erstellen von und die Teilnahme an Teams, das Erstellen von Kanälen usw.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5bedaee766005787bb7b532f4f5561faf91dd35d
ms.sourcegitcommit: bd9b29cdaa183b1f5cc2d643a5a2d231a56a2c3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "35614205"
---
# <a name="how-exchange-and-microsoft-teams-interact"></a>Interaktion von Exchange und Microsoft Teams

> [!Tip]
> Schauen Sie sich die folgende Sitzung an, um zu erfahren, wie Teams mit Azure Active Directory (AAD), Office 365 Groups, Exchange, SharePoint und OneDrive for Business interagieren: [Grundlagen von Microsoft Teams](https://aka.ms/teams-foundations)

Um den vollen Funktionsumfang von Teams zu nutzen, sollten alle Benutzer für Exchange Online, SharePoint Online und das Erstellen einer Office 365-Gruppe aktiviert sein.

Die Exchange-Postfächer der Benutzer können online oder lokal gehostet werden. In Exchange Online oder Exchange Dedicated vNext gehostete Benutzer können alle Funktionen von Microsoft Teams verwenden. Sie können Teams und Kanäle erstellen und diesen beitreten, Besprechungen erstellen und anzeigen, anrufen und chatten, Benutzerprofilbilder ändern sowie Connectors, Registerkarten und Bots hinzufügen und konfigurieren.

In Exchange Online Dedicated – Legacy oder Exchange lokal gehostete Benutzer müssen mit Azure Active Directory für Office 365 synchronisiert werden. Sie können Teams und Kanäle erstellen oder an diesen teilnehmen, Registerkarten und Bots hinzufügen und konfigurieren sowie chatten und anrufen. Sie können jedoch keine Benutzerprofilbilder ändern oder Connectors hinzufügen und konfigurieren. Sie können Nachrichten von Connectors empfangen, die von anderen Benutzern konfiguriert wurden. Die Möglichkeiten zum Erstellen und Anzeigen von Besprechungen hängen von der Version ab: Das Erstellen und Anzeigen von Besprechungen wird für das kumulative Update 3 (CU3) von Exchange 2016 und höher unterstützt, aber nicht für niedrigere Versionen.

Die folgende Tabelle enthält Informationen für Benutzer, für die Exchange Online in verschiedenen Umgebungen gehostet ist.

**Unterstützte Aktionen:**

| Benutzerpostfach ist gehostet in: | eDiscovery| Rechtliche&nbsp;Aufbewahrung | Aufbewahrungs| Team-und Kanal-Mgmt |Besprechungen erstellen und anzeigen| Benutzerprofilbild bearbeiten | Anrufprotokoll | Verwalten von Kontakten | Zugreifen auf Outlook-Kontakte | Voicemail |Connectors hinzufügen und konfigurieren|Registerkarten hinzufügen und konfigurieren|Bots hinzufügen und konfigurieren| 
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
|**Exchange Online**|Ja <sup>2</sup>|Ja <sup>2</sup>|Ja |Ja|Ja|Ja|Ja|Ja|Ja|Ja|Ja|Ja |Ja|
|**Exchange Online Dedicated vNext**|Ja <sup>2</sup>|Ja <sup>2</sup>|Ja |Ja |Ja|Ja|Ja |Ja|Ja|Ja|Ja |Ja |Ja|
|**Exchange Online Dedicated – Vorgängerversion** (Synchronisierung in Azure AD erforderlich)|Ja <sup>2</sup>|Ja <sup>2, 3</sup>|Ja <sup>4|Ja|Nein|Nein|Ja|Ja|Nein|Ja <sup>5|Ja |Ja |Ja|
|**Exchange lokal** (Synchronisierung in Azure AD erforderlich)|Ja <sup>2</sup>| Ja <sup>2, 3</sup> |Ja <sup>4|Ja|Ja (Exchange 2016 CU3 +)|Ja (Exchange 2016 CU3 +)|Ja |Ja|Nein|Ja <sup>5|Ja |Ja |Ja|

<sup>1</sup> Exchange 2016 CU3 und höher unterstützt  
<sup>2</sup> eDiscovery und rechtliche Aufbewahrungsmöglichkeiten für Compliance auf Kanal Nachrichten werden für alle Hosting-Optionen unterstützt.  
<sup>3</sup> Teams private Chat-Nachrichten werden für diese Hosting-Option noch nicht unterstützt.

<sup>4</sup> die Aufbewahrung verwendet ein Schatten Postfach für den Online Benutzer zum Speichern von Nachrichten. [Microsoft Teams unterstützt eDiscovery für Teams-Benutzer in einer Exchange-Hybrid Umgebung](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-supports-eDiscovery-for-Teams-users-in-a/ba-p/200009).

<sup>5</sup> Teams Benutzer mit dem lokalen Exchange-Postfach können Voicemail in Microsoft Teams verwenden und Voicemail-Nachrichten in Outlook empfangen, aber Voicemail-Nachrichten stehen nicht zum Anzeigen oder wiedergeben innerhalb des Teams-Clients zur Verfügung.

## <a name="requirements-to-get-the-most-out-of-microsoft-teams"></a>Voraussetzungen, um Microsoft Teams optimal nutzen zu können

Microsoft Teams arbeitet mit mehreren Office 365-Diensten zusammen, um Benutzern eine umfassende Erfahrung bereitzustellen. Um diese Erfahrung zu unterstützen, müssen Sie bestimmte Features oder Dienste aktivieren und Lizenzen zuweisen.

- SharePoint Online ist erforderlich, um Dateien in Teamunterhaltungen freizugeben und zu speichern. Microsoft Teams unterstützt keine lokalen SharePoint-Instanzen.

- Benutzern muss eine SharePoint Online-Lizenz zugewiesen sein, wenn Sie Dateien in Chats freigeben möchten. Wenn Benutzer nicht mit SharePoint Online-Lizenzen zugewiesen und aktiviert sind, verfügen Sie nicht über OneDrive for Business-Speicher in Office 365. Die Dateifreigabe funktioniert weiterhin in Kanälen, aber die Benutzer können keine Dateien in Chats ohne OneDrive for Business-Speicher in Office 365 freigeben.

- Benutzer müssen für die Erstellung von Office 365-Gruppen in Microsoft Teams aktiviert sein.

- Damit Microsoft Teams mit Exchange lokal arbeiten können, müssen Sie das neue Exchange OAuth-Authentifizierungsprotokoll konfigurieren, wie unter [Konfigurieren der OAuth-Authentifizierung zwischen Exchange und Exchange Online-Organisationen](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)beschrieben.

> [!NOTE]
>Für die Integration von Exchange lokal und Teams muss die erforderliche Lizenz für den Aad-synchronisierten Benutzer zugewiesen werden.

## <a name="additional-considerations"></a>Weitere Überlegungen

Im folgenden finden Sie einige zusätzliche Dinge, die Sie berücksichtigen sollten, wenn Sie Microsoft Teams in Ihrer Organisation implementieren.

- In Microsoft Teams funktionieren Sicherheits- und Compliance-Funktionen wie eDiscovery, Inhaltssuche, Archivierung und gesetzliche Aufbewahrungspflicht am besten in Exchange Online- und SharePoint Online-Umgebungen. Für Kanalunterhalten werden Nachrichten im Gruppenpostfach in Exchange Online als Journal erfasst und stehen für eDiscovery zur Verfügung. Bei Aktivierung von SharePoint Online und OneDrive for Business (mit Geschäfts- oder Schulkonto) für Benutzer in der gesamten Organisation stehen diese Compliance-Funktionen auch für alle Dateien innerhalb von Teams zur Verfügung.

- Steuern und schützen Sie die Konfiguration von Konformitätsrichtlinien in Teams und Exchange mithilfe von bedingtem Zugriff. Weitere Informationen finden Sie unter [wie funktionieren bedingte Zugriffsrichtlinien für Teams?](security-compliance-overview.md#how-do-conditional-access-policies-work-for-teams) .

- Wenn Ihre Organisation über Compliance-Anforderungen verfügt, um sicherzustellen, dass alle Besprechungs Diskussionen auffindbar sind, sollten Sie private Besprechungen deaktivieren, wenn der Organisator über ein lokales Exchange-Postfach verfügt.

- In einer Exchange-hybridbereitstellung können Inhalte aus Chatnachrichten unabhängig davon durchsucht werden, ob Chat-Teilnehmer über ein Cloud-basiertes Postfach oder ein lokales Postfach verfügen. Weitere Informationen finden Sie unter [Suchen von Cloud-basierten Postfächern für lokale Benutzer in Office 365](https://docs.microsoft.com/office365/securitycompliance/search-cloud-based-mailboxes-for-on-premises-users). Wenn Sie mehr über die Suche nach Inhalten in Teams erfahren möchten, lesen Sie [die Inhaltssuche im Office 365 Security #a0 Compliance Center](https://docs.microsoft.com/Office365/SecurityCompliance/content-search#searching-microsoft-teams-and-office-365-groups).

> [!TIP]
> Informationen zum Verwenden von Azure AD Connect zur Synchronisierung mit Azure Active Directory finden Sie unter [integrieren Ihrer lokalen Identitäten in Azure Active Directory](https://go.microsoft.com/fwlink/?linkid=854600).
