---
title: Planen der Medienumgehung in Cloud Connector Edition
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e69ac58c-e8fe-40bc-a4c8-f0a0190fbaa7
description: Lesen Sie dieses Thema, um die Planungsüberlegungen für die Implementierung der Medienumgehung mit Cloud Connector Edition, Version 2.0 und höher, zu überprüfen. Informationen zum Bereitstellen von Medien zu umgehen Sie, finden Sie unter Deploy Medien in der Cloud Connector Edition umgehen.
ms.openlocfilehash: a2dfca68d7bfe02ae0701dc13d76bc24121a1cb8
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="plan-for-media-bypass-in-cloud-connector-edition"></a>Planen der Medienumgehung in Cloud Connector Edition
 
Lesen Sie dieses Thema, um die Planungsüberlegungen für die Implementierung der Medienumgehung mit Cloud Connector Edition, Version 2.0 und höher, zu überprüfen. Informationen zum Bereitstellen von Medien zu umgehen Sie, finden Sie unter [medienumgehung in der Cloud Connector Edition bereitstellen](deploy-media-bypass-in-cloud-connector.md).
  
Die medienumgehung kann ein Client zum Senden von Medien direkt an den nächsten Hop (Public Switched Telephone Network, PSTN) – Session Border Controller (SBC) oder ein Gateway – und die Cloud Connector Edition-Komponente aus dem Medienpfad auszuschließen.
  
Die Medienumgehung kann die Sprachqualität verbessern, indem die Latenz verringert, die Möglichkeit von Paketverlust verhindert sowie potenzielle Fehlerstellen minimiert werden. Vermeidung von Medien für umgangener Anrufe verarbeiten reduziert die Belastung Cloud Connector, wodurch eine größere Anzahl gleichzeitiger Anrufe und Skalierbarkeit verbessern kann. 
  
 Freigeben von Cloud-Connector aus Medien Verarbeitungsaufgaben kann die Anzahl der Cloud Connector Einheiten, die eine Infrastruktur erfordert, die reduziert, damit die medienumgehung Wenn möglich aktiviert werden sollten.
  
## <a name="how-media-bypass-affects-media-and-signaling-pathways"></a>Auswirkungen der Medienumgehung auf Medien- und Signalisierungspfade

Während die Signalisierung mit und ohne Medienumgehung dem gleichen Pfad folgt, unterscheidet sich der Medienfluss. Die folgenden Diagramme zeigen Medien- und Signalisierungspfade in Topologien mit und ohne Medienumgehung.  
  
Beispielsweise in der folgenden Topologie – die nicht beschäftigen medienumgehung – eine Skype für Business Client platziert einen PSTN-Anruf an eine externe Nummer, die SIP-Signale wechselt zu Office 365 und Office 365 leitet die signaldatenverkehr entsprechend der Endbenutzer VoIP Richtlinie. Für Benutzer von Cloud-Connector weist die VoIP-Richtlinie signaldatenverkehr mit dem Cloud Connector-Edgeserver, die die signaldatenverkehr dann an eine PSTN Session Border Controller (SBC) oder über die Cloud Connector Mediation-Server-Gateway weitergeleitet. Die Medien werden übertragen aus der Skype für Business-Client zum Vermittlungsserver Cloud-Connector, und klicken Sie dann auf den SBC oder Gateway, wie im folgenden Diagramm dargestellt:
  
**Medien- und signaldatenverkehr ohne Media umgehen**

![Signalisierung ohne Medienumgehung](../../media/5cd7e3bf-2565-4bd9-ad5a-f03e13c01060.png)
  
Ein eingehender Anruf aus dem PSTN verwendet den gleichen Signalisierungspfad in umgekehrter Richtung. Für interne Benutzer wird weiterhin letztlich zwischen der Skype für Business-Client und der Cloud Connector Mediation-Server, und klicken Sie dann die SBC oder Gateway medienfluss.
  
In der nächsten Topologie – die beschäftigen medienumgehung – Signale denselben Pfad dauert, aber die Medien werden direkt zwischen den Skype für Business-Client und die SBC oder Gateway, übertragen, wie im folgenden Diagramm dargestellt:
  
**Medien- und signaldatenverkehr mit Medien umgehen**

![Signalisierung mit Medienumgehung](../../media/60400c38-4921-4964-89f2-5e53b68fb497.png)
  
## <a name="multi-site-scenario-and-media-bypass"></a>Szenario mit mehreren Standorten und Medienumgehung

Die medienumgehung ist außerdem hilfreich, wenn Telefoniedienste für mehrere Websites mit einer einzigen Appliance Cloud-Connector bereitgestellt werden soll. Da Cloud Connector basierend auf Quell- oder Ziel Zahlen Anrufe weiterleiten können, stellen Sie die meisten Unternehmen ein SBC oder Gateway hinter Cloud Connector, um Routingentscheidungen bereit. In diesem Szenario eliminiert die Medienumgehung wie im folgenden Diagramm gezeigt den Hop zwischen dem Client und dem zentralen SBC oder Gateway:
  
**Anwendung mit mehreren Standorten**

![Beispiel für Cloud Connector mit mehreren Standorten](../../media/ace8dc3c-1082-46a2-b8b4-98cbf678620e.png)
  
1. Der SIP-Datenverkehr fließt von dem Benutzer in Zürich nach Office 365.
    
2. Der Datenverkehr leitet klicken Sie dann auf die Cloud Connector Einheit in Amsterdam gemäß der Benutzer VoIP-routing-Richtlinie.
    
3. Die Cloud Connector Appliance in Amsterdam sendet den SIP-Datenverkehr an das Gateway zentralen in Amsterdam.
    
4. Das zentrale Gateway in Amsterdam macht die entsprechenden Routingentscheidungen und sendet dann den Datenverkehr auf einen SBC oder das Gateway in Zürich, Medien fließt direkt zwischen den Skype für Business-Client und SBC oder das Gateway in Amsterdam dagegen.
    
 Dieser Ansatz ermöglicht berücksichtigenden mehr Benutzer pro einer Cloud-Connector-Bereitstellung, in dem Cloud Connector zentrale. Obwohl Cloud Connector aus dem Medienpfad entfernt wird, können in einem Szenario mit zentralisierten mit mehreren Medien weiterhin das WAN zweimal als erforderlich, um über den zentralisierten SBC oder ein Gateway flow durchlaufen.
  
Wenn ein Client außerhalb des Firmennetzwerks befinden, das Tätigen eines ausgehenden Anrufs ist, fließt der Mediendatenverkehr über die Edge und Mediation Server eines Cloud-Connector und WAN-Verbindung zwischen Zürich und Amsterdam, wie im folgenden Diagramm dargestellt:
  
![Beispiel 2 für Cloud Connector mit mehreren Standorten](../../media/ef95839c-4552-440e-9698-7615707a1b50.png)
  
## <a name="supported-clients-for-media-bypass"></a>Für Medienumgehung unterstützte Clients

Die erste Version von medienumgehung, ist der einzige unterstützte Client die Skype für Business 2016 Windows-Client, die Teil von Office 365 ProPlus, Version 16.0.7870.2020 ist oder höher. Kunden können jeden Kanal verwenden: monatlicher Kanal, halbjähriger Kanal oder First Release für verzögerten Kanal. 
  
> [!NOTE]
> Wenn Sie eine Client-VPN-Lösung in Kombination mit dem Skype for Business-Client verwenden, wird Medienumgehung nur mit einer VPN-Konfiguration mit geteiltem Tunnel unterstützt. 
  
Weitere Informationen zu den Kanälen Version finden Sie unter [Übersicht über die Update-Kanäle für Office 365 ProPlus](https://support.office.com/en-us/article/Overview-of-update-channels-for-Office-365-ProPlus-9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4?ui=en-US&amp;rs=en-US&amp;ad=US).
  
Die aktuelle Version Version der Clients in unterschiedliche Kanäle finden Sie unter [Office 365-Client Channel Versionen aktualisieren](https://technet.microsoft.com/en-us/office/mt465751.aspx). 
  
## <a name="cloud-connector-capacity-considerations-with-media-bypass"></a>Kapazitätsüberlegungen für Cloud Connector mit Medienumgehung

Ohne medienumgehung – und von der Hardware – eine Cloud-Connector Appliance von 50 500 gleichzeitige Anrufe, die über einen Vermittlungsserver Reisen Media erfordern behandeln kann. Weitere Informationen finden Sie unter [Planen von Skype für Business Cloud Connector Edition](https://technet.microsoft.com/en-us/library/mt605227.aspx). 
  
Bei aktivierter Medienumgehung verwenden interne Clients in der unterstützten Version den Vermittlungsserver nicht, sodass die Anzahl der internen Clients erheblich zunehmen kann. 
  
Wie bereits erwähnt, werden externe Clients oder nicht unterstützte Clients Cloud Connector Rand und Mediation Server für Medien verwendet werden. Bei der Berechnung, wie viele Connector Cloud Appliances in einer Website verschoben werden soll, müssen Sie den Datenverkehr von externen Benutzern und Benutzern auf nicht unterstützte Clients berücksichtigen.
  
## <a name="cloud-connector-supports-always-bypass-mode"></a>Cloud Connector unterstützt den Modus „Immer umgehen“

Cloud-Connector unterstützt nur Modus immer umgehen. In lokalen Umgebungen gibt es zwei Optionen: „Immer umgehen“ und „Use Site and Region Information“ (Standort- und Regionsinformationen verwenden).
  
„Immer umgehen“ bedeutet, dass Medienumgehung bei allen PSTN-Anrufen versucht wird, bei denen interne Clients Ursprung oder Ziel sind. Ob es sich um einen internen oder externen Client handelt, wird mithilfe einer Website in der virtuellen Maschine des Vermittlungsservers ermittelt. Wenn der Client die Website erreichen kann, gilt sie als intern, und die Medienumgehung wird verwendet. Wenn der Client die Website nicht erreichen kann (wenn sich der Client z. B. in einem Heimnetzwerk befindet), wird keine Medienumgehung verwendet.  
  
„Immer umgehen“ setzt unbehinderte Konnektivität zwischen Benutzern und den PSTN-Gateways an einem PSTN-Standort voraus.  
  
Weitere Informationen finden Sie unter [Planen von Skype für Business Cloud Connector Edition](https://technet.microsoft.com/en-us/library/mt605227.aspx). 
  
Beispielsweise in der folgenden Abbildung muss Europa Benutzer über eine gute Verbindung an den drei Session Border Controller (SBCs) in Amsterdam während US West Benutzer über eine gute Verbindung zu den zwei SBCs in Seattle sein müssen. „Gute Verbindung“ bedeutet, dass sie sich an den gleichen Netzwerkstandorten wie die SBCs oder Gateways befinden oder dass sie über WAN-Verbindungen mit entsprechender Bandbreite verfügen.
  
![Cloud Connector-Kapazität](../../media/efb2269b-d44f-474e-aea8-c5158e729cfe.png)
  
> [!NOTE]
> Wenn ein Benutzer aus Zürich zur Niederlassung in Seattle reist und Sie das interne Netzwerk zum Übermitteln des Mediendatenverkehrs zwischen dem reisenden Benutzer und den Gateways in Europa verwenden möchten (anstatt über das Internet zu gehen), müssen Sie sicherstellen, dass die Niederlassung in Seattle und die Niederlassung in Amsterdam, in der sich die europäischen SBCs oder Gateways befinden, als gut verbunden eingestuft werden können. 
  
## <a name="codecs-used-in-media-bypass"></a>Bei der Medienumgehung verwendete Codecs

Bei aktivierter Medienumgehung wird für den Mediendatenverkehr zwischen einem Client und einem SBC oder Gateway der Codec G.711 verwendet. 
  
## <a name="see-also"></a>Siehe auch

#### 

[Die medienumgehung in der Cloud Connector Edition bereitstellen](deploy-media-bypass-in-cloud-connector.md)

