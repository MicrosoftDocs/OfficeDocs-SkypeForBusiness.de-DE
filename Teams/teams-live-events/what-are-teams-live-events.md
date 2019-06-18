---
title: Was sind Live-Ereignisse in Microsoft Teams?
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.topic: conceptual
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: sonua
search.appverid: MET150
description: Erfahren Sie, wie Sie mit Live Ereignissen Videos und Inhalte an große Online-Benutzergruppen in Teams, jammern und Datenströmen übertragen können.
f1keywords: ms.teamsadmincenter.liveevents.policies
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4110e9dbfdff6548c0cae1406f1139835d00ec40
ms.sourcegitcommit: 9d9376c6e5e6d79e33ba54fb8ce87509a2f57754
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2019
ms.locfileid: "35013010"
---
# <a name="what-are-microsoft-teams-live-events"></a>Was sind Live-Ereignisse in Microsoft Teams?

## <a name="overview"></a>Übersicht

Mit Live-Ereignissen von Teams können Benutzer in Ihrer Organisation Video-und Besprechungsinhalte an große Online-Zielgruppen übertragen. 

Mit den Live-Ereignissen von Microsoft 365 können Live-Videoübertragungen auf eine neue Ebene durchführen, was die Verbindung über den gesamten Lebenszyklus des Engagements mit Teilnehmern vor, während und nach Live-Events anregt. Sie können ein Live-Ereignis erstellen, unabhängig davon, wo sich Ihre Zielgruppe, Ihr Team oder Ihre Community befindet, indem Sie Microsoft Stream, Teams oder jammern verwenden.  

Teams bietet Chat basierte Zusammenarbeit, Anrufe, Besprechungen und Live Ereignisse, sodass Sie das Publikum ihrer Besprechungen erweitern können. Live-Events von Teams ist eine Erweiterung von Teams-Besprechungen, die es Benutzern ermöglichen, Video-und Besprechungsinhalte an eine große Online-Zielgruppe zu übertragen. Diese sind für eine 1: n-Kommunikation vorgesehen, in der der Gastgeber des Ereignisses die Interaktionen führt und die Teilnahme am Publikum in erster Linie dazu dient, die vom Host freigegebenen Inhalte anzuzeigen. Die Teilnehmer können das Live-oder aufgezeichnete Ereignis in "jammern", "Teams" und/oder "Stream" verfolgen und mit moderierten Q-#a0 einer Unterhaltung oder einer jammern-Konversation mit den Referenten interagieren. 

Live-Events von Teams gelten als die nächste Version der Skype-Live Konferenz und ersetzen schließlich die Funktionen, die in der Skype-Live Konferenz zur Verfügung gestellt werden. An diesem Punkt wird Microsoft weiterhin Skype-Live Konferenz für Benutzer unterstützen, die Skype for Business in ihren Organisationen verwenden, ohne Unterbrechungen beim Service für neue oder zukünftige Ereignisse. Wir empfehlen Ihnen jedoch, Teams Live-Events zu testen, um alle neuen und spannenden Funktionen wie Bildschirmübertragung und Unterstützung externer Hardware/Software-Encoder zu nutzen. 

Also lasst uns loslegen. Sehen Sie sich zunächst das folgende Diagramm an, in dem die Komponenten auf hoher Ebene, die an Microsoft 365-Live Ereignissen beteiligt sind und wie diese verbunden sind, angezeigt werden. 

![Diagramm mit wichtigen Komponenten von Live Ereignissen] (../media/teams-live-events.png  "Diagramm mit wichtigen Komponenten von Live Ereignissen, Terminplanung, Produktion, Datenstrom Plattform, zertifizierten Drittanbieter-ECDN")

### <a name="event-group-roles"></a>Ereignisgruppen Rollen
Mit Live Ereignissen in Teams können mehrere Rollen (Organisator, Produzent, Referent und Teilnehmer) erfolgreich übertragen und an einem Ereignis teilnehmen. Weitere Informationen finden Sie unter [Rollen der Ereignisgruppe](https://support.office.com/article/get-started-with-microsoft-teams-live-events-d077fec2-a058-483e-9ab5-1494afda578a?ui=en-US&rs=en-US&ad=US#bkmk_roles).

## <a name="key-components"></a>Schlüsselkomponenten
Sie können aus dem Bild oben sehen, dass es vier wichtige Komponenten gibt, die in Teams für Live-Ereignisse verwendet werden.

### <a name="scheduling"></a>Planung
Teams bietet den Organisatoren die Möglichkeit, ein Ereignis mit den entsprechenden Berechtigungen für Teilnehmer zu erstellen, Ereignis Teammitglieder festzulegen, eine Produktionsmethode auszuwählen und Teilnehmer einzuladen. Wenn das Live-Ereignis in einer Gruppe von "jammern" erstellt wurde, können die Teilnehmer des Live-Ereignisses für die Interaktion mit Personen in dem Ereignis eine Jammer Unterhaltung verwenden. 

Screenshot ![mit dem Bildschirm "neue Live Ereignisse"] Screenshot mit (../media/teams-live-events-schedule.png "dem neuen Live Ereignis Bildschirm zum Erstellen und Planen eines neuen Liveereignisses")

### <a name="production"></a>Produktions
Der Videoeingang ist das Fundament des Live-Events und kann von einer einzelnen Webcam bis hin zu einer professionellen Videoproduktion mit mehreren Kameras variieren. Die Live Ereignisse in Microsoft 365 unterstützen ein Spektrum von Produktionsszenarien, einschließlich eines Ereignisses, das in Teams mit einer Webcam oder einem Ereignis in einer externen APP oder einem Gerät erstellt wurde. Sie können diese Optionen je nach Projektanforderungen und Budget auswählen. Es gibt zwei Möglichkeiten zum Erstellen von Ereignissen:

- **Teams**: mit dieser Produktionsmethode können Benutzer ihre Live-Events in Teams mit Ihrer Webcam oder mit einer/V-Eingabe von Teams Room Systems erstellen. Diese Option ist die beste und schnellste Option, wenn Sie die Audio-und Videogeräte, die mit dem PC verbunden sind, verwenden möchten, oder wenn Sie Remote Referenten einladen, an der Veranstaltung teilzunehmen. Diese Option ermöglicht es Benutzern, Ihre Webcams einfach zu nutzen und Ihren Bildschirm als Eingabe für die Veranstaltung freizugeben. 

    ![Screenshot mit einem Live Ereignis, das mit der Schnellstart Methode erstellt] wurde (../media/teams-live-events-quick-start.png "Screenshot mit einem Live Ereignis, das mithilfe der Schnellstart-Produktionsmethode erstellt wird")

- **Externe APP oder Gerät**: externe Encoder ermöglichen Benutzern, Ihre Live Ereignisse direkt von einem externen Hardware-oder softwarebasierten Encoder mit [Stream](https://stream.microsoft.com)zu produzieren. Diese Option ist am besten geeignet, wenn Sie bereits über Studio-qualitätsgeräte (beispielsweise Medien Mischer) verfügen, die das Streaming zu einem RTMP-Dienst (Real-Time Messaging Protocol) unterstützen. Diese Art der Produktion wird in der Regel in großflächigen Ereignissen wie exekutiven Stadthallen verwendet, in denen ein einzelner Datenstrom von einem Medien Mixer an das Publikum übertragen wird. 

    ![Screenshot mit einem Live Ereignis, das mit einer externen APP oder einem Gerät erstellt] wurde (../media/teams-live-events-external-encoder.png "Screenshot mit einem Live Ereignis, das mit der externen APP oder Geräte Produktionsmethode erstellt wird")

### <a name="streaming-platform"></a>Streaming-Plattform
Die Live-Event-Streaming-Plattform besteht aus den folgenden Teilen:

- **Azure Media Services**: [Azure Media Services](https://docs.microsoft.com/azure/media-services/previous/) bietet Ihnen Broadcast-Quality-Video Streaming-Dienste, um größere Zielgruppen auf den heute beliebtesten mobilen Geräten zu erreichen. Media Services verbessert die Barrierefreiheit, Verteilung und Skalierbarkeit und macht es einfach und kostengünstig, Inhalte an Ihre lokalen oder weltweiten Zielgruppen zu streamen, während Sie Ihre Inhalte schützen.
- **Azure Content Delivery Network (CDN)**: Sobald der Datenstrom in Echtzeit übertragen wird, wird er über das [Azure Content Delivery Network (CDN)](https://docs.microsoft.com/azure/cdn/)bereitgestellt. Azure Media Services bietet integriertes CDN für Streaming-Endpunkte. Auf diese Weise können die Streams weltweit ohne Pufferung angezeigt werden.

### <a name="enterprise-content-delivery-network-ecdn"></a>Enterprise Content Delivery Network (ECDN)
Das Ziel von ECDN besteht darin, die Videoinhalte aus dem Internet zu übernehmen und die Inhalte im gesamten Unternehmen zu verteilen, ohne die Netzwerkleistung zu beeinträchtigen. Sie können einen der folgenden Certified ECDN-Partner verwenden, um Ihr Netzwerk für Live-Events in Ihrer Organisation zu optimieren:
- [Struktur](https://www.hivestreaming.com/partners/integration-partners/microsoft/)
- [Kollective](http://www.kollective.com)
- [Typhierarchie](http://www.ramp.com)

### <a name="attendee-experience"></a>Teilnehmer-Erfahrung 
Die Teilnehmer-Erfahrung ist der wichtigste Aspekt von Live Ereignissen, und es ist wichtig, dass die Teilnehmer am Live-Ereignis teilnehmen können, ohne dass Probleme auftreten. Die Teilnehmer-Oberfläche verwendet Azure Media Player (für Ereignisse, die in Teams erstellt wurden) und Stream Player (für Ereignisse, die in einer externen APP oder einem Gerät erstellt wurden) und funktioniert auf Desktop-, Browser-und Mobilgeräten (Ios, Android). Office 365 bietet jammern und Teams zwei Zusammenarbeit-Hubs, und die Live-Teilnehmer-Erfahrung ist in diese Tools für die Zusammenarbeit integriert. 

![Screenshot der Live-Teilnehmer-Erfahrung] (../media/teams-live-events-attendee.png "Screenshot der Live-Teilnehmer-Erfahrung")

## <a name="next-steps"></a>Nächste Schritte
Wechseln Sie zu [Plan für Teams-Live Ereignisse](plan-for-teams-live-events.md).

### <a name="related-topics"></a>Verwandte Themen
- [Live Ereignisse in Microsoft 365 in jammern, Microsoft Teams und Microsoft Stream](https://docs.microsoft.com/stream/live-event-m365)
- [Erste Schritte mit Microsoft Teams Live-Events](https://support.office.com/article/d077fec2-a058-483e-9ab5-1494afda578a)
- [Live Ereignisse in "jammern"](https://support.office.com/article/live-events-in-yammer-4ece0ee2-c268-4636-bf2a-16e454befe57)
- [Live Ereignisse in Microsoft Stream](https://docs.microsoft.com/stream/live-event-overview)

 
