---
title: Planen der medienumgehung in Cloud Connector Edition
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e69ac58c-e8fe-40bc-a4c8-f0a0190fbaa7
description: Lesen Sie dieses Thema, um die Planungsüberlegungen für die Implementierung der medienumgehung mit Cloud Connector Edition, Version 2,0 und höher, zu überprüfen. Informationen zum Bereitstellen der medienumgehung finden Sie unter Deploy Media Bypass in Cloud Connector Edition.
ms.openlocfilehash: 47b8d9e5d0b69b95c48f89591d75d53591b7426c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42010308"
---
# <a name="plan-for-media-bypass-in-cloud-connector-edition"></a>Planen der medienumgehung in Cloud Connector Edition
 
Lesen Sie dieses Thema, um die Planungsüberlegungen für die Implementierung der medienumgehung mit Cloud Connector Edition, Version 2,0 und höher, zu überprüfen. Informationen zum Bereitstellen der medienumgehung finden Sie unter [Deploy Media Bypass in Cloud Connector Edition](deploy-media-bypass-in-cloud-connector.md).
  
Durch die medienumgehung kann ein Client Medien direkt an den nächsten Hop (Public Switched Telephone Network, PSTN) – einen Gateway-oder Session Border Controller (SBC) – senden und die Cloud Connector Edition-Komponente aus dem Medienpfad entfernen.
  
Die medienumgehung kann die Sprachqualität verbessern, indem die Wartezeit, die Möglichkeit von Paketverlusten und die Anzahl der potenziellen Fehlerpunkte reduziert werden. Durch die Eliminierung der Medienverarbeitung für Umgehungs Anrufe wird die Last von Cloud Connector reduziert, wodurch eine höhere Anzahl gleichzeitiger Anrufe ermöglicht wird und die Skalierbarkeit verbessert werden kann. 
  
 Durch das Freigeben von Cloud Connector aus Medien Verarbeitungsaufgaben wird möglicherweise die Anzahl der Cloud Connector-Appliances verringert, die eine Infrastruktur benötigt, daher sollten Sie die medienumgehung nach Möglichkeit aktivieren.
  
## <a name="how-media-bypass-affects-media-and-signaling-pathways"></a>Auswirkungen der medienumgehung auf Medien-und Signalisierungs Pfade

Während die Signalisierung mit oder ohne medienumgehung denselben Pfad hat, unterscheidet sich der Medienfluss. Die folgenden Diagramme zeigen Medien-und Signalisierungs Pfade in Topologien mit und ohne medienumgehung. 
  
Beispielsweise wird in der folgenden Topologie, in der keine medienumgehung verwendet wird, ein Skype for Business-Client einen PSTN-Anruf an eine externe Nummer richtet, die SIP-Signalübertragung an Office 365 und Office 365 dann den Signalisierungs Datenverkehr entsprechend der Endbenutzer Stimme leitet. Richtlinie. Für Cloud Connector-Benutzer leitet die VoIP-Richtlinie den Signalisierungs Datenverkehr an den Cloud Connector Edgeserver, der den Signalisierungs Datenverkehr dann über den Cloud Connector-Vermittlungsserver an einen PSTN-Sitzungs Grenz Controller (SBC) oder ein Gateway weiterleitet. Medien Flüsse vom Skype for Business-Client zum Cloud Connector Vermittlungsserver und dann zum SBC oder Gateway, wie im folgenden Diagramm dargestellt:
  
**Medien-und Signalisierungs Pfade ohne medienumgehung**

![Signalisierung ohne medienumgehung](../../media/5cd7e3bf-2565-4bd9-ad5a-f03e13c01060.png)
  
Bei einem eingehenden Anruf aus dem PSTN wird derselbe Signalpfad in umgekehrter Richtung verwendet. Für interne Benutzer fließt das Medium letztlich immer noch zwischen dem Skype for Business-Client und dem Cloud Connector Vermittlungsserver und dann dem SBC oder Gateway.
  
In der nächsten Topologie, bei der die medienumgehung verwendet wird, nimmt die Signalisierung denselben Pfad an, aber die Medien fließen direkt zwischen dem Skype for Business-Client und dem SBC oder Gateway, wie im folgenden Diagramm dargestellt:
  
**Medien-und Signalisierungs Pfade mit medienumgehung**

![Signalisierung mit medienumgehung](../../media/60400c38-4921-4964-89f2-5e53b68fb497.png)
  
## <a name="multi-site-scenario-and-media-bypass"></a>Szenario mit mehreren Standorten und medienumgehung

Die medienumgehung ist auch hilfreich, wenn Sie Telefondienste für mehrere Standorte mit einer einzigen Cloud Connector-Appliance bereitstellen möchten. Da Cloud Connector keine Anrufe basierend auf Quell-oder Zielrufnummern weiterleiten kann, stellen die meisten Unternehmen einen SBC oder ein Gateway hinter Cloud Connector bereit, um Routingentscheidungen zu treffen. Die medienumgehung in diesem Szenario eliminiert den Hop zwischen dem Client und dem zentralen SBC oder Gateway, wie im folgenden Diagramm dargestellt:
  
**Multi-Site-Anwendung**

![Beispiel für Cloud Connector-Multisite](../../media/ace8dc3c-1082-46a2-b8b4-98cbf678620e.png)
  
1. Der SIP-Datenverkehr fließt vom Benutzer in Zürich zu Office 365.
    
2. Der Datenverkehr wird dann zur Cloud Connector-Appliance in Amsterdam weitergeleitet, wie in der Richtlinie für Benutzer VoIP-Routing angegeben.
    
3. Die Cloud Connector-Appliance in Amsterdam sendet den SIP-Datenverkehr an das zentrale Gateway in Amsterdam.
    
4. Das zentrale Gateway in Amsterdam trifft die entsprechenden Routingentscheidungen und sendet dann den Datenverkehr an einen SBC oder ein Gateway in Zürich, während die Medien direkt zwischen dem Skype for Business-Client und dem SBC oder Gateway in Amsterdam fließen.
    
   Dieser Ansatz ermöglicht es, mehr Benutzer pro Cloud Connector-Bereitstellung zu bedienen, wobei Cloud Connector zentralisiert ist. Obwohl Cloud Connector aus dem Medienpfad entfernt wird, kann das WAN in einem zentralisierten Szenario mit mehreren Standorten immer noch zweimal durchlaufen, wenn es erforderlich ist, um den zentralisierten SBC oder das Gateway zu durchlaufen.
  
Wenn ein Client außerhalb des Unternehmensnetzwerks einen ausgehenden Anruf platziert, fließt der Mediendatenverkehr über die Edge-und Vermittlungsserver von Cloud Connector und WAN-Link zwischen Zürich und Amsterdam, wie im folgenden Diagramm dargestellt:
  
![Cloud Connector-Multisite-Beispiel 2](../../media/ef95839c-4552-440e-9698-7615707a1b50.png)
  
## <a name="supported-clients-for-media-bypass"></a>Unterstützte Clients für die medienumgehung

Mit der ersten Version der medienumgehung ist der einzige unterstützte Client der Skype for Business 2016 Windows-Client, der Teil von Office 365 ProPlus, Version 16.0.7870.2020 oder höher ist. Kunden können einen beliebigen Kanal verwenden: aktuell, verzögert oder Erstversion zurückgestellt. 
  
> [!NOTE]
> Wenn Sie eine Client-VPN-Lösung in Kombination mit dem Skype for Business-Client verwenden, wird die medienumgehung nur mit einer VPN-Konfiguration mit geteilten Tunneln unterstützt. 
  
Weitere Informationen zu den Veröffentlichungs Kanälen finden Sie unter [Overview of Update Channels for Office 365 ProPlus](https://support.office.com/article/Overview-of-update-channels-for-Office-365-ProPlus-9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4?ui=en-US&amp;rs=en-US&amp;ad=US).
  
Informationen zur aktuellen Version der Clients in verschiedenen Kanälen finden Sie unter [Releaseinformationen für Updates für Office 365 ProPlus](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus). 
  
## <a name="cloud-connector-capacity-considerations-with-media-bypass"></a>Überlegungen zur Cloud Connector-Kapazität mit medienumgehung

Ohne medienumgehung – und je nach Hardware – kann eine Cloud Connector-Appliance zwischen 50 und 500 gleichzeitige Anrufe verarbeiten, bei denen Medien über eine Vermittlungsserver reisen müssen. Weitere Informationen finden Sie unter [Plan for Skype for Business Cloud Connector Edition](https://technet.microsoft.com/library/mt605227.aspx). 
  
Wenn die medienumgehung aktiviert ist, verwenden interne Clients in der unterstützten Version nicht die Vermittlungsserver, sodass sich die Anzahl interner Clients erheblich erhöhen kann. 
  
Wie oben erwähnt, verwenden externe Clients oder nicht unterstützte Clients den Cloud Connector-Edgeserver und Vermittlungsserver für Medien. Wenn Sie berechnen, wie viele Cloud Connector-Appliances an einem Standort gespeichert werden sollen, müssen Sie den Datenverkehr von externen Benutzern und Benutzern auf nicht unterstützten Clients berücksichtigen.
  
## <a name="cloud-connector-supports-always-bypass-mode"></a>Cloud Connector unterstützt Always Bypass-Modus

Cloud Connector unterstützt immer den Bypass-Modus. In lokalen Umgebungen gibt es zwei Optionen: umgehen und verwenden Sie immer Standort-und Regionsinformationen.
  
Always Bypass bedeutet, dass für alle PSTN-Anrufe mit internen Clients als Ursprung oder Zielpunkt eine medienumgehung versucht wird. Um festzustellen, ob der Client intern oder extern ist, wird eine Website auf dem virtuellen Computer des Vermittlungsservers verwendet. Wenn der Client den Standort erreichen kann, wird er als intern betrachtet, und die medienumgehung wird verwendet. Wenn der Client die Website nicht erreichen kann (beispielsweise befindet sich der Client in einem Heimnetzwerk), wird die medienumgehung nicht verwendet. 
  
Always Bypass erfordert eine ungehinderte Konnektivität zwischen Benutzern und den PSTN-Gateways innerhalb eines PSTN-Standorts. 
  
Weitere Informationen finden Sie unter [Plan for Skype for Business Cloud Connector Edition](https://technet.microsoft.com/library/mt605227.aspx). 
  
In der folgenden Abbildung müssen beispielsweise die Benutzer in Europa gut mit den drei Sitzungs Grenz Controllern (SBCS) in Amsterdam verbunden sein, während US-West-Benutzer gut mit den beiden SBCS in Seattle verbunden sein müssen. "Gut verbunden" bedeutet, dass Sie sich entweder an denselben Netzwerkstandorten befinden wie die SBCS oder Gateways oder über WAN-Verbindungen mit einer angemessenen Bandbreite.
  
![Cloud Connector-Kapazität](../../media/efb2269b-d44f-474e-aea8-c5158e729cfe.png)
  
> [!NOTE]
> Wenn ein Benutzer aus Zürich in das Büro in Seattle reist und Sie das interne Netzwerk verwenden möchten, um den Mediendatenverkehr zwischen dem Reisenden Benutzer und den Gateways in Europa (im Gegensatz zur Übertragung über das Internet) zu übermitteln, müssen Sie sicherstellen, dass das Seattle-Office und das Amsterdam Office, in dem sich europäische SBCS oder Gateways befinden, die ebenfalls verbunden sind. 
  
## <a name="codecs-used-in-media-bypass"></a>In der medienumgehung verwendete Codecs

Wenn die medienumgehung aktiviert ist, verwendet der Mediendatenverkehr zwischen einem Client und einem SBC oder Gateway den G. 711-Codec. 
  
## <a name="see-also"></a>Siehe auch

[Bereitstellen der medienumgehung in Cloud Connector Edition](deploy-media-bypass-in-cloud-connector.md)
