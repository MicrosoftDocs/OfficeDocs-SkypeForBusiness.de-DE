---
title: Leistungsindikatoren für Mobilität in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: d18ed85a-673d-4695-aa3f-ac83a38ab90a
description: 'Zusammenfassung: Erfahren Sie mehr über die Leistungsindikatoren, mit denen Sie Server überwachen können, auf denen die Unified Communications-Web-API (UCWA) und der Skype for Business Server Mcx Mobility Service ausgeführt werden.'
ms.openlocfilehash: 4ea7ba3f7c4d9685fe01c64157324a64f823c5bc
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58578779"
---
# <a name="mobility-performance-counters-in-skype-for-business-server"></a>Leistungsindikatoren für Mobilität in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über die Leistungsindikatoren, mit denen Sie Server überwachen können, auf denen die Unified Communications-Web-API (UCWA) und der Skype for Business Server Mcx Mobility Service ausgeführt werden.
  
In den folgenden Tabellen sind die Namen und Beschreibungen von Leistungsindikatoren aufgeführt, mit denen Sie Server überwachen können, auf denen die Unified Communications Web API (UCWA) und der Skype for Business Server Mcx Mobility Service ausgeführt werden. 
  
Der Kategoriename für die Leistungsindikatoren in der UCWA-Tabelle lautet **LS:WEB - UCWA**.
  
Der Kategoriename für die Leistungsindikatoren in der Mcx Mobility Service-Tabelle lautet **LS:WEB – Mobile Communication Service**.

> [!NOTE]
> MCX(Mobility Service)-Unterstützung für ältere mobile Clients ist in Skype for Business Server 2019 nicht mehr verfügbar. Alle aktuellen Skype for Business mobile Clients verwenden bereits unified Communications Web API (UCWA), um Chatnachrichten, Anwesenheitsinformationen und Kontakte zu unterstützen. Benutzer mit Legacyclients, die MCX verwenden, müssen auf einen aktuellen Client aktualisieren.
  
## <a name="performance-counters-for-ucwa"></a>Leistungsindikatoren für UCWA

|Leistungsindikator|Beschreibung|
|:-----|:-----|
|Anzahl der aktiven Anwendungen  <br/> |Die aktuelle Anzahl von Anwendungen  <br/> |
|Anzahl der aktiven Anwendungsfreigabemodalitäten  <br/> |Die aktuelle Anzahl der Modalitäten für die Anwendungsfreigabe  <br/> |
|Anzahl der aktiven Audiomodalitäten  <br/> |Die aktuelle Anzahl der Audiomodalität  <br/> |
|Anzahl der aktiven Datenzusammenarbeitsmodalitäten  <br/> |Die aktuelle Anzahl der Datenzusammenarbeitsmodalitäten  <br/> |
|Latenz beim Abrufen von Active Directory-Fotos (ms)  <br/> |Dieser Indikator zeigt die durchschnittliche Zeit (in Millisekunden) zum Abrufen eines Fotos aus dem Active Directory an.  <br/> |
|Anzahl der aktiven Messaging-Modalitäten  <br/> |Die aktuelle Anzahl der Messaging-Modalität  <br/> |
|Anzahl der aktiven Panoramavideomodalitäten  <br/> |Die aktuelle Anzahl der Panoramavideomodalitäten  <br/> |
|Active Pending Get Count  <br/> |Die Anzahl der derzeit aktiven ausstehenden Abrufe; Lange gehaltene Verbindungen mit dem Server  <br/> |
|Anzahl aktiver Sitzungen  <br/> |Die aktuelle Anzahl der in UCWA registrierten Endpunkte pro Anwendung und Die Gesamtzahl  <br/> |
|Anzahl der aktiven Benutzerinstanzen  <br/> |Die aktuelle Anzahl von Benutzerinstanzen  <br/> |
|Aktive Benutzerinstanzen ohne Anwendung  <br/> |Die aktuelle Anzahl von Benutzerinstanzen ohne Anwendung  <br/> |
|Anzahl der aktiven Videomodalitäten  <br/> |Die aktuelle Anzahl der Videomodalitäten  <br/> |
|Empfangene/zweite Anwendungserstellungsanforderungen  <br/> |Die Anzahl der empfangenen Anwendungserstellungsanforderungen pro Sekunde.  <br/> |
|AS MCU-Verknüpfungsfehler  <br/> |Die Anzahl der AS MCU-Verbindungsfehler  <br/> |
|FEHLER BEI DER AV MCU-Verknüpfung  <br/> |Die Anzahl der AV MCU-Teilnahmefehler  <br/> |
|Durchschnittliche Startzeit der Anwendung (ms)  <br/> |Die durchschnittliche Startzeit der Anwendung in Millisekunden  <br/> |
|Durchschnittliche Lebensdauer für Sitzung (ms)  <br/> |Die durchschnittliche Dauer einer Sitzung in Millisekunden.  <br/> |
|Fehler bei der Daten-MCU-Verknüpfung  <br/> |Die Anzahl der Fehler bei der Daten-MCU-Verknüpfung  <br/> |
|Exchange Kontaktsuchlatenz (ms)  <br/> |Dieser Indikator zeigt die durchschnittliche Zeit (in Millisekunden) zum Durchsuchen des Kontakts in Exchange  <br/> |
|Exchange Hd Photo Get Latency (ms)  <br/> |Dieser Indikator zeigt die durchschnittliche Zeit (in Millisekunden) zum Abrufen eines Fotos aus Exchange  <br/> |
|HTTP 4xx-Antworten/Sekunde  <br/> |Die Pro-Sekunde-Antwortrate mit HTTP 4xx-Code  <br/> |
|HTTP 5xx-Antworten/Sekunde  <br/> |Die Anzahl der Antworten pro Sekunde mit HTTP 5xx-Code  <br/> |
|IM MCU-Teilnahmefehler  <br/> |Die Anzahl der McU-Verbindungsfehler bei Chatnachrichten  <br/> |
|Anzahl der Fehler beim Abrufen von Active Directory-Fotos  <br/> |Die Gesamtzahl der Fehler beim Abrufen von Fotos aus Active Directory  <br/> |
|Anzahl der Fehler bei der Kontaktsuche  <br/> |Die Gesamtzahl der Fehler beim Durchsuchen von Kontakten in Exchange  <br/> |
|Anzahl der Deserialisierungsfehler  <br/> |Die Gesamtzahl der Deserialisierungsfehler  <br/> |
|Anzahl der Fehler beim Abrufen von HD-Fotos  <br/> |Die Gesamtzahl der Fehler beim Abrufen von HD-Fotos aus Exchange  <br/> |
|Mehr als die maximalen Abonnements pro Anwendung  <br/> |Die Anzahl der Abonnementanforderungen über dem maximal zulässigen Wert pro Anwendung.  <br/> |
|Über den maximalen Abonnements pro Batch  <br/> |Die Anzahl der Abonnementanforderungen über dem maximal zulässigen Wert pro Batch  <br/> |
|Fehler beim Anwesenheitsabonnement  <br/> |Die Anzahl der Fehler beim Abonnieren von Anwesenheitsinformationen.  <br/> |
|Registrieren von Endpunktfehlern  <br/> |Die Anzahl der Fehler beim Registrieren von Endpunkten  <br/> |
|Empfangene Anforderungen/Sekunde  <br/> |Die Anzahl der empfangenen Anforderungen pro Sekunde.  <br/> |
|Erfolgreiche Anforderungen/Sekunde  <br/> |Die Anzahl der erfolgreichen Anforderungen pro Sekunde (HTTP-Antwortcodes 2xx/3xx)  <br/> |
|Erfolgreiches Erstellen von Anwendungsanforderungen/Sekunde  <br/> |Die Anzahl der erfolgreichen Anwendungserstellungsanforderungen pro Sekunde.  <br/> |
|Timed Out Pending Get Count  <br/> |Die Anzahl ausstehender Ausstehender ruft dieses Timeout ab.  <br/> |
|Gesamtzahl empfangener Anwendungserstellungsanforderungen  <br/> |Die Gesamtzahl der Anwendungserstellungsanforderungen, die seit dem Starten des Diensts empfangen wurden.  <br/> |
|Http-Antworten insgesamt 4xx  <br/> |Die Gesamtzahl der HTTP 4xx-Antworten  <br/> |
|Http-Antworten insgesamt 5xx  <br/> |Die Gesamtzahl der HTTP 5xx-Antworten  <br/> |
|Gesamtzahl der im Befehlskanal empfangenen Anforderungen  <br/> |Die Gesamtzahl der über den Befehlskanal empfangenen Anforderungen.  <br/> |
|Gesamtzahl der erfolgreichen Anforderungen  <br/> |Die Gesamtzahl der erfolgreichen Anforderungen.  <br/> |
|Gesamtzahl der initiierten Sitzungen  <br/> |Die Gesamtzahl der Sitzungen, die seit dem Starten des Diensts initiiert wurden.  <br/> |
|Gesamtzahl der aufgrund eines Leerlauftimeouts beendeten Sitzungen  <br/> |Die Gesamtzahl der Sitzungen, die beendet wurden, da das Leerlauftimeout des Benutzers erreicht wurde.  <br/> |
|Gedrosselte Anwendungen insgesamt  <br/> |Die Anzahl der gedrosselten Anwendungen  <br/> |
   
**Leistungsindikatoren für Mcx Mobility Service**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|Durchschnittliche Sitzungsdauer in Millisekunden  <br/> |Die durchschnittliche Dauer einer Sitzung in Millisekunden.  <br/> |
|Aktuelle Pushbenachrichtigungsabonnements  <br/> |Die aktuelle Anzahl von Pushbenachrichtigungsabonnements. Diese Zahl stellt in Verbindung mit der Anzahl der derzeit aktiven Sitzungen die Teilmenge der derzeit aktiven Sitzungen dar, die für Windows Mobile- oder iPhone-Geräte registriert sind.  <br/> |
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
> McX(Mobility Service)-Unterstützung für mobile Legacyclients ist in Skype for Business Server 2019 nicht mehr verfügbar. Alle aktuellen Skype for Business mobile Clients verwenden bereits unified Communications Web API (UCWA), um Chatnachrichten, Anwesenheitsinformationen und Kontakte zu unterstützen. Benutzer mit Legacyclients, die MCX verwenden, müssen auf einen aktuellen Client aktualisieren.
