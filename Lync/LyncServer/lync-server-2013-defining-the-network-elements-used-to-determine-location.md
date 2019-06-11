---
title: 'Lync Server 2013: Definieren der Netzwerkelemente, die zum Ermitteln des Standorts verwendet werden'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining the network elements used to determine location
ms:assetid: 7538779d-055d-44ed-8dd7-11c45fc1b9f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398567(v=OCS.15)
ms:contentKeyID: 48184508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 572e7e5392390e659b52853cb47e30f696c65e91
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832705"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-the-network-elements-used-to-determine-location-in-lync-server-2013"></a>Definieren der Netzwerkelemente, die zum Ermitteln des Standorts in lync Server 2013 verwendet werden

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-29_

Wenn Sie Ihre lync Server-Infrastruktur zur Unterstützung der automatischen Erkennung von clientstandorten einrichten, müssen Sie zunächst entscheiden, welche Netzwerkelemente Sie verwenden möchten, um Anrufern Standorte zuzuordnen. In lync Server 2013 können Sie die folgenden Layer 2-und Layer 3-Netzwerkelemente mit Speicherorten verknüpfen:

  - Adressen für drahtlosen Zugriffspunkt (BSSID, Basic Service Set Identification) (Layer 2)

  - LLDP-Switch-Port (Layer 2)

  - LLDP-Switch-Chassis-IDs (Layer 2)

  - IP-Subnetze (Layer 3)

  - Client-MAC-Adressen (Layer 2)

Die Netzwerkelemente werden gemäß ihrer Rangfolge aufgelistet. Wenn ein Client mithilfe von mehr als einem Netzwerkelement gefunden werden kann, verwendet lync Server die Rangfolge, um zu bestimmen, welcher Mechanismus verwendet werden soll.

Die folgenden Abschnitte enthalten weitere Einzelheiten zur Verwendung der einzelnen Netzwerkelemente.

<div>


> [!IMPORTANT]  
> Wenn Sie Netzwerkelemente verwenden, um Anrufern Standorte zuzuordnen, ist es äußerst wichtig, dass Sie die Datenbank des Standort Informationsdiensts auf dem neuesten Stand halten. Wenn Sie beispielsweise ein Netzwerkelement hinzufügen oder ändern (z. B. einen drahtlosen Zugriffspunkt), müssen Sie den alten Eintrag löschen und den neuen Eintrag in der Standortdatenbank hinzufügen.



</div>

<div>

## <a name="wireless-access-point"></a>Drahtloser Zugriffspunkt

Wenn ein Client drahtlos eine Verbindung mit dem Netzwerk herstellt, verwendet die standortanforderung die BSSID-Adresse des WAP, um dessen Standort festzulegen. Wenn der Client Roaming hat, ist der angezeigte WAP möglicherweise nicht der nächstgelegene, und es ist sogar möglich, einen WAP aufzunehmen, der sich auf einer anderen Etage des Gebäudes befindet. Um anzugeben, dass die Position Näherungswert ist, können Sie den Positionswert mit einem near-oder Close-Deskriptor voranstellen.

Bei dieser Standortmethode wird davon ausgegangen, dass die BSSID der einzelnen Zugriffspunkte statisch ist. Wenn der Zugriffspunktanbieter jedoch dynamisch zugewiesene BSSIDs verwendet, könnte sich die von einem Zugriffspunkt erhaltene BSSID ändern (dies kann beispielsweise bei einer Konfigurationsänderung für den Zugriffspunkt auftreten) und könnte für die drahtlosen Clients die Situation auftreten, dass sie keinen Standort erhalten. Um diese Möglichkeit zu verhindern, müssen Sie die Datenbank für den standortinformationsdienst mit ERLs für alle möglichen BSSID-Adressen auffüllen, die von jedem WAP verwendet werden.

</div>

<div>

## <a name="lldp-ports-and-switches"></a>LLDP-Ports und -Switches

Verwaltete Ethernet-Switches, die LLDP-MED (Link Layer Discovery Protocol-Media Endpoint Discover) unterstützen, können die ID- und Portinformationen eines Netzwerks für einen kompatiblen LLDP-MED-Client bereitstellen, die dann wiederum bei der Standortdatenbank abgefragt werden, um den Standort des Geräts anzugeben. Sie können Erwartungsregellisten ausschließlich der Switch-Chassis-ID zuordnen oder sie alternativ auf Portebene zuweisen.

<div>


> [!NOTE]  
> Lync Server 2013 unterstützt die Verwendung von LLDP-MED zum Ermitteln von Speicherorten nur von lync Phone Edition-Geräten und lync 2013, die unter Windows 8 ausgeführt werden. Wenn Sie Layer 2-Daten auf switchebene verwenden müssen, um den Speicherort anderer auf einem drahtgebundenen PC basierender lync-Clients zu ermitteln, müssen Sie die Client-Mac-Adressen Methode verwenden.



</div>

</div>

<div>

## <a name="subnet"></a>Subnetz

Layer 3-IP-Subnetze stellen einen Mechanismus bereit, der von allen lync Server-Clients unterstützt wird, die zum automatischen Erkennen des Client Standorts verwendet werden können. Die Verwendung von IP-Subnetzen ist die einfachste Methode zur Ermittlung von Standorten, um verkabelte Clients zu konfigurieren und zu verwalten. Bevor Sie sich für die Verwendung von Subnetzen entscheiden, sollten Sie jedoch anhand der folgenden Fragen ermitteln, ob die Standortgenauigkeit des Subnetzes für eine präzise Ermittlung des Clientstandorts ausreicht:

  - Umfassen ein oder mehrere Client-Subnetze verschiedene Etagen?

  - Umfassen ein oder mehrere Subnetze mehrere Gebäude?

  - Welchen Etagenbereich umfassen die einzelnen Client-Subnetze?

Wenn das Subnetz einen zu großen Bereich umfasst, müssen Sie möglicherweise eine andere Methode zum Ermitteln der Clients verwenden. Es wird empfohlen, dass Kunden – sofern möglich – ihre IP-Subnetzverwendung neu anordnen, um die Anforderungen für die Standortgenauigkeit in Erwartungsregellisten zu erfüllen, statt die Kosten und Komplexität von SNMP-basierten Drittanbieter-Lösungen tragen zu müssen.

</div>

<div>

## <a name="client-mac-address"></a>Client-MAC-Adresse

Wenn Sie die Mac-Adresse eines Clientcomputers zum Auffinden eines Anrufers verwenden möchten, benötigen Sie verwaltete Ethernet-Switches, und Sie müssen eine SNMP-Lösung eines Drittanbieters bereitstellen, die die Mac-Adressen von lync-Clients ermitteln kann, die mit diesen Switches verbunden sind. Die SNMP-Lösung fragt kontinuierlich die verwalteten Switches ab, um die aktuellen Zuordnungen der Endpunkt-Mac-Adressen abzurufen, die mit jedem Port verbunden sind, und ruft die entsprechenden Port-IDs ab. Während der Anforderung eines lync-Clients an den standortinformationsdienst fragt der standortinformationsdienst die Drittanbieteranwendung mithilfe der Mac-Adresse des Clients ab und gibt dann alle übereinstimmenden Switch-IP-Adressen und Port-IDs zurück. Der standortinformationsdienst verwendet diese Informationen, um seinen veröffentlichten Layer 2-Wiremap nach einem übereinstimmenden Datensatz abzufragen, und gibt den Speicherort an den Client zurück. Wenn Sie diese Option verwenden, stellen Sie sicher, dass die Switch-Port-IDs zwischen der SNMP-Anwendung und den veröffentlichten Speicherort-Datensätzen konsistent sind.

<div>


> [!NOTE]  
> Einige SNMP-Lösungen von Drittanbietern können nicht verwaltete Zugriffs Schalter unterstützen. Wenn der Switch, der den lync-Client nicht verwaltet, aber über einen Uplink zu einem verwalteten Verteilungs Schalter verfügt, kann der verwaltete Switch der SNMP-Anwendung die Mac-Adressen der Clients melden, die mit dem Zugriffs Schalter verbunden sind. Mithilfe dieser Informationen kann der standortinformationsdienst den Standort des Benutzers ermitteln. Es ist jedoch möglich, allen Anschlüssen des nicht verwalteten Switches nur ein einzelnes Erl zuzuweisen, sodass die Standort Spezifität nur auf der Chassis-Ebene des Zugriffs Schalters und nicht auf der Portebene verfügbar ist.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

