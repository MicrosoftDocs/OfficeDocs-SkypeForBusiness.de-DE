---
title: Definieren der Netzwerkelemente zum Ermitteln des Standorts in Skype für Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7538779d-055d-44ed-8dd7-11c45fc1b9f5
description: Entscheidungen zur Planung der Netzwerkkomponenten, mit denen Sie Anrufer Speicherorte für E9-1-1-Bereitstellung in Skype for Business Server Enterprise-VoIP zugeordnet werden.
ms.openlocfilehash: 4cab36efdf0f4bcfbf3834e9c077558610655e3a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882306"
---
# <a name="define-the-network-elements-used-to-determine-location-in-skype-for-business-server"></a>Definieren der Netzwerkelemente zum Ermitteln des Standorts in Skype für Business Server
 
Entscheidungen zur Planung der Netzwerkkomponenten, mit denen Sie Anrufer Speicherorte für E9-1-1-Bereitstellung in Skype for Business Server Enterprise-VoIP zugeordnet werden.
  
Wenn Sie Ihre Skype für Business Server-Infrastruktur zur Unterstützung von Clients für automatische Speicherort Erkennung einrichten, müssen Sie zuerst entscheiden, welche Elemente Sie beabsichtigen, zum Zuordnen von Anrufern zu Speicherorten verwenden. In Skype für Business Server können Sie die folgenden Elemente der Ebene 2 und Layer 3-Netzwerk Speicherorte zuordnen:
  
- Adressen für drahtlosen Zugriffspunkt (BSSID, Basic Service Set Identification) (Layer 2)
    
- LLDP-Switch-Port (Layer 2)
    
- LLDP-Switch-Chassis-IDs (Layer 2)
    
- IP-Subnetze (Layer 3)
    
- Client-MAC-Adressen (Layer 2)
    
Die Netzwerkelemente werden gemäß ihrer Rangfolge aufgelistet. Wenn ein Client mit mehr als ein Netzwerkelement gefunden werden kann, verwendet Skype für Business Server die Reihenfolge der Priorität um zu bestimmen, welche Mechanismus verwenden. 
  
Die folgenden Abschnitte enthalten weitere Einzelheiten zur Verwendung der einzelnen Netzwerkelemente.
  
> [!IMPORTANT]
> Wenn Sie Netzwerkelementen zuordnen Anrufer zu Speicherorten verwenden, ist es von größter Bedeutung, dass die Standortinformationen Service-Datenbank auf dem neuesten Stand halten. Wenn Sie beispielsweise ein Netzwerkelement hinzufügen oder ändern (z. B. einen drahtlosen Zugriffspunkt), müssen Sie den alten Eintrag löschen und den neuen Eintrag in der Standortdatenbank hinzufügen. 
  
## <a name="wireless-access-point"></a>Drahtloser Zugriffspunkt

Ein Client drahtlos mit dem Netzwerk her, verwendet die Anforderung Speicherort die Adresse BSSID den drahtlosen Zugriffspunkt an um den Speicherort zu ermitteln. Wenn der Client roaming ist, der drahtlosen Zugriffspunkt angegeben möglicherweise nicht die nächste aus, und es ist auch möglich, um einen drahtlosen Zugriffspunkt zu übernehmen, die auf einem anderen Bodenfläche des Gebäude befindet. Um anzugeben, dass der Speicherort ungefähre ist, können Sie den Speicherortwert mit einer **[nahezu in]** oder **[schließen]** Deskriptor einleiten.
  
Bei dieser Standortmethode wird davon ausgegangen, dass die BSSID der einzelnen Zugriffspunkte statisch ist. Wenn der Hersteller Ihres WAP dynamisch zugewiesenen BSSIDs verwendet wird, jedoch der BSSID, die von einem drahtlosen Zugriffspunkt abgerufen werden konnte (Dies kann erfolgen nach der Änderung einer WAP) ändern, und drahtlose Clients konnte in einer Situation, in dem sie einen Speicherort erhalten, bleiben. Um diese Möglichkeit zu verhindern, müssen Sie die Standortinformationen Dienstdatenbank mit ERLs für alle möglichen BSSID Adressen von einzelnen WAP verwendete auffüllen. 
  
## <a name="lldp-ports-and-switches"></a>LLDP-Ports und -Switches

Verwaltete Ethernet-Switches, die LLDP-MED (Link Layer Discovery Protocol-Media Endpoint Discover) unterstützen, können die ID- und Portinformationen eines Netzwerks für einen kompatiblen LLDP-MED-Client bereitstellen, die dann wiederum bei der Standortdatenbank abgefragt werden, um den Standort des Geräts anzugeben. Sie können Erwartungsregellisten ausschließlich der Switch-Chassis-ID zuordnen oder sie alternativ auf Portebene zuweisen.
  
> [!NOTE]
> Skype für Business Server unterstützt die Verwendung von LLDP-MED zur Ermittlung von Standorte nur über Lync Phone Edition-Geräte und Skype für Business-Clients unter Windows 8 ausgeführt. Wenn Sie Switch-Ebene Layer 2 Daten verwenden, um den Speicherort der anderen verkabelten PC-basierte Skype für Business Server-Clients ermitteln müssen, müssen Sie den Client-MAC-Adresse-Methode verwenden. 
  
## <a name="subnet"></a>Subnetz

Layer 3-IP-Subnetze bieten einen Mechanismus für Business Server-Clients, die verwendet werden können, an dem Standort des Clients automatisch erkennen von allen Skype unterstützt. Die Verwendung von IP-Subnetzen ist die einfachste Methode zur Ermittlung von Standorten, um verkabelte Clients zu konfigurieren und zu verwalten. Bevor Sie sich für die Verwendung von Subnetzen entscheiden, sollten Sie jedoch anhand der folgenden Fragen ermitteln, ob die Standortgenauigkeit des Subnetzes für eine präzise Ermittlung des Clientstandorts ausreicht:
  
- Umfassen ein oder mehrere Client-Subnetze verschiedene Etagen?
    
- Umfassen ein oder mehrere Subnetze mehrere Gebäude?
    
- Welchen Etagenbereich umfassen die einzelnen Client-Subnetze?
    
Wenn das Subnetz einen zu großen Bereich umfasst, müssen Sie möglicherweise eine andere Methode zum Ermitteln der Clients verwenden. Es wird empfohlen, dass Kunden – sofern möglich – ihre IP-Subnetzverwendung neu anordnen, um die Anforderungen für die Standortgenauigkeit in Erwartungsregellisten zu erfüllen, statt die Kosten und Komplexität von SNMP-basierten Drittanbieter-Lösungen tragen zu müssen.
  
## <a name="client-mac-address"></a>Client-MAC-Adresse

Um MAC-Adresse des Clientcomputers einen Anrufer zu suchen, benötigen Sie verwaltete Ethernet-Switches, und Sie müssen eine Drittanbieter-SNMP-Lösung, die die MAC-Adressen der Skype für Business Clients verbunden (oder über) erkennen kann Bereitstellen dieser Switches. Die SNMP-Lösung ständig fragt die verwaltete Switches, um die aktuelle Zuordnung von der Endpunkt MAC-Adressen für jeden Port verbunden abrufen und ruft die entsprechenden Port-IDs. Während einer Skype für Business-Client-Anforderung an den Dienst Standortinformationen die Standortinformationen Service fragt die Drittanbieter-Anwendung mithilfe der Client-MAC-Adresse, und gibt dann alle übereinstimmenden Switch IP-Adressen und Port-IDs zurück. Der Standortinformationen-Dienst verwendet diese Informationen, um seine veröffentlichten Layer 2 Wiremap für keinen übereinstimmenden Datensatz abzufragen und gibt die Position an den Client zurück. Wenn Sie diese Option verwenden, stellen Sie sicher, dass die Switch-Port-Bezeichner zwischen SNMP-Anwendung und dem Veröffentlichungsort Datenbankdatensätze konsistent sind.
  
> [!NOTE]
> Einige Drittanbieter-SNMP-Lösungen können nicht verwalteten Zugriff Switches unterstützen. Wenn Switches, der die Skype für Client Business services nicht verwalteten ist aber eine Uplink mit einem verwalteten Verteilung Switch hat, kann die Option verwaltete wieder die SNMP-Anwendung die MAC-Adressen der Clients an den Zugriffs-Switch angeschlossen melden. Diese Informationen kann den Standortinformationen-Dienst zum Identifizieren des Speicherorts des Benutzers an. Es ist jedoch möglich, nur einen einzigen ERL für alle Ports auf dem nicht verwalteten Switch zuweisen, damit nur auf der Ebene Chassis des Access-Switches, nicht die Zugriffsebene Port der Speicherort detailgenauigkeit zur Verfügung steht. 
  

