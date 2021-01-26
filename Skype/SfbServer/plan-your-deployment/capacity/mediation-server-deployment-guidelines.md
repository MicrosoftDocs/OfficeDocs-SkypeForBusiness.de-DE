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
ms.openlocfilehash: 245916286fe5f1590581989b8a09daf637c03aa9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800085"
---
# <a name="deployment-guidelines-for-mediation-server-in-skype-for-business-server"></a>Bereitstellungsrichtlinien für Vermittlungsserver in Skype for Business Server
 
In diesem Thema werden Planungsrichtlinien für die Vermittlungsserverbereitstellung beschrieben.
  
## <a name="collocated-or-stand-alone-mediation-server"></a>Collocated or Stand-alone Mediation Server?

Der Vermittlungsserver ist standardmäßig auf dem Standard Edition- oder Front-End-Server in einem Front-End-Pool an zentralen Standorten ausgeführt. Die Anzahl der Festnetzanrufe( Public Switched Telephone Network, PSTN), die verarbeitet werden können, und die Anzahl der in dem Pool erforderlichen Computer hängt von:
  
- Die Anzahl der Gateway-Peers, die der Vermittlungsserverpool steuert.
    
- Die Zeiträume für hohen Datenverkehr über diese Gateways.
    
- Der Prozentsatz der Anrufe, deren Medien den Vermittlungsserver umgehen.
    
Berücksichtigen Sie bei der Planung unbedingt die Medienverarbeitungsanforderungen für PSTN-Anrufe und A/V-Konferenzen, die keine Medienumgehung unterstützen, sowie die Verarbeitung, die erforderlich ist, um Signalinteraktionen für die Anzahl der Anrufe während der Gebuchtzeit zu verarbeiten, die unterstützt werden müssen. Wenn Sie nicht über genügend CPU verfügen, müssen Sie einen eigenständigen Pool von Vermittlungsservern bereitstellen. Darüber hinaus müssen PSTN-Gateways, IP-PBX-Anlagen und SBCs in Teilmengen aufgeteilt werden, die von den zugeordneten Vermittlungsservern in einem Pool und den eigenständigen Vermittlungsservern in einem oder mehreren eigenständigen Pools gesteuert werden.
  
Wenn Sie PSTN-Gateways, IP-PBX-Anlagen oder Session Border Controller (SBCs) bereitgestellt haben, die nicht mit einem Pool von Vermittlungsservern interagieren können, müssen sie einem eigenständigen Pool zugeordnet werden, der aus einem einzelnen Vermittlungsserver besteht. Zu den Dinge, die Ihre PSTN-Gateways, IP-PBXs oder SBCs benötigen, gehören:
  
- Durchführen eines Netzwerkschicht-DNS-Lastenausgleichs für Vermittlungsserver in einem Pool (oder anderweitige einheitliches Routen des Datenverkehrs an alle Vermittlungsserver in einem Pool).
    
- Akzeptieren sie Datenverkehr von einem beliebigen Vermittlungsserver in einem Pool.
    
Sie können das Skype for Business Planning Tool verwenden, um zu bewerten, ob das Verbinden des Vermittlungsservers mit Ihrem Front-End-Pool die Last bewältigen kann. Wenn Ihre Umgebung diese Anforderungen nicht erfüllen kann, müssen Sie einen eigenständigen Vermittlungsserverpool bereitstellen.
  
## <a name="central-site-and-branch-site-considerations"></a>Überlegungen zum zentralen Standort und Zweigstellenstandort

 Vermittlungsserver am zentralen Standort können zum Weiterleiten von Anrufen für IP-Nebenstellenanlagen oder PSTN-Gateways an Zweigstellenstandorten verwendet werden. Bei der Bereitstellung von SIP-Trunks müssen Sie jedoch einen Vermittlungsserver an dem Standort bereitstellen, an dem jeder Trunk beendet wird. Ein Vermittlungsserver am zentralen Standort führt Anrufe für eine IP-PBX- oder ein PSTN-Gateway an einem Zweigstellenstandort aus, die Medienumgehung ist jedoch nicht erforderlich, es wird jedoch eine Medienumgehung empfohlen. Wenn Sie die Medienumgehung aktivieren können, verringert dies die Latenz des Medienpfads und führt folglich zu einer verbesserten Medienqualität, da der Medienpfad nicht dem Signalpfad folgen muss. Zudem wird durch die Medienumgehung die Verarbeitungslast des Pools verringert.
  
> [!NOTE]
> Die Medienumgehung funktioniert nicht mit jedem PSTN-Gateway, jeder IP-PBX-Anlage und jedem SBC. Microsoft hat eine Reihe von PSTN-Gateways und SBCs mit zertifizierten Partnern getestet und einige Tests mit Cisco IP-PBXs durchgeführt. Die Medienumgehung wird nur mit Produkten und Versionen unterstützt, die im Unified Communications Open Interoperability Program aufgeführt sind – Lync Server unter Explore getestete Geräte, Infrastruktur und Tools, die Ihre Skype for Business-Erfahrung [unterstützen und erweitern.](http://partnersolutions.skypeforbusiness.com/solutionscatalog) 
  
Wenn Ausfallsicherheit für Zweigstellenstandorte erforderlich ist, muss eine Survivable Branch Appliance oder eine Kombination aus einem Front-End-Server, einem Vermittlungsserver und einem Gateway am Zweigstellenstandort bereitgestellt werden. (Bei ausfallsicheren Zweigstellenstandorten wird davon ausgegangen, dass Anwesenheits- und Konferenzstandorte am Standort nicht ausfallsicher sind.) Anleitungen zur Planung von Zweigstellenstandorten für Sprachnachrichten finden Sie unter ["Plan for Enterprise-VoIP resiliency in Skype for Business Server ".](../enterprise-voice-solution/enterprise-voice-resiliency.md)
  
Wenn die IP-PBX-Anlage bei Interaktionen mit einer IP-PBX-Anlage frühe Medieninteraktionen mit mehreren frühen Dialogen und RFC 3960-Interaktionen nicht ordnungsgemäß unterstützt, können die ersten Wörter der Begrüßung für eingehende Anrufe von der IP-PBX-Anlage an die Endpunkte von Lync abgeschnitten werden. Dieses Verhalten kann schwerwiegender sein, wenn ein Vermittlungsserver an einem zentralen Standort Anrufe für eine IP-PBX-Anlage weiterleite, an der die Route an einem Zweigstellenstandort endet, da mehr Zeit für den Abschluss der Signalisierung erforderlich ist. Wenn sie dieses Verhalten haben, ist die Bereitstellung eines Vermittlungsservers am Zweigstellenstandort die einzige Möglichkeit, die Beschneidung der ersten Wörter zu reduzieren.
  
Wenn der zentrale Standort über eine TDM-Nebenstellenlage verfügt oder die Notwendigkeit eines PSTN-Gateways durch die IP-Nebenstellenanlage nicht eliminiert wird, müssen Sie ein Gateway zur Anrufroute hinzufügen, das mit dem Vermittlungsserver und der Nebenstellenanlage verbunden ist.
  
> [!NOTE]
> Um die Medienleistung des eigenständigen Vermittlungsservers zu verbessern, sollten Sie rss (Receive-Side Scaling) auf den Netzwerkadaptern auf diesen Servern aktivieren. Mit RSS können eingehende Pakete gleichzeitig von mehreren Prozessoren auf dem Server verarbeitet werden. Weitere Informationen finden Sie unter "[Receive-Side Scaling Enhancements in Windows Server".](https://go.microsoft.com/fwlink/p/?LinkId=268731) Ausführliche Informationen zum Aktivieren von RSS finden Sie in der Dokumentation zum Netzwerkadapter. 
  

