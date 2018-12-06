---
title: Überwachen der Mobilität in Bezug auf die Leistung in Lync Server 2013
TOCTitle: Überwachen der Mobilität in Bezug auf die Leistung in Lync Server 2013
ms:assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Hh690033(v=OCS.15)
ms:contentKeyID: 49294890
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Überwachen der Mobilität in Bezug auf die Leistung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-14_

Der Lync Server-Mobilitätsdienst erhöht die Last auf Front-End-Servern und Front-End-Pools. Mobile Geräte, die auch bei einer inaktiven mobilen Anwendung die Verbindung mit dem Server aufrechterhalten (z. B. Android- und Nokia-Geräte), erzeugen eine höhere Last als Geräte, die die Serververbindung beenden, wenn die mobile Anwendung minimiert wird. Nimmt die Nutzung der Mobilitätsdienste zu, müssen Sie die Mobilitätsleistung überwachen, um festzustellen, ob die Kapazität erhöht werden muss.

Die Mobilitätsleistung wird durch mehrere Limits beeinflusst:

  - Verfügbarer Speicher

  - Anforderungswarteschlangenlimit

  - Gleichzeitige Verbindungen

  - IIS-Warteschlangenlänge

Darüber hinaus wirken sich andere Serverlimits auf die Mobilitätsleistung aus. Hierzu gehören maximal zwölf gleichzeitige Anmeldungen, Authentifizierungen und Sitzungserneuerungen und -beendigungen. Die Maximalwerte müssen für die meisten Bereitstellungen nicht geändert werden.

## In diesem Abschnitt

  - [Überwachen der Serverspeicher-Kapazitätslimits](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)

  - [Überwachen des Mobilitätsdiensts und der Verwendung der UCWA](lync-server-2013-monitoring-mobility-service-and-ucwa-usage.md)

  - [Konfigurieren des Mobilitätsdiensts für hohe Leistung](lync-server-2013-configuring-mobility-service-for-high-performance.md)

  - [Überwachen der Protokolldateien der IIS-Ablaufverfolgung für Anforderungen](lync-server-2013-monitoring-iis-request-tracing-log-files.md)

  - [Leistungsindikatoren für Mobilität](lync-server-2013-mobility-performance-counters.md)

