---
title: Planen von Liveereignissen in Microsoft Teams
author: cichur
ms.author: v-cichur
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
- m365initiative-meetings
- enabler-strategic
search.appverid: MET150
description: In diesem Artikel erfahren Sie, welche Faktoren zu berücksichtigen sind, wenn Sie Liveereignisse in Microsoft Teams einrichten.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: af2915d1e86fbfe1c3dc2bd804511a8e7ca6865a
ms.sourcegitcommit: 27bfa015413bc7742bca4ea227e0324da0c740d7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145912"
---
# <a name="plan-for-live-events-in-microsoft-teams"></a>Planen von Liveereignissen in Microsoft Teams

Wenn Sie Live Events in Teams planen, um große Besprechungen in Ihrer Organisation abzuhalten, gibt es mehrere Faktoren, die Sie vor Beginn der Einrichtung berücksichtigen müssen.

> [!Note]
> Einzelheiten zu Liveereignisse in Teams auf verschiedenen Plattformen finden Sie unter [Features für Teams nach Plattform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3). Weitere Informationen zu den Bandbreitenanforderungen für Teams finden Sie unter [Vorbereiten Ihrer Organisation](../prepare-network.md).

## <a name="who-can-attend-create-and-schedule-live-events"></a>Wer kann an Liveereignissen teilnehmen, diese erstellen und planen?

Jeder kann an einem Liveereignis ohne Lizenz teilnehmen. Lesen Sie [Schnellstart für Administratoren: Besprechungen und Liveereignisse](../quick-start-meetings-live-events.md).

Die folgenden Voraussetzungen müssen erfüllt sein, damit ein Benutzer ein Teams-Liveereignis planen kann.

Folgende Lizenzen müssen für die Organisation, Erstellung oder Vorführung eines Microsoft Teams-Liveereignisses zugewiesen werden:  

- **Organisation:** Eine Microsoft oder Office 365 Enterprise E1-, E3- oder E5-Lizenz **[oder]** eine Microsoft oder Office 365 Education A3- oder A5-Lizenz. 
- **Erstellung oder Vorführung:** Eine Microsoft oder Office 365 Enterprise E1-, E3- oder E5-Lizenz **[oder]** eine Microsoft oder Office 365 Education A1-, A3 oder A5-Lizenz. Die Ausnahme von dieser Anforderung ist, dass Gastnutzer ohne Lizenz präsentieren können, wenn die anderen Kriterien für [Gastnutzer](plan-for-teams-live-events.md#guest-to-present) erfüllt sind.
- Eine Microsoft Teams Lizenz – diese ist in den im ersten und zweiten Aufzählungspunkt aufgeführten Lizenzen enthalten.
- Eine Microsoft Stream-Lizenz – ist erforderlich, wenn Sie planen, den Inhalt mit einer externen App oder einem externen Gerät zu teilen; siehe [Microsoft Stream-Lizenzierung](https://docs.microsoft.com/stream/license-overview).

  Benutzer brauchen keine Microsoft Stream-Lizenz, wenn Sie möchten, dass Benutzer nur die Aufzeichnungen aufnehmen und herunterladen. Das bedeutet, dass die Aufzeichnungen nicht in Microsoft Stream gespeichert werden, sondern in Azure Media Services (AMS) mit einem 180-Tage-Limit, bevor sie gelöscht werden. Derzeit können Admins keine Befähigung zum Löschen verwalten oder steuern.

>[!Note]
> Der Wechsel von Microsoft Stream zu [OneDrive for Business und SharePoint für Besprechungsaufzeichnungen](../tmr-meeting-recording-change.md) erfolgt schrittweise. Bei der Markteinführung können Sie sich optional für diese Erfahrung anmelden. Im November müssen Sie sich abmelden, wenn Sie Stream weiterhin nutzen möchten. Ab Anfang 2021 verlangen wir von allen Kunden die Verwendung von OneDrive for Business und Microsoft Office SharePoint Online für Besprechungsaufzeichnungen.

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

Als bewährte Methode empfiehlt es sich, einen Kanal für Produzenten und Referenten des Liveereignisses zu erstellen, damit sie vor der Veranstaltung chatten und Informationen teilen können. Gäste, die keine Microsoft 365-Anmeldeinformationen haben, können den Kalender in Teams nicht sehen. Um ihnen die Teilnahme an dem Ereignis zu erleichtern, können die Produzenten den Ereignislink im Kanal posten. Referenten können dann Teams öffnen, zum Kanal wechseln und dann auf den Link klicken, um an dem Ereignis teilzunehmen.

## <a name="who-can-watch-live-events"></a>Wer kann Liveereignisse anschauen?

| Sichtbarkeit für Teilnehmer | Teams-Produktion | Produktion externer Apps oder Geräte |
|------------------------------|-----------------|----------------------|
|Öffentlich (anonyme Benutzer)      |  Ja            |  Nein                  |
|Gastbenutzer                   |  Ja<sup>1</sup>            |  Nein                  |
|Jeder im Unternehmen mit externem Zugriff (Partnerverbund) |  Ja<sup>1</sup>|  Nein                  |
|Jeder im Unternehmen           |  Ja            |  Ja                 |
|Bestimmte Gruppen/Personen      |  Ja            |  Ja                 |

<sup>1</sup> Können nur über „Personen & Gruppen“ eingeladen werden <br>

## <a name="teams-live-events-and-skype-meeting-broadcast"></a>Teams-Liveereignisse und Skype Meeting Broadcast

Die folgende Tabelle enthält eine Gegenüberstellung der verfügbaren Kernfunktionen und Features bei Liveereignissen und Skype Meeting Broadcast.

> [!IMPORTANT]
> **Das Limit für Microsoft 365 Live-Ereignisse wird erhöht**
>
> **Um die Bedürfnisse unserer Kunden weiterhin zu unterstützen, werden wir bis zum 30. Juni 2021 temporäre Limiterhöhungen für Liveereignisse verlängern, beispielsweise**:
>
>- Ereignisunterstützung für bis zu 20.000 Teilnehmer
>- 50 Ereignisse können über einen Mandanten gleichzeitig gehostet werden
>- Ereignisdauer von 16 Stunden pro Übertragung
>
> Außerdem können Liveereignisse mit bis zu 100.000 Teilnehmern über das Microsoft 365-Unterstützungsprogramm für Liveereignisse geplant werden. Das Team bewertet jede Anfrage und arbeitet mit Ihnen zusammen, um die eventuell verfügbaren Optionen zu bestimmen. [Weitere Informationen](https://aka.ms/Stream/Blog/LiveEventOptions). 

| Funktion | Skype Meeting Broadcast | In Teams produzierte Ereignisse | In einer externen App oder auf einem externen Gerät produzierte Ereignisse |
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

<sup>1</sup> Die festgelegten Grenzen können geändert werden. Überprüfen Sie [Grenzwerte und Daten für Teams](../limits-specifications-teams.md).<br/>
<sup>2</sup> Sie können bis zu 100 Referenten und Produzenten in einem Liveereignis haben, aber nur die letzten 10, die gesprochen haben, werden in der Liste angezeigt.

## <a name="regional-availability"></a>Regionale Verfügbarkeit

Sie können Teams-Liveereignisse in mehreren Regionen der Welt nutzen. Die folgenden Informationen zeigen die Verfügbarkeit für die Ereignisteammitglieder und -teilnehmer.

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
- **China:** Mitglieder und Teilnehmer des Ereignisteams können die Liveereignisse des Teams nicht nutzen, da das Azure CDN in China nicht zugänglich ist. Eine Problemumgehung ist die Verwendung einer Firmen-VPN-Verbindung, die den Client über das Firmennetzwerk des Kunden mit dem CDN verbindet.

## <a name="next-steps"></a>Nächste Schritte

Navigieren Sie zu [Einrichten von Teams-Liveereignissen](set-up-for-teams-live-events.md).

### <a name="related-topics"></a>Verwandte Themen

- [Was sind Teams-Liveereignisse?](what-are-teams-live-events.md)
- [Einrichten von Teams-Liveereignissen](set-up-for-teams-live-events.md)
- [Konfigurieren der Einstellungen für Liveereignisse in Teams](configure-teams-live-events.md)
