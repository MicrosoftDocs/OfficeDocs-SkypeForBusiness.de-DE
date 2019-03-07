---
title: Plan für Live-Ereignisse in Microsoft Teams
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: tonysmit
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
description: Informationen Sie zu den Faktoren berücksichtigen vor dem Einrichten von live Ereignisse in der Microsoft-Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: d6847a4db0a2517e90535aa5ab013b030fb36f38
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/07/2019
ms.locfileid: "30463196"
---
# <a name="plan-for-live-events-in-microsoft-teams"></a>Plan für Live-Ereignisse in Microsoft Teams
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

Wenn Sie Teams live Ereignisse zum Speichern von großer Besprechungen in Ihrer Organisation planen, sind verschiedene Faktoren, die Sie berücksichtigen, bevor sie alle bis festgelegt wird gestartet müssen. 

## <a name="who-can-create-and-schedule-live-events"></a>Wer kann erstellen und planen live Ereignisse? 
Die folgenden erforderlichen Komponenten sind erforderlich für den Benutzer ein Teams live-Ereignis planen.

Hier werden die Lizenzen, die zugewiesen werden müssen:  
- Eine Lizenz für Office 365 Enterprise E3 oder E5 oder eine Lizenz für Office 365 A3 oder A5. 
- Skype für Unternehmen, und eine Microsoft-Teams und Microsoft Stream-Lizenz.

Es ist wichtig, zu wissen, dass eine Office 365-Lizenz erforderlich ist, um ein live-Ereignis als authentifizierter Benutzer teilnehmen, aber dies hängt von der Produktionsmethode verwendet:

- **Für Quick Start Produktion**  Der Benutzer muss eine Microsoft-Teams Lizenz zugewiesen werden.
- **Für externe Encoder Produktion** Der Benutzer muss eine Microsoft-Stream-Lizenz zugewiesen werden.

Weitere Informationen zur Lizenzierung finden Sie unter [Microsoft-Teams, Add-On-Lizenzierung](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

Der Benutzer benötigt:
- Planen von privaten Besprechung in Teams aktiviert (*der TeamsMeetingPolicy AllowPrivateMeetingScheduling - Parameter = True*).
- Live Ereignis Planung in Teams aktiviert (*der TeamsMeetingBroadcastPolicy AllowBroadcastScheduling - Parameter = True*).
- Berechtigungen zum Erstellen von live Ereignisse in Microsoft Stream (für [externe Encoder Produktion](#production)).

> [!IMPORTANT]
> Office 365 Gäste, Verbund- und anonyme Benutzer können nicht als Hersteller oder Referenten in Teams live Ereignisse eingeladen werden. Office 365 Gast und Verbundbenutzer können nur live Ereignisse anonym sehen Sie sich. 
 
## <a name="who-can-watch-live-events"></a>Wer live Ereignisse überwachen können?

|**ATTENDEE Sichtbarkeit**       |**Schnellstart**  |**Externe encoder**  |
|------------------------------|-----------------|----------------------|
|Öffentliche (anonyme Benutzer)      |  Ja            |  Nein                  |
|Gast-Benutzer                   |  Keine<sup>1</sup> |  Nein                  |
|Jede Person in einer verbundenen Unternehmen |  Keine<sup>1</sup> |  Nein                  |
|Jeder in Unternehmen           |  Ja             |  Ja                 |
|Spezifische Gruppen / für die Personensuche      |  Ja             |  Ja                 |

<sup>1</sup> können nur live Ereignisse als anonyme Benutzer beobachten.

 
## <a name="teams-live-events-and-skype-meeting-broadcast"></a>Teams live Ereignisse und Skype Besprechung übertragen
In der folgenden Tabelle werden wichtige Funktionen und Features in live Ereignisse und wie unterscheiden sich von Skype Besprechung übertragen angebotenen behandelt. 

|**Funktion**   |**Skype-Livekonferenzen** |**Teams live Ereignisse (Schnellstart)** |**Teams live Ereignisse (externe Encoder)** |
|---------|---------|---------|---------|
|Maximale Benutzergruppe Größe |10.000 Teilnehmer |10.000 Teilnehmer * |10.000 Teilnehmer * |
|Maximale Dauer des live-Ereignis |4 Stunden |4 Stunden |4 Stunden |
|Erstellung des Live-Ereignis |   Skype-Meeting Broadcast-Portal |Teams, Yammer über Teams | Teams, über den Teams, Stream Yammer |
|Benutzergruppe Engagements – Yammer |& #x 2714; |& #x 2714; (integrierte Experience) |& #x 2714; (integrierte Experience) |
|Benutzergruppe Engagements – Q moderiert & A |& #x 2714;  |& #x 2714; |& #x 2714; |
|Hersteller-Client für Windows |& #x 2714; (Skype für Unternehmen) |& #x 2714; (Teams) |& #x 2714; (Stream-Objekt einbetten Teams über Stream) |
|Hersteller-Client auf einem Mac |X  | & #x 2714; (Teams) |& #x 2714; (Stream-Objekt einbetten Teams über Stream) |
|Teilnehmeranzahl in Producer-Benutzeroberfläche |X  |& #x 2714; (Teams) |& #x 2714; (Stream-Objekt einbetten Teams über Stream) |
|Ermöglicht es mehrere Referenten |& #x 2714; (Skype für Unternehmen) |& #x 2714; (Teams) |n/v  |
Ein Referent während der Besprechung einladen |& #x 2714; (Skype für Unternehmen) |X |n/v |
|Referent beitreten auf Webservern und Mobile |& #x 2714; (Skype für Unternehmen)  |X |n/v |
|Referenten – PSTN-Zugang |X |& #x 2714; (Teams) |n/v |
|Ein Bildschirm angezeigt |X |& #x 2714; (Teams) |n/v |
|Präsentieren Sie eine PowerPoint (PPT-Freigabe) |& #x 2714; |X (per Bildschirmfreigabe gemindert) |n/v |
|Cloud-basierten besprechungsaufzeichnung |& #x 2714; |& #x 2714; |& #x 2714; |
|Automatische veröffentlichen Aufzeichnung in Microsoft Stream-Objekt |X |X |& #x 2714; |
|Echtzeit Beschriftungen und Übersetzung |& #x 2714; |& #x 2714; (bald verfügbar) |X |
|Beschriftungen in Aufzeichnungen live-Ereignis |& #x 2714; |& #x 2714; (bald verfügbar) |& #x 2714; |
|ATTENDEE DVR-Steuerelemente (anhalten, Zurückspulen) |& #x 2714; |& #x 2714; |& #x 2714; |
|Partner eCDN Support |& #x 2714; (Struktur, Kollective, lernen) |& #x 2714; (Struktur, Kollective, lernen) |& #x 2714; (Struktur, Kollective, lernen) |
|Nach dem broadcast Anwesenheitsbericht für Hersteller |& #x 2714; |& #x 2714; |X |
|Benutzergruppe Stimmung Analysis – Live voting & Umfragen |& #x 2714; (Microsoft Pulse) |X |X |

> [!IMPORTANT]
> Die Grenzwerte, die festgelegt werden können geändert werden.

## <a name="regional-availability"></a>Regionale Verfügbarkeit
Sie können Teams live Ereignisse auf der ganzen Welt mehrere Regionen verwenden. Die folgende Informationen zeigt Verfügbarkeit für Teammitglieder Ereignis und Teilnehmer. 

> [!IMPORTANT]
> Die Region für das Ereignis wird je nach der Organisator und der Office 365-Organisation automatisch ausgewählt.

**In diesen Regionen verfügbar**
- Amerikanischen Kontinent
- Europa/Afrika
- Asien-Pazifik
- Wechseln Sie lokale Kanada

**Ausschlüsse und Überlegungen**
- **Lokal wechseln:** Vereinigtes Königreich, Indien und andere Microsoft-Teams wechseln Sie lokal werden derzeit nicht unterstützt.
- **China:** Ereignis Teammitglieder und Teilnehmer ist nicht möglich Teams live Ereignisse verwendet werden, da Azure CDN nicht in China zugegriffen werden kann. Eine problemumgehung besteht darin, ein Unternehmen VPN-Verbindung verwenden, die über das Unternehmensnetzwerk des Kunden zu CDN verbundenen Client fungiert.

## <a name="next-steps"></a>Nächste Schritte
Wechseln Sie zur [für Teams live Ereignisse einrichten](set-up-for-teams-live-events.md).

### <a name="related-topics"></a>Verwandte Themen
- [Was sind Teams live Ereignisse?](what-are-teams-live-events.md)
- [Einrichten von für Teams live Ereignisse](set-up-for-teams-live-events.md)
- [Konfigurieren von live Ereignisse Einstellungen in Teams](configure-teams-live-events.md)

