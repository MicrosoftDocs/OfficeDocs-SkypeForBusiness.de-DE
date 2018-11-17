---
title: Bereitstellungsrichtlinien für den Vermittlungsserver in Skype für Business Server
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
description: In diesem Thema wird beschrieben, Planungsleitfäden für die Bereitstellung des Vermittlungsservers.
ms.openlocfilehash: 0b22a285be9e04929d53faffb58e0f7a3f8f3750
ms.sourcegitcommit: 6ad3ce36140464319f5957652331acd6a4273f82
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2018
ms.locfileid: "26561900"
---
# <a name="deployment-guidelines-for-mediation-server-in-skype-for-business-server"></a>Bereitstellungsrichtlinien für den Vermittlungsserver in Skype für Business Server
 
In diesem Thema wird beschrieben, Planungsleitfäden für die Bereitstellung des Vermittlungsservers.
  
## <a name="collocated-or-stand-alone-mediation-server"></a>Verbundenen oder eigenständigen Vermittlungsserver?

Vermittlungsserver ist, wird standardmäßig auf dem Standard Edition-Server oder Front-End-Server in einem Front-End-Pool an zentralen Standorten gemeinsam ausgeführt. Die Anzahl von Anrufen über das Telefonfestnetz (Public Switched Telephone Network, PSTN), die verarbeitet werden können, und die Anzahl erforderlicher Computer im Pool hängt von folgenden Faktoren ab:
  
- Die Anzahl von gatewaypeers, die der vermittlungsserverpool steuert.
    
- Datenverkehr zu Spitzenzeiten, der über diese Gateways verarbeitet wird
    
- Der Prozentsatz an anrufen, deren Medien des Vermittlungsservers Umgehung.
    
Berücksichtigen Sie bei der Planung unbedingt die Medienverarbeitungsanforderungen für PSTN-Anrufe und A/V-Konferenzen, die eine Medienumgehung nicht unterstützen, sowie die erforderliche Leistung zur Verarbeitung von Signalinteraktionen für die Anzahl von Anrufen zu Spitzenzeiten, die unterstützt werden müssen. Wenn Sie nicht über genügend CPU verfügen, müssen Sie einen eigenständigen Vermittlungsserver-Pool bereit. Darüber hinaus müssen PSTN-Gateways, IP-Nebenstellenanlagen und SBCs in Untergruppen aufgeteilt werden, die durch die verbundenen Vermittlungsserver in einem Pool und den eigenständigen Vermittlungsserver in einen oder mehrere eigenständigen Pools gesteuert werden.
  
Wenn Sie bereitgestellt PSTN-Gateways, IP-PBX-Anlagen oder Session Border Controller (SBCs), in denen die Fähigkeit zur Interaktion mit einem Pool von Vermittlungsservern fehlt, müssen sie einen eigenständigen Pool bestehend aus einem einzelnen Mediation Server zugeordnet werden soll. Einige der Dinge, die von Ihren PSTN-Gateways, IP-Nebenstellenanlagen oder SBCs erledigt werden müssen, sind:
  
- Ausführen der Vermittlungsschicht Domain Name System (DNS) Lastenausgleich über Mediation Server in einem Pool (oder anderweitige einheitliche Weiterleitung des Datenverkehrs an alle Vermittlungsserver in einem Pool).
    
- Akzeptieren von Datenverkehr von einem beliebigen Vermittlungsserver in einem Pool.
    
Die Skype für Business Planungstool können Sie ermitteln, ob die Verbindung des Vermittlungsservers mit den Front-End-Pool die Last verarbeiten kann. Wenn Ihre Umgebung diesen Anforderungen nicht erfüllen kann, müssen Sie einen eigenständigen vermittlungsserverpool bereitstellen.
  
## <a name="central-site-and-branch-site-considerations"></a>Überlegungen zum zentralen Standort und Zweigstellenstandort

 Vermittlungsserver am zentralen Standort können für das Anrufrouting für IP-Nebenstellenanlagen oder PSTN-Gateways an Zweigniederlassungen verwendet werden. Wenn Sie SIP-Trunks bereitstellen, müssen Sie jedoch einen Vermittlungsserver am Standort bereitstellen, auf dem jeden Trunk beendet wird. Einen Vermittlungsserver am zentralen Standort Weiterleiten von Anrufen für eine IP-Nebenstellenanlage oder PSTN-Gateway an einem Zweigstellenstandort ist es nicht erforderlich, die Verwendung von Medien umgehen, eine medienumgehung wird jedoch empfohlen. Der Grund: Wenn Sie die Medienumgehung aktivieren können, wird die Latenz für den Medienpfad reduziert und somit eine bessere Medienqualität erreicht, da der Medienpfad nicht mehr dem Signalpfad folgen muss. Zudem wird durch die Medienumgehung die Verarbeitungslast des Pools verringert.
  
> [!NOTE]
> Die Medienumgehung funktioniert nicht mit allen PSTN-Gateways, IP-Nebenstellenanlagen oder SBCs. Microsoft hat eine Reihe von PSTN-Gateways und SBCs mit zertifizierten Partnern getestet und einige Tests mit IP-Nebenstellenanlagen von Cisco durchgeführt. Die medienumgehung wird nur mit Produkten unterstützt und aufgeführtes Dokument Versionen Unified Communications Open Interoperability Program – Lync Server unter [Explore getestet, Geräte, Infrastruktur und Tools, die Unterstützung und Erweitern Ihrer Skype Business wünschen](http://partnersolutions.skypeforbusiness.com/solutionscatalog). 
  
Wenn Zweigstellenstandorte erforderlich ist, muss eine Survivable Branch Appliance oder eine Kombination aus einem Front-End-Server, einen Vermittlungsserver und ein Gateway am Zweigstellenstandort bereitgestellt werden. (Die Annahme mit Zweigstellenstandorte ist, dass die Anwesenheit und Konferenzen nicht am Standort ausfallsichere sind.) Anleitung zum Planen von VoIP Zweigstellenstandort finden Sie unter [Planen für Enterprise Voice Resiliency in Skype für Business Server](../enterprise-voice-solution/enterprise-voice-resiliency.md).
  
Für Interaktionen mit einer IP-Nebenstellenanlage Wenn die IP-Nebenstellenanlage nicht ordnungsgemäß early Media-Interaktionen mit mehreren frühe Dialoge und damit zusammenhängende Interaktionen RFC 3960, unterstützt möglich Zuschneiden des ersten Wörter der die Begrüßung für eingehende Anrufe von der IP-Nebenstellenanlage an Lync-Endpunkte. Dieses Verhalten kann Schweregrad, wenn einem Vermittlungsserver an einem zentralen Standort Weiterleiten von Anrufen für eine IP-Nebenstellenanlage beendet wird, in dem die Route an einem Zweigstellenstandort ist, da mehr Zeit benötigt wird, für die Durchführung Signale sein. Wenn Sie dieses Verhalten auftreten, ist die Bereitstellung eines Vermittlungsservers am Zweigstellenstandort die einzige Möglichkeit zur Reduzierung des ersten Wörter clipping.
  
Schließlich müssen verfügt Ihre zentralen Standort eine TDM-Nebenstellenanlage oder der IP-Nebenstellenanlage kein PSTN-Gateway erforderlich ist, klicken Sie dann auf das Herstellen einer Verbindung mit Vermittlungsserver und der Nebenstellenanlage Route für Anrufe ein Gateway bereitstellen.
  
> [!NOTE]
> Um die Medienqualität von eigenständigen Vermittlungsservern zu verbessern, sollten Sie RSS (Receive-Side Scaling) für die Netzwerkadapter dieser Server aktivieren. Mit RSS können eingehende Pakete gleichzeitig von mehreren Prozessoren auf dem Server verarbeitet werden. Weitere Informationen hierzu finden Sie unter "[Receive-Side Skalierung Erweiterungen in Windows Server](https://go.microsoft.com/fwlink/p/?LinkId=268731)". Weitere Informationen zum Aktivieren von RSS finden Sie in der Dokumentation zu Ihrem Netzwerkadapter. 
  

