---
title: Definieren sie die Netzwerkelemente, die verwendet werden, um den Standort in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7538779d-055d-44ed-8dd7-11c45fc1b9f5
description: Entscheidungen, die für die Planung der Netzwerkkomponenten erforderlich sind, mit denen Anrufer Standorten für die E9-1-1-Bereitstellung in Skype for Business Server Enterprise-VoIP zugeordnet werden.
ms.openlocfilehash: 6de3d960dd68dfc0f34ce0e67fef569c36e44612
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60861112"
---
# <a name="define-the-network-elements-used-to-determine-location-in-skype-for-business-server"></a>Definieren sie die Netzwerkelemente, die verwendet werden, um den Standort in Skype for Business Server
 
Entscheidungen, die für die Planung der Netzwerkkomponenten erforderlich sind, mit denen Anrufer Standorten für die E9-1-1-Bereitstellung in Skype for Business Server Enterprise-VoIP zugeordnet werden.
  
Wenn Sie Ihre Skype for Business Server-Infrastruktur einrichten, um die automatische Erkennung von Clientstandorten zu unterstützen, müssen Sie zunächst entscheiden, welche Netzwerkelemente Sie zum Zuordnen von Anrufern zu Standorten verwenden möchten. In Skype for Business Server können Sie die folgenden Layer 2- und Layer 3-Netzwerkelemente Speicherorten zuordnen:
  
- Adressen für drahtlosen Zugriffspunk (BSSID, Basic Service Set Identification) (Layer 2)
    
- LLDP-Switch-Port (Layer 2)
    
- LLDP-Switch-Chassis-IDs (Layer 2)
    
- IP-Subnetze (Layer 3)
    
- Client-MAC-Adressen (Layer 2)
    
Die Netzwerkelemente werden gemäß ihrer Rangfolge aufgelistet. Wenn ein Client mit mehr als einem Netzwerkelement gefunden werden kann, verwendet Skype for Business Server die Rangfolge, um zu bestimmen, welcher Mechanismus verwendet werden soll. 
  
Die folgenden Abschnitte enthalten weitere Einzelheiten zur Verwendung der einzelnen Netzwerkelemente.
  
> [!IMPORTANT]
> Wenn Sie Netzwerkelemente zum Zuordnen von Anrufern zu Standorten verwenden, ist es von entscheidender Bedeutung, dass Sie die Standortinformationsdienst-Datenbank auf dem neuesten Stand halten. Wenn Sie beispielsweise ein Netzwerkelement hinzufügen oder ändern (angenommen Sie fügen z. B. einen drahtlosen Zugriffspunkt hinzu), müssen Sie den alten Eintrag löschen und den neuen Eintrag in der Standortdatenbank hinzufügen. 
  
## <a name="wireless-access-point"></a>Drahtloser Zugriffspunkt

Wenn ein Client drahtlos eine Verbindung mit dem Netzwerk herstellt, verwendet die Standortanforderung die BSSID-Adresse des WAP, um seinen Standort zu bestimmen. Wenn der Client roamingt, ist die angegebene WAP möglicherweise nicht die nächstgelegene, und es ist sogar möglich, einen WAP auf einer anderen Ebene des Gebäudes zu verwenden. Um anzugeben, dass es sich um eine ungefähre Position handelt, können Sie dem Standortwert einen **[Near]-** oder **[Closeto]-Deskriptor** voranstellen.
  
Bei dieser Standortmethode wird davon ausgegangen, dass die BSSID der einzelnen Zugriffspunkte statisch ist. Wenn Ihr WAP-Anbieter jedoch dynamisch zugewiesene BSSIDs verwendet, kann sich die BSSID, die von einem WAP abgerufen wird, ändern (dies kann nach einer ÄNDERUNG der WAP-Konfiguration passieren), und Drahtlose Clients könnten in einer Situation bleiben, in der sie keinen Standort erhalten. Um diese Möglichkeit zu verhindern, müssen Sie die Standortinformationsdienstdatenbank mit ERLs für alle möglichen BSSID-Adressen auffüllen, die von jedem WAP verwendet werden. 
  
## <a name="lldp-ports-and-switches"></a>LLDP-Ports und -Switches

Verwaltete Ethernet-Switches, die LLDP-MED (Link Layer Discovery Protocol-Media Endpoint Discover) unterstützen, können die ID- und Portinformationen eines Netzwerks für einen kompatiblen LLDP-MED-Client bereitstellen, die dann wiederum bei der Standortdatenbank abgefragt werden, um den Standort des Geräts anzugeben. Sie können Erwartungsregellisten ausschließlich der Switch-Chassis-ID zuordnen oder sie alternativ auf Portebene zuweisen.
  
> [!NOTE]
> Skype for Business Server unterstützt die Verwendung von LLDP-MED zum Ermitteln von Speicherorten nur von Lync Telefon Edition-Geräten und Skype for Business Clients, die auf Windows 8 ausgeführt werden. Wenn Sie Layer 2-Daten auf Switchebene verwenden müssen, um den Speicherort anderer kabelgebundener PC-basierter Skype for Business Server-Clients zu ermitteln, müssen Sie die Mac-Clientadressenmethode verwenden. 
  
## <a name="subnet"></a>Subnetz

Ip-Subnetze der Ebene 3 bieten einen Mechanismus, der von allen Skype for Business Server-Clients unterstützt wird und verwendet werden kann, um den Clientstandort automatisch zu erkennen. Die Verwendung von IP-Subnetzen ist die einfachste Methode zur Ermittlung von Standorten, um verkabelte Clients zu konfigurieren und zu verwalten. Bevor Sie sich für die Verwendung von Subnetzen entscheiden, sollten Sie jedoch anhand der folgenden Fragen ermitteln, ob die Standortgenauigkeit des Subnetzes für eine präzise Ermittlung des Clientstandorts ausreicht:
  
- Umfassen ein oder mehrere Client-Subnetze verschiedene Etagen?
    
- Umfassen ein oder mehrere Subnetze mehrere Gebäude?
    
- Welchen Etagenbereich umfassen die einzelnen Client-Subnetze?
    
Wenn das Subnetz einen zu großen Bereich umfasst, müssen Sie möglicherweise eine andere Methode zum Ermitteln der Clients verwenden. Es wird empfohlen, sofern möglich, dass Kunden ihre IP-Subnetzverwendung neu anordnen, um die Anforderungen für die Standortgenauigkeit in Erwartungsregellisten zu erfüllen, statt die Kosten und Komplexität von SNMP-basierten Drittanbieter-Lösungen tragen zu müssen.
  
## <a name="client-mac-address"></a>Client-MAC-Adresse

Um die MAC-Adresse eines Clientcomputers zu verwenden, um einen Anrufer zu finden, benötigen Sie verwaltete Ethernet-Switches, und Sie müssen eine SNMP-Lösung eines Drittanbieters bereitstellen, die die MAC-Adressen Skype for Business Clients ermitteln kann, die mit diesen Switches verbunden sind (oder über diese Switches) sind. Die SNMP-Lösung fragt kontinuierlich die verwalteten Switches ab, um die aktuellen Zuordnungen der Mac-Endpunktadressen abzurufen, die mit jedem Port verbunden sind, und ruft die entsprechenden Port-IDs ab. Während einer Skype for Business Clientanforderung an den Standortinformationsdienst fragt der Standortinformationsdienst die Drittanbieteranwendung mithilfe der MAC-Adresse des Clients ab und gibt dann alle übereinstimmenden Switch-IP-Adressen und Port-IDs zurück. Der Standortinformationsdienst verwendet diese Informationen, um die veröffentlichte Layer 2-Wiremap nach einem übereinstimmenden Datensatz abfragt, und gibt den Speicherort an den Client zurück. Wenn Sie diese Option verwenden, stellen Sie sicher, dass die Switchport-IDs zwischen der SNMP-Anwendung und den veröffentlichten Speicherortdatenbankdatensätzen konsistent sind.
  
> [!NOTE]
> Einige SNMP-Lösungen von Drittanbietern können nicht verwaltete Zugriffsoptionen unterstützen. Wenn der Switch, der den Skype for Business Client bedient, nicht verwaltet wird, aber einen Uplink zu einem verwalteten Verteilungsschalter aufweist, kann der verwaltete Switch der SNMP-Anwendung die MAC-Adressen der Clients melden, die mit dem Zugriffsschalter verbunden sind. Diese Informationen ermöglichen es dem Standortinformationsdienst, den Standort des Benutzers zu identifizieren. Es ist jedoch möglich, allen Ports des nicht verwalteten Switches nur eine einzige ERL zuzuweisen, sodass die Standortspezifität nur auf der Gehäuseebene des Zugriffsschalters und nicht auf der Portebene verfügbar ist. 
  

