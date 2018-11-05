---
title: 'Lync Server 2013: Technische Anforderungen für die Medienumgehung'
TOCTitle: Technische Anforderungen für die Medienumgehung
ms:assetid: 6162a204-0e7c-460a-8eb2-e592c6590a8a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398435(v=OCS.15)
ms:contentKeyID: 49294174
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Technische Anforderungen für die Medienumgehung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

Bei jedem Anruf in das Festnetz ermittelt der Vermittlungsserver, ob Mediendaten des Lync-Quellendpunkts direkt an einen Vermittlungsserver-Peer gesendet werden können, ohne über den Vermittlungsserver zu laufen. Der Peer kann ein PSTN-Gateway, eine IP-Nebenstellenanlage oder ein SBC (Session Border Controller) bei einem Anbieter von Internettelefoniediensten sein, der zu der Leitung zwischen dem Vermittlungsserver gehört, bei dem der Anruf weitergeleitet wird.

Die Medienumgehung kann implementiert werden, wenn die folgenden Voraussetzungen erfüllt sind:

  - Ein Vermittlungsserver-Peer muss die erforderlichen Funktionen für die Medienumgehung unterstützen, wobei die Fähigkeit zum Umgang mit mehreren gegabelten Antworten ("frühe Dialoge") am wichtigsten ist. Wie viele frühe Antworten Ihr Gateway, SBC oder Ihre Nebenstellenanlage maximal entgegennehmen kann, erfahren Sie vom entsprechenden Hersteller bzw. von Ihrem Anbieter von Internettelefoniediensten.

  - Der Vermittlungsserver-Peer muss Mediendatenverkehr direkt von Lync-Endpunkten entgegennehmen. Viele Anbieter von Internettelefoniediensten erlauben ihrem SBC, nur Datenverkehr vom Vermittlungsserver zu empfangen. Ob Ihr SBC Mediendatenverkehr direkt von Lync-Endpunkten akzeptiert, erfahren Sie von Ihrem Anbieter von Internettelefoniediensten.

  - Zwischen Lync-Clients und einem Vermittlungsserver-Peer muss eine gute Verbindung bestehen, d. h., sie müssen sich entweder in derselben Netzwerkregion oder an Netzwerkstandorten befinden, die über WAN-Links ohne Bandbreiteneinschränkungen mit der Region verbunden sind.

## Siehe auch

#### Konzepte

[Modi für die Medienumgehung in Lync Server 2013](lync-server-2013-media-bypass-modes.md)  
[Medienumgehung und Anrufsteuerung in Lync Server 2013](lync-server-2013-media-bypass-and-call-admission-control.md)

