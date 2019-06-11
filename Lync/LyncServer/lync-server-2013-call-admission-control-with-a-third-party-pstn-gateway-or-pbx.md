---
title: Anrufsteuerung mit einem PSTN-Gateway oder einer Nebenstellenanlage eines Drittanbieters
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call admission control with a third-party PSTN gateway or PBX
ms:assetid: 95dc4ceb-bcad-48ee-86ec-af911727f853
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398762(v=OCS.15)
ms:contentKeyID: 48184850
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1996b56a50dbe616c8dc6e9b9b1c779c564b185
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839711"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-in-lync-server-2013-with-a-third-party-pstn-gateway-or-pbx"></a>Anrufsteuerung mit einem PSTN-Gateway oder einer Nebenstellenanlage eines Drittanbieters in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-20_

In diesem Thema werden Beispiele für die Bereitstellung der Anrufsteuerung (Call Admission Control, CAC) auf der Verbindung zwischen der Gatewayschnittstelle des Vermittlungsservers und einem Drittanbieter-PSTN-Gateway  (Public Switched Telephone Network) oder einer Festnetztelefonanlage beschrieben.

<div>

## <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a>Fall 1: Anrufsteuerung zwischen dem Vermittlungsserver und einem PSTN-Gateway

Die Anrufsteuerung kann auf der WAN-Verbindung von der Gatewayschnittstelle des Vermittlungsservers zu einer Drittanbieter-Nebenstellenanlage oder einem PSTN-Gateway bereitgestellt werden.

**Fall 1: Anrufsteuerung zwischen dem Vermittlungsserver und einem PSTN-Gateway**

![Fall 1: CAC zwischen dem PSTN-Gateway des Vermittlungsservers] (images/Gg398762.4bebf9ee-2732-4ea6-bbe5-0269b2903d8c(OCS.15).jpg "Fall 1: CAC zwischen dem PSTN-Gateway des Vermittlungsservers")

In diesem Beispiel wird CAC zwischen dem Vermittlungs Server und einem PSTN-Gateway angewendet. Wenn ein lync-Clientbenutzer am Netzwerkstandort 1 einen PSTN-Anruf über das PSTN-Gateway in Network Site 2 ablegt, fließt das Medium über die WAN-Verbindung. Für jede PSTN-Sitzung werden daher zwei Prüfungen in Bezug auf die Anrufsteuerung durchgeführt:

  - Zwischen der lync-Clientanwendung und dem Vermittlungs Server

  - Zwischen dem Vermittlungs Server und dem PSTN-Gateway

Dies gilt sowohl für eingehende PSTN-Anrufe an einen Client an Netzwerkstandort 1 als auch für ausgehende PSTN-Anrufe, die von einer Clientanwendung an Netzwerkstandort 1 aus getätigt werden.

<div>


> [!NOTE]
> Stellen Sie sicher, dass das IP-Subnetz, dem das PSTN-Gateway angehört, konfiguriert und Netzwerkstandort 2 zugeordnet ist.<BR>Stellen Sie sicher, dass das IP-Subnetz, zu dem beide Schnittstellen des Vermittlungsservers gehören, konfiguriert ist und dem Netzwerkstandort 1 zugeordnet ist.<BR>Ausführliche Informationen finden Sie unter <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Zuordnen eines Subnetzes zu einer Netzwerk Website in lync Server 2013</A>.



</div>

</div>

<div>

## <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a>Fall 2: CAC zwischen dem Vermittlungs Server und einer Drittanbieter-Telefonanlage mit medienendpunkt

Diese Konfiguration ähnelt Fall 1. In beiden Fällen weiß der Vermittlungsserver, welches Gerät Medien am gegenüberliegenden Ende der WAN-Verbindung beendet, und die IP-Adresse des PSTN-Gateways oder der Telefonanlage mit Media Termination Point (MTP) wird auf dem Vermittlungsserver als nächster Hop konfiguriert.

**Fall 2: Anrufsteuerung zwischen dem Vermittlungsserver und einer Drittanbieter-Nebenstellenanlage mit Medienendpunkt**

![Fall 2: CAC zwischen Vermittlungs Server-PBX mit MTP] (images/Gg398762.1c0b5263-c053-4cca-842f-85dd670760c8(OCS.15).jpg "Fall 2: CAC zwischen Vermittlungs Server-PBX mit MTP")

In diesem Beispiel wird CAC zwischen dem Vermittlungs Server und der PBX/MTP angewendet. Wenn ein lync-Clientbenutzer an der Netzwerk Website 1 einen PSTN-Anruf über die Telefonanlage/MTP in der Netzwerk Website 2 platziert, fließt das Medium über die WAN-Verbindung. Für jede PSTN-Sitzung werden daher zwei Prüfungen der Anrufsteuerung durchgeführt:

  - Zwischen der lync-Clientanwendung und dem Vermittlungs Server

  - Zwischen dem Vermittlungs Server und der PBX/MTP

Dies gilt sowohl für eingehende PSTN-Anrufe an einen Client an Netzwerkstandort 1 als auch für ausgehende PSTN-Anrufe, die von einem Client an Netzwerkstandort 1 aus getätigt werden.

<div>


> [!NOTE]
> Stellen Sie sicher, dass das IP-Subnetz, dem der Medienendpunkt angehört, konfiguriert und Netzwerkstandort 2 zugeordnet ist.<BR>Stellen Sie sicher, dass das IP-Subnetz, zu dem beide Schnittstellen des Vermittlungsservers gehören, konfiguriert ist und dem Netzwerkstandort 1 zugeordnet ist.<BR>Ausführliche Informationen finden Sie unter <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Zuordnen eines Subnetzes zu einer Netzwerk Website in lync Server 2013</A>.



</div>

</div>

<div>

## <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a>Fall 3: CAC zwischen dem Vermittlungs Server und einer Drittanbieter-Telefonanlage ohne medienendpunkt

Fall 3 unterscheidet sich leicht von den ersten beiden Fällen. Wenn kein MTP auf der Drittanbieter-Telefonanlage vorhanden ist, kann der Vermittlungs Server für eine ausgehende Sitzungs Anfrage an die Drittanbieter-PBX-Anlage nicht wissen, wo Medien in der PBX-Grenze beendet werden. In diesem Fall fließt das Medium direkt zwischen dem Vermittlungs Server und dem Endpunktgerät eines Drittanbieters.

**Fall 3: Anrufsteuerung zwischen dem Vermittlungsserver und einer Drittanbieter-Nebenstellenanlage ohne Medienendpunkt**

![Fall 3: CAC zwischen Vermittlungs Server-PBX No MTP] (images/Gg398762.f4bcf800-3a68-4037-bb3f-adb2fdf50d32(OCS.15).jpg "Fall 3: CAC zwischen Vermittlungs Server-PBX No MTP")

Wenn in diesem Beispiel ein lync-Clientbenutzer am Netzwerkstandort 1 einen Benutzer über die Telefonanlage anruft, kann der Vermittlungsserver CAC-Prüfungen nur auf dem Proxy-Leg durchführen (zwischen der lync-Clientanwendung und dem Vermittlungsserver). Da der Vermittlungsserver keine Informationen über das Endpunktgerät aufweist, während die Sitzung angefordert wird, können keine CAC-Prüfungen für die WAN-Verbindung (zwischen dem Vermittlungsserver und dem Endpunkt des Drittanbieters) vor der Einrichtung des Anrufs durchgeführt werden. Nach dem Einrichten der Sitzung vereinfacht der Vermittlungs Server jedoch die Berechnung der im trunk verwendeten Bandbreite.

Bei Anrufen, die vom Endpunkt eines Drittanbieters stammen, sind die Informationen zu diesem Endpunktgerät zum Zeitpunkt der Sitzungsanforderung verfügbar, und die CAC-Prüfung kann sowohl auf den Seiten des Vermittlungsservers ausgeführt werden.

<div>


> [!NOTE]
> Stellen Sie sicher, dass das IP-Subnetz, dem die Endpunktgeräte angehören, konfiguriert und Netzwerkstandort 2 zugeordnet ist.<BR>Stellen Sie sicher, dass das IP-Subnetz, zu dem beide Schnittstellen des Vermittlungsservers gehören, konfiguriert ist und dem Netzwerkstandort 1 zugeordnet ist.<BR>Ausführliche Informationen finden Sie unter <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Zuordnen eines Subnetzes zu einer Netzwerk Website in lync Server 2013</A>.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

