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
description: In diesem Artikel erfahren Sie mehr über die Teams, die im Microsoft Teams Admin Center verfügbar sind.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8e52cfeb36ddc734a5cef420261308e9b8867d56
ms.sourcegitcommit: 5ca04ee10e3f254e1b24506de116591fdfd51d18
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2022
ms.locfileid: "62929140"
---
# <a name="microsoft-teams-analytics-and-reporting"></a>Microsoft Teams – Analyse und Berichterstellung

Eine neue Analyse- und Berichterstellungserfahrung für Microsoft Teams finden Sie im Microsoft Teams Admin Center. Sie können verschiedene Berichte ausführen, um Einblicke zu erhalten, wie Benutzer in Ihrer Organisation ihre Teams. So können Sie beispielsweise sehen, wie viele Benutzer über Kanal- und Chatnachrichten kommunizieren, sowie die Arten von Geräten, mit Teams. Ihre Organisation kann die Informationen aus den Berichten verwenden, um Nutzungsmuster besser zu verstehen, bei der Entscheidungsfindung für Unternehmen zu helfen sowie Schulungs- und Kommunikationsaufwand zu informieren.

## <a name="how-to-access-the-reports"></a>Zugreifen auf die Berichte

Um auf die Berichte zugreifen zu können, müssen Sie ein globaler Administrator in Microsoft 365 oder Office 365, ein globaler Leser in Microsoft 365 oder Office 365, Teams-Dienstadministrator oder Skype for Business-Administrator sein. Weitere Informationen zu Teams Administratorrollen und zu den Berichten, auf die jede Administratorrolle zugreifen kann, finden Sie unter Verwenden [Teams Administratorrollen](../using-admin-roles.md) zum Verwalten Teams.

Wechseln Sie zum Microsoft Teams Admin Center, wählen Sie in der linken Navigationsleiste Analyse **&-Berichte** aus, und wählen Sie dann unter Berichte anzeigen den Bericht **aus, den** Sie ausführen möchten.

> [!NOTE]
> Die Berichte im Microsoft Teams Admin Center sind von den Aktivitätsberichten für Teams getrennt, die Zu den Microsoft 365-Berichten im Microsoft 365 Admin Center. Weitere Informationen zu den Aktivitätsberichten in der Microsoft 365 Admin Center Finden Teams [Aktivitätsberichte im Microsoft 365 Admin Center](../teams-activity-reports.md)

## <a name="teams-reporting-reference"></a>Teams berichterstellungsreferenz

Hier finden Sie eine Liste der Teams im Microsoft Teams Admin Center und eine Übersicht über einige der Informationen, die in den einzelnen Berichten zur Verfügung stehen.

Wir verbessern ständig die Berichterstattungserfahrung Teams und fügen Features und Funktionen hinzu. Im Laufe der Zeit werden wir zusätzliche Funktionen in die Berichte einfügen und neue Berichte im Microsoft Teams Admin Center hinzufügen.

|Bericht  |Was wird gemessen? |
|---------|---------|
|[Teams-Nutzungsbericht](teams-usage-report.md)  |  Aktive Benutzer<br/>Aktive Benutzer in Teams und Kanälen<br/>Aktive Kanäle<br/>Nachrichten<br/>Datenschutzeinstellungen von Teams<br/>Gäste in einem Team   |
|[Teams-Benutzeraktivitätsbericht](user-activity-report.md)  | Nachrichten, die ein Benutzer in einem Teamchat gepostet hat<br/>Nachrichten, die ein Benutzer in einem privaten Chat gepostet hat<br/>  1:1 ruft einen Benutzer an, an dem teilgenommen wurde.<br/> Anzahl der vom Benutzer organisierten Besprechungen <br/>Anzahl der Besprechungen, an der der Benutzer teilgenommen hat<br/>Besprechungen, Audio, Video und Bildschirmfreigabe<br/>   Datum der letzten Aktivität eines Benutzers     |
|[Teams-Gerätenutzungsbericht](device-usage-report.md)   |  Windows-Benutzer<br/>Mac-Benutzer<br/>iOS-Benutzer<br/>Android-Smartphonebenutzer     |
|[Teams-Liveereignis-Nutzungsbericht](teams-live-event-usage-report.md)   |  Gesamtansichten<br>Startzeitpunkt<br>Ereignisstatus<br>Organisator<br>Moderator<br>Produzent<br>Aufzeichnungseinstellung<br>Produktionstyp    |
|[Teams Bericht über blockierte Benutzer im PSTN](pstn-blocked-users-report.md)   |  Anzeigename<br>Telefon-Nummer<br>Grund<br>Aktionstyp<br>Datum und Uhrzeit der Aktion   |
|[Teams PSTN-Minutenpools](pstn-minute-pools-report.md) |  Land oder Region<br>Funktion (Lizenz) <br>Gesamtminuten<br>Verwendete Minuten<br>Verfügbare Minuten|
|[Teams PSTN-Nutzungsbericht – Anrufpläne](pstn-usage-report.md#calling-plans)|  Zeitstempel<br>Benutzername<br>Telefon-Nummer<br>Anruftyp <br>Called to<br>In das Land oder die Region <br>Von aufgerufen <br>Aus dem Land oder der Region<br>Aufladen<br>Währung<br>Dauer<br>In- und Ausland<br>Anruf-ID<br>Zahlentyp<br>Land oder Region<br>Konferenz-ID<br>Funktion (Lizenz)|
|[Teams PSTN-Nutzungsbericht – Direct Routing](pstn-usage-report.md#direct-routing)  |  Zeitstempel<br>Anzeigename<br>SIP-Adresse<br>Telefon-Nummer <br>Anruftyp<br>Called to<br>Startzeitpunkt<br>Einladungszeitpunkt<br>Fehlerzeit<br>Endzeitpunkt<br>Dauer<br>Zahlentyp<br>Medienumgehung<br>SBC-FQDN<br>Azure-Region<br>Ereignistyp<br>Endgültiger SIP-Code<br>Endgültiger Microsoft-Untercode<br>Endgültiger SIP-Ausdruck<br>Korrelations-ID  |
|[Teams information protection license report](information-protection-license-report.md)  | <br>Ob Benutzer über gültige Lizenzen zum Senden von Nachrichten über Änderungsbenachrichtigungen verfügen</br><br>Gesamtzahl der von einem Benutzer ausgelösten Änderungsbenachrichtigungsereignisse<br><br>Welche Apps lauschen auf organisationsweite Änderungsbenachrichtigungsereignisse<br>|
|[Teams Bericht "Virtuelle Besuche"](virtual-visits-usage-report.md)  | Anzahl virtueller Besuche<br>Anzahl der Bookings-Besuche<br>Anzahl der Teams EHR (Electronic Health Records) integrierten Besuche<br>Durchschnittliche Dauer eines Besuchs<br>Durchschnittliche Wartezeit der Teilnehmer im Wartebereich<br>Startzeitpunkt<br>Besprechungs-ID<br>Wartezeit im Wartebereich<br>Dauer<br>Status<br>Produkttyp<br>Teilnehmer<br>SMS gesendet
[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="make-the-user-specific-data-anonymous"></a>Anonymisiert benutzerspezifische Daten

Um die Daten in den Teams benutzeraktivitäten und Teams zu anonym machen, müssen Sie ein globaler Administrator sein. Dadurch werden identifizierbare Informationen wie Anzeigename, E-Mail-Adresse und AAD-ID in Berichten und deren Exporten ausgeblendet.

1. Wechseln Microsoft 365 Admin Center Website zum  \> Einstellungen **Organigramm Einstellungen**, und wählen Sie unter Registerkarte Dienste die Option Berichte **aus**.
    
2. Wählen **Sie Berichte** und dann **anonyme Bezeichner anzeigen aus**. Diese Einstellung wird sowohl auf die Verwendungsberichte in Microsoft 365 Admin Center als Teams Admin Center angewendet.
  
3. Wählen Sie **Änderungen speichern aus**.

> [!NOTE]
> Durch Aktivieren dieser Einstellung werden die Informationen in Teams [Benutzeraktivitätsberichten](user-activity-report.md) und Teams [Geräteverwendungsberichten nicht identifiziert](device-usage-report.md). Dies wirkt sich nicht auf andere Nutzungsberichte aus, die im Teams Admin Center verfügbar sind.
