---
title: Bereitstellungsrichtlinien für den Vermittlungsserver in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
description: In diesem Thema werden Planungsrichtlinien für die Vermittlungs Server Bereitstellung beschrieben.
ms.openlocfilehash: fdfc18871e4aa9ea30d7a02063e7d1a0bc05b6ca
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277608"
---
# <a name="deployment-guidelines-for-mediation-server-in-skype-for-business-server"></a>Bereitstellungsrichtlinien für den Vermittlungsserver in Skype for Business Server
 
In diesem Thema werden Planungsrichtlinien für die Vermittlungs Server Bereitstellung beschrieben.
  
## <a name="collocated-or-stand-alone-mediation-server"></a>Oder eigenständigen Vermittlungs Server?

Der Vermittlungsserver befindet sich standardmäßig auf dem Standard Edition-Server oder Front-End-Server in einem Front-End-Pool an zentralen Standorten. Die Anzahl von Anrufen über das Telefonfestnetz (Public Switched Telephone Network, PSTN), die verarbeitet werden können, und die Anzahl erforderlicher Computer im Pool hängt von folgenden Faktoren ab:
  
- Die Anzahl der Gateway-Peers, die vom Vermittlungs Server Pool gesteuert werden.
    
- Datenverkehr zu Spitzenzeiten, der über diese Gateways verarbeitet wird
    
- Der Prozentsatz der Anrufe, deren Medien den Vermittlungs Server umgehen.
    
Berücksichtigen Sie bei der Planung unbedingt die Medienverarbeitungsanforderungen für PSTN-Anrufe und A/V-Konferenzen, die eine Medienumgehung nicht unterstützen, sowie die erforderliche Leistung zur Verarbeitung von Signalinteraktionen für die Anzahl von Anrufen zu Spitzenzeiten, die unterstützt werden müssen. Wenn Sie nicht über genügend CPU verfügen, müssen Sie einen eigenständigen Pool von Vermittlungsservern bereitstellen. Darüber hinaus müssen PSTN-Gateways, IP-PBX-Anlagen und SBCS in Teilmengen aufgeteilt werden, die von den zusammengefassten Vermittlungsservern in einem Pool und den eigenständigen Vermittlungsservern in einem oder mehreren eigenständigen Pools gesteuert werden.
  
Wenn Sie PSTN-Gateways, IP-PBX-Anlagen oder SBCS (Session Border Controllers) bereitgestellt haben, die nicht in der Lage sind, mit einem Pool von Vermittlungsservern zu interagieren, müssen Sie einem eigenständigen Pool zugeordnet werden, der aus einem einzelnen Vermittlungsserver besteht. Einige der Dinge, die von Ihren PSTN-Gateways, IP-Nebenstellenanlagen oder SBCs erledigt werden müssen, sind:
  
- Durchführen von DNS (Domain Name System)-Lastenausgleich auf Netzwerkebene über Vermittlungsserver in einem Pool (oder anderweitiges Weiterleiten des Datenverkehrs an alle Vermittlungsserver in einem Pool)
    
- Akzeptieren Sie den Datenverkehr von einem beliebigen Vermittlungs Server in einem Pool.
    
Sie können das Skype for Business-Planungs Tool verwenden, um zu ermitteln, ob abstimmen dem Vermittlungs Server mit dem Front-End-Pool die Last verarbeiten kann. Wenn Ihre Umgebung diese Anforderungen nicht erfüllen kann, müssen Sie einen eigenständigen Vermittlungs Server Pool bereitstellen.
  
## <a name="central-site-and-branch-site-considerations"></a>Überlegungen zum zentralen Standort und Zweigstellenstandort

 Vermittlungsserver am zentralen Standort können verwendet werden, um Anrufe für IP-PBX-oder PSTN-Gateways an Zweigstellen zu leiten. Wenn Sie jedoch SIP-Trunks bereitstellen, müssen Sie einen Vermittlungs Server an der Website bereitstellen, auf der jeder trunk beendet wird. Die Verwendung eines Vermittlungsservers an der zentralen Standort Route für Anrufe an ein IP-PBX-oder PSTN-Gateway an einer Zweigstelle erfordert keine medienumgehung, es wird jedoch eine medienumgehung empfohlen. Der Grund: Wenn Sie die Medienumgehung aktivieren können, wird die Latenz für den Medienpfad reduziert und somit eine bessere Medienqualität erreicht, da der Medienpfad nicht mehr dem Signalpfad folgen muss. Zudem wird durch die Medienumgehung die Verarbeitungslast des Pools verringert.
  
> [!NOTE]
> Die Medienumgehung funktioniert nicht mit allen PSTN-Gateways, IP-Nebenstellenanlagen oder SBCs. Microsoft hat eine Reihe von PSTN-Gateways und SBCs mit zertifizierten Partnern getestet und einige Tests mit IP-Nebenstellenanlagen von Cisco durchgeführt. Die medienumgehung wird nur mit Produkten und Versionen unterstützt, die unter Unified Communications Open Interoperability Program aufgelistet sind – lync Server unter [Explore getestete Geräte, Infrastruktur und Tools, die Ihre Skype for Business-Benutzeroberfläche unterstützen und erweitern](http://partnersolutions.skypeforbusiness.com/solutionscatalog). 
  
Wenn die Stabilität des Zweigstellen Standorts erforderlich ist, muss eine Survivable Branch-Appliance oder eine Kombination aus einem Front-End-Server, einem Vermittlungsserver und einem Gateway an der Zweigstelle bereitgestellt werden. (Die Annahme, dass die Stabilität des Zweigstellen Standorts davon ausgeht, dass Anwesenheit und Konferenzen auf der Website nicht belastbar sind.) Anleitungen zur Planung von Branch-Websites für VoIP finden Sie unter [Planen der Enterprise-VoIP-Resilienz in Skype for Business Server](../enterprise-voice-solution/enterprise-voice-resiliency.md).
  
Für Interaktionen mit einer IP-PBX-Anlage, wenn die IP-Telefonanlage nicht ordnungsgemäß frühe Medien Interaktionen mit mehreren frühen Dialogfeldern und RFC 3960-Interaktionen unterstützt, können die ersten Wörter der Ansage für eingehende Anrufe von der IP-PBX zu lync-Endpunkten abgeschnitten werden. Dieses Verhalten kann gravierender sein, wenn ein Vermittlungs Server an einem zentralen Standort Routing Anrufe für eine IP-PBX-Anlage durchführt, bei der die Route an einer Zweigstelle beendet wird, da für die Signalisierungs Ausführung mehr Zeit benötigt wird. Wenn dieses Verhalten auftritt, ist die Bereitstellungeines Vermittlungsservers auf der Verzweigungs Website die einzige Möglichkeit, das Clipping der ersten Wörter zu reduzieren.
  
Wenn Ihre zentrale Website über eine TDM-Telefonanlage verfügt oder wenn Ihre IP-Telefonanlage nicht die Notwendigkeit eines PSTN-Gateways beseitigt, müssen Sie ein Gateway auf der Anrufroute bereitstellen, die den Vermittlungs Server und die Telefonanlage verbindet.
  
> [!NOTE]
> Um die Medienqualität von eigenständigen Vermittlungsservern zu verbessern, sollten Sie RSS (Receive-Side Scaling) für die Netzwerkadapter dieser Server aktivieren. Mit RSS können eingehende Pakete gleichzeitig von mehreren Prozessoren auf dem Server verarbeitet werden. Ausführliche Informationen finden Sie unter[Verbesserungen bei der Empfangs seitigen Skalierung in Windows Server](https://go.microsoft.com/fwlink/p/?LinkId=268731). Weitere Informationen zum Aktivieren von RSS finden Sie in der Dokumentation zu Ihrem Netzwerkadapter. 
  

