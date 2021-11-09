---
title: Bereitstellungsrichtlinien für den Vermittlungsserver in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
description: In diesem Thema werden Die Planungsrichtlinien für die Bereitstellung des Vermittlungsservers beschrieben.
ms.openlocfilehash: 99f975d3dddb8837569c8e8aa1128f7515b2d562
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60844168"
---
# <a name="deployment-guidelines-for-mediation-server-in-skype-for-business-server"></a>Bereitstellungsrichtlinien für den Vermittlungsserver in Skype for Business Server
 
In diesem Thema werden Die Planungsrichtlinien für die Bereitstellung des Vermittlungsservers beschrieben.
  
## <a name="collocated-or-stand-alone-mediation-server"></a>Verbundener oder eigenständiger Vermittlungsserver?

Der Vermittlungsserver ist standardmäßig auf dem Standard Edition Server oder dem Front-End-Server in einem Front-End-Pool an zentralen Standorten verbunden. Die Anzahl der PsTN-Anrufe (Public Switched Telephone Network), die verarbeitet werden können, und die Anzahl der für den Pool erforderlichen Computer hängt von Folgenden ab:
  
- Die Anzahl der Gatewaypeers, die vom Vermittlungsserverpool gesteuert werden.
    
- Die Datenverkehrszeiträume mit hohem Datenverkehr über diese Gateways.
    
- Der Prozentsatz der Anrufe, bei denen es sich um Anrufe handelt, deren Medien den Vermittlungsserver umgehen.
    
Berücksichtigen Sie bei der Planung unbedingt die Medienverarbeitungsanforderungen für PSTN-Anrufe und A/V-Konferenzen, die keine Medienumgehung unterstützen, sowie die Verarbeitung, die erforderlich ist, um Signalinteraktionen für die Anzahl der Anrufe zu Auslastungsstunden zu verarbeiten, die unterstützt werden müssen. Wenn Sie nicht über genügend CPU verfügen, müssen Sie einen eigenständigen Pool von Vermittlungsservern bereitstellen. Darüber hinaus müssen PSTN-Gateways, IP-Nebenstellenanlagen und SBCs in Teilmengen aufgeteilt werden, die von den verbundenen Vermittlungsservern in einem Pool und den eigenständigen Vermittlungsservern in einem oder mehreren eigenständigen Pools gesteuert werden.
  
Wenn Sie PSTN-Gateways, IP-Nebenstellenanlagen oder SBCs (Session Border Controller) bereitgestellt haben, die nicht mit einem Pool von Vermittlungsservern interagieren können, müssen sie einem eigenständigen Pool zugeordnet werden, der aus einem einzelnen Vermittlungsserver besteht. Zu den Aufgaben, die Ihre PSTN-Gateways, IP-PBXs oder SBCs ausführen müssen, gehören:
  
- Führen Sie einen DNS-Lastenausgleich (Domain Name System) auf Netzwerkebene über Vermittlungsserver in einem Pool aus (oder leiten Sie den Datenverkehr auf andere Weise einheitlich an alle Vermittlungsserver in einem Pool weiter).
    
- Akzeptieren sie Datenverkehr von einem beliebigen Vermittlungsserver in einem Pool.
    
Sie können das Skype for Business-Planungstool verwenden, um zu bewerten, ob das Verbinden des Vermittlungsservers mit Ihrem Front-End-Pool die Last verarbeiten kann. Wenn Ihre Umgebung diese Anforderungen nicht erfüllen kann, müssen Sie einen eigenständigen Vermittlungsserverpool bereitstellen.
  
## <a name="central-site-and-branch-site-considerations"></a>Überlegungen zum zentralen Standort und Zweigstellenstandort

 Vermittlungsserver am zentralen Standort können zum Weiterleiten von Anrufen für IP-Nebenstellenanlagen oder PSTN-Gateways an Zweigstellenstandorten verwendet werden. Wenn Sie jedoch SIP-Trunks bereitstellen, müssen Sie einen Vermittlungsserver an dem Standort bereitstellen, an dem jeder Trunk beendet wird. Wenn ein Vermittlungsserver am zentralen Standort Anrufe für eine IP-Nebenstellenanlage oder ein PSTN-Gateway an einem Zweigstellenstandort leitet, ist keine Medienumgehung erforderlich, es wird jedoch eine Medienumgehung empfohlen. Das liegt daran, dass die Medienpfadlatenz reduziert wird, wenn Sie die Medienumgehung aktivieren können, und folglich zu einer verbesserten Medienqualität führt, da der Medienpfad nicht dem Signalpfad folgen muss. Zudem wird durch die Medienumgehung die Verarbeitungslast des Pools verringert.
  
> [!NOTE]
> Die Medienumgehung funktioniert nicht mit jedem PSTN-Gateway, jeder IP-Nebenstellenanlage und jedem SBC. Microsoft hat eine Reihe von PSTN-Gateways und SBCs mit zertifizierten Partnern getestet und einige Tests mit Ip-Nebenstellenanlagen von Cisco durchgeführt. Die Medienumgehung wird nur mit Produkten und Versionen unterstützt, die im Unified Communications Open Interoperability-Programm aufgeführt sind – Lync Server bei [Explore getestete Geräte, Infrastruktur und Tools, die Ihre Skype for Business unterstützen und erweitern.](http://partnersolutions.skypeforbusiness.com/solutionscatalog) 
  
Wenn Ausfallsicherheit für Zweigstellenstandorte erforderlich ist, muss eine Survivable Branch Appliance oder eine Kombination aus einem Front-End-Server, einem Vermittlungsserver und einem Gateway am Zweigstellenstandort bereitgestellt werden. (Bei der Ausfallsicherheit von Zweigstellenstandorten wird davon ausgegangen, dass Anwesenheits- und Konferenzfunktionen am Standort nicht ausfallsicher sind.) Anleitungen zur Planung von Zweigstellen für VoIP finden Sie unter [Plan for Enterprise-VoIP resiliency in Skype for Business Server](../enterprise-voice-solution/enterprise-voice-resiliency.md).
  
Wenn die IP-Nebenstellenanlage bei Interaktionen mit einer IP-Nebenstellenanlage frühe Medieninteraktionen mit mehreren frühen Dialogfeldern und RFC 3960-Interaktionen nicht ordnungsgemäß unterstützt, können die ersten Wörter der Begrüßung für eingehende Anrufe von der IP-Nebenstellenanlage an Lync-Endpunkte beschnitten werden. Dieses Verhalten kann schwerwiegender sein, wenn ein Vermittlungsserver an einem zentralen Standort Anrufe für eine IP-Nebenstellenanlage weiterleitet, bei der die Route an einem Zweigstellenstandort beendet wird, da mehr Zeit erforderlich ist, um die Signalisierung abzuschließen. Wenn dieses Verhalten vorliegt, ist die Bereitstellung eines Vermittlungsservers an der Zweigstelle die einzige Möglichkeit, die Beschneidung der ersten Wörter zu reduzieren.
  
Wenn der zentrale Standort über eine TDM-Nebenstellenlage verfügt oder die Notwendigkeit eines PSTN-Gateways durch die IP-Nebenstellenanlage nicht eliminiert wird, müssen Sie ein Gateway zur Anrufroute hinzufügen, das mit dem Vermittlungsserver und der Nebenstellenanlage verbunden ist.
  
> [!NOTE]
> Um die Medienleistung des eigenständigen Vermittlungsservers zu verbessern, sollten Sie RSS (Receive-Side Scaling) auf den Netzwerkadaptern auf diesen Servern aktivieren. Mit RSS können eingehende Pakete gleichzeitig von mehreren Prozessoren auf dem Server verarbeitet werden. Ausführliche Informationen finden Sie unter "Verbesserungen bei der[empfangsseitigen Skalierung in Windows Server".](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh997036(v=ws.11)) Ausführliche Informationen zum Aktivieren von RSS finden Sie in der Dokumentation zum Netzwerkadapter. 
