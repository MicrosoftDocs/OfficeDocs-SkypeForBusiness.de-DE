---
title: 'Lync Server 2013: Datenerfassung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Data collection
ms:assetid: e40b03e5-455d-4bbc-831a-c61b1380db53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399008(v=OCS.15)
ms:contentKeyID: 48185722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df4f19df012dfeac7576cc5b39d749564a4350a1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832740"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="data-collection-in-lync-server-2013"></a>Datenerfassung in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-08_

In der Microsoft lync Server 2013-Kommunikationssoftware können Sie Microsoft lync Server 2013, Planungs Tool ausführen, ohne Ihre vorhandenen und vorgeschlagenen IP-Adressen und vollqualifizierten Domänennamen (FQDNs) für Edgeserver zu dokumentieren, doch ist dies wesentlich schwieriger ohne Konfigurationsfehler zu verursachen. Wenn beispielsweise die Koexistenz für eine bestimmte Zeitdauer erforderlich ist, besteht ein häufiger Fehler darin, FQDNs aus einer vorhandenen Edge-Bereitstellung für Ihre lync Server 2013-Edge-Bereitstellung wieder zu verwenden. Indem Sie die vorhandenen und vorgeschlagenen IP-Adressen und FQDNs in einer Tabelle, einer Tabelle oder einer anderen visuellen Form aufgeschrieben haben, können Sie während der Installation Setup Probleme verhindern.

<div>


> [!WARNING]  
> Wenn Sie frühere Versionen des Planungstools verwendet haben, haben Sie möglicherweise das Tool zum Erstellen Ihrer Topologie und des exportierten Topologie-Dokuments für die Verwendung in Topology Builder verwendet, um Ihre Topologie zu veröffentlichen. Die Möglichkeit, die Topologie zu exportieren, wurde aus dem Planungs Tool entfernt. Mit einer früheren Version des Planungstools zum Erstellen eines Topologie-Dokuments für lync Server 2013 wird dringend abgeraten, und es entstehen unerwartete Ergebnisse.



</div>

Daher empfiehlt es sich, die folgende Daten Sammlungs Vorlage, die ihrer Edge-Topologie entspricht, zu verwenden, um die verschiedenen FQDN-und IP-Adressen zu sammeln, die Sie in das Planungs Tool eingeben müssen. Indem Sie die aktuelle und vorgeschlagene Konfiguration dokumentieren, können Sie die Werte in den richtigen Kontext für Ihre Produktionsumgebung setzen. Und Sie müssen darüber nachdenken, wie Sie die Koexistenz und Features wie einfache URLs, Dateifreigaben und Lastenausgleich konfigurieren.

Damit Sie Microsoft lync Server 2013 erfolgreich bereitstellen können, müssen Sie sich mit der Interaktion und dem Vertrauen auf die einzelnen Komponenten vertraut machen. Wenn Sie Daten aus Ihrer vorhandenen Netzwerk-und Serverinfrastruktur sammeln und die Planungsanleitungen in diesen Abschnitten anwenden, können Sie die Komponenten von lync Server 2013-Edgeserver in Ihre Infrastruktur integrieren.

Bei der [Auswahl einer Topologie in lync Server 2013](lync-server-2013-choosing-a-topology.md)wurden drei Hauptarchitekturen mit zwei Variationen für insgesamt fünf mögliche Bereitstellungsszenarien vorgestellt. Eines dieser Szenarien ist der Ausgangspunkt für Ihre Datensammlung. Die IP-Adressen, Servernamen und Domänennamen sind Beispiele, die mit den entsprechenden Zertifikat-, Firewall-und DNS-Diagrammen übereinstimmen, die die für eine vollständige Planungslösung erforderlichen Informationen detailliert beschreiben. Die Diagramme und das Ausfüllen ihrer erforderlichen Zertifikat-, DNS-und firewallwerte sind besonders wichtig in teamübergreifenden Kommunikationen, bei denen die Verwaltung der Zertifizierungsstelle, die Firewall-Konfiguration und DNS von anderen Teams als dem Team verwaltet werden, das plant die Bereitstellung. Die Diagramme enthalten Informationen zu erforderlichen Komponenten, die verwendet werden können, um diese Anforderungen für die teamübergreifende Zusammenarbeit zu kommunizieren.

Die bereitgestellten Diagramme sind absichtlich generisch, ermöglichen jedoch die Sammlung aller relevanten Daten, die für die Kommunikation der Anforderungen in einem teamübergreifenden Szenario erforderlich sind, in dem Netzwerk, Firewall, Zertifikatserstellung und-Verwaltung, Server Bereitstellung und Serververwaltung werden von verschiedenen Gruppen gehandhabt. Die erforderlichen Details für die Konfiguration von Netzwerk, Firewalls, Ports und Protokollen, Zertifikaten und Servern sind von unschätzbarem Wert, wenn die Bereitstellung von lync Server im Gange ist.

**Edge-Server und Edge-Pool**

![7624717a-ce99-4ae8-A929-2c4d74a2e47d] (images/Gg399008.7624717a-ce99-4ae8-a929-2c4d74a2e47d(OCS.15).jpg "7624717a-ce99-4ae8-A929-2c4d74a2e47d")

**Reverseproxy**

![cf63fc50-2d11-4334-afc8-2d664ba1b6bb] (images/Gg399008.cf63fc50-2d11-4334-afc8-2d664ba1b6bb(OCS.15).jpg "cf63fc50-2d11-4334-afc8-2d664ba1b6bb")

**Director-oder Director-Pool**

![56ba29ff-1309-4d5d-bf5c-35372169e947] (images/Gg399008.56ba29ff-1309-4d5d-bf5c-35372169e947(OCS.15).jpg "56ba29ff-1309-4d5d-bf5c-35372169e947")

</div>

<span> </span>

</div>

</div>

</div>

