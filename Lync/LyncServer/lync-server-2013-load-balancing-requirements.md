---
title: Anforderungen an den Lastenausgleich für Lync Server 2013
TOCTitle: Anforderungen an den Lastenausgleich für Lync Server 2013
ms:assetid: 84489328-64a4-486c-9384-a3e5c8ed9c8b
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg615011(v=OCS.15)
ms:contentKeyID: 49294609
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anforderungen an den Lastenausgleich für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-05_

Wenn Sie über Front-End-Pools, Director-Pools oder Edgeserver-Pools verfügen, müssen Sie für diese Pools einen Lastenausgleich bereitstellen. Beim Lastenausgleich wird der Datenverkehr auf die Server in einem Pool verteilt.

Lync Server 2013 unterstützt zwei Lösungen für den Lastenausgleich für Datenverkehr vom Client zum Server: DNS-Lastenausgleich (Domain Name System) und Hardwaregerät zum Lastenausgleich. Der DNS-Lastenausgleich bietet mehrere Vorteile wie einfache Verwaltung, effizientere Problembehandlung und die Möglichkeit, einen Großteil des Lync Server-Datenverkehrs bei potenziellen Problemen mit dem Hardwaregerät zum Lastenausgleich zu isolieren.

Entscheiden Sie, welche Lösung für den Lastenausgleich für die einzelnen Pools in der Bereitstellung jeweils geeignet ist, und beachten Sie dabei die folgenden Einschränkungen:

  - Für die interne Edgeschnittstelle und die externe Edgeschnittstelle muss derselbe Typ von Lastenausgleich verwendet werden. Es ist nicht möglich, für eine Edgeschnittstelle den DNS-Lastenausgleich und für die andere Edgeschnittstelle ein Hardwaregerät zum Lastenausgleich zu verwenden.

  - Für einige Arten von Datenverkehr ist ein Hardwaregerät zum Lastenausgleich erforderlich. HTTP-Datenverkehr erfordert beispielsweise ein Hardwaregerät zum Lastenausgleich anstatt eines DNS-Lastenausgleichs. Der DNS-Lastenausgleich funktioniert nicht beim Client-zu-Server-Datenverkehr.

Ausführliche Informationen zum Auswählen einer Lösung mit einem Hardwaregerät zum Lastenausgleich finden Sie unter [Anforderungen an das Hardwaregerät zum Lastenausgleich für Lync Server 2013](lync-server-2013-hardware-load-balancer-requirements.md).

Wenn Sie für einen Pool den DNS-Lastenausgleich verwenden möchten, aber dennoch Hardwaregeräte zum Lastenausgleich benötigen, beispielsweise für den HTTP-Datenverkehr, ist die Verwaltung der Hardwaregeräte zum Lastenausgleich jetzt erheblich einfacher. Ein Beispiel hierfür ist, dass ausschließlich der HTTP- und HTTPS-Datenverkehr verwaltet wird, während alle anderen Protokolle vom DNS-Lastenausgleich verwaltet werden. Ausführliche Informationen finden Sie unter [DNS-Lastenausgleich in Lync Server 2013](lync-server-2013-dns-load-balancing.md).

Für den Datenverkehr von Server zu Server verwendet Lync Server 2013 einen topologieerkennenden Lastenausgleich. Server lesen die veröffentlichte Topologie im zentralen Verwaltungsspeicher, um die FQDNs von Servern in der Topologie abzurufen, und verteilen den Datenverkehr automatisch unter den Servern. Administratoren müssen diese Art des Lastenausgleichs weder konfigurieren noch verwalten.

Wenn Sie den DNS-Lastenausgleich verwenden und den Datenverkehr für einen bestimmten Computer blockieren müssen, reicht es nicht aus, einfach nur die IP-Adresseinträge aus dem Pool-FQDN zu entfernen. Sie müssen auch den DNS-Eintrag für den Computer entfernen.

