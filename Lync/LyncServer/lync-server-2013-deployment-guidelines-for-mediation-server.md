---
title: 'Lync Server 2013: Bereitstellungsrichtlinien für Vermittlungsserver'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment guidelines for Mediation Server
ms:assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398622(v=OCS.15)
ms:contentKeyID: 48184606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0404590ab5b3208de989093df7ede55a3aee2f54
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038227"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-guidelines-for-mediation-server-in-lync-server-2013"></a>Bereitstellungsrichtlinien für Vermittlungsserver in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-12_

In diesem Thema werden Planungsrichtlinien für Vermittlungsserver Bereitstellung beschrieben. Nachdem Sie diese Richtlinien überprüft haben, empfehlen wir Ihnen, das Planungs Tool zum Erstellen und anzeigen möglicher alternativer Topologien zu verwenden, die als Modelle für die endgültige, von Ihnen bereitzustellende Topologie fungieren können.

<div>

## <a name="collocated-or-stand-alone-mediation-server"></a>Verbundenes oder eigenständiges Vermittlungsserver?

Der Vermittlungsserver ist standardmäßig mit anderen Servern auf dem Standard Edition-Server oder Front-End-Server in einem Front-End-Pool an zentralen Standorten verbunden. Die Anzahl der PSTN-Anrufe (Public Switched Telephone Network), die verarbeitet werden können, und die Anzahl der im Pool erforderlichen Computer hängen von folgenden Anforderungen ab:

  - Die Anzahl der Gateway-Peers, die vom Vermittlungsserver Pool gesteuert werden

  - Die großen Datenverkehrs Zeiträume über diese Gateways

  - Der Prozentsatz der Anrufe, bei denen es sich um Anrufe handelt, deren Medien die Vermittlungsserver umgehen

Achten Sie bei der Planung darauf, die Anforderungen an die Medienverarbeitung für PSTN-Anrufe und A/V-Konferenzen, die nicht für die medienumgehung konfiguriert sind, sowie die Verarbeitung zur Behandlung von Signalisierungs Interaktionen für die Anzahl der Anrufe, die unterstützt werden müssen, zu berücksichtigen. Wenn nicht genügend CPU vorhanden ist, müssen Sie einen eigenständigen Pool von Vermittlungsservern bereitstellen. und PSTN-Gateways, IP-Nebenstellenanlagen und SBCS müssen in Untergruppen unterteilt werden, die von den verbundenen Vermittlungsservern in einem Pool und den eigenständigen Vermittlungsservern in einem oder mehreren eigenständigen Pools gesteuert werden.

Wenn Sie PSTN-Gateways, IP-Nebenstellenanlagen oder Session Border Controller (SBCS) bereitgestellt haben, die nicht die richtigen Funktionen für die Interaktion mit einem Pool von Vermittlungsservern unterstützen, einschließlich der folgenden, müssen Sie einem eigenständigen Pool zugeordnet sein, der aus eines einzelnen Vermittlungsserver:

  - Ausführen von Netzwerkschicht Domain Name System (DNS) Lastenausgleich über Vermittlungsserver in einem Pool (oder anderweitige gleichmäßige Weiterleitung des Datenverkehrs an alle Vermittlungsserver in einem Pool)

  - Akzeptieren von Datenverkehr von jedem Vermittlungsserver in einem Pool

Mit dem Microsoft lync Server 2013 Planungs Tool können Sie auswerten, ob abstimmen die Vermittlungsserver mit Ihrem Front-End-Pool die Last verarbeiten kann. Falls Ihre Umgebung diese Anforderungen nicht erfüllen kann, müssen Sie einen eigenständigen Vermittlungsserverpool bereitstellen.

</div>

<div>

## <a name="central-site-and-branch-site-considerations"></a>Überlegungen zum zentralen Standort und Zweigstellenstandort

Vermittlungsserver am zentralen Standort können zum Weiterleiten von Anrufen für IP-Nebenstellenanlagen oder PSTN-Gateways an Zweigstellenstandorten verwendet werden. Bei Bereitstellung von SIP-Trunks müssen Sie jedoch einen Vermittlungsserver an dem Standort bereitstellen, der als Endpunkt für die einzelnen Trunks dient. Bei Einsatz eines Vermittlungsservers am zentralen Standort zum Weiterleiten von Anrufen für eine IP-Nebenstellenanlage oder ein PSTN-Gateway an einem Zweigstellenstandort ist keine Medienumgehung erforderlich. Wenn Sie die Medienumgehung jedoch aktivieren können, wird die Latenz für den Medienpfad reduziert und somit eine bessere Medienqualität erreicht, da der Medienpfad nicht länger dem Signalpfad folgen muss. Zudem wird durch die Medienumgehung die Verarbeitungslast des Pools verringert.

<div>


> [!NOTE]  
> Die Medienumgehung kann nicht mit jedem PSTN-Gateway, IP-PBX und SBC interagieren. Microsoft hat eine Reihe von PSTN-Gateways und SBCS mit zertifizierten Partnern getestet und einige Tests mit Cisco IP-PBX durchgeführt. Die medienumgehung wird nur mit Produkten und Versionen unterstützt, die unter Unified Communications Open Interoperability Program <A href="http://go.microsoft.com/fwlink/p/?linkid=268730">http://go.microsoft.com/fwlink/p/?LinkId=268730</A>– lync Server unter aufgeführt sind.



</div>

Wenn Ausfallsicherheit für Zweigstellenstandorte erforderlich ist, muss eine Survivable Branch Appliance oder eine Kombination aus einem Front-End-Server, einem Vermittlungsserver und einem Gateway am Zweigstellenstandort bereitgestellt werden. (Die Annahme mit Ausfallsicherheit für Zweigstellenstandorte besteht darin, dass Anwesenheit und Konferenzen am Standort nicht belastbar sind.) Anleitungen zur Planung von Zweigstellenstandorten für VoIP finden Sie unter [Planning for Branch-Site Voice Resilienz in lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).

Wenn die IP-Nebenstellenanlage für Interaktionen mit einer IP-Nebenstellenanlage nicht ordnungsgemäß unterstützt frühe Medien Interaktionen mit mehreren frühen Dialogen und RFC 3960-Interaktionen, kann es sein, Clipping der ersten Worte der Begrüßung für eingehende Anrufe von der IP-Nebenstellenanlage zu lync-Endpunkten. Dieses Verhalten kann gravierender sein, wenn eine Vermittlungsserver an einem zentralen Standort Routing Anrufe für eine IP-Nebenstellenanlage ist, bei der die Route an einem Zweigstellenstandort beendet wird, da mehr Zeit erforderlich ist, um die Signalisierung abzuschließen. Wenn dieses Verhalten auftritt, ist die Bereitstellungeines Vermittlungsservers am Zweigstellenstandort die einzige Möglichkeit, das Clipping der ersten Wörter zu reduzieren.

Wenn der zentrale Standort über eine TDM-Nebenstellenlage verfügt oder die Notwendigkeit eines PSTN-Gateways durch die IP-Nebenstellenanlage nicht eliminiert wird, müssen Sie ein Gateway zur Anrufroute hinzufügen, das mit dem Vermittlungsserver und der Nebenstellenanlage verbunden ist.

<div>


> [!NOTE]  
> Um die Medien Leistung eigenständiger Vermittlungsserver zu verbessern, sollten Sie die Receive-Side Scaling (RSS) auf den Netzwerkadaptern auf diesen Servern aktivieren. Mit RSS können eingehende Pakete gleichzeitig von mehreren Prozessoren auf dem Server verarbeitet werden. Ausführliche Informationen finden Sie unter "Verbesserungen bei der Empfangs seitigen <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?LinkId=268731</A>Skalierung in Windows Server" unter. Ausführliche Informationen zum Aktivieren von RSS finden Sie in der Dokumentation zu Ihrem Netzwerkadapter.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

