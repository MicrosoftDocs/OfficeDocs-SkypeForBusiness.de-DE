---
title: Planen der Medienumgehung in der Cloud Connector Edition
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
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e69ac58c-e8fe-40bc-a4c8-f0a0190fbaa7
description: Lesen Sie dieses Thema, um Planungsüberlegungen für die Implementierung der Medienumgehung mit Cloud Connector Edition, Version 2.0 und höher, zu überprüfen. Informationen zum Bereitstellen der Medienumgehung finden Sie unter "Bereitstellen der Medienumgehung in Cloud Connector Edition".
ms.openlocfilehash: 182defd3d1fb7acf1fb2ba6fcc4e15e88e24a82c
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "58729744"
---
# <a name="plan-for-media-bypass-in-cloud-connector-edition"></a>Planen der Medienumgehung in der Cloud Connector Edition
 
Lesen Sie dieses Thema, um Planungsüberlegungen für die Implementierung der Medienumgehung mit Cloud Connector Edition, Version 2.0 und höher, zu überprüfen. Informationen zum Bereitstellen der Medienumgehung finden Sie unter [Bereitstellen der Medienumgehung in Cloud Connector Edition.](deploy-media-bypass-in-cloud-connector.md)
  
Die Medienumgehung ermöglicht es einem Client, Medien direkt an den nächsten Hop (PsTN) zu senden – ein Gateway oder Session Border Controller (SBC) – und die Cloud Connector Edition-Komponente aus dem Medienpfad zu entfernen.
  
Die Medienumgehung kann die Sprachqualität verbessern, indem die Latenz, die Möglichkeit von Paketverlust und die Anzahl möglicher Fehlerpunkte reduziert wird. Die Ausschaltung der Medienverarbeitung für umgangene Anrufe reduziert die Last für Cloud Connector, wodurch eine höhere Anzahl gleichzeitiger Anrufe ermöglicht wird und die Skalierbarkeit verbessert werden kann. 
  
 Das Freigeben von Cloud Connector von Medienverarbeitungsaufgaben kann die Anzahl der Cloud Connector-Appliances verringern, die eine Infrastruktur erfordert. Daher sollten Sie die Medienumgehung nach Möglichkeit aktivieren.
  
## <a name="how-media-bypass-affects-media-and-signaling-pathways"></a>Auswirkungen der Medienumgehung auf Medien- und Signalisierungspfade

Während die Signalisierung denselben Pfad mit oder ohne Medienumgehung einnimmt, unterscheidet sich der Medienfluss. Die folgenden Diagramme zeigen Medien- und Signalisierungspfade in Topologien mit und ohne Medienumgehung. 
  
Beispielsweise wird in der folgenden Topologie, die keine Medienumgehung verwendet, ein Skype for Business Client einen PSTN-Anruf an eine externe Nummer abgibt, wird das SIP-Signal an Microsoft 365 oder Office 365 gesendet, wodurch der Signaldatenverkehr gemäß der VoIP-Richtlinie des Endbenutzers gesteuert wird. Für Cloud Connector-Benutzer leitet die VoIP-Richtlinie Signaldatenverkehr an den Cloud Connector Edge Server weiter, der den Signaldatenverkehr dann über den Cloud Connector-Vermittlungsserver an einen PSTN-Session Border Controller (SBC) oder ein Gateway weiterleitet. Medien fließen vom Skype for Business-Client zum Cloud Connector-Vermittlungsserver und dann zum SBC oder Gateway, wie im folgenden Diagramm dargestellt:
  
**Medien- und Signalisierungspfade ohne Medienumgehung**

![Signalisierung ohne Medienumgehung.](../../media/5cd7e3bf-2565-4bd9-ad5a-f03e13c01060.png)
  
Ein eingehender Anruf aus dem PSTN verwendet denselben Signalpfad in umgekehrter Richtung. Für interne Benutzer werden die Medien letztendlich immer noch zwischen dem Skype for Business-Client und dem Cloud Connector-Vermittlungsserver und dann dem SBC oder Gateway fließen.
  
In der nächsten Topologie , bei der die Medienumgehung verwendet wird, nimmt die Signalisierung den gleichen Pfad, aber die Medien fließen direkt zwischen dem Skype for Business-Client und dem SBC oder Gateway, wie im folgenden Diagramm dargestellt:
  
**Medien- und Signalisierungspfade mit Medienumgehung**

![Signalisierung mit Medienumgehung.](../../media/60400c38-4921-4964-89f2-5e53b68fb497.png)
  
## <a name="multi-site-scenario-and-media-bypass"></a>Szenario mit mehreren Websites und Medienumgehung

Die Medienumgehung ist auch nützlich, wenn Sie Telefoniedienste für mehrere Standorte mit einer einzigen Cloud Connector-Appliance bereitstellen möchten. Da Cloud Connector Anrufe nicht basierend auf Quell- oder Zielnummern weiterleiten kann, stellen die meisten Unternehmen einen SBC oder ein Gateway hinter Cloud Connector bereit, um Routingentscheidungen zu treffen. Die Medienumgehung in diesem Szenario eliminiert den Hop zwischen dem Client und dem zentralen SBC oder Gateway, wie im folgenden Diagramm dargestellt:
  
**Anwendung mit mehreren Websites**

![Beispiel für cloudkonnektor mit mehreren Websites.](../../media/ace8dc3c-1082-46a2-b8b4-98cbf678620e.png)
  
1. Der SIP-Datenverkehr fließt vom Benutzer in Zürich zu Microsoft 365 oder Office 365.
    
2. Der Datenverkehr wird dann wie in der VoIP-Routingrichtlinie des Benutzers angegeben an die Cloud Connector-Appliance in Amsterdam geroutet.
    
3. Die Cloud Connector-Appliance in Amsterdam sendet den SIP-Datenverkehr an das zentrale Gateway in Amsterdam.
    
4. Das zentrale Gateway in Amsterdam trifft die entsprechenden Routingentscheidungen und sendet dann den Datenverkehr an einen SBC oder ein Gateway in Amsterdam, während die Medien direkt zwischen dem Skype for Business-Client und SBC oder Gateway in Amsterdam fließen.
    
   Dieser Ansatz ermöglicht die Bereitstellung mehrerer Benutzer pro Cloud Connector-Bereitstellung, bei der Cloud Connector zentralisiert ist. Obwohl Cloud Connector aus dem Medienpfad entfernt wird, durchlaufen Medien in einem zentralisierten Szenario mit mehreren Standorten das WAN möglicherweise immer noch doppelt so wie erforderlich, um den zentralen SBC oder das Gateway zu durchlaufen.
  
Wenn sich ein Client außerhalb des Unternehmensnetzwerks befindet und einen ausgehenden Anruf tätigt, fließt der Mediendatenverkehr über die Edge- und Vermittlungsserver von Cloud Connector und der WAN-Verbindung zwischen Amsterdam und Amsterdam, wie im folgenden Diagramm dargestellt:
  
![Cloud Connector Mit mehreren Websites (Beispiel 2).](../../media/ef95839c-4552-440e-9698-7615707a1b50.png)
  
## <a name="supported-clients-for-media-bypass"></a>Unterstützte Clients für die Medienumgehung

Bei der ersten Version der Medienumgehung wird nur der Skype for Business 2016-Windows-Client unterstützt, der Teil von Microsoft 365 Apps for Enterprise Version 16.0.7870.2020 oder höher ist. Kunden können einen beliebigen Kanal verwenden: Current, Deferred oder First Release Deferred. 
  
> [!NOTE]
> Wenn Sie eine Client-VPN-Lösung in Kombination mit dem Skype for Business-Client verwenden, wird die Medienumgehung nur bei einer VPN-Konfiguration mit geteilten Tunneln unterstützt. 
  
Weitere Informationen zu den Veröffentlichungskanälen finden Sie unter [Übersicht über Updatekanäle für Microsoft 365 Apps for Enterprise](https://support.office.com/article/Overview-of-update-channels-for-Office-365-ProPlus-9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4?ui=en-US&amp;rs=en-US&amp;ad=US).
  
Die aktuelle Version der Clients in verschiedenen Kanälen finden Sie unter [Versionsinformationen für Updates für Microsoft 365 Apps for Enterprise.](/officeupdates/release-notes-office365-proplus) 
  
## <a name="cloud-connector-capacity-considerations-with-media-bypass"></a>Überlegungen zur Cloud Connector-Kapazität bei der Medienumgehung

Ohne Medienumgehung – und abhängig von der Hardware – kann eine Cloud Connector-Appliance 50 bis 500 gleichzeitige Anrufe verarbeiten, bei denen Medien über einen Vermittlungsserver übertragen werden müssen. Weitere Informationen finden Sie unter [Plan for Skype for Business Cloud Connector Edition](./plan-skype-for-business-cloud-connector-edition.md). 
  
Wenn die Medienumgehung aktiviert ist, verwenden interne Clients in der unterstützten Version nicht den Vermittlungsserver, sodass die Anzahl der internen Clients erheblich erhöht werden kann. 
  
Wie oben erwähnt, verwenden externe Clients oder nicht unterstützte Clients den Cloud Connector-Edgeserver und vermittlungsserver für Medien. Bei der Berechnung, wie viele Cloud Connector-Appliances an einem Standort platziert werden sollen, müssen Sie den Datenverkehr von externen Benutzern und Benutzern auf nicht unterstützten Clients berücksichtigen.
  
## <a name="cloud-connector-supports-always-bypass-mode"></a>Cloud Connector unterstützt den Modus "Always Bypass"

Cloud Connector unterstützt nur den Modus "Always Bypass". In lokalen Umgebungen gibt es zwei Optionen: Immer Standort- und Regionsinformationen umgehen und verwenden.
  
Always Bypass bedeutet, dass für alle PSTN-Anrufe mit internen Clients als Ursprung oder Zielpunkt eine Medienumgehung versucht wird. Um festzustellen, ob der Client intern oder extern ist, wird eine Website auf dem virtuellen Computer des Vermittlungsservers verwendet. Wenn der Client den Standort erreichen kann, gilt er als intern, und die Medienumgehung wird verwendet. Wenn der Client den Standort nicht erreichen kann (z. B. wenn sich der Client in einem Heimnetzwerk befindet), wird keine Medienumgehung verwendet. 
  
"Always Bypass" erfordert eine nicht beauftragte Verbindung zwischen Benutzern und den PSTN-Gateways innerhalb eines PSTN-Standorts. 
  
Weitere Informationen finden Sie unter [Plan for Skype for Business Cloud Connector Edition](./plan-skype-for-business-cloud-connector-edition.md). 
  
Im folgenden Diagramm müssen Die Benutzer in Europa beispielsweise gut mit den drei SbCs (Session Border Controller) in Amsterdam verbunden sein, während Benutzer des US-Amerikanischen Westens gut mit den beiden SBCs in Seattle verbunden sein müssen. Eine gute Verbindung bedeutet, dass sie sich entweder an den gleichen Netzwerkstandorten wie die SBCs oder Gateways befinden oder über WAN-Verbindungen mit entsprechender Bandbreite.
  
![Cloud Connector-Kapazität.](../../media/efb2269b-d44f-474e-aea8-c5158e729cfe.png)
  
> [!NOTE]
> Wenn ein Benutzer aus Amsterdam zum Büro in Seattle unterwegs ist und Sie das interne Netzwerk verwenden möchten, um Mediendatenverkehr zwischen dem reisenden Benutzer und Gateways in Europa bereitzustellen (im Gegensatz zum Internet), müssen Sie sicherstellen, dass das Büro Seattle und das Büro in Amsterdam, in dem sich europäische SBCs oder Gateways befinden, als gut verbunden gelten. 
  
## <a name="codecs-used-in-media-bypass"></a>Codecs, die bei der Medienumgehung verwendet werden

Wenn die Medienumgehung aktiviert ist, verwendet der Mediendatenverkehr zwischen einem Client und einem SBC oder Gateway den G.711-Codec. 
  
## <a name="see-also"></a>Siehe auch

[Bereitstellen der Medienumgehung in Cloud Connector Edition](deploy-media-bypass-in-cloud-connector.md)