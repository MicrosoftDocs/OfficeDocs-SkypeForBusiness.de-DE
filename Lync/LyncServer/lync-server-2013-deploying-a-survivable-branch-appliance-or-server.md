---
title: 'Lync Server 2013: Bereitstellen einer Survivable Branch Appliance oder eines Survivable Branch Servers'
TOCTitle: Bereitstellen einer Survivable Branch Appliance oder eines Survivable Branch Servers
ms:assetid: cb780c14-dc5f-41ba-8092-f20ae905bd16
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398849(v=OCS.15)
ms:contentKeyID: 49295424
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Bereitstellen einer Survivable Branch Appliance oder eines Survivable Branch Servers mit Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2014-12-10_

Ausfallsicheres Enterprise-VoIP bezieht sich auf die Fähigkeit, für die Benutzer an Zweigniederlassungen unterbrechungsfreie Enterprise-VoIP-Dienste bereitzustellen, auch wenn die Verbindung zum zentralen Standort nicht mehr verfügbar ist.

Für kleine und mittelgroße Zweigniederlassungen (mit 25 bis 1.000 Benutzern) wird die Bereitstellung einer Survivable Branch-Anwendung empfohlen, die PSTN-Anrufe unter Verwendung des integrierten PSTN-Gateways oder über einen SIP-Trunk zu einem Telefoniedienstanbieter terminiert. Bei einer Survivable Branch-Anwendung handelt es sich um ein Drittanbietergerät, das aus einem Bladeserver mit Windows Server 2008 R2-Betriebssystem, Lync Server 2013-Registrierungsstelle, Vermittlungsserversoftware und einem PSTN-Gateway in einem einzigen Gehäuse besteht.

Für Zweigniederlassungen mit 1.000 bis 5.000 Benutzern und einem nicht ausfallsicheren WAN wird ein Survivable Branch-Server empfohlen, der entweder mit einem PSTN-Gateway oder einem SIP-Trunk zu einem Telefondienstanbieter verbunden ist. Bei einem Survivable Branch-Server handelt es sich um einen Windows Server-basierten Computer mit installierter Registrierungsstelle und Vermittlungsserversoftware.


> [!NOTE]
> Für Zweigniederlassungen mit mehr als 5.000&nbsp;Benutzern und dedizierten Lync Server-Administratoren wird eine vollständige, von der Lync Server-Bereitstellung im zentralen Standort getrennte Lync Server 2013-Bereitstellung empfohlen.<BR>Informationen zur optimalen Ausfallsicherheitslösung für die Zweigniederlassungen in Ihrer Organisation sowie zu Voraussetzungen und Planungsüberlegungen finden Sie unter <A href="lync-server-2013-branch-site-resiliency-requirements.md">Anforderungen für die Ausfallsicherheit an Zweigstellenstandorten für Lync Server 2013</A> in der Planungsdokumentation.



## In diesem Abschnitt

  - [Bereitstellen einer Survivable Branch Appliance oder eines Survivable Branch Servers mit Lync Server 2013 – Aufgaben am zentralen Standort](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)

  - [Bereitstellen einer Survivable Branch Appliance oder eines Survivable Branch Servers mit Lync Server 2013 – Aufgaben am Zweigstellenstandort](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)

  - [Konfigurieren von Benutzern für Ausfallsicherheit für Zweigstellenstandorte in Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

  - [Verwalten von Benutzern in einer Survivable Branch Appliance oder auf einem Survivable Branch Server in Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)

  - [Anhänge: Survivable Branch Appliances und Survivable Branch Server in Lync Server 2013](lync-server-2013-appendices-survivable-branch-appliances-and-servers.md)

## Siehe auch

#### Weitere Ressourcen

[Bereitstellen von Lync Server 2013](lync-server-2013-deploying-lync-server.md)

