---
title: Microsoft Teams – Analyse und Berichterstellung
author: serdarsoysal
ms.author: serdars
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
description: In diesem Artikel erfahren Sie mehr über die Teams Berichte, die im Microsoft Teams Admin Center verfügbar sind.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f6a3cbf42c65d054befac8ad4e1f25d8be65f286
ms.sourcegitcommit: 68162a8c9dee9a27af596353baabeda9b8fa64f3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2022
ms.locfileid: "64853036"
---
# <a name="microsoft-teams-analytics-and-reporting"></a>Microsoft Teams – Analyse und Berichterstellung

Eine neue Analyse- und Berichterstellungserfahrung für Microsoft Teams ist im Microsoft Teams Admin Center verfügbar. Sie können verschiedene Berichte ausführen, um Einblicke zu erhalten, wie Benutzer in Ihrer Organisation Teams verwenden. Sie können z. B. sehen, wie viele Benutzer über Kanal- und Chatnachrichten kommunizieren und welche Arten von Geräten sie zum Herstellen einer Verbindung mit Teams verwenden. Ihre Organisation kann die Informationen aus den Berichten verwenden, um Nutzungsmuster besser zu verstehen, Geschäftsentscheidungen zu treffen und Schulungs- und Kommunikationsanstrengungen zu informieren.

## <a name="how-to-access-the-reports"></a>So greifen Sie auf die Berichte zu

Um auf die Berichte zugreifen zu können, müssen Sie ein globaler Administrator in Microsoft 365 oder Office 365, globaler Leser in Microsoft 365 oder Office 365, Teams Dienstadministrator oder Skype for Business Administrator sein. Weitere Informationen zu Teams Administratorrollen und zu den Berichten, auf die jede Administratorrolle zugreifen kann, finden [Sie unter Verwenden Teams Administratorrollen zum Verwalten von Teams](../using-admin-roles.md).

Wechseln Sie zum Microsoft Teams Admin Center, wählen Sie in der linken **Navigationsleiste Analytics & Berichte** aus, und wählen Sie dann unter **"Berichte anzeigen**" den Bericht aus, den Sie ausführen möchten.

> [!NOTE]
> Die Berichte im Microsoft Teams Admin Center sind getrennt von den Aktivitätsberichten für Teams, die Teil der Microsoft 365-Berichte im Microsoft 365 Admin Center sind. Weitere Informationen zu den Aktivitätsberichten im Microsoft 365 Admin Center finden Sie [unter Teams Aktivitätsberichte im Microsoft 365 Admin Center](../teams-activity-reports.md)

## <a name="teams-reporting-reference"></a>referenz zur Teams-Berichterstellung

Hier ist eine Liste der Teams Berichte, die im Microsoft Teams Admin Center verfügbar sind, und eine Übersicht über einige der Informationen, die in jedem Bericht verfügbar sind.

Wir verbessern kontinuierlich die Teams Berichterstellung und fügen Features und Funktionen hinzu. Im Laufe der Zeit werden wir zusätzliche Funktionen in die Berichte integrieren und neue Berichte im Microsoft Teams Admin Center hinzufügen.

|Bericht  |Was wird gemessen? |
|---------|---------|
|[Teams-Nutzungsbericht](teams-usage-report.md)  |  Aktive Benutzer<br/>Aktive Benutzer in Teams und Kanälen<br/>Aktive Kanäle<br/>Nachrichten<br/>Datenschutzeinstellung von Teams<br/>Gäste in einem Team   |
|[Teams-Benutzeraktivitätsbericht](user-activity-report.md)  | Nachrichten, die ein Benutzer in einem Teamchat gepostet hat<br/>Nachrichten, die ein Benutzer in einem privaten Chat gepostet hat<br/>  1:1 Anrufe, an der ein Benutzer teilgenommen hat<br/> Anzahl der vom Benutzer organisierten Besprechungen <br/>Anzahl der Besprechungen, an der der Benutzer teilgenommen hat<br/>Audio-, Video- und Bildschirmfreigabezeit für Besprechungen<br/>   Datum der letzten Aktivität eines Benutzers     |
|[Teams-Gerätenutzungsbericht](device-usage-report.md)   |  Windows-Benutzer<br/>Mac-Benutzer<br/>iOS-Benutzer<br/>Android-Telefonbenutzer     |
|[Teams-Liveereignis-Nutzungsbericht](teams-live-event-usage-report.md)   |  Gesamtansichten<br>Startzeitpunkt<br>Ereignisstatus<br>Organisator<br>Moderator<br>Produzent<br>Aufzeichnungseinstellung<br>Produktionstyp    |
|[Bericht über Teams PSTN-Blockierte Benutzer](pstn-blocked-users-report.md)   |  Anzeigename<br>Telefon Nummer<br>Grund<br>Aktionstyp<br>Datum und Uhrzeit der Aktion   |
|[Teams Bericht über PSTN-Minutenpools](pstn-minute-pools-report.md) |  Land oder Region<br>Funktion (Lizenz) <br>Gesamtminuten<br>Verwendete Minuten<br>Verfügbare Minuten|
|[Teams PSTN-Nutzungsbericht – Anrufpläne](pstn-usage-report.md#calling-plans)|  Zeitstempel<br>Benutzername<br>Telefon Nummer<br>Anruftyp <br>Angerufen an<br>Nach Land oder Region <br>Aufgerufen von <br>Aus Land oder Region<br>Berechnen<br>Währung<br>Dauer<br>Inland/International<br>Anruf-ID<br>Zahlentyp<br>Land oder Region<br>Konferenz-ID<br>Funktion (Lizenz)|
|[Teams PSTN-Nutzungsbericht – Direct Routing](pstn-usage-report.md#direct-routing)  |  Zeitstempel<br>Anzeigename<br>SIP-Adresse<br>Telefon Nummer <br>Anruftyp<br>Angerufen an<br>Startzeitpunkt<br>Einladungszeitpunkt<br>Fehlerzeit<br>Endzeitpunkt<br>Dauer<br>Zahlentyp<br>Medienumgehung<br>SBC-FQDN<br>Azure-Region<br>Ereignistyp<br>Endgültiger SIP-Code<br>Endgültige Microsoft-Untercodierung<br>Letzter SIP-Ausdruck<br>Korrelations-ID  |
|[Teams Lizenzbericht zum Informationsschutz](information-protection-license-report.md)  | <br>Gibt an, ob Benutzer über gültige Lizenzen zum Pushen ihrer Nachrichten über Änderungsbenachrichtigungen verfügen.</br><br>Gesamtanzahl der von einem Benutzer ausgelösten Änderungsbenachrichtigungsereignisse<br><br>Welche Apps überwachen organisationsweite Änderungsbenachrichtigungsereignisse<br>|
|[Nutzungsbericht für Teams virtuelle Besuche](virtual-visits-usage-report.md)  | Anzahl virtueller Termine<br>Anzahl der Bookings Termine<br>Anzahl der in Teams elektronischen Gesundheitsakten (EHR) integrierten Termine<br>Durchschnittliche Dauer eines Termins<br>Durchschnittliche Wartezeit der Teilnehmer im Wartebereich<br>Startzeitpunkt<br>Besprechungs-ID<br>Wartezeit des Wartebereichs<br>Dauer<br>Status<br>Produkttyp<br>Teilnehmer<br>GESENDETE SMS
[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="make-the-user-specific-data-anonymous"></a>Anonymisieren der benutzerspezifischen Daten

Um die Daten in Teams Benutzeraktivität und Teams Bericht über die Gerätenutzung anonym zu machen, müssen Sie ein globaler Administrator sein. Dadurch werden identifizierbare Informationen wie Anzeigename, E-Mail und Microsoft Azure Active Directory-ID in Berichten und deren Exporten ausgeblendet.

1. Wechseln Sie in Microsoft 365 Admin Center zur **Einstellungen Einstellungen** \> **Organisation**, und wählen Sie unter der Registerkarte "**Dienste**" die Option "**Berichte**" aus.
    
2. Wählen Sie **"Berichte**" und dann " **Verborgene Benutzer-, Gruppen- und Websitenamen in allen Berichten anzeigen"** aus. Diese Einstellung wird sowohl auf die Verwendungsberichte in Microsoft 365 Admin Center als auch auf Teams Admin Center angewendet.
  
3. Wählen Sie **"Änderungen speichern" aus**.

> [!NOTE]
> Durch Aktivieren dieser Einstellung werden Informationen in [Teams Benutzeraktivitätsbericht](user-activity-report.md) und [Teams Bericht über die Gerätenutzung](device-usage-report.md) nicht mehr identifiziert. Es wirkt sich nicht auf andere Nutzungsberichte aus, die im Admin Center Teams verfügbar sind.
> Diese Einstellung gilt auch für Microsoft 365 Verwendungsberichte in Microsoft 365 Admin Center, Microsoft Graph und Power BI.
