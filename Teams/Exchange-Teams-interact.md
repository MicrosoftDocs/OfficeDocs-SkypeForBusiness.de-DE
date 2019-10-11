---
title: Interaktion von Exchange und Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: Lernen Sie die Funktionen kennen, die in Microsoft Teams und den zahlreichen Exchange-Setups gemeinsam verwendet werden, wie zum Beispiel das Erstellen von und die Teilnahme an Teams, das Erstellen von Kanälen usw.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 42d15f32cbdf7326ea8daf85860bd451d93ed3f3
ms.sourcegitcommit: de7e0afbd40bbe52994ab99d85cf9e95ecbc4a6c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2019
ms.locfileid: "37434651"
---
# <a name="how-exchange-and-microsoft-teams-interact"></a>Interaktion von Exchange und Microsoft Teams

> [!Tip]
> Schauen Sie sich die folgende Sitzung an, um zu erfahren, wie Teams mit Azure Active Directory (AAD), Office 365 Groups, Exchange, SharePoint und OneDrive for Business interagieren: [Grundlagen von Microsoft Teams](https://aka.ms/teams-foundations)

Um den vollen Funktionsumfang von Teams zu nutzen, sollten alle Benutzer für Exchange Online, SharePoint Online und das Erstellen einer Office 365-Gruppe aktiviert sein.

Exchange-Postfächer der Benutzer können online oder lokal gehostet werden. Einige Features erfordern jedoch eine hybridbereitstellung, die mit Ihrem Office 365-Mandanten in Kraft ist.

Benutzer, die auf Exchange Online oder dedizierten Exchange-vNext erhielten gehostet werden, können alle Features von Teams verwenden. Sie können Teams und Kanäle erstellen und daran teilnehmen, Besprechungen erstellen und anzeigen, Anrufe führen und chatten, Benutzerprofil Bilder ändern sowie Connectors, Registerkarten und Bots hinzufügen und konfigurieren.

Benutzer, die auf Exchange Online Dedicated (Legacy) gehostet werden, müssen mit Azure Active Directory auf Office 365 synchronisiert werden. Sie können Teams und Kanäle erstellen und daran teilnehmen, Registerkarten und Bots hinzufügen und konfigurieren sowie die Chat-und Anruffunktionen nutzen. Sie können jedoch keine Profil Bilder ändern, Besprechungen verwalten, auf Outlook-Kontakte zugreifen oder Connectors verwalten.

Benutzer mit lokal gehosteten Postfächern müssen mit Azure Active Directory synchronisiert werden. Sie können alle Funktionen im obigen Szenario nutzen, aber darüber hinaus können Sie auch das Benutzerprofil Bild ändern und Besprechungen verwalten, wobei Exchange Server 2016 (Kumulatives Update 3) oder höher ausgeführt wird und lokal ausgeführt wird.

Die folgende Tabelle enthält eine hilfreiche Kurzübersicht über die Verfügbarkeit von Features, die auf der Exchange-Umgebung basiert.


**Unterstützte Aktionen:**

| Benutzerpostfach ist gehostet in: | eDiscovery| Rechtliche&nbsp;Aufbewahrung | Aufbewahrungs| Team-und Kanal-Mgmt |Besprechungen erstellen und anzeigen| Benutzerprofilbild bearbeiten | Anrufprotokoll | Verwalten von Kontakten | Zugreifen auf Outlook-Kontakte | Voicemail |Connectors hinzufügen und konfigurieren|Registerkarten hinzufügen und konfigurieren|Bots hinzufügen und konfigurieren| 
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
|**Exchange Online**|Ja <sup>2</sup>|Ja <sup>2</sup>|Ja |Ja |Ja |Ja |Ja |Ja |Ja |Ja |Ja |Ja |Ja |
|**Exchange Online Dedicated vNext**|Ja <sup>2</sup>|Ja <sup>2</sup>|Ja |Ja |Ja |Ja |Ja |Ja |Ja |Ja |Ja |Ja |Ja|
|**Exchange Online Dedicated – Vorgängerversion** (Synchronisierung in Azure AD erforderlich)|Ja <sup>2</sup>|Ja <sup>2, 3</sup>|Ja <sup>4|Ja|Nein|Nein|Ja|Ja|Nein|Ja <sup>5|Ja <sup>6|Ja |Ja |
|**Exchange lokal** (Synchronisierung mit Azure AD erforderlich)|Ja <sup>2</sup>| Ja <sup>2, 3</sup> |Ja <sup>4|Ja|Ja (Exchange 2016 CU3 +)|Ja (Exchange 2016 CU3 +)|Ja |Ja|Nein|Ja <sup>5|Ja <sup>6|Ja |Ja |

<sup>1</sup> Exchange 2016 CU3 und höher wird unterstützt.  

<sup>2</sup> eDiscovery und rechtliche Aufbewahrungsmöglichkeiten für Compliance auf Kanal Nachrichten werden für alle Hosting-Optionen unterstützt.

<sup>3</sup> Teams private Chat-Nachrichten werden für diese Hosting-Option noch nicht unterstützt.

<sup>4</sup> die Aufbewahrung verwendet ein Schatten Postfach für den Online Benutzer zum Speichern von Nachrichten. [Microsoft Teams unterstützt eDiscovery für Teams-Benutzer in einer Exchange-Hybrid Umgebung](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-supports-eDiscovery-for-Teams-users-in-a/ba-p/200009).

<sup>5</sup> Teams Benutzer mit lokalem Exchange-Postfach können Voicemail in Microsoft Teams verwenden und Voicemail-Nachrichten in Outlook empfangen, aber Voicemail-Nachrichten stehen nicht zum Anzeigen oder wiedergeben innerhalb des Teams-Clients zur Verfügung.

<sup>6</sup> wenn einer der Besitzer eines Teams Connectors hinzufügen kann, können alle anderen Personen in diesem Team dies auch dann tun, wenn die Postfächer lokal gehostet werden.


Weitere Informationen:

## <a name="requirements-to-get-the-most-out-of-microsoft-teams"></a>Voraussetzungen, um Microsoft Teams optimal nutzen zu können

Microsoft Teams arbeitet mit mehreren Office 365-Diensten zusammen, um Benutzern eine umfassende Erfahrung bereitzustellen. Um diese Erfahrung zu unterstützen, müssen Sie bestimmte Features oder Dienste aktivieren und Lizenzen zuweisen.

- SharePoint Online ist erforderlich, um Dateien in Teamunterhaltungen freizugeben und zu speichern. Microsoft Teams unterstützt keine lokalen SharePoint-Instanzen.

- Benutzern muss eine SharePoint Online-Lizenz zugewiesen sein, wenn Sie Dateien in Chats freigeben möchten. Wenn Benutzer nicht mit SharePoint Online-Lizenzen zugewiesen und aktiviert sind, verfügen Sie nicht über OneDrive for Business-Speicher in Office 365. Die Dateifreigabe funktioniert weiterhin in Kanälen, aber die Benutzer können keine Dateien in Chats ohne OneDrive for Business-Speicher in Office 365 freigeben.

- Benutzer müssen für die Erstellung von Office 365-Gruppen in Microsoft Teams aktiviert sein.

- Damit Microsoft Teams mit Exchange lokal arbeiten können, müssen Sie das neue Exchange OAuth-Authentifizierungsprotokoll konfigurieren, wie unter [Konfigurieren der OAuth-Authentifizierung zwischen Exchange und Exchange Online-Organisationen](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)beschrieben.

> [!NOTE]
>Für die Integration von Exchange lokal und Teams muss die erforderliche Lizenz für den Aad-synchronisierten Benutzer zugewiesen werden.

> [!IMPORTANT]
> Wenn Sie den Skype for Business-Client deinstallieren, nachdem Sie einen Benutzer in den **TeamsOnly**-Modus verschoben haben, funktionieren die Anwesenheitsinformationen in Outlook und anderen Office-Apps nicht mehr. In Microsoft Teams funktionieren die Anwesenheitsinformationen einwandfrei. Problemumgehung: damit die Anwesenheit in Outlook (und anderen Office-Apps) angezeigt wird, muss Skype for Business installiert sein, auch wenn Sie nur Teams im Modus " **nur Teams** " ausführen. Das Problem ist Microsoft bekannt, und es wird gerade an einer Lösung gearbeitet.

## <a name="additional-considerations"></a>Weitere Überlegungen

Im folgenden finden Sie einige zusätzliche Dinge, die Sie berücksichtigen sollten, wenn Sie Microsoft Teams in Ihrer Organisation implementieren.

- In Microsoft Teams funktionieren Sicherheits- und Compliance-Funktionen wie eDiscovery, Inhaltssuche, Archivierung und gesetzliche Aufbewahrungspflicht am besten in Exchange Online- und SharePoint Online-Umgebungen. Für Kanalunterhalten werden Nachrichten im Gruppenpostfach in Exchange Online als Journal erfasst und stehen für eDiscovery zur Verfügung. Bei Aktivierung von SharePoint Online und OneDrive for Business (mit Geschäfts- oder Schulkonto) für Benutzer in der gesamten Organisation stehen diese Compliance-Funktionen auch für alle Dateien innerhalb von Teams zur Verfügung.

- Steuern und schützen Sie die Konfiguration von Konformitätsrichtlinien in Teams und Exchange mithilfe von bedingtem Zugriff. Weitere Informationen finden Sie unter [wie funktionieren bedingte Zugriffsrichtlinien für Teams?](security-compliance-overview.md#how-do-conditional-access-policies-work-for-teams) .

- Wenn Ihre Organisation über Compliance-Anforderungen verfügt, um sicherzustellen, dass alle Besprechungs Diskussionen auffindbar sind, sollten Sie private Besprechungen deaktivieren, wenn der Organisator über ein lokales Exchange-Postfach verfügt.

- In einer Exchange-hybridbereitstellung können Inhalte aus Chatnachrichten unabhängig davon durchsucht werden, ob Chat-Teilnehmer über ein Cloud-basiertes Postfach oder ein lokales Postfach verfügen. Weitere Informationen finden Sie unter [Suchen von Cloud-basierten Postfächern für lokale Benutzer in Office 365](https://docs.microsoft.com/office365/securitycompliance/search-cloud-based-mailboxes-for-on-premises-users). Wenn Sie mehr über die Suche nach Inhalten in Teams erfahren möchten, lesen Sie [die Inhaltssuche im Office 365 Security #a0 Compliance Center](https://docs.microsoft.com/Office365/SecurityCompliance/content-search#searching-microsoft-teams-and-office-365-groups).

> [!TIP]
> Informationen zum Verwenden von Azure AD Connect zur Synchronisierung mit Azure Active Directory finden Sie unter [integrieren Ihrer lokalen Identitäten in Azure Active Directory](https://go.microsoft.com/fwlink/?linkid=854600).
