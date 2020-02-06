---
title: Mobilitäts Leistungsindikatoren in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d18ed85a-673d-4695-aa3f-ac83a38ab90a
description: 'Zusammenfassung: erfahren Sie mehr über die Leistungsindikatoren, die Sie zum Überwachen von Servern mit der Unified Communications Web-API (UCWA) und dem Skype for Business Server MCX-Mobilitätsdienst verwenden können.'
ms.openlocfilehash: e9a3ade40694ef18e1022388d48838822d409625
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817764"
---
# <a name="mobility-performance-counters-in-skype-for-business-server"></a>Mobilitäts Leistungsindikatoren in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über die Leistungsindikatoren, die Sie zum Überwachen von Servern mit der Unified Communications Web-API (UCWA) und dem Skype for Business Server MCX-Mobilitätsdienst verwenden können.
  
In den folgenden Tabellen sind die Namen und Beschreibungen der Leistungsindikatoren aufgeführt, die Sie zum Überwachen von Servern mit der Unified Communications Web-API (UCWA) und dem Skype for Business Server MCX-Mobilitätsdienst verwenden können. 
  
Der Kategorienname für die Indikatoren in der UCWA-Tabelle lautet **ls: Web-UCWA**.
  
Der Kategoriename für die Leistungsindikatoren in der Mcx-Mobilitätsdiensttabelle ist **LS:WEB - Mobile Communication Service**.

> [!NOTE]
> MCX (Mobility Service)-Unterstützung für ältere Mobile Clients steht in Skype for Business Server 2019 nicht mehr zur Verfügung. Alle derzeitigen mobilen Skype for Business-Clients verwenden bereits Unified Communications Web API (UCWA) zur Unterstützung von Instant Messaging (im), Anwesenheitsinformationen und Kontakten. Benutzer mit Legacy-Clients, die MCX verwenden, müssen ein Upgrade auf einen aktuellen Client durchführen.
  
## <a name="performance-counters-for-ucwa"></a>Leistungsindikatoren für UCWA

|Leistungsindikator|Beschreibung|
|:-----|:-----|
|Anzahl aktiver Anwendungen  <br/> |Die aktuelle Anzahl von Anwendungen.  <br/> |
|Anzahl der aktiven Anwendungsfreigabemodalitäten  <br/> |Die aktuelle Anzahl der Anwendungsfreigabemodalitäten.  <br/> |
|Anzahl der aktiven Audiomodalitäten  <br/> |Die aktuelle Anzahl der Audiomodalitäten.  <br/> |
|Anzahl der aktiven Datenzusammenarbeitsmodalitäten  <br/> |Die aktuelle Anzahl der Datenzusammenarbeitsmodalitäten.  <br/> |
|Wartezeit bei Active Directory-HD-Fotoabruf (ms)  <br/> |Dieser Leistungsindikator zeigt die durchschnittliche Zeit (in Millisekunden) zum Abrufen eines Fotos aus Active Directory an.  <br/> |
|Anzahl der aktiven Messaging-Modalitäten  <br/> |Die aktuelle Anzahl der Messaging-Modalitäten.  <br/> |
|Anzahl der aktiven Panoramavideomodalitäten  <br/> |Die aktuelle Anzahl der Panoramavideomodalitäten.  <br/> |
|Anzahl aktiver ausstehender GET-Anforderungen  <br/> |Die Anzahl der derzeit aktiven ausstehenden GET-Anforderungen; lange gehaltene Verbindungen mit dem Server.  <br/> |
|Anzahl aktiver Sitzungen  <br/> |Die aktuelle Gesamtzahl der Endpunkte, die in UCWA pro Anwendung registriert sind.  <br/> |
|Anzahl aktiver Benutzerinstanzen  <br/> |Die aktuelle Anzahl von Benutzerinstanzen.  <br/> |
|Aktive Benutzerinstanzen ohne Anwendung  <br/> |Die aktuelle Anzahl von Benutzerinstanzen ohne Anwendung.  <br/> |
|Anzahl der aktiven Videomodalitäten  <br/> |Die aktuelle Anzahl der Videomodalitäten.  <br/> |
|Empfangene Anwendungserstellungsanforderungen/Sekunde  <br/> |Die Rate der empfangenen Anwendungserstellungsanforderungen pro Sekunde.  <br/> |
|AS-MCU-Teilnahmefehler  <br/> |Die Anzahl der AS-MCU-Teilnahmefehler.  <br/> |
|Audio-Video-MCU-Teilnahmefehler  <br/> |Die Anzahl der Audio-Video-MCU-Teilnahmefehler.  <br/> |
|Durchschnittliche Anwendungsstartzeit (ms)  <br/> |Die durchschnittliche Anwendungsstartzeit in Millisekunden.  <br/> |
|Durchschnittliche Sitzungsdauer (ms)  <br/> |Die durchschnittliche Dauer einer Sitzung in Millisekunden.  <br/> |
|Daten-MCU-Teilnahmefehler  <br/> |Die Anzahl der Daten-MCU-Teilnahmefehler.  <br/> |
|Wartezeit bei Exchange-Kontaktsuche (ms)  <br/> |Dieser Leistungsindikator zeigt die durchschnittliche Zeit (in Millisekunden) bei der Suche eines Kontakts in Exchange an.  <br/> |
|Wartezeit bei Exchange-HD-Fotoabruf (ms)  <br/> |Dieser Leistungsindikator zeigt die durchschnittliche Zeit (in Millisekunden) zum Abrufen eines Fotos aus Exchange an.  <br/> |
|HTTP-4xx-Antworten/Sekunde  <br/> |Die Rate der Antworten mit dem HTTP-Code 4xx pro Sekunde.  <br/> |
|HTTP-5xx-Antworten/Sekunde  <br/> |Die Rate der Antworten mit dem HTTP-Code 5xx pro Sekunde.  <br/> |
|Chat-MCU-Teilnahmefehler  <br/> |Die Anzahl der Chat-MCU-Teilnahmefehler.  <br/> |
|Anzahl von Fehlern beim Abruf von Fotos aus Active Directory  <br/> |Die Gesamtzahl der Fehler beim Abrufen von Fotos aus Active Directory.  <br/> |
|Anzahl von Fehlern bei Kontaktsuche  <br/> |Die Gesamtzahl von Fehlern bei der Kontaktsuche in Exchange.  <br/> |
|Anzahl von Deserialisierungsfehlern  <br/> |Die Gesamtzahl der Deserialisierungsfehler.  <br/> |
|Anzahl der HD-fotofehler erhalten  <br/> |Die Gesamtzahl der Fehler beim Abrufen von HD-Fotos aus Exchange.  <br/> |
|Über Maximum an Abonnements pro Anwendung  <br/> |Die Anzahl der Abonnementanforderungen über der maximal pro Anwendung erlaubten Anzahl.  <br/> |
|Über Maximum an Abonnements pro Batch  <br/> |Die Anzahl der Abonnementanforderungen über der maximal pro Batch erlaubten Anzahl.  <br/> |
|Fehler beim Abonnieren der Anwesenheit  <br/> |Die Anzahl der Fehler beim Abonnieren der Anwesenheit.  <br/> |
|Fehler beim Registrieren von Endpunkten  <br/> |Die Anzahl der Fehler beim Registrieren von Endpunkten.  <br/> |
|Empfangene Anforderungen/Sekunde  <br/> |Die Anzahl der empfangenen Anforderungen pro Sekunde.  <br/> |
|Erfolgreiche Anforderungen/Sekunde  <br/> |Die Anzahl der erfolgreichen Anforderungen pro Sekunde (HTTP-Antwortcodes 2xx/3xx).  <br/> |
|Erfolgreiche Anwendungserstellungsanforderungen/Sekunde  <br/> |Die Rate der erfolgreichen Anwendungserstellungsanforderungen pro Sekunde.  <br/> |
|Anzahl der GET-Anforderungen mit Timeout  <br/> |Die Anzahl der ausstehenden GET-Anforderungen, bei denen das Zeitlimit überschritten wurde.  <br/> |
|Gesamtzahl der empfangenen Anwendungserstellungsanforderungen  <br/> |Die Gesamtzahl der Anwendungserstellungsanforderungen, die seit dem Start des Diensts empfangen wurden.  <br/> |
|Gesamtzahl der HTTP-4xx-Antworten  <br/> |Die Gesamtzahl der HTTP-Antworten vom Typ 4xx.  <br/> |
|Gesamtzahl der HTTP-5xx-Antworten  <br/> |Die Gesamtzahl der HTTP-Antworten vom Typ 5xx.  <br/> |
|Gesamtzahl der über den Befehlskanal empfangenen Anforderungen  <br/> |Die Gesamtzahl der über den Befehlskanal empfangenen Anforderungen.  <br/> |
|Gesamtzahl der erfolgreichen Anforderungen  <br/> |Die Gesamtzahl der erfolgreichen Anforderungen.  <br/> |
|Gesamtzahl der initiierten Sitzungen  <br/> |Die Gesamtzahl der Sitzungen, die seit dem Start des Diensts initiiert wurden.  <br/> |
|Gesamtzahl der Sitzungen, die aufgrund eines Leerlauftimeouts beendet wurden  <br/> |Die Gesamtzahl der Sitzungen, die beendet wurden, da das Leerlauftimeout des Benutzers erreicht wurde.  <br/> |
|Gesamtzahl der gedrosselten Anwendungen  <br/> |Die Anzahl der gedrosselten Anwendungen.  <br/> |
   
**Leistungsindikatoren für den Mcx-Mobilitätsdienst**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|Durchschnittliche Sitzungsdauer in Millisekunden  <br/> |Die durchschnittliche Dauer einer Sitzung in Millisekunden.  <br/> |
|Aktuelle Pushbenachrichtigungsabonnements  <br/> |Die aktuelle Anzahl von Pushbenachrichtigungsabonnements. Diese Anzahl in Verbindung mit „Anzahl derzeit aktiver Sitzungen“ stellt eine Teilmenge der derzeit aktiven Sitzungen dar, die für Windows Mobile- oder iPhone-Geräte registriert sind.  <br/> |
|Anzahl derzeit aktiver Netzwerkumfragen mit Timeout  <br/> |Die Anzahl von Netzwerkumfragen, bei denen ein Timeout aufgetreten ist.  <br/> |
|Anzahl derzeit aktiver Umfragen  <br/> |Die Anzahl von derzeit aktiven Umfragen (lange gehaltene Verbindungen mit dem Server).  <br/> |
|Anzahl derzeit aktiver Sitzungen  <br/> |Die derzeitige Anzahl der im Mobilitätsdienst registrierten Endpunkte.  <br/> |
|Anzahl derzeit aktiver Sitzungen mit aktiven Anwesenheitsabonnements  <br/> |Die Anzahl derzeit aktiver Sitzungen mit aktiven Anwesenheitsabonnements.  <br/> |
|Gescheiterte Pushbenachrichtigungsanforderungen/Sekunde  <br/> |Die Anzahl der gescheiterten Pushbenachrichtigungsanforderungen pro Sekunde.  <br/> |
|Erfolgreiche Pushbenachrichtigungsanforderungen/Sekunde  <br/> |Die Anzahl der erfolgreichen Pushbenachrichtigungsanforderungen pro Sekunde.  <br/> |
|Gedrosselte Pushbenachrichtigungsanforderungen/Sekunde  <br/> |Die Anzahl der gedrosselten Pushbenachrichtigungsanforderungen pro Sekunde.  <br/> |
|Pushbenachrichtigungsanforderungen/Sekunde  <br/> |Die Anzahl der gesendeten Pushbenachrichtigungsanforderungen pro Sekunde.  <br/> |
|Gescheiterte Anforderungen/Sekunde  <br/> |Die Anzahl der gescheiterten Anforderungen pro Sekunde.  <br/> |
|Empfangene Anforderungen/Sekunde  <br/> |Die Anzahl der empfangenen Anforderungen pro Sekunde.  <br/> |
|Abgelehnte Anforderungen/Sekunde  <br/> |Die Anzahl der abgelehnten Anforderungen pro Sekunde.  <br/> |
|Erfolgreiche Anforderungen/Sekunde  <br/> |Die Anzahl der erfolgreichen Anforderungen pro Sekunde.  <br/> |
|Erfolgreiche Anforderungen zur Sitzungsinitiierung/Sekunde  <br/> |Die Anzahl der erfolgreichen Anforderungen zur Standortermittlung pro Sekunde. Anforderungen zum Initiieren einer Sitzung beanspruchen die meisten CPU-Ressourcen auf dem Server. Maximal wird eine Last von 12 Anforderungen/Sekunde unterstützt. Die Aufrechterhaltbarkeit hängt von anderen Lasten auf dem Server ab. Das Initiieren einer Sitzung bedeutet normalerweise, dass ein Benutzer angemeldet wird, der für einen längeren Zeitraum abgemeldet war.  <br/> |
|Gesamtzahl der abgelehnten eingehenden Sprachanrufe  <br/> |Die Gesamtzahl der abgelehnten eingehenden Sprachanrufe.  <br/> |
|Gesamtzahl der gescheiterten eingehenden Sprachanrufe  <br/> |Die Gesamtzahl der gescheiterten eingehenden Sprachanrufe.  <br/> |
|Gesamtzahl der gescheiterten ausgehenden Sprachanrufe  <br/> |Die Gesamtzahl der gescheiterten ausgehenden Sprachanrufe.  <br/> |
|Gesamtzahl der vom Benutzer beendeten Sitzungen  <br/> |Die Gesamtzahl der vom Benutzer beendeten Sitzungen.  <br/> |
|Gesamtzahl der Pushbenachrichtigungsanforderungen  <br/> |Die Gesamtzahl der Pushbenachrichtigungsanforderungen.  <br/> |
|Gesamtzahl gescheiterter Pushbenachrichtigungsanforderungen  <br/> |Die Gesamtzahl der gescheiterten Pushbenachrichtigungsanforderungen.  <br/> |
|Gesamtzahl erfolgreicher Pushbenachrichtigungsanforderungen  <br/> |Die Gesamtzahl der erfolgreichen Pushbenachrichtigungsanforderungen.  <br/> |
|Gesamtzahl gedrosselter Pushbenachrichtigungsanforderungen  <br/> |Die Gesamtzahl der gedrosselten Pushbenachrichtigungsanforderungen.  <br/> |
|Gesamtzahl der gescheiterten Anforderungen  <br/> |Die Gesamtzahl der gescheiterten Anforderungen.  <br/> |
|Gesamtzahl der über den Befehlskanal empfangenen Anforderungen  <br/> |Die Gesamtzahl der über den Befehlskanal empfangenen Anforderungen.  <br/> |
|Gesamtzahl der abgelehnten Anforderungen  <br/> |Die Gesamtzahl der abgelehnten Anforderungen.  <br/> |
|Gesamtzahl der erfolgreichen Anforderungen  <br/> |Die Gesamtzahl der an den Mobilitätsdienst gerichteten Anforderungen, die erfolgreich waren.  <br/> |
|Gesamtzahl der initiierten Sitzungen  <br/> |Die Gesamtzahl der Sitzungen, die seit dem Start des Mobilitätsdiensts initiiert wurden.  <br/> |
|Gesamtzahl der Sitzungen, die aufgrund eines Leerlauftimeouts des Benutzers beendet wurden  <br/> |Die Gesamtzahl der Sitzungen, die beendet wurden, da das Leerlauftimeout des Benutzers erreicht wurde.  <br/> |
|Gesamtzahl der erfolgreichen eingehenden Sprachanrufe  <br/> |Die Gesamtzahl der erfolgreichen eingehenden Sprachanrufe.  <br/> |
|Gesamtzahl der erfolgreichen ausgehenden Sprachanrufe  <br/> |Die Gesamtzahl der erfolgreichen ausgehenden Sprachanrufe.  <br/> |
   
> [!NOTE]
> MCX (Mobility Service)-Unterstützung für ältere Mobile Clients steht in Skype for Business Server 2019 nicht mehr zur Verfügung. Alle derzeitigen mobilen Skype for Business-Clients verwenden bereits Unified Communications Web API (UCWA) zur Unterstützung von Instant Messaging (im), Anwesenheitsinformationen und Kontakten. Benutzer mit Legacy-Clients, die MCX verwenden, müssen ein Upgrade auf einen aktuellen Client durchführen.
