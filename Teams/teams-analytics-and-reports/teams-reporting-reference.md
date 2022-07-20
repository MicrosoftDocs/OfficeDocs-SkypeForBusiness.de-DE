---
title: Microsoft Teams – Analyse und Berichterstellung
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
- ms.teamsadmincenter.analyticsandreports.overview
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: In diesem Artikel erfahren Sie mehr über die Teams-Berichte, die im Microsoft Teams Admin Center verfügbar sind.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bd6be2023745390a0f1225224e6ebbe9bcbde1dc
ms.sourcegitcommit: e6f3e1e499ed1298b3e6f7a1b53f6cb8ba73c9b1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2022
ms.locfileid: "66906960"
---
# <a name="microsoft-teams-analytics-and-reporting"></a>Microsoft Teams – Analyse und Berichterstellung

Eine neue Analyse- und Berichterstellungserfahrung für Microsoft Teams ist im Microsoft Teams Admin Center verfügbar. Sie können verschiedene Berichte ausführen, um Einblicke in die Verwendung von Teams durch Benutzer in Ihrer Organisation zu erhalten. So können Sie beispielsweise sehen, wie viele Benutzer über Kanal- und Chatnachrichten kommunizieren und welche Arten von Geräten sie für die Verbindung mit Teams verwenden. Ihre Organisation kann die Informationen aus den Berichten verwenden, um Nutzungsmuster besser zu verstehen, Geschäftsentscheidungen zu treffen und Schulungs- und Kommunikationsanstrengungen zu informieren.

## <a name="how-to-access-the-reports"></a>So greifen Sie auf die Berichte zu

Um auf die Berichte zugreifen zu können, müssen Sie ein globaler Administrator in Microsoft 365 oder Office 365, globaler Leser in Microsoft 365 oder Office 365, Teams-Dienstadministrator oder Skype for Business Administrator sein. Weitere Informationen zu Teams-Administratorrollen und den Berichten, auf die jede Administratorrolle zugreifen kann, finden [Sie unter Verwenden von Teams-Administratorrollen zum Verwalten von Teams](../using-admin-roles.md).

Wechseln Sie zum Microsoft Teams Admin Center, wählen Sie in der linken **Navigationsleiste Analytics & Berichte** aus, und wählen Sie dann unter **"Berichte anzeigen**" den Bericht aus, den Sie ausführen möchten.

> [!NOTE]
> Die Berichte im Microsoft Teams Admin Center sind getrennt von den Aktivitätsberichten für Teams, die Teil der Microsoft 365-Berichte in der Microsoft 365 Admin Center sind. Weitere Informationen zu den Aktivitätsberichten im Microsoft 365 Admin Center finden Sie [unter Microsoft 365-Berichte im Admin Center](/microsoft-365/admin/activity-reports/activity-reports).

## <a name="teams-reporting-reference"></a>Referenz zur Teams-Berichterstellung

Hier finden Sie eine Liste der Teams-Berichte, die im Microsoft Teams Admin Center verfügbar sind, und eine Übersicht über einige der Informationen, die in jedem Bericht verfügbar sind.

Wir verbessern kontinuierlich die Teams-Berichterstellung und fügen Features und Funktionen hinzu. Im Laufe der Zeit werden wir zusätzliche Funktionen in die Berichte integrieren und neue Berichte im Microsoft Teams Admin Center hinzufügen.

|Bericht  |Was wird gemessen? |
|---------|---------|
|[Teams-Nutzungsbericht](teams-usage-report.md)  |  Aktive Benutzer<br/>Aktive Benutzer in Teams und Kanälen<br/>Aktive Kanäle<br/>Nachrichten<br/>Datenschutzeinstellung von Teams<br/>Gäste in einem Team   |
|[Teams-Benutzeraktivitätsbericht](user-activity-report.md)  | Nachrichten, die ein Benutzer in einem Teamchat gepostet hat<br/>Nachrichten, die ein Benutzer in einem privaten Chat gepostet hat<br/>  1:1 Anrufe, an der ein Benutzer teilgenommen hat<br/> Anzahl der vom Benutzer organisierten Besprechungen <br/>Anzahl der Besprechungen, an der der Benutzer teilgenommen hat<br/>Audio-, Video- und Bildschirmfreigabezeit für Besprechungen<br/>   Datum der letzten Aktivität eines Benutzers     |
|[Teams-Gerätenutzungsbericht](device-usage-report.md)   |  Windows-Benutzer<br/>Mac-Benutzer<br/>iOS-Benutzer<br/>Android-Telefonbenutzer     |
|[Teams-Liveereignis-Nutzungsbericht](teams-live-event-usage-report.md)   |  Gesamtansichten<br>Startzeitpunkt<br>Ereignisstatus<br>Organisator<br>Moderator<br>Produzent<br>Aufzeichnungseinstellung<br>Produktionstyp    |
|[Bericht "Teams PSTN blockierte Benutzer"](pstn-blocked-users-report.md)   |  Anzeigename<br>Telefonnummer<br>Grund<br>Aktionstyp<br>Datum und Uhrzeit der Aktion   |
|[Teams-Bericht zu PSTN-Minutenpools](pstn-minute-pools-report.md) |  Land oder Region<br>Funktion (Lizenz) <br>Gesamtminuten<br>Verwendete Minuten<br>Verfügbare Minuten|
|[PSTN-Nutzungsbericht für Teams – Anrufpläne](pstn-usage-report.md#calling-plans)|  Zeitstempel<br>Benutzername<br>Telefonnummer<br>Anruftyp <br>Angerufen an<br>Nach Land oder Region <br>Aufgerufen von <br>Aus Land oder Region<br>Berechnen<br>Währung<br>Dauer<br>Inland/International<br>Anruf-ID<br>Zahlentyp<br>Land oder Region<br>Konferenz-ID<br>Funktion (Lizenz)|
|[PSTN-Nutzungsbericht für Teams – Direct Routing](pstn-usage-report.md#direct-routing)  |  Zeitstempel<br>Anzeigename<br>SIP-Adresse<br>Telefonnummer <br>Anruftyp<br>Angerufen an<br>Startzeitpunkt<br>Einladungszeitpunkt<br>Fehlerzeit<br>Endzeitpunkt<br>Dauer<br>Zahlentyp<br>Medienumgehung<br>SBC-FQDN<br>Azure-Region<br>Ereignistyp<br>Endgültiger SIP-Code<br>Endgültige Microsoft-Untercodierung<br>Letzter SIP-Ausdruck<br>Korrelations-ID  |
|[Teams Information Protection-Lizenzbericht](information-protection-license-report.md)  | <br>Gibt an, ob Benutzer über gültige Lizenzen zum Pushen ihrer Nachrichten über Änderungsbenachrichtigungen verfügen.</br><br>Gesamtanzahl der von einem Benutzer ausgelösten Änderungsbenachrichtigungsereignisse<br><br>Welche Apps überwachen organisationsweite Änderungsbenachrichtigungsereignisse<br>|
|[Nutzungsbericht "Virtuelle Besuche in Teams"](/microsoft-365/frontline/virtual-visits-usage-report?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json)  | Anzahl virtueller Termine<br>Anzahl der Bookings-Termine<br>Anzahl der in teams electronic health records (EHR) integrierten Termine<br>Durchschnittliche Dauer eines Termins<br>Durchschnittliche Wartezeit der Teilnehmer im Wartebereich<br>Startzeitpunkt<br>Besprechungs-ID<br>Wartezeit des Wartebereichs<br>Dauer<br>Status<br>Produkttyp<br>Teilnehmer<br>GESENDETE SMS
|[Teams-EE-Connector Virtuelle Termine Bericht](/microsoft-365/frontline/ehr-connector-report?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json) | Startzeitpunkt<br>Dauer<br>Primär (Name des Besprechungsorganisators)<br>E-Mail des Primären (E-Mail des Besprechungsorganisators)<br>Abteilung<br>Telefonzentralen<br>Wartezeit des Wartebereichs<br>Gibt an, ob der Termin innerhalb der Zuteilungsgrenze liegt.|
[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="make-the-user-specific-data-anonymous"></a>Anonymisieren der benutzerspezifischen Daten

Um die Daten in Teams-Benutzeraktivitäten und Teams-Gerätenutzungsberichten anonym zu machen, müssen Sie ein globaler Administrator sein. Dadurch werden identifizierbare Informationen wie Anzeigename, E-Mail und Microsoft Azure Active Directory-ID in Berichten und deren Exporten ausgeblendet.

1. Wechseln Sie in Microsoft 365 Admin Center zu den **Organisationseinstellungen "Einstellungen**\>", und wählen Sie auf der Registerkarte "**Dienste**" die Option "**Berichte**" aus.
    
2. Wählen Sie **"Berichte**" und dann " **Verborgene Benutzer-, Gruppen- und Websitenamen in allen Berichten anzeigen"** aus. Diese Einstellung wird sowohl auf die Nutzungsberichte in Microsoft 365 Admin Center als auch auf das Teams Admin Center angewendet.
  
3. Wählen Sie **"Änderungen speichern" aus**.

> [!NOTE]
> Durch Aktivieren dieser Einstellung werden Informationen in [Teams-Benutzeraktivitätsberichten](user-activity-report.md) und [Teams-Gerätenutzungsberichten](device-usage-report.md) gelöscht. Es wirkt sich nicht auf andere Nutzungsberichte aus, die im Teams Admin Center verfügbar sind.
> Diese Einstellung gilt auch für Microsoft 365-Nutzungsberichte in Microsoft 365 Admin Center, Microsoft Graph und Power BI.
