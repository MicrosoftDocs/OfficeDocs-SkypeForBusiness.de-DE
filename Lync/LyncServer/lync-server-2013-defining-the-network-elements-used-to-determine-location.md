---
title: 'Lync Server 2013: Definieren der zum Bestimmen des Standorts verwendeten Netzwerkelemente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the network elements used to determine location
ms:assetid: 7538779d-055d-44ed-8dd7-11c45fc1b9f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398567(v=OCS.15)
ms:contentKeyID: 48184508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6cfedb09cdcdebdc12cdd2aed69e56532dcca5ad
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504502"
---
# <a name="defining-the-network-elements-used-to-determine-location-in-lync-server-2013"></a>Definieren der Netzwerkelemente, die zum Bestimmen des Standorts in lync Server 2013 verwendet werden

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-29_

Wenn Sie Ihre lync Server-Infrastruktur für die Unterstützung der automatischen Clientstandort Erkennung einrichten, müssen Sie zunächst entscheiden, welche Netzwerkelemente Sie verwenden, um Anrufern Standorte zuzuordnen. In lync Server 2013 können Sie die folgenden Layer 2-und Layer 3-Netzwerkelemente mit Standorten verknüpfen:

  - Adressen für drahtlosen Zugriffspunk (BSSID, Basic Service Set Identification) (Layer 2)

  - LLDP-Switch-Port (Layer 2)

  - LLDP-Switch-Chassis-IDs (Layer 2)

  - IP-Subnetze (Layer 3)

  - Client-MAC-Adressen (Layer 2)

Die Netzwerkelemente werden gemäß ihrer Rangfolge aufgelistet. Wenn ein Client mit mehr als einem Netzwerkelement gefunden werden kann, verwendet lync Server die Rangfolge, um den zu verwendenden Mechanismus zu ermitteln.

Die folgenden Abschnitte enthalten weitere Einzelheiten zur Verwendung der einzelnen Netzwerkelemente.

<div>


> [!IMPORTANT]  
> Wenn Sie Netzwerkelemente zum Zuordnen von Anrufern zu Standorten verwenden, ist es äußerst wichtig, dass Sie die Standortinformationsdienst-Datenbank auf dem neuesten Stand halten. Wenn Sie beispielsweise ein Netzwerkelement hinzufügen oder ändern (angenommen Sie fügen z. B. einen drahtlosen Zugriffspunkt hinzu), müssen Sie den alten Eintrag löschen und den neuen Eintrag in der Standortdatenbank hinzufügen.



</div>

<div>

## <a name="wireless-access-point"></a>Drahtloser Zugriffspunkt

Wenn ein Client drahtlos eine Verbindung mit dem Netzwerk herstellt, verwendet die standortanforderung die BSSID-Adresse des WAP, um den Speicherort zu ermitteln. Wenn der Client Roaming durchführt, ist der angegebene WAP möglicherweise nicht der nächste, und es ist sogar möglich, einen WAP auf einem anderen Stockwerk des Gebäudes zu holen. Um anzugeben, dass der Speicherort ungefähr ist, können Sie den Location-Wert mit einem near-oder Close-to-Deskriptor voranstellen.

Bei dieser Standortmethode wird davon ausgegangen, dass die BSSID der einzelnen Zugriffspunkte statisch ist. Wenn der Zugriffspunktanbieter jedoch dynamisch zugewiesene BSSIDs verwendet, könnte sich die von einem Zugriffspunkt erhaltene BSSID ändern (dies kann beispielsweise bei einer Konfigurationsänderung für den Zugriffspunkt auftreten) und für die drahtlosen Clients könnte die Situation auftreten, dass sie keinen Standort erhalten. Um diese Möglichkeit zu verhindern, müssen Sie die Standortinformationsdienst Datenbank mit ERLs für alle möglichen BSSID-Adressen auffüllen, die von den einzelnen WAP-Adressen verwendet werden.

</div>

<div>

## <a name="lldp-ports-and-switches"></a>LLDP-Ports und -Switches

Verwaltete Ethernet-Switches, die LLDP-MED (Link Layer Discovery Protocol-Media Endpoint Discover) unterstützen, können die ID- und Portinformationen eines Netzwerks für einen kompatiblen LLDP-MED-Client bereitstellen, die dann wiederum bei der Standortdatenbank abgefragt werden, um den Standort des Geräts anzugeben. Sie können Erwartungsregellisten ausschließlich der Switch-Chassis-ID zuordnen oder sie alternativ auf Portebene zuweisen.

<div>


> [!NOTE]  
> Lync Server 2013 unterstützt die Verwendung von LLDP-MED zur Bestimmung von Speicherorten nur für lync Phone Edition-Geräte und lync 2013, die auf Windows 8 durchführen. Wenn Sie Layer 2-Daten auf switchebene verwenden müssen, um den Speicherort anderer drahtgebundener PC-basierter lync-Clients zu ermitteln, müssen Sie die Client MAC-Adress Methode verwenden.



</div>

</div>

<div>

## <a name="subnet"></a>Subnetz

Layer 3-IP-Subnetze bieten einen Mechanismus, der von allen lync Server-Clients unterstützt wird, die zum automatischen Erkennen des Client Standorts verwendet werden können. Die Verwendung von IP-Subnetzen ist die einfachste Methode zur Ermittlung von Standorten, um verkabelte Clients zu konfigurieren und zu verwalten. Bevor Sie sich für die Verwendung von Subnetzen entscheiden, sollten Sie jedoch anhand der folgenden Fragen ermitteln, ob die Standortgenauigkeit des Subnetzes für eine präzise Ermittlung des Clientstandorts ausreicht:

  - Umfassen ein oder mehrere Client-Subnetze verschiedene Etagen?

  - Umfassen ein oder mehrere Subnetze mehrere Gebäude?

  - Welchen Etagenbereich umfassen die einzelnen Client-Subnetze?

Wenn das Subnetz einen zu großen Bereich umfasst, müssen Sie möglicherweise eine andere Methode zum Ermitteln der Clients verwenden. Es wird empfohlen, sofern möglich, dass Kunden ihre IP-Subnetzverwendung neu anordnen, um die Anforderungen für die Standortgenauigkeit in Erwartungsregellisten zu erfüllen, statt die Kosten und Komplexität von SNMP-basierten Drittanbieter-Lösungen tragen zu müssen.

</div>

<div>

## <a name="client-mac-address"></a>Client-MAC-Adresse

Um die Mac-Adresse eines Clientcomputers zum Auffinden eines Anrufers zu verwenden, benötigen Sie Managed Ethernet Switches und müssen eine Drittanbieter-SNMP-Lösung bereitstellen, mit der die Mac-Adressen von lync-Clients ermittelt werden, die mit diesen Switches verbunden sind (oder über diese). Die SNMP-Lösung fragt kontinuierlich die verwalteten Switches ab, um die aktuellen Zuordnungen der Endpunkt-Mac-Adressen abzurufen, die mit jedem Port verbunden sind, und ruft die entsprechenden Port-IDs ab. Während der Anforderung eines lync-Clients an den Standortinformationsdienst fragt der Standortinformationsdienst die Drittanbieteranwendung mithilfe der Mac-Adresse des Clients ab und gibt dann alle übereinstimmenden Switch-IP-Adressen und Port-IDs zurück. Der Standortinformationsdienst verwendet diese Informationen zum Abfragen seiner veröffentlichten Schicht 2-Wiremap nach einem übereinstimmenden Datensatz und gibt den Speicherort an den Client zurück. Wenn Sie diese Option verwenden, stellen Sie sicher, dass die Switch-Port-IDs zwischen der SNMP-Anwendung und den veröffentlichten Datensätzen der Speicherort Datenbank konsistent sind.

<div>


> [!NOTE]  
> Einige SNMP-Lösungen von Drittanbietern können nicht verwaltete Zugriffs Switches unterstützen. Wenn der Switch, von dem der lync-Client verwaltet wird, aber über einen Uplink an eine verwaltete Verteilungsoption verfügt, kann der verwaltete Switch der SNMP-Anwendung die Mac-Adressen der mit dem Zugriffs Schalter verbundenen Clients zurückerstatten. Mithilfe dieser Informationen kann der Standortinformationsdienst den Speicherort des Benutzers ermitteln. Es ist jedoch möglich, allen Ports auf dem nicht verwalteten Switch nur ein einzelnes Erl zuzuweisen, sodass die Standort Spezifität nur auf der Chassis-Ebene des Zugriffs Switches und nicht auf der Portebene zur Verfügung steht.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

