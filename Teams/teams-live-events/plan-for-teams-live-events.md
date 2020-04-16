---
title: Planen von Liveereignissen in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 08/19/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: sonua
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
search.appverid: MET150
description: Informieren Sie sich über die Faktoren, die Sie berücksichtigen sollten, bevor Sie Liveereignisse in Microsoft Teams einrichten.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2f70a7a2be51045f616ebb4cedc5baf46dbe101d
ms.sourcegitcommit: 56ceda54ca48d2984298d4d1f26017c0147d4431
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2020
ms.locfileid: "43505622"
---
# <a name="plan-for-live-events-in-microsoft-teams"></a>Planen von Liveereignissen in Microsoft Teams

Wenn Sie Liveereignisse in Teams planen, um große Besprechungen in Ihrer Organisation abzuhalten, müssen Sie eine Reihe von Faktoren berücksichtigen, bevor Sie mit der Einrichtung beginnen. 

## <a name="who-can-create-and-schedule-live-events"></a>Wer kann Liveereignisse erstellen und planen? 
Die folgenden Voraussetzungen müssen erfüllt sein, damit ein Benutzer ein Teams-Liveereignis planen kann.

Folgende Lizenzen müssen zugewiesen werden:  
- Eine Lizenz für Office 365 Enterprise E1, E3 oder E5 oder eine Lizenz für Office 365 A3 oder A5
- Eine Lizenz für Microsoft Teams
- Eine Lizenz für Microsoft Stream

> [!IMPORTANT]
> Der Benutzer, der ein Liveereignis erstellt und plant, muss über ein Exchange Online-Postfach verfügen.

Es ist wichtig zu wissen, dass eine Office 365-Lizenz erforderlich ist, um an einem Liveereignis als authentifizierter Benutzer teilzunehmen, aber diese Anforderung hängt von der verwendeten Produktionsmethode ab:

- **Für Ereignisse, die in Teams erstellt werden**, muss dem Benutzer eine Teams-Lizenz zugewiesen werden.
- **Für Ereignisse, die mit einer externen App oder einem externen Gerät erstellt wurden**, muss dem Benutzer eine Stream-Lizenz zugewiesen werden.

> [!NOTE]
> Für US Government Cloud Community (GCC)-Organisationen sind jetzt Teams-Liveereignisse verfügbar.

Weitere Informationen zur Lizenzierung finden Sie unter [Microsoft Teams-Add-On-Lizensierung](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

Der Benutzer muss Folgendes besitzen:
- Die Planung privater Besprechungen in Teams muss aktiviert sein (*TeamsMeetingPolicy -AllowPrivateMeetingScheduling-Parameter = True"*).
- Die Videofreigabe in Teams-Besprechungen muss aktiviert sein (*TeamsMeetingPolicy -AllowIPVideo-Parameter = True*).
- Die Bildschirmfreigabe in Teams-Besprechungen muss aktiviert sein (*TeamsMeetingPolicy -ScreenSharingMode-Parameter = EntireScreen*).
- Die Planung von Liveereignissen in Teams muss aktiviert sein (*TeamsMeetingBroadcastPolicy -AllowBroadcastScheduling-Parameter = True*).
- Berechtigungen zum Erstellen von Liveereignissen in Stream (für die Produktion externer Anwendungen oder Geräte).
- Der Koexistenzmodus ist so konfiguriert, dass Teambesprechungen (*Inselmodus, "Besprechung zuerst" oder "Nur Teams"*) geplant werden können.

> [!IMPORTANT]
> Nicht authentifizierte anonyme Benutzer können nicht als Produzenten oder Referenten zu Teams-Liveereignissen eingeladen werden. 
 
## <a name="who-can-watch-live-events"></a>Wer kann Liveereignisse anschauen?

|**Sichtbarkeit für Teilnehmer**       |**Teams-Produktion **  |**Produktion externer Anwendungen oder Geräte**  |
|------------------------------|-----------------|----------------------|
|Öffentlich (anonyme Benutzer)      |  Ja            |  Nein                  |
|Gastbenutzer                   |  Ja            |  Nein                  |
|Alle im Unternehmensverbund |  Ja<sup>1</sup>|  Nein                  |
|Jeder im Unternehmen           |  Ja            |  Ja                 |
|Bestimmte Gruppen/Personen      |  Ja            |  Ja                 |

<sup>1</sup> Verbundteilnehmer können nur über "Personen und Gruppen" eingeladen werden. <br>
 
## <a name="teams-live-events-and-skype-meeting-broadcast"></a>Teams-Liveereignisse und Skype Meeting Broadcast

Die folgende Tabelle enthält eine Gegenüberstellung der verfügbaren Kernfunktionen und Features bei Liveereignissen und Skype Meeting Broadcast. 

|**Funktion**   |**Skype Meeting Broadcast** |**In Teams produzierte Ereignisse** |**In einer externen App oder auf einem externen Gerät produzierte Ereignisse** |
|---------|---------|---------|---------|
|Maximale Zielgruppengröße |10.000 Teilnehmer |10.000 Teilnehmer<sup>1</sup> |10.000 Teilnehmer<sup>1</sup> |
|Maximale Dauer eines Liveereignisses |4 Stunden |4 Stunden |4 Stunden |
|Maximale Anzahl von Referenten und Produzenten in einem Liveereignis |10 <sup>2</sup> |10 <sup>2</sup> |10 <sup>2</sup> |
|Maximale Anzahl gleichzeitiger Liveereignisse pro Office 365-Mandant |15  | 15  | 15  |
|Erstellung von Liveereignissen |   Skype Meeting Broadcast-Portal |Teams, Yammer via Teams | Teams, Yammer via Teams, Stream |
|Zielgruppen-Engagement – Yammer |&#x2714; |&#x2714; (integrierte Lösung) |&#x2714; (integrierte Lösung) |
|Zielgruppen-Engagement – Moderierte F & A |&#x2714;  |&#x2714; |&#x2714; |
|Produzentenclient unter Windows |&#x2714; (Skype for Business) |&#x2714; (Teams) |&#x2714; (Stream, Teams via Stream Embed) |
|Produzentenclient auf Mac |&#x274C;  | &#x2714; (Teams) |&#x2714; (Stream, Teams via Stream Embed) |
|Teilnehmeranzahl in Produzenten-UI |&#x274C;  |&#x2714; (Teams) |&#x2714; (Stream, Teams via Stream Embed) |
|Mehrere Referenten zulässig |&#x2714; (Skype for Business) |&#x2714; (Teams) |–  |
|Referenten während der Sitzung einladen |&#x2714; (Skype for Business) |&#x274C; |Nicht zutreffend |
|Referenten über Web und Mobilgerät teilnehmen |&#x2714; (Skype for Business)  |&#x274C; |Nicht zutreffend |
|Verbund- & Gastreferenten/teilnehmer |&#x2714; (Skype for Business)  |  &#x2714; (Teams) |Nicht zutreffend |
|Referent – Telefonfestnetz (PSTN)-Zugang |&#x274C; |&#x2714; (Teams) |– |
|Bildschirm präsentieren |&#x274C; |&#x2714; (Teams) |– |
|PowerPoint präsentieren (PPT-Freigabe) |&#x2714; |&#x274C; (möglich über Bildschirmfreigabe) |Nicht zutreffend |
|Aufzeichnung einer cloudbasierten Besprechung |&#x2714; |&#x2714; |&#x2714; |
|Automatische Veröffentlichung der Aufzeichnung in Stream |&#x274C; |&#x274C; |&#x2714; |
|Livebeschriftungen und Untertitel |&#x2714; |&#x2714; |&#x274C; |
|Beschriftungen in Aufzeichnungen von Liveereignissen |&#x2714; |&#x2714; |&#x2714; |
|Teilnehmer-DVR-Steuerung (Pause, Rücklauf) |&#x2714; |&#x2714; |&#x2714; |
|Partner eCDN-Unterstützung |&#x2714; (Hive, Kollective, Ramp) |&#x2714; (Hive, Kollective, Ramp) |&#x2714; (Hive, Kollective, Ramp) |
|Nachträglich gesendeter Anwesenheitsbericht für Produzenten |&#x2714; |&#x2714; |&#x274C; |
|Teilnehmerstimmungsanalyse – Liveabstimmungen & -umfragen |&#x2714; (Microsoft Pulse) |&#x274C; |&#x274C; |

<sup>1</sup> Die festgelegten Grenzen können geändert werden. Überprüfen Sie [Grenzwerte und Daten für Teams](../limits-specifications-teams.md).<br/>
<sup>2</sup> Sie können bis zu 250 Referenten und Produzenten in einem Liveereignis haben, aber nur die letzten 10, die gesprochen haben, werden in der Liste angezeigt.


## <a name="regional-availability"></a>Regionale Verfügbarkeit
Sie können Teams-Liveereignisse in mehreren Regionen der Welt nutzen. Die folgenden Informationen zeigen die Verfügbarkeit für die Ereignisteammitglieder und -teilnehmer. 

> [!IMPORTANT]
> Die Region für das Ereignis wird automatisch in Abhängigkeit vom Organisator und der Office 365-Organisation ausgewählt.

**Verfügbar in diesen Regionen**
- Nord- und Südamerika
- Europa/Afrika
- Asiatisch-pazifischer Raum
- "Go Local" Kanada, Indien, Australien, Japan, UK

**Ausschlüsse und Überlegungen**.
- **Go Locals:** Teams Go Locals, außerhalb der oben aufgeführten, werden derzeit nicht unterstützt.
- **China:** Mitglieder und Teilnehmer des Ereignisteams können die Liveereignisse des Teams nicht nutzen, da das Azure CDN in China nicht zugänglich ist. Eine Problemumgehung ist die Verwendung einer Firmen-VPN-Verbindung, die den Client über das Firmennetzwerk des Kunden mit dem CDN verbindet.

## <a name="next-steps"></a>Nächste Schritte
Navigieren Sie zu [Einrichten von Teams-Liveereignissen](set-up-for-teams-live-events.md).

### <a name="related-topics"></a>Verwandte Themen
- [Was sind Teams-Liveereignisse?](what-are-teams-live-events.md)
- [Einrichten von Teams-Liveereignissen](set-up-for-teams-live-events.md)
- [Konfigurieren der Einstellungen für Liveereignisse in Teams](configure-teams-live-events.md)
