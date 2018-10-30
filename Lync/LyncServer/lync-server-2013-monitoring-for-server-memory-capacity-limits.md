---
title: Überwachen der Serverspeicher-Kapazitätslimits
TOCTitle: Überwachen der Serverspeicher-Kapazitätslimits
ms:assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Hh689982(v=OCS.15)
ms:contentKeyID: 49293291
ms.date: 12/28/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Überwachen der Serverspeicher-Kapazitätslimits

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.


> [!WARNING]
> Die Informationen zur Kapazitätsplanung in diesem Thema beziehen sich nur auf Lync 2010 Mobile-Clients und den Mobilitätsdienst (Mcx). Die Kapazitätsplanung für die von Lync 2013&nbsp;Mobile-Clients verwendeten Unified Communications-Web-API (UCWA) wird durch das Lync Server&nbsp;2013, Planungstool bereitgestellt.



Mithilfe zweier Leistungsindikatoren für Mobilität können Sie aktuelle Verwendungsdaten ermitteln und die Kapazität für den Lync Server 2013-Mobilitätsdienst (Mcx) planen sowie die Speicherauslastung für die UCWA überwachen. Für die UCWA ist die Indikatorenkategorie **LS:WEB – UCWA**; für den Mobilitätsdienst befinden sich die Indikatoren in der Kategorie **LS:WEB - Mobile Communication Service**. Die zu überwachenden Indikatoren sind:

  - **Anzahl der derzeit aktiven Sitzungen mit aktiven Anwesenheitsabonnements**: Dies ist die aktuelle Anzahl von Endpunkten, die über die UCWA oder den Mobilitätsdienst (Mcx) registriert wurden und aktive Anwesenheitsabonnements besitzen (Anzahl der immer verbundenen mobilen Benutzer).

  - **Anzahl der derzeit aktiven Sitzungen**: Dies ist die aktuelle Anzahl von Endpunkten, die über UCWA oder den Mobilitätsdienst registriert wurden.

Wenn Unterschied zwischen **Anzahl der derzeit aktiven Sitzungen mit aktiven Anwesenheitsabonnements** und **Anzahl der derzeit aktiven Sitzungen** im Laufe der Zeit gering ist, bedeutet dies, dass die meisten Benutzer ein mobiles Gerät verwenden, dass immer verbunden ist, beispielsweise ein Android- oder Nokia-Mobilgerät (nur für Mcx). Immer verbundene UCWA-Geräte umfassen Apple- und Android-Geräte, auf denen Lync 2013 Mobile-Clients ausgeführt werden). Wenn **Anzahl der derzeit aktiven Sitzungen** sehr viel höher ist als **Anzahl der derzeit aktiven Sitzungen mit aktiven Anwesenheitsabonnements** weist dies darauf hin, dass mehr Benutzer ein Hintergrund-Endpunktgerät unter Mcx verwenden, z. B. ein Apple iOS-Gerät oder ein Windows Phone. (Windows Phone ist der einzige Lync 2013 Mobile-Client, der registriert wird).

Sie sollten die Leistungsindikatoren für **Anzahl der derzeit aktiven Sitzungen mit aktiven Anwesenheitsabonnements** und **Anzahl der derzeit aktiven Sitzungen** basierend auf der erwarteten Nutzung, den Ergebnissen der Kapazitätsplanung und der laufenden Überwachung des Mobilitätsdiensts und anderer Front-End-Server-Leistungsindikatoren beschränken. Die festgelegten Beschränkungen sollten das Auswerten der Serverkapazität und das Auslösen von Warnungen bei einer Kapazitätsüberschreitung ermöglichen.

Zum Bestimmen der richtigen Beschränkungen müssen Sie zuerst ermitteln, wie viel Speicher auf dem Front-End-Server für den Mobilitätsdienst verfügbar ist. Überwachen Sie die Leistungsindikatoren, um anhand der folgenden Formel festzustellen, ob zusätzliche Kapazität eingeplant werden muss:

Insgesamt vom Mcx-Mobilitätsdienst belegter Speicherplatz (MB) = 164 + (400 + 134) : 1024 + **Anzahl der derzeit aktiven Sitzungen mit aktiven Anwesenheitsabonnements** + 400 : 1024 x (**Anzahl der derzeit aktiven Sitzungen** - **Anzahl der derzeit aktiven Sitzungen mit aktiven Anwesenheitsabonnements**)


> [!IMPORTANT]
> Der Microsoft Lync Server 2010-Kapazitätsrechner ist ein mit allen Formeln vorausgefülltes Arbeitsblatt, anhand deren ein Planer die Anforderungen an die Server bestimmen kann, darunter CPU, Arbeitsspeicherund Festplatte. Sie finden das Arbeitsblatt und ein zugehöriges Dokument zum Download unter: <A class=uri href="http://go.microsoft.com/fwlink/?linkid=212657">http://go.microsoft.com/fwlink/?linkid=212657</A>



Auf dem Front-End-Server muss genügend Speicherplatz verfügbar sein, um den Mobilitätsdienst in Failoversituationen zu unterstützen. Sie können den derzeit verwendeten Speicher auf dem Front-End-Server mit dem Leistungsindikator **Speicher\\Verfügbare MB** überprüfen oder die oben genannte Formel verwenden, um den Speicherplatz zu planen, der vom Mobilitätsdienst voraussichtlich verwendet wird.

Ist auf dem Front-End-Server weniger als 1.500 MB Speicherplatz verfügbar, wenn Sie die voraussichtliche Anzahl von Mobilitätsbenutzern planen, müssen Sie weitere Hardware hinzufügen, um den Mobilitätsdienst zu unterstützen. Ausführliche Informationen finden Sie in der Betriebsdokumentation unter [Überwachen der Mobilität in Bezug auf die Leistung in Lync Server 2013](lync-server-2013-monitoring-mobility-for-performance.md).

## Siehe auch

#### Weitere Ressourcen

[Überwachen der Mobilität in Bezug auf die Leistung in Lync Server 2013](lync-server-2013-monitoring-mobility-for-performance.md)

