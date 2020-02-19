---
title: 'Lync Server 2013: Datensammlung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Data collection
ms:assetid: e40b03e5-455d-4bbc-831a-c61b1380db53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399008(v=OCS.15)
ms:contentKeyID: 48185722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e198ecb80bbe0616422e10e1df18a8778196761
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138336"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="data-collection-in-lync-server-2013"></a>Datensammlung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-08_

In Microsoft lync Server 2013 Kommunikationssoftware können Sie das Planungs Tool Microsoft lync Server 2013 ausführen, ohne Ihre vorhandenen und vorgeschlagenen IP-Adressen und Edgeserver vollqualifizierten Domänennamen (FQDNs) zu dokumentieren, dies ist jedoch wesentlich schwieriger ohne Konfigurationsfehler zu verursachen. Wenn beispielsweise die Koexistenz für einen bestimmten Zeitraum erforderlich ist, besteht ein häufiger Fehler darin, FQDNs aus einer vorhandenen Edge-Bereitstellung für Ihre lync Server 2013-Edge-Bereitstellung wiederzuverwenden. Durch das aufschreiben vorhandener und vorgeschlagener IP-Adressen und FQDNs in einer Tabellenkalkulation, Tabelle oder in einem anderen visuellen Formular können Sie während der Installation Installationsprobleme vermeiden.

<div>


> [!WARNING]  
> Wenn Sie frühere Versionen des Planungstools verwendet haben, haben Sie das Tool möglicherweise zum Erstellen Ihrer Topologie und des exportierten Topologie-Dokuments zur Verwendung im Topologie-Generator zum Veröffentlichen Ihrer Topologie verwendet. Die Möglichkeit, die Topologie zu exportieren, wurde aus dem Planungs Tool entfernt. Das Verwenden einer früheren Version des Planungstools zum Erstellen eines Topologie-Dokuments für lync Server 2013 wird dringend empfohlen, und es werden unerwartete Ergebnisse erzielt.



</div>

Daher empfiehlt es sich, die folgende Daten Sammlungs Vorlage zu verwenden, die ihrer Edge-Topologie entspricht, um die verschiedenen FQDN-und IP-Adressen zu erfassen, die Sie in das Planungs Tool eingeben müssen. Durch das Dokumentieren der aktuellen und vorgeschlagenen Konfiguration können Sie die Werte in den richtigen Kontext für Ihre Produktionsumgebung setzen. Gleichzeitig müssen Sie die Konfiguration von Koexistenz und Features, wie z. B. einfachen URLs, Dateifreigaben und Lastenausgleich, planen.

Um Microsoft lync Server 2013 erfolgreich bereitzustellen, müssen Sie die Interaktion von und das Vertrauen auf die einzelnen Komponenten verstehen. Durch das Sammeln von Daten aus Ihrer vorhandenen Netzwerk-und Serverinfrastruktur und die Anwendung der Planungsanleitung in diesen Abschnitten können Sie lync Server 2013 Edgeserver-Komponenten in Ihre Infrastruktur integrieren.

Bei der [Auswahl einer Topologie in lync Server 2013](lync-server-2013-choosing-a-topology.md)werden drei Hauptarchitekturen mit zwei Variationen für insgesamt fünf mögliche Bereitstellungsszenarien eingeführt. Eines dieser Szenarien ist der Ausgangspunkt für die Datenerfassung. Die IP-Adressen, Servernamen und Domänennamen sind Beispiele, die den Zertifikat-, Firewall und DNS-Diagrammen entsprechen, welche die erforderlichen Informationen für eine umfassende Planungslösung enthalten. Die Diagramme und die Angabe der erforderlichen Werte für Zertifikate, DNS und Firewalls spielen bei der teamübergreifenden Kommunikation eine besonders wichtige Rolle, bei der die Verwaltung von Zertifizierungsstelle, Firewallkonfiguration und DNS von anderen Teams als dem Team, das die Bereitstellung plant, ausgeführt wird. Die Diagramme liefern Informationen zu erforderlichen Komponenten, die für die Weitergabe dieser Anforderungen für die teamübergreifende Zusammenarbeit verwendet werden können.

Die bereitgestellten Diagramme sind absichtlich generisch, ermöglichen jedoch die Sammlung aller relevanten Daten, die für die Kommunikation von Anforderungen in einem teamübergreifenden Szenario erforderlich wären, in dem Netzwerk, Firewall, Zertifikaterstellung und-Verwaltung, Server die Bereitstellung und die Serververwaltung werden von verschiedenen Gruppen verarbeitet. Die erforderlichen Details für die Konfiguration von Netzwerken, Firewalls, Ports und Protokollen, Zertifikaten und Servern sind von unschätzbarem Wert, wenn die Bereitstellung von lync Server fortgeschritten ist.

**Edgeserver und Edgepool**

![7624717a-ce99-4ae8-a929-2c4d74a2e47d](images/Gg399008.7624717a-ce99-4ae8-a929-2c4d74a2e47d(OCS.15).jpg "7624717a-ce99-4ae8-a929-2c4d74a2e47d")

**Reverseproxy**

![cf63fc50-2d11-4334-afc8-2d664ba1b6bb](images/Gg399008.cf63fc50-2d11-4334-afc8-2d664ba1b6bb(OCS.15).jpg "cf63fc50-2d11-4334-afc8-2d664ba1b6bb")

**Director oder Director-Pool**

![56ba29ff-1309-4d5d-bf5c-35372169e947](images/Gg399008.56ba29ff-1309-4d5d-bf5c-35372169e947(OCS.15).jpg "56ba29ff-1309-4d5d-bf5c-35372169e947")

</div>

<span> </span>

</div>

</div>

</div>

