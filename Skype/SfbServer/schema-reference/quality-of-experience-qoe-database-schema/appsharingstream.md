---
title: AppSharingStream-Tabelle
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 391490cb-d7b8-44ca-b4d1-429600da909c
description: Die AppSharingStream-Tabelle enthält Metriken zur Qualität der Benutzererfahrung für die Netzwerkdatenströme, die für die Anwendungsfreigabe verwendet werden. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: d95e0d78175f8e17363dc558d82cafefba36ce28
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120877"
---
# <a name="appsharingstream-table"></a>AppSharingStream-Tabelle
 
Die AppSharingStream-Tabelle enthält Metriken zur Qualität der Benutzererfahrung für die Netzwerkdatenströme, die für die Anwendungsfreigabe verwendet werden. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Key/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |dateTime  <br/> |Primär, Fremd  <br/> |Datum und Uhrzeit des Sitzungsbeginns.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primär, Fremd  <br/> |Sequenzielle ID, anhand der zwischen Sitzungen unterschieden wird, die an denselben Tag und zur derselben Uhrzeit gestartet wurden.  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primär, Fremd  <br/> | Weitere Informationen finden Sie unter [MediaLine Table](./medialine-0.md). <br/> |
|**StreamID** <br/> |int  <br/> |Primary  <br/> |Eindeutige ID des Anwendungsfreigabe-Datenstroms.  <br/> |
|**JitterInterArrival** <br/> |int  <br/> ||Der durchschnittliche Jitter, der zwischen dem Eintreffen von RTP-Paketen ermittelt wurde. (Jitter ist ein Maß für das "Zittern" der Übertragung während eines Anrufs.) Hohe Jitterwerte werden in der Regel durch Überlastung oder einen überlasteten Medienserver verursacht und führen zu verzerrter oder unterbrochener Sprachübertragung.  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> ||Der maximale Jitter, der zwischen dem Eintreffen von RTP-Paketen ermittelt wurde. (Jitter ist ein Maß für das "Zittern" der Übertragung während eines Anrufs.) Hohe Jitterwerte werden in der Regel durch Überlastung oder einen überlasteten Medienserver verursacht und führen zu verzerrter oder unterbrochener Sprachübertragung.  <br/> |
|**RoundTrip** <br/> |int  <br/> ||Die durchschnittliche Zeit (in Millisekunden), die ein RTP-Paket (Real-Time Transport-Protokoll) benötigt, um zu einem anderen Endpunkt und wieder zurück zu gelangen. Eine Roundtripzeit von 200 ms oder weniger gilt als akzeptable Qualität.  <br/> Hohe Roundtripwerte können durch internationale Anrufweiterleitung, eine falsche Routingkonfiguration oder einen überlasteten Medienserver verursacht werden. Sie führen zu Problemen bei bidirektionalen Echtzeit-Audiounterhaltungen.  <br/> |
|**RoundTripMax** <br/> |int  <br/> ||Die maximale Zeit (in Millisekunden), die ein RTP-Paket (Real-Time Transport Protocol) benötigt, um zu einem anderen Endpunkt und wieder zurück zu gelangen. Eine Roundtripzeit von 200 ms oder weniger gilt als akzeptable Qualität.  <br/> Hohe Roundtripwerte können durch internationale Anrufweiterleitung, eine falsche Routingkonfiguration oder einen überlasteten Medienserver verursacht werden. Sie führen zu Problemen bei bidirektionalen Echtzeit-Audiounterhaltungen.  <br/> |
|**PacketLossRate** <br/> |Gleitkommazahl  <br/> ||Die durchschnittliche Rate an RTP-Paketverlusten (Real-Time Transport-Protokoll; ein Protokoll für die Übertragung von Audio und Video über das Internet). Zu Paketverlusten kommt es, wenn RTP-Pakete ihr Ziel nicht erreichen. Hohe Verlustraten werden allgemein durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver verursacht. Paketverluste führen in der Regel zu verzerrter oder unterbrochener Sprachübertragung.  <br/> |
|**PacketLossRateMax** <br/> |Gleitkommazahl  <br/> ||Die maximale Rate an RTP-Paketverlusten (Real-Time Transport-Protokoll). Zu Paketverlusten kommt es, wenn RTP-Pakete ihr Ziel nicht erreichen. Hohe Verlustraten werden allgemein durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver verursacht. Paketverluste führen in der Regel zu verzerrter oder unterbrochener Sprachübertragung.  <br/> |
|**PacketUtilization** <br/> |int  <br/> ||Die Anzahl der gesendeten Pakete.  <br/> |
|**BandwidthEst** <br/> |int  <br/> ||Die geschätzte unidirektionale Bandbreite, die am Ende der Sitzung verfügbar ist (in Bits pro Sekunde).  <br/> |
|**AppSharingPayloadDescription** <br/> |int  <br/> ||Beschreibung der Anwendungsfreigabe-Nutzlast.  <br/> |
|**RelativeOneWayTotal** <br/> |Gleitkommazahl  <br/> ||Gesamter Umfang der unidirektionalen Latenz. Die relative unidirektionale Latenz misst die Verzögerung zwischen Client und Server.  <br/> |
|**RelativeOneWayAverage** <br/> |Gleitkommazahl  <br/> ||Durchschnittlicher Umfang der unidirektionalen Latenz. Die relative unidirektionale Latenz misst die Verzögerung zwischen Client und Server.  <br/> |
|**RelativeOneWayMax** <br/> |Gleitkommazahl  <br/> ||Maximaler Umfang der unidirektionalen Latenz. Die relative unidirektionale Latenz misst die Verzögerung zwischen Client und Server.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||Undirektionale Burstvorkommen insgesamt. Bei einer "bursty"-Übertragung handelt es sich um eine Übertragung, bei der Daten in unvorhersehbaren Bursts fließen und nicht in einem konstanten Datenstrom. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |Gleitkommazahl  <br/> ||Undirektionale Burstdichte insgesamt. Bei einer "bursty"-Übertragung handelt es sich um eine Übertragung, bei der Daten in unvorhersehbaren Bursts fließen und nicht in einem konstanten Datenstrom. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |Gleitkommazahl  <br/> ||Undirektionale Burstdauer insgesamt. Bei einer "bursty"-Übertragung handelt es sich um eine Übertragung, bei der Daten in unvorhersehbaren Bursts fließen und nicht in einem konstanten Datenstrom. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||Gesamt vorkommende Einweglücken. Bei einer "bursty"-Übertragung handelt es sich um eine Übertragung, bei der Daten in unvorhersehbaren Bursts und nicht in einem konstanten Datenstrom fließen. Lücken deuten auf Verzögerungen zwischen diesen Bursts hin. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.  <br/> |
|**RelativeOneWayGapDensity** <br/> |Gleitkommazahl  <br/> ||Gesamtdichte der einwegspalten. Bei einer "bursty"-Übertragung handelt es sich um eine Übertragung, bei der Daten in unvorhersehbaren Bursts und nicht in einem konstanten Datenstrom fließen. Lücken deuten auf Verzögerungen zwischen diesen Bursts hin. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.  <br/> |
|**RelativeOneWayGapDuration** <br/> |Gleitkommazahl  <br/> ||Gesamt one-way gap duration. Bei einer "bursty"-Übertragung handelt es sich um eine Übertragung, bei der Daten in unvorhersehbaren Bursts und nicht in einem konstanten Datenstrom fließen. Lücken deuten auf Verzögerungen zwischen diesen Bursts hin. Diese Metrik misst den Datenfluss zwischen dem Client und dem Server.  <br/> |
|**ApplicationSharingType** <br/> |varChar(256)  <br/> ||Anwendungsrolle (Freigebender Benutzer oder Betrachter) und Inhaltstyp.  <br/> |
|**RDPTileProcessingLatencyTotal** <br/> |Gleitkommazahl  <br/> ||Gesamte Verarbeitungszeit für Remotedesktopprotokoll-Kacheln (RDP). Je höher der Gesamtwert, desto länger die Verzögerung bei der Wiedergabe.  <br/> |
|**RDPTileProcessingLatencyAverage** <br/> |Gleitkommazahl  <br/> ||Durchschnittliche Verarbeitungszeit für Remotedesktopprotokoll-Kacheln (RDP). Je höher der Gesamtwert, desto länger die Verzögerung bei der Wiedergabe.  <br/> |
|**RDPTileProcessingLatencyMax** <br/> |Gleitkommazahl  <br/> ||Maximale Verarbeitungszeit für Remotedesktopprotokoll-Kacheln (RDP). Je höher der Gesamtwert, desto länger die Verzögerung bei der Wiedergabe.  <br/> |
|**RDPTileProcessingLatencyBurstOccurrences** <br/> |int  <br/> ||Burstvorkommen in der Verarbeitungszeit für Remotedesktopprotokoll-Kacheln (RDP). Bei einer "bursty"-Übertragung handelt es sich um eine Übertragung, bei der Daten in unvorhersehbaren Bursts fließen und nicht in einem konstanten Datenstrom.  <br/> |
|**RDPTileProcessingLatencyBurstDensity** <br/> |Gleitkommazahl  <br/> ||Burstdichte in der Verarbeitungszeit für Remotedesktopprotokoll-Kacheln (RDP). Bei einer "bursty"-Übertragung handelt es sich um eine Übertragung, bei der Daten in unvorhersehbaren Bursts fließen und nicht in einem konstanten Datenstrom.  <br/> |
|**RDPTileProcessingLatencyBurstDuration** <br/> |Gleitkommazahl  <br/> ||Burstdauer in der Verarbeitungszeit für Remotedesktopprotokoll-Kacheln (RDP). Bei einer "bursty"-Übertragung handelt es sich um eine Übertragung, bei der Daten in unvorhersehbaren Bursts fließen und nicht in einem konstanten Datenstrom.  <br/> |
|**RDPTileProcessingLatencyGapOccurrences** <br/> |int  <br/> ||Lückenvorkommen in der Verarbeitungszeit für Remotedesktopprotokoll-Kacheln (RDP).  <br/> |
|**RDPTileProcessingLatencyGapDensity** <br/> |Gleitkommazahl  <br/> ||Lückendichte in der Verarbeitungszeit für Remotedesktopprotokoll-Kacheln (RDP). Je geringer die Lückendichte, desto besser das Wiedergabeerlebnis.  <br/> |
|**RDPTileProcessingLatencyGapDuration** <br/> |Gleitkommazahl  <br/> ||Lückendauer in der Verarbeitungszeit für Remotedesktopprotokoll-Kacheln (RDP). Je kürzer die Lückendauer, desto besser das Wiedergabeerlebnis.  <br/> |
|**CaptureTileRateTotal** <br/> |Gleitkommazahl  <br/> ||Gesamtrate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).  <br/> |
|**CaptureTileRateAverage** <br/> |Gleitkommazahl  <br/> ||Durchschnittliche Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).  <br/> |
|**CaptureTileRateMax** <br/> |Gleitkommazahl  <br/> ||Maximale Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).  <br/> |
|**CaptureTileRateBurstOccurrences** <br/> |int  <br/> ||Burstvorkommen in der Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).  <br/> |
|**CaptureTileRateBurstDensity** <br/> |Gleitkommazahl  <br/> ||Burstdichte in der Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).  <br/> |
|**CaptureTileRateBurstDuration** <br/> |Gleitkommazahl  <br/> ||Burstdauer in der Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).  <br/> |
|**CaptureTileRateGapOccurrences** <br/> |int  <br/> ||Lückenvorkommen in der Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).  <br/> |
|**CaptureTileRateGapDensity** <br/> |Gleitkommazahl  <br/> ||Lückendichte in der Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).  <br/> |
|**CaptureTileRateGapDuration** <br/> |Gleitkommazahl  <br/> ||Lückendauer in der Rate der aufgezeichneten Kacheln (in Kacheln pro Sekunde).  <br/> |
|**SpoiledTilePercentTotal** <br/> |Gleitkommazahl  <br/> ||Gesamtprozentsatz des Inhalts, der nicht angezeigt, sondern stattdessen verworfen und durch aktuellen Inhalt überschrieben wurde.  <br/> |
|**SpoiledTilePercentAverage** <br/> |Gleitkommazahl  <br/> ||Durchschnittlicher Prozentsatz des Inhalts, der nicht angezeigt, sondern stattdessen verworfen und durch aktuellen Inhalt überschrieben wurde.  <br/> |
|**SpoiledTilePercentMax** <br/> |Gleitkommazahl  <br/> ||Maximaler Prozentsatz des Inhalts, der nicht angezeigt, sondern stattdessen verworfen und durch aktuellen Inhalt überschrieben wurde.  <br/> |
|**SpoiledTilePercentBurstOccurrences** <br/> |int  <br/> ||Burstvorkommen für den Inhalt, der nicht angezeigt, sondern stattdessen verworfen und durch aktuellen Inhalt überschrieben wurde.  <br/> |
|**SpoiledTilePercentBurstDensity** <br/> |Gleitkommazahl  <br/> ||Burstdichte für den Inhalt, der nicht angezeigt, sondern stattdessen verworfen und durch neuen Inhalt überschrieben wurde.  <br/> |
|**SpoiledTilePercentBurstDuration** <br/> |Gleitkommazahl  <br/> ||Burstdauer für den Inhalt, der nicht angezeigt, sondern stattdessen verworfen und durch neuen Inhalt überschrieben wurde.  <br/> |
|**SpoiledTilePercentGapOccurrences** <br/> |int  <br/> ||Lückenvorkommen für den Inhalt, der nicht angezeigt, sondern stattdessen verworfen und durch neuen Inhalt überschrieben wurde.  <br/> |
|**SpoiledTilePercentGapDensity** <br/> |Gleitkommazahl  <br/> ||Lückendichte für den Inhalt, der nicht angezeigt, sondern stattdessen verworfen und durch neuen Inhalt überschrieben wurde.  <br/> |
|**SpoiledTilePercentGapDuration** <br/> |Gleitkommazahl  <br/> ||Lückendauer für den Inhalt, der nicht angezeigt, sondern stattdessen verworfen und durch neuen Inhalt überschrieben wurde.  <br/> |
|**ScrapingFrameRateTotal** <br/> |Gleitkommazahl  <br/> ||Gesamtanzahl der Scrapingframes aus der Grafikquelle.  <br/> |
|**ScrapingFrameRateAverage** <br/> |Gleitkommazahl  <br/> ||Durchschnittliche Anzahl der Scrapingframes aus der Grafikquelle.  <br/> |
|**ScrapingFrameRateMax** <br/> |Gleitkommazahl  <br/> ||Maximale Anzahl der Scrapingframes aus der Grafikquelle.  <br/> |
|**ScrapingFrameRateBurstOccurrences** <br/> |int  <br/> ||Burstvorkommen in den Scrapingframes aus der Grafikquelle.  <br/> |
|**ScrapingFrameRateBurstDensity** <br/> |Gleitkommazahl  <br/> ||Burstdichte in den Scrapingframes aus der Grafikquelle.  <br/> |
|**ScrapingFrameRateBurstDuration** <br/> |Gleitkommazahl  <br/> ||Burstdauer in den Scrapingframes aus der Grafikquelle.  <br/> |
|**ScrapingFrameRateGapOccurrences** <br/> |int  <br/> ||Lückenvorkommen in den Scrapingframes aus der Grafikquelle.  <br/> |
|**ScrapingFrameRateGapDensity** <br/> |Gleitkommazahl  <br/> ||Lückendichte in den Scrapingframes aus der Grafikquelle.  <br/> |
|**ScrapingFrameRateGapDuration** <br/> |Gleitkommazahl  <br/> ||Lückendauer in den Scrapingframes aus der Grafikquelle.  <br/> |
|**IncomingTileRateTotal** <br/> |Gleitkommazahl  <br/> ||Rate eingehender Frames insgesamt, die vom Betrachter empfangen werden.  <br/> |
|**IncomingTileRateAverage** <br/> |Gleitkommazahl  <br/> ||Durchschnittliche Rate eingehender Frames, die vom Betrachter empfangen werden.  <br/> |
|**IncomingTileRateMax** <br/> |Gleitkommazahl  <br/> ||Durchschnittliche Rate eingehender Kacheln, die vom Betrachter empfangen werden.  <br/> |
|**IncomingTileRateBurstOccurrences** <br/> |int  <br/> ||Burstvorkommen in der Rate eingehender Kacheln, die vom Betrachter empfangen werden.  <br/> |
|**IncomingTileRateBurstDensity** <br/> |Gleitkommazahl  <br/> ||Burstdichte in der Rate eingehender Kacheln, die vom Betrachter empfangen werden.  <br/> |
|**IncomingTileRateBurstDuration** <br/> |Gleitkommazahl  <br/> ||Burstdauer in der Rate eingehender Kacheln, die vom Betrachter empfangen werden.  <br/> |
|**IncomingTileRateGapOccurrences** <br/> |int  <br/> ||Lückenvorkommen in der Rate eingehender Kacheln, die vom Betrachter empfangen werden.  <br/> |
|**IncomingTileRateGapDensity** <br/> |Gleitkommazahl  <br/> ||Lückendichte in der Rate eingehender Kacheln, die vom Betrachter empfangen werden.  <br/> |
|**IncomingTileRateGapDuration** <br/> |Gleitkommazahl  <br/> ||Lückendauer in der Rate eingehender Kacheln, die vom Betrachter empfangen werden.  <br/> |
|**IncomingFrameRateTotal** <br/> |Gleitkommazahl  <br/> ||Rate eingehender Frames insgesamt, die vom Betrachter empfangen werden.  <br/> |
|**IncomingFrameRateAverage** <br/> |Gleitkommazahl  <br/> ||Durchschnittliche Rate eingehender Frames, die vom Betrachter empfangen werden.  <br/> |
|**IncomingFrameRateMax** <br/> |Gleitkommazahl  <br/> ||Durchschnittliche Rate eingehender Frames, die vom Betrachter empfangen werden.  <br/> |
|**IncomingFrameRateBurstOccurrences** <br/> |int  <br/> ||Burstvorkommen in der Rate eingehender Frames, die vom Betrachter empfangen werden.  <br/> |
|**IncomingFrameRateBurstDensity** <br/> |Gleitkommazahl  <br/> ||Burstdichte in der Rate eingehender Frames, die vom Betrachter empfangen werden.  <br/> |
|**IncomingFrameRateBurstDuration** <br/> |Gleitkommazahl  <br/> ||Burstdauer in der Rate eingehender Frames, die vom Betrachter empfangen werden.  <br/> |
|**IncomingFrameRateGapOccurrences** <br/> |int  <br/> ||Lückenvorkommen in der Rate eingehender Frames, die vom Betrachter empfangen werden.  <br/> |
|**IncomingFrameRateGapDensity** <br/> |Gleitkommazahl  <br/> ||Lückendichte in der Rate eingehender Frames, die vom Betrachter empfangen werden.  <br/> |
|**IncomingFrameRateDuration** <br/> |Gleitkommazahl  <br/> ||Lückendauer in der Rate eingehender Frames, die vom Betrachter empfangen werden.  <br/> |
|**OutgoingTileRateTotal** <br/> |Gleitkommazahl  <br/> ||Rate ausgehender Kacheln insgesamt für den Absender.  <br/> |
|**OutgoingTileRateAverage** <br/> |Gleitkommazahl  <br/> ||Durchschnittliche Rate ausgehender Kacheln für den Absender.  <br/> |
|**OutgoingTileRateMax** <br/> |Gleitkommazahl  <br/> ||Maximale Rate ausgehender Kacheln für den Absender.  <br/> |
|**OutgoingTileRateBurstOccurrences** <br/> |int  <br/> ||Burstvorkommen in der Rate ausgehender Kacheln für den Absender.  <br/> |
|**OutgoingTileRateBurstDensity** <br/> |Gleitkommazahl  <br/> ||Burstdichte in der Rate ausgehender Kacheln für den Absender.  <br/> |
|**OutgoingTileRateBurstDuration** <br/> |Gleitkommazahl  <br/> ||Burstdauer in der Rate ausgehender Kacheln für den Absender.  <br/> |
|**OutgoingTileRateGapOccurrences** <br/> |int  <br/> ||Lückenvorkommen in der Rate ausgehender Kacheln für den Absender.  <br/> |
|**OutgoingTileRateGapDensity** <br/> |Gleitkommazahl  <br/> ||Lückendichte in der Rate ausgehender Kacheln für den Absender.  <br/> |
|**OutgoingTileRateGapDuration** <br/> |Gleitkommazahl  <br/> ||Lückendauer in der Rate ausgehender Kacheln für den Absender.  <br/> |
|**OutgoingFrameRateTotal** <br/> |Gleitkommazahl  <br/> ||Rate ausgehender Frames insgesamt für den Absender.  <br/> |
|**OutgoingFrameRateAverage** <br/> |Gleitkommazahl  <br/> ||Durchschnittliche Rate ausgehender Frames für den Absender.  <br/> |
|**OutgoingFrameRateMax** <br/> |Gleitkommazahl  <br/> ||Maximale Rate ausgehender Frames für den Absender.  <br/> |
|**OutgoingFrameRateBurstOccurrences** <br/> |int  <br/> ||Burstvorkommen in der Rate ausgehender Frames für den Absender.  <br/> |
|**OutgoingFrameRateBurstDensity** <br/> |Gleitkommazahl  <br/> ||Burstdichte in der Rate ausgehender Frames für den Absender.  <br/> |
|**OutgoingFrameRateBurstDuration** <br/> |Gleitkommazahl  <br/> ||Burstdauer in der Rate ausgehender Frames für den Absender.  <br/> |
|**OutgoingFrameRateGapOccurrences** <br/> |int  <br/> ||Lückenvorkommen in der Rate ausgehender Frames für den Absender.  <br/> |
|**OutgoingFrameRateGapDensity** <br/> |Gleitkommazahl  <br/> ||Lückendichte in der Rate ausgehender Frames für den Absender.  <br/> |
|**OutgoingFrameRateGapDuration** <br/> |Gleitkommazahl  <br/> ||Lückendauer in der Rate ausgehender Frames für den Absender.  <br/> |
|**AverageRectangleHeight** <br/> |int  <br/> ||Durchschnittliche Höhe der Videoauflösung in Pixeln.  <br/> |
|**AverageRectangleWidth** <br/> |int  <br/> ||Durchschnittliche Breite der Videoauflösung in Pixeln.  <br/> |
|**Eingehendes** <br/> |bit  <br/> ||Durchschnittliche Framerate (in Frames pro Sekunde) für eingehende Übertragungen.  <br/> |
|**Ausgehend** <br/> |bit  <br/> ||Durchschnittliche Framerate (in Frames pro Sekunde) für ausgehende Übertragungen.  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> ||1 bedeutet, dass die Betrachter vom Anrufer zum Angerufenen verläuft.  <br/> 0 bedeutet, dass die Datenstromrichtung vom Angerufenen zum Anrufer verläuft.  <br/> |
