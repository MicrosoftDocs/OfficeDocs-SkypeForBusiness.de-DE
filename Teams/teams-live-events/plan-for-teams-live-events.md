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
localization_priority: Priority
ms.collection:
- M365-collaboration
search.appverid: MET150
description: In diesem Artikel erfahren Sie, welche Faktoren zu berücksichtigen sind, wenn Sie Liveereignisse in Microsoft Teams einrichten.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9ac74a75ff159a4ec00a660c4bb01759614c8d10
ms.sourcegitcommit: 0a9c5c01b37a93eecc369ca0ed49ae18f6a5065b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2020
ms.locfileid: "48655491"
---
# <a name="plan-for-live-events-in-microsoft-teams"></a>Planen von Liveereignissen in Microsoft Teams

Wenn Sie Live Events in Teams planen, um große Besprechungen in Ihrer Organisation abzuhalten, gibt es mehrere Faktoren, die Sie vor Beginn der Einrichtung berücksichtigen müssen.

 > [!Note]
> For details about Teams live events on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3). See [prepare your organization](../prepare-network.md) to learn about bandwidth requirements for Teams live events.

## <a name="who-can-attend-create-and-schedule-live-events"></a>Wer kann an Liveereignissen teilnehmen, diese erstellen und planen?

Anyone can attend a live event without a license. Read [Admin quick start - Meetings and live events](../quick-start-meetings-live-events.md).

Die folgenden Voraussetzungen müssen erfüllt sein, damit ein Benutzer ein Teams-Liveereignis planen kann.

Folgende Lizenzen müssen für die Erstellung oder Vorführung eines Microsoft Teams-Liveereignisses zugewiesen werden:  

- A Microsoft or Office 365 Enterprise E1, E3, or E5 license or an Office 365 Education A3 or A5 license. The exception to this requirement is guest users can present without a license if the other criteria for [guest users](plan-for-teams-live-events.md#guest-to-present) is met.
- Eine Microsoft Teams Lizenz – diese ist in den im ersten Aufzählungspunkt aufgeführten Lizenzen enthalten.
- Eine Microsoft Stream-Lizenz – ist erforderlich, wenn Sie planen, den Inhalt mit einer externen App oder einem externen Gerät zu teilen; siehe [Microsoft Stream-Lizenzierung](https://docs.microsoft.com/stream/license-overview).

  Benutzer brauchen keine Microsoft Stream-Lizenz, wenn Sie möchten, dass Benutzer nur die Aufzeichnungen aufnehmen und herunterladen. Das bedeutet, dass die Aufzeichnungen nicht in Microsoft Stream gespeichert werden, sondern in Azure Media Services (AMS) mit einem 180-Tage-Limit, bevor sie gelöscht werden. Derzeit können Admins keine Befähigung zum Löschen verwalten oder steuern.

>[!Note]
> The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](../tmr-meeting-recording-change.md) will be a phased approach. At launch you'll be able to opt-in to this experience, in November you'll have to opt-out if you want to continue using Stream, and some time in early 2021 we'll require all customers to OneDrive for Business and SharePoint for meeting recordings.

> [!NOTE]
> Zurzeit gibt es keine Microsoft 365 Small Business-Pläne, die zum Erstellen und Abhalten von Microsoft Teams-Liveereignissen verwendet werden können.

Es ist wichtig zu wissen, dass eine Microsoft 365- oder Office 365-Lizenz erforderlich ist, um an einem Liveereignis als authentifizierter Benutzer teilzunehmen, aber diese Anforderung hängt von der verwendeten Produktionsmethode ab:

- **Für Ereignisse, die in Teams erstellt werden**, muss dem Benutzer eine Teams-Lizenz zugewiesen werden.
- **Für Ereignisse, die mit einer externen App oder einem externen Gerät erstellt wurden**, muss dem Benutzer eine Stream-Lizenz zugewiesen werden.

> [!NOTE]
> Für US Government Cloud Community (GCC)-Organisationen sind jetzt Teams-Liveereignisse verfügbar.

Weitere Informationen zur Lizenzierung finden Sie unter [Microsoft Teams-Add-On-Lizensierung](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).

Der Benutzer muss Folgendes besitzen:

- Die Planung privater Besprechungen in Teams muss aktiviert sein (*TeamsMeetingPolicy -AllowPrivateMeetingScheduling-Parameter = True"*).
- Die Videofreigabe in Teams-Besprechungen muss aktiviert sein (*TeamsMeetingPolicy -AllowIPVideo-Parameter = True*).
- Die Bildschirmfreigabe in Teams-Besprechungen muss aktiviert sein (*TeamsMeetingPolicy -ScreenSharingMode-Parameter = EntireScreen*).
- Die Planung von Liveereignissen in Teams muss aktiviert sein (*TeamsMeetingBroadcastPolicy -AllowBroadcastScheduling-Parameter = True*).
- Berechtigungen zum Erstellen von Liveereignissen in Stream (für die Produktion externer Anwendungen oder Geräte).
- Der Koexistenzmodus ist so konfiguriert, dass Teambesprechungen (*Inselmodus, "Besprechung zuerst" oder "Nur Teams"*) geplant werden können.

> [!IMPORTANT]
> Nicht authentifizierte anonyme Benutzer können nicht als Produzenten oder Moderatoren zu Liveereignissen in Teams eingeladen werden.

### <a name="guest-to-present"></a>[Gast zur Präsentation](#guest-to-present)

Damit ein Gast bei einem Liveereignis präsentieren kann, gehen Sie wie folgt vor:

1. [Fügen Sie den Benutzer als Gast zu einem Team hinzu](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).
2. Der Benutzer muss die Gasteinladung annehmen und dem Team beitreten.
3. [Planen Sie das Liveereignis, und fügen Sie den Gast zu ihrer Ereignisgruppe hinzu](https://support.microsoft.com/article/schedule-a-teams-live-event-7a9ce97c-e1cd-470f-acaf-e6dfc179a0e2).

As a best practice, we recommend that you create a channel for producers and presenters of the live event so they can chat and share information before the event. Guests who don't have Microsoft 365 credentials won't see the Calendar in Teams. To make it easy for them to join the event, producers can post the event link to the channel. Presenters can then open Teams, go to the channel, and then click the link to join the event.

## <a name="who-can-watch-live-events"></a>Wer kann Liveereignisse anschauen?

|**Sichtbarkeit für Teilnehmer**       |**Teams-Produktion **  |**Produktion externer Anwendungen oder Geräte**  |
|------------------------------|-----------------|----------------------|
|Öffentlich (anonyme Benutzer)      |  Ja            |  Nein                  |
|Gastbenutzer                   |  Ja            |  Nein                  |
|Jeder im Unternehmen mit externem Zugriff (Partnerverbund) |  Ja<sup>1</sup>|  Nein                  |
|Jeder im Unternehmen           |  Ja            |  Ja                 |
|Bestimmte Gruppen/Personen      |  Ja            |  Ja                 |

<sup>1</sup> Teilnehmer mit externem Zugriff (Verbundteilnehmer) können nur über „Personen & Gruppen“ eingeladen werden. <br>

## <a name="teams-live-events-and-skype-meeting-broadcast"></a>Teams-Liveereignisse und Skype Meeting Broadcast

Die folgende Tabelle enthält eine Gegenüberstellung der verfügbaren Kernfunktionen und Features bei Liveereignissen und Skype Meeting Broadcast.

> [!IMPORTANT]
> **Das Limit für Microsoft 365 Live-Ereignisse wird erhöht**
>
> **Um unsere Kunden zu unterstützen, werden bis zum 1. Januar 2021 zeitlich begrenzte Erhöhungen für Liveereignisse in Teams, Stream und Yammer erweitern, einschließlich**:
>
>- Bis zu 20.000 Teilnehmer pro Ereignis
>- Bis zu 50 gleichzeitige Ereignisse pro Team-Mandant
>- Bis zu 16 Stunden pro Sendung
>
> Additionally, live events with up to 100,000 attendees can be planned through the Microsoft 365 live events assistance program. The team will assess each request and work with you to determine options that may be available. [Learn more](https://aka.ms/Stream/Blog/LiveEventOptions). **After January 1, 2021, customers who need these limit increases will be required to purchase the [Advanced Communications add-on](../teams-add-on-licensing/advanced-communications.md).**

|**Funktion**   |**Skype Meeting Broadcast** |**In Teams produzierte Ereignisse** |**In einer externen App oder auf einem externen Gerät produzierte Ereignisse** |
|---------|---------|---------|---------|
|Maximale Zielgruppengröße |10.000 Teilnehmer |10.000 Teilnehmer<sup>1</sup> |10.000 Teilnehmer<sup>1</sup> |
|Maximale Dauer eines Liveereignisses |4 Stunden |4 Stunden |4 Stunden |
|Maximale Anzahl von Referenten und Produzenten in einem Liveereignis |10 <sup>2</sup> |10 <sup>2</sup> |10 <sup>2</sup> |
|Maximale Anzahl gleichzeitiger Liveereignisse pro Microsoft 365- oder Office 365-Organisation |15  | 15  | 15  |
|Erstellung von Liveereignissen |   Skype Meeting Broadcast-Portal |Teams, Yammer via Teams | Teams, Yammer via Teams, Stream |
|Zielgruppen-Engagement – Yammer |&#x2714; |&#x2714; (integrierte Lösung) |&#x2714; (integrierte Lösung) |
|Zielgruppen-Engagement – Moderierte F & A |&#x2714;  |&#x2714; |&#x2714; |
|Produzentenclient unter Windows |&#x2714; (Skype for Business) |&#x2714; (Teams) |&#x2714; (Stream, Teams via Stream Embed) |
|Produzentenclient auf Mac |&#x274C;  | &#x2714; (Teams) |&#x2714; (Stream, Teams via Stream Embed) |
|Teilnehmeranzahl in Produzenten-UI |&#x274C;  |&#x2714; (Teams) |&#x2714; (Stream, Teams via Stream Embed) |
|Mehrere Referenten zulässig |&#x2714; (Skype for Business) |&#x2714; (Teams) |–  |
|Referenten während der Sitzung einladen |&#x2714; (Skype for Business) |&#x274C; |Nicht zutreffend |
|Referenten über Web und Mobilgerät teilnehmen |&#x2714; (Skype for Business)  |&#x274C; |– |
|Externer Zugriff (Partnerverbund) & Gastreferenten/-teilnehmer |&#x2714; (Skype for Business)  |  &#x2714; (Teams) |Nicht zutreffend |
|Referent – Telefonfestnetz (PSTN)-Zugang |&#x274C; |&#x2714; (Teams) |– |
|Bildschirm präsentieren |&#x274C; |&#x2714; (Teams) |– |
|Systemaudio unter Windows freigeben (nur bei Bildschirmfreigabe verfügbar)|&#x274C; |&#x2714; (Teams) |&#x2714; |
|PowerPoint präsentieren (PPT-Freigabe) |&#x2714; |&#x274C; (möglich über Bildschirmfreigabe) |Nicht zutreffend |
|Aufzeichnung einer cloudbasierten Besprechung |&#x2714; |&#x2714; |&#x2714; |
|Automatische Veröffentlichung der Aufzeichnung in Stream |&#x274C; |&#x274C; |&#x2714; |
|Livebeschriftungen und Untertitel |&#x2714; |&#x2714; |&#x274C; |
|Beschriftungen in Aufzeichnungen von Liveereignissen |&#x2714; |&#x2714; |&#x2714; |
|Teilnehmer-DVR-Steuerung (Pause, Rücklauf) |&#x2714; |&#x2714; |&#x2714; |
|Partner eCDN-Unterstützung |&#x2714; (Kollective, Hive, Riverbed) |&#x2714; (Kollective, Hive, Riverbed) |&#x2714; (Hive, Kollective, Rampe, Riverbed) |
|Nachträglich gesendeter Anwesenheitsbericht für Produzenten |&#x2714; |&#x2714; |&#x274C; |
|Teilnehmerstimmungsanalyse – Liveabstimmungen & -umfragen |&#x2714; (Microsoft Pulse) |&#x274C; |&#x274C; |

<sup>1</sup> The limits that are set might be changed. Check [Limits and specifications for Teams](../limits-specifications-teams.md).<br/>
<sup>2</sup> Sie können bis zu 250 Referenten und Produzenten in einem Liveereignis haben, aber nur die letzten 10, die gesprochen haben, werden in der Liste angezeigt.

## <a name="regional-availability"></a>Regionale Verfügbarkeit

You can use Teams live events in multiple regions across the world. The following information shows availability for event team members and attendees.

> [!IMPORTANT]
> Die Region für das Ereignis wird automatisch in Abhängigkeit vom Organisator und vom Microsoft 365-Mandantenstandort ausgewählt.

**In diesen regionalen Rechenzentren verfügbar**

- Nordamerika
- Mittelamerika
- Südamerika
- Asiatisch-pazifischer Raum
- Europa/Afrika

**Datenspeicherort für diese Länder/Regionen (unterstützt)**

- Australien
- Kanada
- Indien
- Japan
- Vereinigtes Königreich

**Diese Länder/Regionen und Clouds werden nicht unterstützt**

- Deutschland
- Frankreich
- Norwegen
- Südafrika
- Südkorea
- Schweiz
- VAE
- Government Community Cloud (GCC)-H
- DOD

**Ausschlüsse und Überlegungen**.

- **Datenspeicherort:** Teams-Datenspeicherorte außerhalb der oben aufgeführten werden derzeit nicht unterstützt.
- **China:** Event team members and attendees will not be able to use Teams live events because Azure CDN is not accessible in China. A workaround is to use a company VPN connection, which gets the client connected to CDN via the customer's corporate network.

## <a name="next-steps"></a>Nächste Schritte

Navigieren Sie zu [Einrichten von Teams-Liveereignissen](set-up-for-teams-live-events.md).

### <a name="related-topics"></a>Verwandte Themen

- [Was sind Teams-Liveereignisse?](what-are-teams-live-events.md)
- [Einrichten von Teams-Liveereignissen](set-up-for-teams-live-events.md)
- [Konfigurieren der Einstellungen für Liveereignisse in Teams](configure-teams-live-events.md)
