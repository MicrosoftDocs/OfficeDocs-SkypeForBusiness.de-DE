---
title: 'Lync Server 2013: Definieren der Netzwerkelemente zum Ermitteln des Standorts'
TOCTitle: Definieren der Netzwerkelemente zum Ermitteln des Standorts
ms:assetid: 7538779d-055d-44ed-8dd7-11c45fc1b9f5
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398567(v=OCS.15)
ms:contentKeyID: 49294437
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Definieren der Netzwerkelemente zum Ermitteln des Standorts in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-29_

Wenn Sie Ihre Lync Server-Infrastruktur für die Unterstützung der automatischen Ermittlung von Clientstandorten einrichten, müssen Sie zunächst festlegen, welche Netzwerkelemente für die Zuordnung von Aufrufern zu Standorten verwendet werden sollen. In Lync Server 2013 können Standorten die folgenden Netzwerkelemente aus Layer 2 und 3 zugeordnet werden:

  - Adressen für drahtlosen Zugriffspunk (BSSID, Basic Service Set Identification) (Layer 2)

  - LLDP-Switch-Port (Layer 2)

  - LLDP-Switch-Chassis-IDs (Layer 2)

  - IP-Subnetze (Layer 3)

  - Client-MAC-Adressen (Layer 2)

Die Netzwerkelemente werden gemäß ihrer Rangfolge aufgelistet. Wenn der Standort eines Clients anhand mehrerer Netzwerkelemente ermittelt werden kann, bestimmt Lync Server anhand dieser Rangfolge, welcher Mechanismus verwendet wird.

Die folgenden Abschnitte enthalten weitere Einzelheiten zur Verwendung der einzelnen Netzwerkelemente.


> [!IMPORTANT]
> Wenn Sie Netzwerkelemente für die Zuordnung von Aufrufern zu Standorten verwenden, muss unbedingt darauf geachtet werden, dass die Standortinformationsdienst-Datenbank auf dem aktuellen Stand gehalten wird. Wenn Sie beispielsweise ein Netzwerkelement hinzufügen oder ändern (angenommen Sie fügen z. B. einen drahtlosen Zugriffspunkt hinzu), müssen Sie den alten Eintrag löschen und den neuen Eintrag in der Standortdatenbank hinzufügen.



## Drahtloser Zugriffspunkt

Wenn ein Client eine drahtlose Verbindung mit dem Netzwerk herstellt, bestimmt die Standortanforderung den Standort anhand der BSSID-Adresse des drahtlosen Zugriffspunkts, mit dem der Client verbunden ist. Wenn der Client einen Roamingdienst verwendet, handelt es sich dabei möglicherweise nicht um den nächstgelegenen drahtlosen Zugriffspunkt. Stattdessen ist es sogar möglich, dass ein drahtloser Zugriffspunkt ausgewählt wird, der sich in einer anderen Etage des Gebäudes befindet. Um darauf hinzuweisen, dass die Standortangabe nicht präzise ist, können Sie dem Standort einen Deskriptor wie Near oder Close to voranstellen.

Bei dieser Standortmethode wird davon ausgegangen, dass die BSSID der einzelnen Zugriffspunkte statisch ist. Wenn der Zugriffspunktanbieter jedoch dynamisch zugewiesene BSSIDs verwendet, könnte sich die von einem Zugriffspunkt erhaltene BSSID ändern (dies kann beispielsweise bei einer Konfigurationsänderung für den Zugriffspunkt auftreten) und für die drahtlosen Clients könnte die Situation auftreten, dass sie keinen Standort erhalten. Sie können diese Möglichkeit ausschließen, indem Sie die Standortinformationsdienst-Datenbanken für alle möglichen BSSID-Adressen, die von den einzelnen Zugriffspunkten verwendet werden, mit Erwartungsregellisten auffüllen.

## LLDP-Ports und -Switches

Verwaltete Ethernet-Switches, die LLDP-MED (Link Layer Discovery Protocol-Media Endpoint Discover) unterstützen, können die ID- und Portinformationen eines Netzwerks für einen kompatiblen LLDP-MED-Client bereitstellen, die dann wiederum bei der Standortdatenbank abgefragt werden, um den Standort des Geräts anzugeben. Sie können Erwartungsregellisten ausschließlich der Switch-Chassis-ID zuordnen oder sie alternativ auf Portebene zuweisen.


> [!NOTE]
> In Lync Server 2013 wird die Verwendung von LLDP-MED zur Bestimmung der Standorte nur für Lync Phone Edition-Geräte und Lync 2013 bei einer Ausführung unter Windows&nbsp;8 unterstützt. Wenn Sie Layer-2-Daten auf Switchebene verwenden müssen, um den Standort anderer verkabelter PC-basierter Lync-Clients zu ermitteln, müssen Sie die Client-MAC-Adressen-Methode verwenden.



## Subnetz

Layer-3-IP-Subnetze bieten einen allgemeinen Mechanismus für die automatische Ermittlung von Clientstandorten, der von allen Lync Server-Clients unterstützt wird. Die Verwendung von IP-Subnetzen ist die einfachste Methode zur Ermittlung von Standorten, um verkabelte Clients zu konfigurieren und zu verwalten. Bevor Sie sich für die Verwendung von Subnetzen entscheiden, sollten Sie jedoch anhand der folgenden Fragen ermitteln, ob die Standortgenauigkeit des Subnetzes für eine präzise Ermittlung des Clientstandorts ausreicht:

  - Umfassen ein oder mehrere Client-Subnetze verschiedene Etagen?

  - Umfassen ein oder mehrere Subnetze mehrere Gebäude?

  - Welchen Etagenbereich umfassen die einzelnen Client-Subnetze?

Wenn das Subnetz einen zu großen Bereich umfasst, müssen Sie möglicherweise eine andere Methode zum Ermitteln der Clients verwenden. Es wird empfohlen, sofern möglich, dass Kunden ihre IP-Subnetzverwendung neu anordnen, um die Anforderungen für die Standortgenauigkeit in Erwartungsregellisten zu erfüllen, statt die Kosten und Komplexität von SNMP-basierten Drittanbieter-Lösungen tragen zu müssen.

## Client-MAC-Adresse

Wenn Sie die MAC-Adresse eines Clientcomputers zum Ermitteln des Aufrufers verwenden möchten, benötigen Sie verwaltete Ethernet-Switches. Außerdem müssen Sie eine Drittanbieter-SNMP-Lösung bereitstellen, die die MAC-Adressen von Lync-Clients ermittelt, die mit (oder über) diese Switches verbunden sind. Die SNMP-Lösung fragt kontinuierlich die verwalteten Switches ab, um die aktuelle Zuordnung der Endpunkt-MAC-Adressen zu erhalten, die mit den einzelnen Ports verbunden sind, und ermittelt die zugehörigen Port-IDs. Bei einer Lync-Client-Anforderung an den Standortinformationsdienst fragt der Standortinformationsdienst unter Verwendung der Client-MAC-Adresse die Drittanbieteranwendung ab und gibt übereinstimmende IP-Adressen und Port-IDs zurück. Der Standortinformationsdienst verwendet diese Informationen, um seine veröffentlichte Layer-2-Standortzuordnung nach einem übereinstimmenden Datensatz abzufragen, und gibt den Standort des Clients zurück. Bei Verwendung dieser Option müssen Sie sicherstellen, dass die Switch-Port-Identifizierer zwischen der SNMP-Anwendung und den Datenbankeinträgen zu den veröffentlichten Standorten konsistent sind.


> [!NOTE]
> Einige Drittanbieter-SNMP-Lösungen unterstützen auch nicht verwaltete Zugriffsswitches. Wenn der Switch, der Informationen für den Lync-Client bereitstellt, nicht verwaltet ist, aber über einen Uplink zu einem verwalteten Verteilerswitch verfügt, kann der verwaltete Switch die MAC-Adressen der Clients an die SNMP-Anwendung zurückmelden, die mit dem Zugriffsswitch verbunden sind. Anhand dieser Informationen kann der Standortinformationsdienst den Standort des Benutzers ermitteln. Es ist auch möglich, nur eine einzelne Erwartungsregelliste für alle Ports in einem nicht verwalteten Switch zuzuweisen. In diesem Fall ist die Standortgenauigkeit nur auf Chassis-Ebene des Zugriffsswitchs und nicht auf Portebene verfügbar.


