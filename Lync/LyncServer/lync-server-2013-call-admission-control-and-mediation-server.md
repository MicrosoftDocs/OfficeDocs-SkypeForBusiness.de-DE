---
title: 'Lync Server 2013: Anrufsteuerung und Vermittlungsserver'
TOCTitle: Anrufsteuerung und Vermittlungsserver
ms:assetid: 76faccdc-67d0-4c8b-8e47-1e23c93b02c6
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398585(v=OCS.15)
ms:contentKeyID: 49294439
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anrufsteuerung und Vermittlungsserver in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

Die Anrufsteuerung, die erstmalig unter Lync Server 2010 eingeführt wurde, verwaltet Echtzeitsitzungen basierend auf der verfügbaren Bandbreite, um schlechte QoE-Resultate (Quality of Experience) für Benutzer in überlasteten Netzwerken zu verhindern. Zur Unterstützung dieser Funktion ist der Vermittlungsserver, der Signal- und Mediendaten zwischen der Enterprise-VoIP-Infrastruktur und einem Gateway oder SIP-Trunkinganbieter übersetzt, für die Bandbreitenverwaltung der Interaktion auf Lync Server- und Gatewayseite verantwortlich. Bei der Anrufsteuerung übernimmt das als Endpunkt eingesetzte Gerät für einen Anruf die Bandbreitenreservierung. Die Gatewaypeers (PSTN-Gateway, IP-Nebenstellenanlage, SBC), mit denen der Vermittlungsserver auf Gatewayseite interagiert, bieten keine Unterstützung für die Lync Server 2013-Anrufsteuerung. Daher muss der Vermittlungsserver die Bandbreiteninteraktion für seinen Gatewaypeer übernehmen. Wenn möglich, reserviert der Vermittlungsserver die Bandbreite im Voraus. Ist dies nicht möglich (z. B. wenn der Ort des maßgeblichen Medienendpunkts auf Gatewayseite für einen ausgehenden Anruf an den Gatewaypeer nicht bekannt ist), wird die Bandbreite beim Tätigen des Anrufs reserviert. Dieses Verhalten kann zu einer zu hohen Bandbreitenbelegung führen, ist jedoch die einzige Möglichkeit, Anruffehler zu vermeiden.

Die Medienumgehung und die Bandbreitenreservierung schließen sich gegenseitig aus. Wenn für einen Anruf die Medienumgehung implementiert wird, wird für diesen Anruf keine Anrufsteuerung ausgeführt. Es wird davon ausgegangen, dass für den Anruf keine Verbindungen mit beschränkter Bandbreite verwendet werden. Wenn die Anrufsteuerung für einen bestimmten Anruf verwendet wird, an dem der Vermittlungsserver beteiligt ist, kann keine Medienumgehung implementiert werden.

Genauere Informationen zur Medienumgehung und zur finden Sie unter [Planung der Medienumgehung in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) oder [Planen des Anrufsteuerungsdiensts in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) in der Planungsdokumentation.

