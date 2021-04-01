---
title: Microsoft Teams – Analyse und Berichterstellung
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
- ms.teamsadmincenter.analyticsandreports.overview
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: In diesem Artikel erfahren Sie mehr über die Teams-Berichte, die im Microsoft Teams Admin Center verfügbar sind.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6d195c90dc7e959146546dde1a75fedf0764c24a
ms.sourcegitcommit: 66e7b28ba1c0433535eb6a3e7d883851c27d9d1f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2021
ms.locfileid: "51478345"
---
# <a name="microsoft-teams-analytics-and-reporting"></a>Microsoft Teams – Analyse und Berichterstellung

Eine neue Analyse- und Berichterstellungserfahrung für Microsoft Teams ist im Microsoft Teams Admin Center verfügbar. Sie können verschiedene Berichte ausführen, um Einblicke in die Verwendung von Teams durch Benutzer in Ihrer Organisation zu erhalten. So können Sie beispielsweise sehen, wie viele Benutzer über Kanal- und Chatnachrichten kommunizieren und welche Geräte sie zum Herstellen einer Verbindung mit Teams verwenden. Ihre Organisation kann die Informationen aus den Berichten verwenden, um Nutzungsmuster besser zu verstehen, geschäftliche Entscheidungen zu treffen sowie Schulungs- und Kommunikationsaufwand zu informieren.

## <a name="how-to-access-the-reports"></a>So greifen Sie auf die Berichte zu

Um auf die Berichte zugreifen zu können, müssen Sie ein globaler Administrator in Microsoft 365 oder Office 365, Microsoft Teams-Dienstadministrator oder Skype for Business-Administrator sein. Weitere Informationen zu Den Teams-Administratorrollen und den Berichten, auf die jede Administratorrolle zugreifen kann, finden Sie unter Verwenden von [Teams-Administratorrollen zum](../using-admin-roles.md)Verwalten von Teams.

Wechseln Sie zum Microsoft Teams Admin Center, wählen Sie in der linken Navigationsleiste Analytics **&-Berichte** aus, und wählen Sie dann unter Bericht den Bericht **aus,** den Sie ausführen möchten.

> [!NOTE]
> Die Berichte im Microsoft Teams Admin Center sind von den Aktivitätsberichten für Teams getrennt, die Teil der Microsoft 365-Berichte im Microsoft 365 Admin Center sind. Weitere Informationen zu den Aktivitätsberichten im Microsoft 365 Admin Center finden Sie unter Teams-Aktivitätsberichte im [Microsoft 365 Admin Center.](../teams-activity-reports.md)

## <a name="teams-reporting-reference"></a>Berichtsreferenz zu Teams

Hier finden Sie eine Liste der Im Microsoft Teams Admin Center verfügbaren Teams-Berichte und eine Übersicht über einige der Informationen, die in den einzelnen Berichten verfügbar sind.

Wir verbessern kontinuierlich die Berichterstattungserfahrung von Teams und fügen Features und Funktionen hinzu. Im Laufe der Zeit werden wir zusätzliche Funktionen in die Berichte einfügen und neue Berichte im Microsoft Teams Admin Center hinzufügen.

|Bericht  |Was wird gemessen? |
|---------|---------|
|[Teams-Nutzungsbericht](teams-usage-report.md)  |  Aktive Benutzer<br/>Aktive Benutzer in Teams und Kanälen<br/>Aktive Kanäle<br/>Nachrichten<br/>Datenschutzeinstellungen von Teams<br/>Gäste in einem Team   |
|[Teams-Benutzeraktivitätsbericht](user-activity-report.md)  | Nachrichten, die ein Benutzer in einem Teamchat gepostet hat<br/>Nachrichten, die ein Benutzer in einem privaten Chat gepostet hat<br/>  1:1 ruft einen Benutzer an, an dem teilgenommen wurde<br/> Anzahl der organisierten Besprechungsbenutzer <br/>Anzahl der Besprechungsbenutzer, die daran teilgenommen haben<br/>Zeit für die Audio-, Video- und Bildschirmfreigabe für Besprechungen<br/>   Datum der letzten Aktivität eines Benutzers     |
|[Teams-Gerätenutzungsbericht](device-usage-report.md)   |  Windows-Benutzer<br/>Mac-Benutzer<br/>iOS-Benutzer<br/>Benutzer von Android-Smartphones     |
|[Teams-Liveereignis-Nutzungsbericht](teams-live-event-usage-report.md)   |  Gesamtansichten<br>Startzeitpunkt<br>Ereignisstatus<br>Organisator<br>Presenter<br>Produzent<br>Aufzeichnungseinstellung<br>Produktionstyp    |
|[Bericht "Blockierte Benutzer in Teams PSTN"](pstn-blocked-users-report.md)   |  Anzeigename<br>Telefonnummer<br>Grund<br>Aktionstyp<br>Datum und Uhrzeit der Aktion   |
|[Bericht "Teams PSTN-Minutenpools"](pstn-minute-pools-report.md) |  Land oder Region<br>Funktion (Lizenz) <br>Gesamtminuten<br>Verwendete Minuten<br>Verfügbare Minuten|
|[Bericht zur Verwendung von Teams PSTN – Anrufpläne](pstn-usage-report.md#calling-plans)|  Zeitstempel<br>Benutzername<br>Telefonnummer<br>Anruftyp <br>Angerufen<br>In das Land oder die Region <br>Von aufgerufen <br>Aus dem Land oder der Region<br>Aufladen<br>Währung<br>Dauer<br>Inland/International<br>Anruf-ID<br>Zahlentyp<br>Land oder Region<br>Konferenz-ID<br>Funktion (Lizenz)|
|[Bericht zur Verwendung von Teams PSTN – Direktes Routing](pstn-usage-report.md#direct-routing)  |  Zeitstempel<br>Anzeigename<br>SIP-Adresse<br>Telefonnummer <br>Anruftyp<br>Angerufen<br>Startzeitpunkt<br>Einladungszeitpunkt<br>Fehlerzeit<br>Endzeitpunkt<br>Dauer<br>Zahlentyp<br>Medienumgehung<br>SBC FQDN<br>Azure-Region<br>Ereignistyp<br>Letzter SIP-Code<br>Endgültiger Microsoft-Untercode<br>Letzter SIP-Ausdruck<br>Korrelations-ID  |

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="make-the-user-specific-data-anonymous"></a>Anonymisierter Benutzerdaten

Um die Daten in Den Teams-Benutzeraktivitäten und dem Bericht zur Gerätenutzung von Teams anonym zu machen, müssen Sie ein globaler Administrator sein. Dadurch werden identifizierbare Informationen wie Anzeigename, E-Mail und AAD-ID in Berichten und ihren Exporten ausgeblendet.

1. Wechseln Sie im Microsoft 365  Admin Center zu Einstellungen für Organisationseinstellungen, und wählen Sie auf der Registerkarte Dienste \> die Option **Berichte aus.** 
    
2. Wählen **Sie Berichte** und dann anonyme **Bezeichner anzeigen aus.** Diese Einstellung wird sowohl auf die Nutzungsberichte im Microsoft 365 Admin Center als auch auf das Teams Admin Center angewendet.
  
3. Wählen **Sie Änderungen speichern aus.**

> [!NOTE]
> Wenn Sie diese Einstellung aktivieren, werden die Informationen in [den Berichten "Benutzeraktivitätsbericht"](user-activity-report.md) und ["Teams-Gerätenutzungsbericht" nicht mehr](device-usage-report.md) identifiziert. Dies wirkt sich nicht auf andere Nutzungsberichte aus, die im Teams Admin Center verfügbar sind.
