---
title: 'Lync Server 2013: Für den Director erforderliche Komponenten'
TOCTitle: Für den Director erforderliche Komponenten
ms:assetid: 15c7c8d4-b93f-4386-b2d1-d76dab8f801e
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398228(v=OCS.15)
ms:contentKeyID: 49293283
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Für den Director erforderliche Komponenten in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-08_

Die einzige erforderliche Komponente zum Erstellen und Konfigurieren eines Directors ist das Bereitstellen der Director-Serverrolle. Dazu verwenden Sie den Topologie-Generator und definieren entweder einen Pool mit einem einzigen Computer oder einen Pool mit mehreren Computern im Directorpool-Knoten. Nachdem Sie den Director oder den Directorpool definiert haben, führen Sie den Lync Server-Bereitstellungs-Assistenten auf dem Computer aus, der als Director dienen soll. Bei einem Directorpool führen Sie den Lync Server-Bereitstellungs-Assistenten auf jedem Server aus, der ein Mitglied des Pools sein wird.

## Topologien

Sie können einen einzelnen Director-Server oder einen Directorpool implementieren. Der Director ist stets ein separater Server oder Pool, der nicht gemeinsam mit anderen Serverrollen in Lync Server 2013 ausgeführt wird.


> [!NOTE]
> Wenn Sie keine Directors bereitstellen, übernimmt der Front-End-Server oder der Front-End-Pool die Director-Rolle.



Für einen Pool mit Directors muss ein Lastenausgleich ausgeführt werden. Führen Sie eine der folgenden Aktionen aus:

  - Erstellen Sie eine Topologie, die ein Hardwaregerät zum Lastenausgleich für Webdienste und einen DNS (Domain Name System)-Lastenausgleich für die anderen Datenverkehrstypen verwendet.
    
    [Skalierter Directorpool – DNS-Lastenausgleich und Hardwarelastenausgleich in Lync Server 2013](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md)

  - Erstellen Sie eine Topologie, die ein Hardwaregerät zum Lastenausgleich, um den erforderlichen Lastenausgleich für den Directorpool auszuführen.
    
    [Skalierter Directorpool (Hardwarelastenausgleich) in Lync Server 2013](lync-server-2013-scaled-director-pool-hardware-load-balancer.md)

