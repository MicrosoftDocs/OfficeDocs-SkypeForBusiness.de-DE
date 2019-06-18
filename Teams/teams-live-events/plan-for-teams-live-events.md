---
title: Plan für Live-Ereignisse in Microsoft Teams
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
description: Informieren Sie sich über die Faktoren, die Sie berücksichtigen müssen, bevor Sie Live Ereignisse in Microsoft Teams einrichten.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 14827e6ded282c113e56dd3fa567b4c7835bbf23
ms.sourcegitcommit: 9d9376c6e5e6d79e33ba54fb8ce87509a2f57754
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2019
ms.locfileid: "35013029"
---
# <a name="plan-for-live-events-in-microsoft-teams"></a>Plan für Live-Ereignisse in Microsoft Teams

Wenn Sie Team-Live-Events planen, um umfangreiche Besprechungen in Ihrer Organisation zu führen, müssen Sie einige Faktoren berücksichtigen, bevor Sie mit der Einrichtung beginnen. 

## <a name="who-can-create-and-schedule-live-events"></a>Wer kann Live-Events erstellen und planen? 
Die folgenden Voraussetzungen sind erforderlich, damit der Benutzer ein Live-Event für Teams planen können.

Hier sind die Lizenzen, die zugewiesen werden müssen:  
- Eine Office 365 Enterprise E1-, E3-oder E5-Lizenz oder eine Office 365 a3-oder A5-Lizenz
- Eine Microsoft Teams-Lizenz
- Eine Microsoft Stream-Lizenz

> [!IMPORTANT]
> Der Benutzer, der ein Live Ereignis erstellt und plant, muss über ein Exchange Online-Postfach verfügen.

Es ist wichtig zu wissen, dass eine Office 365-Lizenz erforderlich ist, um als authentifizierter Benutzer an einem Live Ereignis teilzunehmen, aber diese Anforderung hängt von der verwendeten Produktionsmethode ab:

- **Für Ereignisse, die in Teams erstellt wurden**  Dem Benutzer muss eine Teams-Lizenz zugewiesen sein.
- **Für Ereignisse, die mit einer externen APP oder einem Gerät erstellt wurden** Dem Benutzer muss eine Datenstrom Lizenz zugewiesen sein.

Weitere Informationen zur Lizenzierung finden Sie unter [Microsoft Teams-Add-on-Lizenzierung](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

Der Benutzer muss über Folgendes verfügen:
- Planung privater Besprechungen in Teams aktiviert (*der TeamsMeetingPolicy-AllowPrivateMeetingScheduling-Parameter = wahr*).
- Video Freigabe in Teambesprechungen aktiviert (*der TeamsMeetingPolicy-AllowIPVideo-Parameter = wahr*).
- Die Bildschirmfreigabe ist in Teams-Besprechungen aktiviert (*der TeamsMeetingPolicy-ScreenSharingMode-Parameter = EntireScreen*).
- Live-Ereignisplanung in Teams aktiviert (*der TeamsMeetingBroadcastPolicy-AllowBroadcastScheduling-Parameter = wahr*).
- Berechtigungen zum Erstellen von Live Ereignissen in Stream (für externe APP-oder Geräteproduktion).

> [!IMPORTANT]
> Office 365-Gäste, Partner und anonyme Benutzer können nicht als Produzenten oder Referenten in Teams Live-Events eingeladen werden. Office 365 Guest-und Federated-Benutzer können Live-Ereignisse nur anonym überwachen. 
 
## <a name="who-can-watch-live-events"></a>Wer kann Live-Events sehen?

|**Sichtbarkeit von Teilnehmern**       |**Team Produktion**  |**Externe APP-oder Geräteproduktion**  |
|------------------------------|-----------------|----------------------|
|Öffentlich (anonyme Benutzer)      |  Ja            |  Nein                  |
|Gastbenutzer                   |  Nr.<sup>1</sup> |  Nein                  |
|Jeder im Verbundunternehmen |  Nr.<sup>1</sup> |  Nein                  |
|Jeder in Unternehmen           |  Ja             |  Ja                 |
|Bestimmte Gruppen/Personen      |  Ja             |  Ja                 |

<sup>1</sup> kann Live-Ereignisse nur als anonyme Benutzer ansehen.

 
## <a name="teams-live-events-and-skype-meeting-broadcast"></a>Teams Live-Events und Skype-Live Konferenz
In der folgenden Tabelle werden die wichtigsten Funktionen und Funktionen von Live Ereignissen sowie deren Unterschiede zwischen Skype-Live Konferenzen hervorgehoben. 

|**Funktion**   |**Skype-Livekonferenzen** |**In Teams erstellte Ereignisse** |**Ereignisse, die in einer externen APP oder einem Gerät erstellt wurden** |
|---------|---------|---------|---------|
|Maximale Zielgruppengröße |10.000-Teilnehmer |10.000 Teilnehmer * |10.000 Teilnehmer * |
|Maximale Dauer des Liveereignisses |4 Stunden |4 Stunden |4 Stunden |
|Maximale Anzahl von gleichzeitigen Live Ereignissen pro Office 365-Mandanten |15  | 15  | 15  |
|Erstellen von Live Ereignissen |   Skype-Live Konferenz-Portal |Teams, jammern über Teams | Teams, über Teams jammern, streamen |
|Publikums Engagement – jammern |&#x2714; |&#x2714; (integrierte Benutzeroberfläche) |&#x2714; (integrierte Benutzeroberfläche) |
|Audience Engagement – moderiert Q #a0 A |&#x2714;  |&#x2714; |&#x2714; |
|Producer-Client unter Windows |&#x2714; (Skype for Business) |&#x2714; (Teams) |&#x2714; (streamen, Teams per Datenstrom einbetten) |
|Producer-Client auf einem Mac |X  | &#x2714; (Teams) |&#x2714; (streamen, Teams per Datenstrom einbetten) |
|Anzahl der Teilnehmer in der Producer-Benutzeroberfläche |X  |&#x2714; (Teams) |&#x2714; (streamen, Teams per Datenstrom einbetten) |
|Ermöglicht mehrere Referenten |&#x2714; (Skype for Business) |&#x2714; (Teams) |Nicht zutreffend  |
|Einladen eines Referenten während der Besprechung |&#x2714; (Skype for Business) |X |Nicht zutreffend |
|Referenten-Join im Web und Handy |&#x2714; (Skype for Business)  |X |Nicht zutreffend |
|Verbundene #a0 Gastreferenten/Teilnehmer |&#x2714; (Skype for Business)  | (in Kürze verfügbar) |Nicht zutreffend |
|Referent – PSTN-Zugriff |X |&#x2714; (Teams) |Nicht zutreffend |
|Präsentieren eines Bildschirms |X |&#x2714; (Teams) |Nicht zutreffend |
|Präsentieren einer PowerPoint-Freigabe (PPT-Freigabe) |&#x2714; |X (durch Bildschirmübertragung verringert) |Nicht zutreffend |
|Cloud-basierte Besprechungsaufzeichnung |&#x2714; |&#x2714; |&#x2714; |
|Aufzeichnen in Datenstrom automatisch veröffentlichen |X |X |&#x2714; |
|Untertitel und Übersetzungen in Echtzeit |&#x2714; |&#x2714; (in Kürze verfügbar) |X |
|Beschriftungen in Live-Ereignisaufzeichnungen |&#x2714; |&#x2714; (in Kürze verfügbar) |&#x2714; |
|Steuerelemente für Teilnehmer-DVR (anhalten, Zurückspulen) |&#x2714; |&#x2714; |&#x2714; |
|Support für Partner-ECDN |&#x2714; (Hive, Kollective, Laderampe) |&#x2714; (Hive, Kollective, Laderampe) |&#x2714; (Hive, Kollective, Laderampe) |
|Teilnahmebericht nach der Übertragung für Hersteller |&#x2714; |&#x2714; |X |
|Analyse der Zielgruppe – Live Voting #a0 Umfragen |&#x2714; (Microsoft Pulse) |X |X |

> [!IMPORTANT]
> Die festgelegten Grenzwerte können geändert werden.

## <a name="regional-availability"></a>Regionale Verfügbarkeit
Sie können Teams Live-Events in mehreren Regionen in der ganzen Welt nutzen. Die folgenden Informationen zeigen die Verfügbarkeit für Ereignis Teammitglieder und Teilnehmer. 

> [!IMPORTANT]
> Je nach Organisator und Office 365-Organisation wird der Bereich für das Ereignis automatisch ausgewählt.

**Verfügbar in diesen Regionen**
- Nord
- Europa/Afrika
- Asien/Pazifik
- Go local Canada

**Ausschlüsse und Überlegungen**
- **Ortsansässige:** Großbritannien, Indien, Australien, Japan und andere Teams gehen ortsansässige werden derzeit nicht unterstützt.
- **China:** Ereignis Teammitglieder und Teilnehmer können keine Teams-Live Ereignisse verwenden, da in China nicht auf Azure CDN zugegriffen werden kann. Eine Problemumgehung besteht darin, eine VPN-Verbindung des Unternehmens zu verwenden, wodurch der Client über das Unternehmensnetzwerk des Kunden mit CDN verbunden wird.

## <a name="next-steps"></a>Nächste Schritte
Wechseln Sie zu [Einrichten für Live-Events für Teams](set-up-for-teams-live-events.md).

### <a name="related-topics"></a>Verwandte Themen
- [Was sind Teams-Liveereignisse?](what-are-teams-live-events.md)
- [Einrichten von Teams-Liveereignissen](set-up-for-teams-live-events.md)
- [Konfigurieren von Live Ereigniseinstellungen in Microsoft Teams](configure-teams-live-events.md)

