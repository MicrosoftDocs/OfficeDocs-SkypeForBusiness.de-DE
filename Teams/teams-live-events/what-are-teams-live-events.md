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
ms.reviewer: tonysmit
search.appverid: MET150
description: Hier erfahren Sie, wie live Ereignisse Benutzer Video- und große online Publikum in Microsoft-Teams, Yammer und Stream Microsoft Content übertragen können.
f1keywords: ms.teamsadmincenter.liveevents.policies
appliesto:
- Microsoft Teams
ms.openlocfilehash: 02db69572fa13e5c02717e7d8d192ca1b61cff8e
ms.sourcegitcommit: 70d4d02a3cc894f2f197aeea459ac079cde63877
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "30542895"
---
# <a name="what-are-microsoft-teams-live-events"></a>Was sind Live-Ereignisse in Microsoft Teams?
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

## <a name="overview"></a>Übersicht

Microsoft-Teams live-Ereignissen können Benutzer in Ihrer Organisation Video- und Meeting Inhalte für große online Benutzergruppen übertragen. 

Microsoft 365 live Ereignisse bringen live Videostreaming auf eine neue Ebene, Förderung der Verbindung während des gesamten Projekts Lebenszyklus mit Teilnehmer vor, während und nach live-Ereignissen. Sie können ein live-Ereignis erstellen, unabhängig von dessen Speicherort Ihrer Benutzergruppe, Team oder Community befindet sich mit Microsoft Stream, Microsoft-Teams, oder Yammer.  

Teams bietet Chat-basierte Zusammenarbeit, Anrufe, Konferenzen und live-Ereignissen, Sie können erweitern Sie die Benutzergruppe Besprechungsliste. Teams live Ereignisse ist eine Erweiterung von Teams Besprechungen, die Benutzern ermöglichen, Video- und Meeting Inhalte an eine große online Benutzergruppe übertragen. Diese sind für die 1: n-Kommunikation vorgesehen, in denen der Host des Ereignisses wird die Interaktionen führende und Benutzergruppe Teilnahme ist in erster Linie zum Anzeigen des Inhalts von Host gemeinsam genutzt werden. Die Teilnehmer können das live oder aufgezeichnete-Ereignis im Yammer, Teams und/oder Microsoft Stream Video, und die Referenten mit moderierte Q & A oder eine Unterhaltung Yammer interagieren können. 

Ersetzen Sie Teams live Ereignisse gelten die nächste Version von Skype Besprechung übertragen und schließlich werden die Funktionen in Skype Besprechung übertragen. Während der public Preview-Version von Teams live-Ereignissen wird es weiterhin Skype Besprechung übertragen,-ohne Unterbrechung im Dienst für neue oder zukünftigen Ereignisse unterstützen. Jedoch wir empfehlen Ihnen, Teams live Ereignisse, um alle neuen und interessanten Features Bildschirmfreigabe, einschließlich nutzen ausprobieren Teilnehmeranzahl, und Unterstützung für externe Hardware und Software Encoder. 

Also lasst uns loslegen. Betrachten Sie zuerst das folgende Diagramm, das zeigt, beteiligten Komponenten auf hohe Ebene in Microsoft 365 live Ereignisse und wie sie verbunden sind. 

![Diagramm der wichtige Komponenten der live Ereignisse, Planung, Produktion, Stream Microsoft-Plattform, certified eCDN Drittanbieter - Anbieter] (../media/teams-live-events.png  "Diagramm der wichtige Komponenten der live Ereignisse, Planung, Produktion, Stream Microsoft-Plattform, certified eCDN Drittanbieter - Anbieter")

## <a name="key-components"></a>Wichtige Komponenten
Sie können aus dem obigen Bild sehen, sind vier wichtige Komponenten, die mit live Ereignisse in Teams verwendet werden.

### <a name="scheduling"></a>Planung
Teams bietet die Möglichkeit für die Verwaltung von Organisatoren auf ein Ereignis mit der entsprechenden Teilnehmer Berechtigungen erstellen, Ereignis Teammitglieder festzulegen, wählen Sie Produktionsmethode und Teilnehmer einladen. Wenn das live-Ereignis innerhalb einer Gruppe Yammer erstellt wurde, werden die live-Ereignis Teilnehmer Yammer Unterhaltung verwenden für die Interaktion mit Personen in das Ereignis können. 

![Screenshot mit neu live Ereignisse Bildschirm zum Erstellen und planen ein neues live-Ereignis] (../media/teams-live-events-schedule.png "Screenshot mit neu live Ereignis Bildschirm zum Erstellen und planen ein neues live-Ereignis")

### <a name="production"></a>Produktion
Die live-Ereignisse in Microsoft 365 ein Spektrum der Produktionsszenarien unterstützen, schließen Sie ein Schnellstart-Ereignis mithilfe von Webcams oder externen Encoder Ereignisse mit dem Studio Qualität Equipment. Video Eingabe bildet die Grundlage für die Live-Ereignisse und kann aus einer einzelnen Webcam an eine professionelle video Multi-Kamera-Produktion variieren. Sie können diese Optionen je nach ihren Project-Anforderungen und Ihrem Budget auswählen. Es gibt zwei Methoden, um Ereignisse zu erzeugen:

- **Schnellstart Produktion**: die Schnellstart Produktion-Methode können Benutzer ihre live Ereignissen mithilfe von Teams Besprechungen zu erstellen. Diese Option eignet sich am besten und schnellste Option aus, wenn Sie die Audio- und Videogeräte automatisch verwenden möchten verbunden mit dem PC oder remote Referenten für das Ereignis Teilnahme einladen. Mit dieser Option können Benutzer auf einfache Weise ihre Webcams verwenden und Freigeben von ihren Bildschirm als Eingabe für das Ereignis. 

    ![Screenshot zeigt ein live-Ereignis erstellt, indem die Quick start Produktionsmethode] (../media/teams-live-events-quick-start.png "Screenshot zeigt ein live-Ereignis, das erzeugt wird, mithilfe der Schnellstartleiste, start Produktionsmethode")

- **Externe Encoder Produktion**: externe Encoder zulassen, dass Benutzer ihre live Ereignisse direkt aus einer externen Hardware oder eine softwarebasierte Encoder mit [Microsoft Stream-Objekt](https://stream.microsoft.com)zu erstellen. Diese Option empfiehlt sich, wenn Sie bereits Studio Qualität Equipment (beispielsweise Media Mischern) verfügen, welche Unterstützung streaming an einen Dienst Real-Time Messaging Protocol (RTMP). Diese Art der Produktion wird normalerweise in großem Umfang Ereignisse wie executive Stadt Hallen – verwendet, in ein einzelner Datenstrom aus einem Media Mixer auf die Benutzergruppe gesendet wird. 

    ![Screenshot zeigt ein live-Ereignis erstellt, indem Sie die externen Encoder Produktion-Methode] (../media/teams-live-events-external-encoder.png "Screenshot des ein, die mit der externen Encoder Produktion-Methode erzeugt wird, live-Ereignis")

### <a name="streaming-platform"></a>Streaming-Plattform
Die live-Ereignis-streaming-Plattform besteht aus die folgenden Teile:

- **Azure-Media-Dienste**: [Azure Media-Dienste](https://docs.microsoft.com/azure/media-services/previous/) können Sie die Übertragung Qualität video streaming-Dienste größere Benutzergruppen auf heutigen am häufigsten verwendeten mobilen Geräten zu erreichen. Media-Dienste verbessert Eingabehilfen, Verteilergruppen und Skalierbarkeit und können sie einfach und kostengünstige Stream von Inhalten für Ihre lokale oder weltweit Zielgruppe – alle beim Schützen Ihrer Inhalte.
- **Azure Content Delivery Network (CDN)**: Sobald Ihr Stream live wird, über die [Azure Content Delivery Network (CDN)](https://docs.microsoft.com/azure/cdn/)geliefert. Azure Media-Dienste bietet integrierte CDN für streaming-Endpunkte. Dies ermöglicht die Datenströme weltweit mit keine Pufferung angezeigt werden.

### <a name="enterprise-content-delivery-network-ecdn"></a>Enterprise Content Delivery Network (eCDN)
Das Ziel des eCDN ist den Videoinhalt aus dem Internet und verteilen die Inhalte im gesamten Unternehmen ohne Beeinträchtigung der Leistung des Netzwerks. Eine der folgenden können certified Partner eCDN Sie um Ihr Netzwerk für live Ereignisse frei, die in Ihrem Unternehmen zu optimieren:
- [Struktur](https://www.hivestreaming.com/partners/integration-partners/microsoft/)
- [Kollective](http://www.kollective.com)
- [Lernen](http://www.ramp.com)

### <a name="attendee-experience"></a>Umgebung Teilnehmer 
Umgebung der Teilnehmer ist der wichtigste Aspekt der live Ereignisse, und es ist wichtig, dass die Teilnehmer im live-Ereignis teilnehmen können, ohne Probleme. Umgebung der Teilnehmer Azure Media Player verwendet und kann über den Desktop, Browser und Mobile (iOS Android). Office 365 bietet Yammer und Teams als zwei Zusammenarbeit Hubs und die Teilnehmer live Erfahrung in diese Tools für die Zusammenarbeit integriert ist. 

![Screenshot mit der Teilnehmer live Ereignisse auftreten] (../media/teams-live-events-attendee.png "Screenshot mit der Teilnehmer live Ereignisse auftreten")

## <a name="next-steps"></a>Nächste Schritte
Wechseln Sie zur [Planung von Teams live Ereignisse](plan-for-teams-live-events.md).

### <a name="related-topics"></a>Verwandte Themen
- [Ereignisse über Microsoft 365 in Yammer, Microsoft-Teams und Stream Microsoft Live](https://docs.microsoft.com/stream/live-event-m365)
- [Live-Ereignisse im Microsoft-Teams](https://support.office.com/article/microsoft-teams-live-event-overview-d077fec2-a058-483e-9ab5-1494afda578a)
- [Live Ereignisse in Yammer](https://support.office.com/article/live-events-in-yammer-4ece0ee2-c268-4636-bf2a-16e454befe57)
- [Live-Ereignisse im Microsoft-Stream](https://docs.microsoft.com/stream/live-event-overview)

 
