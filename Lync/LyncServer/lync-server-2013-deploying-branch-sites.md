---
title: 'Lync Server 2013: Bereitstellen von Zweigstellen'
TOCTitle: Bereitstellen von Zweigstellen
ms:assetid: 1475dee0-66ae-4ee5-b6f1-7409b4bbff45
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398217(v=OCS.15)
ms:contentKeyID: 49293263
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Bereitstellen von Zweigstellen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

Für Benutzer an Zweigstellenstandorten werden die meisten Lync Server 2013-Funktionen über den Server am zentralen Standort bereitgestellt, dem die Zweigstelle zugeordnet ist. Jede Zweigstelle ist mit genau einem zentralen Standort verbunden. Zum Tätigen und Entgegennehmen von Anrufen aus dem Telefonfestnetz (Public Switched Telephone Network, PSTN) kann ein Zweigstellenstandort eine der folgenden Komponenten umfassen:

  - Ein PSTN-Gateway und optional einen Vermittlungsserver

  - Einen SIP-Trunk

  - Eine vorhandene VoIP-Infrastruktur mit einer Nebenstellenanlage

  - Eine Survivable Branch-Anwendung

  - Ein Survivable Branch-Server

Zweigstellenstandorte mit einer Survivable Branch-Anwendung oder einem Survivable Branch-Server bieten beim Auftreten von WAN-Fehlern (Wide Area Network) oder bei einem Ausfall des zentralen Standorts mehr Ausfallsicherheit als Zweigstellen ohne diese Lösungen. Wenn beispielsweise an einem Standort eine Survivable Branch-Anwendung oder ein Survivable Branch-Server bereitgestellt wurde, können Benutzer weiterhin PSTN-Anrufe tätigen und empfangen, wenn die Netzwerkverbindung zwischen der Zweigstelle und dem zentralen Standort ausfällt. Eine weitere Möglichkeit zur Bereitstellung von Ausfallsicherheit für Zweigstellenstandorte ist die Verwendung eines PSTN-Gateways oder SIP-Trunks mit einer vollständigen Lync Server-Bereitstellung am Zweigstellenstandort.

Informationen dazu, welche Zweigstellenbereitstellung für Ihre Organisation am besten geeignet ist, sowie Informationen zu Voraussetzungen und anderen Planungsüberlegungen finden Sie unter [Planen der PSTN-Konnektivität in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) und [Planen von VoIP-Ausfallsicherheit für Zweigstellen in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) in der Planungsdokumentation.

## In diesem Abschnitt

  - [Bereitstellen der PSTN-Konnektivität an einem Zweigstellenstandort in Lync Server 2013](lync-server-2013-providing-pstn-connectivity-at-a-branch-site.md)

  - [Bereitstellen einer Survivable Branch Appliance oder eines Survivable Branch Servers mit Lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md)

