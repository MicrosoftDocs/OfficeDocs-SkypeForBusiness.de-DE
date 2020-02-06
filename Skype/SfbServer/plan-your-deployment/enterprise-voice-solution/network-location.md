---
title: Definieren der Netzwerkelemente, die zum Ermitteln des Standorts in Skype for Business Server verwendet werden
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7538779d-055d-44ed-8dd7-11c45fc1b9f5
description: Entscheidungen, die für die Planung der Netzwerkkomponenten erforderlich sind, die Sie für die Zuordnung von Anrufern zu Speicherorten für die E9-1-1-Bereitstellung in Skype for Business Server Enterprise-VoIP verwenden.
ms.openlocfilehash: 404ac2d151f367ad391e4d5426090f20448cc383
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802665"
---
# <a name="define-the-network-elements-used-to-determine-location-in-skype-for-business-server"></a>Definieren der Netzwerkelemente, die zum Ermitteln des Standorts in Skype for Business Server verwendet werden
 
Entscheidungen, die für die Planung der Netzwerkkomponenten erforderlich sind, die Sie für die Zuordnung von Anrufern zu Speicherorten für die E9-1-1-Bereitstellung in Skype for Business Server Enterprise-VoIP verwenden.
  
Wenn Sie Ihre Skype for Business Server-Infrastruktur zur Unterstützung der automatischen Erkennung von clientstandorten einrichten, müssen Sie zunächst entscheiden, welche Netzwerkelemente Sie für die Zuordnung von Anrufern zu Speicherorten verwenden möchten. In Skype for Business Server können Sie die folgenden Layer 2-und Layer 3-Netzwerkelemente mit Speicherorten verknüpfen:
  
- Adressen für drahtlosen Zugriffspunkt (BSSID, Basic Service Set Identification) (Layer 2)
    
- LLDP-Switch-Port (Layer 2)
    
- LLDP-Switch-Chassis-IDs (Layer 2)
    
- IP-Subnetze (Layer 3)
    
- Client-MAC-Adressen (Layer 2)
    
Die Netzwerkelemente werden gemäß ihrer Rangfolge aufgelistet. Wenn ein Client mit mehr als einem Netzwerkelement gefunden werden kann, verwendet Skype for Business Server die Rangfolge, um zu bestimmen, welcher Mechanismus verwendet werden soll. 
  
Die folgenden Abschnitte enthalten weitere Einzelheiten zur Verwendung der einzelnen Netzwerkelemente.
  
> [!IMPORTANT]
> Wenn Sie Netzwerkelemente verwenden, um Anrufern Standorte zuzuordnen, ist es äußerst wichtig, dass Sie die Datenbank des Standort Informationsdiensts auf dem neuesten Stand halten. Wenn Sie beispielsweise ein Netzwerkelement hinzufügen oder ändern (z. B. einen drahtlosen Zugriffspunkt), müssen Sie den alten Eintrag löschen und den neuen Eintrag in der Standortdatenbank hinzufügen. 
  
## <a name="wireless-access-point"></a>Drahtloser Zugriffspunkt

Wenn ein Client drahtlos eine Verbindung mit dem Netzwerk herstellt, verwendet die standortanforderung die BSSID-Adresse des WAP, um dessen Standort festzulegen. Wenn der Client Roaming hat, ist der angezeigte WAP möglicherweise nicht der nächstgelegene, und es ist sogar möglich, einen WAP aufzunehmen, der sich auf einer anderen Etage des Gebäudes befindet. Um anzugeben, dass die Position Näherungswert ist, können Sie den Positionswert mit einem **[Near]** -oder **[Closet]** -Deskriptor voranstellen.
  
Bei dieser Standortmethode wird davon ausgegangen, dass die BSSID der einzelnen Zugriffspunkte statisch ist. Wenn Ihr WAP-Anbieter jedoch dynamisch zugewiesene BSSIDs verwendet, kann sich die BSSID, die von einem WAP abgerufen wird, ändern (Dies kann nach einer Änderung der WAP-Konfiguration geschehen), und drahtlose Clients können in einer Situation verbleiben, in der Sie keinen Standort erhalten. Um diese Möglichkeit zu verhindern, müssen Sie die Datenbank für den standortinformationsdienst mit ERLs für alle möglichen BSSID-Adressen auffüllen, die von jedem WAP verwendet werden. 
  
## <a name="lldp-ports-and-switches"></a>LLDP-Ports und -Switches

Verwaltete Ethernet-Switches, die LLDP-MED (Link Layer Discovery Protocol-Media Endpoint Discover) unterstützen, können die ID- und Portinformationen eines Netzwerks für einen kompatiblen LLDP-MED-Client bereitstellen, die dann wiederum bei der Standortdatenbank abgefragt werden, um den Standort des Geräts anzugeben. Sie können Erwartungsregellisten ausschließlich der Switch-Chassis-ID zuordnen oder sie alternativ auf Portebene zuweisen.
  
> [!NOTE]
> Skype for Business Server unterstützt die Verwendung von LLDP-MED zum Ermitteln von Speicherorten nur von lync Phone Edition-Geräten und Skype for Business-Clients, die unter Windows 8 ausgeführt werden. Wenn Sie Layer 2-Daten auf Switch-Ebene verwenden müssen, um den Standort anderer kabelgebundener PC-basierter Skype for Business Server-Clients zu ermitteln, müssen Sie die Client-Mac-Adressen Methode verwenden. 
  
## <a name="subnet"></a>Subnetz

Layer 3-IP-Subnetze bieten einen Mechanismus, der von allen Skype for Business Server-Clients unterstützt wird, die zum automatischen Erkennen des Client Standorts verwendet werden können. Die Verwendung von IP-Subnetzen ist die einfachste Methode zur Ermittlung von Standorten, um verkabelte Clients zu konfigurieren und zu verwalten. Bevor Sie sich für die Verwendung von Subnetzen entscheiden, sollten Sie jedoch anhand der folgenden Fragen ermitteln, ob die Standortgenauigkeit des Subnetzes für eine präzise Ermittlung des Clientstandorts ausreicht:
  
- Umfassen ein oder mehrere Client-Subnetze verschiedene Etagen?
    
- Umfassen ein oder mehrere Subnetze mehrere Gebäude?
    
- Welchen Etagenbereich umfassen die einzelnen Client-Subnetze?
    
Wenn das Subnetz einen zu großen Bereich umfasst, müssen Sie möglicherweise eine andere Methode zum Ermitteln der Clients verwenden. Es wird empfohlen, dass Kunden – sofern möglich – ihre IP-Subnetzverwendung neu anordnen, um die Anforderungen für die Standortgenauigkeit in Erwartungsregellisten zu erfüllen, statt die Kosten und Komplexität von SNMP-basierten Drittanbieter-Lösungen tragen zu müssen.
  
## <a name="client-mac-address"></a>Client-MAC-Adresse

Wenn Sie die Mac-Adresse eines Clientcomputers zum Auffinden eines Anrufers verwenden möchten, benötigen Sie verwaltete Ethernet-Switches, und Sie müssen eine SNMP-Lösung eines Drittanbieters bereitstellen, die die Mac-Adressen von Skype for Business-Clients ermitteln kann, die mit diesen Switches verbunden sind. Die SNMP-Lösung fragt kontinuierlich die verwalteten Switches ab, um die aktuellen Zuordnungen der Endpunkt-Mac-Adressen abzurufen, die mit jedem Port verbunden sind, und ruft die entsprechenden Port-IDs ab. Während der Anforderung eines Skype for Business-Clients an den standortinformationsdienst fragt der standortinformationsdienst die Drittanbieteranwendung mithilfe der Mac-Adresse des Clients ab und gibt dann alle übereinstimmenden Switch-IP-Adressen und Port-IDs zurück. Der standortinformationsdienst verwendet diese Informationen, um seinen veröffentlichten Layer 2-Wiremap nach einem übereinstimmenden Datensatz abzufragen, und gibt den Speicherort an den Client zurück. Wenn Sie diese Option verwenden, stellen Sie sicher, dass die Switch-Port-IDs zwischen der SNMP-Anwendung und den veröffentlichten Speicherort-Datensätzen konsistent sind.
  
> [!NOTE]
> Einige SNMP-Lösungen von Drittanbietern können nicht verwaltete Zugriffs Schalter unterstützen. Wenn der Switch, der den Skype for Business-Client nicht verwaltet, aber über einen Uplink zu einem verwalteten Verteilungs Schalter verfügt, kann der verwaltete Switch der SNMP-Anwendung die Mac-Adressen der Clients melden, die mit dem Zugriffs Schalter verbunden sind. Mithilfe dieser Informationen kann der standortinformationsdienst den Standort des Benutzers ermitteln. Es ist jedoch möglich, allen Anschlüssen des nicht verwalteten Switches nur ein einzelnes Erl zuzuweisen, sodass die Standort Spezifität nur auf der Chassis-Ebene des Zugriffs Schalters und nicht auf der Portebene verfügbar ist. 
  

