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
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d97f92b56b4a3e38489b1f99f8ba25497485495f
ms.sourcegitcommit: a610bfe9c0192432744dfaf8d5ff5c2bb5a16b00
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2020
ms.locfileid: "43191242"
---
# <a name="how-exchange-and-microsoft-teams-interact"></a>Interaktion von Exchange und Microsoft Teams

> [!Tip]
> Schauen Sie sich die folgende Sitzung an, um zu erfahren, wie Teams mit Azure Active Directory (AAD), Office 365 Groups, Exchange, SharePoint und OneDrive for Business interagieren: [Grundlagen von Microsoft Teams](https://aka.ms/teams-foundations)

Um den vollen Funktionsumfang von Teams zu nutzen, sollten alle Benutzer für Exchange Online, SharePoint Online und das Erstellen einer Office 365-Gruppe aktiviert sein.

Exchange-Postfächer der Benutzer können online oder lokal gehostet werden. Einige Features erfordern jedoch eine hybridbereitstellung, die mit Ihrem Office 365-Mandanten in Kraft ist.

Benutzer, die auf Exchange Online oder dedizierten Exchange-vNext erhielten gehostet werden, können alle Features von Teams verwenden. Sie können Teams und Kanäle erstellen und daran teilnehmen, Besprechungen erstellen und anzeigen, Anrufe tätigen und chatten, Benutzerprofil Bilder ändern (sofern dies von der Postfachrichtlinie für Outlook in der WebPost Fach Richtlinie gestattet wird) und Connectors, Registerkarten und Bots hinzufügen und konfigurieren.

Benutzer, die auf Exchange Online Dedicated (Legacy) gehostet werden, müssen mit Azure Active Directory auf Office 365 synchronisiert werden. Sie können Teams und Kanäle erstellen und daran teilnehmen, Registerkarten und Bots hinzufügen und konfigurieren sowie die Chat-und Anruffunktionen nutzen. Sie können jedoch keine Profil Bilder ändern, Besprechungen verwalten, auf Outlook-Kontakte zugreifen oder Connectors verwalten.

Benutzer mit lokal gehosteten Postfächern müssen mit Azure Active Directory synchronisiert werden. Sie können alle Features des obigen Szenarios verwenden, aber darüber hinaus können Sie auch das Bild des Benutzerprofils ändern (sofern dies von der Outlook-WebPost Fach Richtlinie ermöglicht wird), und Besprechungen verwalten, wobei Exchange Server 2016 (Kumulatives Update 3) oder höher ausgeführt wird, wobei OAuth konfiguriert ist (vorzugsweise über den Hybrid-Konfigurations-Assistenten).

Die folgende Tabelle enthält eine hilfreiche Kurzübersicht über die Verfügbarkeit von Features, die auf der Exchange-Umgebung basiert.


**Unterstützte Aktionen:**

| Benutzerpostfach ist gehostet in: | eDiscovery| Rechtliche&nbsp;Aufbewahrung | Aufbewahrungs| Team-und Kanal-Mgmt |Erstellen und Anzeigen von Besprechungen in Teams| Benutzerprofilbild bearbeiten | Anrufprotokoll | Verwalten von Kontakten | Zugreifen auf Outlook-Kontakte | Voicemail |Connectors hinzufügen und konfigurieren|Registerkarten hinzufügen und konfigurieren|Bots hinzufügen und konfigurieren| 
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
|**Exchange Online**|Ja <sup>2</sup>|Ja <sup>2</sup>|Ja |Ja |Ja |Ja<sup>8</sup>|Ja |Ja |Ja <sup>7</sup>|Ja |Ja |Ja |Ja |
|**Exchange Online Dedicated vNext**|Ja <sup>2</sup>|Ja <sup>2</sup>|Ja |Ja |Ja |Ja<sup>8</sup>|Ja |Ja |Ja <sup>7</sup>|Ja |Ja |Ja |Ja|
|**Exchange Online Dedicated – Vorgängerversion** (Synchronisierung in Azure AD erforderlich)|Ja <sup>2</sup>|Ja <sup>2, 3</sup>|Ja <sup>4|Ja|Nein|Nein|Ja|Ja|Nein|Ja <sup>5|Ja <sup>6|Ja |Ja |
|**Lokales Exchange lokal** (Synchronisierung mit Azure AD & OAuth-Konfiguration erforderlich)|Ja <sup>2</sup>| Ja <sup>2, 3</sup> |Ja <sup>4|Ja|Ja (Exchange 2016 CU3 +)|Ja<sup>8</sup> (Exchange 2016 CU3 +)|Ja |Ja|Nein|Ja <sup>5|Ja <sup>6|Ja |Ja |

<sup>1</sup> Exchange 2016 CU3 und höher wird unterstützt.  

<sup>2</sup> eDiscovery und rechtliche Aufbewahrungsmöglichkeiten für Compliance auf Kanal Nachrichten werden für alle Hosting-Optionen unterstützt.

<sup>3</sup> Teams private Chat-Nachrichten werden für diese Hosting-Option noch nicht unterstützt.

<sup>4</sup> die Aufbewahrung verwendet ein Schatten Postfach für den Online Benutzer zum Speichern von Nachrichten. [Microsoft Teams unterstützt eDiscovery für Teams-Benutzer in einer Exchange-Hybrid Umgebung](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-supports-eDiscovery-for-Teams-users-in-a/ba-p/200009).

<sup>5</sup> Teams Benutzer mit lokalem Exchange-Postfach können Voicemail in Microsoft Teams verwenden und Voicemail-Nachrichten in Outlook empfangen, aber Voicemail-Nachrichten stehen nicht zum Anzeigen oder wiedergeben innerhalb des Teams-Clients zur Verfügung.

<sup>6</sup> wenn einer der Besitzer eines Teams Connectors hinzufügen kann, können alle anderen Personen in diesem Team dies auch dann tun, wenn die Postfächer lokal gehostet werden.

<sup>7</sup> nur Kontakte im Standardordner "Kontakte". Der Zugriff auf andere Kontakteordner oder Unterordner wird nicht unterstützt.

<sup>8</sup> Teams honoriert die [Outlook-Einstellung für die Web-Postfachrichtlinie](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy) , die von mandantenadministratoren konfiguriert wird, um zu steuern, ob Benutzer Ihr Profilbild ändern können. Wenn die Einstellung **-SetPhotoEnabled** in der Richtlinie deaktiviert ist, können Benutzer Ihr Profilbild nicht hinzufügen, ändern oder entfernen. Wenn ein Benutzer beispielsweise ein Profilbild hochlädt, das von der IT-oder Personalabteilung Ihrer Organisation genehmigt wurde, ist keine Aktion erforderlich. Wenn ein Benutzer jedoch ein unangemessenes Bild hochlädt, ändern Sie das Bild entsprechend den internen Richtlinien Ihrer Organisation.

## <a name="requirements-to-get-the-most-out-of-microsoft-teams"></a>Voraussetzungen, um Microsoft Teams optimal nutzen zu können

Microsoft Teams arbeitet mit mehreren Office 365-Diensten zusammen, um Benutzern eine umfassende Erfahrung bereitzustellen. Um diese Erfahrung zu unterstützen, müssen Sie bestimmte Features oder Dienste aktivieren und Lizenzen zuweisen.

- SharePoint Online ist erforderlich, um Dateien in Teamunterhaltungen freizugeben und zu speichern. Microsoft Teams unterstützt keine lokalen SharePoint-Instanzen.

- Benutzern muss eine SharePoint Online-Lizenz zugewiesen sein, wenn Sie Dateien in Chats freigeben möchten. Wenn Benutzer nicht mit SharePoint Online-Lizenzen zugewiesen und aktiviert sind, verfügen Sie nicht über OneDrive for Business-Speicher in Office 365. Die Dateifreigabe funktioniert weiterhin in Kanälen, aber die Benutzer können keine Dateien in Chats ohne OneDrive for Business-Speicher in Office 365 freigeben.

- Benutzer müssen für die Erstellung von Office 365-Gruppen in Microsoft Teams aktiviert sein.

- Damit Microsoft Teams mit Exchange lokal arbeiten können, müssen Sie das neue Exchange OAuth-Authentifizierungsprotokoll konfigurieren, wie unter [Konfigurieren der OAuth-Authentifizierung zwischen Exchange und Exchange Online-Organisationen](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)beschrieben.

> [!NOTE]
>Für die Integration von Exchange lokal und Teams muss die erforderliche Lizenz für den Aad-synchronisierten Benutzer zugewiesen werden.

> [!IMPORTANT]
> Wenn Sie den Skype for Business-Client deinstallieren, nachdem Sie einen Benutzer in den Modus **nur für Teams** verschoben haben, funktioniert die Anwesenheit in Outlook und anderen Office-Apps möglicherweise nicht mehr. In Microsoft Teams funktionieren die Anwesenheitsinformationen einwandfrei. Um dieses Problem zu beheben, wählen Sie Ihr Profilbild in der oberen rechten Ecke von Microsoft Teams aus, und wählen Sie dann **Einstellungen**aus. Wählen Sie auf der Registerkarte **Allgemein** unter **Anwendung** **die Option Teams als Chat-App für Office registrieren aus (erfordert einen Neustart von Office-Anwendungen)**. Nachdem Sie diese Option ausgewählt haben, schließen Sie alle Office-Apps, einschließlich Outlook, und öffnen Sie Sie erneut. Nachdem Sie Outlook geöffnet haben, stehen die Anwesenheitsinformationen zur Verfügung.

## <a name="additional-considerations"></a>Weitere Überlegungen

Im folgenden finden Sie einige zusätzliche Dinge, die Sie berücksichtigen sollten, wenn Sie Microsoft Teams in Ihrer Organisation implementieren.

- In Microsoft Teams funktionieren Sicherheits- und Compliance-Funktionen wie eDiscovery, Inhaltssuche, Archivierung und gesetzliche Aufbewahrungspflicht am besten in Exchange Online- und SharePoint Online-Umgebungen. Für Kanalunterhalten werden Nachrichten im Gruppenpostfach in Exchange Online als Journal erfasst und stehen für eDiscovery zur Verfügung. Bei Aktivierung von SharePoint Online und OneDrive for Business (mit Geschäfts- oder Schulkonto) für Benutzer in der gesamten Organisation stehen diese Compliance-Funktionen auch für alle Dateien innerhalb von Teams zur Verfügung.

- Steuern und schützen Sie die Konfiguration von Konformitätsrichtlinien in Teams und Exchange mithilfe von bedingtem Zugriff. Weitere Informationen finden Sie unter [wie funktionieren bedingte Zugriffsrichtlinien für Teams?](security-compliance-overview.md#how-conditional-access-policies-work-for-teams) .

- Wenn Ihre Organisation über Compliance-Anforderungen verfügt, um sicherzustellen, dass alle Besprechungs Diskussionen auffindbar sind, sollten Sie private Besprechungen deaktivieren, wenn der Organisator über ein lokales Exchange-Postfach verfügt.

- In einer Exchange-hybridbereitstellung können Inhalte aus Chatnachrichten unabhängig davon durchsucht werden, ob Chat-Teilnehmer über ein Cloud-basiertes Postfach oder ein lokales Postfach verfügen. Weitere Informationen finden Sie unter [Suchen von Cloud-basierten Postfächern für lokale Benutzer in Office 365](https://docs.microsoft.com/office365/securitycompliance/search-cloud-based-mailboxes-for-on-premises-users). Wenn Sie mehr über die Suche nach Inhalten in Teams erfahren möchten, lesen Sie [die Inhaltssuche im Office 365 Security & Compliance Center](https://docs.microsoft.com/Office365/SecurityCompliance/content-search#searching-microsoft-teams-and-office-365-groups).

> [!TIP]
> Informationen zum Verwenden von Azure AD Connect zur Synchronisierung mit Azure Active Directory finden Sie unter [integrieren Ihrer lokalen Identitäten in Azure Active Directory](https://go.microsoft.com/fwlink/?linkid=854600).
