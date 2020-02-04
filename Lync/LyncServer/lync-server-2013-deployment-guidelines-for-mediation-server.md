---
title: 'Lync Server 2013: Bereitstellungsrichtlinien für den Vermittlungsserver'
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
ms.openlocfilehash: 3c91ea4368d96e6a558a25eda86d163e4ced4cb8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762673"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-guidelines-for-mediation-server-in-lync-server-2013"></a>Bereitstellungsrichtlinien für den Vermittlungsserver in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-12_

In diesem Thema werden Planungsrichtlinien für die Vermittlungs Server Bereitstellung beschrieben. Nachdem Sie diese Richtlinien überprüft haben, empfehlen wir, dass Sie das Planungs Tool verwenden, um mögliche Alternative Topologien zu erstellen und anzuzeigen, die als Modelle dafür dienen können, wie die endgültige, von Ihnen bereitzustellende Topologie aussehen würde.

<div>

## <a name="collocated-or-stand-alone-mediation-server"></a>Oder eigenständigen Vermittlungs Server?

Der Vermittlungsserver befindet sich standardmäßig auf dem Standard Edition-Server oder Front-End-Server in einem Front-End-Pool an zentralen Standorten. Die Anzahl von Anrufen über das Telefonfestnetz (Public Switched Telephone Network, PSTN), die verarbeitet werden können, und die Anzahl erforderlicher Computer im Pool hängt von folgenden Faktoren ab:

  - Die Anzahl der Gateway-Peers, die vom Vermittlungs Server Pool gesteuert werden

  - Datenverkehr zu Spitzenzeiten, der über diese Gateways verarbeitet wird

  - Der Prozentsatz der Anrufe, deren Medien den Vermittlungs Server umgehen

Berücksichtigen Sie bei der Planung unbedingt die Medienverarbeitungsanforderungen für PSTN-Anrufe und für A/V-Konferenzen, die nicht für eine Medienumgehung konfiguriert sind, sowie die erforderliche Leistung zur Verarbeitung von Signalinteraktionen für die Anzahl von Anrufen zu Spitzenzeiten, die unterstützt werden müssen. Wenn nicht genügend CPU vorhanden ist, müssen Sie einen eigenständigen Pool von Vermittlungsservern bereitstellen. und PSTN-Gateways, IP-PBX-Anlagen und SBCS müssen in Teilmengen aufgeteilt werden, die von den zusammengefassten Vermittlungsservern in einem Pool und den eigenständigen Vermittlungsservern in einem oder mehreren eigenständigen Pools gesteuert werden.

Wenn Sie PSTN-Gateways, IP-PBX-Anlagen oder SBCS (Session Border Controllers) bereitgestellt haben, die nicht die richtigen Funktionen für die Interaktion mit einem Pool von Mediations Servern, einschließlich der folgenden, unterstützen, müssen Sie einem eigenständigen Pool zugeordnet sein, bestehend aus eines einzelnen Vermittlungsservers:

  - Durchführen von DNS (Domain Name System)-Lastenausgleich auf Netzwerkebene über Vermittlungsserver in einem Pool (oder anderweitiges Weiterleiten des Datenverkehrs an alle Vermittlungsserver in einem Pool)

  - Akzeptieren von Datenverkehr von einem beliebigen Vermittlungs Server in einem Pool

Sie können das Planungs Tool Microsoft lync Server 2013 verwenden, um zu evaluieren, ob abstimmen dem Vermittlungsserver mit dem Front-End-Pool die Last verarbeiten kann. Wenn Ihre Umgebung diese Anforderungen nicht erfüllen kann, müssen Sie einen eigenständigen Vermittlungs Server Pool bereitstellen.

</div>

<div>

## <a name="central-site-and-branch-site-considerations"></a>Überlegungen zum zentralen Standort und Zweigstellenstandort

Vermittlungsserver am zentralen Standort können verwendet werden, um Anrufe für IP-PBX-oder PSTN-Gateways an Zweigstellen zu leiten. Wenn Sie jedoch SIP-Trunks bereitstellen, müssen Sie einen Vermittlungs Server an der Website bereitstellen, auf der jeder trunk beendet wird. Die Verwendung eines Vermittlungsservers an der zentralen Standort Route für Anrufe an ein IP-PBX-oder PSTN-Gateway an einer Zweigstelle erfordert keine medienumgehung. Wenn Sie jedoch die medienumgehung aktivieren können, wird dadurch die Latenz des Medien Pfads verringert und dadurch die Medienqualität verbessert, da der Medienpfad nicht mehr dem Signalisierungs Pfad folgen muss. Zudem wird durch die Medienumgehung die Verarbeitungslast des Pools verringert.

<div>


> [!NOTE]  
> Die Medienumgehung funktioniert nicht mit allen PSTN-Gateways, IP-Nebenstellenanlagen oder SBCs. Microsoft hat eine Reihe von PSTN-Gateways und SBCs mit zertifizierten Partnern getestet und einige Tests mit IP-Nebenstellenanlagen von Cisco durchgeführt. Die medienumgehung wird nur mit Produkten und Versionen unterstützt, die unter Unified Communications Open Interoperability Program – <A href="http://go.microsoft.com/fwlink/p/?linkid=268730">http://go.microsoft.com/fwlink/p/?LinkId=268730</A>lync Server unter aufgeführt sind.



</div>

Wenn die Stabilität des Zweigstellen Standorts erforderlich ist, muss eine Survivable Branch-Appliance oder eine Kombination aus einem Front-End-Server, einem Vermittlungsserver und einem Gateway an der Zweigstelle bereitgestellt werden. (Die Annahme, dass die Stabilität des Zweigstellen Standorts davon ausgeht, dass Anwesenheit und Konferenzen auf der Website nicht belastbar sind.) Anleitungen zur Planung von Zweigstellen für Sprachanrufe finden Sie unter [Planen der sprach Sicherheit in der Zweigstelle in lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).

Für Interaktionen mit einer IP-PBX-Anlage, wenn die IP-Telefonanlage nicht ordnungsgemäß frühe Medien Interaktionen mit mehreren frühen Dialogfeldern und RFC 3960-Interaktionen unterstützt, können die ersten Wörter der Ansage für eingehende Anrufe von der IP-PBX zu lync-Endpunkten abgeschnitten werden. Dieses Verhalten kann gravierender sein, wenn ein Vermittlungs Server an einem zentralen Standort Routing Anrufe für eine IP-PBX-Anlage durchführt, bei der die Route an einer Zweigstelle beendet wird, da für die Signalisierungs Ausführung mehr Zeit benötigt wird. Wenn dieses Verhalten auftritt, ist die Bereitstellungeines Vermittlungsservers auf der Verzweigungs Website die einzige Möglichkeit, das Clipping der ersten Wörter zu reduzieren.

Wenn Ihre zentrale Website über eine TDM-Telefonanlage verfügt oder wenn Ihre IP-Telefonanlage nicht die Notwendigkeit eines PSTN-Gateways beseitigt, müssen Sie ein Gateway auf der Anrufroute bereitstellen, die den Vermittlungs Server und die Telefonanlage verbindet.

<div>


> [!NOTE]  
> Um die Medienqualität von eigenständigen Vermittlungsservern zu verbessern, sollten Sie RSS (Receive-Side Scaling) für die Netzwerkadapter dieser Server aktivieren. Mit RSS können eingehende Pakete gleichzeitig von mehreren Prozessoren auf dem Server verarbeitet werden. Ausführliche Informationen finden Sie unter "Verbesserungen bei der Empfangs seitigen <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?LinkId=268731</A>Skalierung in Windows Server" unter. Weitere Informationen zum Aktivieren von RSS finden Sie in der Dokumentation zu Ihrem Netzwerkadapter.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

