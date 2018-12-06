---
title: 'Lync Server 2013: Stellvertretung'
TOCTitle: Stellvertretung
ms:assetid: 89e76e5c-3cfb-4504-8d0d-7509c8ba9815
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ994045(v=OCS.15)
ms:contentKeyID: 52056383
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Stellvertretung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-03-09_

Die Stellvertretungsmöglichkeiten in Lync werden in der folgenden Weise vom standortbasierten Routing beeinflusst:

  - Wenn eine für standortbasiertes Routing aktivierte Stellvertretung einen Anruf im Auftrag eines Vorgesetzten führt, wird die VoIP-Richtlinie der Stellvertretung zum Autorisieren des Anrufs verwendet, und die VoIP-Routingrichtlinie vom Standort der Stellvertretung wird für das Routen des Anrufs verwendet

  - Für eingehende Anrufe aus dem öffentlichen Telefonnetz für einen Vorgesetzten gelten die gleichen Regeln wie für Anrufweiterleitung oder paralleles Anrufen, wie in den Themen zur Anrufweiterleitung und -durchstellung bzw. zum parallelen Anrufen beschrieben.

  - Wenn eine Stellvertretung einen Endpunkt im öffentlichen Telefonnetz als Ziel für paralleles Anrufen festlegt, wird bei einem für den Vorgesetzten eingehenden Anruf die VoIP-Routingrichtlinie des Standorts, der dem eingehenden Trunk zugeordnet ist, für das Routen des Anrufs an den Endpunkt der Stellvertretung im öffentlichen Telefonnetz verwendet.

  - Für Stellvertretungen empfiehlt es sich, dass der Vorgesetzte und die ihm zugeordneten Stellvertretungen sich normalerweise am gleichen Netzwerkstandort befinden.

## Siehe auch

#### Weitere Ressourcen

[Szenarien für das standortbasierte Routing in Lync Server 2013](lync-server-2013-scenarios-for-location-based-routing.md)

