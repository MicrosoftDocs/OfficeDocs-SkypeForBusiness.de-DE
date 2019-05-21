---
title: Planen der Medienumgehung in Cloud Connector Edition
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e69ac58c-e8fe-40bc-a4c8-f0a0190fbaa7
description: Lesen Sie dieses Thema, um Planungsüberlegungen zur Implementierung der medienumgehung mit Cloud Connector Edition, Version 2,0 und höher, zu überprüfen. Informationen zum Bereitstellen der medienumgehung finden Sie unter Bereitstellen der medienumgehung in Cloud Connector Edition.
ms.openlocfilehash: 00f700880e26f12da3aa6c2d791e4f15bfe9a90b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287027"
---
# <a name="plan-for-media-bypass-in-cloud-connector-edition"></a>Planen der Medienumgehung in Cloud Connector Edition
 
Lesen Sie dieses Thema, um Planungsüberlegungen zur Implementierung der medienumgehung mit Cloud Connector Edition, Version 2,0 und höher, zu überprüfen. Informationen zum Bereitstellen der medienumgehung finden Sie unter [Bereitstellen der medienumgehung in Cloud Connector Edition](deploy-media-bypass-in-cloud-connector.md).
  
Die medienumgehung ermöglicht es einem Client, Medien direkt an das öffentlich geschaltete Telefon Netzwerk (PSTN) nächster Hop zu senden – einen Gateway-oder Session Border Controller (SBC) – und die Cloud Connector Edition-Komponente aus dem Medienpfad zu entfernen.
  
Mit der medienumgehung können Sie die Sprachqualität verbessern, indem Sie die Wartezeit, die Möglichkeit des Paketverlusts und die Anzahl der potenziellen Fehlerpunkte verringern. Durch die Eliminierung der Medienverarbeitung für Umgehungs Anrufe wird die Auslastung von Cloud Connector verringert, was eine höhere Anzahl gleichzeitiger Anrufe ermöglicht und die Skalierbarkeit verbessern kann. 
  
 Durch das Freigeben von Cloud Connector von Medien Verarbeitungsaufgaben kann die Anzahl der Cloud Connector-Appliances, die eine Infrastruktur erfordert, verringert werden, daher sollten Sie die medienumgehung nach Möglichkeit aktivieren.
  
## <a name="how-media-bypass-affects-media-and-signaling-pathways"></a>Auswirkungen der Medienumgehung auf Medien- und Signalisierungspfade

Während die Signalisierung mit und ohne Medienumgehung dem gleichen Pfad folgt, unterscheidet sich der Medienfluss. Die folgenden Diagramme zeigen Medien- und Signalisierungspfade in Topologien mit und ohne Medienumgehung.   
  
In der folgenden Topologie, die keine medienumgehung verwendet, stellt ein Skype for Business-Client einen PSTN-Anruf an eine externe Nummer, die SIP-Signalisierung geht an Office 365, und Office 365 leitet den signalisierten Datenverkehr entsprechend der Endbenutzer-Stimme weiter. Richtlinie. Für Benutzer von Cloud Connector leitet die VoIP-Richtlinie das Signalisieren des Datenverkehrs an den Edge-Server für Cloud-Connector weiter, der dann den Signalisierungsdaten Verkehr an einen PSTN-Sitzungs Grenz Controller (SBC) oder ein Gateway über den Vermittlungsserver für Cloud Connector weiterleitet. Medien fließen vom Skype for Business-Client zum Cloud Connector-Vermittlungs Server und dann zum SBC oder Gateway, wie in der folgenden Abbildung dargestellt:
  
**Medien- und Signalisierungspfade ohne Medienumgehung**

![Signalisierung ohne Medienumgehung](../../media/5cd7e3bf-2565-4bd9-ad5a-f03e13c01060.png)
  
Ein eingehender Anruf aus dem PSTN verwendet den gleichen Signalisierungspfad in umgekehrter Richtung. Für interne Benutzer werden Medien weiterhin letztendlich zwischen dem Skype for Business-Client und dem Cloud Connector-Vermittlungs Server und dann dem SBC oder Gateway fließen.
  
In der nächsten Topologie, bei der die medienumgehung verwendet wird, hat das signalisieren denselben Pfad, doch die Medien fließen direkt zwischen dem Skype for Business-Client und dem SBC oder Gateway, wie in der folgenden Abbildung dargestellt:
  
**Medien- und Signalisierungspfade mit Medienumgehung**

![Signalisierung mit Medienumgehung](../../media/60400c38-4921-4964-89f2-5e53b68fb497.png)
  
## <a name="multi-site-scenario-and-media-bypass"></a>Szenario mit mehreren Standorten und Medienumgehung  

Die medienumgehung ist auch hilfreich, wenn Sie mit einer einzigen Cloud Connector-Appliance Telefoniedienst für mehrere Websites bereitstellen möchten. Da Cloud Connector Anrufe nicht basierend auf Quell-oder Zielrufnummern weiterleiten kann, stellen die meisten Unternehmen ein SBC-oder Gateway hinter Cloud Connector bereit, um Routingentscheidungen zu treffen. In diesem Szenario eliminiert die Medienumgehung wie im folgenden Diagramm gezeigt den Hop zwischen dem Client und dem zentralen SBC oder Gateway:
  
**Anwendung mit mehreren Standorten**

![Beispiel für Cloud Connector mit mehreren Standorten](../../media/ace8dc3c-1082-46a2-b8b4-98cbf678620e.png)
  
1. Der SIP-Datenverkehr fließt vom Benutzer in Zürich nach Office 365.
    
2. Der Datenverkehr wird dann an die Cloud Connector-Appliance in Amsterdam weitergeleitet, wie in der Richtlinie für die Benutzer VoIP-Routing angegeben.
    
3. Die Cloud Connector-Appliance in Amsterdam sendet den SIP-Datenverkehr an das zentrale Gateway in Amsterdam.
    
4. Das zentrale Gateway in Amsterdam trifft geeignete Routingentscheidungen und sendet dann den Datenverkehr an einen SBC oder ein Gateway in Zürich, während Medien direkt zwischen dem Skype for Business-Client und dem SBC oder Gateway in Amsterdam fließen.
    
   Dieser Ansatz ermöglicht es, mehr Benutzer pro eine Cloud Connector-Bereitstellung zu bedienen, wenn Cloud Connector zentralisiert ist. Auch wenn der Cloud Connector aus dem Medienpfad entfernt wird, kann das WAN in einem zentralisierten Szenario mit mehreren Standorten weiterhin zweimal so durchlaufen, wie es erforderlich ist, um den zentralisierten SBC oder das Gateway zu durchlaufen.
  
Wenn sich ein Client außerhalb des Unternehmensnetzwerks befindet und einen ausgehenden Anruf anbietet, fließt der Mediendatenverkehr über die Edge-und Vermittlungsserver des Cloud Connectors und der WAN-Verbindung zwischen Zürich und Amsterdam, wie in der folgenden Abbildung dargestellt:
  
![Beispiel 2 für Cloud Connector mit mehreren Standorten](../../media/ef95839c-4552-440e-9698-7615707a1b50.png)
  
## <a name="supported-clients-for-media-bypass"></a>Für Medienumgehung unterstützte Clients

Mit der ersten Version von Media Bypass ist der einzige unterstützte Client der Skype for Business 2016-Windows-Client, der Teil von Office 365 ProPlus, Version 16.0.7870.2020 oder höher ist. Kunden können jeden Kanal verwenden: monatlicher Kanal, halbjähriger Kanal oder First Release für verzögerten Kanal. 
  
> [!NOTE]
> Wenn Sie eine Client-VPN-Lösung in Kombination mit dem Skype for Business-Client verwenden, wird Medienumgehung nur mit einer VPN-Konfiguration mit geteiltem Tunnel unterstützt. 
  
Weitere Informationen zu den Freigabe Kanälen finden Sie unter [Übersicht über die Update Kanäle für Office 365 ProPlus](https://support.office.com/en-us/article/Overview-of-update-channels-for-Office-365-ProPlus-9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4?ui=en-US&amp;rs=en-US&amp;ad=US).
  
Die aktuelle Version der Clients in verschiedenen Kanälen finden Sie unter [Versionsinformationen für Updates für Office 365 ProPlus](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus). 
  
## <a name="cloud-connector-capacity-considerations-with-media-bypass"></a>Kapazitätsüberlegungen für Cloud Connector mit Medienumgehung

Ohne medienumgehung – und je nach Hardware – kann eine Cloud Connector-Appliance von 50 zu 500 gleichzeitige Anrufe verarbeiten, die Medien für den Transport über einen Vermittlungs Server erforderlich machen. Weitere Informationen finden Sie unter [Planen von Skype for Business Cloud Connector Edition](https://technet.microsoft.com/en-us/library/mt605227.aspx). 
  
Bei aktivierter Medienumgehung verwenden interne Clients in der unterstützten Version den Vermittlungsserver nicht, sodass die Anzahl der internen Clients erheblich zunehmen kann.  
  
Wie bereits erwähnt, verwenden externe Clients oder nicht unterstützte Clients die Edge-und Vermittlungsserver für Cloud-Connectors für Medien. Bei der Berechnung, wie viele Cloud Connector-Appliances auf einer Website gespeichert werden sollen, müssen Sie den Datenverkehr von externen Benutzern und Benutzern auf nicht unterstützten Clients berücksichtigen.
  
## <a name="cloud-connector-supports-always-bypass-mode"></a>Cloud Connector unterstützt den Modus „Immer umgehen“

Cloud Connector unterstützt nur den Bypass-Modus. In lokalen Umgebungen gibt es zwei Optionen: „Immer umgehen“ und „Use Site and Region Information“ (Standort- und Regionsinformationen verwenden).
  
„Immer umgehen“ bedeutet, dass Medienumgehung bei allen PSTN-Anrufen versucht wird, bei denen interne Clients Ursprung oder Ziel sind. Ob es sich um einen internen oder externen Client handelt, wird mithilfe einer Website in der virtuellen Maschine des Vermittlungsservers ermittelt. Wenn der Client die Website erreichen kann, gilt sie als intern, und die Medienumgehung wird verwendet. Wenn der Client die Website nicht erreichen kann (wenn sich der Client z. B. in einem Heimnetzwerk befindet), wird keine Medienumgehung verwendet.  
  
„Immer umgehen“ setzt unbehinderte Konnektivität zwischen Benutzern und den PSTN-Gateways an einem PSTN-Standort voraus.  
  
Weitere Informationen finden Sie unter [Planen von Skype for Business Cloud Connector Edition](https://technet.microsoft.com/en-us/library/mt605227.aspx). 
  
In der nachstehenden Abbildung müssen Europa Benutzer beispielsweise gut mit den drei Session Border Controllers (SBCS) in Amsterdam verbunden sein, während US West-Benutzer gut mit den beiden SBCS in Seattle verbunden sein müssen. „Gute Verbindung“ bedeutet, dass sie sich an den gleichen Netzwerkstandorten wie die SBCs oder Gateways befinden oder dass sie über WAN-Verbindungen mit entsprechender Bandbreite verfügen.
  
![Cloud Connector-Kapazität](../../media/efb2269b-d44f-474e-aea8-c5158e729cfe.png)
  
> [!NOTE]
> Wenn ein Benutzer aus Zürich zur Niederlassung in Seattle reist und Sie das interne Netzwerk zum Übermitteln des Mediendatenverkehrs zwischen dem reisenden Benutzer und den Gateways in Europa verwenden möchten (anstatt über das Internet zu gehen), müssen Sie sicherstellen, dass die Niederlassung in Seattle und die Niederlassung in Amsterdam, in der sich die europäischen SBCs oder Gateways befinden, als gut verbunden eingestuft werden können. 
  
## <a name="codecs-used-in-media-bypass"></a>Bei der Medienumgehung verwendete Codecs

Bei aktivierter Medienumgehung wird für den Mediendatenverkehr zwischen einem Client und einem SBC oder Gateway der Codec G.711 verwendet.  
  
## <a name="see-also"></a>Siehe auch

[Bereitstellen der medienumgehung in Cloud Connector Edition](deploy-media-bypass-in-cloud-connector.md)
