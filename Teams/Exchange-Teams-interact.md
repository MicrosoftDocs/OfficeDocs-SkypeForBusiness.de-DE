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
ms.openlocfilehash: 2806d913fb63dcd2a7a25b26153435333282e871
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752977"
---
# <a name="how-exchange-and-microsoft-teams-interact"></a>Interaktion von Exchange und Microsoft Teams

> [!Tip]
> Schauen Sie sich die folgende Sitzung an, um zu erfahren, wie Teams mit Azure Active Directory (AAD), Microsoft 365 Groups, Exchange, SharePoint und OneDrive for Business interagieren: [Grundlagen von Microsoft Teams](https://aka.ms/teams-foundations)

Für die vollständige Team Erfahrung sollte jeder Benutzer für die Erstellung von Exchange Online, SharePoint Online und Microsoft 365-Gruppen aktiviert sein.

Exchange-Postfächer der Benutzer können online oder lokal gehostet werden. Für die Integration in lokalen Exchange ist eine Exchange-hybridbereitstellung erforderlich. Weitere Informationen zum Einrichten einer hybridbereitstellung finden Sie unter [Exchange Server-hybridbereitstellungen](https://docs.microsoft.com/exchange/exchange-hybrid).

Benutzer, die auf Exchange Online oder dedizierten Exchange-vNext erhielten gehostet werden, können alle Features von Teams verwenden. Sie können Teams und Kanäle erstellen und daran teilnehmen, Besprechungen erstellen und anzeigen, Anrufe tätigen und chatten, Benutzerprofil Bilder ändern (sofern dies von der Postfachrichtlinie für Outlook in der WebPost Fach Richtlinie gestattet wird) und Connectors, Registerkarten und Bots hinzufügen und konfigurieren.

Benutzer, die auf Exchange Online Dedicated (Legacy) gehostet werden, müssen mit Azure Active Directory auf Microsoft 365 oder Office 365 synchronisiert werden. Sie können Teams und Kanäle erstellen und daran teilnehmen, Registerkarten und Bots hinzufügen und konfigurieren sowie die Chat-und Anruffunktionen nutzen. Sie können jedoch keine Profil Bilder ändern, Besprechungen verwalten, auf Outlook-Kontakte zugreifen oder Connectors verwalten.

Benutzer mit lokal gehosteten Postfächern müssen mit Azure Active Directory synchronisiert werden. Sie können alle Funktionen des obigen Szenarios nutzen, darüber hinaus können Sie auch das Bild des Benutzerprofils ändern (sofern dies von der Outlook-Postfachrichtlinie ermöglicht wird), und Besprechungen verwalten, wobei Exchange Server 2016 (Kumulatives Update 3) oder höher ausgeführt wird, lokal mit OAuth konfiguriert ist (vorzugsweise über den Exchange-Hybrid Konfigurationsassistenten), wie unter Konfigurieren der [OAuth-Authentifizierung zwischen Exchange und Exchange Online-Organisationen](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)beschrieben. Wenn Sie die Kalender Delegierung für diese Benutzer aktivieren möchten, müssen Sie auch die Schritte 2-3 ausführen, wie unter [Konfigurieren von Integration und OAuth zwischen Skype for Business Online und Exchange Server](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)beschrieben ist. mit den folgenden Schritten wird der Team Planungsanwendung die erforderlichen Berechtigungen zum Bestätigen von Stell Vertretungs Berechtigungen bereitgestellt.

Die folgende Tabelle enthält eine hilfreiche Kurzübersicht über die Verfügbarkeit von Features, die auf der Exchange-Umgebung basiert.

> [!NOTE]
> Die Funktionsintegration zwischen lokalen Exchange und Teams erfordert eine Exchange-hybridbereitstellung. Diese Anforderung gilt zusätzlich zu den versionsspezifischen Anforderungen, die in einigen Features in der folgenden Tabelle genannt werden.

**Unterstützte Aktionen:**

| Benutzerpostfach ist gehostet in: | eDiscovery| Rechtliche &nbsp; Aufbewahrung | Aufbewahrungs| Team-und Kanal-Mgmt |Erstellen und Anzeigen von Besprechungen in Teams| Benutzerprofilbild bearbeiten | Anrufprotokoll | Verwalten von Kontakten | Zugreifen auf Outlook-Kontakte | Voicemail |Connectors hinzufügen und konfigurieren|Registerkarten hinzufügen und konfigurieren|Bots hinzufügen und konfigurieren|
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
|**Exchange Online**|Ja <sup>2</sup>|Ja <sup>2</sup>|Ja |Ja |Ja |Ja<sup>8</sup>|Ja |Ja |Ja <sup>7</sup>|Ja |Ja |Ja |Ja |
|**Exchange Online Dedicated vNext**|Ja <sup>2</sup>|Ja <sup>2</sup>|Ja |Ja |Ja |Ja<sup>8</sup>|Ja |Ja |Ja <sup>7</sup>|Ja |Ja |Ja |Ja|
|**Exchange Online Dedicated – Vorgängerversion** (Synchronisierung in Azure AD erforderlich)|Ja <sup>2</sup>|Ja <sup>2, 3</sup>|Ja <sup> 4|Ja|Nein|Nein|Ja|Ja|Nein|Ja <sup> 5|Ja <sup> 6|Ja |Ja |
|**Lokales Exchange lokal** (Synchronisierung mit Azure AD & OAuth-Konfiguration erforderlich)|Ja <sup>2</sup>| Ja <sup>2</sup> |Ja <sup> 4|Ja|Ja (Exchange 2016 CU3 +)|Nein|Ja|Ja|Nein|Ja <sup> 5|Ja <sup> 6|Ja |Ja |

<sup>1</sup> Exchange 2016 CU3 und höher wird unterstützt.  

<sup>2</sup> eDiscovery und rechtliche Aufbewahrungsmöglichkeiten für Compliance auf Kanal Nachrichten werden für alle Hosting-Optionen unterstützt.

<sup>3</sup> Teams private Chat-Nachrichten werden für diese Hosting-Option noch nicht unterstützt.

<sup>4</sup> die Aufbewahrung verwendet ein Schatten Postfach für den Online Benutzer zum Speichern von Nachrichten. [Microsoft Teams unterstützt eDiscovery für Teams-Benutzer in einer Exchange-Hybrid Umgebung](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-supports-eDiscovery-for-Teams-users-in-a/ba-p/200009).

<sup>5</sup> Teams Benutzer mit lokalem Exchange-Postfach können Voicemail in Microsoft Teams verwenden und Voicemail-Nachrichten in Outlook empfangen, aber Voicemail-Nachrichten stehen nicht zum Anzeigen oder wiedergeben innerhalb des Teams-Clients zur Verfügung.

<sup>6</sup> wenn einer der Besitzer eines Teams Connectors hinzufügen kann, können alle anderen Personen in diesem Team dies auch dann tun, wenn die Postfächer lokal gehostet werden.

<sup>7</sup> nur Kontakte im Standardordner "Kontakte". Der Zugriff auf andere Kontakteordner oder Unterordner wird nicht unterstützt.

<sup>8</sup> Teams honoriert die [Outlook-Einstellung für die Web-Postfachrichtlinie](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy) , die von mandantenadministratoren konfiguriert wird, um zu steuern, ob Benutzer Ihr Profilbild ändern können. Wenn die Einstellung **-SetPhotoEnabled** in der Richtlinie deaktiviert ist, können Benutzer Ihr Profilbild nicht hinzufügen, ändern oder entfernen. Wenn ein Benutzer beispielsweise ein Profilbild hochlädt, das von der IT-oder Personalabteilung Ihrer Organisation genehmigt wurde, ist keine Aktion erforderlich. Wenn ein Benutzer jedoch ein unangemessenes Bild hochlädt, ändern Sie das Bild entsprechend den internen Richtlinien Ihrer Organisation.

## <a name="requirements-to-get-the-most-out-of-microsoft-teams"></a>Voraussetzungen, um Microsoft Teams optimal nutzen zu können

Microsoft Teams arbeitet mit verschiedenen Microsoft 365-und Office 365-Diensten zusammen, um Benutzern eine umfangreiche Benutzererfahrung bereitzustellen. Um diese Erfahrung zu unterstützen, müssen Sie bestimmte Features oder Dienste aktivieren und Lizenzen zuweisen.

- SharePoint Online ist erforderlich, um Dateien in Teamunterhaltungen freizugeben und zu speichern. Microsoft Teams unterstützt keine lokalen SharePoint-Instanzen.

- Benutzern muss eine SharePoint Online-Lizenz zugewiesen sein, wenn Sie Dateien in Chats freigeben möchten. Wenn Benutzer nicht mit SharePoint Online-Lizenzen zugewiesen und aktiviert sind, verfügen Sie nicht über OneDrive for Business-Speicher in Microsoft 365 oder Office 365. Die Dateifreigabe funktioniert weiterhin in Kanälen, aber die Benutzer können keine Dateien in Chats ohne OneDrive for Business-Speicher in Microsoft 365 oder Office 365 freigeben.

- Benutzer müssen für die Erstellung von Microsoft 365-Gruppen aktiviert sein, damit Sie Teams in Microsoft Teams erstellen können.

- Damit Microsoft Teams mit Exchange lokal arbeiten können, müssen Sie das neue Exchange OAuth-Authentifizierungsprotokoll konfigurieren, vorzugsweise durch Ausführen des Exchange-Hybrid-Assistenten, wie unter [Konfigurieren der OAuth-Authentifizierung zwischen Exchange und Exchange Online-Organisationen](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)beschrieben. Damit Benutzer mit Exchange lokales Postfach Teams-Besprechungen im Auftrag eines anderen Benutzers planen können, müssen Sie auch die Schritte 2-3 ausführen, wie unter [Konfigurieren von Integration und OAuth zwischen Skype for Business Online und Exchange Server](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)beschrieben ist.

> [!NOTE]
> Das Outlook Teams-Add-in kann zum Planen einer Teambesprechung für Postfächer verwendet werden, die in Exchange lokal gehostet werden. Das Planen einer Teambesprechung im Auftrag eines anderen Benutzers mit lokalem Exchange-Standort erfordert jedoch Exchange 2013 CU9 und höher und das neue Exchange OAuth-Authentifizierungsprotokoll. Sowohl Stellvertretung als auch delegator müssen ein Postfach in Exchange lokal aufweisen.

> [!NOTE]
> Für die Integration von Exchange lokal und Teams muss die erforderliche Lizenz für den Aad-synchronisierten Benutzer zugewiesen werden.

> [!IMPORTANT]
> Wenn Sie den Skype for Business-Client deinstallieren, nachdem Sie einen Benutzer in den Modus **nur für Teams** verschoben haben, funktioniert die Anwesenheit in Outlook und anderen Office-Apps möglicherweise nicht mehr. In Microsoft Teams funktionieren die Anwesenheitsinformationen einwandfrei. Um dieses Problem zu beheben, wählen Sie Ihr Profilbild in der oberen rechten Ecke von Microsoft Teams aus, und wählen Sie dann **Einstellungen**aus. Wählen Sie auf der Registerkarte **Allgemein** unter **Anwendung** **die Option Teams als Chat-App für Office registrieren aus (erfordert einen Neustart von Office-Anwendungen)**. Nachdem Sie diese Option ausgewählt haben, schließen Sie alle Office-Apps, einschließlich Outlook, und öffnen Sie Sie erneut. Nachdem Sie Outlook geöffnet haben, stehen die Anwesenheitsinformationen zur Verfügung.

## <a name="additional-considerations"></a>Weitere Überlegungen

Im folgenden finden Sie einige zusätzliche Dinge, die Sie berücksichtigen sollten, wenn Sie Microsoft Teams in Ihrer Organisation implementieren.

- In Microsoft Teams funktionieren Sicherheits- und Compliance-Funktionen wie eDiscovery, Inhaltssuche, Archivierung und gesetzliche Aufbewahrungspflicht am besten in Exchange Online- und SharePoint Online-Umgebungen. Für Kanalunterhalten werden Nachrichten im Gruppenpostfach in Exchange Online als Journal erfasst und stehen für eDiscovery zur Verfügung. Bei Aktivierung von SharePoint Online und OneDrive for Business (mit Geschäfts- oder Schulkonto) für Benutzer in der gesamten Organisation stehen diese Compliance-Funktionen auch für alle Dateien innerhalb von Teams zur Verfügung.

- Steuern und schützen Sie die Konfiguration von Konformitätsrichtlinien in Teams und Exchange mithilfe von bedingtem Zugriff. Weitere Informationen finden Sie unter [wie funktionieren bedingte Zugriffsrichtlinien für Teams?](security-compliance-overview.md#how-conditional-access-policies-work-for-teams) .

- Wenn Ihre Organisation über Compliance-Anforderungen verfügt, um sicherzustellen, dass alle Besprechungs Diskussionen auffindbar sind, sollten Sie private Besprechungen deaktivieren, wenn der Organisator über ein lokales Exchange-Postfach verfügt.

- In einer Exchange-hybridbereitstellung können Inhalte aus Chatnachrichten unabhängig davon durchsucht werden, ob Chat-Teilnehmer über ein Cloud-basiertes Postfach oder ein lokales Postfach verfügen. Weitere Informationen finden Sie unter [Suchen von Cloud-basierten Postfächern für lokale Benutzer](https://docs.microsoft.com/office365/securitycompliance/search-cloud-based-mailboxes-for-on-premises-users). Wenn Sie mehr über die Suche nach Inhalten in Teams erfahren möchten, lesen Sie [die Inhaltssuche im Microsoft 365 Compliance Center](https://docs.microsoft.com/Office365/SecurityCompliance/content-search#searching-microsoft-teams-and-office-365-groups).

> [!TIP]
> Informationen zum Verwenden von Azure AD Connect zur Synchronisierung mit Azure Active Directory finden Sie unter [integrieren Ihrer lokalen Identitäten in Azure Active Directory](https://go.microsoft.com/fwlink/?linkid=854600).

## <a name="requirements-for-on-premises-exchange-mailbox-user"></a>Anforderungen für lokale Exchange-Postfachbenutzer

Wenn Benutzer die Möglichkeit haben möchten, eine Teambesprechung mithilfe von Exchange zu planen, müssen Sie Folgendes sicherstellen:

- Sowohl Stellvertretung als auch delegator müssen über ein Postfach auf dem Exchange-Server verfügen.

- Automatisch entdecken (automatisch) v2 ist erforderlich, damit der Team Dienst eine nicht authentifizierte Ermittlung des Postfachs des Benutzers durchführen kann. Autod v2 wird in Exchange 2013 CU19 + unterstützt.

- Der Exchange-Server muss mit dem Auth-Server für EVOSTS konfiguriert sein. Diese wird automatisch als Teil des Hybrid-Assistenten für Exchange (HWA) konfiguriert.

    Wenn Sie Hwa nicht ausführen möchten, können Sie den auth-Server für Evo STS auf dem Exchange-Server manuell erstellen, indem Sie die [OAuth-Authentifizierung zwischen Exchange-und Exchange Online-Organisationen konfigurieren](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help). Wir empfehlen jedoch, dass Sie die Hwa verwenden.

- Auf dem Exchange-Server muss eine Partner Anwendung mit einer Anwendungs-ID von **Skype for Business Online, 00000004-0000-0ff1-ce00-000000000000,** konfiguriert sein. Die ID wird vom Team Planungsdienst und einem verknüpften Benutzerkonto verwendet, das die folgenden Eigenschaften hat:

  - Im Exchange-Adressbuch verborgen. Es empfiehlt sich, die Datei aus dem Adressbuch zu verbergen, da es sich um ein deaktiviertes Benutzerkonto handelt.

  - Zuordnung der Exchange-Verwaltungsrolle von **UserApplication**

Um die Integration abzuschließen, führen Sie die Schritte 1-3 in [wie konfigurieren Sie die OAuth-Authentifizierung zwischen Ihren lokalen Exchange-und Exchange Online-Organisationen?](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help#how-do-you-configure-oauth-authentication-between-your-on-premises-exchange-and-exchange-online-organizations) Beachten Sie, dass Schritt 2 eine Rollenzuweisung für ArchiveApplication enthält, die für die Delegierung nicht erforderlich ist, aber zum Archivieren des SFB-Online Chats in einem Exchange-Postfach dient.
