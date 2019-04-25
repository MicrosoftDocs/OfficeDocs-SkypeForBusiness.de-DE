---
title: AppSharingStream-Tabelle
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 391490cb-d7b8-44ca-b4d1-429600da909c
description: AppSharingStream-Tabelle enthält die Quality of Experience-Metriken für die Netzwerkstreams für die Anwendungsfreigabe verwendet. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: 8e01cc4d35269b34e3e6fba13fd331139e3f7ae7
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212341"
---
# <a name="appsharingstream-table"></a>AppSharingStream-Tabelle
 
AppSharingStream-Tabelle enthält die Quality of Experience-Metriken für die Netzwerkstreams für die Anwendungsfreigabe verwendet. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |dateTime  <br/> |Primär, Fremd  <br/> |Datum und Uhrzeit, zu der die Sitzung gestartet hat.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primär, Fremd  <br/> |Sequenzielle ID zur Unterscheidung von Sitzungen, die an demselben Tag und zur gleichen Zeit gestartet genutzt.  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primär, Fremd  <br/> | Finden Sie unter [MediaLine-Tabelle](https://docs.microsoft.com/skypeforbusiness/schema-reference/quality-of-experience-qoe-database-schema/medialine-0). <br/> |
|**StreamID** <br/> |int  <br/> |Primary  <br/> |Eindeutiger Bezeichner der Anwendungsfreigabe-Datenstroms.  <br/> |
|**JitterInterArrival** <br/> |int  <br/> ||Der durchschnittliche Jitter, der zwischen dem Eintreffen von RTP-Paketen ermittelt wurde. (Jitter ist ein Maß für das „Zittern“ der Übertragung während eines Anrufs.) Hohe Jitterwerte werden in der Regel durch Überlastung oder einen überlasteten Medienserver verursacht und führen zu verzerrter oder unterbrochener Sprachübertragung.  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> ||Maximale Jitter zwischen RTP Paket Eingänge erkannt. (Jitter ist ein Maß für die "Shakiness" mit einem Anruf.) Hohe Jitter-Werte werden in der Regel durch Überlastung oder einen überladenen Medienserver verursacht und zu Audio verzerrt oder verloren.  <br/> |
|**RoundTrip** <br/> |int  <br/> ||Die durchschnittliche Zeit (in Millisekunden), die ein RTP-Paket (Real-Time Transport-Protokoll) benötigt, um zu einem anderen Endpunkt und wieder zurück zu gelangen. Eine Roundtripzeit von 200 ms oder weniger gilt als akzeptable Qualität.  <br/> Hohe Roundtripwerte können durch internationale Anrufweiterleitung, eine falsche Routingkonfiguration oder einen überlasteten Medienserver verursacht werden. Sie führen zu Problemen bei bidirektionalen Echtzeit-Audiounterhaltungen.  <br/> |
|**RoundTripMax** <br/> |int  <br/> ||Maximale Zeitraum (in Millisekunden) für eine Real-Time Transport Protocol-Pakets mit einem anderen Endpunkt Reisen und dann wieder erforderlich ist. Eine Roundtripzeit von 200 ms oder weniger gilt als akzeptable Qualität.  <br/> Hohe Roundtripwerte können durch internationale Anrufweiterleitung, eine falsche Routingkonfiguration oder einen überlasteten Medienserver verursacht werden. Sie führen zu Problemen bei bidirektionalen Echtzeit-Audiounterhaltungen.  <br/> |
|**PacketLossRate** <br/> |float  <br/> ||Die durchschnittliche Rate an RTP-Paketverlusten (Real-Time Transport-Protokoll; ein Protokoll für die Übertragung von Audio und Video über das Internet). Zu Paketverlusten kommt es, wenn RTP-Pakete ihr Ziel nicht erreichen. Hohe Verlustraten werden allgemein durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver verursacht. Paketverluste führen in der Regel zu verzerrter oder unterbrochener Sprachübertragung.  <br/> |
|**PacketLossRateMax** <br/> |float  <br/> ||Maximale Rate von Paketverlusten RTP (Real-Time Transport Protocol). (Paketverlust tritt auf, wenn RTP-Pakete, ein Protokoll für die Übertragung von Audio- und Videodaten über das Internet zu ihren Zielen ist fehlgeschlagen.) Hohe Paketverlust sind in der Regel durch eine Überlastung verursacht. Fehlende Bandbreite; Drahtlose Überlastung oder Störungen; oder einen überladenen Medienserver. Paketverluste führen in der Regel zu verzerrter oder unterbrochener Sprachübertragung.  <br/> |
|**PacketUtilization** <br/> |int  <br/> ||Anzahl der gesendeten Pakete.  <br/> |
|**BandwidthEst** <br/> |int  <br/> ||Geschätzte unidirektionale verfügbare Bandbreite am Ende der Sitzung. In Bits pro Sekunde gemeldet.  <br/> |
|**AppSharingPayloadDescription** <br/> |int  <br/> ||Beschreibung der Anwendungsfreigabe-Nutzlast.  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||Die Gesamtmenge des unidirektionalen Wartezeit. Relative unidirektionale Wartezeit misst die Verzögerung zwischen dem Client und dem Server.  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||Durchschnittliche Dauer der unidirektionalen Wartezeit. Relative unidirektionale Wartezeit misst die Verzögerung zwischen dem Client und dem Server.  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||Maximale Größe des unidirektionalen Wartezeit. Relative unidirektionale Wartezeit misst die Verzögerung zwischen dem Client und dem Server.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||Insgesamt unidirektionale Bursts vorkommen. Eine "bursty" Übertragung ist eine Übertragung, in dem Daten in unvorhersehbare Bursts im Gegensatz zu einem kontinuierlichen Datenstrom fließt. Diese Metrik misst Datenfluss zwischen dem Client und dem Server.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |float  <br/> ||Insgesamt unidirektionale Bursts Dichte. Eine "bursty" Übertragung ist eine Übertragung, in dem Daten in unvorhersehbare Bursts im Gegensatz zu einem kontinuierlichen Datenstrom fließt. Diese Metrik misst Datenfluss zwischen dem Client und dem Server.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||Insgesamt unidirektionale Bursts Dauer. Eine "bursty" Übertragung ist eine Übertragung, in dem Daten in unvorhersehbare Bursts im Gegensatz zu einem kontinuierlichen Datenstrom fließt. Diese Metrik misst Datenfluss zwischen dem Client und dem Server.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||Unidirektionale lückenvorkommen insgesamt. Eine "bursty" Übertragung ist eine Übertragung, in dem Daten in unvorhersehbare Bursts im Gegensatz zu einem kontinuierlichen Datenstrom fließt. Geben Sie Lücken Verzögerungen zwischen diesen Bursts an. Diese Metrik misst Datenfluss zwischen dem Client und dem Server.  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||Unidirektionale lückendichte insgesamt. Eine "bursty" Übertragung ist eine Übertragung, in dem Daten in unvorhersehbare Bursts im Gegensatz zu einem kontinuierlichen Datenstrom fließt. Geben Sie Lücken Verzögerungen zwischen diesen Bursts an. Diese Metrik misst Datenfluss zwischen dem Client und dem Server.  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||Unidirektionale lückendauer insgesamt. Eine "bursty" Übertragung ist eine Übertragung, in dem Daten in unvorhersehbare Bursts im Gegensatz zu einem kontinuierlichen Datenstrom fließt. Geben Sie Lücken Verzögerungen zwischen diesen Bursts an. Diese Metrik misst Datenfluss zwischen dem Client und dem Server.  <br/> |
|**ApplicationSharingType** <br/> |Varchar(256)-Wert  <br/> ||Geben Sie Anwendungsrolle (freigebender Benutzer oder Betrachter) und Inhalte.  <br/> |
|**RDPTileProcessingLatencyTotal** <br/> |float  <br/> ||Gesamtanzahl der Verarbeitungszeit für Remotedesktopprotokoll (RDP) Kacheln. Höhere insgesamt entspricht eine längere Verzögerung in die Anzeigequalität.  <br/> |
|**RDPTileProcessingLatencyAverage** <br/> |float  <br/> ||Durchschnittliche Verarbeitungszeit für Remotedesktopprotokoll (RDP) Kacheln. Höhere insgesamt entspricht eine längere Verzögerung in die Anzeigequalität.  <br/> |
|**RDPTileProcessingLatencyMax** <br/> |float  <br/> ||Maximale Verarbeitungszeit für Remotedesktopprotokoll (RDP) Kacheln. Höhere insgesamt entspricht eine längere Verzögerung in die Anzeigequalität.  <br/> |
|**RDPTileProcessingLatencyBurstOccurrences** <br/> |int  <br/> ||Burstvorkommen Sie in der Verarbeitungszeit für Remotedesktopprotokoll (RDP) Kacheln. Eine "bursty" Übertragung ist eine Übertragung, in dem Daten in unvorhersehbare Bursts im Gegensatz zu einem kontinuierlichen Datenstrom fließt.  <br/> |
|**RDPTileProcessingLatencyBurstDensity** <br/> |float  <br/> ||Burstdichte in der Verarbeitungszeit für Remotedesktopprotokoll (RDP) Kacheln. Eine "bursty" Übertragung ist eine Übertragung, in dem Daten in unvorhersehbare Bursts im Gegensatz zu einem kontinuierlichen Datenstrom fließt.  <br/> |
|**RDPTileProcessingLatencyBurstDuration** <br/> |float  <br/> ||Burstdauer in der Verarbeitungszeit für Remotedesktopprotokoll (RDP) Kacheln. Eine "bursty" Übertragung ist eine Übertragung, in dem Daten in unvorhersehbare Bursts im Gegensatz zu einem kontinuierlichen Datenstrom fließt.  <br/> |
|**RDPTileProcessingLatencyGapOccurrences** <br/> |int  <br/> ||Lückenvorkommen in der Verarbeitungszeit für Remotedesktopprotokoll (RDP) Kacheln.  <br/> |
|**RDPTileProcessingLatencyGapDensity** <br/> |float  <br/> ||Lückendichte in der Verarbeitungszeit für Remotedesktopprotokoll (RDP) Kacheln. Niedrige lückendichte entspricht eine bessere Wiedergabe wünschen.  <br/> |
|**RDPTileProcessingLatencyGapDuration** <br/> |float  <br/> ||Lückendauer in der Verarbeitungszeit für Remotedesktopprotokoll (RDP) Kacheln. Kurze Lücke Dauer entsprechen den eine bessere Wiedergabe wünschen.  <br/> |
|**CaptureTileRateTotal** <br/> |float  <br/> ||Gesamtrate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).  <br/> |
|**CaptureTileRateAverage** <br/> |float  <br/> ||Durchschnittliche Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).  <br/> |
|**CaptureTileRateMax** <br/> |float  <br/> ||Maximale Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).  <br/> |
|**CaptureTileRateBurstOccurrences** <br/> |int  <br/> ||Burstvorkommen Sie in der Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).  <br/> |
|**CaptureTileRateBurstDensity** <br/> |float  <br/> ||Burstdichte in der Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).  <br/> |
|**CaptureTileRateBurstDuration** <br/> |float  <br/> ||Burstdauer in der Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).  <br/> |
|**CaptureTileRateGapOccurrences** <br/> |int  <br/> ||Lückenvorkommen in der Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).  <br/> |
|**CaptureTileRateGapDensity** <br/> |float  <br/> ||Lückendichte in der Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).  <br/> |
|**CaptureTileRateGapDuration** <br/> |float  <br/> ||Lückendauer in der Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).  <br/> |
|**SpoiledTilePercentTotal** <br/> |float  <br/> ||Gesamtprozentsatz des Inhalts, der der nicht angezeigt, aber wurde stattdessen verworfen und durch neuen Inhalt überschrieben.  <br/> |
|**SpoiledTilePercentAverage** <br/> |float  <br/> ||Durchschnittliche Prozentsatz des Inhalts, der der nicht angezeigt, aber wurde stattdessen verworfen und durch neuen Inhalt überschrieben.  <br/> |
|**SpoiledTilePercentMax** <br/> |float  <br/> ||Maximaler Prozentsatz des Inhalts, der der nicht angezeigt, aber wurde stattdessen verworfen und durch neuen Inhalt überschrieben.  <br/> |
|**SpoiledTilePercentBurstOccurrences** <br/> |int  <br/> ||Burstvorkommen Sie für den Inhalt, der der nicht angezeigt, aber wurde stattdessen verworfen und durch neuen Inhalt überschrieben.  <br/> |
|**SpoiledTilePercentBurstDensity** <br/> |float  <br/> ||Burstdichte für den Inhalt, der der nicht angezeigt, aber wurde stattdessen verworfen und durch neuen Inhalt überschrieben.  <br/> |
|**SpoiledTilePercentBurstDuration** <br/> |float  <br/> ||Burstdauer für den Inhalt, der der nicht angezeigt, aber wurde stattdessen verworfen und durch neuen Inhalt überschrieben.  <br/> |
|**SpoiledTilePercentGapOccurrences** <br/> |int  <br/> ||Lückenvorkommen für den Inhalt, der der nicht angezeigt, aber wurde stattdessen verworfen und durch neuen Inhalt überschrieben.  <br/> |
|**SpoiledTilePercentGapDensity** <br/> |float  <br/> ||Lückendichte für den Inhalt, der der nicht angezeigt, aber wurde stattdessen verworfen und durch neuen Inhalt überschrieben.  <br/> |
|**SpoiledTilePercentGapDuration** <br/> |float  <br/> ||Lückendauer für den Inhalt, der der nicht angezeigt, aber wurde stattdessen verworfen und durch neuen Inhalt überschrieben.  <br/> |
|**ScrapingFrameRateTotal** <br/> |float  <br/> ||Gesamtanzahl der scrapingframes aus der grafikquelle.  <br/> |
|**ScrapingFrameRateAverage** <br/> |float  <br/> ||Durchschnittliche Anzahl der scrapingframes aus der grafikquelle.  <br/> |
|**ScrapingFrameRateMax** <br/> |float  <br/> ||Maximale Anzahl der scrapingframes aus der grafikquelle.  <br/> |
|**ScrapingFrameRateBurstOccurrences** <br/> |int  <br/> ||Burstvorkommen Sie in den scrapingframes aus der grafikquelle.  <br/> |
|**ScrapingFrameRateBurstDensity** <br/> |float  <br/> ||Burstdichte in den scrapingframes aus der grafikquelle.  <br/> |
|**ScrapingFrameRateBurstDuration** <br/> |float  <br/> ||Burstdauer in den scrapingframes aus der grafikquelle.  <br/> |
|**ScrapingFrameRateGapOccurrences** <br/> |int  <br/> ||Lückenvorkommen in den scrapingframes aus der grafikquelle.  <br/> |
|**ScrapingFrameRateGapDensity** <br/> |float  <br/> ||Lückendichte in den scrapingframes aus der grafikquelle.  <br/> |
|**ScrapingFrameRateGapDuration** <br/> |float  <br/> ||Lückendauer in den scrapingframes aus der grafikquelle.  <br/> |
|**IncomingTileRateTotal** <br/> |float  <br/> ||Rate eingehender Frames insgesamt, wie vom Betrachter empfangen.  <br/> |
|**IncomingTileRateAverage** <br/> |float  <br/> ||Durchschnittliche Rate eingehender Frames als vom Betrachter empfangen werden.  <br/> |
|**IncomingTileRateMax** <br/> |float  <br/> ||Maximale durchschnittliche Rate eingehender Kacheln vom Betrachter empfangen.  <br/> |
|**IncomingTileRateBurstOccurrences** <br/> |int  <br/> ||Burstvorkommen Sie in der Rate eingehender Kacheln vom Betrachter empfangen.  <br/> |
|**IncomingTileRateBurstDensity** <br/> |float  <br/> ||Burstdichte in der Rate eingehender Kacheln vom Betrachter empfangen.  <br/> |
|**IncomingTileRateBurstDuration** <br/> |float  <br/> ||Burstdauer in der Rate eingehender Kacheln vom Betrachter empfangen.  <br/> |
|**IncomingTileRateGapOccurrences** <br/> |int  <br/> ||Lückenvorkommen in der Rate eingehender Kacheln als vom Betrachter empfangen werden.  <br/> |
|**IncomingTileRateGapDensity** <br/> |float  <br/> ||Lückendichte in der Rate eingehender Kacheln als vom Betrachter empfangen werden.  <br/> |
|**IncomingTileRateGapDuration** <br/> |float  <br/> ||Lückendauer in der Rate eingehender Kacheln als vom Betrachter empfangen werden.  <br/> |
|**IncomingFrameRateTotal** <br/> |float  <br/> ||Rate eingehender Frames insgesamt, wie vom Betrachter empfangen.  <br/> |
|**IncomingFrameRateAverage** <br/> |float  <br/> ||Durchschnittliche Rate eingehender Frames als vom Betrachter empfangen werden.  <br/> |
|**IncomingFrameRateMax** <br/> |float  <br/> ||Maximale Rate eingehender Frames als vom Betrachter empfangen werden.  <br/> |
|**IncomingFrameRateBurstOccurrences** <br/> |int  <br/> ||Burstvorkommen Sie in der Rate eingehender Frames vom Betrachter empfangen.  <br/> |
|**IncomingFrameRateBurstDensity** <br/> |float  <br/> ||Burstdichte in der Rate eingehender Frames vom Betrachter empfangen.  <br/> |
|**IncomingFrameRateBurstDuration** <br/> |float  <br/> ||Burstdauer in der Rate eingehender Frames vom Betrachter empfangen.  <br/> |
|**IncomingFrameRateGapOccurrences** <br/> |int  <br/> ||Lückenvorkommen in der Rate eingehender Frames als vom Betrachter empfangen werden.  <br/> |
|**IncomingFrameRateGapDensity** <br/> |float  <br/> ||Lückendichte in der Rate eingehender Frames als vom Betrachter empfangen werden.  <br/> |
|**IncomingFrameRateDuration** <br/> |float  <br/> ||Lückendauer in der Rate eingehender Frames als vom Betrachter empfangen werden.  <br/> |
|**OutgoingTileRateTotal** <br/> |float  <br/> ||Insgesamt Rate ausgehender Kacheln für den Absender.  <br/> |
|**OutgoingTileRateAverage** <br/> |float  <br/> ||Durchschnittliche Rate ausgehender Kacheln für den Absender.  <br/> |
|**OutgoingTileRateMax** <br/> |float  <br/> ||Maximale Rate ausgehender Kacheln für den Absender.  <br/> |
|**OutgoingTileRateBurstOccurrences** <br/> |int  <br/> ||Burstvorkommen Sie in der Rate ausgehender Kacheln für den Absender.  <br/> |
|**OutgoingTileRateBurstDensity** <br/> |float  <br/> ||Burstdichte in der Rate ausgehender Kacheln für den Absender.  <br/> |
|**OutgoingTileRateBurstDuration** <br/> |float  <br/> ||Burstdauer in der Rate ausgehender Kacheln für den Absender.  <br/> |
|**OutgoingTileRateGapOccurrences** <br/> |int  <br/> ||Lückenvorkommen in der Rate ausgehender Kacheln für den Absender.  <br/> |
|**OutgoingTileRateGapDensity** <br/> |float  <br/> ||Lückendichte in der Rate ausgehender Kacheln für den Absender.  <br/> |
|**OutgoingTileRateGapDuration** <br/> |float  <br/> ||Lückendauer in der Rate ausgehender Kacheln für den Absender.  <br/> |
|**OutgoingFrameRateTotal** <br/> |float  <br/> ||Insgesamt Rate ausgehender Frames für den Absender.  <br/> |
|**OutgoingFrameRateAverage** <br/> |float  <br/> ||Durchschnittliche Rate ausgehender Frames für den Absender.  <br/> |
|**OutgoingFrameRateMax** <br/> |float  <br/> ||Maximale Rate ausgehender Frames für den Absender.  <br/> |
|**OutgoingFrameRateBurstOccurrences** <br/> |int  <br/> ||Burstvorkommen Sie in der Rate ausgehender Frames für den Absender.  <br/> |
|**OutgoingFrameRateBurstDensity** <br/> |float  <br/> ||Burstdichte in der Rate ausgehender Frames für den Absender.  <br/> |
|**OutgoingFrameRateBurstDuration** <br/> |float  <br/> ||Burstdauer in der Rate ausgehender Frames für den Absender.  <br/> |
|**OutgoingFrameRateGapOccurrences** <br/> |int  <br/> ||Lückenvorkommen in der Rate ausgehender Frames für den Absender.  <br/> |
|**OutgoingFrameRateGapDensity** <br/> |float  <br/> ||Lückendichte in der Rate ausgehender Frames für den Absender.  <br/> |
|**OutgoingFrameRateGapDuration** <br/> |float  <br/> ||Lückendauer in der Rate ausgehender Frames für den Absender.  <br/> |
|**AverageRectangleHeight** <br/> |int  <br/> ||Durchschnittliche Höhe der videoauflösung in Pixeln an.  <br/> |
|**AverageRectangleWidth** <br/> |int  <br/> ||Durchschnittliche Breite der videoauflösung in Pixeln an.  <br/> |
|**Eingehend** <br/> |bit  <br/> ||Durchschnittliche Framerate (in Frames pro Sekunde) für eingehende Übertragungen.  <br/> |
|**Ausgehend** <br/> |bit  <br/> ||Durchschnittliche Framerate (in Frames pro Sekunde) für ausgehende Übertragungen.  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> ||1 bedeutet, dass die streamrichtung vom Anrufer zum angerufenen verläuft.  <br/> 0 bedeutet, dass die streamrichtung vom angerufenen zum Anrufer verläuft.  <br/> |
   

