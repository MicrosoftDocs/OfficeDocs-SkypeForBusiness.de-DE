---
title: Bereitstellungsrichtlinien für Vermittlungsserver in Skype for Business Server
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
ms.collection: IT_Skype16
ms.assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
description: In diesem Thema werden Planungsrichtlinien für die Vermittlungsserverbereitstellung beschrieben.
ms.openlocfilehash: ffb60abaf3027541f13fe73294eafda51e5d1d0f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118534"
---
# <a name="deployment-guidelines-for-mediation-server-in-skype-for-business-server"></a>Bereitstellungsrichtlinien für Vermittlungsserver in Skype for Business Server
 
In diesem Thema werden Planungsrichtlinien für die Vermittlungsserverbereitstellung beschrieben.
  
## <a name="collocated-or-stand-alone-mediation-server"></a>Kollokierter oder eigenständiger Vermittlungsserver?

Der Vermittlungsserver ist standardmäßig auf dem Standard Edition- oder Front-End-Server in einem Front-End-Pool an zentralen Standorten zusammengeknallt. Die Anzahl der Telefonanrufe (Public Switched Telephone Network, PSTN), die verarbeitet werden können, und die Anzahl der im Pool benötigten Computer hängt von den
  
- Die Anzahl der Gateway peers, die der Vermittlungsserverpool steuert.
    
- Die Zeiträume mit hohem Datenverkehr über diese Gateways.
    
- Der Prozentsatz der Anrufe, deren Medien den Vermittlungsserver umgehen.
    
Berücksichtigen Sie bei der Planung unbedingt die Medienverarbeitungsanforderungen für PSTN-Anrufe und A/V-Konferenzen, die keine Medienumgehung unterstützen, sowie die Verarbeitung, die erforderlich ist, um Signalinteraktionen für die Anzahl der Anrufe während der Gebuchtzeit zu verarbeiten, die unterstützt werden müssen. Wenn Sie nicht über genügend CPU verfügen, müssen Sie einen eigenständigen Pool von Vermittlungsservern bereitstellen. Darüber hinaus müssen PSTN-Gateways, IP-PBXs und SBCs in Teilmengen aufgeteilt werden, die von den zugeordneten Vermittlungsservern in einem Pool und den eigenständigen Vermittlungsservern in einem oder mehreren eigenständigen Pools gesteuert werden.
  
Wenn Sie PSTN-Gateways, IP-PBXs oder Session Border Controller (SBCs) bereitgestellt haben, die nicht mit einem Pool von Vermittlungsservern interagieren können, müssen sie einem eigenständigen Pool zugeordnet werden, der aus einem einzelnen Vermittlungsserver besteht. Zu den folgenden Maßnahmen müssen Ihre PSTN-Gateways, IP-PBXs oder SBCs gehören:
  
- Führen Sie den Lastenausgleich des Domänennamenssystems (Domain Name System, DNS) auf Vermittlungsservern in einem Pool durch (oder führen Sie den Datenverkehr auf andere Weise einheitlich an alle Vermittlungsserver in einem Pool aus).
    
- Akzeptieren des Datenverkehrs von einem beliebigen Vermittlungsserver in einem Pool.
    
Sie können das Skype for Business Planning Tool verwenden, um zu bewerten, ob das Verbinden des Vermittlungsservers mit Ihrem Front-End-Pool die Last verarbeiten kann. Wenn Ihre Umgebung diese Anforderungen nicht erfüllen kann, müssen Sie einen eigenständigen Vermittlungsserverpool bereitstellen.
  
## <a name="central-site-and-branch-site-considerations"></a>Überlegungen zum zentralen Standort und Zweigstellenstandort

 Vermittlungsserver am zentralen Standort können zum Weiterleiten von Anrufen für IP-Nebenstellenanlagen oder PSTN-Gateways an Zweigstellenstandorten verwendet werden. Wenn Sie jedoch SIP-Trunks bereitstellen, müssen Sie einen Vermittlungsserver am Standort bereitstellen, an dem jeder Trunk beendet wird. Wenn ein Vermittlungsserver an der zentralen Standortroute Anrufe für eine IP-PBX- oder PSTN-Gateway an einem Zweigstellenstandort aufruft, ist keine Medienumgehung erforderlich, es wird jedoch eine Medienumgehung empfohlen. Wenn Sie die Medienumgehung aktivieren können, reduziert sie die Medienpfadlatenz und führt folglich zu einer verbesserten Medienqualität, da der Medienpfad nicht erforderlich ist, um dem Signalpfad zu folgen. Zudem wird durch die Medienumgehung die Verarbeitungslast des Pools verringert.
  
> [!NOTE]
> Die Medienumgehung funktioniert nicht mit jedem PSTN-Gateway, jeder IP-PBX und jedem SBC. Microsoft hat eine Reihe von PSTN-Gateways und SBCs mit zertifizierten Partnern getestet und einige Tests mit Cisco IP-PBXs durchgeführt. Die Medienumgehung wird nur mit Produkten und Versionen unterstützt, die im Unified Communications Open Interoperability Program - Lync Server unter [Explore tested devices, infrastructure, and tools](http://partnersolutions.skypeforbusiness.com/solutionscatalog)that support and extend your Skype for Business experience aufgeführt sind. 
  
Wenn Ausfallsicherheit für Zweigstellenstandorte erforderlich ist, muss eine Survivable Branch Appliance oder eine Kombination aus einem Front-End-Server, einem Vermittlungsserver und einem Gateway am Zweigstellenstandort bereitgestellt werden. (Bei ausfallsicheren Zweigstellenstandorten wird davon ausgegangen, dass Anwesenheit und Konferenzen am Standort nicht ausfallsicher sind.) Anleitungen zur Planung von Zweigstellenstandorten für Voice finden Sie unter [Plan for Enterprise-VoIP resiliency in Skype for Business Server](../enterprise-voice-solution/enterprise-voice-resiliency.md).
  
Wenn die IP-PBX bei Interaktionen mit einer IP-PBX frühe Medieninteraktionen mit mehreren frühen Dialogen und RFC 3960-Interaktionen nicht ordnungsgemäß unterstützt, können die ersten Wörter der Begrüßung für eingehende Anrufe von der IP-PBX an Lync-Endpunkte abgeschnitten werden. Dieses Verhalten kann schwerwiegender sein, wenn ein Vermittlungsserver an einem zentralen Standort Anrufe für eine IP-PBX weiterleite, bei der die Route an einem Zweigstellenstandort beendet wird, da mehr Zeit zum Abschließen der Signalisierung erforderlich ist. Wenn Sie dieses Verhalten erleben, ist die Bereitstellung eines Vermittlungsservers am Zweigstellenstandort die einzige Möglichkeit, die Beschneidung der ersten Wörter zu reduzieren.
  
Wenn der zentrale Standort über eine TDM-Nebenstellenlage verfügt oder die Notwendigkeit eines PSTN-Gateways durch die IP-Nebenstellenanlage nicht eliminiert wird, müssen Sie ein Gateway zur Anrufroute hinzufügen, das mit dem Vermittlungsserver und der Nebenstellenanlage verbunden ist.
  
> [!NOTE]
> Um die Medienleistung des eigenständigen Vermittlungsservers zu verbessern, sollten Sie die empfangsseitige Skalierung (RSS) auf den Netzwerkadaptern auf diesen Servern aktivieren. Mit RSS können eingehende Pakete gleichzeitig von mehreren Prozessoren auf dem Server verarbeitet werden. Weitere Informationen finden Sie unter "[Receive-Side Scaling Enhancements in Windows Server](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh997036(v=ws.11))". Ausführliche Informationen zum Aktivieren von RSS finden Sie in der Netzwerkadapterdokumentation. 
