---
title: Definieren der Netzwerkelemente, die zum Bestimmen des Standorts in Skype for Business Server verwendet werden
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Entscheidungen, die für die Planung erforderlich sind, welche Netzwerkkomponenten Sie verwenden, um Anrufer Standorten für die E9-1-1-Bereitstellung in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: 473ef9efc8598b303d6c7a05b902d57e0ad8ffd5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813635"
---
# <a name="define-the-network-elements-used-to-determine-location-in-skype-for-business-server"></a>Definieren der Netzwerkelemente, die zum Bestimmen des Standorts in Skype for Business Server verwendet werden
 
Entscheidungen, die für die Planung erforderlich sind, welche Netzwerkkomponenten Sie verwenden, um Anrufer Standorten für die E9-1-1-Bereitstellung in Skype for Business Server Enterprise-VoIP.
  
Wenn Sie Ihre Skype for Business Server-Infrastruktur so einrichten, dass die automatische Erkennung von Clientstandorten unterstützt wird, müssen Sie zunächst entscheiden, welche Netzwerkelemente Sie verwenden möchten, um Anrufer Standorten zu zuordnungen. In Skype for Business Server können Sie die folgenden Layer 2- und Layer 3-Netzwerkelemente Standorten zuordnen:
  
- Adressen für drahtlosen Zugriffspunk (BSSID, Basic Service Set Identification) (Layer 2)
    
- LLDP-Switch-Port (Layer 2)
    
- LLDP-Switch-Chassis-IDs (Layer 2)
    
- IP-Subnetze (Layer 3)
    
- Client-MAC-Adressen (Layer 2)
    
Die Netzwerkelemente werden gemäß ihrer Rangfolge aufgelistet. Wenn ein Client mithilfe von mehr als einem Netzwerkelement gespeichert werden kann, verwendet Skype for Business Server die Rangfolge, um zu bestimmen, welcher Mechanismus verwendet werden soll. 
  
Die folgenden Abschnitte enthalten weitere Einzelheiten zur Verwendung der einzelnen Netzwerkelemente.
  
> [!IMPORTANT]
> Wenn Sie Netzwerkelemente zum Zuordnung von Anrufern zu Standorten verwenden, ist es äußerst wichtig, die Datenbank des Standortinformationsdiensts auf dem neuesten Stand zu halten. Wenn Sie beispielsweise ein Netzwerkelement hinzufügen oder ändern (angenommen Sie fügen z. B. einen drahtlosen Zugriffspunkt hinzu), müssen Sie den alten Eintrag löschen und den neuen Eintrag in der Standortdatenbank hinzufügen. 
  
## <a name="wireless-access-point"></a>Drahtloser Zugriffspunkt

Wenn ein Client drahtlos eine Verbindung mit dem Netzwerk herstellt, verwendet die Standortanforderung die BSSID-Adresse des Funkdienstanbieters, um seinen Standort zu ermitteln. Wenn der Client roamingt, ist der angegebene WaP möglicherweise nicht der nächste, und es ist sogar möglich, einen WaP zu nehmen, der sich in einem anderen Stockwerk des Gebäudes befindet. Um anzugeben, dass es sich um eine ungefähre Position handelt, können Sie dem Standortwert eine **[Near]-** oder **[Closeto]-Beschreibung** vorschreiben.
  
Bei dieser Standortmethode wird davon ausgegangen, dass die BSSID der einzelnen Zugriffspunkte statisch ist. Wenn Ihr Anbieter von Funkdienstanbietern jedoch dynamisch zugewiesene BSSIDs verwendet, könnte sich die von einem Funkdienstanbieter erhaltene BSSID ändern (dies kann nach einer Änderung der Konfiguration des Funkdienstanbieters passieren), und die Drahtlosclients könnten in einer Situation bleiben, in der sie keinen Standort erhalten. Um diese Möglichkeit zu verhindern, müssen Sie die Standortinformationsdienstdatenbank mit ERLs für alle möglichen von jedem WaP verwendeten BSSID-Adressen auffüllen. 
  
## <a name="lldp-ports-and-switches"></a>LLDP-Ports und -Switches

Verwaltete Ethernet-Switches, die LLDP-MED (Link Layer Discovery Protocol-Media Endpoint Discover) unterstützen, können die ID- und Portinformationen eines Netzwerks für einen kompatiblen LLDP-MED-Client bereitstellen, die dann wiederum bei der Standortdatenbank abgefragt werden, um den Standort des Geräts anzugeben. Sie können Erwartungsregellisten ausschließlich der Switch-Chassis-ID zuordnen oder sie alternativ auf Portebene zuweisen.
  
> [!NOTE]
> Skype for Business Server unterstützt die Verwendung von LLDP-MED zum Bestimmen von Speicherorten nur von Lync Phone Edition-Geräten und Skype for Business-Clients, die auf Windows 8. Wenn Sie Layer 2-Daten auf Switchebene verwenden müssen, um den Standort anderer verkabelter PC-basierter Skype for Business Server-Clients zu ermitteln, müssen Sie die Client-MAC-Adressmethode verwenden. 
  
## <a name="subnet"></a>Subnetz

Layer 3-IP-Subnetze bieten einen Mechanismus, der von allen Skype for Business Server-Clients unterstützt wird und zum automatischen Erkennen des Clientstandorts verwendet werden kann. Die Verwendung von IP-Subnetzen ist die einfachste Methode zur Ermittlung von Standorten, um verkabelte Clients zu konfigurieren und zu verwalten. Bevor Sie sich für die Verwendung von Subnetzen entscheiden, sollten Sie jedoch anhand der folgenden Fragen ermitteln, ob die Standortgenauigkeit des Subnetzes für eine präzise Ermittlung des Clientstandorts ausreicht:
  
- Umfassen ein oder mehrere Client-Subnetze verschiedene Etagen?
    
- Umfassen ein oder mehrere Subnetze mehrere Gebäude?
    
- Welchen Etagenbereich umfassen die einzelnen Client-Subnetze?
    
Wenn das Subnetz einen zu großen Bereich umfasst, müssen Sie möglicherweise eine andere Methode zum Ermitteln der Clients verwenden. Es wird empfohlen, sofern möglich, dass Kunden ihre IP-Subnetzverwendung neu anordnen, um die Anforderungen für die Standortgenauigkeit in Erwartungsregellisten zu erfüllen, statt die Kosten und Komplexität von SNMP-basierten Drittanbieter-Lösungen tragen zu müssen.
  
## <a name="client-mac-address"></a>Client-MAC-Adresse

Um die MAC-Adresse eines Clientcomputers für die Suche nach einem Anrufer zu verwenden, benötigen Sie verwaltete Ethernet-Switches, und Sie müssen eine Drittanbieter-SNMP-Lösung bereitstellen, die die MAC-Adressen von Skype for Business-Clients ermitteln kann, die mit diesen Switches verbunden (oder über diese Switches) verbunden sind. Die SNMP-Lösung ruft die verwalteten Switches kontinuierlich ab, um die aktuellen Zuordnungen der Endpunkt-MAC-Adressen zu erhalten, die mit jedem Port verbunden sind, und ruft die entsprechenden Port-IDs ab. Während der Anforderung eines Skype for Business-Clients an den Standortinformationsdienst fragt der Standortinformationsdienst die Drittanbieteranwendung mithilfe der CLIENT-MAC-Adresse ab und gibt dann übereinstimmende Switch-IP-Adressen und Port-IDs zurück. Der Standortinformationsdienst verwendet diese Informationen, um die veröffentlichte Layer 2-Wiremap nach einem übereinstimmenden Datensatz zu abfragen und gibt den Standort an den Client zurück. Wenn Sie diese Option verwenden, stellen Sie sicher, dass die Switchportbezeichner zwischen der SNMP-Anwendung und den veröffentlichten Standortdatenbankdatensätzen konsistent sind.
  
> [!NOTE]
> Einige #A0 von Drittanbietern können nicht verwaltete Zugriffswechsel unterstützen. Wenn der Switch, der den Skype for Business-Client unterstützt, nicht verwaltet wird, aber über einen Uplink zu einem verwalteten Verteilungswechsel verfügt, kann der verwaltete Switch der SNMP-Anwendung die MAC-Adressen der clients melden, die mit dem Zugriffswechsel verbunden sind. Diese Informationen ermöglichen es dem Standortinformationsdienst, den Standort des Benutzers zu identifizieren. Es ist jedoch möglich, allen Ports des nicht verwalteten Switches nur eine einzige ERL zuzuordnen, sodass die Standortspezifischität nur auf Der Chassisebene des Zugriffsschalters und nicht auf Portebene verfügbar ist. 
  

