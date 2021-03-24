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
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e69ac58c-e8fe-40bc-a4c8-f0a0190fbaa7
description: Lesen Sie dieses Thema, um Planungsüberlegungen für die Implementierung der Medienumgehung mit Cloud Connector Edition, Version 2.0 und höher, zu überprüfen. Informationen zum Bereitstellen der Medienumgehung finden Sie unter Deploy media bypass in Cloud Connector Edition.
ms.openlocfilehash: bae10c77a6b382eaca7189ed6ae52960a6fb1bf9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096199"
---
# <a name="plan-for-media-bypass-in-cloud-connector-edition"></a>Planen der Medienumgehung in der Cloud Connector Edition
 
Lesen Sie dieses Thema, um Planungsüberlegungen für die Implementierung der Medienumgehung mit Cloud Connector Edition, Version 2.0 und höher, zu überprüfen. Informationen zum Bereitstellen der Medienumgehung finden Sie unter [Deploy media bypass in Cloud Connector Edition](deploy-media-bypass-in-cloud-connector.md).
  
Mit der Medienumgehung kann ein Client Medien direkt an das Public Switched Telephone Network (PSTN) des nächsten Hops senden – ein Gateway oder einen Session Border Controller (SBC) – und die Cloud Connector Edition-Komponente aus dem Medienpfad entfernen.
  
Die Medienumgehung kann die Sprachqualität verbessern, indem die Latenz, die Möglichkeit eines Paketverlusts und die Anzahl der potenziellen Fehlerpunkte reduziert werden. Die Eliminierung der Medienverarbeitung für umgangene Anrufe verringert die Last für Cloud Connector, was eine höhere Anzahl gleichzeitiger Anrufe ermöglicht und die Skalierbarkeit verbessern kann. 
  
 Wenn Sie Cloud Connector von Medienverarbeitungsaufgaben lösen, kann die Anzahl der Cloud Connector-Appliances reduziert werden, die für eine Infrastruktur erforderlich sind. Daher sollten Sie die Medienumgehung nach Möglichkeit aktivieren.
  
## <a name="how-media-bypass-affects-media-and-signaling-pathways"></a>Auswirkungen der Medienumgehung auf Medien- und Signalpfade

Während die Signalisierung denselben Pfad mit oder ohne Medienumgehung einnimmt, unterscheidet sich der Medienfluss. Die folgenden Diagramme zeigen Medien- und Signalpfade in Topologien mit und ohne Medienumgehung. 
  
In der folgenden Topologie, die keine Medienumgehung verwendet, führt beispielsweise ein Skype for Business-Client einen PSTN-Anruf an eine externe Nummer aus, die SIP-Signalisierung geht an Microsoft 365 oder Office 365, die den Signaldatenverkehr gemäß der Endbenutzer-Voicerichtlinie leitet. Für Cloud Connector-Benutzer leitet die Voicerichtlinie den Signaldatenverkehr an den Cloud Connector Edge Server weiter, der dann den Signaldatenverkehr über den Cloud Connector Mediation Server an einen PSTN Session Border Controller (SBC) oder gateway weiter leitet. Medien fließen vom Skype for Business-Client zum Cloud Connector-Vermittlungsserver und dann zum SBC oder Gateway, wie im folgenden Diagramm dargestellt:
  
**Medien- und Signalpfade ohne Medienumgehung**

![Signalisierung ohne Medienumgehung](../../media/5cd7e3bf-2565-4bd9-ad5a-f03e13c01060.png)
  
Ein eingehender Anruf aus dem PSTN verwendet denselben Signalpfad in umgekehrter Richtung. Für interne Benutzer fließen medien letztlich weiterhin zwischen dem Skype for Business-Client und dem Cloud Connector Mediation Server und dann zwischen dem SBC oder Gateway.
  
In der nächsten Topologie , in der die Medienumgehung verwendet wird, erfolgt die Signalisierung auf denselben Pfad, aber Medien fließen direkt zwischen dem Skype for Business-Client und dem SBC oder Gateway, wie im folgenden Diagramm dargestellt:
  
**Medien- und Signalpfade mit Medienumgehung**

![Signalisierung mit Medienumgehung](../../media/60400c38-4921-4964-89f2-5e53b68fb497.png)
  
## <a name="multi-site-scenario-and-media-bypass"></a>Szenario mit mehreren Standort und Medienumgehung

Die Medienumgehung ist auch hilfreich, wenn Sie Telefoniedienste für mehrere Standorte mithilfe einer einzelnen Cloud Connector-Appliance bereitstellen möchten. Da Cloud Connector Anrufe nicht basierend auf Quell- oder Zielnummern weiterleiten kann, stellen die meisten Unternehmen einen SBC oder ein Gateway hinter Cloud Connector zur Entscheidung über das Routing ein. Die Medienumgehung in diesem Szenario eliminiert den Hop zwischen dem Client und dem zentralen SBC oder Gateway, wie im folgenden Diagramm dargestellt:
  
**Anwendung mit mehreren Websiten**

![Beispiel für cloudconnector für mehrere Standorte](../../media/ace8dc3c-1082-46a2-b8b4-98cbf678620e.png)
  
1. Der SIP-Datenverkehr fließt vom Benutzer in Zürich zu Microsoft 365 oder Office 365.
    
2. Der Datenverkehr wird dann wie in der Benutzer-Voiceroutingrichtlinie angegeben an die Cloud Connector-Appliance in Amsterdam weiterleit.
    
3. Die Cloud Connector-Appliance in Amsterdam sendet den SIP-Datenverkehr an das zentrale Gateway in Amsterdam.
    
4. Das zentrale Gateway in Amsterdam trifft die entsprechenden Routingentscheidungen und sendet dann den Datenverkehr an einen SBC oder Gateway in Zürich, während Medien direkt zwischen dem Skype for Business-Client und dem SBC oder Gateway in Amsterdam fließen.
    
   Dieser Ansatz ermöglicht die Bereitstellung von mehr Benutzern pro Cloud Connector-Bereitstellung, bei der Cloud Connector zentralisiert ist. Auch wenn Cloud Connector aus dem Medienpfad entfernt ist, können Medien in einem zentralisierten Szenario mit mehreren Standort immer noch doppelt so viele Wan durchlaufen wie erforderlich, um den zentralisierten SBC oder das Gateway zu durchlaufen.
  
Wenn sich ein Client außerhalb des Unternehmensnetzwerks befindet, der einen ausgehenden Anruf tätigt, fließt der Mediendatenverkehr über die Edge- und Vermittlungsserver von Cloud Connector und die WAN-Verbindung zwischen Zürich und Amsterdam, wie im folgenden Diagramm dargestellt:
  
![Cloud Connector Multisite (Beispiel 2)](../../media/ef95839c-4552-440e-9698-7615707a1b50.png)
  
## <a name="supported-clients-for-media-bypass"></a>Unterstützte Clients für die Medienumgehung

Mit der ersten Version der Medienumgehung wird nur der Skype for Business 2016 Windows Client unterstützt, der Teil von Microsoft 365 Apps for Enterprise, Version 16.0.7870.2020 oder höher ist. Kunden können einen beliebigen Kanal verwenden: Current, Deferred oder First Release Deferred. 
  
> [!NOTE]
> Wenn Sie eine Client-VPN-Lösung in Kombination mit dem Skype for Business-Client verwenden, wird die Medienumgehung nur mit einer VPN-Konfiguration mit geteilten Tunneln unterstützt. 
  
Weitere Informationen zu den Veröffentlichungskanälen finden Sie unter Übersicht über [Updatekanäle für Microsoft 365 Apps for Enterprise](https://support.office.com/article/Overview-of-update-channels-for-Office-365-ProPlus-9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4?ui=en-US&amp;rs=en-US&amp;ad=US).
  
Die aktuelle Version der Clients in verschiedenen Kanälen finden Sie unter [Release information for updates to Microsoft 365 Apps for Enterprise](/officeupdates/release-notes-office365-proplus). 
  
## <a name="cloud-connector-capacity-considerations-with-media-bypass"></a>Überlegungen zur Cloud Connector-Kapazität bei der Medienumgehung

Ohne Medienumgehung – und je nach Hardware – kann eine Cloud Connector-Appliance zwischen 50 und 500 gleichzeitige Anrufe verarbeiten, für die Medien über einen Vermittlungsserver übertragen werden müssen. Weitere Informationen finden Sie unter [Plan for Skype for Business Cloud Connector Edition](./plan-skype-for-business-cloud-connector-edition.md). 
  
Wenn die Medienumgehung aktiviert ist, verwenden interne Clients der unterstützten Version nicht den Vermittlungsserver, sodass die Anzahl der internen Clients erheblich steigen kann. 
  
Wie oben erwähnt, verwenden externe Clients oder nicht unterstützte Clients den Cloud Connector Edge und Vermittlungsserver für Medien. Wenn Sie berechnen, wie viele Cloud Connector-Appliances an einem Standort platziert werden sollen, müssen Sie den Datenverkehr von externen Benutzern und Benutzern auf nicht unterstützten Clients berücksichtigen.
  
## <a name="cloud-connector-supports-always-bypass-mode"></a>Cloud Connector unterstützt den Always Bypass-Modus

Cloud Connector unterstützt nur den Always Bypass-Modus. In lokalen Umgebungen gibt es zwei Optionen: Immer Standort- und Regioneninformationen umgehen und verwenden.
  
Always Bypass bedeutet, dass für alle PSTN-Anrufe mit internen Clients als Ursprung oder Zielpunkt die Medienumgehung versucht wird. Um festzustellen, ob der Client intern oder extern ist, wird eine Website auf dem virtuellen Vermittlungsservercomputer verwendet. Wenn der Client die Website erreichen kann, wird er als intern betrachtet, und die Medienumgehung wird verwendet. Wenn der Client den Standort nicht erreichen kann (z. B. befindet sich der Client in einem Heimnetzwerk), wird keine Medienumgehung verwendet. 
  
Die Always Bypass erfordert eine ungehinderte Verbindung zwischen Benutzern und den PSTN-Gateways innerhalb eines PSTN-Standorts. 
  
Weitere Informationen finden Sie unter [Plan for Skype for Business Cloud Connector Edition](./plan-skype-for-business-cloud-connector-edition.md). 
  
Im folgenden Diagramm müssen die Benutzer in Europa beispielsweise gut mit den drei Session Border Controllern (SBCs) in Amsterdam verbunden sein, während Benutzer aus dem US-Westen gut mit den beiden SBCs in Seattle verbunden sein müssen. Gut verbunden bedeutet, dass sie sich entweder an denselben Netzwerkstandorten wie die SBCs oder Gateways oder über WAN-Verbindungen befinden, die über die richtige Bandbreite verfügen.
  
![Cloud Connector Capacity](../../media/efb2269b-d44f-474e-aea8-c5158e729cfe.png)
  
> [!NOTE]
> Wenn ein Benutzer aus Zürich in das Büro in Seattle reist und Sie das interne Netzwerk verwenden möchten, um den Mediendatenverkehr zwischen dem reisenden Benutzer und den Gateways in Europa zu liefern (an stelle über das Internet), müssen Sie sicherstellen, dass das Büro in Seattle und das Büro in Amsterdam, in dem sich europäische SBCs oder Gateways befinden, ebenfalls verbunden sind. 
  
## <a name="codecs-used-in-media-bypass"></a>Codecs, die bei der Medienumgehung verwendet werden

Wenn die Medienumgehung aktiviert ist, verwendet der Mediendatenverkehr zwischen einem Client und einem SBC oder Gateway den G.711-Codec. 
  
## <a name="see-also"></a>Siehe auch

[Bereitstellen der Medienumgehung in Cloud Connector Edition](deploy-media-bypass-in-cloud-connector.md)