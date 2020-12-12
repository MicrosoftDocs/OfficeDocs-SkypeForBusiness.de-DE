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
ms.openlocfilehash: 6e2e6af198c578279e2af8928e8a6ac299f262a5
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/12/2020
ms.locfileid: "49661900"
---
# <a name="how-exchange-and-microsoft-teams-interact"></a>Interaktion von Exchange und Microsoft Teams

> [!Tip]
> Schauen Sie sich die folgende Sitzung an, um zu erfahren, wie Teams mit Azure Active Directory (AAD), Microsoft 365 Groups, Exchange, SharePoint und OneDrive for Business interagieren: [Grundlagen von Microsoft Teams](https://aka.ms/teams-foundations)

Für die vollständige Team Erfahrung sollte jeder Benutzer für die Erstellung von Exchange Online, SharePoint Online und Microsoft 365-Gruppen aktiviert sein.

Exchange-Postfächer der Benutzer können online oder lokal gehostet werden.

Benutzer, die auf Exchange Online oder dedizierten Exchange-vNext erhielten gehostet werden, können alle Features von Teams verwenden. Sie können Teams und Kanäle erstellen und daran teilnehmen, Besprechungen erstellen und anzeigen, Anrufe tätigen und chatten, Benutzerprofil Bilder ändern (sofern dies von der Postfachrichtlinie für Outlook in der WebPost Fach Richtlinie gestattet wird) und Connectors, Registerkarten und Bots hinzufügen und konfigurieren. Eine umfassendere Liste der verfügbaren Features finden Sie in der nachstehenden Tabelle.

Benutzer, die auf Exchange Online Dedicated (Legacy) gehostet werden, müssen mit Azure Active Directory auf Microsoft 365 oder Office 365 synchronisiert werden. Sie können Teams und Kanäle erstellen und daran teilnehmen, Registerkarten und Bots hinzufügen und konfigurieren sowie die Chat-und Anruffunktionen nutzen. Sie können jedoch keine Profil Bilder ändern, Besprechungen verwalten, auf Outlook-Kontakte zugreifen oder Connectors verwalten.

> [!IMPORTANT]
> Für die Integration in lokale Umgebungen wird dringend empfohlen, dass Sie über eine vollständige klassische Hybrid Bereitstellung mit Exchange Server 2016 oder höher verfügen. Die moderne Hybrid-Unterstützung ist auf Frei/Gebucht-Funktionen limitiert und bietet beispielsweise keine Kalenderintegration von Teams in Postfächer vor Ort. Weitere Informationen zum Einrichten einer hybridbereitstellung finden Sie unter [Exchange Server-hybridbereitstellungen](https://docs.microsoft.com/exchange/exchange-hybrid).

Benutzer mit lokal gehosteten Postfächern müssen mit Azure Active Directory synchronisiert werden. Sie können alle Funktionen in dem obigen Szenario nutzen, aber darüber hinaus können Sie Besprechungen verwalten, wenn die Anforderungen unter [Anforderungen für Lokal gehostete Postfächer](#requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises) erfüllt sind.

Die folgende Tabelle enthält eine hilfreiche Kurzübersicht über die Verfügbarkeit von Features, die auf der Exchange-Umgebung basiert.

**Unterstützte Aktionen:**

| Benutzerpostfach ist gehostet in:                                        | eDiscovery       | Rechtliche &nbsp; Aufbewahrung    | Aufbewahrungs  | Team-und Kanal-Mgmt | Erstellen und Anzeigen von Besprechungen in Teams | Benutzerprofilbild bearbeiten | Anrufprotokoll | Verwalten von Kontakten | Zugreifen auf Outlook-Kontakte | Voicemail  | Connectors hinzufügen und konfigurieren | Registerkarten hinzufügen und konfigurieren | Bots hinzufügen und konfigurieren |
|---------------------------------------------------------------------|------------------|--------------------|------------|-----------------------|-----------------------------------|-----------------------------|--------------|-----------------|-------------------------|------------|------------------------------|------------------------|------------------------|
| **Exchange Online**                                                 | Ja <sup>1</sup> | Ja <sup>1</sup>   | Ja        | Ja                   | Ja                               | Ja<sup>7</sup>             | Ja          | Ja             | Ja <sup>6</sup>        | Ja        | Ja                          | Ja                    | Ja                    |
| **Exchange Online Dedicated vNext**                                 | Ja <sup>1</sup> | Ja <sup>1</sup>   | Ja        | Ja                   | Ja                               | Ja<sup>7</sup>             | Ja          | Ja             | Ja <sup>6</sup>        | Ja        | Ja                          | Ja                    | Ja                    |
| **Exchange Online Dedicated – Vorgängerversion** (Synchronisierung in Azure AD erforderlich)  | Ja <sup>1</sup> | Ja <sup>1, 2</sup> | Ja <sup>3</sup> | Ja                   | Nein                                | Nein                          | Ja          | Ja             | Nein                      | Ja <sup>4</sup> | Ja <sup>5</sup>                   | Ja                    | Ja                    |
| **Lokales Exchange** (Synchronisierung mit Azure AD) | Ja <sup>1</sup> | Ja <sup>1</sup>   | Ja <sup>3</sup> | Ja                   | Ja <sup>8</sup>         | Nein                          | Ja          | Ja             | Nein                      | Ja <sup>4</sup> | Ja <sup>5</sup>                   | Ja                    | Ja                    |

<sup>1</sup> eDiscovery und rechtliche Aufbewahrungsmöglichkeiten für Compliance auf Kanal Nachrichten werden für alle Hosting-Optionen unterstützt.

<sup>2</sup> Teams private Chat-Nachrichten werden für diese Hosting-Option noch nicht unterstützt.

<sup>3</sup> bei der Aufbewahrung wird ein Shadow-Postfach für den Online Benutzer zum Speichern von Nachrichten verwendet.

<sup>4</sup> Teams-Benutzer mit lokalem Exchange-Postfach können Voicemail in Microsoft Teams verwenden und Voicemail-Nachrichten in Outlook empfangen, aber Voicemail-Nachrichten stehen nicht zum Anzeigen oder wiedergeben innerhalb des Teams-Clients zur Verfügung.

<sup>5</sup> wenn einer der Besitzer eines Teams Connectors hinzufügen kann, können alle anderen Personen in diesem Team dies auch dann tun, wenn die Postfächer lokal gehostet werden.

<sup>6</sup> nur Kontakte im Standardordner "Kontakte". Der Zugriff auf andere Kontakteordner oder Unterordner wird nicht unterstützt.

<sup>7</sup> Teams honoriert die [Outlook-Einstellung für die Web-Postfachrichtlinie](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy) , die von mandantenadministratoren konfiguriert wird, um zu steuern, ob Benutzer Ihr Profilbild ändern können. Wenn die Einstellung **-SetPhotoEnabled** in der Richtlinie deaktiviert ist, können Benutzer Ihr Profilbild nicht hinzufügen, ändern oder entfernen. Wenn ein Benutzer beispielsweise ein Profilbild hochlädt, das von der IT-oder Personalabteilung Ihrer Organisation genehmigt wurde, ist keine Aktion erforderlich. Wenn ein Benutzer jedoch ein unangemessenes Bild hochlädt, ändern Sie es gemäß den internen Richtlinien Ihrer Organisation.

<sup>8</sup> Sie müssen die Anforderungen erfüllen, die im Abschnitt [Anforderungen zum Erstellen und Anzeigen von Besprechungen für Postfächer gehostet werden, die lokal gehostet werden](#requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises) .

## <a name="requirements-to-get-the-most-out-of-microsoft-teams"></a>Voraussetzungen, um Microsoft Teams optimal nutzen zu können

Microsoft Teams arbeitet mit verschiedenen Microsoft 365-und Office 365-Diensten zusammen, um Benutzern eine umfassende Erfahrung bereitzustellen. Um diese Erfahrung zu unterstützen, müssen Sie bestimmte Features oder Dienste aktivieren und Lizenzen zuweisen.

- Benutzern muss eine Exchange Online-Lizenz zugewiesen sein.

- SharePoint Online ist erforderlich, um Dateien in Teamunterhaltungen freizugeben und zu speichern. Microsoft Teams unterstützt keine lokalen SharePoint-Instanzen.

- Benutzern muss eine SharePoint Online-Lizenz zugewiesen sein, wenn Sie Dateien in Chats freigeben möchten. Wenn Benutzer nicht mit SharePoint Online-Lizenzen zugewiesen und aktiviert sind, verfügen Sie nicht über OneDrive for Business-Speicher in Microsoft 365 oder Office 365. Die Dateifreigabe funktioniert weiterhin in Kanälen, aber die Benutzer können keine Dateien in Chats ohne OneDrive for Business-Speicher in Microsoft 365 oder Office 365 freigeben.

- Benutzer müssen für die Erstellung von Microsoft 365-Gruppen aktiviert sein, damit Sie Teams in Microsoft Teams erstellen können.

  > [!IMPORTANT]
  > Wenn Sie den Skype for Business-Client deinstallieren, nachdem Sie einen Benutzer in den Modus **nur für Teams** verschoben haben, funktioniert die Anwesenheit in Outlook und anderen Office-Apps möglicherweise nicht mehr. In Microsoft Teams funktionieren die Anwesenheitsinformationen einwandfrei. Um dieses Problem zu beheben, wählen Sie Ihr Profilbild in der oberen rechten Ecke von Microsoft Teams aus, und wählen Sie dann **Einstellungen** aus. Wählen Sie auf der Registerkarte **Allgemein** unter **Anwendung** **die Option Teams als Chat-App für Office registrieren aus (erfordert einen Neustart von Office-Anwendungen)**. Nachdem Sie diese Option ausgewählt haben, schließen Sie alle Office-Apps, einschließlich Outlook, und öffnen Sie Sie erneut. Nachdem Sie Outlook geöffnet haben, stehen die Anwesenheitsinformationen zur Verfügung.

## <a name="requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises"></a>Voraussetzungen für das Erstellen und Anzeigen von Besprechungen für Lokal gehostete Postfächer

Wenn Postfächer lokal gehostet werden, müssen zum Erstellen und Anzeigen von Besprechungen die folgenden Voraussetzungen erfüllt sein:

- Die erforderliche Teams-Lizenz muss für den Azure Active Directory-synchronisierten Benutzer zugewiesen werden.

- Benutzer müssen mit Azure Active Directory synchronisiert werden. Informationen zum Verwenden von Azure AD Connect zur Synchronisierung mit Azure Active Directory finden Sie unter [Dokumentation zur Hybrid Identität](https://docs.microsoft.com/azure/active-directory/hybrid/).

- Postfächer werden in Exchange Server 2016 Kumulatives Update 3 oder höher gehostet.

- Auto Ermittlungs-und Exchange-Webdienste werden extern veröffentlicht.

- Die OAuth-Authentifizierung wird vorzugsweise über den Exchange-Hybrid Konfigurations-Assistenten konfiguriert, der eine vollständige Hybrid Konfiguration ausführt (klassisch oder modern). Wenn Sie den Assistenten für die Hybrid Konfiguration nicht verwenden können, konfigurieren Sie OAuth wie unter [Konfigurieren der OAuth-Authentifizierung zwischen Exchange und Exchange Online-Organisationen](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)beschrieben.

  > [!NOTE]
  > Exchange Trusts OAuth-Token des Teams-Diensts, der als EvoSTS bezeichnet wird. Schritt 1 sollte ausreichen, aber nur die EvoSTS; ACS wird für den frei/gebucht-Lookup im Kalender verwendet.

- Das Kontrollkästchen für das Exchange-Feature für die Hybrid Bereitstellung in Azure AD Connect ist aktiviert.

- Für die Kalender-APP-Unterstützung und Teams Outlook Add-In für Mac müssen Exchange-Webdienst-URLs als SPNs in Mandant Azure AD für den Exchange-Dienstprinzipal konfiguriert sein. Dieser Schritt erfolgt mit dem Hybrid-Konfigurations-Assistenten oder den folgenden [manuellen Schritten zur Hybriden modernen Authentifizierung](https://docs.microsoft.com/microsoft-365/enterprise/configure-exchange-server-for-hybrid-modern-authentication#add-on-premises-web-service-urls-as-spns-in-azure-ad).

So aktivieren Sie die Kalender Delegierung für diese Benutzer:

- Sie müssen auch die Schritte 2-3 ausführen, wie unter [Konfigurieren von Integration und OAuth zwischen Skype for Business Online und Exchange Server](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)beschrieben ist. mit den folgenden Schritten wird der Team Planungsanwendung die erforderlichen Berechtigungen zum Bestätigen von Stell Vertretungs Berechtigungen bereitgestellt.
 
  > [!NOTE]
  > Schritt 2 enthält die Rollenzuweisung für ArchiveApplication, die für die Delegierung nicht erforderlich ist.

- Bei der Planung einer Besprechung im Auftrag einer anderen Person ist Exchange 2013 CU19 oder höher erforderlich. Dies dient zur Unterstützung der nicht authentifizierten Ermittlung des Postfachs durch unseren Dienst, um Stell Vertretungs Berechtigungen für das Postfach zu überprüfen. Der Stell Vertretungs-und delegator-Speicherort kann Exchange 2013 oder höher oder Exchange Online sein, die AutoErmittlung muss jedoch in Exchange 2013 CU19 oder höher aufgelöst werden.

## <a name="additional-considerations"></a>Weitere Überlegungen

Im folgenden finden Sie einige zusätzliche Dinge, die Sie berücksichtigen sollten, wenn Sie Microsoft Teams in Ihrer Organisation implementieren.

- In Microsoft Teams funktionieren Sicherheits- und Compliance-Funktionen wie eDiscovery, Inhaltssuche, Archivierung und gesetzliche Aufbewahrungspflicht am besten in Exchange Online- und SharePoint Online-Umgebungen. Für Kanalunterhalten werden Nachrichten im Gruppenpostfach in Exchange Online als Journal erfasst und stehen für eDiscovery zur Verfügung. Bei Aktivierung von SharePoint Online und OneDrive for Business (mit Geschäfts- oder Schulkonto) für Benutzer in der gesamten Organisation stehen diese Compliance-Funktionen auch für alle Dateien innerhalb von Teams zur Verfügung.

- Steuern und schützen Sie die Konfiguration von Konformitätsrichtlinien in Teams und Exchange mithilfe von bedingtem Zugriff. Weitere Informationen finden Sie unter [wie funktionieren bedingte Zugriffsrichtlinien für Teams?](security-compliance-overview.md#how-conditional-access-policies-work-for-teams)

- Wenn Ihre Organisation über Compliance-Anforderungen verfügt, um sicherzustellen, dass alle Besprechungs Diskussionen auffindbar sind, sollten Sie private Besprechungen deaktivieren, wenn der Organisator über ein lokales Exchange-Postfach verfügt. Weitere Informationen finden Sie unter [Zulassen der Planung privater Besprechungen](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#allow-scheduling-private-meetings).

- In einer Exchange-hybridbereitstellung können Inhalte aus Chatnachrichten unabhängig davon durchsucht werden, ob Chat-Teilnehmer über ein Cloud-basiertes Postfach oder ein lokales Postfach verfügen. Weitere Informationen finden Sie unter [Suchen von Cloud-basierten Postfächern für lokale Benutzer](https://docs.microsoft.com/office365/securitycompliance/search-cloud-based-mailboxes-for-on-premises-users). Wenn Sie mehr über die Suche nach Inhalten in Teams erfahren möchten, lesen Sie [die Inhaltssuche im Microsoft 365 Compliance Center](https://docs.microsoft.com/Office365/SecurityCompliance/content-search#searching-microsoft-teams-and-office-365-groups).

- Für den Anwesenheitsstatus müssen Microsoft Teams überprüfen, ob das Postfach auf Exchange Online oder lokal gehostet wird. Der Dienst entscheidet dann, wo auf das Postfach zugegriffen werden soll. Damit der Team Dienst den Post Fach Standort über den übrigen API-Aufruf an den Exchange Online-Dienst überprüfen kann, müssen Sie eine Exchange-Hybridumgebung bereitstellen, indem Sie den Exchange-Assistenten für die Hybrid Konfiguration ausführen, wie unter [Erstellen einer hybridbereitstellung mit dem Hybrid Konfigurations-Assistenten](https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid)beschrieben.

## <a name="troubleshooting"></a>Problembehandlung

Eine vollständige Anleitung zur Problembehandlung für das Thema finden Sie unter [Problembehandlung von Microsoft Teams und Exchange Server-Interaktions Problemen](https://docs.microsoft.com/microsoftteams/troubleshoot/known-issues/teams-exchange-interaction-issue).
