---
title: Lync Server 2013-Standorte
TOCTitle: Standorte
ms:assetid: 022cb6dd-37e2-4882-a53e-5ddfdbc6f53a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398076(v=OCS.15)
ms:contentKeyID: 49292990
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server-Standorte für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-16_

In Lync Server definieren Sie *Standorte* für Ihr Netzwerk, die Lync Server-Komponenten umfassen. Bei einem Standort handelt es sich um einen Satz von Computern, die durch ein Hochgeschwindigkeitsnetzwerk mit niedriger Latenz miteinander verbunden sind, beispielsweise durch ein einzelnes lokales Netzwerk (Local Area Network, LAN) oder zwei Netzwerke, die über ein Hochgeschwindigkeits-Glasfasernetzwerk verbunden sind. Beachten Sie, dass Lync Server-Standorte sich vom Konzept der Standorte in Active Directory-Domänendienste und Microsoft Exchange Server unterscheiden. Die Lync Server-Standorte müssen nicht Ihren Active Directory-Standorten entsprechen.

## Standorttypen

Bei jedem Standort handelt es sich entweder um einen *zentralen Standort* , der mindestens einen Front-End-Pool oder Standard Edition-Server umfasst, oder um einen *Zweigstellenstandort* . Jeder Zweigstellenstandort ist genau einem zentralen Standort zugeordnet, und die meisten Lync Server-Funktionen werden den Benutzern in der Zweigstelle über die Server im zugeordneten zentralen Standort bereitgestellt.

Jeder Zweigstellenstandort umfasst eine der folgenden Komponenten:

  - Eine *Survivable Branch Appliance (SBA)* . Dies ist ein Bladeserver nach Industriestandard, bei dem eine Lync Server-Registrierungsstelle und ein Vermittlungsserver unter Windows Server ausgeführt werden. Die Survivable Branch-Anwendung umfasst außerdem ein PSTN-Gateway (Public Switched Telephone Network). Die Survivable Branch-Anwendung ist für Zweigstellenstandorte mit 25 bis 1.000 Benutzern konzipiert.

  - Einen *Survivable Branch Server (SBS)* . Dies ist ein Server mit Windows Server, der vorgegebene Hardwareanforderungen erfüllt und auf dem die Software für die Lync Server-Registrierungsstelle und den Vermittlungsserver installiert wurde. Der Server muss entweder über ein PSTN-Gateway oder einen SIP-Trunk mit einem Telefoniedienstanbieter verbunden sein. Der Survivable Branch Server ist für Zweigstellen mit 1.000 bis 5.000 Benutzern konzipiert.

  - Ein PSTN-Gateway und optional ein *Vermittlungsserver* . Ausführliche Informationen hierzu und zu anderen Serverrollen finden Sie unter [Serverrollen in Lync Server 2013](lync-server-2013-server-roles.md).

Ein Zweigstellenstandort mit einer ausfallsicheren WAN-Verbindung (Wide Area Network) zu einem zentralen Standort kann die dritte Option nutzen – ein PSTN-Gateway und optional einen Vermittlungsserver. Zweigstellen mit weniger ausfallsicheren Leitungen sollten eine Survivable Branch-Anwendung oder einen Survivable Branch Server verwenden, die/der Ausfallsicherheit bei WAN-Ausfällen bietet. Wenn beispielsweise an einem Standort eine Survivable Branch-Anwendung oder ein Survivable Branch Server bereitgestellt wurde, können Benutzer weiterhin Enterprise-VoIP-Anrufe tätigen und empfangen, wenn die WAN-Verbindung zwischen der Zweigstelle und dem zentralen Standort ausfällt. Ausführliche Informationen zu Survivable Branch-Anwendung, Survivable Branch Server und Ausfallsicherheit finden Sie unter [Planen der Ausfallsicherheit für Enterprise-VoIP in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) in der Planungsdokumentation.

## Standorttopologien

Ihre Bereitstellung muss mindestens einen zentralen Standort enthalten und kann einen oder mehrere Zweigstellenstandorte umfassen. Jeder Zweigstellenstandort ist mit einem zentralen Standort verbunden. Der zentrale Standort stellt für die Zweigstelle Lync Server-Dienste bereit, die am Zweigstellenstandort nicht lokal gehostet werden, z. B. Anwesenheitsinformationen und Konferenzfunktionen.

Wenn Sie über mehrere Standorte verfügen, können Sie die Front-End-Pools an unterschiedlichen Standorten zu Paaren verknüpfen, um die Notfallwiederherstellung zu ermöglichen. Ausführliche Informationen finden Sie unter [Unterstützung für hohe Verfügbarkeit und Notfallwiederherstellung in Lync Server 2013](lync-server-2013-high-availability-and-disaster-recovery-support.md).

## Siehe auch

#### Konzepte

[Serverrollen in Lync Server 2013](lync-server-2013-server-roles.md)  
[Unterstützung für hohe Verfügbarkeit und Notfallwiederherstellung in Lync Server 2013](lync-server-2013-high-availability-and-disaster-recovery-support.md)  

#### Weitere Ressourcen

[Planen der Ausfallsicherheit für Enterprise-VoIP in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

