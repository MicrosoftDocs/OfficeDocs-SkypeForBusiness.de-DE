---
title: 'Lync Server 2013: Bewährte Methoden für die Anrufsteuerung'
TOCTitle: Bewährte Methoden für die Anrufsteuerung
ms:assetid: 97173cca-8175-4ae2-a247-eb7ef809da93
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398770(v=OCS.15)
ms:contentKeyID: 49294820
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Bewährte Methoden für die Anrufsteuerung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-22_

Halten Sie sich bei der Bereitstellung der Anrufsteuerung an die folgenden bewährten Methoden, um die Leistung zu verbessern und die Bereitstellung zu vereinfachen:

  - Stellen Sie sicher, dass WANs für den aktuellen und den erwarteten Mediendatenverkehr angemessen ausgelegt sind.
    

    > [!NOTE]
    > Es empfiehlt sich, bei der Bandbreiteneinschränkungen einen Puffer einzurechnen. Manche Szenarien, zum Beispiel Racebedingungen, wirken sich auf die verwendete Gesamtbandbreite aus und können zu Situationen führen, in denen die Bandbreiteneinschränkung überschritten wird. Wenn beispielsweise zwei Anrufe gestartet werden, während der Mediendatenverkehr sich einer Bandbreiteneinschränkung nähert, wird möglicherweise einer der beiden Anrufe abgewiesen, weil der andere zuerst gestartet wurde.



  - Überwachen Sie die Netzwerkbelegung und die Kommunikationsdatensätze, damit Sie die optimalen Einstellungen für die Anrufsteuerung wählen und diese bei Änderungen in der Netzwerkbelegung aktualisieren können.

  - Verwenden Sie Richtlinien für die Anrufsteuerung zur Ergänzung der QoS-Einstellungen.

  - Wenn Sie blockierte Anrufe zum PSTN umleiten möchten, überprüfen Sie die Funktionalität und die Kapazität des PSTN. Weitere Informationen hierzu finden Sie unter [Planen des VoIP-Routings für ausgehende Anrufe in Lync Server 2013](lync-server-2013-planning-outbound-voice-routing.md).
    

    > [!NOTE]
    > Kapazität bezieht sich auf die Anzahl der Ports, die Sie zur Unterstützung einer möglichen PSTN-Umleitung öffnen müssen.


