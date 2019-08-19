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
ms.openlocfilehash: b0f3e24d38e877d923e52de3f1c7116853737dc7
ms.sourcegitcommit: ab259764dc50bdd52efed3abb1d065ee19486946
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2019
ms.locfileid: "36393348"
---
# <a name="how-exchange-and-microsoft-teams-interact"></a>Interaktion von Exchange und Microsoft Teams

> [!Tip]
> Erfahren Sie in der folgenden Sitzung, wie Teams mit Azure Active Directory (AAD), Office 365-Gruppen, Exchange, SharePoint und OneDrive for Business interagiert: [Microsoft Teams – Grundlagen](https://aka.ms/teams-foundations)

Um den vollen Funktionsumfang von Teams zu nutzen, sollten alle Benutzer für Exchange Online, SharePoint Online und das Erstellen einer Office 365-Gruppe aktiviert sein.

Exchange-Postfächer der Benutzer können online oder lokal gehostet werden. Einige Features erfordern jedoch eine Hybridbereitstellung, um mit Ihrem Office 365-Mandanten eingesetzt werden zu können.

Benutzer, die auf Exchange Online- oder Exchange-dedizierten vNext gehostet werden, können alle Features von Teams verwenden. Sie können Teams und Kanäle erstellen und diesen beitreten, Besprechungen erstellen und anzeigen, telefonieren und chatten, Benutzerprofilbilder ändern sowie Konnektoren, Registerkarten und Bots hinzufügen und konfigurieren.

In Exchange Online Dedicated (Legacy) gehostete Benutzer müssen mit Azure Active Directory für Office 365 synchronisiert werden. Sie können Teams und Kanäle erstellen oder diesen beitreten, Registerkarten und Bots hinzufügen und konfigurieren sowie die Chat- und Anruffunktionen nutzen. Sie können jedoch keine Profil Bilder ändern, Besprechungen verwalten, auf Outlook-Kontakte zugreifen oder Konnektoren verwalten.

Benutzer mit lokalen Postfächern müssen mit Azure Active Directory synchronisiert werden. Sie können alle Funktionen des vorstehenden Szenarios nutzen, sie können jedoch zusätzlich dazu das Benutzerprofilbild ändern und Besprechungen verwalten, vorausgesetzt, dass Exchange Server 2016 (Kumulatives Update 3) oder höher lokal ausgeführt wird.

Die folgende Tabelle enthält eine hilfreiche Kurzübersicht über die Verfügbarkeit von Funktionen auf Basis der Exchange-Umgebung.


**Unterstützte Aktionen:**

| Benutzerpostfach ist gehostet in: | eDiscovery| Gesetzliche&nbsp;Aufbewahrungspflicht | Aufbewahrung| Team-und Kanalverwaltung |Besprechungen erstellen und anzeigen| Benutzerprofilbild bearbeiten | Anrufliste | Verwalten von Kontakten | Zugriff auf Outlook-Kontakte | Voicemail |Connectors hinzufügen und konfigurieren|Registerkarten hinzufügen und konfigurieren|Bots hinzufügen und konfigurieren| 
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
|**Exchange Online**|Ja <sup>2</sup>|Ja <sup>2</sup>|Ja|Ja|Ja|Ja|Ja|Ja|Ja|Ja|Ja|Ja|Ja|
|**Exchange Online Dedicated vNext**|Ja <sup>2</sup>|Ja <sup>2</sup>|Ja|Ja|Ja|Ja|Ja|Ja|Ja|Ja|Ja|Ja|Ja|
|**Exchange Online Dedicated – Vorgängerversion** (Synchronisierung in Azure AD erforderlich)|Ja <sup>2</sup>|Ja <sup>2,3</sup>|Ja <sup>4|Ja|Nein|Nein|Ja|Ja|Nein|Ja <sup>5|Ja <sup>6|Ja|Ja|
|**Exchange lokal** (Synchronisierung in Azure AD erforderlich)|Ja <sup>2</sup>| Ja <sup>2,3</sup> |Ja <sup>4|Ja|Ja (Exchange 2016 CU3+)|Ja (Exchange 2016 CU3+)|Ja|Ja|Nein|Ja <sup>5|Ja <sup>6|Ja|Ja|

<sup>1</sup> Exchange 2016 CU3 und höher wird unterstützt.  

<sup>2</sup> Bei allen Hostingoptionen wird eDiscovery unterstützt und die gesetzliche Aufbewahrungspflicht eingehalten.

<sup>3</sup> Die gesetzliche Aufbewahrungspflicht wird bei privaten Chatnachrichten in Teams derzeit noch nicht unterstützt.

<sup>4</sup> Die Aufbewahrung erfolgt in einem Schattenpostfach, in dem die Nachrichten des Online-Benutzers gespeichert werden. [Microsoft Teams unterstützt eDiscovery für Teams-Benutzer in einer Exchange-Hybridumgebung](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-supports-eDiscovery-for-Teams-users-in-a/ba-p/200009).

<sup>5</sup> Teams-Benutzer mit lokalen Exchange-Postfächern können Voicemail mit Teams verwenden und Voicemail-Nachrichten in Outlook erhalten, aber Voicemail-Nachrichten können im Team-Client nicht angezeigt oder wiedergegeben werden.

<sup>6</sup> Wenn einer der Besitzer eines Teams Konnektoren hinzufügen kann, sind alle anderen Personen in diesem Team ebenso in der Lage dazu – auch dann, wenn ihre Postfächer lokal verwaltet sind.


Weitere Informationen:

## <a name="requirements-to-get-the-most-out-of-microsoft-teams"></a>Voraussetzungen für die optimale Nutzung von Microsoft Teams

Microsoft Teams arbeitet mit mehreren Office 365-Diensten zusammen, um den Benutzern eine umfangreiche Umgebung zu bieten. Zur Unterstützung dieser Erfahrung müssen Sie bestimmte Features oder Dienste aktivieren und Lizenzen zuweisen.

- SharePoint Online ist erforderlich, um Dateien in Team-Unterhaltungen zu teilen und zu speichern. Microsoft Teams unterstützt die lokale SharePoint-Installation nicht.

- Benutzern muss eine SharePoint Online-Lizenz zugewiesen werden, wenn sie Dateien in Chats teilen möchten. Wenn Benutzer nicht mit SharePoint Online-Lizenzen ausgestattet und diese aktiviert sind, verfügen sie nicht über einen OneDrive for Business-Speicher in Office 365. Die Dateifreigabe ist in Kanälen weiterhin möglich, ohne OneDrive for Business-Speicher in Office 365 können die Benutzer jedoch keine Dateien in Chats freigeben.

- Benutzer müssen für die Erstellung von Office 365-Gruppen in Microsoft Teams aktiviert sein.

- Damit Microsoft Teams lokal mit Exchange funktionieren kann, müssen Sie das neue Exchange OAuth-Authentifizierungsprotokoll konfigurieren, wie unter [Konfigurieren der OAuth-Authentifizierung zwischen Exchange und Exchange Online-Organisationen](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help) beschrieben.

> [!NOTE]
>Für die Integration von lokalem Exchange und Teams muss die erforderliche Lizenz für den AAD-synchronisierten Benutzer zugewiesen werden.

## <a name="additional-considerations"></a>Zusätzliche Überlegungen

Hier sind einige weitere Punkte, die Sie berücksichtigen sollten, wenn Sie Microsoft Teams in Ihrer Organisation implementieren.

- In Microsoft Teams funktionieren Sicherheits- und Compliance-Funktionen wie eDiscovery, Inhaltssuche, Archivierung und gesetzliche Aufbewahrungspflicht am besten in Exchange Online- und SharePoint Online-Umgebungen. Für Kanalunterhalten werden Nachrichten im Gruppenpostfach in Exchange Online als Journal erfasst und stehen für eDiscovery zur Verfügung. Bei Aktivierung von SharePoint Online und OneDrive for Business (mit Geschäfts- oder Schulkonto) für Benutzer in der gesamten Organisation stehen diese Compliance-Funktionen auch für alle Dateien innerhalb von Teams zur Verfügung.

- Sie können die Konfiguration von Konformitätsrichtlinien in Teams und Exchange mithilfe des bedingten Zugriffs Steuern und schützen. Weitere Informationen finden Sie unter [Wie funktionieren Richtlinien für bedingten Zugriff in Verbindung mit Microsoft Teams?](security-compliance-overview.md#how-do-conditional-access-policies-work-for-teams) .

- Wenn Ihre Organisation Compliance-Anforderungen erfüllen muss, um sicherzustellen, dass alle Besprechungsdiskussionen gefunden werden können, sollten Sie private Besprechungen deaktivieren, wenn der Organisator über ein lokales Exchange-Postfach verfügt.

- Bei einer Hybridbereitstellung von Exchange sind Inhalte aus Chatnachrichten unabhängig davon durchsuchbar, ob Chat-Teilnehmer über ein Cloud-basiertes Postfach oder ein lokales-Postfach verfügen. Weitere Informationen finden Sie unter [Durchsuchen von Cloud-basierten Postfächern für lokale Benutzer in Office 365](https://docs.microsoft.com/office365/securitycompliance/search-cloud-based-mailboxes-for-on-premises-users). Weitere Informationen zur Suche nach Inhalten in Teams finden Sie unter [Ausführen einer Inhaltssuche im Office 365 Security & Compliance Center](https://docs.microsoft.com/Office365/SecurityCompliance/content-search#searching-microsoft-teams-and-office-365-groups).

> [!TIP]
> Informationen zur Verwendung von Azure AD Connect zwecks Synchronisierung mit Azure Active Directory finden Sie unter [Integrieren Ihrer lokalen Identitäten mit Azure Active Directory](https://go.microsoft.com/fwlink/?linkid=854600).
